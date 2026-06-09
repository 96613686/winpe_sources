# CBiometricUnit::WaitForNotification(thread_inside_functions const &,ulong,void *,void *,bool)

- ea: `0x180008414`
- end: `0x180008684`
- name: `?WaitForNotification@CBiometricUnit@@QEAA?AW4_NOTIFICATION_TYPE@1@AEBVthread_inside_functions@@KPEAX1_N@Z`
- size: `624`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007978`
- `0x180046b70`
- `0x180067fa8`
- `0x18007aa30`

## callees

- `0x180008414`
- `0x18003ddf8`
- `0x180055928`
- `0x180060964`
- `0x180068f60`
- `0x1800787d4`
- `0x180078928`
- `0x1800789b8`
- `0x180078b28`
- `0x180079580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800085c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800085c2`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000850c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000850c`

## string_xrefs

- `0x1800085ef`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x18000860f`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x18000865c`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x180008672`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`

## pseudocode

```c

```
