# CTSThread::BindThread(void)

- ea: `0x1800392d0`
- end: `0x1800396cc`
- name: `?BindThread@CTSThread@@UEAAJXZ`
- size: `1020`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800010b0`
- `0x18000a118`
- `0x18000abc0`
- `0x18000b98c`
- `0x18001b160`
- `0x18001b580`
- `0x18001b690`
- `0x18001b7c0`
- `0x18001b7ec`
- `0x18001bae0`
- `0x1800391a8`
- `0x1800392d0`
- `0x180039ddc`
- `0x18003a4dc`
- `0x18003b7b4`
- `0x18003ce6c`
- `0x180049010`

## string_xrefs

- `0x18003946d`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180039642`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180039369`: `Failed to create thread signal`
- `0x180039401`: `thread descriptor creation failed in bind path`
- `0x180039454`: `BindThread`
- `0x180039629`: `BindThread`
- `0x18003947b`: `Failing BindThread - thread does not allow binding`
- `0x180039654`: `Failed to InitializeInThreadContext`
- `0x1800395a5`: `Unable to add the current thread to the descriptor`

## pseudocode

```c
__int64 __fastcall CTSThread::BindThread(CTSThread *this)
{
  CTSReaderWriterLock *v2; // r12
  int Id; // ebx
  int ActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  struct CTS_TLS_ThreadDescriptor *v7; // rsi
  int v8; // r15d
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+B0h] [rbp+40h] BYREF
  int v25; // [rsp+B8h] [rbp+48h] BYREF
  struct CTS_TLS_ThreadDescriptor *v26; // [rsp+C0h] [rbp+50h] BYREF
  const char *v27; // [rsp+C8h] [rbp+58h] BYREF

  v23 = 0;
  v26 = 0;
  v2 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  if ( !*((_QWORD *)this + 85) )
  {
    Id = (*(__int64 (__fastcall **)(_QWORD, char *, unsigned int (__fastcall *)(CTSThread *), CTSThread *))(**((_QWORD **)this + 92) + 32LL))(
           *((_QWORD *)this + 92),
           (char *)this + 680,
           CTSThread::OnNotifyThreadMessage,
           this);
    if ( Id < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix();
        v5 = 48;
        v6 = "Failed to create thread signal";
LABEL_16:
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v5,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)v6,
          Id);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
  }
  if ( *((_DWORD *)this + 20) != 1 )
  {
    Id = -2147467259;
    goto LABEL_45;
  }
  v7 = TSGet_TLS_ThreadDescriptor();
  if ( v7 )
  {
    v8 = 0;
    TCntPtr<CTSBufferResult>::SafeRelease(&v26);
    v9 = *((_QWORD *)v7 + 4);
    v26 = v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    goto LABEL_18;
  }
  Id = CTS_TLS_ThreadDescriptor::CreateInstance(1, &v26);
  if ( Id >= 0 )
  {
    v7 = v26;
    v8 = 1;
LABEL_18:
    if ( !*((_DWORD *)v7 + 124) )
    {
      Id = -2147467259;
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        v24 = 913;
        v27 = "BindThread";
        v25 = -2147467259;
        v21 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v22 = "Failing BindThread - thread does not allow binding";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (unsigned int)byte_1800554EB,
          v11,
          v12,
          (__int64)&v22,
          (__int64)&v25,
          (__int64)&v21,
          (__int64)&v24,
          (__int64)&v27);
      }
      goto LABEL_43;
    }
    Id = PAL_System_ThreadGetId((char *)this + 56);
    if ( Id >= 0 )
    {
      Id = PAL_System_ThreadGetDeathCondition(*((_DWORD *)this + 14), (void **)this + 8);
      if ( Id >= 0 )
      {
        Id = CTSThread::InitializeInThreadContext(this, v15);
        if ( Id < 0 )
        {
          if ( (unsigned int)dword_18005C008 > 2 )
          {
            v24 = 935;
            v27 = "BindThread";
            v25 = -2147467259;
            v22 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
            v21 = "Failed to InitializeInThreadContext";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v16,
              (unsigned int)&word_1800554A6,
              v17,
              v18,
              (__int64)&v21,
              (__int64)&v25,
              (__int64)&v22,
              (__int64)&v24,
              (__int64)&v27);
          }
        }
        else
        {
          *((_DWORD *)this + 20) = 3;
          Id = CTS_TLS_ThreadDescriptor::AddThreadToList(v7, this);
          if ( Id >= 0 )
          {
            *((_DWORD *)this + 46) = 1;
            if ( v7 != *((struct CTS_TLS_ThreadDescriptor **)this + 81) )
            {
              TCntPtr<CTSBufferResult>::SafeRelease((char *)this + 648);
              *((_QWORD *)this + 81) = v7;
              if ( v7 )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 4) + 8LL))(*((_QWORD *)v7 + 4));
            }
            goto LABEL_45;
          }
          if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v19 = RdpX_GetActivityIdPrefix();
            WPP_SF_DsD(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
              52,
              (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
              v19,
              (__int64)"Unable to add the current thread to the descriptor",
              Id);
          }
        }
      }
      else
      {
        v13 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) )
        {
          v14 = 51;
          goto LABEL_26;
        }
      }
    }
    else
    {
      v13 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) )
      {
        v14 = 50;
LABEL_26:
        WPP_SF_(*(_QWORD *)(v13 + 16), v14, &WPP_903e1551464439edae082eb88b6439cd_Traceguids);
      }
    }
LABEL_43:
    if ( v8 )
      CTS_TLS_ThreadDescriptor::DetachThread(v7, this);
    goto LABEL_45;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    v5 = 49;
    v6 = "thread descriptor creation failed in bind path";
    goto LABEL_16;
  }
LABEL_45:
  CTSReaderWriterLock::WriteUnlock(v2);
  TCntPtr<CTSBufferResult>::SafeRelease(&v26);
  TCntPtr<IDispatch>::SafeRelease(&v23);
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x1800392d0  push    rbp
0x1800392d2  push    rbx
0x1800392d3  push    rsi
0x1800392d4  push    rdi
0x1800392d5  push    r12
0x1800392d7  push    r14
0x1800392d9  push    r15
0x1800392db  mov     rbp, rsp
0x1800392de  sub     rsp, 70h
0x1800392e2  mov     rdi, rcx
0x1800392e5  mov     [rbp+var_10], 0
0x1800392ed  mov     [rbp+arg_10], 0
0x1800392f5  lea     r12, [rcx+94h]
0x1800392fc  mov     rcx, r12; this
0x1800392ff  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180039304  lea     rdx, [rdi+2A8h]
0x18003930b  cmp     qword ptr [rdx], 0
0x18003930f  jnz     short loc_180039375
0x180039311  mov     rcx, [rdi+2E0h]
0x180039318  lea     r8, ?OnNotifyThreadMessage@CTSThread@@KAIPEAX@Z; CTSThread::OnNotifyThreadMessage(void *)
0x18003931f  mov     r9, rdi
0x180039322  mov     rax, [rcx]
0x180039325  mov     rax, [rax+20h]
0x180039329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003932e  mov     ebx, eax
0x180039330  test    eax, eax
0x180039332  jns     short loc_180039375
0x180039334  mov     rcx, cs:WPP_GLOBAL_Control
0x18003933b  lea     rax, WPP_GLOBAL_Control
0x180039342  cmp     rcx, rax
0x180039345  jz      loc_1800396A1
0x18003934b  test    byte ptr [rcx+1Ch], 8
0x18003934f  jz      loc_1800396A1
0x180039355  cmp     byte ptr [rcx+19h], 2
0x180039359  jb      loc_1800396A1
0x18003935f  call    RdpX_GetActivityIdPrefix
0x180039364  mov     edx, 30h ; '0'
0x180039369  lea     rcx, aFailedToCreate_2; "Failed to create thread signal"
0x180039370  jmp     loc_180039408
0x180039375  mov     r14d, 1
0x18003937b  cmp     [rdi+50h], r14d
0x18003937f  jz      short loc_18003938B
0x180039381  mov     ebx, 80004005h
0x180039386  jmp     loc_1800396A1
0x18003938b  call    ?TSGet_TLS_ThreadDescriptor@@YAPEAVCTS_TLS_ThreadDescriptor@@XZ; TSGet_TLS_ThreadDescriptor(void)
0x180039390  mov     rsi, rax
0x180039393  test    rax, rax
0x180039396  jz      short loc_1800393BA
0x180039398  lea     rcx, [rbp+arg_10]
0x18003939c  xor     r15d, r15d
0x18003939f  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x1800393a4  mov     rcx, [rsi+20h]
0x1800393a8  mov     [rbp+arg_10], rsi
0x1800393ac  mov     rax, [rcx]
0x1800393af  mov     rax, [rax+8]
0x1800393b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393b8  jmp     short loc_180039437
0x1800393ba  lea     rdx, [rbp+arg_10]; struct CTS_TLS_ThreadDescriptor **
0x1800393be  mov     ecx, r14d; int
0x1800393c1  call    ?CreateInstance@CTS_TLS_ThreadDescriptor@@SAJHPEAPEAV1@@Z; CTS_TLS_ThreadDescriptor::CreateInstance(int,CTS_TLS_ThreadDescriptor * *)
0x1800393c6  mov     ebx, eax
0x1800393c8  test    eax, eax
0x1800393ca  jns     short loc_180039430
0x1800393cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393d3  lea     rax, WPP_GLOBAL_Control
0x1800393da  cmp     rcx, rax
0x1800393dd  jz      loc_1800396A1
0x1800393e3  test    byte ptr [rcx+1Ch], 8
0x1800393e7  jz      loc_1800396A1
0x1800393ed  cmp     byte ptr [rcx+19h], 2
0x1800393f1  jb      loc_1800396A1
0x1800393f7  call    RdpX_GetActivityIdPrefix
0x1800393fc  mov     edx, 31h ; '1'
0x180039401  lea     rcx, aThreadDescript_0; "thread descriptor creation failed in bi"...
0x180039408  mov     dword ptr [rsp+70h+var_48], ebx
0x18003940c  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180039413  mov     [rsp+70h+var_50], rcx
0x180039418  mov     r9d, eax
0x18003941b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039422  mov     rcx, [rcx+10h]
0x180039426  call    WPP_SF_DsD
0x18003942b  jmp     loc_1800396A1
0x180039430  mov     rsi, [rbp+arg_10]
0x180039434  mov     r15d, r14d
0x180039437  cmp     dword ptr [rsi+1F0h], 0
0x18003943e  jnz     short loc_1800394B3
0x180039440  mov     eax, cs:dword_18005C008
0x180039446  mov     ebx, 80004005h
0x18003944b  cmp     eax, 2
0x18003944e  jbe     loc_180039691
0x180039454  lea     rax, aBindthread; "BindThread"
0x18003945b  mov     [rbp+arg_0], 391h
0x180039462  mov     [rbp+arg_18], rax
0x180039466  lea     rdx, byte_1800554EB
0x18003946d  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180039474  mov     [rbp+arg_8], ebx
0x180039477  mov     [rbp+var_20], rax
0x18003947b  lea     rax, aFailingBindthr; "Failing BindThread - thread does not al"...
0x180039482  mov     [rbp+var_18], rax
0x180039486  lea     rax, [rbp+arg_18]
0x18003948a  mov     [rsp+70h+var_30], rax
0x18003948f  lea     rax, [rbp+arg_0]
0x180039493  mov     [rsp+70h+var_38], rax
0x180039498  lea     rax, [rbp+var_20]
0x18003949c  mov     [rsp+70h+var_40], rax
0x1800394a1  lea     rax, [rbp+arg_8]
0x1800394a5  mov     [rsp+70h+var_48], rax
0x1800394aa  lea     rax, [rbp+var_18]
0x1800394ae  jmp     loc_180039687
0x1800394b3  lea     rcx, [rdi+38h]
0x1800394b7  call    PAL_System_ThreadGetId
0x1800394bc  mov     ebx, eax
0x1800394be  test    eax, eax
0x1800394c0  jns     short loc_180039507
0x1800394c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394c9  lea     rax, WPP_GLOBAL_Control
0x1800394d0  cmp     rcx, rax
0x1800394d3  jz      loc_180039691
0x1800394d9  test    [rcx+1Ch], r14b
0x1800394dd  jz      loc_180039691
0x1800394e3  cmp     [rcx+19h], r14b
0x1800394e7  jb      loc_180039691
0x1800394ed  mov     edx, 32h ; '2'
0x1800394f2  mov     rcx, [rcx+10h]
0x1800394f6  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800394fd  call    WPP_SF_
0x180039502  jmp     loc_180039691
0x180039507  mov     ecx, [rdi+38h]; dwThreadId
0x18003950a  lea     rdx, [rdi+40h]; void **
0x18003950e  call    ?PAL_System_ThreadGetDeathCondition@@YAJKPEAPEAX@Z; PAL_System_ThreadGetDeathCondition(ulong,void * *)
0x180039513  mov     ebx, eax
0x180039515  test    eax, eax
0x180039517  jns     short loc_18003954B
0x180039519  mov     rcx, cs:WPP_GLOBAL_Control
0x180039520  lea     rax, WPP_GLOBAL_Control
0x180039527  cmp     rcx, rax
0x18003952a  jz      loc_180039691
0x180039530  test    [rcx+1Ch], r14b
0x180039534  jz      loc_180039691
0x18003953a  cmp     [rcx+19h], r14b
0x18003953e  jb      loc_180039691
0x180039544  mov     edx, 33h ; '3'
0x180039549  jmp     short loc_1800394F2
0x18003954b  mov     rcx, rdi; this
0x18003954e  call    ?InitializeInThreadContext@CTSThread@@AEAAJH@Z; CTSThread::InitializeInThreadContext(int)
0x180039553  mov     ebx, eax
0x180039555  test    eax, eax
0x180039557  js      loc_18003961E
0x18003955d  mov     rdx, rdi; struct ITSThread *
0x180039560  mov     dword ptr [rdi+50h], 3
0x180039567  mov     rcx, rsi; this
0x18003956a  call    ?AddThreadToList@CTS_TLS_ThreadDescriptor@@AEAAJPEAVITSThread@@@Z; CTS_TLS_ThreadDescriptor::AddThreadToList(ITSThread *)
0x18003956f  mov     ebx, eax
0x180039571  test    eax, eax
0x180039573  jns     short loc_1800395D9
0x180039575  mov     rcx, cs:WPP_GLOBAL_Control
0x18003957c  lea     rax, WPP_GLOBAL_Control
0x180039583  cmp     rcx, rax
0x180039586  jz      loc_180039691
0x18003958c  test    byte ptr [rcx+1Ch], 8
0x180039590  jz      loc_180039691
0x180039596  cmp     byte ptr [rcx+19h], 2
0x18003959a  jb      loc_180039691
0x1800395a0  call    RdpX_GetActivityIdPrefix
0x1800395a5  lea     rcx, aUnableToAddThe; "Unable to add the current thread to the"...
0x1800395ac  mov     dword ptr [rsp+70h+var_48], ebx
0x1800395b0  mov     [rsp+70h+var_50], rcx
0x1800395b5  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800395bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800395c3  mov     edx, 34h ; '4'
0x1800395c8  mov     r9d, eax
0x1800395cb  mov     rcx, [rcx+10h]
0x1800395cf  call    WPP_SF_DsD
0x1800395d4  jmp     loc_180039691
0x1800395d9  mov     [rdi+0B8h], r14d
0x1800395e0  cmp     rsi, [rdi+288h]
0x1800395e7  jz      loc_1800396A1
0x1800395ed  lea     rcx, [rdi+288h]
0x1800395f4  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x1800395f9  mov     [rdi+288h], rsi
0x180039600  test    rsi, rsi
0x180039603  jz      loc_1800396A1
0x180039609  mov     rcx, [rsi+20h]
0x18003960d  mov     rax, [rcx]
0x180039610  mov     rax, [rax+8]
0x180039614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039619  jmp     loc_1800396A1
0x18003961e  mov     eax, cs:dword_18005C008
0x180039624  cmp     eax, 2
0x180039627  jbe     short loc_180039691
0x180039629  lea     rax, aBindthread; "BindThread"
0x180039630  mov     [rbp+arg_0], 3A7h
0x180039637  mov     [rbp+arg_18], rax
0x18003963b  lea     rdx, word_1800554A6
0x180039642  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180039649  mov     [rbp+arg_8], 80004005h
0x180039650  mov     [rbp+var_18], rax
0x180039654  lea     rax, aFailedToInitia_0; "Failed to InitializeInThreadContext"
0x18003965b  mov     [rbp+var_20], rax
0x18003965f  lea     rax, [rbp+arg_18]
0x180039663  mov     [rsp+70h+var_30], rax
0x180039668  lea     rax, [rbp+arg_0]
0x18003966c  mov     [rsp+70h+var_38], rax
0x180039671  lea     rax, [rbp+var_18]
0x180039675  mov     [rsp+70h+var_40], rax
0x18003967a  lea     rax, [rbp+arg_8]
0x18003967e  mov     [rsp+70h+var_48], rax
0x180039683  lea     rax, [rbp+var_20]
0x180039687  mov     [rsp+70h+var_50], rax
0x18003968c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180039691  test    r15d, r15d
0x180039694  jz      short loc_1800396A1
0x180039696  mov     rdx, rdi; struct ITSThread *
0x180039699  mov     rcx, rsi; this
0x18003969c  call    ?DetachThread@CTS_TLS_ThreadDescriptor@@QEAAXPEAVITSThread@@@Z; CTS_TLS_ThreadDescriptor::DetachThread(ITSThread *)
0x1800396a1  mov     rcx, r12; this
0x1800396a4  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x1800396a9  lea     rcx, [rbp+arg_10]
0x1800396ad  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x1800396b2  lea     rcx, [rbp+var_10]
0x1800396b6  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x1800396bb  mov     eax, ebx
0x1800396bd  add     rsp, 70h
0x1800396c1  pop     r15
0x1800396c3  pop     r14
0x1800396c5  pop     r12
0x1800396c7  pop     rdi
0x1800396c8  pop     rsi
0x1800396c9  pop     rbx
0x1800396ca  pop     rbp
0x1800396cb  retn
```
