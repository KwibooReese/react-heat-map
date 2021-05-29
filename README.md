HeatMap 日历热图
===

[![Build & Deploy](https://github.com/uiwjs/react-heat-map/workflows/Build%20&%20Deploy/badge.svg)](https://github.com/uiwjs/react-heat-map/actions)
[![Issues](https://img.shields.io/github/issues/uiwjs/react-heat-map.svg)](https://github.com/uiwjs/react-heat-map/issues)
[![Forks](https://img.shields.io/github/forks/uiwjs/react-heat-map.svg)](https://github.com/uiwjs/react-heat-map/network)
[![Stars](https://img.shields.io/github/stars/uiwjs/react-heat-map.svg)](https://github.com/uiwjs/react-heat-map/stargazers)
[![Release](https://img.shields.io/github/release/uiwjs/react-heat-map)](https://github.com/uiwjs/react-heat-map/releases)
[![npm version](https://img.shields.io/npm/v/@uiw/react-heat-map.svg)](https://www.npmjs.com/package/@uiw/react-heat-map)

React component create calendar heatmap to visualize time series data, a la github contribution graph.

## Install

```bash
# Not dependent on uiw.
npm install @uiw/react-heat-map --save
```

## 基础用法

<!--rehype:bgWhite=true&codeSandbox=true&codePen=true-->
```jsx
import ReactDOM from 'react-dom';
import HeatMap from '@uiw/react-heat-map';

const Demo = () => {
  const value = [
    { date: '2016/01/11', count:2, content:['一条消息来了！','一条消息来了！'] },
    { date: '2016/04/11', count:2, content:['一条消息来了！'] },
    { date: '2016/05/01', count:5, content:['需要显示的数据'] },
    { date: '2016/05/02', count:5, content:['空的没有消息'] },
    { date: '2016/05/04', count:11, content:['些放弃的人会这样想'] },
  ];
  return (
    <div>
      <HeatMap value={value} startDate={new Date('2016/01/01')} />
    </div>
  )
};
ReactDOM.render(<Demo />, _mount_);
```

## Props

| 参数 | 说明 | 类型 | 默认值 |
|--------- |-------- |--------- |-------- |
| value | 需要显示的数据，必填 | Array | `[]` |
| rectSize | 方格尺寸 | number | `11` |
| startDate | 开始日期 | Date | `new Date()` |
| endDate | 截止日期 | Date | - |
| space | 方格尺寸之间间隔 | number | `2` | 
| rectProps | 方格节点属性设置 | `React.SVGProps<SVGRectElement>` | `2` |
| weekLables | 周显示 | string[] | `['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat']` | 
| monthLables | 月份显示 | string[] | `['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']` | 
| panelColors | 活跃颜色的深浅 | `Record<number, string>` | `{ 0: '#EBEDF0', 8: '#7BC96F', 4: '#C6E48B', 12: '#239A3B', 32: '#196127' }` | 
| renderRect | 单个方块重新渲染 | `() => React.ReactNode` | - |
## Development

**`development`**

Runs the project in development mode.  

```bash
# Step 1, run first, listen to the component compile and output the .js file
# listen for compilation output type .d.ts file
npm run watch
# Step 2, development mode, listen to compile preview website instance
npm run start
```

**`production`**

Builds the app for production to the build folder.

```bash
npm run build
```

The build is minified and the filenames include the hashes.
Your app is ready to be deployed!


## License

Licensed under the MIT License.
