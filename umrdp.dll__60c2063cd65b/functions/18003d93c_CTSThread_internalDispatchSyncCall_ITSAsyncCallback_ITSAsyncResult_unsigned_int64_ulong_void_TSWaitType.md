# CTSThread::internalDispatchSyncCall(ITSAsyncCallback *,ITSAsyncResult *,unsigned __int64,ulong,void *,TSWaitType)

- ea: `0x18003d93c`
- end: `0x18003ddbe`
- name: `?internalDispatchSyncCall@CTSThread@@IEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@_KKPEAXW4TSWaitType@@@Z`
- size: `1154`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003a920`
- `0x18003a950`
- `0x18003a980`

## callees

- `0x1800010b0`
- `0x1800011c8`
- `0x180001738`
- `0x18000a118`
- `0x18000abc0`
- `0x18000b98c`
- `0x18001b70c`
- `0x18001b72c`
- `0x18001bae0`
- `0x18002c600`
- `0x180038cf0`
- `0x18003add0`
- `0x18003d93c`
- `0x18003f158`
- `0x18003f700`
- `0x18003fa50`
- `0x180049010`

## string_xrefs

- `0x18003da06`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003dcc1`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003dab5`: `CreateInstance failed for CTSBufferResult!`
- `0x18003da18`: `No current thread, can't dispatch call`
- `0x18003dc71`: `Sync wait completed ok for pAsyncCallback: 0x%p`
- `0x18003dcd3`: `WaitForCompletion timeout: 0x%x`
- `0x18003dd50`: `Failed to add callback to thread!`

## pseudocode

```c
__int64 __fastcall CTSThread::internalDispatchSyncCall(
        _QWORD *a1,
        struct ITSAsyncCallback *a2,
        struct ITSAsyncResult *a3,
        unsigned __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7)
{
  CTSSyncWaitResult *v7; // r14
  struct ITSAsyncResult *v8; // rbx
  __int64 v9; // rdi
  struct ITSAsyncCallback *v11; // r12
  CTSReaderWriterLock *v13; // r13
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r12
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // r9
  int PooledObject; // esi
  __int64 v22; // rcx
  int ActivityIdPrefix; // eax
  __int64 v24; // rsi
  int v25; // eax
  int v26; // eax
  int v27; // edx
  const char *v28; // rcx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v33; // [rsp+58h] [rbp-31h] BYREF
  CTSSyncWaitResult *v34; // [rsp+60h] [rbp-29h] BYREF
  __int64 v35; // [rsp+68h] [rbp-21h] BYREF
  __int64 v36; // [rsp+70h] [rbp-19h] BYREF
  const char *v37; // [rsp+78h] [rbp-11h] BYREF
  const char *v38; // [rsp+80h] [rbp-9h] BYREF
  const char *v39; // [rsp+88h] [rbp-1h] BYREF
  struct ITSAsyncCallback *v40; // [rsp+D8h] [rbp+4Fh] BYREF
  struct ITSAsyncCallback *v41; // [rsp+E0h] [rbp+57h]
  unsigned __int64 v42; // [rsp+F0h] [rbp+67h]

  v42 = a4;
  v41 = a2;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v34 = 0;
  v36 = 0;
  v11 = a2;
  v35 = 0;
  v13 = (CTSReaderWriterLock *)((char *)a1 + 148);
  CTSReaderWriterLock::ReadLock((CTSReaderWriterLock *)((char *)a1 + 148));
  v16 = a1[24];
  if ( v16 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v14, v15, 0);
    if ( v17 )
    {
      TCntPtr<IDispatch>::SafeRelease(&v36);
      v36 = v17;
      v9 = v17;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v36);
    }
    v11 = v41;
  }
  CTSReaderWriterLock::ReadUnlock(v13);
  if ( !v20 )
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      LODWORD(v40) = 3057;
      v34 = (CTSSyncWaitResult *)"internalDispatchSyncCall";
      v33 = -2147467259;
      v37 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v38 = "No current thread, can't dispatch call";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)qword_180054EE0,
        v19,
        0,
        (__int64)&v38,
        (__int64)&v33,
        (__int64)&v37,
        (__int64)&v40,
        (__int64)&v34);
    }
    PooledObject = -2092630002;
    goto LABEL_46;
  }
  if ( a6 && a5 )
  {
    v22 = a1[84];
    v40 = 0;
    PooledObject = CTSBufferResult::CreateInstance(v22, a5, a6, &v40);
    if ( PooledObject < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          142,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"CreateInstance failed for CTSBufferResult!",
          PooledObject);
      }
      TCntPtr<CTSBufferResult>::SafeRelease(&v40);
      goto LABEL_46;
    }
    v24 = ((unsigned __int64)v40 + 80) & -(__int64)(v40 != 0);
    if ( v24 )
    {
      TCntPtr<IDispatch>::SafeRelease(&v35);
      v8 = (struct ITSAsyncResult *)v24;
      v35 = v24;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v35);
    }
    TCntPtr<CTSBufferResult>::SafeRelease(&v40);
  }
  else if ( a3 )
  {
    TCntPtr<IDispatch>::SafeRelease(&v35);
    v8 = a3;
    v35 = (__int64)a3;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v35);
  }
  PooledObject = CTSObjectPool<CTSSyncWaitResult>::GetPooledObject(a1[82], &v34);
  if ( PooledObject < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v25 = RdpX_GetActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        143,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        v25,
        (__int64)"Unable to get a SyncWaitResult from pool!",
        PooledObject);
    }
    v7 = v34;
    goto LABEL_46;
  }
  v7 = v34;
  PooledObject = CTSSyncWaitResult::InitializeForReuse(v34, v8);
  if ( PooledObject < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_46;
    }
    v26 = RdpX_GetActivityIdPrefix();
    v27 = 144;
    v28 = "InitializeForReuse failed!";
    goto LABEL_45;
  }
  PooledObject = CTSThread::AddCallback(
                   (CTSThread *)a1,
                   v11,
                   (struct ITSAsyncResult *)(((unsigned __int64)v7 + 80) & -(__int64)(v7 != 0)),
                   0,
                   v42,
                   1u,
                   0,
                   0);
  if ( PooledObject < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_46;
    }
    v26 = RdpX_GetActivityIdPrefix();
    v27 = 145;
    v28 = "Failed to add callback to thread!";
LABEL_45:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v27,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      v26,
      (__int64)v28,
      PooledObject);
    goto LABEL_46;
  }
  v29 = CTSSyncWaitResult::WaitForCompletion((__int64)v7, a7, v9);
  if ( v29 < 0 )
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      LODWORD(v40) = v29;
      v38 = "internalDispatchSyncCall";
      v33 = 3121;
      v37 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v39 = "WaitForCompletion timeout: 0x%x";
      LODWORD(v34) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v29,
        (unsigned int)&word_180054E66,
        v30,
        v31,
        (__int64)&v39,
        (__int64)&v34,
        (__int64)&v37,
        (__int64)&v33,
        (__int64)&v38,
        (__int64)&v40);
    }
    PooledObject = -2092630013;
  }
  else
  {
    if ( (unsigned int)dword_18005C008 > 5 )
    {
      v40 = v11;
      v38 = "Sync wait completed ok for pAsyncCallback: 0x%p";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v29,
        (unsigned int)&byte_180054EAF,
        v30,
        v31,
        (__int64)&v38,
        (__int64)&v40);
    }
    PooledObject = *((_DWORD *)v7 + 24);
  }
LABEL_46:
  TCntPtr<IDispatch>::SafeRelease(&v36);
  TCntPtr<IDispatch>::SafeRelease(&v35);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 4) + 16LL))(*((_QWORD *)v7 + 4));
  return (unsigned int)PooledObject;
}

```

## disassembly

```asm
0x18003d93c  mov     rax, rsp
0x18003d93f  mov     [rax+18h], rbx
0x18003d943  mov     [rax+20h], r9
0x18003d947  mov     [rax+10h], rdx
0x18003d94b  push    rbp
0x18003d94c  push    rsi
0x18003d94d  push    rdi
0x18003d94e  push    r12
0x18003d950  push    r13
0x18003d952  push    r14
0x18003d954  push    r15
0x18003d956  lea     rbp, [rax-47h]
0x18003d95a  sub     rsp, 90h
0x18003d961  xor     r14d, r14d
0x18003d964  xor     ebx, ebx
0x18003d966  xor     edi, edi
0x18003d968  mov     [rbp+3Fh+var_68], r14
0x18003d96c  mov     [rbp+3Fh+var_58], rdi
0x18003d970  mov     rsi, r8
0x18003d973  mov     r12, rdx
0x18003d976  mov     [rbp+3Fh+var_60], rbx
0x18003d97a  mov     r15, rcx
0x18003d97d  lea     r13, [rcx+94h]
0x18003d984  mov     rcx, r13; this
0x18003d987  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x18003d98c  mov     rcx, [r15+0C0h]
0x18003d993  xor     r9d, r9d
0x18003d996  test    rcx, rcx
0x18003d999  jz      short loc_18003D9D2
0x18003d99b  mov     rax, [rcx]
0x18003d99e  mov     rax, [rax+40h]
0x18003d9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9a7  xor     r9d, r9d
0x18003d9aa  mov     r12, rax
0x18003d9ad  test    rax, rax
0x18003d9b0  jz      short loc_18003D9CE
0x18003d9b2  lea     rcx, [rbp+3Fh+var_58]
0x18003d9b6  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18003d9bb  lea     rcx, [rbp+3Fh+var_58]
0x18003d9bf  mov     [rbp+3Fh+var_58], r12
0x18003d9c3  mov     rdi, r12
0x18003d9c6  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18003d9cb  mov     r9, r12
0x18003d9ce  mov     r12, [rbp+3Fh+arg_8]
0x18003d9d2  mov     rcx, r13; this
0x18003d9d5  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x18003d9da  xor     r13d, r13d
0x18003d9dd  test    r9, r9
0x18003d9e0  jnz     short loc_18003DA5F
0x18003d9e2  mov     eax, cs:dword_18005C008
0x18003d9e8  cmp     eax, 2
0x18003d9eb  jbe     short loc_18003DA55
0x18003d9ed  lea     rax, aInternaldispat; "internalDispatchSyncCall"
0x18003d9f4  mov     dword ptr [rbp+3Fh+arg_0], 0BF1h
0x18003d9fb  mov     [rbp+3Fh+var_68], rax
0x18003d9ff  lea     rdx, qword_180054EE0
0x18003da06  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003da0d  mov     [rbp+3Fh+var_70], 80004005h
0x18003da14  mov     [rbp+3Fh+var_50], rax
0x18003da18  lea     rax, aNoCurrentThrea; "No current thread, can't dispatch call"
0x18003da1f  mov     [rbp+3Fh+var_48], rax
0x18003da23  lea     rax, [rbp+3Fh+var_68]
0x18003da27  mov     [rsp+0C0h+var_80], rax
0x18003da2c  lea     rax, [rbp+3Fh+arg_0]
0x18003da30  mov     qword ptr [rsp+0C0h+var_88], rax
0x18003da35  lea     rax, [rbp+3Fh+var_50]
0x18003da39  mov     [rsp+0C0h+var_90], rax
0x18003da3e  lea     rax, [rbp+3Fh+var_70]
0x18003da42  mov     qword ptr [rsp+0C0h+var_98], rax
0x18003da47  lea     rax, [rbp+3Fh+var_48]
0x18003da4b  mov     [rsp+0C0h+var_A0], rax
0x18003da50  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003da55  mov     esi, 8345000Eh
0x18003da5a  jmp     loc_18003DD7A
0x18003da5f  mov     r8, [rbp+3Fh+arg_28]
0x18003da63  test    r8, r8
0x18003da66  jz      loc_18003DB29
0x18003da6c  mov     edx, [rbp+3Fh+arg_20]
0x18003da6f  test    edx, edx
0x18003da71  jz      loc_18003DB29
0x18003da77  mov     rcx, [r15+2A0h]
0x18003da7e  lea     r9, [rbp+3Fh+arg_0]
0x18003da82  mov     [rbp+3Fh+arg_0], r13
0x18003da86  call    ?CreateInstance@CTSBufferResult@@SAJPEAV?$CTSObjectPool@VCTSBufferResult@@@@KPEAXPEAPEAV1@@Z; CTSBufferResult::CreateInstance(CTSObjectPool<CTSBufferResult> *,ulong,void *,CTSBufferResult * *)
0x18003da8b  mov     esi, eax
0x18003da8d  test    eax, eax
0x18003da8f  jns     short loc_18003DAF2
0x18003da91  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da98  lea     rax, WPP_GLOBAL_Control
0x18003da9f  cmp     rcx, rax
0x18003daa2  jz      short loc_18003DAE4
0x18003daa4  test    byte ptr [rcx+1Ch], 8
0x18003daa8  jz      short loc_18003DAE4
0x18003daaa  cmp     byte ptr [rcx+19h], 2
0x18003daae  jb      short loc_18003DAE4
0x18003dab0  call    RdpX_GetActivityIdPrefix
0x18003dab5  lea     rcx, aCreateinstance; "CreateInstance failed for CTSBufferResu"...
0x18003dabc  mov     [rsp+0C0h+var_98], esi
0x18003dac0  mov     [rsp+0C0h+var_A0], rcx
0x18003dac5  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003dacc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dad3  mov     edx, 8Eh
0x18003dad8  mov     r9d, eax
0x18003dadb  mov     rcx, [rcx+10h]
0x18003dadf  call    WPP_SF_DsD
0x18003dae4  lea     rcx, [rbp+3Fh+arg_0]
0x18003dae8  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x18003daed  jmp     loc_18003DD7A
0x18003daf2  mov     rax, [rbp+3Fh+arg_0]
0x18003daf6  lea     rcx, [rax+50h]
0x18003dafa  neg     rax
0x18003dafd  sbb     rsi, rsi
0x18003db00  and     rsi, rcx
0x18003db03  jz      short loc_18003DB1E
0x18003db05  lea     rcx, [rbp+3Fh+var_60]
0x18003db09  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18003db0e  mov     rbx, rsi
0x18003db11  lea     rcx, [rbp+3Fh+var_60]
0x18003db15  mov     [rbp+3Fh+var_60], rbx
0x18003db19  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18003db1e  lea     rcx, [rbp+3Fh+arg_0]
0x18003db22  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x18003db27  jmp     short loc_18003DB47
0x18003db29  test    rsi, rsi
0x18003db2c  jz      short loc_18003DB47
0x18003db2e  lea     rcx, [rbp+3Fh+var_60]
0x18003db32  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18003db37  mov     rbx, rsi
0x18003db3a  lea     rcx, [rbp+3Fh+var_60]
0x18003db3e  mov     [rbp+3Fh+var_60], rbx
0x18003db42  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18003db47  mov     rcx, [r15+290h]
0x18003db4e  lea     rdx, [rbp+3Fh+var_68]
0x18003db52  call    ?GetPooledObject@?$CTSObjectPool@VCTSSyncWaitResult@@@@QEAAJPEAPEAVCTSSyncWaitResult@@H@Z; CTSObjectPool<CTSSyncWaitResult>::GetPooledObject(CTSSyncWaitResult * *,int)
0x18003db57  mov     esi, eax
0x18003db59  test    eax, eax
0x18003db5b  jns     short loc_18003DBB9
0x18003db5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db64  lea     rax, WPP_GLOBAL_Control
0x18003db6b  cmp     rcx, rax
0x18003db6e  jz      short loc_18003DBB0
0x18003db70  test    byte ptr [rcx+1Ch], 8
0x18003db74  jz      short loc_18003DBB0
0x18003db76  cmp     byte ptr [rcx+19h], 2
0x18003db7a  jb      short loc_18003DBB0
0x18003db7c  call    RdpX_GetActivityIdPrefix
0x18003db81  lea     rcx, aUnableToGetASy; "Unable to get a SyncWaitResult from poo"...
0x18003db88  mov     [rsp+0C0h+var_98], esi
0x18003db8c  mov     [rsp+0C0h+var_A0], rcx
0x18003db91  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003db98  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db9f  mov     edx, 8Fh
0x18003dba4  mov     r9d, eax
0x18003dba7  mov     rcx, [rcx+10h]
0x18003dbab  call    WPP_SF_DsD
0x18003dbb0  mov     r14, [rbp+3Fh+var_68]
0x18003dbb4  jmp     loc_18003DD7A
0x18003dbb9  mov     r14, [rbp+3Fh+var_68]
0x18003dbbd  mov     rdx, rbx; struct ITSAsyncResult *
0x18003dbc0  mov     rcx, r14; this
0x18003dbc3  call    ?InitializeForReuse@CTSSyncWaitResult@@QEAAJPEAVITSAsyncResult@@@Z; CTSSyncWaitResult::InitializeForReuse(ITSAsyncResult *)
0x18003dbc8  mov     esi, eax
0x18003dbca  test    eax, eax
0x18003dbcc  jns     short loc_18003DC0F
0x18003dbce  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dbd5  lea     rax, WPP_GLOBAL_Control
0x18003dbdc  cmp     rcx, rax
0x18003dbdf  jz      loc_18003DD7A
0x18003dbe5  test    byte ptr [rcx+1Ch], 8
0x18003dbe9  jz      loc_18003DD7A
0x18003dbef  cmp     byte ptr [rcx+19h], 2
0x18003dbf3  jb      loc_18003DD7A
0x18003dbf9  call    RdpX_GetActivityIdPrefix
0x18003dbfe  mov     edx, 90h
0x18003dc03  lea     rcx, aInitializeforr; "InitializeForReuse failed!"
0x18003dc0a  jmp     loc_18003DD57
0x18003dc0f  mov     [rsp+0C0h+var_88], r13d; unsigned int
0x18003dc14  lea     rcx, [r14+50h]
0x18003dc18  mov     [rsp+0C0h+var_90], r13; struct ITSQueuedCallback **
0x18003dc1d  mov     rax, r14
0x18003dc20  neg     rax
0x18003dc23  mov     [rsp+0C0h+var_98], 1; unsigned int
0x18003dc2b  mov     rax, [rbp+3Fh+arg_18]
0x18003dc2f  mov     rdx, r12; struct ITSAsyncCallback *
0x18003dc32  sbb     r8, r8
0x18003dc35  mov     [rsp+0C0h+var_A0], rax; unsigned __int64
0x18003dc3a  and     r8, rcx; struct ITSAsyncResult *
0x18003dc3d  xor     r9d, r9d; unsigned int
0x18003dc40  mov     rcx, r15; this
0x18003dc43  call    ?AddCallback@CTSThread@@UEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@K_KKPEAPEAVITSQueuedCallback@@I@Z; CTSThread::AddCallback(ITSAsyncCallback *,ITSAsyncResult *,ulong,unsigned __int64,ulong,ITSQueuedCallback * *,uint)
0x18003dc48  mov     esi, eax
0x18003dc4a  test    eax, eax
0x18003dc4c  js      loc_18003DD27
0x18003dc52  mov     edx, [rbp+3Fh+arg_30]
0x18003dc55  mov     r8, rdi
0x18003dc58  mov     rcx, r14
0x18003dc5b  call    ?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z; CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)
0x18003dc60  mov     ecx, eax
0x18003dc62  test    eax, eax
0x18003dc64  mov     eax, cs:dword_18005C008
0x18003dc6a  js      short loc_18003DCA7
0x18003dc6c  cmp     eax, 5
0x18003dc6f  jbe     short loc_18003DC9E
0x18003dc71  lea     rax, aSyncWaitComple; "Sync wait completed ok for pAsyncCallba"...
0x18003dc78  mov     [rbp+3Fh+arg_0], r12
0x18003dc7c  mov     [rbp+3Fh+var_48], rax
0x18003dc80  lea     rdx, byte_180054EAF
0x18003dc87  lea     rax, [rbp+3Fh+arg_0]
0x18003dc8b  mov     qword ptr [rsp+0C0h+var_98], rax
0x18003dc90  lea     rax, [rbp+3Fh+var_48]
0x18003dc94  mov     [rsp+0C0h+var_A0], rax
0x18003dc99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18003dc9e  mov     esi, [r14+60h]
0x18003dca2  jmp     loc_18003DD7A
0x18003dca7  cmp     eax, 2
0x18003dcaa  jbe     short loc_18003DD20
0x18003dcac  lea     rax, aInternaldispat; "internalDispatchSyncCall"
0x18003dcb3  mov     dword ptr [rbp+3Fh+arg_0], ecx
0x18003dcb6  mov     [rbp+3Fh+var_48], rax
0x18003dcba  lea     rdx, word_180054E66
0x18003dcc1  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003dcc8  mov     [rbp+3Fh+var_70], 0C31h
0x18003dccf  mov     [rbp+3Fh+var_50], rax
0x18003dcd3  lea     rax, aWaitforcomplet; "WaitForCompletion timeout: 0x%x"
0x18003dcda  mov     [rbp+3Fh+var_40], rax
0x18003dcde  lea     rax, [rbp+3Fh+arg_0]
0x18003dce2  mov     [rsp+48h], rax
0x18003dce7  lea     rax, [rbp+3Fh+var_48]
0x18003dceb  mov     [rsp+0C0h+var_80], rax
0x18003dcf0  lea     rax, [rbp+3Fh+var_70]
0x18003dcf4  mov     qword ptr [rsp+0C0h+var_88], rax
0x18003dcf9  lea     rax, [rbp+3Fh+var_50]
0x18003dcfd  mov     [rsp+0C0h+var_90], rax
0x18003dd02  lea     rax, [rbp+3Fh+var_68]
0x18003dd06  mov     qword ptr [rsp+0C0h+var_98], rax
0x18003dd0b  lea     rax, [rbp+3Fh+var_40]
0x18003dd0f  mov     [rsp+0C0h+var_A0], rax
0x18003dd14  mov     dword ptr [rbp+3Fh+var_68], 80004005h
0x18003dd1b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003dd20  mov     esi, 83450003h
0x18003dd25  jmp     short loc_18003DD7A
0x18003dd27  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd2e  lea     rax, WPP_GLOBAL_Control
0x18003dd35  cmp     rcx, rax
0x18003dd38  jz      short loc_18003DD7A
0x18003dd3a  test    byte ptr [rcx+1Ch], 8
0x18003dd3e  jz      short loc_18003DD7A
0x18003dd40  cmp     byte ptr [rcx+19h], 2
0x18003dd44  jb      short loc_18003DD7A
0x18003dd46  call    RdpX_GetActivityIdPrefix
0x18003dd4b  mov     edx, 91h
0x18003dd50  lea     rcx, aFailedToAddCal; "Failed to add callback to thread!"
0x18003dd57  mov     [rsp+0C0h+var_98], esi
0x18003dd5b  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003dd62  mov     [rsp+0C0h+var_A0], rcx
0x18003dd67  mov     r9d, eax
0x18003dd6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd71  mov     rcx, [rcx+10h]
0x18003dd75  call    WPP_SF_DsD
0x18003dd7a  lea     rcx, [rbp+3Fh+var_58]
0x18003dd7e  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18003dd83  lea     rcx, [rbp+3Fh+var_60]
0x18003dd87  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18003dd8c  test    r14, r14
0x18003dd8f  jz      short loc_18003DDA1
0x18003dd91  mov     rcx, [r14+20h]
0x18003dd95  mov     rax, [rcx]
0x18003dd98  mov     rax, [rax+10h]
0x18003dd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dda1  mov     rbx, [rsp+0C0h+arg_10]
0x18003dda9  mov     eax, esi
0x18003ddab  add     rsp, 90h
0x18003ddb2  pop     r15
0x18003ddb4  pop     r14
0x18003ddb6  pop     r13
0x18003ddb8  pop     r12
0x18003ddba  pop     rdi
0x18003ddbb  pop     rsi
0x18003ddbc  pop     rbp
0x18003ddbd  retn
```
