[toc]

# 2022-05-22 如何写R包

> [原文连接](https://www.jianshu.com/p/c0216f42edc5)

只有**R脚本**与**DESCRIPTION**是需要我们仔细准备的，其它内容都可以通过快捷键写入、更新

## 1. 为函数添加说明文档模板

快捷键`Ctrl+Alt+Shift+R`

## 2. 测试编写的函数有没有问题

```R
devtools::load_all()
```

## 3. 为所有函数在man文件夹逐一自动简历Rd文档，更新NAMESPACE文档

```R
devtools::document()
```

## 4. 编写DESCRIPTION文件

## 5. 编写LICENSE（若GITHUB上已创建则跳过）

```R
usethis::use_mit_license() # MIT license
```

## 6. 补充依赖包信息

```R
usethis::use_package(package, type = 'Imports', min_version = NULL)
# example
usethis::use_package('dplyr', type = 'Imports',
                    min_version = '1.0')
```

## 7. check上述文件，检查问题

```R
devtools::
```







