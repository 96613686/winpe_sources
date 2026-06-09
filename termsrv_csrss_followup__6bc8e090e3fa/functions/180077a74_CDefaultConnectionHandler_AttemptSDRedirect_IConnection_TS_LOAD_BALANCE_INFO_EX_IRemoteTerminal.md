# CDefaultConnectionHandler::AttemptSDRedirect(IConnection *,TS_LOAD_BALANCE_INFO_EX *,IRemoteTerminal *)

- ea: `0x180077a74`
- end: `0x180078062`
- name: `?AttemptSDRedirect@CDefaultConnectionHandler@@QEAAJPEAVIConnection@@PEAUTS_LOAD_BALANCE_INFO_EX@@PEAVIRemoteTerminal@@@Z`
- size: `1518`
- prototype: `__int64 __fastcall(CDefaultConnectionHandler *__hidden this, struct IConnection *, struct TS_LOAD_BALANCE_INFO_EX *, struct IRemoteTerminal *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800799f0`

## callees

- `0x1800016a8`
- `0x180008110`
- `0x1800139c0`
- `0x1800143e4`
- `0x1800146c8`
- `0x180015020`
- `0x180015310`
- `0x18002558c`
- `0x180077a74`
- `0x180079fcc`
- `0x1800a1458`
- `0x1800ce010`

## string_xrefs

- `0x180077fd2`: `Task completed successfully`
- `0x180077ad2`: `Attempting SD reconnect`
- `0x180077abf`: `CDefaultConnectionHandler::AttemptSDRedirect`
- `0x180077b5f`: `CDefaultConnectionHandler::AttemptSDRedirect`
- `0x180077fc7`: `CDefaultConnectionHandler::AttemptSDRedirect`
- `0x180077ac6`: `Session Directory Reconnect`
- `0x180077b6a`: `Session Directory Reconnect`
- `0x180077bc8`: `AttemptSDRedirect`
- `0x180077c7e`: `AttemptSDRedirect`
- `0x180077ce8`: `AttemptSDRedirect`
- `0x180077d66`: `AttemptSDRedirect`
- `0x180077ddc`: `AttemptSDRedirect`
- `0x180077e58`: `AttemptSDRedirect`
- `0x180077ee3`: `AttemptSDRedirect`
- `0x180077f6c`: `AttemptSDRedirect`
- `0x180077c89`: `CUtils::GetSecurityFilterClientToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDefaultConnectionHandler::AttemptSDRedirect(
        CDefaultConnectionHandler *this,
        struct IConnection *a2,
        struct TS_LOAD_BALANCE_INFO_EX *a3,
        struct IRemoteTerminal *a4)
{
  const char *v8; // rcx
  const char **v9; // rax
  __int16 *v10; // rdx
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
  v8 = "CDefaultConnectionHandler::AttemptSDRedirect";
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v21 = "Attempting SD reconnect";
    v23 = "CDefaultConnectionHandler::AttemptSDRedirect";
    v20 = "Session Directory Reconnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"CDefaultConnectionHandler::AttemptSDRedirect",
      (unsigned int)word_180112982,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v20,
      (__int64)&v23,
      (__int64)&v21);
  }
  v27 = 0;
  if ( !*((_DWORD *)this + 400) )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
    {
LABEL_7:
      InstanceOfUserName = -2147467263;
      goto LABEL_8;
    }
    v20 = "SD Perf Not optimized";
    v9 = &v20;
    v10 = word_180112952;
LABEL_6:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v8,
      (_DWORD)v10,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)v9);
    goto LABEL_7;
  }
  InstanceOfUserName = (*(__int64 (__fastcall **)(struct IConnection *, int *))(*(_QWORD *)a2 + 560LL))(a2, &v30);
  if ( InstanceOfUserName < 0 )
  {
    LODWORD(v8) = dword_18012E170;
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_8;
    v20 = "AttemptSDRedirect";
    v23 = "pIConnection->IsFrontAuthUsed";
    v22 = "Warning HResult failed";
    v19 = &v20;
    v18 = &v23;
    v12 = &v22;
    v13 = (__int16 *)&unk_180112908;
    goto LABEL_13;
  }
  if ( !v30 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_7;
    v22 = "FrontAuth not used";
    v9 = &v22;
    v10 = (__int16 *)&unk_1801128D8;
    goto LABEL_6;
  }
  InstanceOfUserName = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, _QWORD, __int64 *))(*(_QWORD *)a4 + 344LL))(
                         a4,
                         0,
                         &v27);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "CUtils::GetSecurityFilterClientToken";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = &word_18011288E;
LABEL_13:
      LODWORD(v21) = InstanceOfUserName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v8,
        (_DWORD)v13,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)v12,
        (__int64)v18,
        (__int64)&v21,
        (__int64)v19);
      goto LABEL_8;
    }
    goto LABEL_8;
  }
  InstanceOfUserName = CUtils::GetInstanceOfUserName(&v28);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "CUtils::GetInstanceOfUserName";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = (__int16 *)&dword_180112844;
      goto LABEL_13;
    }
LABEL_8:
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      LODWORD(v21) = InstanceOfUserName;
      v22 = "CDefaultConnectionHandler::AttemptSDRedirect";
      v20 = "Session Directory Reconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&byte_180112687,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&v20,
        (__int64)&v22,
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
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "pUserName->Initialize";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = word_1801127FA;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  InstanceOfUserName = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, struct IUserName *))(*(_QWORD *)a4 + 168LL))(
                         a4,
                         v14);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "PrepareForSessionArbitration";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = (__int16 *)&unk_1801127B0;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  (*(void (__fastcall **)(struct IRemoteTerminal *))(*(_QWORD *)a4 + 456LL))(a4);
  InstanceOfUserName = CDefaultConnectionHandler::LoadSDArbHandler(v15, &v25);
  if ( InstanceOfUserName < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "LoadSDArbHandler";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = &word_180112766;
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
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "ISessionArbitrationHelper::InitializeEx";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = (__int16 *)&dword_18011271C;
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
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v22 = "AttemptSDRedirect";
      v20 = "EnumSessions";
      v23 = "Warning HResult failed";
      v19 = &v22;
      v18 = &v20;
      v12 = &v23;
      v13 = word_1801126D2;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    LODWORD(v21) = 0;
    v22 = "CDefaultConnectionHandler::AttemptSDRedirect";
    v20 = "Task completed successfully";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v8,
      (unsigned int)&dword_180112644,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v20,
      (__int64)&v22,
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
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v25);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v28);
  return (unsigned int)InstanceOfUserName;
}

```

## disassembly

```asm
0x180077a74  mov     [rsp-8+arg_8], rbx
0x180077a79  mov     [rsp-8+arg_10], rsi
0x180077a7e  push    rbp
0x180077a7f  push    rdi
0x180077a80  push    r12
0x180077a82  push    r14
0x180077a84  push    r15
0x180077a86  lea     rbp, [rsp-37h]
0x180077a8b  sub     rsp, 90h
0x180077a92  mov     rsi, r9
0x180077a95  mov     r15, r8
0x180077a98  mov     r14, rdx
0x180077a9b  mov     rbx, rcx
0x180077a9e  xor     r12d, r12d
0x180077aa1  mov     [rbp+57h+arg_0], r12d
0x180077aa5  mov     [rbp+57h+var_30], r12
0x180077aa9  mov     [rbp+57h+var_48], r12
0x180077aad  mov     [rbp+57h+var_28], r12
0x180077ab1  mov     [rbp+57h+var_50], r12d
0x180077ab5  mov     [rbp+57h+var_40], r12
0x180077ab9  mov     eax, cs:dword_18012E170
0x180077abf  lea     rcx, aCdefaultconnec_2; "CDefaultConnectionHandler::AttemptSDRed"...
0x180077ac6  lea     rdx, aSessionDirecto_2; "Session Directory Reconnect"
0x180077acd  cmp     eax, 4
0x180077ad0  jbe     short loc_180077B0C
0x180077ad2  lea     rax, aAttemptingSdRe; "Attempting SD reconnect"
0x180077ad9  mov     [rbp+57h+var_68], rax
0x180077add  mov     [rbp+57h+var_58], rcx
0x180077ae1  mov     [rbp+57h+var_70], rdx
0x180077ae5  lea     rax, [rbp+57h+var_68]
0x180077ae9  mov     [rsp+0B0h+var_80], rax
0x180077aee  lea     rax, [rbp+57h+var_58]
0x180077af2  mov     [rsp+0B0h+var_88], rax
0x180077af7  lea     rax, [rbp+57h+var_70]
0x180077afb  mov     [rsp+0B0h+var_90], rax
0x180077b00  lea     rdx, word_180112982
0x180077b07  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180077b0c  mov     [rbp+57h+var_38], r12
0x180077b10  cmp     [rbx+640h], r12d
0x180077b17  jnz     loc_180077BA1
0x180077b1d  mov     eax, cs:dword_18012E170
0x180077b23  cmp     eax, 3
0x180077b26  jbe     short loc_180077B48
0x180077b28  lea     rax, aSdPerfNotOptim; "SD Perf Not optimized"
0x180077b2f  mov     [rbp+57h+var_70], rax
0x180077b33  lea     rax, [rbp+57h+var_70]
0x180077b37  lea     rdx, word_180112952
0x180077b3e  mov     [rsp+0B0h+var_90], rax
0x180077b43  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180077b48  mov     edi, 80004001h
0x180077b4d  mov     eax, cs:dword_18012E170
0x180077b53  cmp     eax, 3
0x180077b56  jbe     loc_180078007
0x180077b5c  mov     dword ptr [rbp+57h+var_68], edi
0x180077b5f  lea     rax, aCdefaultconnec_2; "CDefaultConnectionHandler::AttemptSDRed"...
0x180077b66  mov     [rbp+57h+var_60], rax
0x180077b6a  lea     rax, aSessionDirecto_2; "Session Directory Reconnect"
0x180077b71  mov     [rbp+57h+var_70], rax
0x180077b75  lea     rax, [rbp+57h+var_68]
0x180077b79  mov     [rsp+0B0h+var_80], rax
0x180077b7e  lea     rax, [rbp+57h+var_60]
0x180077b82  mov     [rsp+0B0h+var_88], rax
0x180077b87  lea     rax, [rbp+57h+var_70]
0x180077b8b  mov     [rsp+0B0h+var_90], rax
0x180077b90  lea     rdx, byte_180112687
0x180077b97  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180077b9c  jmp     loc_180078007
0x180077ba1  mov     rax, [r14]
0x180077ba4  lea     rdx, [rbp+57h+arg_0]
0x180077ba8  mov     rcx, r14
0x180077bab  mov     rax, [rax+230h]
0x180077bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077bb7  mov     edi, eax
0x180077bb9  test    eax, eax
0x180077bbb  jns     short loc_180077C21
0x180077bbd  mov     ecx, cs:dword_18012E170
0x180077bc3  cmp     ecx, 3
0x180077bc6  jbe     short loc_180077B4D
0x180077bc8  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180077bcf  mov     [rbp+57h+var_70], rax
0x180077bd3  lea     rax, aPiconnectionIs_0; "pIConnection->IsFrontAuthUsed"
0x180077bda  mov     [rbp+57h+var_58], rax
0x180077bde  lea     rax, aWarningHresult; "Warning HResult failed"
0x180077be5  mov     [rbp+57h+var_60], rax
0x180077be9  lea     rax, [rbp+57h+var_70]
0x180077bed  mov     [rsp+0B0h+var_78], rax
0x180077bf2  lea     rax, [rbp+57h+var_68]
0x180077bf6  mov     [rsp+0B0h+var_80], rax
0x180077bfb  lea     rax, [rbp+57h+var_58]
0x180077bff  mov     [rsp+0B0h+var_88], rax
0x180077c04  lea     rax, [rbp+57h+var_60]
0x180077c08  lea     rdx, unk_180112908
0x180077c0f  mov     [rsp+0B0h+var_90], rax
0x180077c14  mov     dword ptr [rbp+57h+var_68], edi
0x180077c17  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180077c1c  jmp     loc_180077B4D
0x180077c21  cmp     [rbp+57h+arg_0], r12d
0x180077c25  jnz     short loc_180077C51
0x180077c27  mov     eax, cs:dword_18012E170
0x180077c2d  cmp     eax, 3
0x180077c30  jbe     loc_180077B48
0x180077c36  lea     rax, aFrontauthNotUs; "FrontAuth not used"
0x180077c3d  mov     [rbp+57h+var_60], rax
0x180077c41  lea     rax, [rbp+57h+var_60]
0x180077c45  lea     rdx, unk_1801128D8
0x180077c4c  jmp     loc_180077B3E
0x180077c51  mov     rax, [rsi]
0x180077c54  lea     r8, [rbp+57h+var_38]
0x180077c58  xor     edx, edx
0x180077c5a  mov     rcx, rsi
0x180077c5d  mov     rax, [rax+158h]
0x180077c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077c69  mov     edi, eax
0x180077c6b  test    eax, eax
0x180077c6d  jns     short loc_180077CCA
0x180077c6f  mov     eax, cs:dword_18012E170
0x180077c75  cmp     eax, 3
0x180077c78  jbe     loc_180077B4D
0x180077c7e  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180077c85  mov     [rbp+57h+var_60], rax
0x180077c89  lea     rax, aCutilsGetsecur_0; "CUtils::GetSecurityFilterClientToken"
0x180077c90  mov     [rbp+57h+var_70], rax
0x180077c94  lea     rax, aWarningHresult; "Warning HResult failed"
0x180077c9b  mov     [rbp+57h+var_58], rax
0x180077c9f  lea     rax, [rbp+57h+var_60]
0x180077ca3  mov     [rsp+0B0h+var_78], rax
0x180077ca8  lea     rax, [rbp+57h+var_68]
0x180077cac  mov     [rsp+0B0h+var_80], rax
0x180077cb1  lea     rax, [rbp+57h+var_70]
0x180077cb5  mov     [rsp+0B0h+var_88], rax
0x180077cba  lea     rax, [rbp+57h+var_58]
0x180077cbe  lea     rdx, word_18011288E
0x180077cc5  jmp     loc_180077C0F
0x180077cca  lea     rcx, [rbp+57h+var_30]; struct IUserName **
0x180077cce  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x180077cd3  mov     edi, eax
0x180077cd5  test    eax, eax
0x180077cd7  jns     short loc_180077D34
0x180077cd9  mov     eax, cs:dword_18012E170
0x180077cdf  cmp     eax, 3
0x180077ce2  jbe     loc_180077B4D
0x180077ce8  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180077cef  mov     [rbp+57h+var_60], rax
0x180077cf3  lea     rax, aCutilsGetinsta_0; "CUtils::GetInstanceOfUserName"
0x180077cfa  mov     [rbp+57h+var_70], rax
0x180077cfe  lea     rax, aWarningHresult; "Warning HResult failed"
0x180077d05  mov     [rbp+57h+var_58], rax
0x180077d09  lea     rax, [rbp+57h+var_60]
0x180077d0d  mov     [rsp+0B0h+var_78], rax
0x180077d12  lea     rax, [rbp+57h+var_68]
0x180077d16  mov     [rsp+0B0h+var_80], rax
0x180077d1b  lea     rax, [rbp+57h+var_70]
0x180077d1f  mov     [rsp+0B0h+var_88], rax
0x180077d24  lea     rax, [rbp+57h+var_58]
0x180077d28  lea     rdx, dword_180112844
0x180077d2f  jmp     loc_180077C0F
0x180077d34  mov     rbx, [rbp+57h+var_30]
0x180077d38  mov     rax, [rbx]
0x180077d3b  mov     r8d, 1
0x180077d41  mov     rdx, [rbp+57h+var_38]
0x180077d45  mov     rcx, rbx
0x180077d48  mov     rax, [rax+18h]
0x180077d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077d51  mov     edi, eax
0x180077d53  test    eax, eax
0x180077d55  jns     short loc_180077DB2
0x180077d57  mov     eax, cs:dword_18012E170
0x180077d5d  cmp     eax, 3
0x180077d60  jbe     loc_180077B4D
0x180077d66  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180077d6d  mov     [rbp+57h+var_60], rax
0x180077d71  lea     rax, aPusernameIniti; "pUserName->Initialize"
0x180077d78  mov     [rbp+57h+var_70], rax
0x180077d7c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180077d83  mov     [rbp+57h+var_58], rax
0x180077d87  lea     rax, [rbp+57h+var_60]
0x180077d8b  mov     [rsp+0B0h+var_78], rax
0x180077d90  lea     rax, [rbp+57h+var_68]
0x180077d94  mov     [rsp+0B0h+var_80], rax
0x180077d99  lea     rax, [rbp+57h+var_70]
0x180077d9d  mov     [rsp+0B0h+var_88], rax
0x180077da2  lea     rax, [rbp+57h+var_58]
0x180077da6  lea     rdx, word_1801127FA
0x180077dad  jmp     loc_180077C0F
0x180077db2  mov     rax, [rsi]
0x180077db5  mov     rdx, rbx
0x180077db8  mov     rcx, rsi
0x180077dbb  mov     rax, [rax+0A8h]
0x180077dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077dc7  mov     edi, eax
0x180077dc9  test    eax, eax
0x180077dcb  jns     short loc_180077E28
0x180077dcd  mov     eax, cs:dword_18012E170
0x180077dd3  cmp     eax, 3
0x180077dd6  jbe     loc_180077B4D
0x180077ddc  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180077de3  mov     [rbp+57h+var_60], rax
0x180077de7  lea     rax, aPrepareforsess; "PrepareForSessionArbitration"
0x180077dee  mov     [rbp+57h+var_70], rax
0x180077df2  lea     rax, aWarningHresult; "Warning HResult failed"
0x180077df9  mov     [rbp+57h+var_58], rax
0x180077dfd  lea     rax, [rbp+57h+var_60]
0x180077e01  mov     [rsp+0B0h+var_78], rax
0x180077e06  lea     rax, [rbp+57h+var_68]
0x180077e0a  mov     [rsp+0B0h+var_80], rax
0x180077e0f  lea     rax, [rbp+57h+var_70]
0x180077e13  mov     [rsp+0B0h+var_88], rax
0x180077e18  lea     rax, [rbp+57h+var_58]
0x180077e1c  lea     rdx, unk_1801127B0
0x180077e23  jmp     loc_180077C0F
0x180077e28  mov     rax, [rsi]
0x180077e2b  mov     rcx, rsi
0x180077e2e  mov     rax, [rax+1C8h]
0x180077e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077e3a  lea     rdx, [rbp+57h+var_48]; struct ISessionArbitrationHelperEx **
0x180077e3e  call    ?LoadSDArbHandler@CDefaultConnectionHandler@@QEAAJPEAPEAVISessionArbitrationHelperEx@@@Z; CDefaultConnectionHandler::LoadSDArbHandler(ISessionArbitrationHelperEx * *)
0x180077e43  mov     edi, eax
0x180077e45  test    eax, eax
0x180077e47  jns     short loc_180077EA4
0x180077e49  mov     eax, cs:dword_18012E170
0x180077e4f  cmp     eax, 3
0x180077e52  jbe     loc_180077B4D
0x180077e58  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180077e5f  mov     [rbp+57h+var_60], rax
0x180077e63  lea     rax, aLoadsdarbhandl; "LoadSDArbHandler"
0x180077e6a  mov     [rbp+57h+var_70], rax
0x180077e6e  lea     rax, aWarningHresult; "Warning HResult failed"
0x180077e75  mov     [rbp+57h+var_58], rax
0x180077e79  lea     rax, [rbp+57h+var_60]
0x180077e7d  mov     [rsp+0B0h+var_78], rax
0x180077e82  lea     rax, [rbp+57h+var_68]
0x180077e86  mov     [rsp+0B0h+var_80], rax
0x180077e8b  lea     rax, [rbp+57h+var_70]
0x180077e8f  mov     [rsp+0B0h+var_88], rax
0x180077e94  lea     rax, [rbp+57h+var_58]
0x180077e98  lea     rdx, word_180112766
0x180077e9f  jmp     loc_180077C0F
0x180077ea4  mov     rdx, rbx
0x180077ea7  lea     rcx, [rbp+57h+var_28]
0x180077eab  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180077eb0  mov     rcx, [rbp+57h+var_48]
0x180077eb4  mov     rax, [rcx]
0x180077eb7  mov     [rsp+0B0h+var_90], rsi
0x180077ebc  mov     r9, r15
0x180077ebf  mov     r8, rbx
0x180077ec2  mov     rdx, r14
0x180077ec5  mov     rax, [rax+58h]
0x180077ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077ece  mov     edi, eax
0x180077ed0  test    eax, eax
0x180077ed2  jns     short loc_180077F2F
0x180077ed4  mov     eax, cs:dword_18012E170
0x180077eda  cmp     eax, 3
0x180077edd  jbe     loc_180077B4D
0x180077ee3  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180077eea  mov     [rbp+57h+var_60], rax
0x180077eee  lea     rax, aIsessionarbitr; "ISessionArbitrationHelper::InitializeEx"
0x180077ef5  mov     [rbp+57h+var_70], rax
0x180077ef9  lea     rax, aWarningHresult; "Warning HResult failed"
0x180077f00  mov     [rbp+57h+var_58], rax
0x180077f04  lea     rax, [rbp+57h+var_60]
0x180077f08  mov     [rsp+0B0h+var_78], rax
0x180077f0d  lea     rax, [rbp+57h+var_68]
0x180077f11  mov     [rsp+0B0h+var_80], rax
0x180077f16  lea     rax, [rbp+57h+var_70]
0x180077f1a  mov     [rsp+0B0h+var_88], rax
0x180077f1f  lea     rax, [rbp+57h+var_58]
0x180077f23  lea     rdx, dword_18011271C
0x180077f2a  jmp     loc_180077C0F
0x180077f2f  mov     rcx, [rbp+57h+var_48]
0x180077f33  mov     rax, [rcx]
0x180077f36  mov     [rsp+0B0h+var_90], r12
0x180077f3b  lea     r9, [rbp+57h+var_40]
0x180077f3f  lea     r8, [rbp+57h+var_50]
0x180077f43  xor     edx, edx
0x180077f45  mov     rax, [rax+20h]
0x180077f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077f4e  mov     edi, eax
0x180077f50  cmp     eax, 1
0x180077f53  jz      short loc_180077FB8
0x180077f55  test    eax, eax
0x180077f57  jns     loc_180077B48
0x180077f5d  mov     eax, cs:dword_18012E170
0x180077f63  cmp     eax, 3
0x180077f66  jbe     loc_180077B4D
0x180077f6c  lea     rax, aAttemptsdredir; "AttemptSDRedirect"
0x180077f73  mov     [rbp+57h+var_60], rax
0x180077f77  lea     rax, aEnumsessions; "EnumSessions"
0x180077f7e  mov     [rbp+57h+var_70], rax
0x180077f82  lea     rax, aWarningHresult; "Warning HResult failed"
0x180077f89  mov     [rbp+57h+var_58], rax
0x180077f8d  lea     rax, [rbp+57h+var_60]
0x180077f91  mov     [rsp+0B0h+var_78], rax
0x180077f96  lea     rax, [rbp+57h+var_68]
0x180077f9a  mov     [rsp+0B0h+var_80], rax
0x180077f9f  lea     rax, [rbp+57h+var_70]
0x180077fa3  mov     [rsp+0B0h+var_88], rax
0x180077fa8  lea     rax, [rbp+57h+var_58]
0x180077fac  lea     rdx, word_1801126D2
0x180077fb3  jmp     loc_180077C0F
  ... truncated ...
```
