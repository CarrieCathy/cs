<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>todolist</title>
    <style>
        body {
            font-family:  "微软雅黑";
            font-size: 14px;
        }
        input {
            font-size: 14px;
        }
        body,ul,div,html {
            padding: 0;
            margin: 0;
        }

        .main {
            width: 800px;
            margin: 0 auto;
        }
        .text-keyword {
            box-sizing: border-box;
            width: 100%;
            height: 40px;
            padding-left: 40px;
            outline: none;
        }
        li {
            position: relative;
            list-style-type: none;
            line-height: 40px;
            padding: 0 20px;    /*border:1 px solid transparent;*/
            border: 1px solid #000;
        }
        li.status-span {
            float: left;
            width: 10px;
            height: 10px;
            margin: 14px 10px 0 0;
            background: #ccc;
        }
        li.status-span.status-end {
            background: #09f;
        }
        li.close {
            position: absolute;
            right: 20px;
            top: 0;
            color: #f00;
            font-size: 20px;
            line-height: 40px;
            height: 40px;
            cursor: pointer;
            display: none;
        }
        li:hover {
            border:  1px solid #09f;
        }
        li:hover.close {
            display: block;
        }
        
    </style>
</head>
<body>
    <div id="app" class="main">
        <h2>小目标列表</h2>
        <div class="list">
            <h3>添加小目标</h3>
            <input type="text" class="text-keyword"
                             @keyup.enter="addList"
                             v-model="addList"
                             placeholder="输入小目标后，按回车键确认"/>
            <p>共有N个目标</p>
            <p>
                <input type="radio" name="chooseType" checked="true"><label>所有目标</label>
                <input type="radio" name="chooseType"><label>已完成目标</label>
                <input type="radio" name="chooseType"><label>未完成目标</label>
            </p>
        </div>
        <ul>
            <li class="li1" >
                <div>
                    <span class="status-span"></span>
                    <span>HTML5</span>
                    <span class="close">X</span>
                </div>
            </li>
            <li class="li1">
                <div>
                    <span class="status-span"></span>
                    <span>CSS3</span>
                    <span class="close">X</span>
                </div>
            </li>
        </ul>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.5.16/vue.js"></script>
    <script>
    new Vue ({
        el: "#app",
        data () {
            return {
                addText: '',
                prolist: [
                    {name: 'HTML5',status:false},
                    {name: 'CSS3',status:false},
                    {name: 'Vue',status:false}
                ]

            }
        },
        computed: {

        },
        methods: {
            addList  () {
                this.prolist.push({
                    name: this.addText,
                    status: false
                })
                this.addText= " ";
            }
        }
    }) 
    </script>
</body>
</html>
