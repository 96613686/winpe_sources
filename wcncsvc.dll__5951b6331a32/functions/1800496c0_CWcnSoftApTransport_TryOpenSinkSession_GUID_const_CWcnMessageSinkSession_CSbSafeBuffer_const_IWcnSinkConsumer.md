# CWcnSoftApTransport::TryOpenSinkSession(_GUID const *,CWcnMessageSinkSession *,CSbSafeBuffer const *,IWcnSinkConsumer * *)

- ea: `0x1800496c0`
- end: `0x180049d85`
- name: `?TryOpenSinkSession@CWcnSoftApTransport@@UEAAJPEBU_GUID@@PEAVCWcnMessageSinkSession@@PEBVCSbSafeBuffer@@PEAPEAVIWcnSinkConsumer@@@Z`
- size: `1733`
- prototype: `int(CWcnSoftApTransport *__hidden this, const struct _GUID *, struct CWcnMessageSinkSession *, const struct CSbSafeBuffer *, struct IWcnSinkConsumer **)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000862c`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000a6d4`
- `0x18000a808`
- `0x18000ebe0`
- `0x1800149ec`
- `0x180016994`
- `0x180017424`
- `0x180018204`
- `0x18001a57c`
- `0x18001b548`
- `0x18001cdd0`
- `0x18001d1e8`
- `0x18001de78`
- `0x1800496c0`
- `0x18004a7a8`
- `0x180053004`
- `0x180056dcf`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800499e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800499e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049964`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049964`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049872`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049a8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049872`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049a8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049954`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049a7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049aca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049954`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049a7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049aca`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWcnSoftApTransport::TryOpenSinkSession(
        CWcnSoftApTransport *this,
        struct _GUID *a2,
        struct CWcnMessageSinkSession *a3,
        const struct CSbSafeBuffer *a4,
        struct IWcnSinkConsumer **a5)
{
  struct CWcnMessageSinkSession *v6; // rax
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  const char *v13; // r9
  _QWORD *v15; // rcx
  __int64 v16; // rsi
  int v17; // eax
  int appended; // ebx
  _BYTE *v19; // r10
  CWcnSession *v20; // rdi
  struct _RTL_CRITICAL_SECTION *v21; // rsi
  CWcnPeer *v22; // r15
  __int64 v23; // r14
  CWcnPeer *v24; // rax
  unsigned int v25; // eax
  __int64 v26; // r10
  CWcnSoftApSession *v27; // rsi
  CWcnPeer *v28; // rax
  __int64 v29; // rdx
  const char *v30; // r9
  __int64 v31; // rdx
  const char *v32; // rax
  unsigned int v33; // eax
  __int64 v34; // r10
  unsigned int v35; // eax
  __int64 v36; // r10
  char v37; // r11
  CWcnPeer *v38; // [rsp+30h] [rbp-81h] BYREF
  struct CWcnMessageSinkSession *v39; // [rsp+38h] [rbp-79h]
  unsigned __int8 v40[32]; // [rsp+40h] [rbp-71h] BYREF
  unsigned __int8 v41[8]; // [rsp+60h] [rbp-51h] BYREF
  int v42; // [rsp+68h] [rbp-49h]
  _BYTE v43[24]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v44[40]; // [rsp+88h] [rbp-29h] BYREF

  v6 = a3;
  v39 = a3;
  v38 = 0;
  *(_QWORD *)v41 = 0;
  v42 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 25, WPP_cc1b862995d736ae8005150cb471f877_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
    v6 = v39;
  }
  if ( !a2 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 26;
    v13 = "pSinkSessionGuid";
LABEL_20:
    WPP_SF_s(*((_QWORD *)v9 + 2), v12, WPP_cc1b862995d736ae8005150cb471f877_Traceguids, v13);
    return 2147500035LL;
  }
  if ( !v6 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 27;
    v13 = "pSinkSession";
    goto LABEL_20;
  }
  if ( !a4 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 28;
    v13 = "pTransportExtra";
    goto LABEL_20;
  }
  if ( !a5 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 29;
    v13 = "ppSinkConsumer";
    goto LABEL_20;
  }
  *a5 = 0;
  v15 = (_QWORD *)*((_QWORD *)a4 + 3);
  if ( v15 && v15[1] - *v15 == 12 )
  {
    v16 = *((_QWORD *)g_pWcnService + 7);
    v17 = CSbSafeBuffer::CopyToBuffer(a4, v41, 0xCu);
    appended = v17;
    if ( v17 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_83:
          if ( v19 != (_BYTE *)&WPP_GLOBAL_Control && (appended < 0 || v19[25] >= 6u) )
          {
            v33 = (unsigned int)GetIndent(-1);
            WPP_SF_sd(
              *(_QWORD *)(v34 + 16),
              40,
              (unsigned int)WPP_cc1b862995d736ae8005150cb471f877_Traceguids,
              v33,
              appended);
          }
          return (unsigned int)appended;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_cc1b862995d736ae8005150cb471f877_Traceguids,
          (unsigned int)v17);
LABEL_28:
        v19 = WPP_GLOBAL_Control;
        goto LABEL_83;
      }
      return (unsigned int)appended;
    }
    v20 = 0;
    v21 = (struct _RTL_CRITICAL_SECTION *)(v16 + 192);
    EnterCriticalSection(v21);
    appended = CWcnPeerCache::GetOrCreatePeer((__int64)v21, a2, &v38);
    v22 = v38;
    if ( appended < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_cc1b862995d736ae8005150cb471f877_Traceguids,
          (unsigned int)appended);
LABEL_46:
      LeaveCriticalSection(v21);
      goto LABEL_78;
    }
    v23 = _RTDynamicCast_0(
            *((_QWORD *)v38 + *((unsigned int *)this - 2) + 7),
            0,
            &IWcnTransportPeer `RTTI Type Descriptor',
            &CWcnSoftApPeer `RTTI Type Descriptor',
            0);
    if ( !v23 )
    {
      v24 = (CWcnPeer *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      v23 = (__int64)v24;
      v38 = v24;
      if ( !v24 )
      {
        appended = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_cc1b862995d736ae8005150cb471f877_Traceguids,
            "pNewSoftApPeer");
        goto LABEL_46;
      }
      *((_BYTE *)v24 + 8) = 0;
      *(_QWORD *)v24 = &CWcnSoftApPeer::`vftable';
      *((_QWORD *)v24 + 5) = 0;
      *((_QWORD *)v24 + 5) = (char *)this - 16;
      CWcnPeer::SetTransportData(v22, *((_DWORD *)this - 2), v24);
      *(_BYTE *)(v23 + 8) = 1;
    }
    LeaveCriticalSection(v21);
    AcquireSRWLockExclusive((PSRWLOCK)v22 + 21);
    CWcnAttribute::CWcnAttribute((CWcnAttribute *)v43);
    CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v40);
    appended = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)v40, &v41[4], 6u);
    if ( appended >= 0 )
    {
      appended = CWcnAttribute::SetValueFromBlob(
                   (CWcnAttribute *)v43,
                   WCN_TYPE_DOT11_MAC_ADDRESS,
                   (const struct CSbSafeBuffer *)v40);
      if ( appended >= 0 )
      {
        CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnPeer *)((char *)v22 + 176), WCN_TYPE_DOT11_MAC_ADDRESS);
        appended = CWcnAttributeDatabase::AppendAttribute(
                     (CWcnPeer *)((char *)v22 + 176),
                     (const struct CWcnAttribute *)v43);
      }
    }
    CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v40);
    CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v44);
    ReleaseSRWLockExclusive((PSRWLOCK)v22 + 21);
    if ( appended < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_79;
      v25 = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v26 + 16), 34, (unsigned int)WPP_cc1b862995d736ae8005150cb471f877_Traceguids, v25, appended);
LABEL_78:
      v19 = WPP_GLOBAL_Control;
LABEL_79:
      if ( v22 )
      {
        _InterlockedDecrement((volatile signed __int32 *)v22 + 66);
        v19 = WPP_GLOBAL_Control;
      }
      if ( v20 )
      {
        CWcnSession::Release(v20);
        v19 = WPP_GLOBAL_Control;
      }
      goto LABEL_83;
    }
    v27 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v22 + 16));
    v20 = (CWcnSession *)*((_QWORD *)v22 + 14);
    if ( v20 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v20 + 398);
      v27 = (CWcnSoftApSession *)_RTDynamicCast_0(
                                   *((_QWORD *)v20 + 25),
                                   0,
                                   &IWcnTransportSession `RTTI Type Descriptor',
                                   &CWcnSoftApSession `RTTI Type Descriptor',
                                   0);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v22 + 16));
    if ( !v27 )
    {
      if ( v20 )
        CWcnSession::Release(v20);
      v28 = (CWcnPeer *)operator new(0x640u, (const struct std::nothrow_t *)&std::nothrow);
      v38 = v28;
      if ( v28 )
        v20 = CWcnSession::CWcnSession(v28);
      else
        v20 = 0;
      if ( !v20 )
      {
        appended = -2147024882;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_79;
        v29 = 35;
        v30 = "pSession";
        goto LABEL_59;
      }
      appended = CWcnSession::Init(v20, v22);
      if ( appended < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_79;
        v31 = 36;
        goto LABEL_64;
      }
      appended = CWcnSession::StartConnect((__int64)v20, v23, *((unsigned int *)this - 2), 0x10000, 1);
      if ( appended < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_79;
        v31 = 37;
LABEL_64:
        WPP_SF_d(*((_QWORD *)v19 + 2), v31, WPP_cc1b862995d736ae8005150cb471f877_Traceguids, (unsigned int)appended);
        goto LABEL_78;
      }
      v27 = (CWcnSoftApSession *)_RTDynamicCast_0(
                                   *((_QWORD *)v20 + 25),
                                   0,
                                   &IWcnTransportSession `RTTI Type Descriptor',
                                   &CWcnSoftApSession `RTTI Type Descriptor',
                                   0);
      if ( !v27 )
      {
        appended = -2147022646;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_79;
        v32 = GetIndent(0);
        v29 = 38;
        v30 = v32;
LABEL_59:
        WPP_SF_s(*((_QWORD *)v19 + 2), v29, WPP_cc1b862995d736ae8005150cb471f877_Traceguids, v30);
        goto LABEL_78;
      }
    }
    appended = CWcnSoftApSession::SetConfigurationAndFinishConnect(
                 v27,
                 v39,
                 (const struct tagWcnEapAuthConfiguration *)v41);
    if ( appended >= 0 )
    {
      *a5 = (struct IWcnSinkConsumer *)(((unsigned __int64)v27 + 32) & -(__int64)(v27 != 0));
      goto LABEL_78;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_79;
    v31 = 39;
    goto LABEL_64;
  }
  appended = -2147024809;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_83;
    v35 = (unsigned int)GetIndent(0);
    WPP_SF_sPP(*(_QWORD *)(v36 + 16), 30, (unsigned int)WPP_cc1b862995d736ae8005150cb471f877_Traceguids, v35, v37, 12);
    goto LABEL_28;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800496c0  push    rbp
0x1800496c2  push    rbx
0x1800496c3  push    rsi
0x1800496c4  push    rdi
0x1800496c5  push    r12
0x1800496c7  push    r13
0x1800496c9  push    r14
0x1800496cb  push    r15
0x1800496cd  lea     rbp, [rsp-17h]
0x1800496d2  sub     rsp, 0C8h
0x1800496d9  mov     rax, cs:__security_cookie
0x1800496e0  xor     rax, rsp
0x1800496e3  mov     [rbp+4Fh+var_50], rax
0x1800496e7  mov     rbx, r9
0x1800496ea  mov     rax, r8
0x1800496ed  mov     [rbp+4Fh+var_C8], rax
0x1800496f1  mov     r14, rdx
0x1800496f4  mov     r13, rcx
0x1800496f7  mov     r12, [rbp+4Fh+arg_20]
0x1800496fb  mov     [rsp+100h+var_D0], 0
0x180049704  xor     ecx, ecx
0x180049706  mov     qword ptr [rbp+4Fh+var_A0], rcx
0x18004970a  mov     [rbp+4Fh+var_98], ecx
0x18004970d  lea     rdi, WPP_GLOBAL_Control
0x180049714  lea     r15, WPP_cc1b862995d736ae8005150cb471f877_Traceguids
0x18004971b  mov     r10, cs:WPP_GLOBAL_Control
0x180049722  cmp     r10, rdi
0x180049725  jz      short loc_180049757
0x180049727  cmp     byte ptr [r10+19h], 6
0x18004972c  jb      short loc_180049757
0x18004972e  mov     ecx, 1; int
0x180049733  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180049738  mov     edx, 19h
0x18004973d  mov     r9, rax
0x180049740  mov     r8, r15
0x180049743  mov     rcx, [r10+10h]
0x180049747  call    WPP_SF_s
0x18004974c  mov     r10, cs:WPP_GLOBAL_Control
0x180049753  mov     rax, [rbp+4Fh+var_C8]
0x180049757  test    r14, r14
0x18004975a  jnz     short loc_180049775
0x18004975c  cmp     r10, rdi
0x18004975f  jz      short loc_1800497D8
0x180049761  cmp     byte ptr [r10+19h], 2
0x180049766  jb      short loc_1800497D8
0x180049768  lea     edx, [r14+1Ah]
0x18004976c  lea     r9, aPsinksessiongu; "pSinkSessionGuid"
0x180049773  jmp     short loc_1800497CC
0x180049775  test    rax, rax
0x180049778  jnz     short loc_180049792
0x18004977a  cmp     r10, rdi
0x18004977d  jz      short loc_1800497D8
0x18004977f  cmp     byte ptr [r10+19h], 2
0x180049784  jb      short loc_1800497D8
0x180049786  lea     edx, [rax+1Bh]
0x180049789  lea     r9, aPsinksession; "pSinkSession"
0x180049790  jmp     short loc_1800497CC
0x180049792  test    rbx, rbx
0x180049795  jnz     short loc_1800497AF
0x180049797  cmp     r10, rdi
0x18004979a  jz      short loc_1800497D8
0x18004979c  cmp     byte ptr [r10+19h], 2
0x1800497a1  jb      short loc_1800497D8
0x1800497a3  lea     edx, [rbx+1Ch]
0x1800497a6  lea     r9, aPtransportextr; "pTransportExtra"
0x1800497ad  jmp     short loc_1800497CC
0x1800497af  test    r12, r12
0x1800497b2  jnz     short loc_1800497E2
0x1800497b4  cmp     r10, rdi
0x1800497b7  jz      short loc_1800497D8
0x1800497b9  cmp     byte ptr [r10+19h], 2
0x1800497be  jb      short loc_1800497D8
0x1800497c0  lea     edx, [r12+1Dh]
0x1800497c5  lea     r9, aPpsinkconsumer; "ppSinkConsumer"
0x1800497cc  mov     r8, r15
0x1800497cf  mov     rcx, [r10+10h]
0x1800497d3  call    WPP_SF_s
0x1800497d8  mov     eax, 80004003h
0x1800497dd  jmp     loc_180049D0E
0x1800497e2  mov     qword ptr [r12], 0
0x1800497ea  mov     rcx, [rbx+18h]
0x1800497ee  test    rcx, rcx
0x1800497f1  jz      loc_180049D2E
0x1800497f7  mov     rax, [rcx+8]
0x1800497fb  sub     rax, [rcx]
0x1800497fe  cmp     rax, 0Ch
0x180049802  jnz     loc_180049D2E
0x180049808  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18004980f  mov     rsi, [rax+38h]
0x180049813  mov     r8d, 0Ch; unsigned __int64
0x180049819  lea     rdx, [rbp+4Fh+var_A0]; unsigned __int8 *
0x18004981d  mov     rcx, rbx; this
0x180049820  call    ?CopyToBuffer@CSbSafeBuffer@@QEBAJPEAE_K@Z; CSbSafeBuffer::CopyToBuffer(uchar *,unsigned __int64)
0x180049825  mov     ebx, eax
0x180049827  test    eax, eax
0x180049829  jns     short loc_180049866
0x18004982b  mov     r10, cs:WPP_GLOBAL_Control
0x180049832  cmp     r10, rdi
0x180049835  jz      loc_180049D0C
0x18004983b  cmp     byte ptr [r10+19h], 2
0x180049840  jb      loc_180049CDC
0x180049846  mov     edx, 1Fh
0x18004984b  mov     r9d, eax
0x18004984e  mov     r8, r15
0x180049851  mov     rcx, [r10+10h]
0x180049855  call    WPP_SF_d
0x18004985a  mov     r10, cs:WPP_GLOBAL_Control
0x180049861  jmp     loc_180049CDC
0x180049866  xor     edi, edi
0x180049868  add     rsi, 0C0h
0x18004986f  mov     rcx, rsi; lpCriticalSection
0x180049872  call    cs:__imp_EnterCriticalSection
0x180049878  lea     r8, [rsp+100h+var_D0]
0x18004987d  mov     rdx, r14
0x180049880  mov     rcx, rsi
0x180049883  call    ?GetOrCreatePeer@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAPEAVCWcnPeer@@W4tagWCN_PROTOCOL_VERSION@@@Z; CWcnPeerCache::GetOrCreatePeer(_GUID const *,CWcnPeer * *,tagWCN_PROTOCOL_VERSION)
0x180049888  mov     ebx, eax
0x18004988a  mov     r15, [rsp+100h+var_D0]
0x18004988f  test    eax, eax
0x180049891  jns     short loc_1800498CF
0x180049893  mov     rcx, cs:WPP_GLOBAL_Control
0x18004989a  lea     rax, WPP_GLOBAL_Control
0x1800498a1  cmp     rcx, rax
0x1800498a4  jz      loc_180049A79
0x1800498aa  cmp     byte ptr [rcx+19h], 2
0x1800498ae  jb      loc_180049A79
0x1800498b4  lea     edx, [rdi+20h]
0x1800498b7  mov     r9d, ebx
0x1800498ba  lea     r8, WPP_cc1b862995d736ae8005150cb471f877_Traceguids
0x1800498c1  mov     rcx, [rcx+10h]
0x1800498c5  call    WPP_SF_d
0x1800498ca  jmp     loc_180049A79
0x1800498cf  mov     ecx, [r13-8]
0x1800498d3  xor     ebx, ebx
0x1800498d5  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800498d9  lea     r9, ??_R0?AVCWcnSoftApPeer@@@8; CWcnSoftApPeer `RTTI Type Descriptor'
0x1800498e0  lea     r8, ??_R0?AVIWcnTransportPeer@@@8; IWcnTransportPeer `RTTI Type Descriptor'
0x1800498e7  xor     edx, edx
0x1800498e9  mov     rcx, [r15+rcx*8+38h]
0x1800498ee  call    __RTDynamicCast_0
0x1800498f3  mov     r14, rax
0x1800498f6  test    rax, rax
0x1800498f9  jnz     short loc_180049951
0x1800498fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049902  lea     ecx, [rbx+30h]; unsigned __int64
0x180049905  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004990a  mov     r14, rax
0x18004990d  mov     [rsp+100h+var_D0], rax
0x180049912  test    rax, rax
0x180049915  jz      loc_180049A3F
0x18004991b  mov     [rax+8], bl
0x18004991e  lea     rax, ??_7CWcnSoftApPeer@@6B@; const CWcnSoftApPeer::`vftable'
0x180049925  mov     [r14], rax
0x180049928  mov     [r14+28h], rbx
0x18004992c  test    r14, r14
0x18004992f  jz      loc_180049A3F
0x180049935  lea     rax, [r13-10h]
0x180049939  mov     [r14+28h], rax
0x18004993d  mov     r8, r14; struct IWcnTransportPeer *
0x180049940  mov     edx, [r13-8]; unsigned int
0x180049944  mov     rcx, r15; this
0x180049947  call    ?SetTransportData@CWcnPeer@@QEAAXKPEAVIWcnTransportPeer@@@Z; CWcnPeer::SetTransportData(ulong,IWcnTransportPeer *)
0x18004994c  mov     byte ptr [r14+8], 1
0x180049951  mov     rcx, rsi; lpCriticalSection
0x180049954  call    cs:__imp_LeaveCriticalSection
0x18004995a  lea     rsi, [r15+0A8h]
0x180049961  mov     rcx, rsi; SRWLock
0x180049964  call    cs:__imp_AcquireSRWLockExclusive
0x18004996a  lea     rcx, [rbp+4Fh+var_90]; this
0x18004996e  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x180049973  nop
0x180049974  lea     rcx, [rbp+4Fh+var_C0]; this
0x180049978  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004997d  nop
0x18004997e  mov     r8d, 6; unsigned __int64
0x180049984  lea     rdx, [rbp+4Fh+var_A0+4]; unsigned __int8 *
0x180049988  lea     rcx, [rbp+4Fh+var_C0]; this
0x18004998c  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x180049991  mov     ebx, eax
0x180049993  test    eax, eax
0x180049995  js      short loc_1800499D1
0x180049997  lea     r8, [rbp+4Fh+var_C0]; struct CSbSafeBuffer *
0x18004999b  mov     edx, 5Ch ; '\'; enum tagWCN_ATTRIBUTE_TYPE
0x1800499a0  lea     rcx, [rbp+4Fh+var_90]; this
0x1800499a4  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x1800499a9  mov     ebx, eax
0x1800499ab  test    eax, eax
0x1800499ad  js      short loc_1800499D1
0x1800499af  lea     rbx, [r15+0B0h]
0x1800499b6  mov     edx, 5Ch ; '\'; enum tagWCN_ATTRIBUTE_TYPE
0x1800499bb  mov     rcx, rbx; this
0x1800499be  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x1800499c3  lea     rdx, [rbp+4Fh+var_90]; struct CWcnAttribute *
0x1800499c7  mov     rcx, rbx; this
0x1800499ca  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x1800499cf  mov     ebx, eax
0x1800499d1  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800499d5  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x1800499da  nop
0x1800499db  lea     rcx, [rbp+4Fh+var_78]; this
0x1800499df  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x1800499e4  mov     rcx, rsi; SRWLock
0x1800499e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800499ed  test    ebx, ebx
0x1800499ef  jns     loc_180049A87
0x1800499f5  mov     r10, cs:WPP_GLOBAL_Control
0x1800499fc  lea     rax, WPP_GLOBAL_Control
0x180049a03  cmp     r10, rax
0x180049a06  jz      loc_180049CA6
0x180049a0c  cmp     byte ptr [r10+19h], 2
0x180049a11  jb      loc_180049CA6
0x180049a17  xor     ecx, ecx; int
0x180049a19  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180049a1e  mov     edx, 22h ; '"'
0x180049a23  mov     dword ptr [rsp+100h+var_E0], ebx
0x180049a27  mov     r9, rax
0x180049a2a  lea     r8, WPP_cc1b862995d736ae8005150cb471f877_Traceguids
0x180049a31  mov     rcx, [r10+10h]
0x180049a35  call    WPP_SF_sd
0x180049a3a  jmp     loc_180049C9F
0x180049a3f  mov     ebx, 8007000Eh
0x180049a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a4b  lea     rax, WPP_GLOBAL_Control
0x180049a52  cmp     rcx, rax
0x180049a55  jz      short loc_180049A79
0x180049a57  cmp     byte ptr [rcx+19h], 2
0x180049a5b  jb      short loc_180049A79
0x180049a5d  mov     edx, 21h ; '!'
0x180049a62  lea     r9, aPnewsoftappeer; "pNewSoftApPeer"
0x180049a69  lea     r8, WPP_cc1b862995d736ae8005150cb471f877_Traceguids
0x180049a70  mov     rcx, [rcx+10h]
0x180049a74  call    WPP_SF_s
0x180049a79  mov     rcx, rsi; lpCriticalSection
0x180049a7c  call    cs:__imp_LeaveCriticalSection
0x180049a82  jmp     loc_180049C9F
0x180049a87  xor     esi, esi
0x180049a89  lea     rcx, [r15+10h]; lpCriticalSection
0x180049a8d  call    cs:__imp_EnterCriticalSection
0x180049a93  mov     rdi, [r15+70h]
0x180049a97  test    rdi, rdi
0x180049a9a  jz      short loc_180049AC6
0x180049a9c  lock inc dword ptr [rdi+638h]
0x180049aa3  mov     dword ptr [rsp+100h+var_E0], esi
0x180049aa7  lea     r9, ??_R0?AVCWcnSoftApSession@@@8; CWcnSoftApSession `RTTI Type Descriptor'
0x180049aae  lea     r8, ??_R0?AVIWcnTransportSession@@@8; IWcnTransportSession `RTTI Type Descriptor'
0x180049ab5  xor     edx, edx
0x180049ab7  mov     rcx, [rdi+0C8h]
0x180049abe  call    __RTDynamicCast_0
0x180049ac3  mov     rsi, rax
0x180049ac6  lea     rcx, [r15+10h]; lpCriticalSection
0x180049aca  call    cs:__imp_LeaveCriticalSection
0x180049ad0  test    rsi, rsi
0x180049ad3  jnz     loc_180049C54
0x180049ad9  test    rdi, rdi
0x180049adc  jz      short loc_180049AE6
0x180049ade  mov     rcx, rdi; this
0x180049ae1  call    ?Release@CWcnSession@@QEAAXXZ; CWcnSession::Release(void)
0x180049ae6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049aed  mov     ecx, 640h; unsigned __int64
0x180049af2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180049af7  mov     [rsp+100h+var_D0], rax
0x180049afc  test    rax, rax
0x180049aff  jz      short loc_180049B0E
0x180049b01  mov     rcx, rax; this
0x180049b04  call    ??0CWcnSession@@QEAA@XZ; CWcnSession::CWcnSession(void)
0x180049b09  mov     rdi, rax
0x180049b0c  jmp     short loc_180049B10
0x180049b0e  xor     edi, edi
0x180049b10  test    rdi, rdi
0x180049b13  jnz     short loc_180049B5B
0x180049b15  mov     ebx, 8007000Eh
0x180049b1a  mov     r10, cs:WPP_GLOBAL_Control
0x180049b21  lea     rax, WPP_GLOBAL_Control
0x180049b28  cmp     r10, rax
0x180049b2b  jz      loc_180049CA6
0x180049b31  cmp     byte ptr [r10+19h], 2
0x180049b36  jb      loc_180049CA6
0x180049b3c  lea     edx, [rdi+23h]
0x180049b3f  lea     r9, aPsession; "pSession"
0x180049b46  lea     r8, WPP_cc1b862995d736ae8005150cb471f877_Traceguids
0x180049b4d  mov     rcx, [r10+10h]
0x180049b51  call    WPP_SF_s
0x180049b56  jmp     loc_180049C9F
0x180049b5b  mov     rdx, r15; struct CWcnPeer *
0x180049b5e  mov     rcx, rdi; this
0x180049b61  call    ?Init@CWcnSession@@QEAAJPEAVCWcnPeer@@@Z; CWcnSession::Init(CWcnPeer *)
0x180049b66  mov     ebx, eax
0x180049b68  test    eax, eax
0x180049b6a  jns     short loc_180049BAB
0x180049b6c  mov     r10, cs:WPP_GLOBAL_Control
0x180049b73  lea     rax, WPP_GLOBAL_Control
0x180049b7a  cmp     r10, rax
0x180049b7d  jz      loc_180049CA6
0x180049b83  cmp     byte ptr [r10+19h], 2
0x180049b88  jb      loc_180049CA6
0x180049b8e  mov     edx, 24h ; '$'
0x180049b93  mov     r9d, ebx
0x180049b96  lea     r8, WPP_cc1b862995d736ae8005150cb471f877_Traceguids
0x180049b9d  mov     rcx, [r10+10h]
0x180049ba1  call    WPP_SF_d
  ... truncated ...
```
