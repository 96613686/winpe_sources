# WsRegistryNotify

- ea: `0x180030360`
- end: `0x18003043e`
- name: `WsRegistryNotify`
- size: `222`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000776c`
- `0x18000b290`
- `0x18000d474`
- `0x18000e140`
- `0x180030360`

## import_xrefs

- `ntdll!RtlDeregisterWaitEx` at `0x18003039f`
- `ntdll!RtlDeregisterWaitEx` at `0x18003039f`
- `ntdll!RtlDeregisterWait` at `0x1800303ad`
- `ntdll!RtlDeregisterWait` at `0x1800303ad`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800303c2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800303c2`
- `ntdll!RtlReleaseResource` at `0x1800303fa`
- `ntdll!RtlReleaseResource` at `0x1800303fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030416`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030429`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030379`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030379`

## pseudocode

```c
void __fastcall WsRegistryNotify(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  int IsTerminating; // eax
  void *v5; // rcx
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  v6[1] = 0;
  EnterCriticalSection(&WsWorkerCriticalSection);
  IsTerminating = WsIsTerminating(v3, v2);
  v5 = (void *)a1[2];
  if ( IsTerminating )
  {
    --WsNumWorkerThreads;
    RtlDeregisterWaitEx(v5, hHandle);
  }
  else
  {
    RtlDeregisterWait(v5);
    if ( RtlAcquireResourceExclusive(&WsInfo, 1u) )
    {
      v6[0] = ConfigHandle;
      WsUpdateWkstaToMatchRegistry(v6, 0);
      WsUpdateRedirToMatchWksta(0, 0);
      RtlReleaseResource(&WsInfo);
    }
    if ( !(unsigned int)WsReInitChangeNotify(&RegNotifyInfo) )
      GetLastError();
  }
  LeaveCriticalSection(&WsWorkerCriticalSection);
}

```

## disassembly

```asm
0x180030360  push    rbx
0x180030362  sub     rsp, 30h
0x180030366  mov     rbx, rcx
0x180030369  mov     [rsp+38h+var_10], 0
0x180030372  lea     rcx, WsWorkerCriticalSection; lpCriticalSection
0x180030379  call    cs:__imp_EnterCriticalSection
0x180030380  nop     dword ptr [rax+rax+00h]
0x180030385  call    WsIsTerminating
0x18003038a  mov     rcx, [rbx+10h]; hWaitHandle
0x18003038e  test    eax, eax
0x180030390  jz      short loc_1800303AD
0x180030392  dec     cs:WsNumWorkerThreads
0x180030398  mov     rdx, cs:hHandle; hCompletionEvent
0x18003039f  call    cs:__imp_RtlDeregisterWaitEx
0x1800303a6  nop     dword ptr [rax+rax+00h]
0x1800303ab  jmp     short loc_180030422
0x1800303ad  call    cs:__imp_RtlDeregisterWait
0x1800303b4  nop     dword ptr [rax+rax+00h]
0x1800303b9  mov     dl, 1; Wait
0x1800303bb  lea     rcx, WsInfo; Resource
0x1800303c2  call    cs:__imp_RtlAcquireResourceExclusive
0x1800303c9  nop     dword ptr [rax+rax+00h]
0x1800303ce  test    al, al
0x1800303d0  jz      short loc_180030406
0x1800303d2  mov     rax, cs:ConfigHandle
0x1800303d9  lea     rcx, [rsp+38h+var_18]
0x1800303de  xor     edx, edx
0x1800303e0  mov     [rsp+38h+var_18], rax
0x1800303e5  call    WsUpdateWkstaToMatchRegistry
0x1800303ea  xor     edx, edx
0x1800303ec  xor     ecx, ecx
0x1800303ee  call    WsUpdateRedirToMatchWksta
0x1800303f3  lea     rcx, WsInfo; Resource
0x1800303fa  call    cs:__imp_RtlReleaseResource
0x180030401  nop     dword ptr [rax+rax+00h]
0x180030406  lea     rcx, RegNotifyInfo; pvContext
0x18003040d  call    WsReInitChangeNotify
0x180030412  test    eax, eax
0x180030414  jnz     short loc_180030422
0x180030416  call    cs:__imp_GetLastError
0x18003041d  nop     dword ptr [rax+rax+00h]
0x180030422  lea     rcx, WsWorkerCriticalSection; lpCriticalSection
0x180030429  call    cs:__imp_LeaveCriticalSection
0x180030430  nop     dword ptr [rax+rax+00h]
0x180030435  xor     eax, eax
0x180030437  add     rsp, 30h
0x18003043b  pop     rbx
0x18003043c  retn
```
