# CDefaultConnectionHandler::AttemptSDRedirect(IConnection *,TS_LOAD_BALANCE_INFO_EX *,IRemoteTerminal *)

- ea: `0x1800744ec`
- end: `0x180074ad9`
- name: `?AttemptSDRedirect@CDefaultConnectionHandler@@QEAAJPEAVIConnection@@PEAUTS_LOAD_BALANCE_INFO_EX@@PEAVIRemoteTerminal@@@Z`
- size: `1517`
- prototype: `__int64 __fastcall(CDefaultConnectionHandler *__hidden this, struct IConnection *, struct TS_LOAD_BALANCE_INFO_EX *, struct IRemoteTerminal *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180076420`

## callees

- `0x180001688`
- `0x180008b40`
- `0x180013150`
- `0x180013a18`
- `0x180013d00`
- `0x1800148d0`
- `0x1800148f0`
- `0x1800241f0`
- `0x1800744ec`
- `0x1800769fc`
- `0x18009d064`
- `0x1800c8010`

## string_xrefs

- `0x180074a4a`: `Task completed successfully`
- `0x18007454a`: `Attempting SD reconnect`
- `0x180074537`: `CDefaultConnectionHandler::AttemptSDRedirect`
- `0x1800745d7`: `CDefaultConnectionHandler::AttemptSDRedirect`
- `0x180074a3f`: `CDefaultConnectionHandler::AttemptSDRedirect`
- `0x18007453e`: `Session Directory Reconnect`
- `0x1800745e2`: `Session Directory Reconnect`
- `0x180074640`: `AttemptSDRedirect`
- `0x1800746f6`: `AttemptSDRedirect`
- `0x180074760`: `AttemptSDRedirect`
- `0x1800747de`: `AttemptSDRedirect`
- `0x180074854`: `AttemptSDRedirect`
- `0x1800748d0`: `AttemptSDRedirect`
- `0x18007495b`: `AttemptSDRedirect`
- `0x1800749e4`: `AttemptSDRedirect`
- `0x180074701`: `CUtils::GetSecurityFilterClientToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDefaultConnectionHandler::AttemptSDRedirect(
        CDefaultConnectionHandler *this,
        struct IConnection *a2,
        struct TS_LOAD_BALANCE_INFO_EX *a3,
        struct IRemoteTerminal *a4)
{
  __int64 v8; // rcx
  const char **v9; // rax
  unsigned __int8 *v10; // rdx
  int InstanceOfUserName; // edi
  const char **v12; // rax
  __int16 *v13; // rdx
  struct IUserName *v14; // rbx
  CDefaultConnectionHandler *v15; // rcx
  int v16; // eax
  const char **v18; // [rsp+28h] [rbp-31h]
  const char **v19; // [rsp+38h] [rbp-21h]
  const char *v20; // [rsp+40h] [rbp-19h] BYREF
  const char *v21; // [rsp+48h] [rbp-11h] BYREF
  const char *v22; // [rsp+50h] [rbp-9h] BYREF
  const char *v23; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v24; // [rsp+60h] [rbp+7h] BYREF
  struct ISessionArbitrationHelperEx *v25; // [rsp+68h] [rbp+Fh] BYREF
  struct _TS_SESSION_INFORMATION_0 *v26; // [rsp+70h] [rbp+17h] BYREF
  __int64 v27; // [rsp+78h] [rbp+1Fh] BYREF
  struct IUserName *v28; // [rsp+80h] [rbp+27h] BYREF
  __int64 v29; // [rsp+88h] [rbp+2Fh] BYREF
  int v30; // [rsp+C0h] [rbp+67h] BYREF

  v30 = 0;
  v28 = 0;
  v25 = 0;
  v29 = 0;
  v24 = 0;
  v26 = 0;
  v8 = (__int64)"CDefaultConnectionHandler::AttemptSDRedirect";
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v21 = "Attempting SD reconnect";
    v23 = "CDefaultConnectionHandler::AttemptSDRedirect";
    v20 = "Session Directory Reconnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (__int64)"CDefaultConnectionHandler::AttemptSDRedirect",
      (unsigned __int8 *)word_18010C902,
      (__int64)a3,
      (__int64)a4,
      (const unsigned __int16 **)&v20,
      (const unsigned __int16 **)&v23,
      (const unsigned __int16 **)&v21);
  }
  v27 = 0;
  if ( !*((_DWORD *)this + 400) )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
    {
LABEL_7:
      InstanceOfUserName = -2147467263;
      goto LABEL_8;
    }
    v20 = "SD Perf Not optimized";
    v9 = &v20;
    v10 = (unsigned __int8 *)word_18010C8D2;
LABEL_6:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v8,
      v10,
      (__int64)a3,
      (__int64)a4,
      (const unsigned __int16 **)v9);
    goto LABEL_7;
  }
  InstanceOfUserName = (*(__int64 (__fastcall **)(struct IConnection *, int *))(*(_QWORD *)a2 + 560LL))(a2, &v30);
  if ( InstanceOfUserName < 0 )
  {
    v8 = (unsigned int)dword_180128170;
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_8;
    v20 = "AttemptSDRedirect";
    v23 = "pIConnection->IsFrontAuthUsed";
    v22 = "Warning HResult failed";
    v19 = &v20;
    v18 = &v23;
    v12 = &v22;
    v13 = (__int16 *)&unk_18010C888;
    goto LABEL_13;
  }
  if ( !v30 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_7;
    v22 = "FrontAuth not used";
    v9 = &v22;
    v10 = (unsigned __int8 *)&unk_18010C858;
    goto LABEL_6;
  }
  InstanceOfUserName = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, _QWORD, __int64 *))(*(_QWORD *)a4 + 344LL))(
                         a4,
                         0,
                         &v27);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "CUtils::GetSecurityFilterClientToken";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = &word_18010C80E;
LABEL_13:
      LODWORD(v21) = InstanceOfUserName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v8,
        (int)v13,
        (__int64)a3,
        (__int64)a4,
        (const unsigned __int16 **)v12,
        (const unsigned __int16 **)v18,
        (__int64)&v21,
        (const unsigned __int16 **)v19);
      goto LABEL_8;
    }
    goto LABEL_8;
  }
  InstanceOfUserName = CUtils::GetInstanceOfUserName(&v28);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "CUtils::GetInstanceOfUserName";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = (__int16 *)&dword_18010C7C4;
      goto LABEL_13;
    }
LABEL_8:
    if ( (unsigned int)dword_180128170 > 3 )
    {
      LODWORD(v21) = InstanceOfUserName;
      v22 = "CDefaultConnectionHandler::AttemptSDRedirect";
      v20 = "Session Directory Reconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned __int8 *)byte_18010C607,
        (__int64)a3,
        (__int64)a4,
        (const unsigned __int16 **)&v20,
        (const unsigned __int16 **)&v22,
        (__int64)&v21);
    }
    goto LABEL_42;
  }
  v14 = v28;
  InstanceOfUserName = (*(__int64 (__fastcall **)(struct IUserName *, __int64, __int64))(*(_QWORD *)v28 + 24LL))(
                         v28,
                         v27,
                         1);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "pUserName->Initialize";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = word_18010C77A;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  InstanceOfUserName = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, struct IUserName *))(*(_QWORD *)a4 + 168LL))(
                         a4,
                         v14);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "PrepareForSessionArbitration";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = (__int16 *)&unk_18010C730;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  (*(void (__fastcall **)(struct IRemoteTerminal *))(*(_QWORD *)a4 + 456LL))(a4);
  InstanceOfUserName = CDefaultConnectionHandler::LoadSDArbHandler(v15, &v25);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "LoadSDArbHandler";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = &word_18010C6E6;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  SmartPtr<ITerminal>::operator=(&v29, v14);
  InstanceOfUserName = (*(__int64 (__fastcall **)(struct ISessionArbitrationHelperEx *, struct IConnection *, struct IUserName *, struct TS_LOAD_BALANCE_INFO_EX *, struct IRemoteTerminal *))(*(_QWORD *)v25 + 88LL))(
                         v25,
                         a2,
                         v14,
                         a3,
                         a4);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "ISessionArbitrationHelper::InitializeEx";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = (__int16 *)&dword_18010C69C;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  v16 = (*(__int64 (__fastcall **)(struct ISessionArbitrationHelperEx *, _QWORD, unsigned int *, struct _TS_SESSION_INFORMATION_0 **, _QWORD))(*(_QWORD *)v25 + 32LL))(
          v25,
          0,
          &v24,
          &v26,
          0);
  InstanceOfUserName = v16;
  if ( v16 != 1 )
  {
    if ( v16 >= 0 )
      goto LABEL_7;
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "EnumSessions";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = word_18010C652;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  if ( (unsigned int)dword_180128170 > 5 )
  {
    LODWORD(v21) = 0;
    v22 = "CDefaultConnectionHandler::AttemptSDRedirect";
    v20 = "Task completed successfully";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned __int8 *)&dword_18010C5C4,
      (__int64)a3,
      (__int64)a4,
      (const unsigned __int16 **)&v20,
      (const unsigned __int16 **)&v22,
      (__int64)&v21);
  }
  InstanceOfUserName = 0;
LABEL_42:
  if ( v26 )
  {
    CUtils::FreeSessionInformation(v24, v26);
    v26 = 0;
  }
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v27);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v29);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v25);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v28);
  return (unsigned int)InstanceOfUserName;
}

```

## disassembly

```asm
0x1800744ec  mov     [rsp-8+arg_8], rbx
0x1800744f1  mov     [rsp-8+arg_10], rsi
0x1800744f6  push    rbp
0x1800744f7  push    rdi
0x1800744f8  push    r12
0x1800744fa  push    r14
0x1800744fc  push    r15
0x1800744fe  lea     rbp, [rsp-37h]
0x180074503  sub     rsp, 90h
0x18007450a  mov     rsi, r9
0x18007450d  mov     r15, r8
0x180074510  mov     r14, rdx
0x180074513  mov     rbx, rcx
0x180074516  xor     r12d, r12d
0x180074519  mov     [rbp+57h+arg_0], r12d
0x18007451d  mov     [rbp+57h+var_30], r12
0x180074521  mov     [rbp+57h+var_48], r12
0x180074525  mov     [rbp+57h+var_28], r12
0x180074529  mov     [rbp+57h+var_50], r12d
0x18007452d  mov     [rbp+57h+var_40], r12
0x180074531  mov     eax, cs:dword_180128170
0x180074537  lea     rcx, aCdefaultconnec_2; "CDefaultConnectionHandler::AttemptSDRed"...
0x18007453e  lea     rdx, aSessionDirecto_2; "Session Directory Reconnect"
0x180074545  cmp     eax, 4
0x180074548  jbe     short loc_180074584
0x18007454a  lea     rax, aAttemptingSdRe; "Attempting SD reconnect"
0x180074551  mov     [rbp+57h+var_68], rax
0x180074555  mov     [rbp+57h+var_58], rcx
0x180074559  mov     [rbp+57h+var_70], rdx
0x18007455d  lea     rax, [rbp+57h+var_68]
0x180074561  mov     [rsp+0B0h+var_80], rax
0x180074566  lea     rax, [rbp+57h+var_58]
0x18007456a  mov     [rsp+0B0h+var_88], rax
0x18007456f  lea     rax, [rbp+57h+var_70]
0x180074573  mov     [rsp+0B0h+var_90], rax
0x180074578  lea     rdx, word_18010C902
0x18007457f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180074584  mov     [rbp+57h+var_38], r12
0x180074588  cmp     [rbx+640h], r12d
0x18007458f  jnz     loc_180074619
0x180074595  mov     eax, cs:dword_180128170
0x18007459b  cmp     eax, 3
0x18007459e  jbe     short loc_1800745C0
0x1800745a0  lea     rax, aSdPerfNotOptim; "SD Perf Not optimized"
0x1800745a7  mov     [rbp+57h+var_70], rax
0x1800745ab  lea     rax, [rbp+57h+var_70]
0x1800745af  lea     rdx, word_18010C8D2
0x1800745b6  mov     [rsp+0B0h+var_90], rax
0x1800745bb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800745c0  mov     edi, 80004001h
0x1800745c5  mov     eax, cs:dword_180128170
0x1800745cb  cmp     eax, 3
0x1800745ce  jbe     loc_180074A7F
0x1800745d4  mov     dword ptr [rbp+57h+var_68], edi
0x1800745d7  lea     rax, aCdefaultconnec_2; "CDefaultConnectionHandler::AttemptSDRed"...
0x1800745de  mov     [rbp+57h+var_60], rax
0x1800745e2  lea     rax, aSessionDirecto_2; "Session Directory Reconnect"
0x1800745e9  mov     [rbp+57h+var_70], rax
0x1800745ed  lea     rax, [rbp+57h+var_68]
0x1800745f1  mov     [rsp+0B0h+var_80], rax
0x1800745f6  lea     rax, [rbp+57h+var_60]
0x1800745fa  mov     [rsp+0B0h+var_88], rax
0x1800745ff  lea     rax, [rbp+57h+var_70]
0x180074603  mov     [rsp+0B0h+var_90], rax
0x180074608  lea     rdx, byte_18010C607
0x18007460f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180074614  jmp     loc_180074A7F
0x180074619  mov     rax, [r14]
0x18007461c  lea     rdx, [rbp+57h+arg_0]
0x180074620  mov     rcx, r14
0x180074623  mov     rax, [rax+230h]
0x18007462a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007462f  mov     edi, eax
0x180074631  test    eax, eax
0x180074633  jns     short loc_180074699
0x180074635  mov     ecx, cs:dword_180128170
0x18007463b  cmp     ecx, 3
0x18007463e  jbe     short loc_1800745C5
0x180074640  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180074647  mov     [rbp+57h+var_70], rax
0x18007464b  lea     rax, aPiconnectionIs_0; "pIConnection->IsFrontAuthUsed"
0x180074652  mov     [rbp+57h+var_58], rax
0x180074656  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007465d  mov     [rbp+57h+var_60], rax
0x180074661  lea     rax, [rbp+57h+var_70]
0x180074665  mov     [rsp+0B0h+var_78], rax
0x18007466a  lea     rax, [rbp+57h+var_68]
0x18007466e  mov     [rsp+0B0h+var_80], rax
0x180074673  lea     rax, [rbp+57h+var_58]
0x180074677  mov     [rsp+0B0h+var_88], rax
0x18007467c  lea     rax, [rbp+57h+var_60]
0x180074680  lea     rdx, unk_18010C888
0x180074687  mov     [rsp+0B0h+var_90], rax
0x18007468c  mov     dword ptr [rbp+57h+var_68], edi
0x18007468f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180074694  jmp     loc_1800745C5
0x180074699  cmp     [rbp+57h+arg_0], r12d
0x18007469d  jnz     short loc_1800746C9
0x18007469f  mov     eax, cs:dword_180128170
0x1800746a5  cmp     eax, 3
0x1800746a8  jbe     loc_1800745C0
0x1800746ae  lea     rax, aFrontauthNotUs; "FrontAuth not used"
0x1800746b5  mov     [rbp+57h+var_60], rax
0x1800746b9  lea     rax, [rbp+57h+var_60]
0x1800746bd  lea     rdx, unk_18010C858
0x1800746c4  jmp     loc_1800745B6
0x1800746c9  mov     rax, [rsi]
0x1800746cc  lea     r8, [rbp+57h+var_38]
0x1800746d0  xor     edx, edx
0x1800746d2  mov     rcx, rsi
0x1800746d5  mov     rax, [rax+158h]
0x1800746dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800746e1  mov     edi, eax
0x1800746e3  test    eax, eax
0x1800746e5  jns     short loc_180074742
0x1800746e7  mov     eax, cs:dword_180128170
0x1800746ed  cmp     eax, 3
0x1800746f0  jbe     loc_1800745C5
0x1800746f6  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x1800746fd  mov     [rbp+57h+var_60], rax
0x180074701  lea     rax, aCutilsGetsecur_0; "CUtils::GetSecurityFilterClientToken"
0x180074708  mov     [rbp+57h+var_70], rax
0x18007470c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180074713  mov     [rbp+57h+var_58], rax
0x180074717  lea     rax, [rbp+57h+var_60]
0x18007471b  mov     [rsp+0B0h+var_78], rax
0x180074720  lea     rax, [rbp+57h+var_68]
0x180074724  mov     [rsp+0B0h+var_80], rax
0x180074729  lea     rax, [rbp+57h+var_70]
0x18007472d  mov     [rsp+0B0h+var_88], rax
0x180074732  lea     rax, [rbp+57h+var_58]
0x180074736  lea     rdx, word_18010C80E
0x18007473d  jmp     loc_180074687
0x180074742  lea     rcx, [rbp+57h+var_30]; struct IUserName **
0x180074746  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18007474b  mov     edi, eax
0x18007474d  test    eax, eax
0x18007474f  jns     short loc_1800747AC
0x180074751  mov     eax, cs:dword_180128170
0x180074757  cmp     eax, 3
0x18007475a  jbe     loc_1800745C5
0x180074760  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180074767  mov     [rbp+57h+var_60], rax
0x18007476b  lea     rax, aCutilsGetinsta_0; "CUtils::GetInstanceOfUserName"
0x180074772  mov     [rbp+57h+var_70], rax
0x180074776  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007477d  mov     [rbp+57h+var_58], rax
0x180074781  lea     rax, [rbp+57h+var_60]
0x180074785  mov     [rsp+0B0h+var_78], rax
0x18007478a  lea     rax, [rbp+57h+var_68]
0x18007478e  mov     [rsp+0B0h+var_80], rax
0x180074793  lea     rax, [rbp+57h+var_70]
0x180074797  mov     [rsp+0B0h+var_88], rax
0x18007479c  lea     rax, [rbp+57h+var_58]
0x1800747a0  lea     rdx, dword_18010C7C4
0x1800747a7  jmp     loc_180074687
0x1800747ac  mov     rbx, [rbp+57h+var_30]
0x1800747b0  mov     rax, [rbx]
0x1800747b3  mov     r8d, 1
0x1800747b9  mov     rdx, [rbp+57h+var_38]
0x1800747bd  mov     rcx, rbx
0x1800747c0  mov     rax, [rax+18h]
0x1800747c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800747c9  mov     edi, eax
0x1800747cb  test    eax, eax
0x1800747cd  jns     short loc_18007482A
0x1800747cf  mov     eax, cs:dword_180128170
0x1800747d5  cmp     eax, 3
0x1800747d8  jbe     loc_1800745C5
0x1800747de  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x1800747e5  mov     [rbp+57h+var_60], rax
0x1800747e9  lea     rax, aPusernameIniti; "pUserName->Initialize"
0x1800747f0  mov     [rbp+57h+var_70], rax
0x1800747f4  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800747fb  mov     [rbp+57h+var_58], rax
0x1800747ff  lea     rax, [rbp+57h+var_60]
0x180074803  mov     [rsp+0B0h+var_78], rax
0x180074808  lea     rax, [rbp+57h+var_68]
0x18007480c  mov     [rsp+0B0h+var_80], rax
0x180074811  lea     rax, [rbp+57h+var_70]
0x180074815  mov     [rsp+0B0h+var_88], rax
0x18007481a  lea     rax, [rbp+57h+var_58]
0x18007481e  lea     rdx, word_18010C77A
0x180074825  jmp     loc_180074687
0x18007482a  mov     rax, [rsi]
0x18007482d  mov     rdx, rbx
0x180074830  mov     rcx, rsi
0x180074833  mov     rax, [rax+0A8h]
0x18007483a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007483f  mov     edi, eax
0x180074841  test    eax, eax
0x180074843  jns     short loc_1800748A0
0x180074845  mov     eax, cs:dword_180128170
0x18007484b  cmp     eax, 3
0x18007484e  jbe     loc_1800745C5
0x180074854  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x18007485b  mov     [rbp+57h+var_60], rax
0x18007485f  lea     rax, aPrepareforsess; "PrepareForSessionArbitration"
0x180074866  mov     [rbp+57h+var_70], rax
0x18007486a  lea     rax, aWarningHresult; "Warning HResult failed"
0x180074871  mov     [rbp+57h+var_58], rax
0x180074875  lea     rax, [rbp+57h+var_60]
0x180074879  mov     [rsp+0B0h+var_78], rax
0x18007487e  lea     rax, [rbp+57h+var_68]
0x180074882  mov     [rsp+0B0h+var_80], rax
0x180074887  lea     rax, [rbp+57h+var_70]
0x18007488b  mov     [rsp+0B0h+var_88], rax
0x180074890  lea     rax, [rbp+57h+var_58]
0x180074894  lea     rdx, unk_18010C730
0x18007489b  jmp     loc_180074687
0x1800748a0  mov     rax, [rsi]
0x1800748a3  mov     rcx, rsi
0x1800748a6  mov     rax, [rax+1C8h]
0x1800748ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800748b2  lea     rdx, [rbp+57h+var_48]; struct ISessionArbitrationHelperEx **
0x1800748b6  call    ?LoadSDArbHandler@CDefaultConnectionHandler@@QEAAJPEAPEAVISessionArbitrationHelperEx@@@Z; CDefaultConnectionHandler::LoadSDArbHandler(ISessionArbitrationHelperEx * *)
0x1800748bb  mov     edi, eax
0x1800748bd  test    eax, eax
0x1800748bf  jns     short loc_18007491C
0x1800748c1  mov     eax, cs:dword_180128170
0x1800748c7  cmp     eax, 3
0x1800748ca  jbe     loc_1800745C5
0x1800748d0  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x1800748d7  mov     [rbp+57h+var_60], rax
0x1800748db  lea     rax, aLoadsdarbhandl; "LoadSDArbHandler"
0x1800748e2  mov     [rbp+57h+var_70], rax
0x1800748e6  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800748ed  mov     [rbp+57h+var_58], rax
0x1800748f1  lea     rax, [rbp+57h+var_60]
0x1800748f5  mov     [rsp+0B0h+var_78], rax
0x1800748fa  lea     rax, [rbp+57h+var_68]
0x1800748fe  mov     [rsp+0B0h+var_80], rax
0x180074903  lea     rax, [rbp+57h+var_70]
0x180074907  mov     [rsp+0B0h+var_88], rax
0x18007490c  lea     rax, [rbp+57h+var_58]
0x180074910  lea     rdx, word_18010C6E6
0x180074917  jmp     loc_180074687
0x18007491c  mov     rdx, rbx
0x18007491f  lea     rcx, [rbp+57h+var_28]
0x180074923  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180074928  mov     rcx, [rbp+57h+var_48]
0x18007492c  mov     rax, [rcx]
0x18007492f  mov     [rsp+0B0h+var_90], rsi
0x180074934  mov     r9, r15
0x180074937  mov     r8, rbx
0x18007493a  mov     rdx, r14
0x18007493d  mov     rax, [rax+58h]
0x180074941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074946  mov     edi, eax
0x180074948  test    eax, eax
0x18007494a  jns     short loc_1800749A7
0x18007494c  mov     eax, cs:dword_180128170
0x180074952  cmp     eax, 3
0x180074955  jbe     loc_1800745C5
0x18007495b  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180074962  mov     [rbp+57h+var_60], rax
0x180074966  lea     rax, aIsessionarbitr; "ISessionArbitrationHelper::InitializeEx"
0x18007496d  mov     [rbp+57h+var_70], rax
0x180074971  lea     rax, aWarningHresult; "Warning HResult failed"
0x180074978  mov     [rbp+57h+var_58], rax
0x18007497c  lea     rax, [rbp+57h+var_60]
0x180074980  mov     [rsp+0B0h+var_78], rax
0x180074985  lea     rax, [rbp+57h+var_68]
0x180074989  mov     [rsp+0B0h+var_80], rax
0x18007498e  lea     rax, [rbp+57h+var_70]
0x180074992  mov     [rsp+0B0h+var_88], rax
0x180074997  lea     rax, [rbp+57h+var_58]
0x18007499b  lea     rdx, dword_18010C69C
0x1800749a2  jmp     loc_180074687
0x1800749a7  mov     rcx, [rbp+57h+var_48]
0x1800749ab  mov     rax, [rcx]
0x1800749ae  mov     [rsp+0B0h+var_90], r12
0x1800749b3  lea     r9, [rbp+57h+var_40]
0x1800749b7  lea     r8, [rbp+57h+var_50]
0x1800749bb  xor     edx, edx
0x1800749bd  mov     rax, [rax+20h]
0x1800749c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749c6  mov     edi, eax
0x1800749c8  cmp     eax, 1
0x1800749cb  jz      short loc_180074A30
0x1800749cd  test    eax, eax
0x1800749cf  jns     loc_1800745C0
0x1800749d5  mov     eax, cs:dword_180128170
0x1800749db  cmp     eax, 3
0x1800749de  jbe     loc_1800745C5
0x1800749e4  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x1800749eb  mov     [rbp+57h+var_60], rax
0x1800749ef  lea     rax, aEnumsessions; "EnumSessions"
0x1800749f6  mov     [rbp+57h+var_70], rax
0x1800749fa  lea     rax, aWarningHresult; "Warning HResult failed"
0x180074a01  mov     [rbp+57h+var_58], rax
0x180074a05  lea     rax, [rbp+57h+var_60]
0x180074a09  mov     [rsp+0B0h+var_78], rax
0x180074a0e  lea     rax, [rbp+57h+var_68]
0x180074a12  mov     [rsp+0B0h+var_80], rax
0x180074a17  lea     rax, [rbp+57h+var_70]
0x180074a1b  mov     [rsp+0B0h+var_88], rax
0x180074a20  lea     rax, [rbp+57h+var_58]
0x180074a24  lea     rdx, word_18010C652
0x180074a2b  jmp     loc_180074687
  ... truncated ...
```
