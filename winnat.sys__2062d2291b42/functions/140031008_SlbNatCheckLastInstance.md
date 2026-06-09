# SlbNatCheckLastInstance

- ea: `0x140031008`
- end: `0x140031080`
- name: `SlbNatCheckLastInstance`
- size: `120`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400311f4`
- `0x140033518`
- `0x140033e5c`

## callees

- `0x14000caa0`
- `0x14003041c`
- `0x140031008`

## import_xrefs

- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140031059`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140031059`
- `NETIO!NmrDeregisterClient` at `0x14003103a`
- `NETIO!NmrDeregisterClient` at `0x14003103a`

## pseudocode

```c
PVOID *__fastcall SlbNatCheckLastInstance(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *result; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8

  if ( SlbNatGlobalState != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  result = &qword_140027338;
  if ( qword_140027338 == &qword_140027338 && SlbNatIpsNmrInitialized )
  {
    if ( NmrDeregisterClient(SlbNatIpsNmrClientHandle) != 259 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6);
    if ( NmrWaitForClientDeregisterComplete(SlbNatIpsNmrClientHandle) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7, v9);
    result = (PVOID *)SlbNatIpsCleanupProvider();
    SlbNatIpsNmrInitialized = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140031008  sub     rsp, 28h
0x14003100c  cmp     cs:SlbNatGlobalState, 1
0x140031013  jz      short loc_14003101A
0x140031015  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003101a  lea     rax, qword_140027338
0x140031021  cmp     cs:qword_140027338, rax
0x140031028  jnz     short loc_14003107A
0x14003102a  cmp     cs:SlbNatIpsNmrInitialized, 0
0x140031031  jz      short loc_14003107A
0x140031033  mov     rcx, cs:SlbNatIpsNmrClientHandle; NmrClientHandle
0x14003103a  call    cs:__imp_NmrDeregisterClient
0x140031041  nop     dword ptr [rax+rax+00h]
0x140031046  cmp     eax, 103h
0x14003104b  jz      short loc_140031052
0x14003104d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140031052  mov     rcx, cs:SlbNatIpsNmrClientHandle; NmrClientHandle
0x140031059  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140031060  nop     dword ptr [rax+rax+00h]
0x140031065  test    eax, eax
0x140031067  jz      short loc_14003106E
0x140031069  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003106e  call    SlbNatIpsCleanupProvider
0x140031073  mov     cs:SlbNatIpsNmrInitialized, 0
0x14003107a  add     rsp, 28h
0x14003107e  retn
```
