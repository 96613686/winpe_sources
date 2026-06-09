# TimezoneDeterminer::StopServiceTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180015750`
- end: `0x180015799`
- name: `?StopServiceTimerCallback@TimezoneDeterminer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `73`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, struct Cache **Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000cfec`
- `0x180011b0c`
- `0x180015750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015781`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015781`

## pseudocode

```c
void __fastcall TimezoneDeterminer::StopServiceTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        struct Cache **Context,
        PTP_TIMER Timer)
{
  _BYTE v3[32]; // [rsp+20h] [rbp-98h] BYREF
  __int64 v4; // [rsp+40h] [rbp-78h]
  __int64 v5; // [rsp+50h] [rbp-68h]

  Cache::Lock(*Context, (Cache::Proxy *)v3);
  if ( *(_BYTE *)(v5 + 1) && !*(_BYTE *)(v4 + 1) )
    SetEvent(ghSvcStopEvent);
  Cache::Proxy::~Proxy((Cache::Proxy *)v3);
}

```

## disassembly

```asm
0x180015750  sub     rsp, 0B8h
0x180015757  mov     rcx, [rdx]
0x18001575a  lea     rdx, [rsp+0B8h+var_98]
0x18001575f  call    ?Lock@Cache@@QEAA?AVProxy@1@XZ; Cache::Lock(void)
0x180015764  mov     rax, [rsp+0B8h+var_68]
0x180015769  cmp     byte ptr [rax+1], 0
0x18001576d  jz      short loc_180015787
0x18001576f  mov     rax, [rsp+0B8h+var_78]
0x180015774  cmp     byte ptr [rax+1], 0
0x180015778  jnz     short loc_180015787
0x18001577a  mov     rcx, cs:?ghSvcStopEvent@@3PEAXEA; hEvent
0x180015781  call    cs:__imp_SetEvent
0x180015787  lea     rcx, [rsp+0B8h+var_98]; this
0x18001578c  call    ??1Proxy@Cache@@QEAA@XZ; Cache::Proxy::~Proxy(void)
0x180015791  add     rsp, 0B8h
0x180015798  retn
```
