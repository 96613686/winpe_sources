# _RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory14SetEntryObject

- ea: `0x140013570`
- end: `0x140013662`
- name: `_RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory14SetEntryObject`
- size: `242`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009270`

## callees

- `0x140013570`
- `0x140018450`
- `0x1400184d7`

## pseudocode

```c
__int64 __fastcall RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory14SetEntryObject(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  unsigned int v3; // r9d
  __int64 result; // rax
  unsigned __int64 v5; // rax
  int v6; // r10d
  unsigned __int64 v7; // r9
  __int64 v8; // r9
  unsigned int v9; // edx
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r9
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx

  v3 = *(_DWORD *)(a1 + 24);
  result = v3 + (*(_DWORD *)(a1 + 28) << 16) - 0x10000;
  if ( a2 < (unsigned int)result )
  {
    v5 = ((a2 - v3) >> 16) + 1;
    if ( a2 < v3 )
      v5 = 0;
    v6 = v3 - 0x10000 + ((_DWORD)v5 << 16);
    if ( a2 < v3 )
      v6 = 0;
    v7 = *(_QWORD *)(a1 + 16);
    if ( v7 <= v5 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v5,
        v7,
        &anon_74322c9add977dfab17ab4536cfbe633_2_llvm_14523797218057561932);
    v8 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v5);
    if ( !v8 )
      RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_74322c9add977dfab17ab4536cfbe633_2_llvm_14523797218057561932);
    v9 = a2 - v6;
    result = *(unsigned int *)(v8 + 64);
    if ( v9 < (unsigned int)result )
    {
      if ( __OFSUB__(0, *(_QWORD *)v8) )
        RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_74322c9add977dfab17ab4536cfbe633_24_llvm_14523797218057561932);
      v10 = v9 >> 8;
      if ( v10 >= *(_QWORD *)(v8 + 16) )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v10,
          *(_QWORD *)(v8 + 16),
          &anon_74322c9add977dfab17ab4536cfbe633_20_llvm_14523797218057561932);
      v11 = *(_QWORD *)(v8 + 8);
      v12 = 3 * v10;
      v13 = (unsigned __int8)v9;
      v14 = *(_QWORD *)(v11 + 8 * v12 + 16);
      if ( v13 >= v14 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v13,
          v14,
          &anon_74322c9add977dfab17ab4536cfbe633_21_llvm_14523797218057561932);
      result = *(_QWORD *)(v11 + 8 * v12 + 8);
      *(_QWORD *)(result + (unsigned int)(16 * v13) + 8) = a3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013570  push    rsi
0x140013571  sub     rsp, 20h
0x140013575  mov     r9d, [rcx+18h]
0x140013579  mov     eax, [rcx+1Ch]
0x14001357c  shl     eax, 10h
0x14001357f  add     eax, r9d
0x140013582  add     eax, 0FFFF0000h
0x140013587  cmp     edx, eax
0x140013589  jnb     loc_140013616
0x14001358f  lea     r11d, [r9-10000h]
0x140013596  mov     eax, edx
0x140013598  sub     eax, r9d
0x14001359b  shr     eax, 10h
0x14001359e  inc     eax
0x1400135a0  xor     esi, esi
0x1400135a2  cmp     edx, r9d
0x1400135a5  cmovb   eax, esi
0x1400135a8  mov     r10d, eax
0x1400135ab  shl     r10d, 10h
0x1400135af  add     r10d, r11d
0x1400135b2  cmp     edx, r9d
0x1400135b5  cmovb   r10d, esi
0x1400135b9  mov     r9, [rcx+10h]
0x1400135bd  cmp     r9, rax
0x1400135c0  jbe     short loc_140013634
0x1400135c2  mov     rcx, [rcx+8]
0x1400135c6  mov     r9, [rcx+rax*8]
0x1400135ca  test    r9, r9
0x1400135cd  jz      short loc_14001361C
0x1400135cf  sub     edx, r10d
0x1400135d2  mov     eax, [r9+40h]
0x1400135d6  cmp     edx, eax
0x1400135d8  jnb     short loc_140013616
0x1400135da  xor     eax, eax
0x1400135dc  cmp     rax, [r9]
0x1400135df  jo      short loc_140013628
0x1400135e1  mov     rax, [r9+10h]
0x1400135e5  mov     ecx, edx
0x1400135e7  shr     ecx, 8
0x1400135ea  cmp     rcx, rax
0x1400135ed  jnb     short loc_140013646
0x1400135ef  mov     edx, edx
0x1400135f1  mov     rax, [r9+8]
0x1400135f5  lea     r9, [rcx+rcx*2]
0x1400135f9  movzx   ecx, dl
0x1400135fc  mov     rdx, [rax+r9*8+10h]
0x140013601  cmp     rcx, rdx
0x140013604  jnb     short loc_140013655
0x140013606  lea     rax, [rax+r9*8]
0x14001360a  mov     rax, [rax+8]
0x14001360e  shl     ecx, 4
0x140013611  mov     [rax+rcx+8], r8
0x140013616  add     rsp, 20h
0x14001361a  pop     rsi
0x14001361b  retn
0x14001361c  lea     rcx, anon_74322c9add977dfab17ab4536cfbe633_2_llvm_14523797218057561932
0x140013623  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x140013628  lea     rcx, anon_74322c9add977dfab17ab4536cfbe633_24_llvm_14523797218057561932
0x14001362f  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x140013634  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_2_llvm_14523797218057561932
0x14001363b  mov     rcx, rax
0x14001363e  mov     rdx, r9
0x140013641  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140013646  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_20_llvm_14523797218057561932
0x14001364d  mov     rdx, rax
0x140013650  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140013655  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_21_llvm_14523797218057561932
0x14001365c  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
