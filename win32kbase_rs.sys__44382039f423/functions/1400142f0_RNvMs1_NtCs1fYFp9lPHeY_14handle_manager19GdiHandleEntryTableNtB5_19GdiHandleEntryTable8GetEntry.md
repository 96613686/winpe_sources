# _RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable8GetEntry

- ea: `0x1400142f0`
- end: `0x1400143bd`
- name: `_RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable8GetEntry`
- size: `205`
- prototype: `__int64 __fastcall(__int64, unsigned int, char)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x140009150`
- `0x140009270`
- `0x140009390`
- `0x140009530`
- `0x1400096c0`
- `0x1400099d0`
- `0x140009b50`
- `0x140009c50`
- `0x140009e00`
- `0x14000a0d0`
- `0x14000a250`

## callees

- `0x1400142f0`
- `0x140018450`
- `0x1400184d7`

## pseudocode

```c
__int64 __fastcall RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable8GetEntry(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 v4; // rax
  __int64 v5; // r8
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdx

  if ( !a3 || a2 >= *(_DWORD *)(a1 + 64) )
  {
    if ( a2 >= *(_DWORD *)(a1 + 64) )
      return 0;
    if ( __OFSUB__(0, *(_QWORD *)a1) )
      RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_74322c9add977dfab17ab4536cfbe633_23_llvm_14523797218057561932);
    v3 = *(_QWORD *)(a1 + 16);
    v4 = a2 >> 8;
    if ( v4 >= v3 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        a2 >> 8,
        v3,
        &anon_74322c9add977dfab17ab4536cfbe633_20_llvm_14523797218057561932);
    v5 = *(_QWORD *)(a1 + 8);
    v6 = *(_QWORD *)(v5 + 24 * v4 + 16);
    if ( (unsigned __int8)a2 >= v6 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        (unsigned __int8)a2,
        v6,
        &anon_74322c9add977dfab17ab4536cfbe633_21_llvm_14523797218057561932);
    if ( !*(_QWORD *)(*(_QWORD *)(v5 + 24 * v4 + 8) + 16 * (unsigned int)(unsigned __int8)a2 + 8LL) )
      return 0;
  }
  if ( *(_BYTE *)(a1 + 56) == 2 )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_74322c9add977dfab17ab4536cfbe633_35_llvm_14523797218057561932);
  v7 = a2;
  v8 = *(_QWORD *)(a1 + 40);
  if ( v8 <= v7 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v7,
      v8,
      &anon_74322c9add977dfab17ab4536cfbe633_35_llvm_14523797218057561932);
  return *(_QWORD *)(a1 + 32) + 24 * v7;
}

```

## disassembly

```asm
0x1400142f0  sub     rsp, 28h
0x1400142f4  test    r8b, r8b
0x1400142f7  jz      short loc_140014300
0x1400142f9  mov     eax, [rcx+40h]
0x1400142fc  cmp     edx, eax
0x1400142fe  jb      short loc_140014348
0x140014300  mov     eax, [rcx+40h]
0x140014303  cmp     edx, eax
0x140014305  jnb     short loc_14001436A
0x140014307  xor     eax, eax
0x140014309  cmp     rax, [rcx]
0x14001430c  jo      short loc_14001437D
0x14001430e  mov     r9, [rcx+10h]
0x140014312  mov     eax, edx
0x140014314  shr     eax, 8
0x140014317  cmp     rax, r9
0x14001431a  jnb     short loc_140014398
0x14001431c  mov     r9d, edx
0x14001431f  mov     r8, [rcx+8]
0x140014323  lea     r10, [rax+rax*2]
0x140014327  movzx   eax, r9b
0x14001432b  mov     r9, [r8+r10*8+10h]
0x140014330  cmp     rax, r9
0x140014333  jnb     short loc_1400143AA
0x140014335  lea     r8, [r8+r10*8]
0x140014339  mov     r8, [r8+8]
0x14001433d  shl     eax, 4
0x140014340  cmp     qword ptr [r8+rax+8], 0
0x140014346  jz      short loc_14001436A
0x140014348  cmp     byte ptr [rcx+38h], 2
0x14001434c  jz      short loc_140014371
0x14001434e  mov     eax, edx
0x140014350  mov     rdx, [rcx+28h]
0x140014354  cmp     rdx, rax
0x140014357  jbe     short loc_140014389
0x140014359  lea     rax, [rax+rax*2]
0x14001435d  shl     rax, 3
0x140014361  add     rax, [rcx+20h]
0x140014365  add     rsp, 28h
0x140014369  retn
0x14001436a  xor     eax, eax
0x14001436c  add     rsp, 28h
0x140014370  retn
0x140014371  lea     rcx, anon_74322c9add977dfab17ab4536cfbe633_35_llvm_14523797218057561932
0x140014378  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x14001437d  lea     rcx, anon_74322c9add977dfab17ab4536cfbe633_23_llvm_14523797218057561932
0x140014384  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x140014389  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_35_llvm_14523797218057561932
0x140014390  mov     rcx, rax
0x140014393  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140014398  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_20_llvm_14523797218057561932
0x14001439f  mov     rcx, rax
0x1400143a2  mov     rdx, r9
0x1400143a5  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x1400143aa  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_21_llvm_14523797218057561932
0x1400143b1  mov     rcx, rax
0x1400143b4  mov     rdx, r9
0x1400143b7  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
