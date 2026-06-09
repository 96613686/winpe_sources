# CSatelliteCargoContext::SendLanguageResults(_GUID const *,CSQLSatelliteConnection *,_SQLSatellite_LanguageError *)

- ea: `0x100412dd0`
- end: `0x100413211`
- name: `?SendLanguageResults@CSatelliteCargoContext@@QEAAJPEBU_GUID@@PEAVCSQLSatelliteConnection@@PEAU_SQLSatellite_LanguageError@@@Z`
- size: `1089`
- prototype: `__int64 __fastcall(CSatelliteCargoContext *__hidden this, const struct _GUID *, struct CSQLSatelliteConnection *, struct _SQLSatellite_LanguageError *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1004089b0`

## callees

- `0x100412dd0`
- `0x10041ec10`
- `0x10041f180`
- `0x100455f90`
- `0x100471d80`
- `0x100478330`
- `0x10047a370`
- `0x10047e710`
- `0x10048823d`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10041314b`
- `KERNEL32!GetCurrentThreadId` at `0x10041314b`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004131be`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004131be`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1004130fe`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1004130fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100412f14`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100412f14`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100412f08`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100412f08`

## pseudocode

```c
__int64 __fastcall CSatelliteCargoContext::SendLanguageResults(
        CSatelliteCargoContext *this,
        const struct _GUID *a2,
        struct CSQLSatelliteConnection *a3,
        struct _SQLSatellite_LanguageError *a4)
{
  __int64 v6; // rcx
  __int64 v7; // r14
  int v8; // edi
  __int64 v9; // r15
  __int64 Ex2; // rax
  __int64 v11; // rbx
  unsigned int v12; // edx
  int v13; // esi
  _OWORD *v14; // r14
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rdx
  int v23; // eax
  DWORD CurrentThreadId; // eax
  __int64 v25; // rdi
  __int64 v26; // rdi
  int v28; // [rsp+20h] [rbp-E0h]
  void **v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h]
  __int64 v31; // [rsp+40h] [rbp-C0h]
  __int64 v32; // [rsp+48h] [rbp-B8h]
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  int v35; // [rsp+60h] [rbp-A0h]
  __int64 v36; // [rsp+64h] [rbp-9Ch]
  int v37; // [rsp+6Ch] [rbp-94h]
  __int64 v38; // [rsp+70h] [rbp-90h]
  __int128 v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+98h] [rbp-68h]
  DWORD v42; // [rsp+9Ch] [rbp-64h]
  const char *v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A8h] [rbp-58h]
  _BYTE v45[216]; // [rsp+B0h] [rbp-50h] BYREF
  int v46; // [rsp+188h] [rbp+88h]
  __int64 v47; // [rsp+190h] [rbp+90h]

  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v6 = *((_QWORD *)a3 + 8);
  v7 = 0;
  v8 = 0;
  v34 = 0;
  v9 = 0;
  v29 = &CSQLSatelliteMessageLanguageManagement::`vftable';
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  Ex2 = SNIPacketAllocateEx2(v6, 1u, 0);
  v11 = Ex2;
  if ( !Ex2 )
  {
    v13 = -2147024882;
    goto LABEL_30;
  }
  v12 = *(_DWORD *)(Ex2 + 180);
  if ( v12 < 0x10 )
  {
    v8 = -2089418750;
    HIDWORD(v33) = -2089418750;
    v13 = -2089418750;
    goto LABEL_30;
  }
  if ( v12 >= 0x18 )
  {
    v7 = *(_QWORD *)(Ex2 + 168) + *(unsigned int *)(Ex2 + 184);
    HIDWORD(v32) = *(_DWORD *)(Ex2 + 180);
    v30 = v7;
    v33 = 2;
    v31 = v7 + 24;
    LODWORD(v32) = v12 - 24;
    *(_WORD *)v7 = 1;
    *(_WORD *)(v7 + 2) &= 0x8018u;
    *(_WORD *)(v7 + 2) |= 0x18u;
    CSQLSatelliteMessage::FireXEvent(&v29, 2);
  }
  else
  {
    v8 = -2089418750;
    HIDWORD(v33) = -2089418750;
  }
  v13 = v8;
  if ( v8 < 0 )
  {
LABEL_30:
    CSQLSatelliteMessage::FireXEvent(&v29, 1);
    if ( v9 )
    {
      v22 = *(_WORD *)(v7 + 2) & 0x7FFF;
      if ( v8 < 0 )
      {
        if ( (unsigned int)v22 >= 0x1A )
        {
          _InterlockedIncrement64((volatile signed __int64 *)(v9 + 8));
        }
        else
        {
          _mm_lfence();
          _InterlockedIncrement64((volatile signed __int64 *)(v9 + 8 * v22 + 8));
        }
      }
      else
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v9
                                                          + 8 * ((*(_WORD *)(v7 + 2) & 0x7FFF) + 26LL * (int)v33)
                                                          + 8));
      }
    }
    if ( v13 < 0 )
      goto LABEL_53;
    goto LABEL_37;
  }
  v14 = (_OWORD *)(v7 + 8);
  if ( !v14 )
    goto LABEL_12;
  if ( !a2 )
  {
    *v14 = 0;
LABEL_12:
    *_errno() = 22;
    _invalid_parameter_noinfo();
    goto LABEL_13;
  }
  *v14 = *a2;
LABEL_13:
  v15 = 0;
  v16 = _RTDynamicCast_0(
          g_satelliteExecutor,
          0,
          &ISatelliteExecutor `RTTI Type Descriptor',
          &CSatelliteSpeesExecutor `RTTI Type Descriptor',
          0);
  if ( v16 )
  {
    v17 = *(_QWORD *)(v16 + 2080);
    if ( v17 )
      v15 = *(_QWORD *)(v17 + 296);
  }
  v34 = v15;
  v18 = CSQLSatelliteMessageLanguageManagement::WriteResult((CSQLSatelliteMessageLanguageManagement *)&v29, a4);
  v7 = v30;
  v13 = v18;
  if ( v18 < 0 )
  {
    v9 = v34;
    v8 = HIDWORD(v33);
    goto LABEL_30;
  }
  *(_WORD *)(v30 + 2) |= 0x8000u;
  if ( (unsigned int)(v31 - v7) > HIDWORD(v32) )
  {
    v8 = -2089418750;
    HIDWORD(v33) = -2089418750;
    v13 = -2089418750;
LABEL_19:
    v9 = v34;
    goto LABEL_30;
  }
  v8 = HIDWORD(v33);
  v13 = HIDWORD(v33);
  *(_DWORD *)(v7 + 4) = v31 - v7;
  if ( v8 < 0 )
    goto LABEL_19;
  CSQLSatelliteMessage::FireXEvent(&v29, 1);
  v9 = v34;
  if ( v34 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(v34 + 8 * (26LL * (int)v33 + (*(_WORD *)(v7 + 2) & 0x7FFF)) + 8));
    v9 = v34;
    v8 = HIDWORD(v33);
  }
  v19 = *(unsigned int *)(v11 + 184);
  v7 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  LODWORD(v33) = 0;
  v20 = *(_QWORD *)(v11 + 168) + v19;
  if ( v20 )
  {
    *(_DWORD *)(v11 + 176) = *(_DWORD *)(v20 + 4);
    v13 = CSQLSatelliteConnection::WriteMessage(a3, (struct SNI_Packet *)v11);
    v11 = 0;
    if ( v13 < 0 )
      goto LABEL_30;
  }
  else
  {
    do
    {
      v21 = *(_QWORD *)(v11 + 208);
      *(_QWORD *)(v11 + 208) = 0;
      SNIPacketRelease((struct SNI_Packet *)v11);
      v11 = v21;
    }
    while ( v21 );
    v13 = 1359;
    v11 = 0;
  }
LABEL_37:
  if ( *((int *)a3 + 38) <= 0 )
    goto LABEL_53;
  _mm_lfence();
  LOBYTE(v28) = 1;
  v23 = WaitableBase::Wait((char *)a3 + 352, 0xFFFFFFFFLL, (char *)a3 + 224, 0, v28);
  if ( *((_BYTE *)a3 + 57) )
    goto LABEL_46;
  switch ( v23 )
  {
    case 0:
      goto LABEL_53;
    case 2:
LABEL_46:
      v13 = -2147467260;
      break;
    case 258:
      v13 = -2147483638;
      break;
    default:
      v13 = -2147024882;
      if ( v23 != -1073741824 )
        v13 = -2147467259;
      break;
  }
  if ( g_extensibilityErrorRingBuffer )
  {
    CurrentThreadId = GetCurrentThreadId();
    v25 = g_extensibilityErrorRingBuffer;
    v42 = CurrentThreadId;
    v40 = 0;
    v43 = "CSatelliteCargoContext::SendLanguageResults";
    v39 = 0;
    v41 = v13;
    v44 = 952;
    v46 = 0;
    v47 = 0;
    if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
      StackFrames<24>::CaptureCurrent(v45, 1);
    if ( (dword_1005113AC & 0x10) != 0 )
      ExtensibilityErrorRecord::FireMatchingEvent(&v39, v45);
    SOS_RingBuffer::StoreRecordInternalWithoutEvent(v25, &v39, v45);
  }
LABEL_53:
  if ( v11 )
  {
    do
    {
      v26 = *(_QWORD *)(v11 + 208);
      *(_QWORD *)(v11 + 208) = 0;
      SNIPacketRelease((struct SNI_Packet *)v11);
      v11 = v26;
    }
    while ( v26 );
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x100412dd0  mov     [rsp-8+arg_0], rbx
0x100412dd5  mov     [rsp-8+arg_8], rsi
0x100412dda  mov     [rsp-8+arg_10], rdi
0x100412ddf  mov     [rsp-8+arg_18], r9
0x100412de4  push    rbp
0x100412de5  push    r12
0x100412de7  push    r13
0x100412de9  push    r14
0x100412deb  push    r15
0x100412ded  lea     rbp, [rsp-0A0h]
0x100412df5  sub     rsp, 1A0h
0x100412dfc  xor     esi, esi
0x100412dfe  lea     rax, ??_7CSQLSatelliteMessageLanguageManagement@@6B@; const CSQLSatelliteMessageLanguageManagement::`vftable'
0x100412e05  mov     r13, r8
0x100412e08  mov     [rsp+1C0h+var_188], rsi
0x100412e0d  mov     r12, rdx
0x100412e10  mov     [rsp+1C0h+var_180], rsi
0x100412e15  xor     r8d, r8d
0x100412e18  mov     [rsp+1C0h+var_178], rsi
0x100412e1d  lea     edx, [rsi+1]
0x100412e20  mov     [rsp+1C0h+var_170], rsi
0x100412e25  mov     rcx, [r13+40h]
0x100412e29  mov     r14d, esi
0x100412e2c  mov     edi, esi
0x100412e2e  mov     [rsp+1C0h+var_168], rsi
0x100412e33  mov     r15d, esi
0x100412e36  mov     [rsp+1C0h+var_190], rax
0x100412e3b  mov     [rsp+1C0h+var_160], esi
0x100412e3f  mov     [rsp+1C0h+var_15C], rsi
0x100412e44  mov     [rsp+1C0h+var_154], esi
0x100412e48  mov     [rsp+1C0h+var_150], rsi
0x100412e4d  call    SNIPacketAllocateEx2
0x100412e52  mov     rbx, rax
0x100412e55  test    rax, rax
0x100412e58  jz      loc_100413073
0x100412e5e  mov     edx, [rax+0B4h]
0x100412e64  cmp     edx, 10h
0x100412e67  jnb     short loc_100412E79
0x100412e69  mov     edi, 83760002h
0x100412e6e  mov     dword ptr [rsp+1C0h+var_170+4], edi
0x100412e72  mov     esi, edi
0x100412e74  jmp     loc_100413078
0x100412e79  cmp     edx, 18h
0x100412e7c  jnb     short loc_100412E89
0x100412e7e  mov     edi, 83760002h
0x100412e83  mov     dword ptr [rsp+1C0h+var_170+4], edi
0x100412e87  jmp     short loc_100412EE1
0x100412e89  mov     r14d, [rax+0B8h]
0x100412e90  lea     rcx, [rsp+1C0h+var_190]
0x100412e95  add     r14, [rax+0A8h]
0x100412e9c  mov     dword ptr [rsp+1C0h+var_178+4], edx
0x100412ea0  mov     [rsp+1C0h+var_188], r14
0x100412ea5  mov     [rsp+1C0h+var_170], 2
0x100412eae  lea     rax, [r14+18h]
0x100412eb2  mov     [rsp+1C0h+var_180], rax
0x100412eb7  lea     eax, [rdx-18h]
0x100412eba  mov     dword ptr [rsp+1C0h+var_178], eax
0x100412ebe  mov     edx, 2
0x100412ec3  mov     eax, 1
0x100412ec8  mov     [r14], ax
0x100412ecc  mov     eax, 8018h
0x100412ed1  and     [r14+2], ax
0x100412ed6  or      word ptr [r14+2], 18h
0x100412edc  call    ?FireXEvent@CSQLSatelliteMessage@@IEAAXW4ESQLSatelliteMessage_OperationCode@@@Z; CSQLSatelliteMessage::FireXEvent(ESQLSatelliteMessage_OperationCode)
0x100412ee1  mov     esi, edi
0x100412ee3  test    edi, edi
0x100412ee5  js      loc_100413078
0x100412eeb  add     r14, 8
0x100412eef  jz      short loc_100412F08
0x100412ef1  test    r12, r12
0x100412ef4  jz      short loc_100412F01
0x100412ef6  movups  xmm0, xmmword ptr [r12]
0x100412efb  movups  xmmword ptr [r14], xmm0
0x100412eff  jmp     short loc_100412F1A
0x100412f01  xorps   xmm0, xmm0
0x100412f04  movups  xmmword ptr [r14], xmm0
0x100412f08  call    cs:__imp__errno
0x100412f0e  mov     dword ptr [rax], 16h
0x100412f14  call    cs:__imp__invalid_parameter_noinfo
0x100412f1a  mov     rcx, cs:?g_satelliteExecutor@@3PEAVISatelliteExecutor@@EA; ISatelliteExecutor * g_satelliteExecutor
0x100412f21  lea     r9, ??_R0?AVCSatelliteSpeesExecutor@@@8; CSatelliteSpeesExecutor `RTTI Type Descriptor'
0x100412f28  xor     r12d, r12d
0x100412f2b  lea     r8, ??_R0?AVISatelliteExecutor@@@8; ISatelliteExecutor `RTTI Type Descriptor'
0x100412f32  xor     edx, edx
0x100412f34  mov     [rsp+1C0h+var_1A0], r12d
0x100412f39  mov     edi, r12d
0x100412f3c  call    __RTDynamicCast_0
0x100412f41  test    rax, rax
0x100412f44  jz      short loc_100412F59
0x100412f46  mov     rax, [rax+820h]
0x100412f4d  test    rax, rax
0x100412f50  jz      short loc_100412F59
0x100412f52  mov     rdi, [rax+128h]
0x100412f59  mov     rdx, [rbp+0C0h+arg_18]; struct _SQLSatellite_LanguageError *
0x100412f60  lea     rcx, [rsp+1C0h+var_190]; this
0x100412f65  mov     [rsp+1C0h+var_168], rdi
0x100412f6a  call    ?WriteResult@CSQLSatelliteMessageLanguageManagement@@QEAAJPEAU_SQLSatellite_LanguageError@@@Z; CSQLSatelliteMessageLanguageManagement::WriteResult(_SQLSatellite_LanguageError *)
0x100412f6f  mov     r14, [rsp+1C0h+var_188]
0x100412f74  mov     esi, eax
0x100412f76  test    eax, eax
0x100412f78  js      loc_100413068
0x100412f7e  mov     eax, 8000h
0x100412f83  or      [r14+2], ax
0x100412f88  mov     eax, dword ptr [rsp+1C0h+var_180]
0x100412f8c  sub     eax, r14d
0x100412f8f  cmp     eax, dword ptr [rsp+1C0h+var_178+4]
0x100412f93  jbe     short loc_100412FAA
0x100412f95  mov     edi, 83760002h
0x100412f9a  mov     dword ptr [rsp+1C0h+var_170+4], edi
0x100412f9e  mov     esi, edi
0x100412fa0  mov     r15, [rsp+1C0h+var_168]
0x100412fa5  jmp     loc_10041307B
0x100412faa  mov     edi, dword ptr [rsp+1C0h+var_170+4]
0x100412fae  mov     esi, edi
0x100412fb0  mov     [r14+4], eax
0x100412fb4  test    edi, edi
0x100412fb6  js      short loc_100412FA0
0x100412fb8  mov     edx, 1
0x100412fbd  lea     rcx, [rsp+1C0h+var_190]
0x100412fc2  call    ?FireXEvent@CSQLSatelliteMessage@@IEAAXW4ESQLSatelliteMessage_OperationCode@@@Z; CSQLSatelliteMessage::FireXEvent(ESQLSatelliteMessage_OperationCode)
0x100412fc7  mov     r15, [rsp+1C0h+var_168]
0x100412fcc  test    r15, r15
0x100412fcf  jz      short loc_100412FF7
0x100412fd1  movzx   edx, word ptr [r14+2]
0x100412fd6  movsxd  rax, dword ptr [rsp+1C0h+var_170]
0x100412fdb  and     edx, 7FFFh
0x100412fe1  imul    rcx, rax, 1Ah
0x100412fe5  add     rdx, rcx
0x100412fe8  lock inc qword ptr [r15+rdx*8+8]
0x100412fee  mov     r15, [rsp+1C0h+var_168]
0x100412ff3  mov     edi, dword ptr [rsp+1C0h+var_170+4]
0x100412ff7  mov     eax, [rbx+0B8h]
0x100412ffd  mov     r14, r12
0x100413000  mov     [rsp+1C0h+var_188], r12
0x100413005  mov     [rsp+1C0h+var_180], r12
0x10041300a  mov     [rsp+1C0h+var_178], r12
0x10041300f  mov     dword ptr [rsp+1C0h+var_170], r12d
0x100413014  add     rax, [rbx+0A8h]
0x10041301b  jz      short loc_100413040
0x10041301d  mov     eax, [rax+4]
0x100413020  mov     rdx, rbx; struct SNI_Packet *
0x100413023  mov     rcx, r13; this
0x100413026  mov     [rbx+0B0h], eax
0x10041302c  call    ?WriteMessage@CSQLSatelliteConnection@@QEAAKPEAVSNI_Packet@@@Z; CSQLSatelliteConnection::WriteMessage(SNI_Packet *)
0x100413031  mov     esi, eax
0x100413033  mov     rbx, r12
0x100413036  test    eax, eax
0x100413038  jns     loc_1004130D1
0x10041303e  jmp     short loc_10041307B
0x100413040  mov     rdi, [rbx+0D0h]
0x100413047  mov     rcx, rbx; struct SNI_Packet *
0x10041304a  mov     [rbx+0D0h], r12
0x100413051  call    SNIPacketRelease
0x100413056  mov     rbx, rdi
0x100413059  test    rdi, rdi
0x10041305c  jnz     short loc_100413040
0x10041305e  mov     esi, 54Fh
0x100413063  mov     rbx, r12
0x100413066  jmp     short loc_1004130D1
0x100413068  mov     r15, [rsp+1C0h+var_168]
0x10041306d  mov     edi, dword ptr [rsp+1C0h+var_170+4]
0x100413071  jmp     short loc_10041307B
0x100413073  mov     esi, 8007000Eh
0x100413078  xor     r12d, r12d
0x10041307b  mov     edx, 1
0x100413080  lea     rcx, [rsp+1C0h+var_190]
0x100413085  call    ?FireXEvent@CSQLSatelliteMessage@@IEAAXW4ESQLSatelliteMessage_OperationCode@@@Z; CSQLSatelliteMessage::FireXEvent(ESQLSatelliteMessage_OperationCode)
0x10041308a  test    r15, r15
0x10041308d  jz      short loc_1004130C9
0x10041308f  movzx   edx, word ptr [r14+2]
0x100413094  and     edx, 7FFFh
0x10041309a  test    edi, edi
0x10041309c  js      short loc_1004130B4
0x10041309e  movsxd  rax, dword ptr [rsp+1C0h+var_170]
0x1004130a3  imul    rcx, rax, 1Ah
0x1004130a7  mov     eax, edx
0x1004130a9  add     rcx, rax
0x1004130ac  lock inc qword ptr [r15+rcx*8+8]
0x1004130b2  jmp     short loc_1004130C9
0x1004130b4  cmp     edx, 1Ah
0x1004130b7  jnb     short loc_1004130C4
0x1004130b9  lfence
0x1004130bc  lock inc qword ptr [r15+rdx*8+8]
0x1004130c2  jmp     short loc_1004130C9
0x1004130c4  lock inc qword ptr [r15+8]
0x1004130c9  test    esi, esi
0x1004130cb  js      loc_1004131C4
0x1004130d1  mov     eax, [r13+98h]
0x1004130d8  test    eax, eax
0x1004130da  jle     loc_1004131C4
0x1004130e0  lfence
0x1004130e3  lea     r8, [r13+0E0h]
0x1004130ea  mov     byte ptr [rsp+1C0h+var_1A0], 1
0x1004130ef  lea     rcx, [r13+160h]
0x1004130f6  xor     r9d, r9d
0x1004130f9  mov     edx, 0FFFFFFFFh
0x1004130fe  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100413104  movzx   ecx, byte ptr [r13+39h]
0x100413109  test    cl, cl
0x10041310b  jnz     short loc_10041313C
0x10041310d  test    eax, eax
0x10041310f  jz      loc_1004131C4
0x100413115  cmp     eax, 2
0x100413118  jz      short loc_10041313C
0x10041311a  cmp     eax, 102h
0x10041311f  jz      short loc_100413135
0x100413121  cmp     eax, 0C0000000h
0x100413126  mov     esi, 8007000Eh
0x10041312b  mov     ecx, 80004005h
0x100413130  cmovnz  esi, ecx
0x100413133  jmp     short loc_100413141
0x100413135  mov     esi, 8000000Ah
0x10041313a  jmp     short loc_100413141
0x10041313c  mov     esi, 80004004h
0x100413141  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100413149  jz      short loc_1004131C4
0x10041314b  call    cs:__imp_GetCurrentThreadId
0x100413151  mov     rdi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100413158  xor     ecx, ecx
0x10041315a  mov     [rbp+0C0h+var_124], eax
0x10041315d  xorps   xmm0, xmm0
0x100413160  lea     rax, aCsatellitecarg_2; "CSatelliteCargoContext::SendLanguageRes"...
0x100413167  mov     [rbp+0C0h+var_130], rcx
0x10041316b  mov     [rbp+0C0h+var_120], rax
0x10041316f  movups  [rbp+0C0h+var_140], xmm0
0x100413173  mov     [rbp+0C0h+var_128], esi
0x100413176  mov     [rbp+0C0h+var_118], 3B8h
0x10041317d  mov     [rbp+0C0h+var_38], r12d
0x100413184  mov     [rbp+0C0h+var_30], r12
0x10041318b  cmp     [rdi+40h], rcx
0x10041318f  jz      short loc_10041319D
0x100413191  lea     edx, [rcx+1]
0x100413194  lea     rcx, [rbp+0C0h+var_110]
0x100413198  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x10041319d  test    byte ptr cs:dword_1005113AC, 10h
0x1004131a4  jz      short loc_1004131B3
0x1004131a6  lea     rdx, [rbp+0C0h+var_110]
0x1004131aa  lea     rcx, [rbp+0C0h+var_140]
0x1004131ae  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x1004131b3  lea     r8, [rbp+0C0h+var_110]
0x1004131b7  mov     rcx, rdi
0x1004131ba  lea     rdx, [rbp+0C0h+var_140]
0x1004131be  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004131c4  test    rbx, rbx
0x1004131c7  jz      short loc_1004131EE
0x1004131c9  nop     dword ptr [rax+00000000h]
0x1004131d0  mov     rdi, [rbx+0D0h]
0x1004131d7  mov     rcx, rbx; struct SNI_Packet *
0x1004131da  mov     [rbx+0D0h], r12
0x1004131e1  call    SNIPacketRelease
0x1004131e6  mov     rbx, rdi
0x1004131e9  test    rdi, rdi
0x1004131ec  jnz     short loc_1004131D0
0x1004131ee  lea     r11, [rsp+1C0h+var_20]
0x1004131f6  mov     eax, esi
0x1004131f8  mov     rbx, [r11+30h]
0x1004131fc  mov     rsi, [r11+38h]
0x100413200  mov     rdi, [r11+40h]
0x100413204  mov     rsp, r11
0x100413207  pop     r15
0x100413209  pop     r14
0x10041320b  pop     r13
0x10041320d  pop     r12
0x10041320f  pop     rbp
0x100413210  retn
```
