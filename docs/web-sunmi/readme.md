## Registry

- Our public registry: [r.cnpmjs.org](https://r.cnpmjs.org), syncing from [registry.npmjs.com](https://registry.npmjs.com)
- [cnpmjs.org](/) version: <span id="app-version"></span>
- [Node.js](https://nodejs.org) version: <span id="node-version"></span>
- For developers in China, please visit [the China mirror](https://npm.taobao.org). 中国用户请访问[国内镜像站点](https://npm.taobao.org)。
- Use the private npm service provided by Alibaba Cloud DevOps which build with cnpm. [https://packages.aliyun.com/](https://packages.aliyun.com/?channel=pd_cnpm_github)

<div class="ant-table" style="margin-bottom: 15px;">
<table class="downloads">
  <tbody class="ant-table-tbody">
    <tr>
      <td class="count" id="total-packages"></td><td>total packages</td>
      <td class="count" id="total-versions"></td><td>total package versions</td>
      <td class="count" id="total-deletes"></td><td>total delete packages</td>
    </tr>
    <tr>
      <td class="count"></td><td> downloads today</td>
      <td class="count"></td><td> downloads in this week</td>
      <td class="count"></td><td> downloads in this month</td>
    </tr>
    <tr>
      <td class="count"></td><td> downloads in the last day</td>
      <td class="count"></td><td> downloads in the last week</td>
      <td class="count"></td><td> downloads in the last month</td>
    </tr>
  </tbody>
</table>
</div>

<div class="sync" style="display:none;">
  <h3>Sync Status</h3>
  <p id="sync-model"></p>
  <p>Last sync time is <span id="last-sync-time"></span>. </p>
  <div class="ant-alert ant-alert-info syncing">
    <span class="anticon ant-alert-icon anticon-info-circle"></span>
    <span class="ant-alert-description">The sync worker is working in the backend now. </span>
  </div>
  <div class="ant-table">
  <table class="sync-status">
    <tbody class="ant-table-tbody">
      <tr>
        <td><span id="need-sync"></span> packages need to be sync</td>
        <td class="syncing"><span id="left-sync"></span> packages and dependencies waiting for sync</td>
        <td><span id="percent-sync"></span>% progress</td>
      </tr>
      <tr>
        <td><span id="success-sync"></span> packages and dependencies sync successed</td>
        <td><span id="fail-sync"></span> packages and dependencies sync failed</td>
        <td>last success: <span id="last-success-name"></span></td>
      </tr>
    </tbody>
  </table>
  </div>
</div>

<script src="/js/readme.js"></script>

## Usage

### set registry 

```bash
# use npm config
npm config set registry http://registry.npm.sunmi.com/

# or use nrm
npm i nrm -g
nrm add sunmi http://registry.npm.sunmi.com/
nrm use sunmi
```

### install

```bash
$ npm install [pkg]
```

### sync

sync package on web: [sync/connect](/sync/connect)

```bash
$ open http://registry.npm.taobao.org/sync/connect
```

### login / logout

```bash
# 登录用户
$ npm login
> Username: xxx
> Password: xxx
> Email: xxx@xxx.xxx

# 查看当前用户
$ npm whoami

# 登出
$ npm logout
```

### publish / unpublish

Only `admin` user can unpublish package to private registry.

```bash
$ npm publish [pkg]
$ npm unpublish [pkg]
```

### owner

Set maintainer of package

```bash
# 添加维护者
$ npm owner add <user> [<@scope>/]<pkg>

# 移除维护者
$ npm owner rm <user> [<@scope>/]<pkg>

# 查看维护者
$ npm owner ls [<@scope>/]<pkg>
```

### Other commands

Support all the other npm commands. e.g.:

```bash
$ npm info [<@scope>/]<pkg>
```
