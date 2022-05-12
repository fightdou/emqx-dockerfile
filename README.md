# emqx-dockerfile

为了支持 emqx 可以绑定 hostIP，修改官方 [emqx](https://github.com/emqx/emqx) 的 dockerfile

k8s emqx 部署 yaml 中导入环境变量

```
env:
  - name: EMQX_MQTT_PORT
    value: "{{ .Values.service.mqtt | default 1883 }}"
  - name: NODE_IP
    valueFrom:
      fieldRef:
        fieldPath: status.hostIP
```
