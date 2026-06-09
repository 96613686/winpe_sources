# VsmmVaGpaCorepMergeVaRanges

- ea: `0x1400f6600`
- end: `0x1400f6748`
- name: `VsmmVaGpaCorepMergeVaRanges`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400edb40`
- `0x1400ef490`

## callees

- `0x1400386a0`
- `0x1400f6600`
- `0x1400f6750`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400f664a`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400f668d`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400f664a`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400f668d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f66b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f66f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f66b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f66f1`

## pseudocode

```c
__int64 __fastcall VsmmVaGpaCorepMergeVaRanges(__int64 a1, __int64 a2, _QWORD *a3, char a4)
{
  _QWORD **v7; // rdi
  _QWORD *v8; // r15
  __int64 v9; // rbp
  __int64 **i; // r12
  __int64 *v11; // rax
  _QWORD *v12; // rcx
  int v13; // ebx
  _QWORD *v15; // rax

  if ( a4
    && (v13 = VsmmNtSlatMergeVaRanges(a1, *(_QWORD *)(*(_QWORD *)(a2 + 24) + 56LL), *(_QWORD *)(a2 + 40)), v13 < 0) )
  {
    VidTraceErrorInternal0("VsmmVaGpaCorepMergeVaRanges", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c", 1627);
  }
  else
  {
    v7 = (_QWORD **)(a3 + 6);
    v8 = *(_QWORD **)(a2 + 48);
    *(_QWORD *)(a2 + 40) = a3[5];
    v9 = *(unsigned int *)(a2 + 64);
    for ( i = (__int64 **)a3[6]; v9; --v9 )
    {
      RtlRbRemoveNode(a1 + 10824, i - 3);
      v11 = i[5];
      *(i - 1) = (__int64 *)-1LL;
      v8[5] = v11;
      if ( ((_DWORD)i[9] & 4) != 0 )
        --*(_QWORD *)(a1 + 10856);
      v8 = (_QWORD *)*v8;
      i = (__int64 **)*i;
    }
    RtlRbRemoveNode(a3[3] + 64LL, a3);
    a3[2] = -1;
    while ( 1 )
    {
      v12 = *v7;
      if ( *v7 == v7 )
        break;
      if ( (_QWORD **)v12[1] != v7 || (v15 = (_QWORD *)*v12, *(_QWORD **)(*v12 + 8LL) != v12) )
        __fastfail(3u);
      *v7 = v15;
      v15[1] = v7;
      ExFreePoolWithTag(v12 - 3, 0x6D4D6456u);
    }
    v13 = 0;
    ExFreePoolWithTag(a3, 0x6D4D6456u);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400f6600  push    rbx
0x1400f6602  push    rbp
0x1400f6603  push    rsi
0x1400f6604  push    rdi
0x1400f6605  push    r12
0x1400f6607  push    r13
0x1400f6609  push    r14
0x1400f660b  push    r15
0x1400f660d  sub     rsp, 28h
0x1400f6611  mov     rsi, r8
0x1400f6614  mov     rbp, rdx
0x1400f6617  mov     r14, rcx
0x1400f661a  test    r9b, r9b
0x1400f661d  jnz     loc_1400F66FF
0x1400f6623  mov     rax, [rsi+28h]
0x1400f6627  lea     rdi, [rsi+30h]
0x1400f662b  mov     r15, [rbp+30h]
0x1400f662f  mov     [rbp+28h], rax
0x1400f6633  mov     ebp, [rbp+40h]
0x1400f6636  mov     r12, [rdi]
0x1400f6639  test    rbp, rbp
0x1400f663c  jz      short loc_1400F6682
0x1400f663e  lea     rdx, [r12-18h]
0x1400f6643  lea     rcx, [r14+2A48h]
0x1400f664a  call    cs:__imp_RtlRbRemoveNode
0x1400f6651  nop     dword ptr [rax+rax+00h]
0x1400f6656  mov     rax, [r12+28h]
0x1400f665b  mov     qword ptr [r12-8], 0FFFFFFFFFFFFFFFFh
0x1400f6664  mov     [r15+28h], rax
0x1400f6668  mov     eax, [r12+48h]
0x1400f666d  test    al, 4
0x1400f666f  jnz     loc_1400F6735
0x1400f6675  mov     r15, [r15]
0x1400f6678  mov     r12, [r12]
0x1400f667c  sub     rbp, 1
0x1400f6680  jnz     short loc_1400F663E
0x1400f6682  mov     rcx, [rsi+18h]
0x1400f6686  mov     rdx, rsi
0x1400f6689  add     rcx, 40h ; '@'
0x1400f668d  call    cs:__imp_RtlRbRemoveNode
0x1400f6694  nop     dword ptr [rax+rax+00h]
0x1400f6699  mov     qword ptr [rsi+10h], 0FFFFFFFFFFFFFFFFh
0x1400f66a1  mov     ebp, 6D4D6456h
0x1400f66a6  mov     rcx, [rdi]
0x1400f66a9  cmp     rcx, rdi
0x1400f66ac  jnz     short loc_1400F66D5
0x1400f66ae  xor     ebx, ebx
0x1400f66b0  mov     edx, ebp; Tag
0x1400f66b2  mov     rcx, rsi; P
0x1400f66b5  call    cs:__imp_ExFreePoolWithTag
0x1400f66bc  nop     dword ptr [rax+rax+00h]
0x1400f66c1  mov     eax, ebx
0x1400f66c3  add     rsp, 28h
0x1400f66c7  pop     r15
0x1400f66c9  pop     r14
0x1400f66cb  pop     r13
0x1400f66cd  pop     r12
0x1400f66cf  pop     rdi
0x1400f66d0  pop     rsi
0x1400f66d1  pop     rbp
0x1400f66d2  pop     rbx
0x1400f66d3  retn
0x1400f66d5  cmp     [rcx+8], rdi
0x1400f66d9  jnz     short loc_1400F6741
0x1400f66db  mov     rax, [rcx]
0x1400f66de  cmp     [rax+8], rcx
0x1400f66e2  jnz     short loc_1400F6741
0x1400f66e4  mov     [rdi], rax
0x1400f66e7  add     rcx, 0FFFFFFFFFFFFFFE8h; P
0x1400f66eb  mov     edx, ebp; Tag
0x1400f66ed  mov     [rax+8], rdi
0x1400f66f1  call    cs:__imp_ExFreePoolWithTag
0x1400f66f8  nop     dword ptr [rax+rax+00h]
0x1400f66fd  jmp     short loc_1400F66A6
0x1400f66ff  mov     rdx, [rdx+18h]
0x1400f6703  mov     r8, [rbp+28h]
0x1400f6707  mov     rdx, [rdx+38h]
0x1400f670b  call    VsmmNtSlatMergeVaRanges
0x1400f6710  mov     ebx, eax
0x1400f6712  test    eax, eax
0x1400f6714  jns     loc_1400F6623
0x1400f671a  mov     r8d, 65Bh
0x1400f6720  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400f6727  lea     rcx, aVsmmvagpacorep; "VsmmVaGpaCorepMergeVaRanges"
0x1400f672e  call    VidTraceErrorInternal0
0x1400f6733  jmp     short loc_1400F66C1
0x1400f6735  dec     qword ptr [r14+2A68h]
0x1400f673c  jmp     loc_1400F6675
0x1400f6741  mov     ecx, 3
0x1400f6746  int     29h; Win8: RtlFailFast(ecx)
```
