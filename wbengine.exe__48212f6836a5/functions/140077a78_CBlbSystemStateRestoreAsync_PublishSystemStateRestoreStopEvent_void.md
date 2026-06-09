# CBlbSystemStateRestoreAsync::PublishSystemStateRestoreStopEvent(void)

- ea: `0x140077a78`
- end: `0x140078028`
- name: `?PublishSystemStateRestoreStopEvent@CBlbSystemStateRestoreAsync@@AEAAJXZ`
- size: `1456`
- prototype: `__int64 __fastcall(CBlbSystemStateRestoreAsync *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x140075000`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bfd8`
- `0x140077a78`
- `0x140083000`
- `0x140083264`
- `0x1400889f0`
- `0x1400d24d8`
- `0x1400d7c08`
- `0x1400d7cc8`
- `0x1400d7d88`
- `0x1400d8000`
- `0x1400d88d4`
- `0x140101b64`
- `0x140101c50`
- `0x140113d68`
- `0x140134d20`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x140077b99`
- `ole32!CoTaskMemAlloc` at `0x140077bcd`
- `ole32!CoTaskMemAlloc` at `0x140077bf5`
- `ole32!CoTaskMemAlloc` at `0x140077c1d`
- `ole32!CoTaskMemAlloc` at `0x140077c49`
- `ole32!CoTaskMemAlloc` at `0x140077c75`
- `ole32!CoTaskMemAlloc` at `0x140077ca1`
- `ole32!CoTaskMemAlloc` at `0x140077ccd`
- `ole32!CoTaskMemAlloc` at `0x140077b99`
- `ole32!CoTaskMemAlloc` at `0x140077bcd`
- `ole32!CoTaskMemAlloc` at `0x140077bf5`
- `ole32!CoTaskMemAlloc` at `0x140077c1d`
- `ole32!CoTaskMemAlloc` at `0x140077c49`
- `ole32!CoTaskMemAlloc` at `0x140077c75`
- `ole32!CoTaskMemAlloc` at `0x140077ca1`
- `ole32!CoTaskMemAlloc` at `0x140077ccd`

## string_xrefs

- `0x140077d37`: `base\stor\blb\engine\service\systemstaterestore.cpp`

## pseudocode

```c
__int64 __fastcall CBlbSystemStateRestoreAsync::PublishSystemStateRestoreStopEvent(CBlbSystemStateRestoreAsync *this)
{
  __int64 v2; // r8
  unsigned int v3; // edx
  __int128 v4; // xmm0
  int v5; // r10d
  __int64 v6; // rcx
  __int64 v7; // r9
  __int64 v8; // rax
  char *v9; // rax
  int VolumeFriendlyNameForPublisher; // ebx
  unsigned __int16 **v11; // rax
  int *v12; // rax
  unsigned int *v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 *v16; // rax
  void *v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // edi
  unsigned int j; // esi
  __int64 v21; // rbx
  unsigned int v22; // r12d
  CBlbApplicationContext **v23; // rax
  const unsigned __int16 *v24; // rcx
  const unsigned __int16 *v25; // rcx
  const unsigned __int16 *v26; // rcx
  int v27; // eax
  unsigned int v28; // ebx
  CBlbApplicationContext **v29; // rax
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+4Ch] [rbp-B4h]
  int v34; // [rsp+50h] [rbp-B0h]
  int v35; // [rsp+54h] [rbp-ACh]
  __int128 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  unsigned int i; // [rsp+70h] [rbp-90h]
  char *v39; // [rsp+78h] [rbp-88h]
  unsigned int v40; // [rsp+80h] [rbp-80h]
  unsigned __int16 **v41; // [rsp+88h] [rbp-78h]
  int *v42; // [rsp+90h] [rbp-70h]
  unsigned int *v43; // [rsp+98h] [rbp-68h]
  __int64 *v44; // [rsp+A0h] [rbp-60h]
  __int64 *v45; // [rsp+A8h] [rbp-58h]
  __int64 *v46; // [rsp+B0h] [rbp-50h]
  __int64 *v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  __int64 v49; // [rsp+C8h] [rbp-38h]
  __int64 v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  __int64 v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+E8h] [rbp-18h]
  __int64 v54; // [rsp+F0h] [rbp-10h]
  __int64 v55; // [rsp+F8h] [rbp-8h]
  __int64 v56; // [rsp+100h] [rbp+0h]
  __int64 v57; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v58; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v59; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 *v60; // [rsp+120h] [rbp+20h] BYREF
  char v61[8]; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 *v62; // [rsp+130h] [rbp+30h] BYREF

  memset_0(&v31, 0, 0xF8u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  memset_0(&v36, 0, 0xE0u);
  v2 = *((_QWORD *)this + 71);
  v3 = 0;
  v4 = *((_OWORD *)this + 16);
  v5 = *((_DWORD *)this + 117);
  v31 = *(_QWORD *)((char *)this + 404);
  v32 = *((_DWORD *)this + 2);
  v33 = *((_DWORD *)this + 3);
  v35 = *((_DWORD *)this + 116);
  v34 = v5;
  v36 = v4;
  v37 = *(_QWORD *)(v2 + 100);
  v6 = 0;
  v40 = *((_DWORD *)this + 88);
  for ( i = 0; v3 < *(_DWORD *)(v2 + 64); ++v3 )
  {
    v7 = 120LL * v3;
    v8 = *(_QWORD *)(v2 + 72);
    if ( *(_BYTE *)(v7 + v8 + 41) || v5 == 4 && (*(_BYTE *)(v7 + v8 + 16) & 0x20) != 0 )
    {
      v6 = (unsigned int)(v6 + 1);
      i = v6;
    }
  }
  v9 = (char *)CoTaskMemAlloc(8 * v6);
  v39 = v9;
  if ( !v9 )
    goto LABEL_12;
  memset_0(v9, 0, 8LL * i);
  v11 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v40);
  v41 = v11;
  if ( !v11 )
    goto LABEL_12;
  memset_0(v11, 0, 8LL * v40);
  v12 = (int *)CoTaskMemAlloc(4LL * v40);
  v42 = v12;
  if ( !v12 )
    goto LABEL_12;
  memset_0(v12, 0, 4LL * v40);
  v13 = (unsigned int *)CoTaskMemAlloc(4LL * v40);
  v43 = v13;
  if ( !v13 )
    goto LABEL_12;
  memset_0(v13, 0, 4LL * v40);
  v14 = (__int64 *)CoTaskMemAlloc(8LL * v40);
  v46 = v14;
  if ( !v14 )
    goto LABEL_12;
  memset_0(v14, 0, 8LL * v40);
  v15 = (__int64 *)CoTaskMemAlloc(8LL * v40);
  v47 = v15;
  if ( !v15 )
    goto LABEL_12;
  memset_0(v15, 0, 8LL * v40);
  v16 = (__int64 *)CoTaskMemAlloc(8LL * v40);
  v45 = v16;
  if ( v16 && (memset_0(v16, 0, 8LL * v40), v17 = CoTaskMemAlloc(8LL * v40), (v44 = (__int64 *)v17) != 0) )
  {
    memset_0(v17, 0, 8LL * v40);
    v18 = *((_QWORD *)this + 71);
    if ( *(_DWORD *)(v18 + 64) )
    {
      v19 = 0;
      for ( j = 0; j < *(_DWORD *)(v18 + 64); ++j )
      {
        v21 = *(_QWORD *)(v18 + 72) + 120LL * j;
        if ( *(_BYTE *)(v21 + 41) || *((_DWORD *)this + 117) == 4 && (*(_BYTE *)(v21 + 16) & 0x20) != 0 )
        {
          if ( v19 >= i )
            BlbAssert(
              "base\\stor\\blb\\engine\\service\\systemstaterestore.cpp",
              0x565u,
              "eventVol < eventInfo.cVolume");
          VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                             v21,
                                             *(unsigned int *)(v21 + 16),
                                             2,
                                             &v39[8 * v19]);
          if ( VolumeFriendlyNameForPublisher < 0 )
            goto LABEL_55;
          ++v19;
        }
        v18 = *((_QWORD *)this + 71);
      }
    }
    v22 = 0;
    if ( *((_DWORD *)this + 88) )
    {
      while ( 1 )
      {
        v23 = (CBlbApplicationContext **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                           (_QWORD *)this + 40,
                                           v22);
        VolumeFriendlyNameForPublisher = CBlbApplicationContext::GetInfo(
                                           *v23,
                                           &v41[v22],
                                           &v42[v22],
                                           &v43[v22],
                                           &v45[v22],
                                           &v44[v22],
                                           &v46[v22],
                                           &v47[v22]);
        if ( VolumeFriendlyNameForPublisher < 0 )
          break;
        if ( ++v22 >= *((_DWORD *)this + 88) )
          goto LABEL_33;
      }
    }
    else
    {
LABEL_33:
      v24 = &String1;
      if ( *((_QWORD *)this + 36) )
        v24 = (const unsigned __int16 *)*((_QWORD *)this + 36);
      VolumeFriendlyNameForPublisher = BlbutilDuplicateString(v24, &v58, 0);
      if ( VolumeFriendlyNameForPublisher >= 0 )
      {
        v25 = &String1;
        if ( *((_QWORD *)this + 37) )
          v25 = (const unsigned __int16 *)*((_QWORD *)this + 37);
        VolumeFriendlyNameForPublisher = BlbutilDuplicateString(v25, &v59, 0);
        if ( VolumeFriendlyNameForPublisher >= 0 )
        {
          VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                             *((_QWORD *)this + 53),
                                             *((unsigned int *)this + 108),
                                             v61);
          if ( VolumeFriendlyNameForPublisher >= 0 )
          {
            v26 = &String1;
            if ( *((_QWORD *)this + 56) )
              v26 = (const unsigned __int16 *)*((_QWORD *)this + 56);
            VolumeFriendlyNameForPublisher = BlbutilDuplicateString(v26, &v62, 0);
            if ( VolumeFriendlyNameForPublisher >= 0 )
            {
              VolumeFriendlyNameForPublisher = BlbutilDuplicateString(&String1, &v60, 0);
              if ( VolumeFriendlyNameForPublisher >= 0 )
              {
                v48 = *((_QWORD *)this + 30);
                v49 = *((_QWORD *)this + 31);
                v50 = *((_QWORD *)this + 29);
                v51 = *((_QWORD *)this + 28);
                v52 = *((_QWORD *)this + 59);
                v53 = *((_QWORD *)this + 60);
                v54 = *((_QWORD *)this + 47);
                v55 = *((_QWORD *)this + 48);
                v56 = *((_QWORD *)this + 61);
                v57 = *((_QWORD *)this + 62);
                v27 = *((_DWORD *)this + 2);
                if ( v27 < 0 )
                {
                  if ( v27 == -2139619299 || v27 == -2139618969 )
                  {
                    PublishSystemStateRestoreCanceledEvent((struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)&v31);
                  }
                  else
                  {
                    v28 = 0;
                    if ( *((_DWORD *)this + 88) )
                    {
                      while ( 1 )
                      {
                        v29 = (CBlbApplicationContext **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                                           (_QWORD *)this + 40,
                                                           v28);
                        if ( CBlbApplicationContext::IsApplicationRestoreCompleted(*v29) )
                          break;
                        if ( ++v28 >= *((_DWORD *)this + 88) )
                          goto LABEL_51;
                      }
                      PublishSystemStateRestorePartialSuccessEvent((struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)&v31);
                    }
                    else
                    {
LABEL_51:
                      PublishSystemStateRestoreGenericFailureEvent((struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)&v31);
                    }
                  }
                }
                else
                {
                  PublishSystemStateRestoreSuccessEvent((struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)&v31);
                }
                PublishSystemStateRestoreStopEvent((struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)&v31);
                VolumeFriendlyNameForPublisher = PublishRecoverySqmDatapoint(
                                                   (CBlbSystemStateRestoreAsync *)((char *)this + 504),
                                                   *((_DWORD *)this + 2),
                                                   *((_DWORD *)this + 3));
              }
            }
          }
        }
      }
    }
  }
  else
  {
LABEL_12:
    VolumeFriendlyNameForPublisher = -2147024882;
  }
LABEL_55:
  FreeSystemStateRestoreStopEventInfo((struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *const)&v31);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  return (unsigned int)VolumeFriendlyNameForPublisher;
}

```

## disassembly

```asm
0x140077a78  push    rbp
0x140077a7a  push    rbx
0x140077a7b  push    rsi
0x140077a7c  push    rdi
0x140077a7d  push    r12
0x140077a7f  push    r13
0x140077a81  push    r14
0x140077a83  push    r15
0x140077a85  lea     rbp, [rsp-58h]
0x140077a8a  sub     rsp, 158h
0x140077a91  mov     rax, cs:__security_cookie
0x140077a98  xor     rax, rsp
0x140077a9b  mov     [rbp+90h+var_50], rax
0x140077a9f  mov     r15, rcx
0x140077aa2  xor     edx, edx; Val
0x140077aa4  lea     rcx, [rsp+190h+var_150]; void *
0x140077aa9  mov     r8d, 0F8h; Size
0x140077aaf  call    memset_0
0x140077ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x140077abb  lea     rax, WPP_GLOBAL_Control
0x140077ac2  cmp     rcx, rax
0x140077ac5  jz      short loc_140077AE8
0x140077ac7  test    byte ptr [rcx+1Ch], 1
0x140077acb  jz      short loc_140077AE8
0x140077acd  cmp     byte ptr [rcx+19h], 4
0x140077ad1  jb      short loc_140077AE8
0x140077ad3  mov     rcx, [rcx+10h]
0x140077ad7  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x140077ade  mov     edx, 29h ; ')'
0x140077ae3  call    WPP_SF_
0x140077ae8  xor     edx, edx; Val
0x140077aea  lea     rcx, [rsp+190h+var_138]; void *
0x140077aef  mov     r8d, 0E0h; Size
0x140077af5  call    memset_0
0x140077afa  mov     rax, [r15+194h]
0x140077b01  xor     r14d, r14d
0x140077b04  mov     r8, [r15+238h]
0x140077b0b  mov     edx, r14d
0x140077b0e  movups  xmm0, xmmword ptr [r15+100h]
0x140077b16  mov     r10d, [r15+1D4h]
0x140077b1d  mov     [rsp+190h+var_150], rax
0x140077b22  mov     eax, [r15+8]
0x140077b26  mov     [rsp+190h+var_148], eax
0x140077b2a  mov     eax, [r15+0Ch]
0x140077b2e  mov     [rsp+190h+var_144], eax
0x140077b32  mov     eax, [r15+1D0h]
0x140077b39  mov     [rsp+190h+var_13C], eax
0x140077b3d  mov     [rsp+190h+var_140], r10d
0x140077b42  movdqu  [rsp+190h+var_138], xmm0
0x140077b48  mov     rax, [r8+64h]
0x140077b4c  mov     [rsp+190h+var_128], rax
0x140077b51  mov     eax, [r15+160h]
0x140077b58  mov     ecx, r14d
0x140077b5b  mov     [rbp+90h+var_110], eax
0x140077b5e  mov     [rsp+190h+var_120], ecx
0x140077b62  cmp     [r8+40h], r14d
0x140077b66  jbe     short loc_140077B95
0x140077b68  mov     eax, edx
0x140077b6a  imul    r9, rax, 78h ; 'x'
0x140077b6e  mov     rax, [r8+48h]
0x140077b72  cmp     [r9+rax+29h], r14b
0x140077b77  jnz     short loc_140077B87
0x140077b79  cmp     r10d, 4
0x140077b7d  jnz     short loc_140077B8D
0x140077b7f  test    byte ptr [r9+rax+10h], 20h
0x140077b85  jz      short loc_140077B8D
0x140077b87  inc     ecx
0x140077b89  mov     [rsp+190h+var_120], ecx
0x140077b8d  inc     edx
0x140077b8f  cmp     edx, [r8+40h]
0x140077b93  jb      short loc_140077B68
0x140077b95  shl     rcx, 3; cb
0x140077b99  call    cs:__imp_CoTaskMemAlloc
0x140077b9f  mov     [rsp+190h+var_118], rax
0x140077ba4  test    rax, rax
0x140077ba7  jnz     short loc_140077BB3
0x140077ba9  mov     ebx, 8007000Eh
0x140077bae  jmp     loc_140077FC8
0x140077bb3  mov     r8d, [rsp+190h+var_120]
0x140077bb8  xor     edx, edx; Val
0x140077bba  shl     r8, 3; Size
0x140077bbe  mov     rcx, rax; void *
0x140077bc1  call    memset_0
0x140077bc6  mov     ecx, [rbp+90h+var_110]
0x140077bc9  shl     rcx, 3; cb
0x140077bcd  call    cs:__imp_CoTaskMemAlloc
0x140077bd3  mov     [rbp+90h+var_108], rax
0x140077bd7  test    rax, rax
0x140077bda  jz      short loc_140077BA9
0x140077bdc  mov     r8d, [rbp+90h+var_110]
0x140077be0  xor     edx, edx; Val
0x140077be2  shl     r8, 3; Size
0x140077be6  mov     rcx, rax; void *
0x140077be9  call    memset_0
0x140077bee  mov     ecx, [rbp+90h+var_110]
0x140077bf1  shl     rcx, 2; cb
0x140077bf5  call    cs:__imp_CoTaskMemAlloc
0x140077bfb  mov     [rbp+90h+var_100], rax
0x140077bff  test    rax, rax
0x140077c02  jz      short loc_140077BA9
0x140077c04  mov     r8d, [rbp+90h+var_110]
0x140077c08  xor     edx, edx; Val
0x140077c0a  shl     r8, 2; Size
0x140077c0e  mov     rcx, rax; void *
0x140077c11  call    memset_0
0x140077c16  mov     ecx, [rbp+90h+var_110]
0x140077c19  shl     rcx, 2; cb
0x140077c1d  call    cs:__imp_CoTaskMemAlloc
0x140077c23  mov     [rbp+90h+var_F8], rax
0x140077c27  test    rax, rax
0x140077c2a  jz      loc_140077BA9
0x140077c30  mov     r8d, [rbp+90h+var_110]
0x140077c34  xor     edx, edx; Val
0x140077c36  shl     r8, 2; Size
0x140077c3a  mov     rcx, rax; void *
0x140077c3d  call    memset_0
0x140077c42  mov     ecx, [rbp+90h+var_110]
0x140077c45  shl     rcx, 3; cb
0x140077c49  call    cs:__imp_CoTaskMemAlloc
0x140077c4f  mov     [rbp+90h+var_E0], rax
0x140077c53  test    rax, rax
0x140077c56  jz      loc_140077BA9
0x140077c5c  mov     r8d, [rbp+90h+var_110]
0x140077c60  xor     edx, edx; Val
0x140077c62  shl     r8, 3; Size
0x140077c66  mov     rcx, rax; void *
0x140077c69  call    memset_0
0x140077c6e  mov     ecx, [rbp+90h+var_110]
0x140077c71  shl     rcx, 3; cb
0x140077c75  call    cs:__imp_CoTaskMemAlloc
0x140077c7b  mov     [rbp+90h+var_D8], rax
0x140077c7f  test    rax, rax
0x140077c82  jz      loc_140077BA9
0x140077c88  mov     r8d, [rbp+90h+var_110]
0x140077c8c  xor     edx, edx; Val
0x140077c8e  shl     r8, 3; Size
0x140077c92  mov     rcx, rax; void *
0x140077c95  call    memset_0
0x140077c9a  mov     ecx, [rbp+90h+var_110]
0x140077c9d  shl     rcx, 3; cb
0x140077ca1  call    cs:__imp_CoTaskMemAlloc
0x140077ca7  mov     [rbp+90h+var_E8], rax
0x140077cab  test    rax, rax
0x140077cae  jz      loc_140077BA9
0x140077cb4  mov     r8d, [rbp+90h+var_110]
0x140077cb8  xor     edx, edx; Val
0x140077cba  shl     r8, 3; Size
0x140077cbe  mov     rcx, rax; void *
0x140077cc1  call    memset_0
0x140077cc6  mov     ecx, [rbp+90h+var_110]
0x140077cc9  shl     rcx, 3; cb
0x140077ccd  call    cs:__imp_CoTaskMemAlloc
0x140077cd3  mov     [rbp+90h+var_F0], rax
0x140077cd7  test    rax, rax
0x140077cda  jz      loc_140077BA9
0x140077ce0  mov     r8d, [rbp+90h+var_110]
0x140077ce4  xor     edx, edx; Val
0x140077ce6  shl     r8, 3; Size
0x140077cea  mov     rcx, rax; void *
0x140077ced  call    memset_0
0x140077cf2  mov     rdx, [r15+238h]
0x140077cf9  cmp     [rdx+40h], r14d
0x140077cfd  jbe     short loc_140077D79
0x140077cff  mov     edi, r14d
0x140077d02  mov     esi, r14d
0x140077d05  mov     eax, esi
0x140077d07  imul    rbx, rax, 78h ; 'x'
0x140077d0b  add     rbx, [rdx+48h]
0x140077d0f  cmp     [rbx+29h], r14b
0x140077d13  jnz     short loc_140077D25
0x140077d15  cmp     dword ptr [r15+1D4h], 4
0x140077d1d  jnz     short loc_140077D6B
0x140077d1f  test    byte ptr [rbx+10h], 20h
0x140077d23  jz      short loc_140077D6B
0x140077d25  cmp     edi, [rsp+190h+var_120]
0x140077d29  jb      short loc_140077D43
0x140077d2b  lea     r8, aEventvolEventi; "eventVol < eventInfo.cVolume"
0x140077d32  mov     edx, 565h; unsigned int
0x140077d37  lea     rcx, aBaseStorBlbEng_41; "base\\stor\\blb\\engine\\service\\syste"...
0x140077d3e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140077d43  mov     rax, [rsp+190h+var_118]
0x140077d48  mov     r8d, 2
0x140077d4e  mov     edx, edi
0x140077d50  mov     rcx, rbx
0x140077d53  lea     r9, [rax+rdx*8]
0x140077d57  mov     edx, [rbx+10h]
0x140077d5a  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAU_GUID@@KW4_BLB_MEDIA_TYPE@@PEAPEAG@Z; GetVolumeFriendlyNameForPublisher(_GUID *,ulong,_BLB_MEDIA_TYPE,ushort * *)
0x140077d5f  mov     ebx, eax
0x140077d61  test    eax, eax
0x140077d63  js      loc_140077FC8
0x140077d69  inc     edi
0x140077d6b  mov     rdx, [r15+238h]
0x140077d72  inc     esi
0x140077d74  cmp     esi, [rdx+40h]
0x140077d77  jb      short loc_140077D05
0x140077d79  mov     r12d, r14d
0x140077d7c  cmp     [r15+160h], r14d
0x140077d83  jbe     loc_140077E0F
0x140077d89  mov     edx, r12d
0x140077d8c  lea     rcx, [r15+140h]
0x140077d93  mov     esi, r12d
0x140077d96  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140077d9b  mov     rcx, [rbp+90h+var_D8]
0x140077d9f  mov     r14, rax
0x140077da2  mov     rax, [rbp+90h+var_108]
0x140077da6  lea     rdi, [rcx+rsi*8]
0x140077daa  mov     rcx, [rbp+90h+var_E0]
0x140077dae  mov     [rsp+190h+var_158], rdi; __int64 *
0x140077db3  lea     rdx, [rax+rsi*8]; unsigned __int16 **
0x140077db7  lea     rbx, [rcx+rsi*8]
0x140077dbb  mov     rcx, [rbp+90h+var_F0]
0x140077dbf  mov     [rsp+190h+var_160], rbx; __int64 *
0x140077dc4  lea     r11, [rcx+rsi*8]
0x140077dc8  mov     rcx, [rbp+90h+var_E8]
0x140077dcc  mov     [rsp+190h+var_168], r11; __int64 *
0x140077dd1  lea     r10, [rcx+rsi*8]
0x140077dd5  mov     rcx, [rbp+90h+var_F8]
0x140077dd9  mov     [rsp+190h+var_170], r10; __int64 *
0x140077dde  lea     r9, [rcx+rsi*4]; unsigned int *
0x140077de2  mov     rcx, [rbp+90h+var_100]
0x140077de6  lea     r8, [rcx+rsi*4]; int *
0x140077dea  mov     rcx, [r14]; this
0x140077ded  call    ?GetInfo@CBlbApplicationContext@@QEAAJPEAPEAGPEAJPEAKPEA_J333@Z; CBlbApplicationContext::GetInfo(ushort * *,long *,ulong *,__int64 *,__int64 *,__int64 *,__int64 *)
0x140077df2  xor     r14d, r14d
0x140077df5  mov     ebx, eax
0x140077df7  test    eax, eax
0x140077df9  js      loc_140077FC8
0x140077dff  inc     r12d
0x140077e02  cmp     r12d, [r15+160h]
0x140077e09  jb      loc_140077D89
0x140077e0f  mov     rax, [r15+120h]
0x140077e16  lea     rdi, String1
0x140077e1d  test    rax, rax
0x140077e20  lea     rdx, [rbp+90h+var_80]; unsigned __int16 **
0x140077e24  mov     rcx, rdi
0x140077e27  cmovnz  rcx, rax; unsigned __int16 *
0x140077e2b  xor     r8d, r8d; unsigned __int64
0x140077e2e  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140077e33  mov     ebx, eax
0x140077e35  test    eax, eax
0x140077e37  js      loc_140077FC8
0x140077e3d  mov     rax, [r15+128h]
0x140077e44  lea     rdx, [rbp+90h+var_78]; unsigned __int16 **
0x140077e48  test    rax, rax
0x140077e4b  mov     rcx, rdi
0x140077e4e  cmovnz  rcx, rax; unsigned __int16 *
0x140077e52  xor     r8d, r8d; unsigned __int64
0x140077e55  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140077e5a  mov     ebx, eax
0x140077e5c  test    eax, eax
0x140077e5e  js      loc_140077FC8
0x140077e64  mov     edx, [r15+1B0h]
0x140077e6b  lea     r8, [rbp+90h+var_68]
0x140077e6f  mov     rcx, [r15+1A8h]
0x140077e76  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAGW4_BLB_MEDIA_TYPE@@AEAPEAG@Z; GetVolumeFriendlyNameForPublisher(ushort *,_BLB_MEDIA_TYPE,ushort * &)
0x140077e7b  mov     ebx, eax
0x140077e7d  test    eax, eax
0x140077e7f  js      loc_140077FC8
0x140077e85  mov     rax, [r15+1C0h]
0x140077e8c  lea     rdx, [rbp+90h+var_60]; unsigned __int16 **
0x140077e90  test    rax, rax
0x140077e93  mov     rcx, rdi
0x140077e96  cmovnz  rcx, rax; unsigned __int16 *
0x140077e9a  xor     r8d, r8d; unsigned __int64
0x140077e9d  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140077ea2  mov     ebx, eax
0x140077ea4  test    eax, eax
0x140077ea6  js      loc_140077FC8
0x140077eac  xor     r8d, r8d; unsigned __int64
0x140077eaf  lea     rdx, [rbp+90h+var_70]; unsigned __int16 **
0x140077eb3  mov     rcx, rdi; unsigned __int16 *
0x140077eb6  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140077ebb  mov     ebx, eax
0x140077ebd  test    eax, eax
0x140077ebf  js      loc_140077FC8
0x140077ec5  mov     rax, [r15+0F0h]
0x140077ecc  mov     [rbp+90h+var_D0], rax
0x140077ed0  mov     rax, [r15+0F8h]
0x140077ed7  mov     [rbp+90h+var_C8], rax
0x140077edb  mov     rax, [r15+0E8h]
0x140077ee2  mov     [rbp+90h+var_C0], rax
0x140077ee6  mov     rax, [r15+0E0h]
0x140077eed  mov     [rbp+90h+var_B8], rax
0x140077ef1  mov     rax, [r15+1D8h]
0x140077ef8  mov     [rbp+90h+var_B0], rax
0x140077efc  mov     rax, [r15+1E0h]
0x140077f03  mov     [rbp+90h+var_A8], rax
0x140077f07  mov     rax, [r15+178h]
0x140077f0e  mov     [rbp+90h+var_A0], rax
0x140077f12  mov     rax, [r15+180h]
0x140077f19  mov     [rbp+90h+var_98], rax
0x140077f1d  mov     rax, [r15+1E8h]
0x140077f24  mov     [rbp+90h+var_90], rax
0x140077f28  mov     rax, [r15+1F0h]
0x140077f2f  mov     [rbp+90h+var_88], rax
0x140077f33  mov     eax, [r15+8]
0x140077f37  test    eax, eax
0x140077f39  js      short loc_140077F47
0x140077f3b  lea     rcx, [rsp+190h+var_150]; struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *
0x140077f40  call    ?PublishSystemStateRestoreSuccessEvent@@YAJPEAU_BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO@@@Z; PublishSystemStateRestoreSuccessEvent(_BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)
  ... truncated ...
```
