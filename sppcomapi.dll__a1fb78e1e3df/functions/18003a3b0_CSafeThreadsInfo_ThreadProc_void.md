# CSafeThreadsInfo::ThreadProc(void *)

- ea: `0x18003a3b0`
- end: `0x18003a46d`
- name: `?ThreadProc@CSafeThreadsInfo@@SAKPEAX@Z`
- size: `189`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003a3b0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a41f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a41f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a433`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a433`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18003a454`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18003a454`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a40b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a40b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003a3ea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003a3ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a3d9`

## pseudocode

```c
__int64 __fastcall CSafeThreadsInfo::ThreadProc(_QWORD *lpThreadParameter)
{
  __int64 v1; // rbp
  __int64 (__fastcall *v3)(__int64); // r14
  HMODULE v4; // rsi
  int v5; // edi
  HANDLE CurrentThread; // rax
  HMODULE v7; // rcx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax

  v1 = lpThreadParameter[2];
  v3 = (__int64 (__fastcall *)(__int64))lpThreadParameter[1];
  v4 = (HMODULE)lpThreadParameter[3];
  lpThreadParameter[3] = 0;
  v5 = *((_DWORD *)lpThreadParameter + 8);
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v5);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpThreadParameter, 0xFFFFFFFF) == 1 )
  {
    v7 = (HMODULE)lpThreadParameter[3];
    if ( v7 )
    {
      FreeLibrary(v7);
      lpThreadParameter[3] = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpThreadParameter);
  }
  result = v3(v1);
  if ( v4 )
    FreeLibraryAndExitThread(v4, result);
  return result;
}

```

## disassembly

```asm
0x18003a3b0  push    rbx
0x18003a3b2  push    rbp
0x18003a3b3  push    rsi
0x18003a3b4  push    rdi
0x18003a3b5  push    r14
0x18003a3b7  sub     rsp, 20h
0x18003a3bb  mov     rbp, [rcx+10h]
0x18003a3bf  mov     rbx, rcx
0x18003a3c2  mov     r14, [rcx+8]
0x18003a3c6  mov     rsi, [rcx+18h]
0x18003a3ca  mov     qword ptr [rcx+18h], 0
0x18003a3d2  mov     edi, [rcx+20h]
0x18003a3d5  test    edi, edi
0x18003a3d7  jz      short loc_18003A3F6
0x18003a3d9  call    cs:__imp_GetCurrentThread
0x18003a3e0  nop     dword ptr [rax+rax+00h]
0x18003a3e5  mov     rcx, rax; hThread
0x18003a3e8  mov     edx, edi; nPriority
0x18003a3ea  call    cs:__imp_SetThreadPriority
0x18003a3f1  nop     dword ptr [rax+rax+00h]
0x18003a3f6  or      eax, 0FFFFFFFFh
0x18003a3f9  lock xadd [rbx], eax
0x18003a3fd  cmp     eax, 1
0x18003a400  jnz     short loc_18003A43F
0x18003a402  mov     rcx, [rbx+18h]; hLibModule
0x18003a406  test    rcx, rcx
0x18003a409  jz      short loc_18003A41F
0x18003a40b  call    cs:__imp_FreeLibrary
0x18003a412  nop     dword ptr [rax+rax+00h]
0x18003a417  mov     qword ptr [rbx+18h], 0
0x18003a41f  call    cs:__imp_GetProcessHeap
0x18003a426  nop     dword ptr [rax+rax+00h]
0x18003a42b  mov     r8, rbx; lpMem
0x18003a42e  xor     edx, edx; dwFlags
0x18003a430  mov     rcx, rax; hHeap
0x18003a433  call    cs:__imp_HeapFree
0x18003a43a  nop     dword ptr [rax+rax+00h]
0x18003a43f  mov     rcx, rbp
0x18003a442  mov     rax, r14
0x18003a445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a44a  test    rsi, rsi
0x18003a44d  jz      short loc_18003A461
0x18003a44f  mov     edx, eax; dwExitCode
0x18003a451  mov     rcx, rsi; hLibModule
0x18003a454  call    cs:__imp_FreeLibraryAndExitThread
0x18003a45b  nop     dword ptr [rax+rax+00h]
0x18003a460  int     3; Trap to Debugger
0x18003a461  add     rsp, 20h
0x18003a465  pop     r14
0x18003a467  pop     rdi
0x18003a468  pop     rsi
0x18003a469  pop     rbp
0x18003a46a  pop     rbx
0x18003a46b  retn
```
