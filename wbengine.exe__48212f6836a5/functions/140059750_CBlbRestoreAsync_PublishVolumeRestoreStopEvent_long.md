# CBlbRestoreAsync::PublishVolumeRestoreStopEvent(long)

- ea: `0x140059750`
- end: `0x140059e67`
- name: `?PublishVolumeRestoreStopEvent@CBlbRestoreAsync@@QEAAJJ@Z`
- size: `1815`
- prototype: `__int64 __fastcall(CBlbRestoreAsync *__hidden this, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task`

## callers

- `0x1400563a0`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x140057a4c`
- `0x140057de0`
- `0x140059750`
- `0x1400d7590`
- `0x1400d8994`
- `0x1400d8a5c`
- `0x1400d8b30`
- `0x1400d8c0c`
- `0x1400d916c`
- `0x140101b64`
- `0x140101c50`
- `0x140113d68`
- `0x140134d20`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x140059866`
- `ole32!CoTaskMemAlloc` at `0x140059898`
- `ole32!CoTaskMemAlloc` at `0x1400598c0`
- `ole32!CoTaskMemAlloc` at `0x1400598e8`
- `ole32!CoTaskMemAlloc` at `0x140059914`
- `ole32!CoTaskMemAlloc` at `0x140059940`
- `ole32!CoTaskMemAlloc` at `0x14005996c`
- `ole32!CoTaskMemAlloc` at `0x140059866`
- `ole32!CoTaskMemAlloc` at `0x140059898`
- `ole32!CoTaskMemAlloc` at `0x1400598c0`
- `ole32!CoTaskMemAlloc` at `0x1400598e8`
- `ole32!CoTaskMemAlloc` at `0x140059914`
- `ole32!CoTaskMemAlloc` at `0x140059940`
- `ole32!CoTaskMemAlloc` at `0x14005996c`
- `ole32!CoTaskMemFree` at `0x140059c39`
- `ole32!CoTaskMemFree` at `0x140059c4c`
- `ole32!CoTaskMemFree` at `0x140059df6`
- `ole32!CoTaskMemFree` at `0x140059e01`
- `ole32!CoTaskMemFree` at `0x140059c39`
- `ole32!CoTaskMemFree` at `0x140059c4c`
- `ole32!CoTaskMemFree` at `0x140059df6`
- `ole32!CoTaskMemFree` at `0x140059e01`
- `RPCRT4!UuidCreate` at `0x1400597f4`
- `RPCRT4!UuidCreate` at `0x1400597f4`

## string_xrefs

- `0x140059d7a`: `base\stor\blb\engine\service\restore.cpp`
- `0x140059da6`: `base\stor\blb\engine\service\restore.cpp`

## pseudocode

```c
__int64 __fastcall CBlbRestoreAsync::PublishVolumeRestoreStopEvent(CBlbRestoreAsync *this, int a2)
{
  void *v3; // r12
  __int128 v4; // xmm0
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  int VolumeFriendlyNameForPublisher; // ebx
  char *v9; // rax
  char *v10; // rax
  _DWORD *v11; // rax
  _DWORD *v12; // rax
  _DWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // r13
  _QWORD *v17; // rsi
  __int64 v18; // r14
  __int64 v19; // r15
  unsigned int v20; // ecx
  __int64 v21; // r14
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // ebx
  __int64 v25; // r14
  unsigned int v26; // edx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v29; // [rsp+28h] [rbp-D8h] BYREF
  int v30; // [rsp+30h] [rbp-D0h]
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  UUID v33; // [rsp+58h] [rbp-A8h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  int v36; // [rsp+70h] [rbp-90h]
  char v37[8]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v38; // [rsp+80h] [rbp-80h]
  char *v39; // [rsp+88h] [rbp-78h]
  char *v40; // [rsp+90h] [rbp-70h]
  _DWORD *v41; // [rsp+98h] [rbp-68h]
  void *v42; // [rsp+A0h] [rbp-60h] BYREF
  void *v43; // [rsp+A8h] [rbp-58h] BYREF
  void *v44; // [rsp+B0h] [rbp-50h] BYREF
  void *v45; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v46; // [rsp+C0h] [rbp-40h]
  _DWORD *v47; // [rsp+C8h] [rbp-38h]
  _QWORD *v48; // [rsp+D0h] [rbp-30h]
  _QWORD *v49; // [rsp+D8h] [rbp-28h]
  void *v50; // [rsp+E0h] [rbp-20h] BYREF
  void *v51[2]; // [rsp+E8h] [rbp-18h] BYREF
  int v52; // [rsp+F8h] [rbp-8h]
  int v53; // [rsp+FCh] [rbp-4h]
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF

  v30 = a2;
  memset_0(&v31, 0, 0xC0u);
  v3 = 0;
  v29 = 0;
  pv = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  memset_0(&v31, 0, 0xC0u);
  Uuid = GUID_NULL;
  UuidCreate(&Uuid);
  v4 = *((_OWORD *)this + 13);
  v5 = *((unsigned int *)this + 81);
  v6 = *((_QWORD *)this + 29);
  v32 = *(_QWORD *)((char *)this + 316);
  v34 = *((_DWORD *)this + 69);
  v35 = *((_DWORD *)this + 4);
  v7 = *((_DWORD *)this + 5);
  v31 = v4;
  v36 = v7;
  v38 = *((_DWORD *)this + 83);
  v33 = Uuid;
  VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(v6, v5, v37);
  if ( VolumeFriendlyNameForPublisher >= 0 )
  {
    v9 = (char *)CoTaskMemAlloc(8LL * v38);
    v39 = v9;
    if ( !v9 )
      goto LABEL_7;
    memset_0(v9, 0, 8LL * v38);
    v10 = (char *)CoTaskMemAlloc(8LL * v38);
    v40 = v10;
    if ( !v10 )
      goto LABEL_7;
    memset_0(v10, 0, 8LL * v38);
    v11 = CoTaskMemAlloc(4LL * v38);
    v41 = v11;
    if ( !v11 )
      goto LABEL_7;
    memset_0(v11, 0, 4LL * v38);
    v12 = CoTaskMemAlloc(4LL * v38);
    v46 = v12;
    if ( !v12 )
      goto LABEL_7;
    memset_0(v12, 0, 4LL * v38);
    v13 = CoTaskMemAlloc(4LL * v38);
    v47 = v13;
    if ( !v13
      || (memset_0(v13, 0, 4LL * v38), v14 = CoTaskMemAlloc(8LL * v38), (v48 = v14) == 0)
      || (memset_0(v14, 0, 8LL * v38), v15 = CoTaskMemAlloc(8LL * v38), (v49 = v15) == 0) )
    {
LABEL_7:
      VolumeFriendlyNameForPublisher = -2147024882;
      goto LABEL_65;
    }
    memset_0(v15, 0, 8LL * v38);
    VolumeFriendlyNameForPublisher = BlbutilMemalloc(&v43, v38, 4u);
    if ( VolumeFriendlyNameForPublisher >= 0 )
    {
      VolumeFriendlyNameForPublisher = BlbutilMemalloc(&v42, v38, 4u);
      if ( VolumeFriendlyNameForPublisher >= 0 )
      {
        VolumeFriendlyNameForPublisher = BlbutilMemalloc(&v44, v38, 4u);
        if ( VolumeFriendlyNameForPublisher >= 0 )
        {
          VolumeFriendlyNameForPublisher = BlbutilMemalloc(&v45, v38, 4u);
          if ( VolumeFriendlyNameForPublisher >= 0 )
          {
            VolumeFriendlyNameForPublisher = BlbutilMemalloc(&v50, v38, 8u);
            if ( VolumeFriendlyNameForPublisher >= 0 )
            {
              VolumeFriendlyNameForPublisher = BlbutilMemalloc(v51, v38, 8u);
              if ( VolumeFriendlyNameForPublisher >= 0 )
              {
                v16 = 0;
                v17 = (_QWORD *)((char *)this + 264);
                while ( (unsigned int)v16 < v38 )
                {
                  v17 = (_QWORD *)((char *)this + 264);
                  v18 = 192 * v16;
                  VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                                     192 * v16 + *((_QWORD *)this + 33) + 60LL,
                                                     *(unsigned int *)(192 * v16 + *((_QWORD *)this + 33) + 76),
                                                     2,
                                                     &v39[8 * v16]);
                  if ( VolumeFriendlyNameForPublisher < 0 )
                    goto LABEL_65;
                  VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                                     v18 + *v17 + 80LL,
                                                     *(unsigned int *)(v18 + *v17 + 96),
                                                     2,
                                                     &v40[8 * v16]);
                  if ( VolumeFriendlyNameForPublisher < 0 )
                    goto LABEL_65;
                  v41[v16] = *(_DWORD *)(v18 + *v17 + 24);
                  v46[v16] = *(_DWORD *)(v18 + *v17 + 28);
                  v47[v16] = *(_DWORD *)(v18 + *v17 + 20);
                  v48[v16] = *(_QWORD *)(v18 + *v17 + 8);
                  v49[v16] = *(_QWORD *)(v18 + *v17);
                  *((_DWORD *)v43 + v16) = *(_DWORD *)(v18 + *v17 + 56);
                  *((_DWORD *)v42 + v16) = *(_DWORD *)(v18 + *v17 + 32);
                  *((_DWORD *)v44 + v16) = *(_DWORD *)(v18 + *v17 + 156);
                  *((_DWORD *)v45 + v16) = *(_DWORD *)(v18 + *v17 + 160);
                  *((_QWORD *)v50 + v16) = *(_QWORD *)(v18 + *v17 + 40);
                  *((_QWORD *)v51[0] + v16) = *(_QWORD *)(v18 + *v17 + 48);
                  v16 = (unsigned int)(v16 + 1);
                }
                v19 = 0;
                while ( 1 )
                {
                  v20 = *((_DWORD *)this + 83);
                  if ( (unsigned int)v19 >= v20 )
                    break;
                  v21 = 192 * v19;
                  if ( *(_DWORD *)(192 * v19 + *v17 + 24) == -2139619048 )
                  {
                    VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                                       v21 + *v17 + 80LL,
                                                       *(unsigned int *)(v21 + *v17 + 96),
                                                       2,
                                                       &v29);
                    if ( VolumeFriendlyNameForPublisher < 0 )
                      goto LABEL_65;
                    VolumeFriendlyNameForPublisher = CBlbVolumeRestoreContext::GetRestoreTargetPath(
                                                       (CBlbVolumeRestoreContext *)(v21 + *v17),
                                                       (unsigned __int16 **)&pv);
                    if ( VolumeFriendlyNameForPublisher < 0 )
                    {
                      v3 = pv;
                      goto LABEL_65;
                    }
                    if ( (int)PublishRestoreVolumeTooSmallEvent(
                                v29,
                                (unsigned __int16 *)pv,
                                *(struct _FILETIME *)((char *)this + 356)) < 0
                      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        120,
                        &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
                    }
                    CoTaskMemFree(pv);
                    v3 = 0;
                    pv = 0;
                    CoTaskMemFree(v29);
                    v29 = 0;
                  }
                  v19 = (unsigned int)(v19 + 1);
                  v17 = (_QWORD *)((char *)this + 264);
                }
                v51[1] = *(void **)((char *)this + 356);
                v52 = *((_DWORD *)this + 91);
                v53 = *((_DWORD *)this + 92);
                if ( v30 >= 0 )
                {
                  v24 = 0;
                  v25 = 0;
                  if ( !v20 )
                    goto LABEL_59;
                  do
                  {
                    if ( *(_DWORD *)(192 * v25 + *v17 + 20) == 8 )
                    {
                      ++v24;
                    }
                    else if ( *(_DWORD *)(192 * v25 + *v17 + 20) != 9 )
                    {
                      BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0xCDEu, "FALSE");
                    }
                    v26 = *((_DWORD *)this + 83);
                    v25 = (unsigned int)(v25 + 1);
                  }
                  while ( (unsigned int)v25 < v26 );
                  if ( v24 >= v26 )
LABEL_59:
                    BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0xCE3u, "cNumFailures < m_cVolume");
                  if ( v24 )
                    PublishVolumeRestorePartialSuccessEvent((struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)&v31);
                  else
                    PublishVolumeRestoreSuccessEvent((struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)&v31);
                  goto LABEL_63;
                }
                if ( v30 == -2139619299 || v30 == -2139618969 )
                {
                  if ( (int)PublishVolumeRestoreCanceledEvent((struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)&v31) < 0 )
                  {
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                    {
                      v23 = 121;
                      goto LABEL_51;
                    }
                  }
                }
                else if ( (int)PublishVolumeRestoreGenericFailureEvent((struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)&v31) < 0 )
                {
                  v22 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                  {
                    v23 = 122;
LABEL_51:
                    WPP_SF_d(v22[2], v23, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
                  }
                }
LABEL_63:
                VolumeFriendlyNameForPublisher = PublishVolumeRestoreStopEvent(
                                                   (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)&v31,
                                                   &VOLUME_RESTORE_STOPPED_EVENT);
                if ( VolumeFriendlyNameForPublisher >= 0 )
                  VolumeFriendlyNameForPublisher = PublishRecoverySqmDatapoint(
                                                     (CBlbRestoreAsync *)((char *)this + 388),
                                                     *((_DWORD *)this + 4),
                                                     *((_DWORD *)this + 5));
              }
            }
          }
        }
      }
    }
  }
LABEL_65:
  CoTaskMemFree(v3);
  CoTaskMemFree(v29);
  FreeVolumeRestoreEventInfo((__int64)&v31);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  return (unsigned int)VolumeFriendlyNameForPublisher;
}

```

## disassembly

```asm
0x140059750  push    rbp
0x140059752  push    rbx
0x140059753  push    rsi
0x140059754  push    rdi
0x140059755  push    r12
0x140059757  push    r13
0x140059759  push    r14
0x14005975b  push    r15
0x14005975d  lea     rbp, [rsp-28h]
0x140059762  sub     rsp, 128h
0x140059769  mov     rax, cs:__security_cookie
0x140059770  xor     rax, rsp
0x140059773  mov     [rbp+60h+var_50], rax
0x140059777  mov     [rsp+160h+var_130], edx
0x14005977b  mov     rdi, rcx
0x14005977e  mov     ebx, 0C0h
0x140059783  lea     rcx, [rsp+160h+var_120]; void *
0x140059788  mov     r8d, ebx; Size
0x14005978b  xor     edx, edx; Val
0x14005978d  call    memset_0
0x140059792  xor     r12d, r12d
0x140059795  mov     [rsp+160h+var_138], 0
0x14005979e  mov     [rsp+160h+pv], r12
0x1400597a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400597aa  lea     rax, WPP_GLOBAL_Control
0x1400597b1  cmp     rcx, rax
0x1400597b4  jz      short loc_1400597D5
0x1400597b6  test    byte ptr [rcx+1Ch], 1
0x1400597ba  jz      short loc_1400597D5
0x1400597bc  cmp     byte ptr [rcx+19h], 4
0x1400597c0  jb      short loc_1400597D5
0x1400597c2  mov     rcx, [rcx+10h]
0x1400597c6  lea     edx, [rbx-49h]
0x1400597c9  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x1400597d0  call    WPP_SF_
0x1400597d5  mov     r8, rbx; Size
0x1400597d8  lea     rcx, [rsp+160h+var_120]; void *
0x1400597dd  xor     edx, edx; Val
0x1400597df  call    memset_0
0x1400597e4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400597eb  lea     rcx, [rbp+60h+Uuid]; Uuid
0x1400597ef  movdqu  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x1400597f4  call    cs:__imp_UuidCreate
0x1400597fa  mov     rax, [rdi+13Ch]
0x140059801  lea     r8, [rsp+160h+var_E8]
0x140059806  movups  xmm0, xmmword ptr [rdi+0D0h]
0x14005980d  mov     edx, [rdi+144h]
0x140059813  mov     rcx, [rdi+0E8h]
0x14005981a  mov     [rsp+160h+var_110], rax
0x14005981f  mov     eax, [rdi+114h]
0x140059825  mov     [rsp+160h+var_F8], eax
0x140059829  mov     eax, [rdi+10h]
0x14005982c  mov     [rsp+160h+var_F4], eax
0x140059830  mov     eax, [rdi+14h]
0x140059833  movdqu  [rsp+160h+var_120], xmm0
0x140059839  mov     [rsp+160h+var_F0], eax
0x14005983d  movups  xmm0, xmmword ptr [rbp+60h+Uuid.Data1]
0x140059841  mov     eax, [rdi+14Ch]
0x140059847  mov     [rbp+60h+var_E0], eax
0x14005984a  movdqu  [rsp+160h+var_108], xmm0
0x140059850  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAGW4_BLB_MEDIA_TYPE@@AEAPEAG@Z; GetVolumeFriendlyNameForPublisher(ushort *,_BLB_MEDIA_TYPE,ushort * &)
0x140059855  mov     ebx, eax
0x140059857  test    eax, eax
0x140059859  js      loc_140059DF3
0x14005985f  mov     ecx, [rbp+60h+var_E0]
0x140059862  shl     rcx, 3; cb
0x140059866  call    cs:__imp_CoTaskMemAlloc
0x14005986c  mov     [rbp+60h+var_D8], rax
0x140059870  test    rax, rax
0x140059873  jnz     short loc_14005987F
0x140059875  mov     ebx, 8007000Eh
0x14005987a  jmp     loc_140059DF3
0x14005987f  mov     r8d, [rbp+60h+var_E0]
0x140059883  xor     edx, edx; Val
0x140059885  shl     r8, 3; Size
0x140059889  mov     rcx, rax; void *
0x14005988c  call    memset_0
0x140059891  mov     ecx, [rbp+60h+var_E0]
0x140059894  shl     rcx, 3; cb
0x140059898  call    cs:__imp_CoTaskMemAlloc
0x14005989e  mov     [rbp+60h+var_D0], rax
0x1400598a2  test    rax, rax
0x1400598a5  jz      short loc_140059875
0x1400598a7  mov     r8d, [rbp+60h+var_E0]
0x1400598ab  xor     edx, edx; Val
0x1400598ad  shl     r8, 3; Size
0x1400598b1  mov     rcx, rax; void *
0x1400598b4  call    memset_0
0x1400598b9  mov     ecx, [rbp+60h+var_E0]
0x1400598bc  shl     rcx, 2; cb
0x1400598c0  call    cs:__imp_CoTaskMemAlloc
0x1400598c6  mov     [rbp+60h+var_C8], rax
0x1400598ca  test    rax, rax
0x1400598cd  jz      short loc_140059875
0x1400598cf  mov     r8d, [rbp+60h+var_E0]
0x1400598d3  xor     edx, edx; Val
0x1400598d5  shl     r8, 2; Size
0x1400598d9  mov     rcx, rax; void *
0x1400598dc  call    memset_0
0x1400598e1  mov     ecx, [rbp+60h+var_E0]
0x1400598e4  shl     rcx, 2; cb
0x1400598e8  call    cs:__imp_CoTaskMemAlloc
0x1400598ee  mov     [rbp+60h+var_A0], rax
0x1400598f2  test    rax, rax
0x1400598f5  jz      loc_140059875
0x1400598fb  mov     r8d, [rbp+60h+var_E0]
0x1400598ff  xor     edx, edx; Val
0x140059901  shl     r8, 2; Size
0x140059905  mov     rcx, rax; void *
0x140059908  call    memset_0
0x14005990d  mov     ecx, [rbp+60h+var_E0]
0x140059910  shl     rcx, 2; cb
0x140059914  call    cs:__imp_CoTaskMemAlloc
0x14005991a  mov     [rbp+60h+var_98], rax
0x14005991e  test    rax, rax
0x140059921  jz      loc_140059875
0x140059927  mov     r8d, [rbp+60h+var_E0]
0x14005992b  xor     edx, edx; Val
0x14005992d  shl     r8, 2; Size
0x140059931  mov     rcx, rax; void *
0x140059934  call    memset_0
0x140059939  mov     ecx, [rbp+60h+var_E0]
0x14005993c  shl     rcx, 3; cb
0x140059940  call    cs:__imp_CoTaskMemAlloc
0x140059946  mov     [rbp+60h+var_90], rax
0x14005994a  test    rax, rax
0x14005994d  jz      loc_140059875
0x140059953  mov     r8d, [rbp+60h+var_E0]
0x140059957  xor     edx, edx; Val
0x140059959  shl     r8, 3; Size
0x14005995d  mov     rcx, rax; void *
0x140059960  call    memset_0
0x140059965  mov     ecx, [rbp+60h+var_E0]
0x140059968  shl     rcx, 3; cb
0x14005996c  call    cs:__imp_CoTaskMemAlloc
0x140059972  mov     [rbp+60h+var_88], rax
0x140059976  test    rax, rax
0x140059979  jz      loc_140059875
0x14005997f  mov     r8d, [rbp+60h+var_E0]
0x140059983  xor     edx, edx; Val
0x140059985  shl     r8, 3; Size
0x140059989  mov     rcx, rax; void *
0x14005998c  call    memset_0
0x140059991  mov     edx, [rbp+60h+var_E0]; unsigned int
0x140059994  lea     rcx, [rbp+60h+var_B8]; void **
0x140059998  mov     r8d, 4; unsigned int
0x14005999e  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400599a3  mov     ebx, eax
0x1400599a5  test    eax, eax
0x1400599a7  js      loc_140059DF3
0x1400599ad  mov     edx, [rbp+60h+var_E0]; unsigned int
0x1400599b0  lea     rcx, [rbp+60h+var_C0]; void **
0x1400599b4  mov     r8d, 4; unsigned int
0x1400599ba  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400599bf  mov     ebx, eax
0x1400599c1  test    eax, eax
0x1400599c3  js      loc_140059DF3
0x1400599c9  mov     edx, [rbp+60h+var_E0]; unsigned int
0x1400599cc  lea     rcx, [rbp+60h+var_B0]; void **
0x1400599d0  mov     r8d, 4; unsigned int
0x1400599d6  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400599db  mov     ebx, eax
0x1400599dd  test    eax, eax
0x1400599df  js      loc_140059DF3
0x1400599e5  mov     edx, [rbp+60h+var_E0]; unsigned int
0x1400599e8  lea     rcx, [rbp+60h+var_A8]; void **
0x1400599ec  mov     r8d, 4; unsigned int
0x1400599f2  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400599f7  mov     ebx, eax
0x1400599f9  test    eax, eax
0x1400599fb  js      loc_140059DF3
0x140059a01  mov     edx, [rbp+60h+var_E0]; unsigned int
0x140059a04  lea     rcx, [rbp+60h+var_80]; void **
0x140059a08  mov     esi, 8
0x140059a0d  mov     r8d, esi; unsigned int
0x140059a10  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x140059a15  mov     ebx, eax
0x140059a17  test    eax, eax
0x140059a19  js      loc_140059DF3
0x140059a1f  mov     edx, [rbp+60h+var_E0]; unsigned int
0x140059a22  lea     rcx, [rbp+60h+var_78]; void **
0x140059a26  mov     r8d, esi; unsigned int
0x140059a29  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x140059a2e  mov     ebx, eax
0x140059a30  test    eax, eax
0x140059a32  js      loc_140059DF3
0x140059a38  xor     r13d, r13d
0x140059a3b  lea     rsi, [rdi+108h]
0x140059a42  cmp     r13d, [rbp+60h+var_E0]
0x140059a46  jnb     loc_140059B77
0x140059a4c  mov     rax, [rbp+60h+var_D8]
0x140059a50  lea     r14, ds:0[r13*2]
0x140059a58  lea     rsi, [rdi+108h]
0x140059a5f  add     r14, r13
0x140059a62  mov     rdx, [rsi]
0x140059a65  mov     r8d, 2
0x140059a6b  shl     r14, 6
0x140059a6f  lea     r9, [rax+r13*8]
0x140059a73  lea     rcx, [rdx+3Ch]
0x140059a77  mov     edx, [r14+rdx+4Ch]
0x140059a7c  add     rcx, r14
0x140059a7f  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAU_GUID@@KW4_BLB_MEDIA_TYPE@@PEAPEAG@Z; GetVolumeFriendlyNameForPublisher(_GUID *,ulong,_BLB_MEDIA_TYPE,ushort * *)
0x140059a84  mov     ebx, eax
0x140059a86  test    eax, eax
0x140059a88  js      loc_140059DF3
0x140059a8e  mov     rdx, [rsi]
0x140059a91  mov     r8d, 2
0x140059a97  mov     rax, [rbp+60h+var_D0]
0x140059a9b  lea     rcx, [rdx+50h]
0x140059a9f  mov     edx, [r14+rdx+60h]
0x140059aa4  add     rcx, r14
0x140059aa7  lea     r9, [rax+r13*8]
0x140059aab  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAU_GUID@@KW4_BLB_MEDIA_TYPE@@PEAPEAG@Z; GetVolumeFriendlyNameForPublisher(_GUID *,ulong,_BLB_MEDIA_TYPE,ushort * *)
0x140059ab0  mov     ebx, eax
0x140059ab2  test    eax, eax
0x140059ab4  js      loc_140059DF3
0x140059aba  mov     rax, [rsi]
0x140059abd  mov     ecx, [r14+rax+18h]
0x140059ac2  mov     rax, [rbp+60h+var_C8]
0x140059ac6  mov     [rax+r13*4], ecx
0x140059aca  mov     rax, [rsi]
0x140059acd  mov     ecx, [r14+rax+1Ch]
0x140059ad2  mov     rax, [rbp+60h+var_A0]
0x140059ad6  mov     [rax+r13*4], ecx
0x140059ada  mov     rax, [rsi]
0x140059add  mov     ecx, [r14+rax+14h]
0x140059ae2  mov     rax, [rbp+60h+var_98]
0x140059ae6  mov     [rax+r13*4], ecx
0x140059aea  mov     rax, [rsi]
0x140059aed  mov     rcx, [r14+rax+8]
0x140059af2  mov     rax, [rbp+60h+var_90]
0x140059af6  mov     [rax+r13*8], rcx
0x140059afa  mov     rax, [rsi]
0x140059afd  mov     rcx, [r14+rax]
0x140059b01  mov     rax, [rbp+60h+var_88]
0x140059b05  mov     [rax+r13*8], rcx
0x140059b09  mov     rax, [rsi]
0x140059b0c  mov     ecx, [r14+rax+38h]
0x140059b11  mov     rax, [rbp+60h+var_B8]
0x140059b15  mov     [rax+r13*4], ecx
0x140059b19  mov     rax, [rsi]
0x140059b1c  mov     ecx, [r14+rax+20h]
0x140059b21  mov     rax, [rbp+60h+var_C0]
0x140059b25  mov     [rax+r13*4], ecx
0x140059b29  mov     rax, [rsi]
0x140059b2c  mov     ecx, [r14+rax+9Ch]
0x140059b34  mov     rax, [rbp+60h+var_B0]
0x140059b38  mov     [rax+r13*4], ecx
0x140059b3c  mov     rax, [rsi]
0x140059b3f  mov     ecx, [r14+rax+0A0h]
0x140059b47  mov     rax, [rbp+60h+var_A8]
0x140059b4b  mov     [rax+r13*4], ecx
0x140059b4f  mov     rax, [rsi]
0x140059b52  mov     rcx, [r14+rax+28h]
0x140059b57  mov     rax, [rbp+60h+var_80]
0x140059b5b  mov     [rax+r13*8], rcx
0x140059b5f  mov     rax, [rsi]
0x140059b62  mov     rcx, [r14+rax+30h]
0x140059b67  mov     rax, [rbp+60h+var_78]
0x140059b6b  mov     [rax+r13*8], rcx
0x140059b6f  inc     r13d
0x140059b72  jmp     loc_140059A42
0x140059b77  xor     r15d, r15d
0x140059b7a  mov     ecx, [rdi+14Ch]
0x140059b80  cmp     r15d, ecx
0x140059b83  jnb     loc_140059C70
0x140059b89  mov     rdx, [rsi]
0x140059b8c  lea     r14, [r15+r15*2]
0x140059b90  shl     r14, 6
0x140059b94  cmp     dword ptr [r14+rdx+18h], 80780118h
0x140059b9d  jnz     loc_140059C57
0x140059ba3  lea     rcx, [rdx+50h]
0x140059ba7  mov     r8d, 2
0x140059bad  mov     edx, [r14+rdx+60h]
0x140059bb2  lea     r9, [rsp+160h+var_138]
0x140059bb7  add     rcx, r14
0x140059bba  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAU_GUID@@KW4_BLB_MEDIA_TYPE@@PEAPEAG@Z; GetVolumeFriendlyNameForPublisher(_GUID *,ulong,_BLB_MEDIA_TYPE,ushort * *)
0x140059bbf  mov     ebx, eax
0x140059bc1  test    eax, eax
0x140059bc3  js      loc_140059DF3
0x140059bc9  mov     rcx, [rsi]
0x140059bcc  lea     rdx, [rsp+160h+pv]; unsigned __int16 **
0x140059bd1  add     rcx, r14; this
0x140059bd4  call    ?GetRestoreTargetPath@CBlbVolumeRestoreContext@@QEAAJPEAPEAG@Z; CBlbVolumeRestoreContext::GetRestoreTargetPath(ushort * *)
0x140059bd9  mov     ebx, eax
0x140059bdb  test    eax, eax
0x140059bdd  js      loc_140059C66
0x140059be3  mov     r8, [rdi+164h]; struct _FILETIME
0x140059bea  mov     rdx, [rsp+160h+pv]; unsigned __int16 *
0x140059bef  mov     rcx, [rsp+160h+var_138]; unsigned __int16 *
0x140059bf4  call    ?PublishRestoreVolumeTooSmallEvent@@YAJPEAG0U_FILETIME@@@Z; PublishRestoreVolumeTooSmallEvent(ushort *,ushort *,_FILETIME)
0x140059bf9  test    eax, eax
0x140059bfb  jns     short loc_140059C34
0x140059bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140059c04  lea     rdx, WPP_GLOBAL_Control
0x140059c0b  cmp     rcx, rdx
0x140059c0e  jz      short loc_140059C34
0x140059c10  test    byte ptr [rcx+1Ch], 1
0x140059c14  jz      short loc_140059C34
0x140059c16  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
