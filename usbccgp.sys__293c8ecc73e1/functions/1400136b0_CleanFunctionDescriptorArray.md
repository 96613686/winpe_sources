# CleanFunctionDescriptorArray

- ea: `0x1400136b0`
- end: `0x14001376b`
- name: `CleanFunctionDescriptorArray`
- size: `187`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140026b6c`

## callees

- `0x1400136b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400136f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013708`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013720`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013738`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013753`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013708`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013720`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013738`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013753`

## pseudocode

```c
void __fastcall CleanFunctionDescriptorArray(_QWORD *P, unsigned int a2)
{
  unsigned int v2; // ebp
  unsigned int v4; // r14d
  __int64 v5; // rsi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  v2 = 0;
  v4 = a2 / 0x50;
  if ( a2 / 0x50 )
  {
    v5 = 0;
    do
    {
      v6 = (void *)P[10 * v5 + 1];
      if ( v6 )
        ExFreePoolWithTag(v6, 0);
      v7 = (void *)P[10 * v5 + 3];
      if ( v7 )
        ExFreePoolWithTag(v7, 0);
      v8 = (void *)P[10 * v5 + 5];
      if ( v8 )
        ExFreePoolWithTag(v8, 0);
      v9 = (void *)P[10 * v5 + 7];
      if ( v9 )
        ExFreePoolWithTag(v9, 0);
      ++v2;
      ++v5;
    }
    while ( v2 < v4 );
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x1400136b0  push    rbx
0x1400136b2  push    rbp
0x1400136b3  push    rsi
0x1400136b4  push    rdi
0x1400136b5  push    r14
0x1400136b7  sub     rsp, 20h
0x1400136bb  mov     edx, edx
0x1400136bd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400136c7  mul     rdx
0x1400136ca  xor     ebp, ebp
0x1400136cc  mov     rdi, rcx
0x1400136cf  mov     r14, rdx
0x1400136d2  shr     r14, 6
0x1400136d6  test    r14d, r14d
0x1400136d9  jz      short loc_14001374E
0x1400136db  xor     esi, esi
0x1400136dd  lea     rbx, [rsi+rsi*4]
0x1400136e1  add     rbx, rbx
0x1400136e4  mov     rcx, [rdi+rbx*8+8]; P
0x1400136e9  test    rcx, rcx
0x1400136ec  jz      short loc_1400136FC
0x1400136ee  xor     edx, edx; Tag
0x1400136f0  call    cs:__imp_ExFreePoolWithTag
0x1400136f7  nop     dword ptr [rax+rax+00h]
0x1400136fc  mov     rcx, [rdi+rbx*8+18h]; P
0x140013701  test    rcx, rcx
0x140013704  jz      short loc_140013714
0x140013706  xor     edx, edx; Tag
0x140013708  call    cs:__imp_ExFreePoolWithTag
0x14001370f  nop     dword ptr [rax+rax+00h]
0x140013714  mov     rcx, [rdi+rbx*8+28h]; P
0x140013719  test    rcx, rcx
0x14001371c  jz      short loc_14001372C
0x14001371e  xor     edx, edx; Tag
0x140013720  call    cs:__imp_ExFreePoolWithTag
0x140013727  nop     dword ptr [rax+rax+00h]
0x14001372c  mov     rcx, [rdi+rbx*8+38h]; P
0x140013731  test    rcx, rcx
0x140013734  jz      short loc_140013744
0x140013736  xor     edx, edx; Tag
0x140013738  call    cs:__imp_ExFreePoolWithTag
0x14001373f  nop     dword ptr [rax+rax+00h]
0x140013744  inc     ebp
0x140013746  inc     rsi
0x140013749  cmp     ebp, r14d
0x14001374c  jb      short loc_1400136DD
0x14001374e  xor     edx, edx; Tag
0x140013750  mov     rcx, rdi; P
0x140013753  call    cs:__imp_ExFreePoolWithTag
0x14001375a  nop     dword ptr [rax+rax+00h]
0x14001375f  add     rsp, 20h
0x140013763  pop     r14
0x140013765  pop     rdi
0x140013766  pop     rsi
0x140013767  pop     rbp
0x140013768  pop     rbx
0x140013769  retn
```
