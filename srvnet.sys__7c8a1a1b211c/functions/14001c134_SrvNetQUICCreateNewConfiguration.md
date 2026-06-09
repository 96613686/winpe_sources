# SrvNetQUICCreateNewConfiguration

- ea: `0x14001c134`
- end: `0x14001c585`
- name: `SrvNetQUICCreateNewConfiguration`
- size: `1105`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140048ca8`
- `0x140049db0`

## callees

- `0x14001389c`
- `0x140013950`
- `0x140015790`
- `0x1400174ac`
- `0x14001c134`
- `0x14001e5b0`
- `0x14001e74c`
- `0x14001e7a8`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14001c266`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14001c266`

## pseudocode

```c
__int64 __fastcall SrvNetQUICCreateNewConfiguration(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v4; // r15
  int v6; // r8d
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 v12; // r11
  size_t v13; // r8
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  int v21; // eax
  int v22; // r8d
  int v23; // r8d
  size_t pcchLength; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v26[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h]
  _DWORD v28[40]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v29[18]; // [rsp+120h] [rbp+20h] BYREF

  v4 = a2;
  pcchLength = 0;
  memset(&v28[1], 0, 0x94u);
  v28[0] = 1;
  memset(v29, 0, sizeof(v29));
  HIWORD(v29[11]) = 1;
  BYTE2(v29[13]) = 0;
  memset(v26, 0, sizeof(v26));
  v27 = 0;
  v29[3] = 0;
  v29[0] = 17039364;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_ds(WPP_GLOBAL_Control->AttachedDevice, 66, v6, *(_DWORD *)(a1 + 136), a1 + 8);
  }
  if ( *(_DWORD *)(a1 + 136) + 140 != (_DWORD)v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids);
    }
    return (unsigned int)-1073741811;
  }
  v8 = RtlRunOnceExecuteOnce(&SrvNetQUICInitOnce, (PRTL_RUN_ONCE_INIT_FN)SrvNetQUICRunOnceInitialize, 0, 0);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return v7;
    }
    v10 = 68;
    goto LABEL_16;
  }
  v11 = a1 + 140;
  v8 = RtlStringCchLengthA((STRSAFE_PCNZCH)(a1 + 140), v4 - 140, &pcchLength);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return v7;
    }
    v10 = 69;
LABEL_16:
    WPP_SF_d(v9->AttachedDevice, v10, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids, (unsigned int)v8);
    return v7;
  }
  v13 = v12 - 140 - pcchLength - 1;
  if ( v13 >= 0x14 )
  {
    v14 = *(_OWORD *)(a1 + 24);
    *(_OWORD *)&v28[6] = *(_OWORD *)(a1 + 8);
    v15 = *(_OWORD *)(a1 + 40);
    *(_OWORD *)&v28[10] = v14;
    v16 = *(_OWORD *)(a1 + 56);
    *(_OWORD *)&v28[14] = v15;
    v17 = *(_OWORD *)(a1 + 72);
    *(_OWORD *)&v28[18] = v16;
    v18 = *(_OWORD *)(a1 + 88);
    *(_OWORD *)&v28[22] = v17;
    v19 = *(_OWORD *)(a1 + 104);
    *(_OWORD *)&v28[26] = v18;
    v20 = *(_OWORD *)(a1 + 120);
    *(_OWORD *)&v28[30] = v19;
    *(_OWORD *)&v28[34] = v20;
    *(_OWORD *)&v28[1] = *(_OWORD *)(v11 + pcchLength + 1);
    v28[5] = *(_DWORD *)(v11 + pcchLength + 17);
    if ( SMBQuicRegistration )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD *, int, _QWORD, _QWORD *))(MsQuic + 64))(
              SMBQuicRegistration,
              &qword_14002F110,
              1,
              v29,
              144,
              0,
              a3);
      v7 = v21;
      if ( v21 >= 0 )
      {
        LODWORD(v26[0]) = 2;
        *((_QWORD *)&v26[0] + 1) = v28;
        if ( (*(_DWORD *)a1 & 4) != 0 )
        {
          DWORD1(v26[0]) = 1136;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids, v11);
          }
        }
        v7 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(MsQuic + 80))(*a3, v26);
        if ( (v7 & 0x80000000) != 0 )
        {
          (*(void (__fastcall **)(_QWORD))(MsQuic + 72))(*a3);
          *a3 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_sd(WPP_GLOBAL_Control->AttachedDevice, 74, v23, v11, v7);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
             && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_sd(WPP_GLOBAL_Control->AttachedDevice, 72, v22, v11, v21);
      }
    }
    else
    {
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids);
      }
    }
  }
  else
  {
    v7 = -1073741789;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qi(WPP_GLOBAL_Control->AttachedDevice, 70, v13, v11, v13);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14001c134  mov     [rsp-8+arg_18], rbx
0x14001c139  push    rbp
0x14001c13a  push    rsi
0x14001c13b  push    rdi
0x14001c13c  push    r12
0x14001c13e  push    r13
0x14001c140  push    r14
0x14001c142  push    r15
0x14001c144  lea     rbp, [rsp-0C0h]
0x14001c14c  sub     rsp, 1C0h
0x14001c153  mov     rax, cs:__security_cookie
0x14001c15a  xor     rax, rsp
0x14001c15d  mov     [rbp+0F0h+var_40], rax
0x14001c164  mov     r14, r8
0x14001c167  mov     r15d, edx
0x14001c16a  mov     rdi, rcx
0x14001c16d  xor     ebx, ebx
0x14001c16f  xor     edx, edx; Val
0x14001c171  mov     [rsp+1F0h+pcchLength], rbx
0x14001c176  mov     r8d, 94h; Size
0x14001c17c  lea     rcx, [rbp+0F0h+var_16C]; void *
0x14001c180  call    memset
0x14001c185  lea     r13d, [rbx+1]
0x14001c189  xor     edx, edx; Val
0x14001c18b  mov     r8d, 90h; Size
0x14001c191  mov     [rbp+0F0h+var_170], r13d
0x14001c195  lea     rcx, [rbp+0F0h+var_D0]; void *
0x14001c199  call    memset
0x14001c19e  xorps   xmm0, xmm0
0x14001c1a1  mov     [rbp+0F0h+var_72], r13w
0x14001c1a6  xor     eax, eax
0x14001c1a8  mov     [rbp+0F0h+var_66], bl
0x14001c1ae  movups  [rsp+1F0h+var_1A8], xmm0
0x14001c1b3  mov     [rsp+1F0h+var_178], rax
0x14001c1b8  movups  [rsp+1F0h+var_198], xmm0
0x14001c1bd  mov     [rbp+0F0h+var_B8], rbx
0x14001c1c1  movups  [rsp+1F0h+var_188], xmm0
0x14001c1c6  mov     [rbp+0F0h+var_D0], 1040004h
0x14001c1ce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c1d5  lea     rsi, WPP_GLOBAL_Control
0x14001c1dc  cmp     rcx, rsi
0x14001c1df  jz      short loc_14001C20A
0x14001c1e1  bt      dword ptr [rcx+2Ch], 15h
0x14001c1e6  jnb     short loc_14001C20A
0x14001c1e8  cmp     byte ptr [rcx+29h], 2
0x14001c1ec  jb      short loc_14001C20A
0x14001c1ee  mov     r9d, [rdi+88h]
0x14001c1f5  lea     rax, [rdi+8]
0x14001c1f9  mov     rcx, [rcx+18h]
0x14001c1fd  lea     edx, [rbx+42h]
0x14001c200  mov     [rsp+1F0h+var_1D0], rax
0x14001c205  call    WPP_SF_ds
0x14001c20a  mov     eax, [rdi+88h]
0x14001c210  add     eax, 8Ch
0x14001c215  cmp     eax, r15d
0x14001c218  jz      short loc_14001C252
0x14001c21a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c221  cmp     rcx, rsi
0x14001c224  jz      short loc_14001C248
0x14001c226  bt      dword ptr [rcx+2Ch], 15h
0x14001c22b  jnb     short loc_14001C248
0x14001c22d  cmp     [rcx+29h], r13b
0x14001c231  jb      short loc_14001C248
0x14001c233  mov     rcx, [rcx+18h]
0x14001c237  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14001c23e  mov     edx, 43h ; 'C'
0x14001c243  call    WPP_SF_
0x14001c248  mov     ebx, 0C000000Dh
0x14001c24d  jmp     loc_14001C558
0x14001c252  xor     r9d, r9d; Context
0x14001c255  lea     rdx, SrvNetQUICRunOnceInitialize; InitFn
0x14001c25c  xor     r8d, r8d; Parameter
0x14001c25f  lea     rcx, SrvNetQUICInitOnce; RunOnce
0x14001c266  call    cs:__imp_RtlRunOnceExecuteOnce
0x14001c26d  nop     dword ptr [rax+rax+00h]
0x14001c272  mov     ebx, eax
0x14001c274  test    eax, eax
0x14001c276  jns     short loc_14001C2BA
0x14001c278  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c27f  cmp     rcx, rsi
0x14001c282  jz      loc_14001C558
0x14001c288  bt      dword ptr [rcx+2Ch], 15h
0x14001c28d  jnb     loc_14001C558
0x14001c293  cmp     [rcx+29h], r13b
0x14001c297  jb      loc_14001C558
0x14001c29d  mov     edx, 44h ; 'D'
0x14001c2a2  mov     rcx, [rcx+18h]
0x14001c2a6  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14001c2ad  mov     r9d, eax
0x14001c2b0  call    WPP_SF_d
0x14001c2b5  jmp     loc_14001C558
0x14001c2ba  lea     rsi, [rdi+8Ch]
0x14001c2c1  mov     rdx, r15
0x14001c2c4  sub     rdx, rsi
0x14001c2c7  lea     r8, [rsp+1F0h+pcchLength]; pcchLength
0x14001c2cc  add     rdx, rdi; cchMax
0x14001c2cf  mov     rcx, rsi; psz
0x14001c2d2  mov     r11, r15
0x14001c2d5  call    RtlStringCchLengthA
0x14001c2da  mov     ebx, eax
0x14001c2dc  test    eax, eax
0x14001c2de  jns     short loc_14001C313
0x14001c2e0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c2e7  lea     rdi, WPP_GLOBAL_Control
0x14001c2ee  cmp     rcx, rdi
0x14001c2f1  jz      loc_14001C558
0x14001c2f7  bt      dword ptr [rcx+2Ch], 15h
0x14001c2fc  jnb     loc_14001C558
0x14001c302  cmp     [rcx+29h], r13b
0x14001c306  jb      loc_14001C558
0x14001c30c  mov     edx, 45h ; 'E'
0x14001c311  jmp     short loc_14001C2A2
0x14001c313  mov     rax, [rsp+1F0h+pcchLength]
0x14001c318  lea     r8, [rdi-1]
0x14001c31c  sub     r11, rsi
0x14001c31f  sub     r11, rax
0x14001c322  add     r8, r11
0x14001c325  cmp     r8, 14h
0x14001c329  jnb     short loc_14001C377
0x14001c32b  mov     ebx, 0C0000023h
0x14001c330  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c337  lea     rdi, WPP_GLOBAL_Control
0x14001c33e  cmp     rcx, rdi
0x14001c341  jz      loc_14001C558
0x14001c347  bt      dword ptr [rcx+2Ch], 15h
0x14001c34c  jnb     loc_14001C558
0x14001c352  cmp     [rcx+29h], r13b
0x14001c356  jb      loc_14001C558
0x14001c35c  mov     rcx, [rcx+18h]
0x14001c360  mov     edx, 46h ; 'F'
0x14001c365  mov     r9, rsi
0x14001c368  mov     [rsp+1F0h+var_1D0], r8
0x14001c36d  call    WPP_SF_qi
0x14001c372  jmp     loc_14001C558
0x14001c377  movups  xmm0, xmmword ptr [rdi+8]
0x14001c37b  mov     rcx, cs:SMBQuicRegistration
0x14001c382  movups  xmm1, xmmword ptr [rdi+18h]
0x14001c386  movups  [rbp+0F0h+var_158], xmm0
0x14001c38a  movups  xmm0, xmmword ptr [rdi+28h]
0x14001c38e  movups  [rbp+0F0h+var_148], xmm1
0x14001c392  movups  xmm1, xmmword ptr [rdi+38h]
0x14001c396  movups  [rbp+0F0h+var_138], xmm0
0x14001c39a  movups  xmm0, xmmword ptr [rdi+48h]
0x14001c39e  movups  [rbp+0F0h+var_128], xmm1
0x14001c3a2  movups  xmm1, xmmword ptr [rdi+58h]
0x14001c3a6  movups  [rbp+0F0h+var_118], xmm0
0x14001c3aa  movups  xmm0, xmmword ptr [rdi+68h]
0x14001c3ae  movups  [rbp+0F0h+var_108], xmm1
0x14001c3b2  movups  xmm1, xmmword ptr [rdi+78h]
0x14001c3b6  movups  [rbp+0F0h+var_F8], xmm0
0x14001c3ba  movups  [rbp+0F0h+var_E8], xmm1
0x14001c3be  movups  xmm0, xmmword ptr [rsi+rax+1]
0x14001c3c3  movups  [rbp+0F0h+var_16C], xmm0
0x14001c3c7  mov     eax, [rsi+rax+11h]
0x14001c3cb  mov     [rbp+0F0h+var_15C], eax
0x14001c3ce  test    rcx, rcx
0x14001c3d1  jnz     short loc_14001C41E
0x14001c3d3  mov     ebx, 0C000009Ah
0x14001c3d8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c3df  lea     rdi, WPP_GLOBAL_Control
0x14001c3e6  cmp     rcx, rdi
0x14001c3e9  jz      loc_14001C558
0x14001c3ef  bt      dword ptr [rcx+2Ch], 15h
0x14001c3f4  jnb     loc_14001C558
0x14001c3fa  cmp     [rcx+29h], r13b
0x14001c3fe  jb      loc_14001C558
0x14001c404  mov     rcx, [rcx+18h]
0x14001c408  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14001c40f  mov     edx, 47h ; 'G'
0x14001c414  call    WPP_SF_
0x14001c419  jmp     loc_14001C558
0x14001c41e  mov     rax, cs:MsQuic
0x14001c425  lea     r9, [rbp+0F0h+var_D0]
0x14001c429  mov     [rsp+1F0h+var_1C0], r14
0x14001c42e  lea     rdx, qword_14002F110
0x14001c435  mov     [rsp+1F0h+var_1C8], 0
0x14001c43e  mov     r8d, r13d
0x14001c441  mov     dword ptr [rsp+1F0h+var_1D0], 90h
0x14001c449  mov     rax, [rax+40h]
0x14001c44d  call    _guard_dispatch_icall
0x14001c452  mov     ebx, eax
0x14001c454  test    eax, eax
0x14001c456  jns     short loc_14001C492
0x14001c458  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c45f  lea     rdi, WPP_GLOBAL_Control
0x14001c466  cmp     rcx, rdi
0x14001c469  jz      loc_14001C558
0x14001c46f  bt      dword ptr [rcx+2Ch], 15h
0x14001c474  jnb     loc_14001C558
0x14001c47a  cmp     [rcx+29h], r13b
0x14001c47e  jb      loc_14001C558
0x14001c484  mov     edx, 48h ; 'H'
0x14001c489  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x14001c48d  jmp     loc_14001C54C
0x14001c492  lea     rax, [rbp+0F0h+var_170]
0x14001c496  mov     dword ptr [rsp+1F0h+var_1A8], 2
0x14001c49e  mov     qword ptr [rsp+1F0h+var_1A8+8], rax
0x14001c4a3  mov     eax, [rdi]
0x14001c4a5  test    al, 4
0x14001c4a7  jz      short loc_14001C4EB
0x14001c4a9  mov     dword ptr [rsp+1F0h+var_1A8+4], 470h
0x14001c4b1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c4b8  lea     rdi, WPP_GLOBAL_Control
0x14001c4bf  cmp     rcx, rdi
0x14001c4c2  jz      short loc_14001C4F2
0x14001c4c4  bt      dword ptr [rcx+2Ch], 15h
0x14001c4c9  jnb     short loc_14001C4F2
0x14001c4cb  cmp     byte ptr [rcx+29h], 2
0x14001c4cf  jb      short loc_14001C4F2
0x14001c4d1  mov     rcx, [rcx+18h]
0x14001c4d5  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14001c4dc  mov     edx, 49h ; 'I'
0x14001c4e1  mov     r9, rsi
0x14001c4e4  call    WPP_SF_s
0x14001c4e9  jmp     short loc_14001C4F2
0x14001c4eb  lea     rdi, WPP_GLOBAL_Control
0x14001c4f2  mov     rax, cs:MsQuic
0x14001c4f9  lea     rdx, [rsp+1F0h+var_1A8]
0x14001c4fe  mov     rcx, [r14]
0x14001c501  mov     rax, [rax+50h]
0x14001c505  call    _guard_dispatch_icall
0x14001c50a  mov     ebx, eax
0x14001c50c  test    eax, eax
0x14001c50e  jns     short loc_14001C558
0x14001c510  mov     rax, cs:MsQuic
0x14001c517  mov     rcx, [r14]
0x14001c51a  mov     rax, [rax+48h]
0x14001c51e  call    _guard_dispatch_icall
0x14001c523  mov     qword ptr [r14], 0
0x14001c52a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c531  cmp     rcx, rdi
0x14001c534  jz      short loc_14001C558
0x14001c536  bt      dword ptr [rcx+2Ch], 15h
0x14001c53b  jnb     short loc_14001C558
0x14001c53d  cmp     [rcx+29h], r13b
0x14001c541  jb      short loc_14001C558
0x14001c543  mov     edx, 4Ah ; 'J'
0x14001c548  mov     dword ptr [rsp+1F0h+var_1D0], ebx
0x14001c54c  mov     rcx, [rcx+18h]
0x14001c550  mov     r9, rsi
0x14001c553  call    WPP_SF_sd
0x14001c558  mov     eax, ebx
0x14001c55a  mov     rcx, [rbp+0F0h+var_40]
0x14001c561  xor     rcx, rsp; StackCookie
0x14001c564  call    __security_check_cookie
0x14001c569  mov     rbx, [rsp+1F0h+arg_18]
0x14001c571  add     rsp, 1C0h
0x14001c578  pop     r15
0x14001c57a  pop     r14
0x14001c57c  pop     r13
0x14001c57e  pop     r12
0x14001c580  pop     rdi
0x14001c581  pop     rsi
0x14001c582  pop     rbp
0x14001c583  retn
```
