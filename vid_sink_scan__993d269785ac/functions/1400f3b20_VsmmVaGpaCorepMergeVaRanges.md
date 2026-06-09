# VsmmVaGpaCorepMergeVaRanges

- ea: `0x1400f3b20`
- end: `0x1400f3c68`
- name: `VsmmVaGpaCorepMergeVaRanges`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400eae60`
- `0x1400ec7b0`

## callees

- `0x140038630`
- `0x1400f3b20`
- `0x1400f3c70`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400f3b6a`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400f3bad`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400f3b6a`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400f3bad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3bd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3c11`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3bd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3c11`

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
0x1400f3b20  push    rbx
0x1400f3b22  push    rbp
0x1400f3b23  push    rsi
0x1400f3b24  push    rdi
0x1400f3b25  push    r12
0x1400f3b27  push    r13
0x1400f3b29  push    r14
0x1400f3b2b  push    r15
0x1400f3b2d  sub     rsp, 28h
0x1400f3b31  mov     rsi, r8
0x1400f3b34  mov     rbp, rdx
0x1400f3b37  mov     r14, rcx
0x1400f3b3a  test    r9b, r9b
0x1400f3b3d  jnz     loc_1400F3C1F
0x1400f3b43  mov     rax, [rsi+28h]
0x1400f3b47  lea     rdi, [rsi+30h]
0x1400f3b4b  mov     r15, [rbp+30h]
0x1400f3b4f  mov     [rbp+28h], rax
0x1400f3b53  mov     ebp, [rbp+40h]
0x1400f3b56  mov     r12, [rdi]
0x1400f3b59  test    rbp, rbp
0x1400f3b5c  jz      short loc_1400F3BA2
0x1400f3b5e  lea     rdx, [r12-18h]
0x1400f3b63  lea     rcx, [r14+2A48h]
0x1400f3b6a  call    cs:__imp_RtlRbRemoveNode
0x1400f3b71  nop     dword ptr [rax+rax+00h]
0x1400f3b76  mov     rax, [r12+28h]
0x1400f3b7b  mov     qword ptr [r12-8], 0FFFFFFFFFFFFFFFFh
0x1400f3b84  mov     [r15+28h], rax
0x1400f3b88  mov     eax, [r12+48h]
0x1400f3b8d  test    al, 4
0x1400f3b8f  jnz     loc_1400F3C55
0x1400f3b95  mov     r15, [r15]
0x1400f3b98  mov     r12, [r12]
0x1400f3b9c  sub     rbp, 1
0x1400f3ba0  jnz     short loc_1400F3B5E
0x1400f3ba2  mov     rcx, [rsi+18h]
0x1400f3ba6  mov     rdx, rsi
0x1400f3ba9  add     rcx, 40h ; '@'
0x1400f3bad  call    cs:__imp_RtlRbRemoveNode
0x1400f3bb4  nop     dword ptr [rax+rax+00h]
0x1400f3bb9  mov     qword ptr [rsi+10h], 0FFFFFFFFFFFFFFFFh
0x1400f3bc1  mov     ebp, 6D4D6456h
0x1400f3bc6  mov     rcx, [rdi]
0x1400f3bc9  cmp     rcx, rdi
0x1400f3bcc  jnz     short loc_1400F3BF5
0x1400f3bce  xor     ebx, ebx
0x1400f3bd0  mov     edx, ebp; Tag
0x1400f3bd2  mov     rcx, rsi; P
0x1400f3bd5  call    cs:__imp_ExFreePoolWithTag
0x1400f3bdc  nop     dword ptr [rax+rax+00h]
0x1400f3be1  mov     eax, ebx
0x1400f3be3  add     rsp, 28h
0x1400f3be7  pop     r15
0x1400f3be9  pop     r14
0x1400f3beb  pop     r13
0x1400f3bed  pop     r12
0x1400f3bef  pop     rdi
0x1400f3bf0  pop     rsi
0x1400f3bf1  pop     rbp
0x1400f3bf2  pop     rbx
0x1400f3bf3  retn
0x1400f3bf5  cmp     [rcx+8], rdi
0x1400f3bf9  jnz     short loc_1400F3C61
0x1400f3bfb  mov     rax, [rcx]
0x1400f3bfe  cmp     [rax+8], rcx
0x1400f3c02  jnz     short loc_1400F3C61
0x1400f3c04  mov     [rdi], rax
0x1400f3c07  add     rcx, 0FFFFFFFFFFFFFFE8h; P
0x1400f3c0b  mov     edx, ebp; Tag
0x1400f3c0d  mov     [rax+8], rdi
0x1400f3c11  call    cs:__imp_ExFreePoolWithTag
0x1400f3c18  nop     dword ptr [rax+rax+00h]
0x1400f3c1d  jmp     short loc_1400F3BC6
0x1400f3c1f  mov     rdx, [rdx+18h]
0x1400f3c23  mov     r8, [rbp+28h]
0x1400f3c27  mov     rdx, [rdx+38h]
0x1400f3c2b  call    VsmmNtSlatMergeVaRanges
0x1400f3c30  mov     ebx, eax
0x1400f3c32  test    eax, eax
0x1400f3c34  jns     loc_1400F3B43
0x1400f3c3a  mov     r8d, 65Bh
0x1400f3c40  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400f3c47  lea     rcx, aVsmmvagpacorep; "VsmmVaGpaCorepMergeVaRanges"
0x1400f3c4e  call    VidTraceErrorInternal0
0x1400f3c53  jmp     short loc_1400F3BE1
0x1400f3c55  dec     qword ptr [r14+2A68h]
0x1400f3c5c  jmp     loc_1400F3B95
0x1400f3c61  mov     ecx, 3
0x1400f3c66  int     29h; Win8: RtlFailFast(ecx)
```
