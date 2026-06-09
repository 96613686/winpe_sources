# WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::~WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>(void)

- ea: `0x180010acc`
- end: `0x180010adb`
- name: `??1?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@QEAA@XZ`
- size: `15`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001be19`

## callees

- `0x180012c18`

## pseudocode

```c
__int64 WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::~WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>()
{
  return WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfUnsubscribe();
}

```

## disassembly

```asm
0x180010acc  sub     rsp, 28h
0x180010ad0  call    ?WnfUnsubscribe@?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@AEAAXXZ; WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfUnsubscribe(void)
0x180010ad5  nop
0x180010ad6  add     rsp, 28h
0x180010ada  retn
```
