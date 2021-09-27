## spring日志级别

```yaml
logging:
  file:
    name: /tmp/ums-app.log
  level:
    root: INFO # 默认的日志级别设置为 INFO
    org:
      springframework: ERROR #  org.springframework 包的日志级别设置成 ERROR
    com:
      example:
        demo: DEBUG    # 业务包的日志级别设置为 DEBUG
```

---