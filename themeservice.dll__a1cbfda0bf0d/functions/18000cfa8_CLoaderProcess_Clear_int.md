# CLoaderProcess::Clear(int)

- ea: `0x18000cfa8`
- end: `0x18000d08c`
- name: `?Clear@CLoaderProcess@@QEAAXH@Z`
- size: `228`
- prototype: `void __fastcall(CLoaderProcess *__hidden this, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ee0`
- `0x18000acc0`
- `0x18000aefc`
- `0x18000d094`

## callees

- `0x18000cfa8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d01f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d03a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d01f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d03a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cfc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cfce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cfe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d051`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d068`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cfc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cfce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cfe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d051`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d068`

## pseudocode

```c
void __fastcall CLoaderProcess::Clear(CLoaderProcess *this, int a2)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // r8
  HANDLE v7; // rcx
  void *v8; // r8
  HANDLE v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
    CloseHandle(v4);
  if ( *(_QWORD *)this )
    CloseHandle(*(HANDLE *)this);
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 3) = 0;
  }
  HeapFree(s_hHeapToUse, 0, *((LPVOID *)this + 4));
  v6 = (void *)*((_QWORD *)this + 5);
  v7 = s_hHeapToUse;
  *((_QWORD *)this + 4) = 0;
  HeapFree(v7, 0, v6);
  v8 = (void *)*((_QWORD *)this + 6);
  v9 = s_hHeapToUse;
  *((_QWORD *)this + 5) = 0;
  HeapFree(v9, 0, v8);
  v10 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 6) = 0;
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 9) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 8);
  if ( v11 )
  {
    CloseHandle(v11);
    *((_QWORD *)this + 8) = 0;
  }
  if ( a2 )
    *((_DWORD *)this + 20) = 0;
}

```

## disassembly

```asm
0x18000cfa8  mov     [rsp+arg_0], rbx
0x18000cfad  push    rdi
0x18000cfae  sub     rsp, 20h
0x18000cfb2  mov     rbx, rcx
0x18000cfb5  mov     edi, edx
0x18000cfb7  mov     rcx, [rcx+8]; hObject
0x18000cfbb  test    rcx, rcx
0x18000cfbe  jz      short loc_18000CFC6
0x18000cfc0  call    cs:__imp_CloseHandle
0x18000cfc6  mov     rcx, [rbx]; hObject
0x18000cfc9  test    rcx, rcx
0x18000cfcc  jz      short loc_18000CFD4
0x18000cfce  call    cs:__imp_CloseHandle
0x18000cfd4  xor     eax, eax
0x18000cfd6  xorps   xmm0, xmm0
0x18000cfd9  movups  xmmword ptr [rbx], xmm0
0x18000cfdc  mov     [rbx+10h], rax
0x18000cfe0  mov     rcx, [rbx+18h]; hObject
0x18000cfe4  test    rcx, rcx
0x18000cfe7  jz      short loc_18000CFF7
0x18000cfe9  call    cs:__imp_CloseHandle
0x18000cfef  mov     qword ptr [rbx+18h], 0
0x18000cff7  mov     r8, [rbx+20h]; lpMem
0x18000cffb  xor     edx, edx; dwFlags
0x18000cffd  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d004  call    cs:__imp_HeapFree
0x18000d00a  mov     r8, [rbx+28h]; lpMem
0x18000d00e  xor     edx, edx; dwFlags
0x18000d010  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d017  mov     qword ptr [rbx+20h], 0
0x18000d01f  call    cs:__imp_HeapFree
0x18000d025  mov     r8, [rbx+30h]; lpMem
0x18000d029  xor     edx, edx; dwFlags
0x18000d02b  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d032  mov     qword ptr [rbx+28h], 0
0x18000d03a  call    cs:__imp_HeapFree
0x18000d040  mov     rcx, [rbx+48h]; hObject
0x18000d044  mov     qword ptr [rbx+30h], 0
0x18000d04c  test    rcx, rcx
0x18000d04f  jz      short loc_18000D05F
0x18000d051  call    cs:__imp_CloseHandle
0x18000d057  mov     qword ptr [rbx+48h], 0
0x18000d05f  mov     rcx, [rbx+40h]; hObject
0x18000d063  test    rcx, rcx
0x18000d066  jz      short loc_18000D076
0x18000d068  call    cs:__imp_CloseHandle
0x18000d06e  mov     qword ptr [rbx+40h], 0
0x18000d076  test    edi, edi
0x18000d078  jz      short loc_18000D081
0x18000d07a  mov     dword ptr [rbx+50h], 0
0x18000d081  mov     rbx, [rsp+28h+arg_0]
0x18000d086  add     rsp, 20h
0x18000d08a  pop     rdi
0x18000d08b  retn
```
