# arrayToTree
数组转树🌲

## 安装
```shell
npm i -S arr2tree
```

## 快速开始
```javascript
const array = [{
        id: 1,
        name: '蔬菜',
        order: 1
    },
    {
        id: 2,
        name: '土豆',
        pid: 1,
        order: 2
    }, {
        id: 3,
        name: '豆角',
        pid: 1,
        order: 1
    }, {
        id: 4,
        name: '水果',
        order: 2
    }
];

arrayToTree(array);
// 输出:
// 
// [
//     {
//         "id": 1,
//         "name": "蔬菜",
//         "order": 1,
//         "children": [
//             {
//                 "id": 3,
//                 "name": "豆角",
//                 "pid": 1,
//                 "order": 1
//             },
//             {
//                 "id": 2,
//                 "name": "土豆",
//                 "pid": 1,
//                 "order": 2
//             }
//         ]
//     },
//     {
//         "id": 4,
//         "name": "水果",
//         "order": 2
//     }
// ]

```

## 🚀 代码逻辑简要说明
1. 把"根节点"和其余"子节点"分别存储到2个变量(容器).
2. 从根(父)出发, 在"子节点"容器中检查每一个子节点, 找到其对应的父节点, 并存储到父节点对应的children字段中, 不符合的"子节点"继续留到"子节点容器"中.
3. 对children字段中的"节点"进行排序(此处排序暂时用的sort).
4. 递归执行"步骤2和3"直到"子节点容器"为空.
5. 对其他"根节点"重复执行"步骤2/3/4".
