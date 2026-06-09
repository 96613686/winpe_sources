# CSatelliteCargoContext::SendLibraryResults(_GUID const *,CSQLSatelliteConnection *,_SQLSatellite_LibraryList * *,_SQLSatellite_String * *)

- ea: `0x100412810`
- end: `0x100412dc5`
- name: `?SendLibraryResults@CSatelliteCargoContext@@SAJPEBU_GUID@@PEAVCSQLSatelliteConnection@@PEAPEAU_SQLSatellite_LibraryList@@PEAPEAU_SQLSatellite_String@@@Z`
- size: `1461`
- prototype: `__int64 __fastcall(const struct _GUID *, struct CSQLSatelliteConnection *, struct _SQLSatellite_LibraryList **, struct _SQLSatellite_String **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x10040ac30`

## callees

- `0x100412810`
- `0x10041ec10`
- `0x10041f180`
- `0x100455f90`
- `0x100471d80`
- `0x100478330`
- `0x10047a370`
- `0x10047c570`
- `0x10048823d`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x100412d08`
- `KERNEL32!GetCurrentThreadId` at `0x100412d08`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100412d7d`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100412d7d`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100412cb8`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100412cb8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100412994`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100412994`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100412988`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100412988`

## pseudocode

```c
__int64 __fastcall CSatelliteCargoContext::SendLibraryResults(
        const struct _GUID *a1,
        struct CSQLSatelliteConnection *a2,
        struct _SQLSatellite_LibraryList **a3,
        struct _SQLSatellite_String **a4)
{
  __int64 v4; // r12
  int v5; // r15d
  __int64 v6; // r13
  struct _SQLSatellite_LibraryList **v7; // r14
  struct CSQLSatelliteConnection *v8; // rbx
  __int64 Ex2; // rax
  __int64 v10; // rdi
  unsigned int v11; // edx
  int v12; // esi
  struct _GUID *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  bool v16; // zf
  struct _SQLSatellite_LibraryList *v17; // rcx
  const struct _SQLSatellite_String *v18; // r8
  struct _SQLSatellite_LibraryList *v19; // rdx
  int v20; // eax
  struct SNI_Packet *v21; // rsi
  struct _SQLSatellite_LibraryList *v22; // rdx
  const struct _SQLSatellite_String *v23; // r8
  int v24; // eax
  int v25; // r14d
  bool v26; // al
  bool v27; // cf
  unsigned int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rdx
  int v33; // eax
  DWORD CurrentThreadId; // eax
  __int64 v35; // rbx
  struct SNI_Packet *v36; // rbx
  int v38; // [rsp+20h] [rbp-E0h]
  bool v39[16]; // [rsp+30h] [rbp-D0h] BYREF
  void **v40; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h]
  __int64 v42; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+58h] [rbp-A8h]
  __int64 v44; // [rsp+60h] [rbp-A0h]
  __int64 v45; // [rsp+68h] [rbp-98h]
  int v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+74h] [rbp-8Ch]
  __int16 v48; // [rsp+7Ch] [rbp-84h]
  int v49; // [rsp+7Eh] [rbp-82h]
  __int16 v50; // [rsp+82h] [rbp-7Eh]
  __int64 v51; // [rsp+84h] [rbp-7Ch]
  int v52; // [rsp+8Ch] [rbp-74h]
  __int128 v53; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h]
  int v55; // [rsp+A8h] [rbp-58h]
  DWORD v56; // [rsp+ACh] [rbp-54h]
  const char *v57; // [rsp+B0h] [rbp-50h]
  int v58; // [rsp+B8h] [rbp-48h]
  _BYTE v59[216]; // [rsp+C0h] [rbp-40h] BYREF
  int v60; // [rsp+198h] [rbp+98h]
  __int64 v61; // [rsp+1A0h] [rbp+A0h]

  v39[0] = 0;
  v41 = 0;
  v4 = 0;
  v42 = 0;
  v43 = 0;
  v5 = 0;
  v44 = 0;
  v6 = 0;
  v45 = 0;
  v7 = a3;
  v40 = &CSQLSatelliteMessageLibraryManagement::`vftable';
  v8 = a2;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v46 = 1024;
  v47 = 260;
  while ( 1 )
  {
    Ex2 = SNIPacketAllocateEx2(*((_QWORD *)v8 + 8), 1u, 0);
    v10 = Ex2;
    if ( !Ex2 )
      break;
    v11 = *(_DWORD *)(Ex2 + 180);
    if ( v11 < 0x400 )
    {
      v5 = -2089418750;
      v21 = (struct SNI_Packet *)Ex2;
      HIDWORD(v44) = -2089418750;
      v25 = -2089418750;
      goto LABEL_45;
    }
    v12 = v11 - 24;
    v4 = *(_QWORD *)(Ex2 + 168) + *(unsigned int *)(Ex2 + 184);
    v41 = v4;
    LODWORD(v43) = v11 - 24;
    HIDWORD(v43) = v11;
    *(_WORD *)v4 = 1;
    v42 = v4 + 24;
    v44 = 2;
    if ( !(_DWORD)v51 || (_DWORD)v51 == 15 )
    {
      v51 = 7;
      LOBYTE(v48) = 0;
      v52 = 0;
    }
    *(_WORD *)(v4 + 2) &= 0x8010u;
    *(_WORD *)(v4 + 2) |= 0x10u;
    CSQLSatelliteMessage::FireXEvent(&v40, 2);
    v13 = (struct _GUID *)(v4 + 8);
    if ( v4 != -8 )
    {
      if ( a1 )
      {
        *v13 = *a1;
        goto LABEL_13;
      }
      *v13 = 0;
    }
    *_errno() = 22;
    _invalid_parameter_noinfo();
LABEL_13:
    if ( !v6 )
    {
      v6 = 0;
      v14 = _RTDynamicCast_0(
              g_satelliteExecutor,
              0,
              &ISatelliteExecutor `RTTI Type Descriptor',
              &CSatelliteSpeesExecutor `RTTI Type Descriptor',
              0);
      if ( v14 )
      {
        v15 = *(_QWORD *)(v14 + 2080);
        if ( v15 )
          v6 = *(_QWORD *)(v15 + 296);
      }
      v45 = v6;
    }
    if ( (unsigned int)(v51 - 7) > 1 )
    {
      if ( (_BYTE)v48 )
      {
        v18 = a4[1];
        v19 = v7[1];
      }
      else
      {
        v18 = *a4;
        v19 = *v7;
      }
      goto LABEL_27;
    }
    v16 = v7[1] == 0;
    LODWORD(v51) = 9;
    *(_BYTE *)(v4 + 24) = !v16 + 1;
    v17 = v7[1];
    if ( v12 >= 1 )
    {
      v42 = v4 + 25;
      LODWORD(v43) = v12 - 1;
      HIBYTE(v48) = (v17 != 0) + 1;
      if ( (_BYTE)v48 )
      {
        v18 = a4[1];
        v19 = v17;
      }
      else
      {
        v18 = *a4;
        v19 = *v7;
      }
LABEL_27:
      v20 = CSQLSatelliteMessageLibraryManagement::WriteLibraryList(
              (CSQLSatelliteMessageLibraryManagement *)&v40,
              v19,
              v18,
              v39);
      v4 = v41;
      v5 = v20;
      v6 = v45;
      HIDWORD(v44) = v20;
      goto LABEL_28;
    }
    v5 = -2089418750;
    HIDWORD(v44) = -2089418750;
    HIBYTE(v48) = (v17 != 0) + 1;
LABEL_28:
    v21 = (struct SNI_Packet *)v10;
    if ( HIBYTE(v48) == 2 && v39[0] && !(_BYTE)v48 && v5 >= 0 )
    {
      v22 = v7[1];
      LOBYTE(v48) = 1;
      v39[0] = 0;
      v23 = a4[1];
      LODWORD(v51) = 9;
      v24 = CSQLSatelliteMessageLibraryManagement::WriteLibraryList(
              (CSQLSatelliteMessageLibraryManagement *)&v40,
              v22,
              v23,
              v39);
      v6 = v45;
      v5 = v24;
      v4 = v41;
      HIDWORD(v44) = v24;
    }
    v25 = v5;
    if ( v5 < 0 )
      goto LABEL_44;
    v26 = v39[0];
    *(_WORD *)(v4 + 2) &= ~0x8000u;
    v27 = v26;
    v28 = v42 - v41;
    *(_WORD *)(v4 + 2) |= v27 ? 0x8000 : 0;
    if ( v28 > HIDWORD(v43) )
    {
      v5 = -2089418750;
      HIDWORD(v44) = -2089418750;
      v25 = -2089418750;
LABEL_44:
      v8 = a2;
      goto LABEL_45;
    }
    *(_DWORD *)(v4 + 4) = v28;
    CSQLSatelliteMessage::FireXEvent(&v40, 1);
    if ( v6 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(v6 + 8 * (26LL * (int)v44 + (*(_WORD *)(v4 + 2) & 0x7FFF)) + 8));
      v6 = v45;
      v5 = HIDWORD(v44);
    }
    v29 = *(unsigned int *)(v10 + 184);
    v21 = 0;
    v4 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    LODWORD(v44) = 0;
    v30 = *(_QWORD *)(v10 + 168) + v29;
    if ( v30 )
    {
      v8 = a2;
      *(_DWORD *)(v10 + 176) = *(_DWORD *)(v30 + 4);
      v25 = CSQLSatelliteConnection::WriteMessage(a2, (struct SNI_Packet *)v10);
      if ( v25 < 0 )
        goto LABEL_45;
    }
    else
    {
      do
      {
        v31 = *(_QWORD *)(v10 + 208);
        *(_QWORD *)(v10 + 208) = 0;
        SNIPacketRelease((struct SNI_Packet *)v10);
        v10 = v31;
      }
      while ( v31 );
      v8 = a2;
      v25 = 1359;
    }
    if ( v39[0] )
      goto LABEL_53;
    v7 = a3;
  }
  v21 = 0;
  v25 = -2147024882;
LABEL_45:
  CSQLSatelliteMessage::FireXEvent(&v40, 1);
  if ( v6 )
  {
    v32 = *(_WORD *)(v4 + 2) & 0x7FFF;
    if ( v5 < 0 )
    {
      if ( (unsigned int)v32 >= 0x1A )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v6 + 8));
      }
      else
      {
        _mm_lfence();
        _InterlockedIncrement64((volatile signed __int64 *)(v6 + 8 * v32 + 8));
      }
    }
    else
    {
      _InterlockedIncrement64((volatile signed __int64 *)(v6 + 8 * ((*(_WORD *)(v4 + 2) & 0x7FFF) + 26LL * (int)v44) + 8));
    }
  }
LABEL_53:
  if ( v25 >= 0 && *((int *)v8 + 38) > 0 )
  {
    _mm_lfence();
    LOBYTE(v38) = 1;
    v33 = WaitableBase::Wait((char *)v8 + 352, 0xFFFFFFFFLL, (char *)v8 + 224, 0, v38);
    if ( *((_BYTE *)v8 + 57) )
      goto LABEL_63;
    switch ( v33 )
    {
      case 0:
        goto LABEL_70;
      case 2:
LABEL_63:
        v25 = -2147467260;
        break;
      case 258:
        v25 = -2147483638;
        break;
      default:
        v25 = -2147024882;
        if ( v33 != -1073741824 )
          v25 = -2147467259;
        break;
    }
    if ( g_extensibilityErrorRingBuffer )
    {
      CurrentThreadId = GetCurrentThreadId();
      v35 = g_extensibilityErrorRingBuffer;
      v56 = CurrentThreadId;
      v54 = 0;
      v57 = "CSatelliteCargoContext::SendLibraryResults";
      v53 = 0;
      v55 = v25;
      v58 = 865;
      v60 = 0;
      v61 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v59, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v53, v59);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v35, &v53, v59);
    }
  }
LABEL_70:
  if ( v21 )
  {
    do
    {
      v36 = (struct SNI_Packet *)*((_QWORD *)v21 + 26);
      *((_QWORD *)v21 + 26) = 0;
      SNIPacketRelease(v21);
      v21 = v36;
    }
    while ( v36 );
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x100412810  mov     [rsp-8+arg_18], r9
0x100412815  mov     [rsp-8+arg_10], r8
0x10041281a  mov     [rsp-8+arg_8], rdx
0x10041281f  mov     [rsp-8+arg_0], rcx
0x100412824  push    rbp
0x100412825  push    rbx
0x100412826  push    rsi
0x100412827  push    rdi
0x100412828  push    r12
0x10041282a  push    r13
0x10041282c  push    r14
0x10041282e  push    r15
0x100412830  lea     rbp, [rsp-0B8h]
0x100412838  sub     rsp, 1B8h
0x10041283f  xor     esi, esi
0x100412841  mov     [rsp+1F0h+var_1C0], 0
0x100412846  lea     rax, ??_7CSQLSatelliteMessageLibraryManagement@@6B@; const CSQLSatelliteMessageLibraryManagement::`vftable'
0x10041284d  mov     [rsp+1F0h+var_1A8], rsi
0x100412852  mov     r12d, esi
0x100412855  mov     [rsp+1F0h+var_1A0], rsi
0x10041285a  mov     [rsp+1F0h+var_198], rsi
0x10041285f  mov     r15d, esi
0x100412862  mov     [rsp+1F0h+var_190], rsi
0x100412867  mov     r13d, esi
0x10041286a  mov     [rsp+1F0h+var_188], rsi
0x10041286f  mov     r14, r8
0x100412872  mov     [rsp+1F0h+var_1B0], rax
0x100412877  mov     rbx, rdx
0x10041287a  mov     [rsp+1F0h+var_174], si
0x10041287f  mov     [rsp+1F0h+var_172], esi
0x100412883  mov     [rbp+0F0h+var_16E], si
0x100412887  mov     [rbp+0F0h+var_16C], rsi
0x10041288b  mov     [rbp+0F0h+var_164], esi
0x10041288e  mov     [rsp+1F0h+var_180], 400h
0x100412896  mov     [rsp+1F0h+var_17C], 104h
0x10041289f  jmp     short loc_1004128B7
0x1004128b0  mov     r14, [rbp+0F0h+arg_10]
0x1004128b7  mov     rcx, [rbx+40h]
0x1004128bb  mov     eax, 1
0x1004128c0  mov     edx, eax
0x1004128c2  xor     r8d, r8d
0x1004128c5  call    SNIPacketAllocateEx2
0x1004128ca  mov     rdi, rax
0x1004128cd  test    rax, rax
0x1004128d0  jz      loc_100412C63
0x1004128d6  mov     edx, [rax+0B4h]
0x1004128dc  cmp     edx, 400h
0x1004128e2  jb      loc_100412C50
0x1004128e8  mov     r12d, [rax+0B8h]
0x1004128ef  lea     esi, [rdx-18h]
0x1004128f2  add     r12, [rax+0A8h]
0x1004128f9  xor     r15d, r15d
0x1004128fc  mov     eax, 1
0x100412901  mov     [rsp+1F0h+var_1A8], r12
0x100412906  mov     dword ptr [rsp+1F0h+var_198], esi
0x10041290a  mov     dword ptr [rsp+1F0h+var_198+4], edx
0x10041290e  mov     [r12], ax
0x100412913  lea     rbx, [r12+18h]
0x100412918  mov     eax, dword ptr [rbp+0F0h+var_16C]
0x10041291b  mov     [rsp+1F0h+var_1A0], rbx
0x100412920  mov     [rsp+1F0h+var_190], 2
0x100412929  test    eax, eax
0x10041292b  jz      short loc_100412932
0x10041292d  cmp     eax, 0Fh
0x100412930  jnz     short loc_100412943
0x100412932  mov     [rbp+0F0h+var_16C], 7
0x10041293a  mov     byte ptr [rsp+1F0h+var_174], r15b
0x10041293f  mov     [rbp+0F0h+var_164], r15d
0x100412943  mov     eax, 8010h
0x100412948  lea     rcx, [rsp+1F0h+var_1B0]
0x10041294d  and     [r12+2], ax
0x100412953  mov     edx, 2
0x100412958  or      word ptr [r12+2], 10h
0x10041295f  call    ?FireXEvent@CSQLSatelliteMessage@@IEAAXW4ESQLSatelliteMessage_OperationCode@@@Z; CSQLSatelliteMessage::FireXEvent(ESQLSatelliteMessage_OperationCode)
0x100412964  lea     rax, [r12+8]
0x100412969  test    rax, rax
0x10041296c  jz      short loc_100412988
0x10041296e  mov     rcx, [rbp+0F0h+arg_0]
0x100412975  test    rcx, rcx
0x100412978  jz      short loc_100412982
0x10041297a  movups  xmm0, xmmword ptr [rcx]
0x10041297d  movups  xmmword ptr [rax], xmm0
0x100412980  jmp     short loc_10041299A
0x100412982  xorps   xmm0, xmm0
0x100412985  movups  xmmword ptr [rax], xmm0
0x100412988  call    cs:__imp__errno
0x10041298e  mov     dword ptr [rax], 16h
0x100412994  call    cs:__imp__invalid_parameter_noinfo
0x10041299a  test    r13, r13
0x10041299d  jnz     short loc_1004129E0
0x10041299f  mov     rcx, cs:?g_satelliteExecutor@@3PEAVISatelliteExecutor@@EA; ISatelliteExecutor * g_satelliteExecutor
0x1004129a6  lea     r9, ??_R0?AVCSatelliteSpeesExecutor@@@8; CSatelliteSpeesExecutor `RTTI Type Descriptor'
0x1004129ad  lea     r8, ??_R0?AVISatelliteExecutor@@@8; ISatelliteExecutor `RTTI Type Descriptor'
0x1004129b4  mov     [rsp+1F0h+var_1D0], r15d
0x1004129b9  xor     edx, edx
0x1004129bb  mov     r13, r15
0x1004129be  call    __RTDynamicCast_0
0x1004129c3  test    rax, rax
0x1004129c6  jz      short loc_1004129DB
0x1004129c8  mov     rax, [rax+820h]
0x1004129cf  test    rax, rax
0x1004129d2  jz      short loc_1004129DB
0x1004129d4  mov     r13, [rax+128h]
0x1004129db  mov     [rsp+1F0h+var_188], r13
0x1004129e0  mov     eax, dword ptr [rbp+0F0h+var_16C]
0x1004129e3  add     eax, 0FFFFFFF9h
0x1004129e6  cmp     eax, 1
0x1004129e9  ja      short loc_100412A5B
0x1004129eb  cmp     [r14+8], r15
0x1004129ef  mov     dword ptr [rbp+0F0h+var_16C], 9
0x1004129f6  setnz   al
0x1004129f9  inc     al
0x1004129fb  mov     [rbx], al
0x1004129fd  mov     rcx, [r14+8]
0x100412a01  cmp     esi, 1
0x100412a04  jl      short loc_100412A42
0x100412a06  inc     rbx
0x100412a09  dec     esi
0x100412a0b  test    rcx, rcx
0x100412a0e  mov     [rsp+1F0h+var_1A0], rbx
0x100412a13  mov     dword ptr [rsp+1F0h+var_198], esi
0x100412a17  setnz   al
0x100412a1a  inc     al
0x100412a1c  mov     byte ptr [rsp+1F0h+var_174+1], al
0x100412a20  mov     rax, [rbp+0F0h+arg_18]
0x100412a27  cmp     byte ptr [rsp+1F0h+var_174], r15b
0x100412a2c  jnz     short loc_100412A39
0x100412a2e  mov     rcx, [r14]
0x100412a31  mov     r8, [rax]
0x100412a34  mov     rdx, rcx
0x100412a37  jmp     short loc_100412A79
0x100412a39  mov     r8, [rax+8]
0x100412a3d  mov     rdx, rcx
0x100412a40  jmp     short loc_100412A79
0x100412a42  test    rcx, rcx
0x100412a45  mov     r15d, 83760002h
0x100412a4b  mov     dword ptr [rsp+1F0h+var_190+4], r15d
0x100412a50  setnz   al
0x100412a53  inc     al
0x100412a55  mov     byte ptr [rsp+1F0h+var_174+1], al
0x100412a59  jmp     short loc_100412A99
0x100412a5b  mov     rax, [rbp+0F0h+arg_18]
0x100412a62  cmp     byte ptr [rsp+1F0h+var_174], r15b
0x100412a67  jnz     short loc_100412A71
0x100412a69  mov     r8, [rax]
0x100412a6c  mov     rdx, [r14]
0x100412a6f  jmp     short loc_100412A79
0x100412a71  mov     r8, [rax+8]; struct _SQLSatellite_String *
0x100412a75  mov     rdx, [r14+8]; struct _SQLSatellite_LibraryList *
0x100412a79  lea     r9, [rsp+1F0h+var_1C0]; bool *
0x100412a7e  lea     rcx, [rsp+1F0h+var_1B0]; this
0x100412a83  call    ?WriteLibraryList@CSQLSatelliteMessageLibraryManagement@@AEAAJPEAU_SQLSatellite_LibraryList@@PEBU_SQLSatellite_String@@AEA_N@Z; CSQLSatelliteMessageLibraryManagement::WriteLibraryList(_SQLSatellite_LibraryList *,_SQLSatellite_String const *,bool &)
0x100412a88  mov     r12, [rsp+1F0h+var_1A8]
0x100412a8d  mov     r15d, eax
0x100412a90  mov     r13, [rsp+1F0h+var_188]
0x100412a95  mov     dword ptr [rsp+1F0h+var_190+4], eax
0x100412a99  cmp     byte ptr [rsp+1F0h+var_174+1], 2
0x100412a9e  mov     rsi, rdi
0x100412aa1  jnz     short loc_100412AF6
0x100412aa3  cmp     [rsp+1F0h+var_1C0], 0
0x100412aa8  jz      short loc_100412AF6
0x100412aaa  cmp     byte ptr [rsp+1F0h+var_174], 0
0x100412aaf  jnz     short loc_100412AF6
0x100412ab1  test    r15d, r15d
0x100412ab4  js      short loc_100412AF6
0x100412ab6  mov     rax, [rbp+0F0h+arg_18]
0x100412abd  lea     r9, [rsp+1F0h+var_1C0]; bool *
0x100412ac2  mov     rdx, [r14+8]; struct _SQLSatellite_LibraryList *
0x100412ac6  lea     rcx, [rsp+1F0h+var_1B0]; this
0x100412acb  mov     byte ptr [rsp+1F0h+var_174], 1
0x100412ad0  mov     [rsp+1F0h+var_1C0], 0
0x100412ad5  mov     r8, [rax+8]; struct _SQLSatellite_String *
0x100412ad9  mov     dword ptr [rbp+0F0h+var_16C], 9
0x100412ae0  call    ?WriteLibraryList@CSQLSatelliteMessageLibraryManagement@@AEAAJPEAU_SQLSatellite_LibraryList@@PEBU_SQLSatellite_String@@AEA_N@Z; CSQLSatelliteMessageLibraryManagement::WriteLibraryList(_SQLSatellite_LibraryList *,_SQLSatellite_String const *,bool &)
0x100412ae5  mov     r13, [rsp+1F0h+var_188]
0x100412aea  mov     r15d, eax
0x100412aed  mov     r12, [rsp+1F0h+var_1A8]
0x100412af2  mov     dword ptr [rsp+1F0h+var_190+4], eax
0x100412af6  mov     r14d, r15d
0x100412af9  test    r15d, r15d
0x100412afc  js      loc_100412C0D
0x100412b02  movzx   eax, [rsp+1F0h+var_1C0]
0x100412b07  mov     ebx, 7FFFh
0x100412b0c  and     [r12+2], bx
0x100412b12  neg     al
0x100412b14  mov     eax, dword ptr [rsp+1F0h+var_1A0]
0x100412b18  sbb     cx, cx
0x100412b1b  sub     eax, dword ptr [rsp+1F0h+var_1A8]
0x100412b1f  and     cx, 8000h
0x100412b24  or      [r12+2], cx
0x100412b2a  cmp     eax, dword ptr [rsp+1F0h+var_198+4]
0x100412b2e  ja      loc_100412BFF
0x100412b34  mov     edx, 1
0x100412b39  mov     [r12+4], eax
0x100412b3e  lea     rcx, [rsp+1F0h+var_1B0]
0x100412b43  call    ?FireXEvent@CSQLSatelliteMessage@@IEAAXW4ESQLSatelliteMessage_OperationCode@@@Z; CSQLSatelliteMessage::FireXEvent(ESQLSatelliteMessage_OperationCode)
0x100412b48  test    r13, r13
0x100412b4b  jz      short loc_100412B72
0x100412b4d  movsxd  rax, dword ptr [rsp+1F0h+var_190]
0x100412b52  movzx   edx, word ptr [r12+2]
0x100412b58  imul    rcx, rax, 1Ah
0x100412b5c  and     rdx, rbx
0x100412b5f  add     rdx, rcx
0x100412b62  lock inc qword ptr [r13+rdx*8+8]
0x100412b68  mov     r13, [rsp+1F0h+var_188]
0x100412b6d  mov     r15d, dword ptr [rsp+1F0h+var_190+4]
0x100412b72  mov     eax, [rdi+0B8h]
0x100412b78  xor     esi, esi
0x100412b7a  mov     r12d, esi
0x100412b7d  mov     [rsp+1F0h+var_1A8], rsi
0x100412b82  mov     [rsp+1F0h+var_1A0], rsi
0x100412b87  mov     [rsp+1F0h+var_198], rsi
0x100412b8c  mov     dword ptr [rsp+1F0h+var_190], esi
0x100412b90  add     rax, [rdi+0A8h]
0x100412b97  jnz     short loc_100412BCD
0x100412b99  nop     dword ptr [rax+00000000h]
0x100412ba0  mov     rbx, [rdi+0D0h]
0x100412ba7  mov     rcx, rdi; struct SNI_Packet *
0x100412baa  mov     [rdi+0D0h], rsi
0x100412bb1  call    SNIPacketRelease
0x100412bb6  mov     rdi, rbx
0x100412bb9  test    rbx, rbx
0x100412bbc  jnz     short loc_100412BA0
0x100412bbe  mov     rbx, [rbp+0F0h+arg_8]
0x100412bc5  mov     r14d, 54Fh
0x100412bcb  jmp     short loc_100412BEF
0x100412bcd  mov     eax, [rax+4]
0x100412bd0  mov     rdx, rdi; struct SNI_Packet *
0x100412bd3  mov     rbx, [rbp+0F0h+arg_8]
0x100412bda  mov     rcx, rbx; this
0x100412bdd  mov     [rdi+0B0h], eax
0x100412be3  call    ?WriteMessage@CSQLSatelliteConnection@@QEAAKPEAVSNI_Packet@@@Z; CSQLSatelliteConnection::WriteMessage(SNI_Packet *)
0x100412be8  mov     r14d, eax
0x100412beb  test    eax, eax
0x100412bed  js      short loc_100412C14
0x100412bef  cmp     [rsp+1F0h+var_1C0], r12b
0x100412bf4  jz      loc_1004128B0
0x100412bfa  jmp     loc_100412C83
0x100412bff  mov     r15d, 83760002h
0x100412c05  mov     dword ptr [rsp+1F0h+var_190+4], r15d
0x100412c0a  mov     r14d, r15d
0x100412c0d  mov     rbx, [rbp+0F0h+arg_8]
0x100412c14  mov     edx, 1
0x100412c19  lea     rcx, [rsp+1F0h+var_1B0]
0x100412c1e  call    ?FireXEvent@CSQLSatelliteMessage@@IEAAXW4ESQLSatelliteMessage_OperationCode@@@Z; CSQLSatelliteMessage::FireXEvent(ESQLSatelliteMessage_OperationCode)
0x100412c23  test    r13, r13
0x100412c26  jz      short loc_100412C83
0x100412c28  movzx   edx, word ptr [r12+2]
0x100412c2e  mov     ecx, 7FFFh
0x100412c33  and     edx, ecx
0x100412c35  test    r15d, r15d
0x100412c38  js      short loc_100412C6E
0x100412c3a  movsxd  rax, dword ptr [rsp+1F0h+var_190]
0x100412c3f  imul    rcx, rax, 1Ah
0x100412c43  mov     eax, edx
0x100412c45  add     rcx, rax
0x100412c48  lock inc qword ptr [r13+rcx*8+8]
0x100412c4e  jmp     short loc_100412C83
0x100412c50  mov     r15d, 83760002h
0x100412c56  mov     rsi, rdi
0x100412c59  mov     dword ptr [rsp+1F0h+var_190+4], r15d
0x100412c5e  mov     r14d, r15d
0x100412c61  jmp     short loc_100412C14
0x100412c63  mov     rsi, rdi
0x100412c66  mov     r14d, 8007000Eh
0x100412c6c  jmp     short loc_100412C14
0x100412c6e  cmp     edx, 1Ah
0x100412c71  jnb     short loc_100412C7E
0x100412c73  lfence
0x100412c76  lock inc qword ptr [r13+rdx*8+8]
0x100412c7c  jmp     short loc_100412C83
0x100412c7e  lock inc qword ptr [r13+8]
0x100412c83  test    r14d, r14d
0x100412c86  js      loc_100412D85
0x100412c8c  mov     eax, [rbx+98h]
0x100412c92  test    eax, eax
0x100412c94  jle     loc_100412D85
0x100412c9a  lfence
0x100412c9d  lea     r8, [rbx+0E0h]
0x100412ca4  mov     byte ptr [rsp+1F0h+var_1D0], 1
0x100412ca9  lea     rcx, [rbx+160h]
0x100412cb0  xor     r9d, r9d
0x100412cb3  mov     edx, 0FFFFFFFFh
0x100412cb8  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100412cbe  movzx   ecx, byte ptr [rbx+39h]
0x100412cc2  test    cl, cl
0x100412cc4  jnz     short loc_100412CF8
0x100412cc6  test    eax, eax
0x100412cc8  jz      loc_100412D85
0x100412cce  cmp     eax, 2
0x100412cd1  jz      short loc_100412CF8
0x100412cd3  cmp     eax, 102h
0x100412cd8  jz      short loc_100412CF0
0x100412cda  cmp     eax, 0C0000000h
0x100412cdf  mov     ecx, 80004005h
0x100412ce4  mov     r14d, 8007000Eh
0x100412cea  cmovnz  r14d, ecx
0x100412cee  jmp     short loc_100412CFE
0x100412cf0  mov     r14d, 8000000Ah
0x100412cf6  jmp     short loc_100412CFE
  ... truncated ...
```
