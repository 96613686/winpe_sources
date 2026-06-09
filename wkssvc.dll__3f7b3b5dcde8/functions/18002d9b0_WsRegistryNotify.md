# WsRegistryNotify

- ea: `0x18002d9b0`
- end: `0x18002da63`
- name: `WsRegistryNotify`
- size: `179`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180007100`
- `0x18000a600`
- `0x18000c920`
- `0x18000d500`
- `0x18002d9b0`

## import_xrefs

- `ntdll!RtlDeregisterWaitEx` at `0x18002d9e9`
- `ntdll!RtlDeregisterWaitEx` at `0x18002d9e9`
- `ntdll!RtlDeregisterWait` at `0x18002d9f1`
- `ntdll!RtlDeregisterWait` at `0x18002d9f1`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002da00`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002da00`
- `ntdll!RtlReleaseResource` at `0x18002da32`
- `ntdll!RtlReleaseResource` at `0x18002da32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002da55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002da55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d9c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d9c9`

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
0x18002d9b0  push    rbx
0x18002d9b2  sub     rsp, 30h
0x18002d9b6  mov     rbx, rcx
0x18002d9b9  mov     [rsp+38h+var_10], 0
0x18002d9c2  lea     rcx, WsWorkerCriticalSection; lpCriticalSection
0x18002d9c9  call    cs:__imp_EnterCriticalSection
0x18002d9cf  call    WsIsTerminating
0x18002d9d4  mov     rcx, [rbx+10h]; hWaitHandle
0x18002d9d8  test    eax, eax
0x18002d9da  jz      short loc_18002D9F1
0x18002d9dc  dec     cs:WsNumWorkerThreads
0x18002d9e2  mov     rdx, cs:hHandle; hCompletionEvent
0x18002d9e9  call    cs:__imp_RtlDeregisterWaitEx
0x18002d9ef  jmp     short loc_18002DA4E
0x18002d9f1  call    cs:__imp_RtlDeregisterWait
0x18002d9f7  mov     dl, 1; Wait
0x18002d9f9  lea     rcx, WsInfo; Resource
0x18002da00  call    cs:__imp_RtlAcquireResourceExclusive
0x18002da06  test    al, al
0x18002da08  jz      short loc_18002DA38
0x18002da0a  mov     rax, cs:ConfigHandle
0x18002da11  lea     rcx, [rsp+38h+var_18]
0x18002da16  xor     edx, edx
0x18002da18  mov     [rsp+38h+var_18], rax
0x18002da1d  call    WsUpdateWkstaToMatchRegistry
0x18002da22  xor     edx, edx
0x18002da24  xor     ecx, ecx
0x18002da26  call    WsUpdateRedirToMatchWksta
0x18002da2b  lea     rcx, WsInfo; Resource
0x18002da32  call    cs:__imp_RtlReleaseResource
0x18002da38  lea     rcx, RegNotifyInfo; pvContext
0x18002da3f  call    WsReInitChangeNotify
0x18002da44  test    eax, eax
0x18002da46  jnz     short loc_18002DA4E
0x18002da48  call    cs:__imp_GetLastError
0x18002da4e  lea     rcx, WsWorkerCriticalSection; lpCriticalSection
0x18002da55  call    cs:__imp_LeaveCriticalSection
0x18002da5b  xor     eax, eax
0x18002da5d  add     rsp, 30h
0x18002da61  pop     rbx
0x18002da62  retn
```
