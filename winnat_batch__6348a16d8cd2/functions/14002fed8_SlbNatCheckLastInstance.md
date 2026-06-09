# SlbNatCheckLastInstance

- ea: `0x14002fed8`
- end: `0x14002ff50`
- name: `SlbNatCheckLastInstance`
- size: `120`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400300c4`
- `0x1400323e8`
- `0x140032d2c`

## callees

- `0x14000caa0`
- `0x14002f2f8`
- `0x14002fed8`

## import_xrefs

- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14002ff29`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14002ff29`
- `NETIO!NmrDeregisterClient` at `0x14002ff0a`
- `NETIO!NmrDeregisterClient` at `0x14002ff0a`

## pseudocode

```c
PVOID *__fastcall SlbNatCheckLastInstance(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID *result; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9

  if ( SlbNatGlobalState != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  result = &qword_140026338;
  if ( qword_140026338 == &qword_140026338 && SlbNatIpsNmrInitialized )
  {
    if ( NmrDeregisterClient(SlbNatIpsNmrClientHandle) != 259 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7, v8);
    if ( NmrWaitForClientDeregisterComplete(SlbNatIpsNmrClientHandle) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9, v11, v12);
    result = (PVOID *)SlbNatIpsCleanupProvider();
    SlbNatIpsNmrInitialized = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002fed8  sub     rsp, 28h
0x14002fedc  cmp     cs:SlbNatGlobalState, 1
0x14002fee3  jz      short loc_14002FEEA
0x14002fee5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002feea  lea     rax, qword_140026338
0x14002fef1  cmp     cs:qword_140026338, rax
0x14002fef8  jnz     short loc_14002FF4A
0x14002fefa  cmp     cs:SlbNatIpsNmrInitialized, 0
0x14002ff01  jz      short loc_14002FF4A
0x14002ff03  mov     rcx, cs:SlbNatIpsNmrClientHandle; NmrClientHandle
0x14002ff0a  call    cs:__imp_NmrDeregisterClient
0x14002ff11  nop     dword ptr [rax+rax+00h]
0x14002ff16  cmp     eax, 103h
0x14002ff1b  jz      short loc_14002FF22
0x14002ff1d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002ff22  mov     rcx, cs:SlbNatIpsNmrClientHandle; NmrClientHandle
0x14002ff29  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14002ff30  nop     dword ptr [rax+rax+00h]
0x14002ff35  test    eax, eax
0x14002ff37  jz      short loc_14002FF3E
0x14002ff39  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002ff3e  call    SlbNatIpsCleanupProvider
0x14002ff43  mov     cs:SlbNatIpsNmrInitialized, 0
0x14002ff4a  add     rsp, 28h
0x14002ff4e  retn
```
