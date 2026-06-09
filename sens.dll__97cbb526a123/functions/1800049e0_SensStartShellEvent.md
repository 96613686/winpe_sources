# SensStartShellEvent

- ea: `0x1800049e0`
- end: `0x180004c19`
- name: `SensStartShellEvent`
- size: `569`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e00`

## callees

- `0x1800049e0`
- `0x180004c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c11`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180004b54`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180004b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004be7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004be7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ab1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004aca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ab1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004aca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004b22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004b22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004b2f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180004b6e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180004b6e`

## pseudocode

```c
DWORD __fastcall SensStartShellEvent(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  _DWORD *v4; // rax
  _DWORD *v5; // rsi
  HANDLE v6; // rcx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  SIZE_T v9; // rax
  LPVOID v10; // rax
  HANDLE v11; // rcx
  SIZE_T v12; // rax
  LPVOID v13; // rax
  HANDLE v14; // rcx
  LPVOID v15; // rax
  unsigned __int16 *v16; // rcx
  HANDLE CurrentProcess; // rax
  void *v18; // rdi
  void *v19; // rbx
  HANDLE v20; // rax
  DWORD LastError; // ebx
  void *v23; // rcx

  *(_QWORD *)(a1 + 24) = byte_18000D350;
  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2 * v2) );
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(*(_QWORD *)(a1 + 16) + 2 * v3) );
  v4 = HeapAlloc(ghSensHeap, 0, 0x38u);
  v5 = v4;
  if ( !v4 )
    return GetLastError();
  v6 = ghSensHeap;
  v7 = v2 + 1;
  *v4 = 56;
  v8 = v3 + 1;
  v4[1] = *(_DWORD *)(a1 + 4);
  v9 = 2 * v7;
  *((_QWORD *)v5 + 4) = 0;
  if ( !is_mul_ok(v7, 2u) )
    v9 = -1;
  *((_QWORD *)v5 + 5) = 0;
  *((_QWORD *)v5 + 6) = 0;
  v10 = HeapAlloc(v6, 0, v9);
  v11 = ghSensHeap;
  *((_QWORD *)v5 + 1) = v10;
  v12 = 2 * v8;
  if ( !is_mul_ok(v8, 2u) )
    v12 = -1;
  v13 = HeapAlloc(v11, 0, v12);
  v14 = ghSensHeap;
  *((_QWORD *)v5 + 2) = v13;
  v15 = HeapAlloc(v14, 0, 2u);
  v16 = (unsigned __int16 *)*((_QWORD *)v5 + 1);
  *((_QWORD *)v5 + 3) = v15;
  if ( v16
    && *((_QWORD *)v5 + 2)
    && v15
    && (StringCchCopyW(v16, v7, *(unsigned __int16 **)(a1 + 8)),
        StringCchCopyW(*((unsigned __int16 **)v5 + 2), v8, *(unsigned __int16 **)(a1 + 16)),
        StringCchCopyW(*((unsigned __int16 **)v5 + 3), 1u, *(unsigned __int16 **)(a1 + 24)),
        CurrentProcess = GetCurrentProcess(),
        v18 = *(void **)(a1 + 32),
        v19 = CurrentProcess,
        v20 = GetCurrentProcess(),
        DuplicateHandle(v20, v18, v19, (LPHANDLE)v5 + 4, 0, 0, 2u)) )
  {
    if ( !QueueUserWorkItem((LPTHREAD_START_ROUTINE)SensWaitToStartRoutine, v5, 0x10u) )
      GetLastError();
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v23 = (void *)*((_QWORD *)v5 + 4);
    if ( v23 )
      CloseHandle(v23);
    HeapFree(ghSensHeap, 0, *((LPVOID *)v5 + 1));
    HeapFree(ghSensHeap, 0, *((LPVOID *)v5 + 2));
    HeapFree(ghSensHeap, 0, *((LPVOID *)v5 + 3));
    HeapFree(ghSensHeap, 0, v5);
    return LastError;
  }
}

```

## disassembly

```asm
0x1800049e0  mov     [rsp+arg_10], rbx
0x1800049e5  mov     [rsp+arg_18], rbp
0x1800049ea  push    rsi
0x1800049eb  push    rdi
0x1800049ec  push    r15
0x1800049ee  sub     rsp, 40h
0x1800049f2  lea     rax, byte_18000D350
0x1800049f9  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180004a00  mov     [rcx+18h], rax
0x180004a04  mov     rbp, rcx
0x180004a07  mov     rax, [rcx+8]
0x180004a0b  mov     rbx, r15
0x180004a0e  xchg    ax, ax
0x180004a10  inc     rbx
0x180004a13  cmp     word ptr [rax+rbx*2], 0
0x180004a18  jnz     short loc_180004A10
0x180004a1a  mov     rax, [rcx+10h]
0x180004a1e  mov     rdi, r15
0x180004a21  inc     rdi
0x180004a24  cmp     word ptr [rax+rdi*2], 0
0x180004a29  jnz     short loc_180004A21
0x180004a2b  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004a32  xor     edx, edx; dwFlags
0x180004a34  mov     r8d, 38h ; '8'; dwBytes
0x180004a3a  call    cs:__imp_HeapAlloc
0x180004a40  mov     rsi, rax
0x180004a43  test    rax, rax
0x180004a46  jz      loc_180004B9B
0x180004a4c  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004a53  inc     rbx
0x180004a56  mov     dword ptr [rax], 38h ; '8'
0x180004a5c  inc     rdi
0x180004a5f  mov     eax, [rbp+4]
0x180004a62  mov     [rsi+4], eax
0x180004a65  mov     eax, 2
0x180004a6a  mov     [rsp+58h+arg_0], r12
0x180004a6f  xor     r12d, r12d
0x180004a72  mul     rbx
0x180004a75  mov     [rsp+58h+arg_8], r14
0x180004a7a  mov     [rsi+20h], r12
0x180004a7e  cmovb   rax, r15
0x180004a82  mov     [rsi+28h], r12
0x180004a86  mov     r8, rax; dwBytes
0x180004a89  mov     [rsi+30h], r12
0x180004a8d  xor     edx, edx; dwFlags
0x180004a8f  call    cs:__imp_HeapAlloc
0x180004a95  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004a9c  mov     [rsi+8], rax
0x180004aa0  mov     eax, 2
0x180004aa5  mul     rdi
0x180004aa8  cmovb   rax, r15
0x180004aac  xor     edx, edx; dwFlags
0x180004aae  mov     r8, rax; dwBytes
0x180004ab1  call    cs:__imp_HeapAlloc
0x180004ab7  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004abe  xor     edx, edx; dwFlags
0x180004ac0  mov     r8d, 2; dwBytes
0x180004ac6  mov     [rsi+10h], rax
0x180004aca  call    cs:__imp_HeapAlloc
0x180004ad0  mov     rcx, [rsi+8]; unsigned __int16 *
0x180004ad4  mov     [rsi+18h], rax
0x180004ad8  test    rcx, rcx
0x180004adb  jz      loc_180004BA3
0x180004ae1  cmp     [rsi+10h], r12
0x180004ae5  jz      loc_180004BA3
0x180004aeb  test    rax, rax
0x180004aee  jz      loc_180004BA3
0x180004af4  mov     r8, [rbp+8]; unsigned __int16 *
0x180004af8  mov     rdx, rbx; unsigned __int64
0x180004afb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004b00  mov     r8, [rbp+10h]; unsigned __int16 *
0x180004b04  mov     rdx, rdi; unsigned __int64
0x180004b07  mov     rcx, [rsi+10h]; unsigned __int16 *
0x180004b0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004b10  mov     r8, [rbp+18h]; unsigned __int16 *
0x180004b14  mov     edx, 1; unsigned __int64
0x180004b19  mov     rcx, [rsi+18h]; unsigned __int16 *
0x180004b1d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004b22  call    cs:__imp_GetCurrentProcess
0x180004b28  mov     rdi, [rbp+20h]
0x180004b2c  mov     rbx, rax
0x180004b2f  call    cs:__imp_GetCurrentProcess
0x180004b35  mov     [rsp+58h+dwOptions], 2; dwOptions
0x180004b3d  lea     r9, [rsi+20h]; lpTargetHandle
0x180004b41  mov     rcx, rax; hSourceProcessHandle
0x180004b44  mov     [rsp+58h+bInheritHandle], r12d; bInheritHandle
0x180004b49  mov     r8, rbx; hTargetProcessHandle
0x180004b4c  mov     [rsp+58h+dwDesiredAccess], r12d; dwDesiredAccess
0x180004b51  mov     rdx, rdi; hSourceHandle
0x180004b54  call    cs:__imp_DuplicateHandle
0x180004b5a  test    eax, eax
0x180004b5c  jz      short loc_180004BA3
0x180004b5e  mov     r8d, 10h; Flags
0x180004b64  lea     rcx, SensWaitToStartRoutine; Function
0x180004b6b  mov     rdx, rsi; Context
0x180004b6e  call    cs:__imp_QueueUserWorkItem
0x180004b74  test    eax, eax
0x180004b76  jz      loc_180004C06
0x180004b7c  xor     eax, eax
0x180004b7e  mov     r12, [rsp+58h+arg_0]
0x180004b83  mov     r14, [rsp+58h+arg_8]
0x180004b88  mov     rbx, [rsp+58h+arg_10]
0x180004b8d  mov     rbp, [rsp+58h+arg_18]
0x180004b92  add     rsp, 40h
0x180004b96  pop     r15
0x180004b98  pop     rdi
0x180004b99  pop     rsi
0x180004b9a  retn
0x180004b9b  call    cs:__imp_GetLastError
0x180004ba1  jmp     short loc_180004B88
0x180004ba3  call    cs:__imp_GetLastError
0x180004ba9  mov     ebx, eax
0x180004bab  mov     rcx, [rsi+20h]; hObject
0x180004baf  test    rcx, rcx
0x180004bb2  jnz     short loc_180004C11
0x180004bb4  mov     r8, [rsi+8]; lpMem
0x180004bb8  xor     edx, edx; dwFlags
0x180004bba  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004bc1  call    cs:__imp_HeapFree
0x180004bc7  mov     r8, [rsi+10h]; lpMem
0x180004bcb  xor     edx, edx; dwFlags
0x180004bcd  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004bd4  call    cs:__imp_HeapFree
0x180004bda  mov     r8, [rsi+18h]; lpMem
0x180004bde  xor     edx, edx; dwFlags
0x180004be0  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004be7  call    cs:__imp_HeapFree
0x180004bed  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004bf4  mov     r8, rsi; lpMem
0x180004bf7  xor     edx, edx; dwFlags
0x180004bf9  call    cs:__imp_HeapFree
0x180004bff  mov     eax, ebx
0x180004c01  jmp     loc_180004B7E
0x180004c06  call    cs:__imp_GetLastError
0x180004c0c  jmp     loc_180004B7C
0x180004c11  call    cs:__imp_CloseHandle
0x180004c17  jmp     short loc_180004BB4
```
