# ServiceStop(void *,uchar)

- ea: `0x1800143a0`
- end: `0x180014429`
- name: `?ServiceStop@@YAXPEAXE@Z`
- size: `137`
- prototype: `void __fastcall(void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x1800010bc`
- `0x1800015c0`
- `0x18000166c`
- `0x1800143a0`
- `0x180014440`
- `0x1800144ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143d1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800143c4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800143c4`

## pseudocode

```c
void __fastcall ServiceStop(void *a1, unsigned int a2)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // edx
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  UpdateServiceStatus(3u, a2, 0x3E8u);
  std::unique_ptr<TzautoupdateWorker>::reset(v2, 0);
  UnregisterWaitEx(ghRegisteredWait, 0);
  CloseHandle(ghSvcStopEvent);
  if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
  {
    v8 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v4,
      (__int64)&dword_180029ABC,
      v5,
      v6,
      (__int64)&v8);
  }
  TraceLoggingUnregister_EventUnregister(v4, v3, v5);
  UpdateServiceStatus(1u, v7, 0);
}

```

## disassembly

```asm
0x1800143a0  sub     rsp, 38h
0x1800143a4  mov     ecx, 3; unsigned int
0x1800143a9  mov     r8d, 3E8h; unsigned int
0x1800143af  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x1800143b4  xor     edx, edx
0x1800143b6  call    ?reset@?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@QEAAXPEAVTzautoupdateWorker@@@Z; std::unique_ptr<TzautoupdateWorker>::reset(TzautoupdateWorker *)
0x1800143bb  mov     rcx, cs:?ghRegisteredWait@@3PEAXEA; WaitHandle
0x1800143c2  xor     edx, edx; CompletionEvent
0x1800143c4  call    cs:__imp_UnregisterWaitEx
0x1800143ca  mov     rcx, cs:?ghSvcStopEvent@@3PEAXEA; hObject
0x1800143d1  call    cs:__imp_CloseHandle
0x1800143d7  mov     eax, cs:dword_180030000
0x1800143dd  cmp     eax, 5
0x1800143e0  jbe     short loc_180014414
0x1800143e2  mov     rdx, 200000000000h
0x1800143ec  call    _tlgKeywordOn
0x1800143f1  test    al, al
0x1800143f3  jz      short loc_180014414
0x1800143f5  lea     rax, [rsp+38h+arg_10]
0x1800143fa  mov     [rsp+38h+arg_10], 1000000h
0x180014403  lea     rdx, dword_180029ABC
0x18001440a  mov     [rsp+38h+var_18], rax
0x18001440f  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180014414  call    TraceLoggingUnregister_EventUnregister
0x180014419  xor     r8d, r8d; unsigned int
0x18001441c  lea     ecx, [r8+1]; unsigned int
0x180014420  add     rsp, 38h
0x180014424  jmp     ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
```
