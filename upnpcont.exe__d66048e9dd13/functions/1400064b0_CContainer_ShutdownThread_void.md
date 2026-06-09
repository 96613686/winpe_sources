# CContainer::ShutdownThread(void *)

- ea: `0x1400064b0`
- end: `0x140006522`
- name: `?ShutdownThread@CContainer@@CAKPEAX@Z`
- size: `114`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400064b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400064c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400064c2`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000651b`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000651b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006507`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1400064d6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1400064d6`

## pseudocode

```c
__int64 __fastcall CContainer::ShutdownThread(PVOID Parameter)
{
  DWORD v1; // ebx

  v1 = WaitForSingleObject(CContainer::s_hEventShutdown, 0x7D0u);
  if ( CContainer::s_hProcessDiedWait )
    UnregisterWait(CContainer::s_hProcessDiedWait);
  CloseHandle(CContainer::s_hEventShutdown);
  CContainer::s_hEventShutdown = 0;
  if ( v1 )
  {
    CloseHandle(CContainer::s_hThreadShutdown);
    CContainer::s_hThreadShutdown = 0;
    ExitProcess(0xFFFFFFFF);
  }
  return 0;
}

```

## disassembly

```asm
0x1400064b0  push    rbx
0x1400064b2  sub     rsp, 20h
0x1400064b6  mov     rcx, cs:?s_hEventShutdown@CContainer@@0PEAXEA; hHandle
0x1400064bd  mov     edx, 7D0h; dwMilliseconds
0x1400064c2  call    cs:__imp_WaitForSingleObject
0x1400064c8  mov     rcx, cs:?s_hProcessDiedWait@CContainer@@0PEAXEA; WaitHandle
0x1400064cf  mov     ebx, eax
0x1400064d1  test    rcx, rcx
0x1400064d4  jz      short loc_1400064DC
0x1400064d6  call    cs:__imp_UnregisterWait
0x1400064dc  mov     rcx, cs:?s_hEventShutdown@CContainer@@0PEAXEA; hObject
0x1400064e3  call    cs:__imp_CloseHandle
0x1400064e9  mov     cs:?s_hEventShutdown@CContainer@@0PEAXEA, 0; void * CContainer::s_hEventShutdown
0x1400064f4  test    ebx, ebx
0x1400064f6  jnz     short loc_140006500
0x1400064f8  xor     eax, eax
0x1400064fa  add     rsp, 20h
0x1400064fe  pop     rbx
0x1400064ff  retn
0x140006500  mov     rcx, cs:?s_hThreadShutdown@CContainer@@0PEAXEA; hObject
0x140006507  call    cs:__imp_CloseHandle
0x14000650d  or      ecx, 0FFFFFFFFh; uExitCode
0x140006510  mov     cs:?s_hThreadShutdown@CContainer@@0PEAXEA, 0; void * CContainer::s_hThreadShutdown
0x14000651b  call    cs:__imp_ExitProcess
```
