# CMSSearchStateMonitor::s_ThreadCreateCallback(void *)

- ea: `0x1800213e0`
- end: `0x180021456`
- name: `?s_ThreadCreateCallback@CMSSearchStateMonitor@@CAKPEAX@Z`
- size: `118`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d4dc`
- `0x1800213e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800213fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800213fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800213f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021404`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800213f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021404`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002142e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002142e`

## pseudocode

```c
__int64 __fastcall CMSSearchStateMonitor::s_ThreadCreateCallback(HANDLE *Parameter)
{
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v4; // rax

  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v4 = GetCurrentProcess();
  if ( !DuplicateHandle(v4, CurrentThread, CurrentProcess, Parameter, 0, 0, 2u) )
  {
    ResultFromKnownLastError();
    *Parameter = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800213e0  mov     [rsp+arg_0], rbx
0x1800213e5  mov     [rsp+arg_8], rsi
0x1800213ea  push    rdi
0x1800213eb  sub     rsp, 40h
0x1800213ef  mov     rsi, rcx
0x1800213f2  call    cs:__imp_GetCurrentProcess
0x1800213f8  mov     rdi, rax
0x1800213fb  call    cs:__imp_GetCurrentThread
0x180021401  mov     rbx, rax
0x180021404  call    cs:__imp_GetCurrentProcess
0x18002140a  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180021412  mov     r9, rsi; lpTargetHandle
0x180021415  mov     rcx, rax; hSourceProcessHandle
0x180021418  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180021420  mov     r8, rdi; hTargetProcessHandle
0x180021423  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18002142b  mov     rdx, rbx; hSourceHandle
0x18002142e  call    cs:__imp_DuplicateHandle
0x180021434  test    eax, eax
0x180021436  jnz     short loc_180021444
0x180021438  call    ?ResultFromKnownLastError@@YAJXZ
0x18002143d  mov     qword ptr [rsi], 0
0x180021444  mov     rbx, [rsp+48h+arg_0]
0x180021449  xor     eax, eax
0x18002144b  mov     rsi, [rsp+48h+arg_8]
0x180021450  add     rsp, 40h
0x180021454  pop     rdi
0x180021455  retn
```
