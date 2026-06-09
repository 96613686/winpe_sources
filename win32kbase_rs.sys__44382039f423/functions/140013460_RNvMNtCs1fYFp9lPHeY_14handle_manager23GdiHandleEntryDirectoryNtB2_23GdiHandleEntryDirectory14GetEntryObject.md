# _RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory14GetEntryObject

- ea: `0x140013460`
- end: `0x14001355f`
- name: `_RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory14GetEntryObject`
- size: `255`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140009150`
- `0x140009530`
- `0x140009b50`
- `0x140009c50`
- `0x140009e00`

## callees

- `0x140013460`
- `0x140018450`
- `0x1400184d7`

## pseudocode

```c
__int64 __fastcall RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory14GetEntryObject(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v2; // r8d
  __int64 result; // rax
  unsigned __int64 v4; // r9
  int v5; // r10d
  unsigned __int64 v6; // rax
  __int64 v7; // r8
  unsigned int v8; // edx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx

  v2 = *(_DWORD *)(a1 + 24);
  result = 0;
  if ( a2 < (*(_DWORD *)(a1 + 28) << 16) + v2 - 0x10000 )
  {
    v4 = ((a2 - v2) >> 16) + 1;
    if ( a2 < v2 )
      v4 = 0;
    v5 = v2 - 0x10000 + ((_DWORD)v4 << 16);
    if ( a2 < v2 )
      v5 = 0;
    v6 = *(_QWORD *)(a1 + 16);
    if ( v6 <= v4 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v4,
        v6,
        &anon_74322c9add977dfab17ab4536cfbe633_1_llvm_14523797218057561932);
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4);
    if ( !v7 )
      RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_74322c9add977dfab17ab4536cfbe633_1_llvm_14523797218057561932);
    v8 = a2 - v5;
    if ( v8 >= *(_DWORD *)(v7 + 64) )
    {
      return 0;
    }
    else
    {
      if ( __OFSUB__(0, *(_QWORD *)v7) )
        RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_74322c9add977dfab17ab4536cfbe633_23_llvm_14523797218057561932);
      v9 = *(_QWORD *)(v7 + 16);
      v10 = v8 >> 8;
      if ( v10 >= v9 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v10,
          v9,
          &anon_74322c9add977dfab17ab4536cfbe633_20_llvm_14523797218057561932);
      v11 = *(_QWORD *)(v7 + 8);
      v12 = 3 * v10;
      v13 = (unsigned __int8)v8;
      v14 = *(_QWORD *)(v11 + 8 * v12 + 16);
      if ( v13 >= v14 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v13,
          v14,
          &anon_74322c9add977dfab17ab4536cfbe633_21_llvm_14523797218057561932);
      return *(_QWORD *)(*(_QWORD *)(v11 + 8 * v12 + 8) + (unsigned int)(16 * v13) + 8LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013460  sub     rsp, 28h
0x140013464  mov     r8d, [rcx+18h]
0x140013468  mov     eax, [rcx+1Ch]
0x14001346b  shl     eax, 10h
0x14001346e  lea     r9d, [rax+r8]
0x140013472  add     r9d, 0FFFF0000h
0x140013479  xor     eax, eax
0x14001347b  cmp     edx, r9d
0x14001347e  jnb     loc_14001350D
0x140013484  lea     r11d, [r8-10000h]
0x14001348b  mov     r9d, edx
0x14001348e  sub     r9d, r8d
0x140013491  shr     r9d, 10h
0x140013495  inc     r9d
0x140013498  cmp     edx, r8d
0x14001349b  cmovb   r9d, eax
0x14001349f  mov     r10d, r9d
0x1400134a2  shl     r10d, 10h
0x1400134a6  add     r10d, r11d
0x1400134a9  cmp     edx, r8d
0x1400134ac  cmovb   r10d, eax
0x1400134b0  mov     rax, [rcx+10h]
0x1400134b4  cmp     rax, r9
0x1400134b7  jbe     short loc_140013531
0x1400134b9  mov     rax, [rcx+8]
0x1400134bd  mov     r8, [rax+r9*8]
0x1400134c1  test    r8, r8
0x1400134c4  jz      short loc_140013519
0x1400134c6  sub     edx, r10d
0x1400134c9  mov     eax, [r8+40h]
0x1400134cd  cmp     edx, eax
0x1400134cf  jnb     short loc_140013512
0x1400134d1  xor     eax, eax
0x1400134d3  cmp     rax, [r8]
0x1400134d6  jo      short loc_140013525
0x1400134d8  mov     rax, [r8+10h]
0x1400134dc  mov     ecx, edx
0x1400134de  shr     ecx, 8
0x1400134e1  cmp     rcx, rax
0x1400134e4  jnb     short loc_140013543
0x1400134e6  mov     edx, edx
0x1400134e8  mov     rax, [r8+8]
0x1400134ec  lea     r8, [rcx+rcx*2]
0x1400134f0  movzx   ecx, dl
0x1400134f3  mov     rdx, [rax+r8*8+10h]
0x1400134f8  cmp     rcx, rdx
0x1400134fb  jnb     short loc_140013552
0x1400134fd  lea     rax, [rax+r8*8]
0x140013501  mov     rax, [rax+8]
0x140013505  shl     ecx, 4
0x140013508  mov     rax, [rax+rcx+8]
0x14001350d  add     rsp, 28h
0x140013511  retn
0x140013512  xor     eax, eax
0x140013514  add     rsp, 28h
0x140013518  retn
0x140013519  lea     rcx, anon_74322c9add977dfab17ab4536cfbe633_1_llvm_14523797218057561932
0x140013520  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x140013525  lea     rcx, anon_74322c9add977dfab17ab4536cfbe633_23_llvm_14523797218057561932
0x14001352c  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x140013531  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_1_llvm_14523797218057561932
0x140013538  mov     rcx, r9
0x14001353b  mov     rdx, rax
0x14001353e  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140013543  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_20_llvm_14523797218057561932
0x14001354a  mov     rdx, rax
0x14001354d  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140013552  lea     r8, anon_74322c9add977dfab17ab4536cfbe633_21_llvm_14523797218057561932
0x140013559  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
```
