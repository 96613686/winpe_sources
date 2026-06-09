# DoRpcSetup(void)

- ea: `0x180005960`
- end: `0x1800059cf`
- name: `?DoRpcSetup@@YAJXZ`
- size: `111`
- prototype: `__int64(void)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180004ca0`
- `0x180004fac`
- `0x18000514c`
- `0x180005890`
- `0x180005920`
- `0x1800059d8`
- `0x180005a5c`
- `0x180005ae0`
- `0x180005c30`
- `0x180005d1c`
- `0x180006038`
- `0x1800060bc`
- `0x180007020`

## callees

- `0x180005960`
- `0x180005b64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000598b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000598b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005974`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005974`

## pseudocode

```c
__int64 DoRpcSetup(void)
{
  const unsigned __int16 *v0; // rdx
  unsigned int v2; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  Binding = 0;
  EnterCriticalSection(&gSensapiLockP);
  if ( ghSensNotify )
  {
    LeaveCriticalSection(&gSensapiLockP);
    return 0;
  }
  else
  {
    v2 = BindToLRpcService(&Binding, v0);
    if ( !v2 )
      ghSensNotify = Binding;
    LeaveCriticalSection(&gSensapiLockP);
    return v2;
  }
}

```

## disassembly

```asm
0x180005960  sub     rsp, 28h
0x180005964  lea     rcx, ?gSensapiLockP@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000596b  mov     [rsp+28h+Binding], 0
0x180005974  call    cs:__imp_EnterCriticalSection
0x18000597a  cmp     cs:?ghSensNotify@@3PEAXEA, 0; void * ghSensNotify
0x180005982  jz      short loc_180005998
0x180005984  lea     rcx, ?gSensapiLockP@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000598b  call    cs:__imp_LeaveCriticalSection
0x180005991  xor     eax, eax
0x180005993  add     rsp, 28h
0x180005997  retn
0x180005998  lea     rcx, [rsp+28h+Binding]; Binding
0x18000599d  mov     [rsp+28h+var_8], rbx
0x1800059a2  call    ?BindToLRpcService@@YAJAEAPEAXPEBG@Z; BindToLRpcService(void * &,ushort const *)
0x1800059a7  mov     ebx, eax
0x1800059a9  test    eax, eax
0x1800059ab  jnz     short loc_1800059B9
0x1800059ad  mov     rax, [rsp+28h+Binding]
0x1800059b2  mov     cs:?ghSensNotify@@3PEAXEA, rax; void * ghSensNotify
0x1800059b9  lea     rcx, ?gSensapiLockP@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800059c0  call    cs:__imp_LeaveCriticalSection
0x1800059c6  mov     eax, ebx
0x1800059c8  mov     rbx, [rsp+28h+var_8]
0x1800059cd  jmp     short loc_180005993
```
