# _RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable7__Create.llvm.14523797218057561932

- ea: `0x140013e50`
- end: `0x1400142dd`
- name: `_RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable7__Create.llvm.14523797218057561932`
- size: `1165`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140013670`
- `0x140019140`

## callees

- `0x140013e50`
- `0x14001790a`
- `0x140017940`
- `0x140017a10`
- `0x140017f00`
- `0x140018470`
- `0x140018f20`
- `0x140019030`

## pseudocode

```c
unsigned __int64 __fastcall RNvMs1_NtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTableNtB5_19GdiHandleEntryTable7__Create_llvm_14523797218057561932(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  unsigned __int64 v8; // r12
  int v9; // r12d
  unsigned __int64 v10; // r14
  __int64 v11; // r15
  __int64 v12; // r14
  char v13; // al
  unsigned __int64 result; // rax
  __int64 v15; // r15
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdi
  _QWORD *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r15
  _QWORD *v23; // rbp
  _BYTE v24[32]; // [rsp+0h] [rbp-E8h] BYREF
  char v25; // [rsp+37h] [rbp-B1h]
  __int64 v26; // [rsp+38h] [rbp-B0h]
  int v27; // [rsp+40h] [rbp-A8h]
  __int64 v28; // [rsp+48h] [rbp-A0h]
  int v29; // [rsp+50h] [rbp-98h]
  unsigned __int64 v30; // [rsp+58h] [rbp-90h] BYREF
  __int128 v31; // [rsp+60h] [rbp-88h]
  __int64 v32; // [rsp+70h] [rbp-78h] BYREF
  __int64 v33; // [rsp+78h] [rbp-70h]
  __int64 v34; // [rsp+80h] [rbp-68h]
  _BYTE v35[24]; // [rsp+88h] [rbp-60h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-48h]

  v6 = Win32AllocPool_0(80, 1668572487);
  if ( !v6 )
  {
    *(_QWORD *)a1 = 0xE00000001LL;
    goto LABEL_13;
  }
  v7 = v6;
  *(_QWORD *)v6 = 0x8000000000000000uLL;
  *(_BYTE *)(v6 + 56) = 2;
  *(_OWORD *)(v6 + 64) = (unsigned __int64)_xmm;
  v8 = ((unsigned __int64)a2 + 255) >> 8;
  v32 = 0;
  v33 = 8;
  v34 = 0;
  if ( !v8 )
  {
    v31 = 8u;
    v26 = 0;
    v27 = 0;
    v9 = 8;
    v10 = 0;
    goto LABEL_4;
  }
  v10 = 4;
  if ( v8 >= 5 )
    v10 = ((unsigned __int64)a2 + 255) >> 8;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm746c6547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182(
    (unsigned int)v35,
    (unsigned int)&v32,
    v10,
    8,
    24);
  if ( *(_DWORD *)v35 == 1 )
  {
    v9 = 14;
  }
  else
  {
    v25 = a3;
    v30 = v10;
    v31 = *(unsigned __int64 *)&v35[8];
    v15 = 0;
    do
    {
      if ( v10 == v15 )
      {
        v10 = 2 * v15;
        if ( (unsigned __int64)(2 * v15) < 5 )
          v10 = 4;
        RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm746c6547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182(
          (unsigned int)v35,
          (unsigned int)&v30,
          v10,
          8,
          24);
        if ( v35[0] )
          goto LABEL_58;
        v16 = *(_QWORD *)&v35[8];
        *(_QWORD *)&v31 = *(_QWORD *)&v35[8];
        v30 = v10;
      }
      else
      {
        v16 = v31;
      }
      v17 = 3 * v15;
      *(_QWORD *)(v16 + 8 * v17) = 0;
      *(_QWORD *)(v16 + 8 * v17 + 8) = 8;
      *(_QWORD *)(v16 + 8 * v17 + 16) = 0;
      v15 = ++*((_QWORD *)&v31 + 1);
      --v8;
    }
    while ( v8 );
    v9 = v31;
    v28 = *(_QWORD *)((char *)&v31 + 4);
    v29 = HIDWORD(v31);
    a3 = v25;
    if ( v10 != 0x8000000000000000uLL )
    {
      v21 = *(_QWORD *)v7;
      v27 = v29;
      v26 = v28;
      if ( v21 != 0x8000000000000000uLL )
      {
        v22 = *(_QWORD *)(v7 + 16);
        if ( v22 )
        {
          v23 = (_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL);
          do
          {
            if ( *(v23 - 1) )
              Win32FreePool_0(*v23);
            v23 += 3;
            --v22;
          }
          while ( v22 );
          v21 = *(_QWORD *)v7;
        }
        a3 = v25;
        if ( v21 )
          Win32FreePool_0(*(_QWORD *)(v7 + 8));
      }
LABEL_4:
      *(_QWORD *)v7 = v10;
      *(_DWORD *)(v7 + 8) = v9;
      *(_QWORD *)(v7 + 12) = v26;
      *(_DWORD *)(v7 + 20) = v27;
      *(_QWORD *)(v7 + 24) = a2;
      if ( !a3 )
      {
LABEL_11:
        *(_DWORD *)(v7 + 76) = a2;
        *(_QWORD *)(a1 + 8) = v7;
        *(_DWORD *)a1 = 0;
        goto LABEL_13;
      }
      v32 = 0;
      v33 = 8;
      v34 = 0;
      if ( !a2 )
      {
        v11 = 8;
        v12 = 0;
        v13 = *(_BYTE *)(v7 + 56);
        if ( v13 != 2 )
          goto LABEL_7;
        goto LABEL_10;
      }
      v12 = 4;
      if ( a2 >= 5uLL )
        v12 = a2;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182(
        (unsigned int)v35,
        (unsigned int)&v32,
        v12,
        8,
        24);
      if ( !v35[0] )
      {
        v33 = *(_QWORD *)&v35[8];
        memset(*(void **)&v35[8], 0, 24LL * a2);
        v11 = v33;
        v13 = *(_BYTE *)(v7 + 56);
        if ( v13 != 2 )
        {
LABEL_7:
          if ( v13 == 1 )
          {
            if ( *(_QWORD *)(v7 + 48) )
              Win32FreePool_0(*(_QWORD *)(v7 + 32));
          }
        }
LABEL_10:
        *(_QWORD *)(v7 + 32) = v11;
        *(_QWORD *)(v7 + 40) = a2;
        *(_QWORD *)(v7 + 48) = v12;
        *(_BYTE *)(v7 + 56) = 1;
        goto LABEL_11;
      }
      *(_QWORD *)a1 = 0xE00000001LL;
      v18 = *(_QWORD *)v7;
      if ( *(_QWORD *)v7 == 0x8000000000000000uLL )
        goto LABEL_43;
      goto LABEL_35;
    }
  }
  *(_DWORD *)(a1 + 4) = v9;
  *(_DWORD *)a1 = 1;
  v18 = *(_QWORD *)v7;
  if ( *(_QWORD *)v7 != 0x8000000000000000uLL )
  {
LABEL_35:
    v19 = *(_QWORD *)(v7 + 16);
    if ( v19 )
    {
      v20 = (_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL);
      do
      {
        if ( *(v20 - 1) )
          Win32FreePool_0(*v20);
        v20 += 3;
        --v19;
      }
      while ( v19 );
      v18 = *(_QWORD *)v7;
    }
    if ( v18 )
      Win32FreePool_0(*(_QWORD *)(v7 + 8));
  }
LABEL_43:
  if ( *(_BYTE *)(v7 + 56) == 1 && *(_QWORD *)(v7 + 48) )
    Win32FreePool_0(*(_QWORD *)(v7 + 32));
  Win32FreePool_0(v7);
LABEL_13:
  result = (unsigned __int64)v24 ^ v36;
  if ( _security_cookie != ((unsigned __int64)v24 ^ v36) )
  {
LABEL_58:
    *(_OWORD *)v35 = *(_OWORD *)&v35[8];
    RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
      (unsigned int)&anon_74322c9add977dfab17ab4536cfbe633_13_llvm_14523797218057561932,
      43,
      (unsigned int)v35,
      (unsigned int)&anon_74322c9add977dfab17ab4536cfbe633_12_llvm_14523797218057561932,
      (__int64)&off_14001C270);
  }
  return result;
}

```

## disassembly

```asm
0x140013e50  push    r15
0x140013e52  push    r14
0x140013e54  push    r13
0x140013e56  push    r12
0x140013e58  push    rsi
0x140013e59  push    rdi
0x140013e5a  push    rbp
0x140013e5b  push    rbx
0x140013e5c  sub     rsp, 0A8h
0x140013e63  mov     r15d, r8d
0x140013e66  mov     ebx, edx
0x140013e68  mov     rdi, rcx
0x140013e6b  mov     rax, cs:__security_cookie
0x140013e72  xor     rax, rsp
0x140013e75  mov     [rsp+0E8h+var_48], rax
0x140013e7d  mov     ecx, 50h ; 'P'
0x140013e82  mov     edx, 63746547h
0x140013e87  call    Win32AllocPool_0
0x140013e8c  test    rax, rax
0x140013e8f  jz      loc_140013F9E
0x140013e95  mov     rsi, rax
0x140013e98  mov     rbp, 8000000000000000h
0x140013ea2  mov     [rax], rbp
0x140013ea5  mov     byte ptr [rax+38h], 2
0x140013ea9  movsd   xmm0, cs:__xmm@0000000000000000ffffffff00000000
0x140013eb1  movups  xmmword ptr [rax+40h], xmm0
0x140013eb5  mov     r13d, ebx
0x140013eb8  lea     r12, [r13+0FFh]
0x140013ebf  shr     r12, 8
0x140013ec3  mov     [rsp+0E8h+var_78], 0
0x140013ecc  mov     [rsp+0E8h+var_70], 8
0x140013ed5  mov     [rsp+0E8h+var_68], 0
0x140013ee1  jnz     loc_140013FDA
0x140013ee7  mov     [rsp+0E8h+var_88], 8
0x140013ef0  mov     [rsp+0E8h+var_80], 0
0x140013ef9  mov     eax, dword ptr [rsp+0E8h+var_80+4]
0x140013efd  mov     rcx, [rsp+0E8h+var_88+4]
0x140013f02  mov     [rsp+0E8h+var_B0], rcx
0x140013f07  mov     [rsp+0E8h+var_A8], eax
0x140013f0b  mov     r12d, 8
0x140013f11  xor     r14d, r14d
0x140013f14  mov     [rsi], r14
0x140013f17  mov     [rsi+8], r12d
0x140013f1b  mov     rax, [rsp+0E8h+var_B0]
0x140013f20  mov     [rsi+0Ch], rax
0x140013f24  mov     eax, [rsp+0E8h+var_A8]
0x140013f28  mov     [rsi+14h], eax
0x140013f2b  mov     [rsi+18h], r13
0x140013f2f  test    r15b, r15b
0x140013f32  jz      short loc_140013F8F
0x140013f34  mov     [rsp+0E8h+var_78], 0
0x140013f3d  mov     [rsp+0E8h+var_70], 8
0x140013f46  mov     [rsp+0E8h+var_68], 0
0x140013f52  test    ebx, ebx
0x140013f54  jnz     loc_140014123
0x140013f5a  mov     r15d, 8
0x140013f60  xor     r14d, r14d
0x140013f63  movzx   eax, byte ptr [rsi+38h]
0x140013f67  cmp     al, 2
0x140013f69  jz      short loc_140013F7F
0x140013f6b  cmp     al, 1
0x140013f6d  jnz     short loc_140013F7F
0x140013f6f  cmp     qword ptr [rsi+30h], 0
0x140013f74  jz      short loc_140013F7F
0x140013f76  mov     rcx, [rsi+20h]
0x140013f7a  call    Win32FreePool_0
0x140013f7f  mov     [rsi+20h], r15
0x140013f83  mov     [rsi+28h], r13
0x140013f87  mov     [rsi+30h], r14
0x140013f8b  mov     byte ptr [rsi+38h], 1
0x140013f8f  mov     [rsi+4Ch], ebx
0x140013f92  mov     [rdi+8], rsi
0x140013f96  mov     dword ptr [rdi], 0
0x140013f9c  jmp     short loc_140013FAB
0x140013f9e  mov     rax, 0E00000001h
0x140013fa8  mov     [rdi], rax
0x140013fab  mov     rax, [rsp+0E8h+var_48]
0x140013fb3  xor     rax, rsp
0x140013fb6  mov     rcx, cs:__security_cookie
0x140013fbd  cmp     rcx, rax
0x140013fc0  jnz     loc_140014290
0x140013fc6  add     rsp, 0A8h
0x140013fcd  pop     rbx
0x140013fce  pop     rbp
0x140013fcf  pop     rdi
0x140013fd0  pop     rsi
0x140013fd1  pop     r12
0x140013fd3  pop     r13
0x140013fd5  pop     r14
0x140013fd7  pop     r15
0x140013fd9  retn
0x140013fda  cmp     r12, 5
0x140013fde  mov     r14d, 4
0x140013fe4  cmovnb  r14, r12
0x140013fe8  mov     [rsp+0E8h+var_C8], 18h
0x140013ff1  lea     rcx, [rsp+0E8h+var_60]
0x140013ff9  lea     rdx, [rsp+0E8h+var_78]
0x140013ffe  mov     r9d, 8
0x140014004  mov     r8, r14
0x140014007  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm746c6547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182
0x14001400c  cmp     dword ptr [rsp+0E8h+var_60], 1
0x140014014  jnz     short loc_140014021
0x140014016  mov     r12d, 0Eh
0x14001401c  jmp     loc_14001410C
0x140014021  mov     [rsp+0E8h+var_B1], r15b
0x140014026  mov     rax, qword ptr [rsp+0E8h+var_60+8]
0x14001402e  mov     [rsp+0E8h+var_90], r14
0x140014033  mov     [rsp+0E8h+var_88], rax
0x140014038  mov     [rsp+0E8h+var_80], 0
0x140014041  xor     r15d, r15d
0x140014044  nop     word ptr [rax+rax+00000000h]
0x140014050  cmp     r14, r15
0x140014053  jz      short loc_14001408C
0x140014055  mov     rax, [rsp+0E8h+var_88]
0x14001405a  lea     rcx, [r15+r15*2]
0x14001405e  mov     qword ptr [rax+rcx*8], 0
0x140014066  mov     qword ptr [rax+rcx*8+8], 8
0x14001406f  mov     qword ptr [rax+rcx*8+10h], 0
0x140014078  mov     r15, [rsp+0E8h+var_80]
0x14001407d  inc     r15
0x140014080  mov     [rsp+0E8h+var_80], r15
0x140014085  dec     r12
0x140014088  jnz     short loc_140014050
0x14001408a  jmp     short loc_1400140E6
0x14001408c  lea     r14, [r15+r15]
0x140014090  cmp     r14, 5
0x140014094  mov     eax, 4
0x140014099  cmovb   r14, rax
0x14001409d  mov     [rsp+0E8h+var_C8], 18h
0x1400140a6  mov     r9d, 8
0x1400140ac  lea     rcx, [rsp+0E8h+var_60]
0x1400140b4  lea     rdx, [rsp+0E8h+var_90]
0x1400140b9  mov     r8, r14
0x1400140bc  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm746c6547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182
0x1400140c1  cmp     [rsp+0E8h+var_60], 0
0x1400140c9  jnz     loc_1400142A0
0x1400140cf  mov     rax, qword ptr [rsp+0E8h+var_60+8]
0x1400140d7  mov     [rsp+0E8h+var_88], rax
0x1400140dc  mov     [rsp+0E8h+var_90], r14
0x1400140e1  jmp     loc_14001405A
0x1400140e6  mov     r12d, dword ptr [rsp+0E8h+var_88]
0x1400140eb  mov     rax, [rsp+0E8h+var_88+4]
0x1400140f0  mov     [rsp+0E8h+var_A0], rax
0x1400140f5  mov     eax, dword ptr [rsp+0E8h+var_80+4]
0x1400140f9  mov     [rsp+0E8h+var_98], eax
0x1400140fd  cmp     r14, rbp
0x140014100  movzx   r15d, [rsp+0E8h+var_B1]
0x140014106  jnz     loc_1400141E4
0x14001410c  mov     [rdi+4], r12d
0x140014110  mov     dword ptr [rdi], 1
0x140014116  mov     rax, [rsi]
0x140014119  cmp     rax, rbp
0x14001411c  jnz     short loc_140014178
0x14001411e  jmp     loc_1400141BB
0x140014123  cmp     r13, 5
0x140014127  mov     r14d, 4
0x14001412d  cmovnb  r14, r13
0x140014131  mov     [rsp+0E8h+var_C8], 18h
0x14001413a  lea     rcx, [rsp+0E8h+var_60]
0x140014142  lea     rdx, [rsp+0E8h+var_78]
0x140014147  mov     r9d, 8
0x14001414d  mov     r8, r14
0x140014150  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182
0x140014155  cmp     [rsp+0E8h+var_60], 0
0x14001415d  jz      loc_140014230
0x140014163  mov     rax, 0E00000001h
0x14001416d  mov     [rdi], rax
0x140014170  mov     rax, [rsi]
0x140014173  cmp     rax, rbp
0x140014176  jz      short loc_1400141BB
0x140014178  mov     rdi, [rsi+10h]
0x14001417c  test    rdi, rdi
0x14001417f  jz      short loc_1400141AD
0x140014181  mov     rbx, [rsi+8]
0x140014185  add     rbx, 8
0x140014189  jmp     short loc_140014199
0x140014190  add     rbx, 18h
0x140014194  dec     rdi
0x140014197  jz      short loc_1400141AA
0x140014199  cmp     qword ptr [rbx-8], 0
0x14001419e  jz      short loc_140014190
0x1400141a0  mov     rcx, [rbx]
0x1400141a3  call    Win32FreePool_0
0x1400141a8  jmp     short loc_140014190
0x1400141aa  mov     rax, [rsi]
0x1400141ad  test    rax, rax
0x1400141b0  jz      short loc_1400141BB
0x1400141b2  mov     rcx, [rsi+8]
0x1400141b6  call    Win32FreePool_0
0x1400141bb  movzx   eax, byte ptr [rsi+38h]
0x1400141bf  cmp     al, 2
0x1400141c1  jz      short loc_1400141D7
0x1400141c3  cmp     al, 1
0x1400141c5  jnz     short loc_1400141D7
0x1400141c7  cmp     qword ptr [rsi+30h], 0
0x1400141cc  jz      short loc_1400141D7
0x1400141ce  mov     rcx, [rsi+20h]
0x1400141d2  call    Win32FreePool_0
0x1400141d7  mov     rcx, rsi
0x1400141da  call    Win32FreePool_0
0x1400141df  jmp     loc_140013FAB
0x1400141e4  mov     rax, [rsi]
0x1400141e7  mov     ecx, [rsp+0E8h+var_98]
0x1400141eb  mov     [rsp+0E8h+var_A8], ecx
0x1400141ef  mov     rcx, [rsp+0E8h+var_A0]
0x1400141f4  mov     [rsp+0E8h+var_B0], rcx
0x1400141f9  cmp     rax, rbp
0x1400141fc  jz      loc_140013F14
0x140014202  mov     r15, [rsi+10h]
0x140014206  test    r15, r15
0x140014209  jz      short loc_140014273
0x14001420b  mov     rbp, [rsi+8]
0x14001420f  add     rbp, 8
0x140014213  jmp     short loc_14001421E
0x140014215  add     rbp, 18h
0x140014219  dec     r15
0x14001421c  jz      short loc_140014266
0x14001421e  cmp     qword ptr [rbp-8], 0
0x140014223  jz      short loc_140014215
0x140014225  mov     rcx, [rbp+0]
0x140014229  call    Win32FreePool_0
0x14001422e  jmp     short loc_140014215
0x140014230  mov     rcx, qword ptr [rsp+0E8h+var_60+8]; void *
0x140014238  mov     [rsp+0E8h+var_70], rcx
0x14001423d  lea     rax, ds:0[r13*8]
0x140014245  lea     r8, [rax+rax*2]; Size
0x140014249  xor     edx, edx; Val
0x14001424b  call    memset
0x140014250  mov     r15, [rsp+0E8h+var_70]
0x140014255  movzx   eax, byte ptr [rsi+38h]
0x140014259  cmp     al, 2
0x14001425b  jnz     loc_140013F6B
0x140014261  jmp     loc_140013F7F
0x140014266  mov     rax, [rsi]
0x140014269  mov     rbp, 8000000000000000h
0x140014273  test    rax, rax
0x140014276  movzx   r15d, [rsp+0E8h+var_B1]
0x14001427c  jz      loc_140013F14
0x140014282  mov     rcx, [rsi+8]
0x140014286  call    Win32FreePool_0
0x14001428b  jmp     loc_140013F14
0x140014290  mov     rcx, [rsp+0E8h+var_48]
0x140014298  xor     rcx, rsp; StackCookie
0x14001429b  call    __security_check_cookie
0x1400142a0  movups  xmm0, xmmword ptr [rsp+0E8h+var_60+8]
0x1400142a8  movups  xmmword ptr [rsp+0E8h+var_60], xmm0
0x1400142b0  lea     rax, off_14001C270; "handle_manager\\src\\GdiHandleEntryTabl"...
0x1400142b7  mov     [rsp+0E8h+var_C8], rax
0x1400142bc  lea     rcx, anon_74322c9add977dfab17ab4536cfbe633_13_llvm_14523797218057561932
0x1400142c3  lea     r9, anon_74322c9add977dfab17ab4536cfbe633_12_llvm_14523797218057561932
0x1400142ca  lea     r8, [rsp+0E8h+var_60]
0x1400142d2  mov     edx, 2Bh ; '+'
0x1400142d7  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
```
