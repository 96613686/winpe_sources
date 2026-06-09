# XMLStream::push(long (XMLStream::*)(void),short)

- ea: `0x1800395e0`
- end: `0x18003971e`
- name: `?push@XMLStream@@AEAAJP81@EAAJXZF@Z`
- size: `318`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180038610`
- `0x180039260`
- `0x180039820`
- `0x18003a990`
- `0x18003acf0`
- `0x18003c7d0`
- `0x18003d0e0`
- `0x18003dbe0`
- `0x180068f10`
- `0x180069110`

## callees

- `0x1800395e0`
- `0x18006a0dd`
- `0x18006a0f5`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039646`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039646`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039699`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039699`

## pseudocode

```c
__int64 __fastcall XMLStream::push(__int64 a1, __int64 a2, __int16 a3)
{
  int v3; // r9d
  unsigned int v5; // ecx
  unsigned int v8; // edx
  unsigned __int64 v9; // rcx
  unsigned int v10; // r14d
  char *v11; // rax
  char *v12; // rbp
  int v13; // eax
  void *v14; // r8
  int v15; // ecx
  __int64 v16; // rdx
  char *v17; // rdx
  __int64 v18; // rdx
  __int64 result; // rax

  v3 = *(_DWORD *)(a1 + 32);
  v5 = *(_DWORD *)(a1 + 36);
  if ( v5 == v3 )
  {
    v8 = v5 + *(_DWORD *)(a1 + 40);
    if ( v8 >= v5
      && (v9 = *(unsigned int *)(a1 + 16) * (unsigned __int64)v8, v9 <= 0xFFFFFFFF)
      && (v10 = *(_DWORD *)(a1 + 16) * v8, v11 = (char *)HeapAlloc(g_hHeap, 0, (unsigned int)v9), (v12 = v11) != 0) )
    {
      memset_0(v11, 0, v10);
      v13 = *(_DWORD *)(a1 + 32);
      if ( v13 )
        memcpy_0(v12, *(const void **)(a1 + 24), (unsigned int)(*(_DWORD *)(a1 + 16) * v13));
      *(_DWORD *)(a1 + 36) += *(_DWORD *)(a1 + 40);
      v14 = *(void **)(a1 + 24);
      if ( v14 )
        HeapFree(g_hHeap, 0, v14);
      v15 = *(_DWORD *)(a1 + 32);
      v16 = (unsigned int)(*(_DWORD *)(a1 + 16) * v15);
      *(_QWORD *)(a1 + 24) = v12;
      *(_DWORD *)(a1 + 32) = v15 + 1;
      v17 = &v12[v16];
    }
    else
    {
      v17 = 0;
    }
  }
  else
  {
    v18 = (unsigned int)(*(_DWORD *)(a1 + 16) * v3);
    *(_DWORD *)(a1 + 32) = v3 + 1;
    v17 = (char *)(*(_QWORD *)(a1 + 24) + v18);
  }
  if ( !v17 )
    return 2147942414LL;
  *((_WORD *)v17 + 4) = a3;
  *(_QWORD *)v17 = *(_QWORD *)a1;
  *((_QWORD *)v17 + 2) = *(_QWORD *)(a1 + 168);
  *((_DWORD *)v17 + 6) = *(_DWORD *)(a1 + 80);
  result = 0;
  *(_WORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = a2;
  return result;
}

```

## disassembly

```asm
0x1800395e0  mov     [rsp+arg_10], rbx
0x1800395e5  mov     [rsp+arg_18], rsi
0x1800395ea  push    rdi
0x1800395eb  sub     rsp, 20h
0x1800395ef  mov     r9d, [rcx+20h]
0x1800395f3  mov     rbx, rcx
0x1800395f6  mov     ecx, [rcx+24h]
0x1800395f9  movzx   edi, r8w
0x1800395fd  mov     rsi, rdx
0x180039600  cmp     ecx, r9d
0x180039603  jnz     loc_1800396BD
0x180039609  mov     edx, [rbx+28h]
0x18003960c  add     edx, ecx
0x18003960e  mov     [rsp+28h+arg_0], rbp
0x180039613  mov     [rsp+28h+arg_8], r14
0x180039618  cmp     edx, ecx
0x18003961a  jb      loc_1800396D1
0x180039620  mov     eax, [rbx+10h]
0x180039623  mov     ecx, edx
0x180039625  imul    rcx, rax
0x180039629  mov     eax, 0FFFFFFFFh
0x18003962e  cmp     rcx, rax
0x180039631  ja      loc_1800396D1
0x180039637  mov     r14d, ecx
0x18003963a  xor     edx, edx; dwFlags
0x18003963c  mov     r8d, ecx; dwBytes
0x18003963f  mov     rcx, cs:g_hHeap; hHeap
0x180039646  call    cs:__imp_HeapAlloc
0x18003964d  nop     dword ptr [rax+rax+00h]
0x180039652  mov     rbp, rax
0x180039655  test    rax, rax
0x180039658  jz      short loc_1800396D1
0x18003965a  mov     r8d, r14d; Size
0x18003965d  xor     edx, edx; Val
0x18003965f  mov     rcx, rax; void *
0x180039662  call    memset_0
0x180039667  mov     eax, [rbx+20h]
0x18003966a  test    eax, eax
0x18003966c  jz      short loc_180039681
0x18003966e  imul    eax, [rbx+10h]
0x180039672  mov     rcx, rbp; void *
0x180039675  mov     rdx, [rbx+18h]; Src
0x180039679  mov     r8d, eax; Size
0x18003967c  call    memcpy_0
0x180039681  mov     eax, [rbx+28h]
0x180039684  add     [rbx+24h], eax
0x180039687  mov     r8, [rbx+18h]; lpMem
0x18003968b  test    r8, r8
0x18003968e  jz      short loc_1800396A5
0x180039690  mov     rcx, cs:g_hHeap; hHeap
0x180039697  xor     edx, edx; dwFlags
0x180039699  call    cs:__imp_HeapFree
0x1800396a0  nop     dword ptr [rax+rax+00h]
0x1800396a5  mov     ecx, [rbx+20h]
0x1800396a8  mov     edx, ecx
0x1800396aa  imul    edx, [rbx+10h]
0x1800396ae  mov     [rbx+18h], rbp
0x1800396b2  lea     eax, [rcx+1]
0x1800396b5  mov     [rbx+20h], eax
0x1800396b8  add     rdx, rbp
0x1800396bb  jmp     short loc_1800396D3
0x1800396bd  mov     edx, r9d
0x1800396c0  lea     eax, [r9+1]
0x1800396c4  imul    edx, [rbx+10h]
0x1800396c8  mov     [rbx+20h], eax
0x1800396cb  add     rdx, [rbx+18h]
0x1800396cf  jmp     short loc_1800396DD
0x1800396d1  xor     edx, edx
0x1800396d3  mov     r14, [rsp+28h+arg_8]
0x1800396d8  mov     rbp, [rsp+28h+arg_0]
0x1800396dd  test    rdx, rdx
0x1800396e0  jz      short loc_180039717
0x1800396e2  mov     [rdx+8], di
0x1800396e6  mov     rax, [rbx]
0x1800396e9  mov     [rdx], rax
0x1800396ec  mov     rax, [rbx+0A8h]
0x1800396f3  mov     [rdx+10h], rax
0x1800396f7  mov     eax, [rbx+50h]
0x1800396fa  mov     [rdx+18h], eax
0x1800396fd  xor     eax, eax
0x1800396ff  mov     [rbx+8], ax
0x180039703  mov     [rbx], rsi
0x180039706  mov     rbx, [rsp+28h+arg_10]
0x18003970b  mov     rsi, [rsp+28h+arg_18]
0x180039710  add     rsp, 20h
0x180039714  pop     rdi
0x180039715  retn
0x180039717  mov     eax, 8007000Eh
0x18003971c  jmp     short loc_180039706
```
