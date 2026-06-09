# CTSRpcClientTrackerMgr::TrackCaller(long,unsigned __int64 *)

- ea: `0x18004da60`
- end: `0x18004e0e3`
- name: `?TrackCaller@CTSRpcClientTrackerMgr@@UEAAJJPEA_K@Z`
- size: `1667`
- prototype: `__int64 __fastcall(CTSRpcClientTrackerMgr *__hidden this, int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001380`
- `0x180001688`
- `0x180001e28`
- `0x180008a40`
- `0x180009ee0`
- `0x180009f50`
- `0x18000a210`
- `0x18000b400`
- `0x18000f080`
- `0x18000f250`
- `0x180011f80`
- `0x180013150`
- `0x1800142e8`
- `0x1800148d0`
- `0x180014f40`
- `0x180015004`
- `0x180015afc`
- `0x180017758`
- `0x180025b44`
- `0x1800321f0`
- `0x1800326dc`
- `0x18004da60`
- `0x1800b8084`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlInsertElementGenericTable` at `0x18004dd7d`
- `ntdll!RtlInsertElementGenericTable` at `0x18004dd7d`
- `RPCRT4!RpcImpersonateClient` at `0x18004dad1`
- `RPCRT4!RpcImpersonateClient` at `0x18004dad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e081`

## string_xrefs

- `0x18004daf8`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18004db24`: `ImpersonateRpcClient`
- `0x18004dbaf`: `GetClientToken`
- `0x18004dc39`: `UserName.GetUserSid`
- `0x18004daee`: `CImpersonate::ImpersonateRpcClient`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTSRpcClientTrackerMgr::TrackCaller(
        CTSRpcClientTrackerMgr *this,
        signed __int32 a2,
        volatile signed __int32 **a3)
{
  CImpersonate *v6; // rcx
  RPC_STATUS v7; // eax
  signed int ClientToken; // ebx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const char *v12; // rax
  char *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  const unsigned __int16 **v17; // rax
  __int16 *v18; // rdx
  unsigned __int16 *v19; // rax
  CTSRpcClientTrackerMgr::CTSRpcClient *v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  struct _RTL_GENERIC_TABLE *v24; // r14
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  volatile signed __int32 *v30; // rdi
  const char *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  unsigned int *v36; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 **p_Buffer; // [rsp+38h] [rbp-C8h]
  unsigned int v38; // [rsp+40h] [rbp-C0h] BYREF
  const char *Buffer; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v40; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pSessionId[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v43; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v45; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v46[2]; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v47; // [rsp+90h] [rbp-70h] BYREF
  void *v48; // [rsp+98h] [rbp-68h] BYREF
  CTSRpcClientTrackerMgr::CTSRpcClient *v49; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v50[2704]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v51[264]; // [rsp+B40h] [rbp+A40h] BYREF

  v40 = 0;
  CUserName::CUserName((CUserName *)v50);
  v48 = 0;
  pv = 0;
  v49 = 0;
  v47 = 0;
  CImpersonate::CheckCurrentContext(v6, 0);
  v7 = RpcImpersonateClient(0);
  ClientToken = v7;
  if ( v7 > 0 )
    ClientToken = (unsigned __int16)v7 | 0x80070000;
  if ( ClientToken >= 0 )
  {
    v40 = 257;
    ClientToken = CRpcUtils::GetClientToken(&v48, 1);
    if ( ClientToken < 0 )
    {
      v9 = (unsigned int)dword_180128170;
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_46;
      pv = "TrackCaller";
      v12 = "GetClientToken";
      v13 = (char *)qword_1801071D8;
      goto LABEL_6;
    }
    ClientToken = CUserName::Initialize((CUserName *)v50, v48, 0);
    if ( ClientToken < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_46;
      pv = "TrackCaller";
      v12 = "UserName.Initialize";
      v13 = &byte_180107217;
      goto LABEL_6;
    }
    ClientToken = CUserName::GetUserSid((CUserName *)v50, (struct _SID **)&pv);
    if ( ClientToken < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_44;
      Buffer = "TrackCaller";
      v38 = ClientToken;
      *(_QWORD *)pSessionId = "UserName.GetUserSid";
      v43 = "Warning HResult failed";
      p_Buffer = (const unsigned __int16 **)&Buffer;
      v36 = &v38;
      v17 = (const unsigned __int16 **)pSessionId;
      v18 = &word_180107256;
      goto LABEL_43;
    }
    v19 = (unsigned __int16 *)operator new(0x648u, (const struct std::nothrow_t *)std::nothrow);
    v46[0] = v19;
    if ( v19 )
      v20 = CTSRpcClientTrackerMgr::CTSRpcClient::CTSRpcClient((CTSRpcClientTrackerMgr::CTSRpcClient *)v19);
    else
      v20 = 0;
    v49 = v20;
    if ( v20 )
    {
      (*(void (__fastcall **)(CTSRpcClientTrackerMgr::CTSRpcClient *))(*(_QWORD *)v20 + 8LL))(v20);
      ClientToken = CTSRpcClientTrackerMgr::CTSRpcClient::Initialize(v20, pv);
      if ( ClientToken < 0 )
      {
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v43 = "TrackCaller";
          v38 = ClientToken;
          Buffer = "ptrRpcClient->Initialize";
          *(_QWORD *)pSessionId = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v21,
            (int)&dword_1801072D4,
            v22,
            v23,
            (const unsigned __int16 **)pSessionId,
            (const unsigned __int16 **)&Buffer,
            (__int64)&v38,
            (const unsigned __int16 **)&v43);
        }
        goto LABEL_44;
      }
      CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v46, (struct _RTL_RESOURCE *)((char *)this + 1592));
      v24 = (struct _RTL_GENERIC_TABLE *)((char *)this + 1696);
      if ( !(unsigned int)CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(v24, v20, &v47) )
      {
        Buffer = (const char *)v20;
        NewElement[0] = 0;
        if ( !RtlInsertElementGenericTable(v24, &Buffer, 8u, NewElement) )
        {
          ClientToken = -2147024882;
          if ( (unsigned int)dword_180128170 > 3 )
          {
            v43 = "TrackCaller";
            v38 = -2147024882;
            Buffer = "m_ptrRpcClientList.Add";
            *(_QWORD *)pSessionId = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              2147942414LL,
              (int)byte_180107313,
              v25,
              v26,
              (const unsigned __int16 **)pSessionId,
              (const unsigned __int16 **)&Buffer,
              (__int64)&v38,
              (const unsigned __int16 **)&v43);
          }
LABEL_27:
          CAutoLock::Unlock((CAutoLock *)v46);
          goto LABEL_44;
        }
        (*(void (__fastcall **)(const char *))(*(_QWORD *)Buffer + 8LL))(Buffer);
        ClientToken = 0;
        if ( !(unsigned int)CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(v24, v20, &v47) )
        {
          ClientToken = -2147023537;
          if ( (unsigned int)dword_180128170 > 3 )
          {
            v43 = "TrackCaller";
            v38 = -2147023537;
            Buffer = "m_ptrRpcClientList.Lookup";
            *(_QWORD *)pSessionId = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v27,
              (int)word_180107352,
              v28,
              v29,
              (const unsigned __int16 **)pSessionId,
              (const unsigned __int16 **)&Buffer,
              (__int64)&v38,
              (const unsigned __int16 **)&v43);
          }
          goto LABEL_27;
        }
      }
      CAutoLock::Unlock((CAutoLock *)v46);
      v30 = v47;
      if ( _InterlockedIncrement(v47 + 401) <= a2 )
      {
        if ( (unsigned int)dword_180128170 > 5 )
        {
          LODWORD(Buffer) = *((_DWORD *)v30 + 401);
          v46[0] = (const unsigned __int16 *)CRpcUtils::GetClientProcessId();
          v45 = (unsigned __int16 *)"RpcClientTracker added successfully this RPC Caller";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            v32,
            (unsigned __int8 *)byte_18010742D,
            v33,
            v34,
            (const unsigned __int16 **)&v45,
            (__int64)v46,
            (__int64)&Buffer);
        }
        *a3 = v30;
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        goto LABEL_44;
      }
      v38 = 0;
      pSessionId[0] = 0;
      CRpcUtils::GetRpcCallerInfo(pSessionId, &v38, 0x104u, v51);
      if ( (unsigned int)dword_180128170 > 1 )
      {
        v43 = (const char *)pSessionId[0];
        Buffer = (const char *)v38;
        v45 = v51;
        v46[0] = (const unsigned __int16 *)"Caller failed to be added";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v14,
          (int)byte_180107391,
          v15,
          v16,
          v46,
          (const unsigned __int16 **)&v45,
          (__int64)&Buffer,
          (__int64)&v43);
      }
      _InterlockedDecrement(v30 + 401);
      ClientToken = -2147024891;
      if ( (unsigned int)dword_180128170 <= 3 )
      {
LABEL_44:
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_46;
      }
      v46[0] = (const unsigned __int16 *)"TrackCaller";
      LODWORD(Buffer) = -2147024891;
      v31 = "ptrFound->IncrementCount() >= MaxCount";
      v18 = &word_1801073EE;
    }
    else
    {
      v14 = 2147942414LL;
      ClientToken = -2147024882;
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_44;
      v46[0] = (const unsigned __int16 *)"TrackCaller";
      LODWORD(Buffer) = -2147024882;
      v31 = "New CTSRpcClient";
      v18 = (__int16 *)byte_180107295;
    }
    v45 = (unsigned __int16 *)v31;
    v43 = "Warning HResult failed";
    p_Buffer = v46;
    v36 = (unsigned int *)&Buffer;
    v17 = (const unsigned __int16 **)&v45;
LABEL_43:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14,
      (int)v18,
      v15,
      v16,
      (const unsigned __int16 **)&v43,
      v17,
      (__int64)v36,
      p_Buffer);
    goto LABEL_44;
  }
  _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", ClientToken, "CImpersonate::ImpersonateRpcClient");
  if ( (unsigned int)dword_180128170 > 3 )
  {
    pv = "TrackCaller";
    v12 = "ImpersonateRpcClient";
    v13 = byte_180107199;
LABEL_6:
    Buffer = v12;
    *(_QWORD *)pSessionId = "Warning HResult failed";
    v38 = ClientToken;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v9,
      (int)v13,
      v10,
      v11,
      (const unsigned __int16 **)pSessionId,
      (const unsigned __int16 **)&Buffer,
      (__int64)&v38,
      (const unsigned __int16 **)&pv);
  }
LABEL_46:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v47);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v49);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v48);
  CUserName::~CUserName((CUserName *)v50);
  CImpersonate::StopImpersonating((CImpersonate *)&v40);
  return (unsigned int)ClientToken;
}

```

## disassembly

```asm
0x18004da60  mov     [rsp-8+arg_8], rbx
0x18004da65  push    rbp
0x18004da66  push    rdi
0x18004da67  push    r12
0x18004da69  push    r14
0x18004da6b  push    r15
0x18004da6d  lea     rbp, [rsp-0C60h]
0x18004da75  sub     rsp, 0D60h
0x18004da7c  mov     rax, cs:__security_cookie
0x18004da83  xor     rax, rsp
0x18004da86  mov     [rbp+0C80h+var_30], rax
0x18004da8d  mov     r12, r8
0x18004da90  mov     r15d, edx
0x18004da93  mov     r14, rcx
0x18004da96  mov     [rsp+0D80h+var_D30], 0
0x18004da9d  lea     rcx, [rbp+0C80h+var_CD0]; this
0x18004daa1  call    ??0CUserName@@QEAA@XZ; CUserName::CUserName(void)
0x18004daa6  nop
0x18004daa7  mov     [rbp+0C80h+var_CE8], 0
0x18004daaf  mov     [rsp+0D80h+pv], 0
0x18004dab8  mov     [rbp+0C80h+var_CE0], 0
0x18004dac0  mov     [rbp+0C80h+var_CF0], 0
0x18004dac8  xor     edx, edx; void *
0x18004daca  call    ?CheckCurrentContext@CImpersonate@@AEAAJPEAX@Z; CImpersonate::CheckCurrentContext(void *)
0x18004dacf  xor     ecx, ecx; BindingHandle
0x18004dad1  call    cs:__imp_RpcImpersonateClient
0x18004dad7  mov     ebx, eax
0x18004dad9  test    eax, eax
0x18004dadb  jle     short loc_18004DAE6
0x18004dadd  movzx   ebx, ax
0x18004dae0  or      ebx, 80070000h
0x18004dae6  test    ebx, ebx
0x18004dae8  jns     loc_18004DB79
0x18004daee  lea     r9, aCimpersonateIm_0; "CImpersonate::ImpersonateRpcClient"
0x18004daf5  mov     r8d, ebx
0x18004daf8  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18004daff  mov     ecx, 8; int
0x18004db04  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004db09  mov     eax, cs:dword_180128170
0x18004db0f  cmp     eax, 3
0x18004db12  jbe     loc_18004E088
0x18004db18  lea     rax, aTrackcaller; "TrackCaller"
0x18004db1f  mov     [rsp+0D80h+pv], rax
0x18004db24  lea     rax, aImpersonaterpc; "ImpersonateRpcClient"
0x18004db2b  lea     rdx, byte_180107199
0x18004db32  mov     [rsp+0D80h+Buffer], rax
0x18004db37  lea     rax, aWarningHresult; "Warning HResult failed"
0x18004db3e  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x18004db43  lea     rax, [rsp+0D80h+pv]
0x18004db48  mov     [rsp+0D80h+var_D48], rax
0x18004db4d  lea     rax, [rsp+0D80h+var_D40]
0x18004db52  mov     [rsp+0D80h+var_D50], rax
0x18004db57  lea     rax, [rsp+0D80h+Buffer]
0x18004db5c  mov     [rsp+0D80h+var_D58], rax
0x18004db61  lea     rax, [rsp+0D80h+pSessionId]
0x18004db66  mov     [rsp+0D80h+var_D40], ebx
0x18004db6a  mov     [rsp+0D80h+var_D60], rax
0x18004db6f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004db74  jmp     loc_18004E088
0x18004db79  mov     [rsp+0D80h+var_D30], 101h
0x18004db80  mov     edx, 1; int
0x18004db85  lea     rcx, [rbp+0C80h+var_CE8]; void **
0x18004db89  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x18004db8e  mov     ebx, eax
0x18004db90  test    eax, eax
0x18004db92  jns     short loc_18004DBC2
0x18004db94  mov     ecx, cs:dword_180128170
0x18004db9a  cmp     ecx, 3
0x18004db9d  jbe     loc_18004E088
0x18004dba3  lea     rax, aTrackcaller; "TrackCaller"
0x18004dbaa  mov     [rsp+0D80h+pv], rax
0x18004dbaf  lea     rax, aGetclienttoken; "GetClientToken"
0x18004dbb6  lea     rdx, qword_1801071D8
0x18004dbbd  jmp     loc_18004DB32
0x18004dbc2  xor     r8d, r8d; int
0x18004dbc5  mov     rdx, [rbp+0C80h+var_CE8]; void *
0x18004dbc9  lea     rcx, [rbp+0C80h+var_CD0]; this
0x18004dbcd  call    ?Initialize@CUserName@@UEAAJ_KH@Z; CUserName::Initialize(unsigned __int64,int)
0x18004dbd2  mov     ebx, eax
0x18004dbd4  test    eax, eax
0x18004dbd6  jns     short loc_18004DC06
0x18004dbd8  mov     eax, cs:dword_180128170
0x18004dbde  cmp     eax, 3
0x18004dbe1  jbe     loc_18004E088
0x18004dbe7  lea     rax, aTrackcaller; "TrackCaller"
0x18004dbee  mov     [rsp+0D80h+pv], rax
0x18004dbf3  lea     rax, aUsernameInitia; "UserName.Initialize"
0x18004dbfa  lea     rdx, byte_180107217
0x18004dc01  jmp     loc_18004DB32
0x18004dc06  lea     rdx, [rsp+0D80h+pv]; struct _SID **
0x18004dc0b  lea     rcx, [rbp+0C80h+var_CD0]; this
0x18004dc0f  call    ?GetUserSid@CUserName@@UEAAJPEAPEAU_SID@@@Z; CUserName::GetUserSid(_SID * *)
0x18004dc14  mov     ebx, eax
0x18004dc16  test    eax, eax
0x18004dc18  jns     short loc_18004DC76
0x18004dc1a  mov     eax, cs:dword_180128170
0x18004dc20  cmp     eax, 3
0x18004dc23  jbe     loc_18004E074
0x18004dc29  lea     rax, aTrackcaller; "TrackCaller"
0x18004dc30  mov     [rsp+0D80h+Buffer], rax
0x18004dc35  mov     [rsp+0D80h+var_D40], ebx
0x18004dc39  lea     rax, aUsernameGetuse; "UserName.GetUserSid"
0x18004dc40  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x18004dc45  lea     rax, aWarningHresult; "Warning HResult failed"
0x18004dc4c  mov     [rsp+0D80h+var_D18], rax
0x18004dc51  lea     rax, [rsp+0D80h+Buffer]
0x18004dc56  mov     [rsp+0D80h+var_D48], rax
0x18004dc5b  lea     rax, [rsp+0D80h+var_D40]
0x18004dc60  mov     [rsp+0D80h+var_D50], rax
0x18004dc65  lea     rax, [rsp+0D80h+pSessionId]
0x18004dc6a  lea     rdx, word_180107256
0x18004dc71  jmp     loc_18004E060
0x18004dc76  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004dc7d  mov     ecx, 648h; unsigned __int64
0x18004dc82  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004dc87  mov     [rbp+0C80h+var_D00], rax
0x18004dc8b  test    rax, rax
0x18004dc8e  jz      short loc_18004DC9D
0x18004dc90  mov     rcx, rax; this
0x18004dc93  call    ??0CTSRpcClient@CTSRpcClientTrackerMgr@@QEAA@XZ; CTSRpcClientTrackerMgr::CTSRpcClient::CTSRpcClient(void)
0x18004dc98  mov     rdi, rax
0x18004dc9b  jmp     short loc_18004DC9F
0x18004dc9d  xor     edi, edi
0x18004dc9f  mov     [rbp+0C80h+var_CE0], rdi
0x18004dca3  test    rdi, rdi
0x18004dca6  jz      loc_18004E008
0x18004dcac  mov     rax, [rdi]
0x18004dcaf  mov     rcx, rdi
0x18004dcb2  mov     rax, [rax+8]
0x18004dcb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dcbb  mov     rdx, [rsp+0D80h+pv]; void *
0x18004dcc0  mov     rcx, rdi; this
0x18004dcc3  call    ?Initialize@CTSRpcClient@CTSRpcClientTrackerMgr@@QEAAJPEAX@Z; CTSRpcClientTrackerMgr::CTSRpcClient::Initialize(void *)
0x18004dcc8  mov     ebx, eax
0x18004dcca  test    eax, eax
0x18004dccc  jns     short loc_18004DD34
0x18004dcce  mov     eax, cs:dword_180128170
0x18004dcd4  cmp     eax, 3
0x18004dcd7  jbe     loc_18004E074
0x18004dcdd  lea     rax, aTrackcaller; "TrackCaller"
0x18004dce4  mov     [rsp+0D80h+var_D18], rax
0x18004dce9  mov     [rsp+0D80h+var_D40], ebx
0x18004dced  lea     rax, aPtrrpcclientIn; "ptrRpcClient->Initialize"
0x18004dcf4  mov     [rsp+0D80h+Buffer], rax
0x18004dcf9  lea     rax, aWarningHresult; "Warning HResult failed"
0x18004dd00  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x18004dd05  lea     rax, [rsp+0D80h+var_D18]
0x18004dd0a  mov     [rsp+0D80h+var_D48], rax
0x18004dd0f  lea     rax, [rsp+0D80h+var_D40]
0x18004dd14  mov     [rsp+0D80h+var_D50], rax
0x18004dd19  lea     rax, [rsp+0D80h+Buffer]
0x18004dd1e  mov     [rsp+0D80h+var_D58], rax
0x18004dd23  lea     rax, [rsp+0D80h+pSessionId]
0x18004dd28  lea     rdx, dword_1801072D4
0x18004dd2f  jmp     loc_18004E06A
0x18004dd34  lea     rdx, [r14+638h]; struct CResource *
0x18004dd3b  lea     rcx, [rbp+0C80h+var_D00]; this
0x18004dd3f  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18004dd44  nop
0x18004dd45  add     r14, 6A0h
0x18004dd4c  lea     r8, [rbp+0C80h+var_CF0]
0x18004dd50  mov     rdx, rdi
0x18004dd53  mov     rcx, r14
0x18004dd56  call    ?Lookup@?$CListTree@VCTSRpcClient@CTSRpcClientTrackerMgr@@@@QEAAHPEAVCTSRpcClient@CTSRpcClientTrackerMgr@@PEAPEAV23@@Z; CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(CTSRpcClientTrackerMgr::CTSRpcClient *,CTSRpcClientTrackerMgr::CTSRpcClient * *)
0x18004dd5b  test    eax, eax
0x18004dd5d  jnz     loc_18004DEA8
0x18004dd63  mov     [rsp+0D80h+Buffer], rdi
0x18004dd68  mov     [rsp+0D80h+NewElement], al
0x18004dd6c  lea     r9, [rsp+0D80h+NewElement]; NewElement
0x18004dd71  lea     r8d, [rax+8]; BufferSize
0x18004dd75  lea     rdx, [rsp+0D80h+Buffer]; Buffer
0x18004dd7a  mov     rcx, r14; Table
0x18004dd7d  call    cs:__imp_RtlInsertElementGenericTable
0x18004dd83  test    rax, rax
0x18004dd86  jnz     short loc_18004DE06
0x18004dd88  mov     ecx, 8007000Eh
0x18004dd8d  mov     ebx, ecx
0x18004dd8f  mov     eax, cs:dword_180128170
0x18004dd95  cmp     eax, 3
0x18004dd98  jbe     short loc_18004DDF7
0x18004dd9a  lea     rax, aTrackcaller; "TrackCaller"
0x18004dda1  mov     [rsp+0D80h+var_D18], rax
0x18004dda6  mov     [rsp+0D80h+var_D40], ecx
0x18004ddaa  lea     rax, aMPtrrpcclientl; "m_ptrRpcClientList.Add"
0x18004ddb1  mov     [rsp+0D80h+Buffer], rax
0x18004ddb6  lea     rax, aWarningHresult; "Warning HResult failed"
0x18004ddbd  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x18004ddc2  lea     rax, [rsp+0D80h+var_D18]
0x18004ddc7  mov     [rsp+0D80h+var_D48], rax
0x18004ddcc  lea     rax, [rsp+0D80h+var_D40]
0x18004ddd1  mov     [rsp+0D80h+var_D50], rax
0x18004ddd6  lea     rax, [rsp+0D80h+Buffer]
0x18004dddb  mov     [rsp+0D80h+var_D58], rax
0x18004dde0  lea     rax, [rsp+0D80h+pSessionId]
0x18004dde5  mov     [rsp+0D80h+var_D60], rax
0x18004ddea  lea     rdx, byte_180107313
0x18004ddf1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004ddf6  nop
0x18004ddf7  lea     rcx, [rbp+0C80h+var_D00]; this
0x18004ddfb  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18004de00  nop
0x18004de01  jmp     loc_18004E074
0x18004de06  mov     rcx, [rsp+0D80h+Buffer]
0x18004de0b  mov     rax, [rcx]
0x18004de0e  mov     rax, [rax+8]
0x18004de12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de17  xor     ebx, ebx
0x18004de19  lea     r8, [rbp+0C80h+var_CF0]
0x18004de1d  mov     rdx, rdi
0x18004de20  mov     rcx, r14
0x18004de23  call    ?Lookup@?$CListTree@VCTSRpcClient@CTSRpcClientTrackerMgr@@@@QEAAHPEAVCTSRpcClient@CTSRpcClientTrackerMgr@@PEAPEAV23@@Z; CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(CTSRpcClientTrackerMgr::CTSRpcClient *,CTSRpcClientTrackerMgr::CTSRpcClient * *)
0x18004de28  test    eax, eax
0x18004de2a  jnz     short loc_18004DEA8
0x18004de2c  mov     ebx, 8007054Fh
0x18004de31  mov     eax, cs:dword_180128170
0x18004de37  cmp     eax, 3
0x18004de3a  jbe     short loc_18004DE99
0x18004de3c  lea     rax, aTrackcaller; "TrackCaller"
0x18004de43  mov     [rsp+0D80h+var_D18], rax
0x18004de48  mov     [rsp+0D80h+var_D40], ebx
0x18004de4c  lea     rax, aMPtrrpcclientl_1; "m_ptrRpcClientList.Lookup"
0x18004de53  mov     [rsp+0D80h+Buffer], rax
0x18004de58  lea     rax, aWarningHresult; "Warning HResult failed"
0x18004de5f  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x18004de64  lea     rax, [rsp+0D80h+var_D18]
0x18004de69  mov     [rsp+0D80h+var_D48], rax
0x18004de6e  lea     rax, [rsp+0D80h+var_D40]
0x18004de73  mov     [rsp+0D80h+var_D50], rax
0x18004de78  lea     rax, [rsp+0D80h+Buffer]
0x18004de7d  mov     [rsp+0D80h+var_D58], rax
0x18004de82  lea     rax, [rsp+0D80h+pSessionId]
0x18004de87  mov     [rsp+0D80h+var_D60], rax
0x18004de8c  lea     rdx, word_180107352
0x18004de93  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004de98  nop
0x18004de99  lea     rcx, [rbp+0C80h+var_D00]; this
0x18004de9d  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18004dea2  nop
0x18004dea3  jmp     loc_18004E074
0x18004dea8  lea     rcx, [rbp+0C80h+var_D00]; this
0x18004deac  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18004deb1  nop
0x18004deb2  mov     rdi, [rbp+0C80h+var_CF0]
0x18004deb6  mov     eax, 1
0x18004debb  lock xadd [rdi+644h], eax
0x18004dec3  inc     eax
0x18004dec5  cmp     eax, r15d
0x18004dec8  jle     loc_18004DF9E
0x18004dece  mov     [rsp+0D80h+var_D40], 0
0x18004ded6  mov     [rsp+0D80h+pSessionId], 0
0x18004dede  lea     r9, [rbp+0C80h+var_240]; unsigned __int16 *
0x18004dee5  mov     r8d, 104h; unsigned int
0x18004deeb  lea     rdx, [rsp+0D80h+var_D40]; unsigned int *
0x18004def0  lea     rcx, [rsp+0D80h+pSessionId]; pSessionId
0x18004def5  call    ?GetRpcCallerInfo@CRpcUtils@@SAJPEAK0KPEAG@Z; CRpcUtils::GetRpcCallerInfo(ulong *,ulong *,ulong,ushort *)
0x18004defa  mov     eax, cs:dword_180128170
0x18004df00  cmp     eax, 1
0x18004df03  jbe     short loc_18004DF61
0x18004df05  mov     eax, [rsp+0D80h+pSessionId]
0x18004df09  mov     [rsp+0D80h+var_D18], rax
0x18004df0e  mov     eax, [rsp+0D80h+var_D40]
0x18004df12  mov     [rsp+0D80h+Buffer], rax
0x18004df17  lea     rax, [rbp+0C80h+var_240]
0x18004df1e  mov     [rsp+0D80h+var_D08], rax
0x18004df23  lea     rax, aCallerFailedTo; "Caller failed to be added"
0x18004df2a  mov     [rbp+0C80h+var_D00], rax
0x18004df2e  lea     rax, [rsp+0D80h+var_D18]
0x18004df33  mov     [rsp+0D80h+var_D48], rax
0x18004df38  lea     rax, [rsp+0D80h+Buffer]
0x18004df3d  mov     [rsp+0D80h+var_D50], rax
0x18004df42  lea     rax, [rsp+0D80h+var_D08]
0x18004df47  mov     [rsp+0D80h+var_D58], rax
0x18004df4c  lea     rax, [rbp+0C80h+var_D00]
0x18004df50  mov     [rsp+0D80h+var_D60], rax
0x18004df55  lea     rdx, byte_180107391
0x18004df5c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18004df61  lock dec dword ptr [rdi+644h]
0x18004df68  mov     ebx, 80070005h
0x18004df6d  mov     eax, cs:dword_180128170
0x18004df73  cmp     eax, 3
0x18004df76  jbe     loc_18004E074
0x18004df7c  lea     rax, aTrackcaller; "TrackCaller"
0x18004df83  mov     [rbp+0C80h+var_D00], rax
0x18004df87  mov     dword ptr [rsp+0D80h+Buffer], ebx
0x18004df8b  lea     rax, aPtrfoundIncrem; "ptrFound->IncrementCount() >= MaxCount"
0x18004df92  lea     rdx, word_1801073EE
0x18004df99  jmp     loc_18004E037
0x18004df9e  mov     eax, cs:dword_180128170
0x18004dfa4  cmp     eax, 5
0x18004dfa7  jbe     short loc_18004DFF3
0x18004dfa9  mov     eax, [rdi+644h]
0x18004dfaf  mov     dword ptr [rsp+0D80h+Buffer], eax
0x18004dfb3  call    ?GetClientProcessId@CRpcUtils@@SAKXZ; CRpcUtils::GetClientProcessId(void)
0x18004dfb8  mov     eax, eax
0x18004dfba  mov     [rbp+0C80h+var_D00], rax
0x18004dfbe  lea     rax, aRpcclienttrack_0; "RpcClientTracker added successfully thi"...
0x18004dfc5  mov     [rsp+0D80h+var_D08], rax
0x18004dfca  lea     rax, [rsp+0D80h+Buffer]
0x18004dfcf  mov     [rsp+0D80h+var_D50], rax
0x18004dfd4  lea     rax, [rbp+0C80h+var_D00]
  ... truncated ...
```
