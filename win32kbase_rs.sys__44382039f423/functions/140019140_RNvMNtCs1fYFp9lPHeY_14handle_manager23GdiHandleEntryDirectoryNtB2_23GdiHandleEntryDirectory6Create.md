# _RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory6Create

- ea: `0x140019140`
- end: `0x1400193a9`
- name: `_RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory6Create`
- size: `617`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000a400`

## callees

- `0x140005590`
- `0x14000a5f0`
- `0x140013e50`
- `0x14001790a`
- `0x140017a10`
- `0x140018470`
- `0x140018f20`
- `0x140019140`

## pseudocode

```c
__int64 __fastcall RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory6Create(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r14
  __int128 v9; // rax
  __int64 v10; // r15
  __int64 v11; // r13
  __int64 v12; // r14
  __int128 v13; // xmm0
  char **v15; // rax
  __int64 v16; // [rsp+0h] [rbp-A8h] BYREF
  __int128 v17; // [rsp+30h] [rbp-78h] BYREF
  __int128 v18; // [rsp+40h] [rbp-68h]
  _BYTE v19[24]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v20; // [rsp+68h] [rbp-40h]

  *(_QWORD *)v19 = 0;
  *(_QWORD *)&v19[8] = 8;
  *(_QWORD *)&v19[16] = 0;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182(
    (unsigned int)&v17,
    (unsigned int)v19,
    256,
    8,
    8);
  if ( (_DWORD)v17 == 1 )
  {
    RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_(v19);
    *(_DWORD *)(a1 + 8) = 14;
    *(_QWORD *)a1 = 0x8000000000000000uLL;
  }
  else
  {
    v6 = *((_QWORD *)&v17 + 1);
    BYTE14(v18) = 0;
    WORD6(v18) = 1;
    *(_QWORD *)&v17 = 256;
    *(_QWORD *)&v18 = 0;
    DWORD2(v18) = a3;
    RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable7__Create_llvm_14523797218057561932(
      (__int64)v19,
      a3,
      0);
    if ( v19[0] )
    {
      *(_DWORD *)(a1 + 8) = *(_DWORD *)&v19[4];
      *(_QWORD *)a1 = 0x8000000000000000uLL;
      RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_(&v17);
      Win32FreePool_0(v6);
    }
    else
    {
      v7 = *(_QWORD *)&v19[8];
      if ( *(_BYTE *)(*(_QWORD *)&v19[8] + 56LL) == 1 && *(_QWORD *)(*(_QWORD *)&v19[8] + 48LL) )
      {
        v8 = *(_QWORD *)&v19[8];
        Win32FreePool_0(*(_QWORD *)(*(_QWORD *)&v19[8] + 32LL));
        v7 = v8;
      }
      *(_QWORD *)(v7 + 32) = a2;
      *(_QWORD *)(v7 + 40) = a3;
      *(_QWORD *)(v7 + 48) = a3;
      *(_BYTE *)(v7 + 56) = 0;
      *(_QWORD *)&v9 = RNvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtBz_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB39_EINtB2_11FallibleVecB11_B39_E8try_pushB1Z_(&v17);
      if ( (_QWORD)v9 != 0x8000000000000001uLL )
      {
        *(_OWORD *)v19 = v9;
        v15 = &anon_74322c9add977dfab17ab4536cfbe633_15_llvm_14523797218057561932;
        goto LABEL_21;
      }
      v10 = 255;
      do
      {
        while ( 1 )
        {
          v11 = v18;
          if ( (_QWORD)v17 == (_QWORD)v18 )
            break;
          *(_QWORD *)(*((_QWORD *)&v17 + 1) + 8 * v18) = 0;
          *(_QWORD *)&v18 = v18 + 1;
          if ( !--v10 )
            goto LABEL_17;
        }
        v12 = 2 * v18;
        if ( (unsigned __int64)(2 * v18) < 5 )
          v12 = 4;
        RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182(
          (unsigned int)v19,
          (unsigned int)&v17,
          v12,
          8,
          8);
        if ( v19[0] )
          goto LABEL_22;
        *((_QWORD *)&v17 + 1) = *(_QWORD *)&v19[8];
        *(_QWORD *)&v17 = v12;
        *(_QWORD *)(*(_QWORD *)&v19[8] + 8 * v11) = 0;
        *(_QWORD *)&v18 = v18 + 1;
        --v10;
      }
      while ( v10 );
LABEL_17:
      v13 = v17;
      *(_OWORD *)(a1 + 16) = v18;
      *(_OWORD *)a1 = v13;
    }
  }
  if ( _security_cookie != ((unsigned __int64)&v16 ^ v20) )
  {
LABEL_22:
    *(_OWORD *)v19 = *(_OWORD *)&v19[8];
    v15 = &anon_74322c9add977dfab17ab4536cfbe633_14_llvm_14523797218057561932;
LABEL_21:
    RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
      (unsigned int)&anon_74322c9add977dfab17ab4536cfbe633_13_llvm_14523797218057561932,
      43,
      (unsigned int)v19,
      (unsigned int)&anon_74322c9add977dfab17ab4536cfbe633_12_llvm_14523797218057561932,
      (__int64)v15);
  }
  return a1;
}

```

## disassembly

```asm
0x140019140  push    r15
0x140019142  push    r14
0x140019144  push    r13
0x140019146  push    r12
0x140019148  push    rsi
0x140019149  push    rdi
0x14001914a  push    rbx
0x14001914b  sub     rsp, 70h
0x14001914f  mov     ebx, r8d
0x140019152  mov     rdi, rdx
0x140019155  mov     rsi, rcx
0x140019158  mov     rax, cs:__security_cookie
0x14001915f  xor     rax, rsp
0x140019162  mov     [rsp+0A8h+var_40], rax
0x140019167  mov     r15, 8000000000000000h
0x140019171  mov     qword ptr [rsp+0A8h+var_58], 0
0x14001917a  mov     qword ptr [rsp+0A8h+var_58+8], 8
0x140019183  mov     qword ptr [rsp+0A8h+var_58+10h], 0
0x14001918c  mov     [rsp+0A8h+var_88], 8
0x140019195  lea     rcx, [rsp+0A8h+var_78]
0x14001919a  lea     rdx, [rsp+0A8h+var_58]
0x14001919f  mov     r8d, 100h
0x1400191a5  mov     r9d, 8
0x1400191ab  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182
0x1400191b0  cmp     dword ptr [rsp+0A8h+var_78], 1
0x1400191b5  jnz     short loc_1400191D0
0x1400191b7  lea     rcx, [rsp+0A8h+var_58]
0x1400191bc  call    _RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_
0x1400191c1  mov     dword ptr [rsi+8], 0Eh
0x1400191c8  mov     [rsi], r15
0x1400191cb  jmp     loc_14001932F
0x1400191d0  mov     r14, qword ptr [rsp+0A8h+var_78+8]
0x1400191d5  mov     byte ptr [rsp+0A8h+var_68+0Eh], 0
0x1400191da  mov     word ptr [rsp+0A8h+var_68+0Ch], 1
0x1400191e1  mov     qword ptr [rsp+0A8h+var_78], 100h
0x1400191ea  mov     qword ptr [rsp+0A8h+var_78+8], r14
0x1400191ef  mov     qword ptr [rsp+0A8h+var_68], 0
0x1400191f8  mov     dword ptr [rsp+0A8h+var_68+8], ebx
0x1400191fc  lea     rcx, [rsp+0A8h+var_58]
0x140019201  mov     edx, ebx
0x140019203  xor     r8d, r8d
0x140019206  call    _RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable7__Create_llvm_14523797218057561932
0x14001920b  cmp     [rsp+0A8h+var_58], 0
0x140019210  jz      short loc_140019233
0x140019212  mov     eax, dword ptr [rsp+0A8h+var_58+4]
0x140019216  mov     [rsi+8], eax
0x140019219  mov     [rsi], r15
0x14001921c  lea     rcx, [rsp+0A8h+var_78]
0x140019221  call    _RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_
0x140019226  mov     rcx, r14
0x140019229  call    Win32FreePool_0
0x14001922e  jmp     loc_14001932F
0x140019233  mov     rdx, qword ptr [rsp+0A8h+var_58+8]
0x140019238  mov     ebx, ebx
0x14001923a  movzx   eax, byte ptr [rdx+38h]
0x14001923e  cmp     al, 2
0x140019240  jz      short loc_14001925C
0x140019242  cmp     al, 1
0x140019244  jnz     short loc_14001925C
0x140019246  cmp     qword ptr [rdx+30h], 0
0x14001924b  jz      short loc_14001925C
0x14001924d  mov     rcx, [rdx+20h]
0x140019251  mov     r14, rdx
0x140019254  call    Win32FreePool_0
0x140019259  mov     rdx, r14
0x14001925c  mov     [rdx+20h], rdi
0x140019260  mov     [rdx+28h], rbx
0x140019264  mov     [rdx+30h], rbx
0x140019268  mov     byte ptr [rdx+38h], 0
0x14001926c  lea     rcx, [rsp+0A8h+var_78]
0x140019271  call    _RNvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtBz_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB39_EINtB2_11FallibleVecB11_B39_E8try_pushB1Z_
0x140019276  inc     r15
0x140019279  cmp     rax, r15
0x14001927c  jnz     loc_140019356
0x140019282  mov     r15d, 0FFh
0x140019288  mov     r12d, 4
0x14001928e  lea     rdi, [rsp+0A8h+var_58]
0x140019293  lea     rbx, [rsp+0A8h+var_78]
0x140019298  nop     dword ptr [rax+rax+00000000h]
0x1400192a0  mov     r13, qword ptr [rsp+0A8h+var_68]
0x1400192a5  cmp     qword ptr [rsp+0A8h+var_78], r13
0x1400192aa  jz      short loc_1400192C5
0x1400192ac  mov     rax, qword ptr [rsp+0A8h+var_78+8]
0x1400192b1  mov     qword ptr [rax+r13*8], 0
0x1400192b9  inc     qword ptr [rsp+0A8h+var_68]
0x1400192be  dec     r15
0x1400192c1  jnz     short loc_1400192A0
0x1400192c3  jmp     short loc_14001931E
0x1400192c5  lea     r14, ds:0[r13*2]
0x1400192cd  cmp     r14, 5
0x1400192d1  cmovb   r14, r12
0x1400192d5  mov     [rsp+0A8h+var_88], 8
0x1400192de  mov     r9d, 8
0x1400192e4  mov     rcx, rdi
0x1400192e7  mov     rdx, rbx
0x1400192ea  mov     r8, r14
0x1400192ed  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182
0x1400192f2  cmp     [rsp+0A8h+var_58], 0
0x1400192f7  jnz     loc_140019396
0x1400192fd  mov     rax, qword ptr [rsp+0A8h+var_58+8]
0x140019302  mov     qword ptr [rsp+0A8h+var_78+8], rax
0x140019307  mov     qword ptr [rsp+0A8h+var_78], r14
0x14001930c  mov     qword ptr [rax+r13*8], 0
0x140019314  inc     qword ptr [rsp+0A8h+var_68]
0x140019319  dec     r15
0x14001931c  jnz     short loc_1400192A0
0x14001931e  movups  xmm0, [rsp+0A8h+var_78]
0x140019323  movups  xmm1, [rsp+0A8h+var_68]
0x140019328  movups  xmmword ptr [rsi+10h], xmm1
0x14001932c  movups  xmmword ptr [rsi], xmm0
0x14001932f  mov     rax, [rsp+0A8h+var_40]
0x140019334  xor     rax, rsp
0x140019337  mov     rcx, cs:__security_cookie
0x14001933e  cmp     rcx, rax
0x140019341  jnz     short loc_140019389
0x140019343  mov     rax, rsi
0x140019346  add     rsp, 70h
0x14001934a  pop     rbx
0x14001934b  pop     rdi
0x14001934c  pop     rsi
0x14001934d  pop     r12
0x14001934f  pop     r13
0x140019351  pop     r14
0x140019353  pop     r15
0x140019355  retn
0x140019356  mov     qword ptr [rsp+0A8h+var_58], rax
0x14001935b  mov     qword ptr [rsp+0A8h+var_58+8], rdx
0x140019360  lea     rax, anon_74322c9add977dfab17ab4536cfbe633_15_llvm_14523797218057561932
0x140019367  mov     [rsp+0A8h+var_88], rax
0x14001936c  lea     rcx, anon_74322c9add977dfab17ab4536cfbe633_13_llvm_14523797218057561932
0x140019373  lea     r9, anon_74322c9add977dfab17ab4536cfbe633_12_llvm_14523797218057561932
0x14001937a  lea     r8, [rsp+0A8h+var_58]
0x14001937f  mov     edx, 2Bh ; '+'
0x140019384  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
0x140019389  mov     rcx, [rsp+0A8h+var_40]
0x14001938e  xor     rcx, rsp; StackCookie
0x140019391  call    __security_check_cookie
0x140019396  movups  xmm0, xmmword ptr [rsp+0A8h+var_58+8]
0x14001939b  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x1400193a0  lea     rax, anon_74322c9add977dfab17ab4536cfbe633_14_llvm_14523797218057561932
0x1400193a7  jmp     short loc_140019367
```
