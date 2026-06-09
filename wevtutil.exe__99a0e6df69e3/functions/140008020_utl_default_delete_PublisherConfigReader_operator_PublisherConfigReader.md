# utl::default_delete<PublisherConfigReader>::operator()(PublisherConfigReader *)

- ea: `0x140008020`
- end: `0x1400080f1`
- name: `??R?$default_delete@VPublisherConfigReader@@@utl@@QEBAXPEAVPublisherConfigReader@@@Z`
- size: `209`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1400088c0`
- `0x14000a6a0`
- `0x14000adf0`

## callees

- `0x140008020`
- `0x140021b24`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008051`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008072`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008093`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008051`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008072`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008093`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008043`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008043`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400080c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400080c6`

## pseudocode

```c
void __fastcall utl::default_delete<PublisherConfigReader>::operator()(__int64 a1, __int64 a2)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v5; // rdi
  HANDLE v6; // rax
  void *v7; // rdi
  HANDLE v8; // rax
  __int64 v9; // rcx

  if ( a2 )
  {
    v2 = *(void **)(a2 + 104);
    if ( v2 != (void *)(a2 + 120) )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    v5 = *(void **)(a2 + 72);
    if ( v5 != (void *)(a2 + 88) )
    {
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
    }
    v7 = *(void **)(a2 + 40);
    if ( v7 != (void *)(a2 + 56) )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v7);
    }
    v9 = *(_QWORD *)(a2 + 32);
    if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
    *(_QWORD *)(a2 + 32) = 0;
    if ( *(_QWORD *)a2 )
      RegCloseKey(*(HKEY *)a2);
    operator delete((void *)a2);
  }
}

```

## disassembly

```asm
0x140008020  test    rdx, rdx
0x140008023  jz      locret_1400080DE
0x140008029  push    rbx
0x14000802a  sub     rsp, 20h
0x14000802e  mov     [rsp+28h+arg_8], rdi
0x140008033  lea     rax, [rdx+78h]
0x140008037  mov     rdi, [rdx+68h]
0x14000803b  mov     rbx, rdx
0x14000803e  cmp     rdi, rax
0x140008041  jz      short loc_140008057
0x140008043  call    cs:__imp_GetProcessHeap
0x140008049  mov     r8, rdi; lpMem
0x14000804c  xor     edx, edx; dwFlags
0x14000804e  mov     rcx, rax; hHeap
0x140008051  call    cs:__imp_HeapFree
0x140008057  mov     rdi, [rbx+48h]
0x14000805b  lea     rax, [rbx+58h]
0x14000805f  cmp     rdi, rax
0x140008062  jz      short loc_140008078
0x140008064  call    cs:__imp_GetProcessHeap
0x14000806a  mov     r8, rdi; lpMem
0x14000806d  xor     edx, edx; dwFlags
0x14000806f  mov     rcx, rax; hHeap
0x140008072  call    cs:__imp_HeapFree
0x140008078  mov     rdi, [rbx+28h]
0x14000807c  lea     rax, [rbx+38h]
0x140008080  cmp     rdi, rax
0x140008083  jz      short loc_140008099
0x140008085  call    cs:__imp_GetProcessHeap
0x14000808b  mov     r8, rdi; lpMem
0x14000808e  xor     edx, edx; dwFlags
0x140008090  mov     rcx, rax; hHeap
0x140008093  call    cs:__imp_HeapFree
0x140008099  mov     rcx, [rbx+20h]
0x14000809d  mov     rdi, [rsp+28h+arg_8]
0x1400080a2  test    rcx, rcx
0x1400080a5  jz      short loc_1400080B6
0x1400080a7  mov     eax, 0FFFFFFFFh
0x1400080ac  lock xadd [rcx+8], eax
0x1400080b1  cmp     eax, 1
0x1400080b4  jz      short loc_1400080DF
0x1400080b6  mov     qword ptr [rbx+20h], 0
0x1400080be  mov     rcx, [rbx]; hKey
0x1400080c1  test    rcx, rcx
0x1400080c4  jz      short loc_1400080CC
0x1400080c6  call    cs:__imp_RegCloseKey
0x1400080cc  mov     edx, 90h; unsigned __int64
0x1400080d1  mov     rcx, rbx; void *
0x1400080d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400080d9  add     rsp, 20h
0x1400080dd  pop     rbx
0x1400080de  retn
0x1400080df  mov     rax, [rcx]
0x1400080e2  mov     edx, 1
0x1400080e7  mov     rax, [rax]
0x1400080ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080ef  jmp     short loc_1400080B6
```
