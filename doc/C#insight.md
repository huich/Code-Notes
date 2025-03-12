## C# Insight(悟)

### 1、対于数据的新增或者编辑一些字段不能重复的情况,新增时该字段不能和表中的其他数据重复，编辑时除了该条数据不能和其他数据重复（编辑时校验需要排除自己）。

```
     //新增 id传-1
     bool isCode = CodeIsRepetition(-1, model.Code);
     if (isCode)
     {
         err = "编码已存在。";
         return false;
     }
     else
     {
         // 不存在验证编码是否符合规则（不能包含大写的 'Y' 和小写的 'y'，以及大写的 'C' 和小写的 'c'）
         if (model.Code.Contains('Y') || model.Code.Contains('y') || model.Code.Contains('C') || model.Code.Contains('c'))
         {
             this.ShowMsg("编码不能包含 'Y'、'y'、'C' 或 'c'", false);
             return false;
         }
     }

    // 编辑 传该条数据的id
    bool isCode = CodeIsRepetition(model.Id, model.Code);
    if (isCode)
    {
        err = "编码已存在。";
        return false;
    }
    else
    {
        // 不存在验证编码是否符合规则（不能包含大写的 'Y' 和小写的 'y'，以及大写的 'C' 和小写的 'c'）
        if (model.Code.Contains('Y') || model.Code.Contains('y') || model.Code.Contains('C') || model.Code.Contains('c'))
        {
            this.ShowMsg("编码不能包含 'Y'、'y'、'C' 或 'c'", false);
            return false;
        }
    }
``` 

```
   private bool CodeIsRepetition(int Id, string Code)
   {
       IList<Info> infos = InfoHelper.Gets("Id != " + Id + "AND Code = '" + Code + "'");
       if (infos.Count != 0)
       {
           return true;
       }
       return false;
   }
```
