# CTSThread::ThreadWaitForMultipleObjects(ulong,void * const *,TSWaitType,ulong,uint *)

- ea: `0x18003d5e0`
- end: `0x18003d8f0`
- name: `?ThreadWaitForMultipleObjects@CTSThread@@UEAAJKPEBQEAXW4TSWaitType@@KPEAI@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003d900`

## callees

- `0x1800010b0`
- `0x180007da0`
- `0x18000abc0`
- `0x18000add8`
- `0x18000b98c`
- `0x18001bae0`
- `0x18002c600`
- `0x180039890`
- `0x180039944`
- `0x180039fd8`
- `0x18003c900`
- `0x18003d5e0`
- `0x18003e460`
- `0x18003e76c`

## string_xrefs

- `0x18003d7f5`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003d71d`: `Unable to create blocking filter`
- `0x18003d6b9`: `Unable to create allow all filter`
- `0x18003d7dc`: `ThreadWaitForMultipleObjects`
- `0x18003d807`: `internalThreadWaitForMultipleObjects failed`

## pseudocode

```c
__int64 __fastcall CTSThread::ThreadWaitForMultipleObjects(
        struct ITSEventFilter **a1,
        unsigned int a2,
        void *const *a3,
        int a4,
        unsigned int a5,
        unsigned int *a6)
{
  struct ITSEventFilter *v6; // rbx
  struct ITSEventFilter **v10; // rdi
  int BlockAllFilter; // r14d
  int ActivityIdPrefix; // eax
  int v13; // edx
  const char *v14; // rcx
  int v15; // eax
  int v16; // r8d
  int v17; // r9d
  struct ITSEventFilter **v18; // rbx
  __int64 v19; // rdx
  int v20; // r8d
  int v21; // r9d
  int v23; // [rsp+50h] [rbp-30h] BYREF
  struct ITSEventFilter *v24; // [rsp+58h] [rbp-28h] BYREF
  const char *v25; // [rsp+60h] [rbp-20h] BYREF
  const char *v26; // [rsp+68h] [rbp-18h] BYREF
  const char *v27; // [rsp+70h] [rbp-10h] BYREF
  int v28; // [rsp+C8h] [rbp+48h] BYREF

  v6 = 0;
  v24 = 0;
  switch ( a4 )
  {
    case 1:
      v10 = a1 + 89;
      if ( a1[89] )
        goto LABEL_28;
      BlockAllFilter = CTSEventFilterFactory::CreateBlockAllFilter(a1 + 89);
      if ( BlockAllFilter >= 0 )
        goto LABEL_27;
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_40;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      v13 = 81;
LABEL_20:
      v14 = "Unable to create blocking filter";
      goto LABEL_39;
    case 2:
      v10 = a1 + 90;
      if ( a1[90] )
        goto LABEL_28;
      BlockAllFilter = CTSEventFilterFactory::CreateSyncOnlyFilter(a1 + 90);
      if ( BlockAllFilter >= 0 )
        goto LABEL_27;
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_40;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      v13 = 82;
      goto LABEL_20;
    case 3:
      v10 = a1 + 91;
      if ( a1[91] )
        goto LABEL_28;
      BlockAllFilter = CTSEventFilterFactory::CreateAllowAllFilter(a1 + 91);
      if ( BlockAllFilter < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_40;
        }
        ActivityIdPrefix = RdpX_GetActivityIdPrefix();
        v13 = 83;
        v14 = "Unable to create allow all filter";
LABEL_39:
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v13,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)v14,
          BlockAllFilter);
        goto LABEL_40;
      }
LABEL_27:
      if ( !*v10 )
        goto LABEL_29;
LABEL_28:
      TCntPtr<IDispatch>::SafeRelease(&v24);
      v6 = *v10;
      v24 = *v10;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v24);
      goto LABEL_29;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL));
  }
LABEL_29:
  v15 = CTSThread::internalThreadWaitForMultipleObjects((CTSThread *)a1, a2, a3, v6, a5, a6);
  BlockAllFilter = v15;
  if ( (int)(v15 + 0x80000000) >= 0 && v15 != -2092630012 && (unsigned int)dword_18005C008 > 2 )
  {
    v28 = 1568;
    v25 = "ThreadWaitForMultipleObjects";
    v23 = -2147467259;
    v26 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    v27 = "internalThreadWaitForMultipleObjects failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0x80000000,
      (unsigned int)byte_1800553C5,
      v16,
      v17,
      (__int64)&v27,
      (__int64)&v23,
      (__int64)&v26,
      (__int64)&v28,
      (__int64)&v25);
  }
  CTSCriticalSection::Lock((CTSCriticalSection *)(a1 + 13));
  v18 = (struct ITSEventFilter **)a1[16];
  CTSCriticalSection::UnLock((CTSCriticalSection *)(a1 + 13));
  if ( v18 != a1 + 16 )
  {
    BlockAllFilter = CTSThread::SignalEventQueue((CTSThread *)a1, v19, v20, v21);
    if ( BlockAllFilter < 0
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      v13 = 85;
      v14 = "Failed to Signal Event Queue";
      goto LABEL_39;
    }
  }
LABEL_40:
  TCntPtr<IDispatch>::SafeRelease(&v24);
  return (unsigned int)BlockAllFilter;
}

```

## disassembly

```asm
0x18003d5e0  mov     [rsp-28h+arg_0], rbx
0x18003d5e5  mov     [rsp-28h+arg_8], rsi
0x18003d5ea  push    rbp
0x18003d5eb  push    rdi
0x18003d5ec  push    r12
0x18003d5ee  push    r14
0x18003d5f0  push    r15
0x18003d5f2  mov     rbp, rsp
0x18003d5f5  sub     rsp, 80h
0x18003d5fc  xor     ebx, ebx
0x18003d5fe  mov     rsi, r8
0x18003d601  mov     [rbp+var_28], rbx
0x18003d605  mov     r12d, edx
0x18003d608  mov     r15, rcx
0x18003d60b  mov     r10d, r9d
0x18003d60e  lea     rax, WPP_GLOBAL_Control
0x18003d615  sub     r10d, 1
0x18003d619  jz      loc_18003D729
0x18003d61f  sub     r10d, 1
0x18003d623  jz      loc_18003D6C5
0x18003d629  cmp     r10d, 1
0x18003d62d  jz      short loc_18003D661
0x18003d62f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d636  cmp     rcx, rax
0x18003d639  jz      loc_18003D799
0x18003d63f  test    byte ptr [rcx+1Ch], 1
0x18003d643  jz      loc_18003D799
0x18003d649  cmp     byte ptr [rcx+19h], 1
0x18003d64d  jb      loc_18003D799
0x18003d653  mov     rcx, [rcx+10h]
0x18003d657  call    WPP_SF_d
0x18003d65c  jmp     loc_18003D799
0x18003d661  lea     rdi, [rcx+2D8h]
0x18003d668  cmp     [rdi], rbx
0x18003d66b  jnz     loc_18003D780
0x18003d671  mov     rcx, rdi; struct ITSEventFilter **
0x18003d674  call    ?CreateAllowAllFilter@CTSEventFilterFactory@@SAJPEAPEAVITSEventFilter@@@Z; CTSEventFilterFactory::CreateAllowAllFilter(ITSEventFilter * *)
0x18003d679  mov     r14d, eax
0x18003d67c  test    eax, eax
0x18003d67e  jns     loc_18003D77B
0x18003d684  mov     rax, cs:WPP_GLOBAL_Control
0x18003d68b  lea     rcx, WPP_GLOBAL_Control
0x18003d692  cmp     rax, rcx
0x18003d695  jz      loc_18003D8C8
0x18003d69b  test    byte ptr [rax+1Ch], 8
0x18003d69f  jz      loc_18003D8C8
0x18003d6a5  cmp     byte ptr [rax+19h], 2
0x18003d6a9  jb      loc_18003D8C8
0x18003d6af  call    RdpX_GetActivityIdPrefix
0x18003d6b4  mov     edx, 53h ; 'S'
0x18003d6b9  lea     rcx, aUnableToCreate; "Unable to create allow all filter"
0x18003d6c0  jmp     loc_18003D8A4
0x18003d6c5  lea     rdi, [rcx+2D0h]
0x18003d6cc  cmp     [rdi], rbx
0x18003d6cf  jnz     loc_18003D780
0x18003d6d5  mov     rcx, rdi; struct ITSEventFilter **
0x18003d6d8  call    ?CreateSyncOnlyFilter@CTSEventFilterFactory@@SAJPEAPEAVITSEventFilter@@@Z; CTSEventFilterFactory::CreateSyncOnlyFilter(ITSEventFilter * *)
0x18003d6dd  mov     r14d, eax
0x18003d6e0  test    eax, eax
0x18003d6e2  jns     loc_18003D77B
0x18003d6e8  mov     rax, cs:WPP_GLOBAL_Control
0x18003d6ef  lea     rcx, WPP_GLOBAL_Control
0x18003d6f6  cmp     rax, rcx
0x18003d6f9  jz      loc_18003D8C8
0x18003d6ff  test    byte ptr [rax+1Ch], 8
0x18003d703  jz      loc_18003D8C8
0x18003d709  cmp     byte ptr [rax+19h], 2
0x18003d70d  jb      loc_18003D8C8
0x18003d713  call    RdpX_GetActivityIdPrefix
0x18003d718  mov     edx, 52h ; 'R'
0x18003d71d  lea     rcx, aUnableToCreate_0; "Unable to create blocking filter"
0x18003d724  jmp     loc_18003D8A4
0x18003d729  lea     rdi, [rcx+2C8h]
0x18003d730  cmp     [rdi], rbx
0x18003d733  jnz     short loc_18003D780
0x18003d735  mov     rcx, rdi; struct ITSEventFilter **
0x18003d738  call    ?CreateBlockAllFilter@CTSEventFilterFactory@@SAJPEAPEAVITSEventFilter@@@Z; CTSEventFilterFactory::CreateBlockAllFilter(ITSEventFilter * *)
0x18003d73d  mov     r14d, eax
0x18003d740  test    eax, eax
0x18003d742  jns     short loc_18003D77B
0x18003d744  mov     rax, cs:WPP_GLOBAL_Control
0x18003d74b  lea     rcx, WPP_GLOBAL_Control
0x18003d752  cmp     rax, rcx
0x18003d755  jz      loc_18003D8C8
0x18003d75b  test    byte ptr [rax+1Ch], 8
0x18003d75f  jz      loc_18003D8C8
0x18003d765  cmp     byte ptr [rax+19h], 2
0x18003d769  jb      loc_18003D8C8
0x18003d76f  call    RdpX_GetActivityIdPrefix
0x18003d774  mov     edx, 51h ; 'Q'
0x18003d779  jmp     short loc_18003D71D
0x18003d77b  cmp     [rdi], rbx
0x18003d77e  jz      short loc_18003D799
0x18003d780  lea     rcx, [rbp+var_28]
0x18003d784  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18003d789  mov     rbx, [rdi]
0x18003d78c  lea     rcx, [rbp+var_28]
0x18003d790  mov     [rbp+var_28], rbx
0x18003d794  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18003d799  mov     rax, [rbp+arg_28]
0x18003d79d  mov     r9, rbx; struct ITSEventFilter *
0x18003d7a0  mov     [rsp+80h+var_58], rax; unsigned int *
0x18003d7a5  mov     r8, rsi; void **
0x18003d7a8  mov     eax, [rbp+arg_20]
0x18003d7ab  mov     edx, r12d; unsigned int
0x18003d7ae  mov     rcx, r15; this
0x18003d7b1  mov     [rsp+80h+var_60], eax; unsigned int
0x18003d7b5  call    ?internalThreadWaitForMultipleObjects@CTSThread@@IEAAJKPEBQEAXPEAVITSEventFilter@@KPEAI@Z; CTSThread::internalThreadWaitForMultipleObjects(ulong,void * const *,ITSEventFilter *,ulong,uint *)
0x18003d7ba  mov     ecx, 80000000h
0x18003d7bf  mov     r14d, eax
0x18003d7c2  add     eax, ecx
0x18003d7c4  test    ecx, eax
0x18003d7c6  jnz     short loc_18003D844
0x18003d7c8  cmp     r14d, 83450004h
0x18003d7cf  jz      short loc_18003D844
0x18003d7d1  mov     eax, cs:dword_18005C008
0x18003d7d7  cmp     eax, 2
0x18003d7da  jbe     short loc_18003D844
0x18003d7dc  lea     rax, aThreadwaitform; "ThreadWaitForMultipleObjects"
0x18003d7e3  mov     [rbp+arg_18], 620h
0x18003d7ea  mov     [rbp+var_20], rax
0x18003d7ee  lea     rdx, byte_1800553C5
0x18003d7f5  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003d7fc  mov     [rbp+var_30], 80004005h
0x18003d803  mov     [rbp+var_18], rax
0x18003d807  lea     rax, aInternalthread; "internalThreadWaitForMultipleObjects fa"...
0x18003d80e  mov     [rbp+var_10], rax
0x18003d812  lea     rax, [rbp+var_20]
0x18003d816  mov     [rsp+80h+var_40], rax
0x18003d81b  lea     rax, [rbp+arg_18]
0x18003d81f  mov     [rsp+80h+var_48], rax
0x18003d824  lea     rax, [rbp+var_18]
0x18003d828  mov     [rsp+80h+var_50], rax
0x18003d82d  lea     rax, [rbp+var_30]
0x18003d831  mov     [rsp+80h+var_58], rax
0x18003d836  lea     rax, [rbp+var_10]
0x18003d83a  mov     qword ptr [rsp+80h+var_60], rax
0x18003d83f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003d844  lea     rcx, [r15+68h]; this
0x18003d848  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18003d84d  lea     rdi, [r15+80h]
0x18003d854  mov     rbx, [rdi]
0x18003d857  lea     rcx, [r15+68h]; this
0x18003d85b  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18003d860  cmp     rbx, rdi
0x18003d863  jz      short loc_18003D8C8
0x18003d865  mov     rcx, r15; this
0x18003d868  call    ?SignalEventQueue@CTSThread@@MEAAJXZ; CTSThread::SignalEventQueue(void)
0x18003d86d  mov     r14d, eax
0x18003d870  test    eax, eax
0x18003d872  jns     short loc_18003D8C8
0x18003d874  mov     rax, cs:WPP_GLOBAL_Control
0x18003d87b  lea     rcx, WPP_GLOBAL_Control
0x18003d882  cmp     rax, rcx
0x18003d885  jz      short loc_18003D8C8
0x18003d887  test    byte ptr [rax+1Ch], 8
0x18003d88b  jz      short loc_18003D8C8
0x18003d88d  cmp     byte ptr [rax+19h], 2
0x18003d891  jb      short loc_18003D8C8
0x18003d893  call    RdpX_GetActivityIdPrefix
0x18003d898  mov     edx, 55h ; 'U'
0x18003d89d  lea     rcx, aFailedToSignal_0; "Failed to Signal Event Queue"
0x18003d8a4  mov     dword ptr [rsp+80h+var_58], r14d
0x18003d8a9  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003d8b0  mov     qword ptr [rsp+80h+var_60], rcx
0x18003d8b5  mov     r9d, eax
0x18003d8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d8bf  mov     rcx, [rcx+10h]
0x18003d8c3  call    WPP_SF_DsD
0x18003d8c8  lea     rcx, [rbp+var_28]
0x18003d8cc  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18003d8d1  lea     r11, [rsp+80h+var_s0]
0x18003d8d9  mov     eax, r14d
0x18003d8dc  mov     rbx, [r11+30h]
0x18003d8e0  mov     rsi, [r11+38h]
0x18003d8e4  mov     rsp, r11
0x18003d8e7  pop     r15
0x18003d8e9  pop     r14
0x18003d8eb  pop     r12
0x18003d8ed  pop     rdi
0x18003d8ee  pop     rbp
0x18003d8ef  retn
```
