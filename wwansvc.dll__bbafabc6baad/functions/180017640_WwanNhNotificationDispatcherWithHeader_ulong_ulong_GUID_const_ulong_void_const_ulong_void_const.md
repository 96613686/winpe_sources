# WwanNhNotificationDispatcherWithHeader(ulong,ulong,_GUID const *,ulong,void const *,ulong,void const *)

- ea: `0x180017640`
- end: `0x1800177fb`
- name: `?WwanNhNotificationDispatcherWithHeader@@YAXKKPEBU_GUID@@KPEBXK1@Z`
- size: `443`
- prototype: `void(unsigned int, unsigned int, const struct _GUID *, unsigned int, const void *, unsigned int, const void *)`
- caller_count: `112`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d5e8`
- `0x180020540`
- `0x180020bd4`
- `0x180020e2c`
- `0x1800221ec`
- `0x180022a5c`
- `0x180022af0`
- `0x180022d2c`
- `0x180022e40`
- `0x18002303c`
- `0x180023150`
- `0x180023268`
- `0x1800233f0`
- `0x180023b24`
- `0x180024538`
- `0x18002a200`
- `0x18002a3e8`
- `0x18002a528`
- `0x18002c22c`
- `0x18002ca60`
- `0x18002d648`
- `0x18002d884`
- `0x18002da98`
- `0x18002dcb8`
- `0x18002dfb0`
- `0x180033abc`
- `0x180034c38`
- `0x180035014`
- `0x1800358e4`
- `0x18003c028`
- `0x18003c130`
- `0x18003c300`
- `0x18003c51c`
- `0x18003cd6c`
- `0x18003cfd8`
- `0x18003f268`
- `0x18003f32c`
- `0x1800402a0`
- `0x180041a24`
- `0x180044cec`
- `0x18004762c`
- `0x180047720`
- `0x180047784`
- `0x1800477e8`
- `0x180048ecc`
- `0x180049034`
- `0x18004912c`
- `0x180049220`
- `0x180049390`
- `0x180049508`

## callees

- `0x180012300`
- `0x1800131dc`
- `0x180014f1c`
- `0x180017640`
- `0x180018a34`
- `0x18001926c`
- `0x18005ba6c`
- `0x1800b68b4`
- `0x1800b6a0c`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800177db`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800177db`

## string_xrefs

- `0x18001767f`: ` Not sending notification because service is not running. notificationCode = [%d]`
- `0x1800176ab`: ` Not sending notification because Notification Handler component is not initialized. NotificationSource = [%d], NotificationCode = [%d]`
- `0x18001776e`: `Notification dispatcher: No thread found for handlingnotification on interface. Aborting`

## pseudocode

```c

```
