# quickly-template

一个根据已有模板快速生成新的模块的命令行工具

## 命令概览

`$ qt new <template> <name> [target]`

- `$ qt new page new-page` 以`page`为模板创建一下新模块`new-page`并输出到当前目录
- `$ qt new pa new-page` 同样是以`page`为模板创建一下新模块`new-page`并输出到当前目录，因为`template`支持简写形式，简写只要满足`startsWith`就会认为其相等的
- `$ qt new page new-page pages` 以`page`为模板创建一下新模块`new-page`并输出到`pages`目录

**详见DEMO**`/example/`

## 模板支持[art-tempate](https://github.com/aui/art-template)编译

```jsx
class page {
    'hi, <%=name%>.'
}
```

```jsx
class page {
    'hi, newPage.'
}
```

## API

```

usage: qt new <template> <name> [target]

Options:
  --version   Show version number                                      [boolean]
  --config    配置文件所在位置
  --root      模板所在根目录,相对目录,基于context来获取root的绝对路径，
                                                             [string] [required]
  --context   默认为process.cwd(), 如果文件qt.config.js存在则为配置文件所在根目录(推荐使用配置文件)
                                                                        [string]
  --target    新生成模块的输出路径，相对路径，默认为process.cwd()
                                                          [string] [default: ""]
  --template  当前使用的模板，模板可选范围即root下面指定的模板，支持简写即当前有模板page那么p,pa,pag等效
                                                                        [string]
  --name      新生成模块的名称                                          [string]
  --rename    为了兼容微信小程序的形式新生成的模块目录下面的文件名字是否全部改变为跟新模块一致，目前有默认检测功能所以也无需手动指定
                                                      [boolean] [default: false]
  --help, -h  Show help                                                [boolean]
  
  ```