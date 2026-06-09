# CTSRpcClientTrackerMgr::TrackCaller(long,unsigned __int64 *)

- ea: `0x1800500a0`
- end: `0x180050736`
- name: `?TrackCaller@CTSRpcClientTrackerMgr@@UEAAJJPEA_K@Z`
- size: `1686`
- prototype: `__int64 __fastcall(CTSRpcClientTrackerMgr *__hidden this, int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001398`
- `0x1800016a8`
- `0x180001e48`
- `0x180007a80`
- `0x180008010`
- `0x1800095a0`
- `0x180009630`
- `0x180009940`
- `0x18000f610`
- `0x18000f820`
- `0x180012750`
- `0x1800139c0`
- `0x180014c04`
- `0x180015020`
- `0x1800158d4`
- `0x1800159d0`
- `0x180016650`
- `0x180018394`
- `0x180026f68`
- `0x180033f60`
- `0x18003444c`
- `0x1800500a0`
- `0x1800be8c0`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlInsertElementGenericTable` at `0x1800503c3`
- `ntdll!RtlInsertElementGenericTable` at `0x1800503c3`
- `RPCRT4!RpcImpersonateClient` at `0x180050111`
- `RPCRT4!RpcImpersonateClient` at `0x180050111`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800506cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800506cd`

## string_xrefs

- `0x18005013e`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18005016a`: `ImpersonateRpcClient`
- `0x1800501f5`: `GetClientToken`
- `0x18005027f`: `UserName.GetUserSid`
- `0x180050134`: `CImpersonate::ImpersonateRpcClient`

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
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // rax
  char *v13; // rdx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  DWORD *v17; // rax
  __int16 *v18; // rdx
  CTSRpcClientTrackerMgr::CTSRpcClient *v19; // rax
  CTSRpcClientTrackerMgr::CTSRpcClient *v20; // rdi
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  struct _RTL_GENERIC_TABLE *v24; // r14
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  volatile signed __int32 *v30; // rdi
  const char *v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  unsigned int *v36; // [rsp+30h] [rbp-D0h]
  const char **p_Buffer; // [rsp+38h] [rbp-C8h]
  unsigned int v38; // [rsp+40h] [rbp-C0h] BYREF
  const char *Buffer; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v40; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pSessionId[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v43; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v45; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v46[2]; // [rsp+80h] [rbp-80h] BYREF
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
      v9 = dword_18012E170;
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_46;
      pv = "TrackCaller";
      v12 = "GetClientToken";
      v13 = (char *)qword_18010D258;
      goto LABEL_6;
    }
    ClientToken = CUserName::Initialize((CUserName *)v50, v48, 0);
    if ( ClientToken < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_46;
      pv = "TrackCaller";
      v12 = "UserName.Initialize";
      v13 = &byte_18010D297;
      goto LABEL_6;
    }
    ClientToken = CUserName::GetUserSid((CUserName *)v50, (struct _SID **)&pv);
    if ( ClientToken < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_44;
      Buffer = "TrackCaller";
      v38 = ClientToken;
      *(_QWORD *)pSessionId = "UserName.GetUserSid";
      v43 = "Warning HResult failed";
      p_Buffer = &Buffer;
      v36 = &v38;
      v17 = pSessionId;
      v18 = &word_18010D2D6;
      goto LABEL_43;
    }
    v19 = (CTSRpcClientTrackerMgr::CTSRpcClient *)operator new(0x648u, (const struct std::nothrow_t *)std::nothrow);
    v46[0] = v19;
    if ( v19 )
      v20 = CTSRpcClientTrackerMgr::CTSRpcClient::CTSRpcClient(v19);
    else
      v20 = 0;
    v49 = v20;
    if ( v20 )
    {
      (*(void (__fastcall **)(CTSRpcClientTrackerMgr::CTSRpcClient *))(*(_QWORD *)v20 + 8LL))(v20);
      ClientToken = CTSRpcClientTrackerMgr::CTSRpcClient::Initialize(v20, pv);
      if ( ClientToken < 0 )
      {
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v43 = "TrackCaller";
          v38 = ClientToken;
          Buffer = "ptrRpcClient->Initialize";
          *(_QWORD *)pSessionId = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v21,
            (unsigned int)&dword_18010D354,
            v22,
            v23,
            (__int64)pSessionId,
            (__int64)&Buffer,
            (__int64)&v38,
            (__int64)&v43);
        }
        goto LABEL_44;
      }
      CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v46, (CTSRpcClientTrackerMgr *)((char *)this + 1592));
      v24 = (struct _RTL_GENERIC_TABLE *)((char *)this + 1696);
      if ( !(unsigned int)CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(v24, v20, &v47) )
      {
        Buffer = (const char *)v20;
        NewElement[0] = 0;
        if ( !RtlInsertElementGenericTable(v24, &Buffer, 8u, NewElement) )
        {
          ClientToken = -2147024882;
          if ( (unsigned int)dword_18012E170 > 3 )
          {
            v43 = "TrackCaller";
            v38 = -2147024882;
            Buffer = "m_ptrRpcClientList.Add";
            *(_QWORD *)pSessionId = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              -2147024882,
              (unsigned int)byte_18010D393,
              v25,
              v26,
              (__int64)pSessionId,
              (__int64)&Buffer,
              (__int64)&v38,
              (__int64)&v43);
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
          if ( (unsigned int)dword_18012E170 > 3 )
          {
            v43 = "TrackCaller";
            v38 = -2147023537;
            Buffer = "m_ptrRpcClientList.Lookup";
            *(_QWORD *)pSessionId = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v27,
              (unsigned int)word_18010D3D2,
              v28,
              v29,
              (__int64)pSessionId,
              (__int64)&Buffer,
              (__int64)&v38,
              (__int64)&v43);
          }
          goto LABEL_27;
        }
      }
      CAutoLock::Unlock((CAutoLock *)v46);
      v30 = v47;
      if ( _InterlockedIncrement(v47 + 401) <= a2 )
      {
        if ( (unsigned int)dword_18012E170 > 5 )
        {
          LODWORD(Buffer) = *((_DWORD *)v30 + 401);
          v46[0] = CRpcUtils::GetClientProcessId();
          v45 = (unsigned __int16 *)"RpcClientTracker added successfully this RPC Caller";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            v32,
            (unsigned int)byte_18010D4AD,
            v33,
            v34,
            (__int64)&v45,
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
      if ( (unsigned int)dword_18012E170 > 1 )
      {
        v43 = (const char *)pSessionId[0];
        Buffer = (const char *)v38;
        v45 = v51;
        v46[0] = "Caller failed to be added";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v14,
          (unsigned int)byte_18010D411,
          v15,
          v16,
          (__int64)v46,
          (__int64)&v45,
          (__int64)&Buffer,
          (__int64)&v43);
      }
      _InterlockedDecrement(v30 + 401);
      ClientToken = -2147024891;
      if ( (unsigned int)dword_18012E170 <= 3 )
      {
LABEL_44:
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_46;
      }
      v46[0] = "TrackCaller";
      LODWORD(Buffer) = -2147024891;
      v31 = "ptrFound->IncrementCount() >= MaxCount";
      v18 = &word_18010D46E;
    }
    else
    {
      v14 = -2147024882;
      ClientToken = -2147024882;
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_44;
      v46[0] = "TrackCaller";
      LODWORD(Buffer) = -2147024882;
      v31 = "New CTSRpcClient";
      v18 = (__int16 *)byte_18010D315;
    }
    v45 = (unsigned __int16 *)v31;
    v43 = "Warning HResult failed";
    p_Buffer = (const char **)v46;
    v36 = (unsigned int *)&Buffer;
    v17 = (DWORD *)&v45;
LABEL_43:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v18,
      v15,
      v16,
      (__int64)&v43,
      (__int64)v17,
      (__int64)v36,
      (__int64)p_Buffer);
    goto LABEL_44;
  }
  _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", ClientToken, "CImpersonate::ImpersonateRpcClient");
  if ( (unsigned int)dword_18012E170 > 3 )
  {
    pv = "TrackCaller";
    v12 = "ImpersonateRpcClient";
    v13 = byte_18010D219;
LABEL_6:
    Buffer = v12;
    *(_QWORD *)pSessionId = "Warning HResult failed";
    v38 = ClientToken;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v9,
      (_DWORD)v13,
      v10,
      v11,
      (__int64)pSessionId,
      (__int64)&Buffer,
      (__int64)&v38,
      (__int64)&pv);
  }
LABEL_46:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v47);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v49);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v48);
  CUserName::~CUserName((CUserName *)v50);
  CImpersonate::StopImpersonating((CImpersonate *)&v40);
  return (unsigned int)ClientToken;
}

```

## disassembly

```asm
0x1800500a0  mov     [rsp-8+arg_8], rbx
0x1800500a5  push    rbp
0x1800500a6  push    rdi
0x1800500a7  push    r12
0x1800500a9  push    r14
0x1800500ab  push    r15
0x1800500ad  lea     rbp, [rsp-0C60h]
0x1800500b5  sub     rsp, 0D60h
0x1800500bc  mov     rax, cs:__security_cookie
0x1800500c3  xor     rax, rsp
0x1800500c6  mov     [rbp+0C80h+var_30], rax
0x1800500cd  mov     r12, r8
0x1800500d0  mov     r15d, edx
0x1800500d3  mov     r14, rcx
0x1800500d6  mov     [rsp+0D80h+var_D30], 0
0x1800500dd  lea     rcx, [rbp+0C80h+var_CD0]; this
0x1800500e1  call    ??0CUserName@@QEAA@XZ; CUserName::CUserName(void)
0x1800500e6  nop
0x1800500e7  mov     [rbp+0C80h+var_CE8], 0
0x1800500ef  mov     [rsp+0D80h+pv], 0
0x1800500f8  mov     [rbp+0C80h+var_CE0], 0
0x180050100  mov     [rbp+0C80h+var_CF0], 0
0x180050108  xor     edx, edx; void *
0x18005010a  call    ?CheckCurrentContext@CImpersonate@@AEAAJPEAX@Z; CImpersonate::CheckCurrentContext(void *)
0x18005010f  xor     ecx, ecx; BindingHandle
0x180050111  call    cs:__imp_RpcImpersonateClient
0x180050118  nop     dword ptr [rax+rax+00h]
0x18005011d  mov     ebx, eax
0x18005011f  test    eax, eax
0x180050121  jle     short loc_18005012C
0x180050123  movzx   ebx, ax
0x180050126  or      ebx, 80070000h
0x18005012c  test    ebx, ebx
0x18005012e  jns     loc_1800501BF
0x180050134  lea     r9, aCimpersonateIm_0; "CImpersonate::ImpersonateRpcClient"
0x18005013b  mov     r8d, ebx
0x18005013e  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180050145  mov     ecx, 8; int
0x18005014a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005014f  mov     eax, cs:dword_18012E170
0x180050155  cmp     eax, 3
0x180050158  jbe     loc_1800506DA
0x18005015e  lea     rax, aTrackcaller; "TrackCaller"
0x180050165  mov     [rsp+0D80h+pv], rax
0x18005016a  lea     rax, aImpersonaterpc; "ImpersonateRpcClient"
0x180050171  lea     rdx, byte_18010D219
0x180050178  mov     [rsp+0D80h+Buffer], rax
0x18005017d  lea     rax, aWarningHresult; "Warning HResult failed"
0x180050184  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x180050189  lea     rax, [rsp+0D80h+pv]
0x18005018e  mov     [rsp+0D80h+var_D48], rax
0x180050193  lea     rax, [rsp+0D80h+var_D40]
0x180050198  mov     [rsp+0D80h+var_D50], rax
0x18005019d  lea     rax, [rsp+0D80h+Buffer]
0x1800501a2  mov     [rsp+0D80h+var_D58], rax
0x1800501a7  lea     rax, [rsp+0D80h+pSessionId]
0x1800501ac  mov     [rsp+0D80h+var_D40], ebx
0x1800501b0  mov     [rsp+0D80h+var_D60], rax
0x1800501b5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800501ba  jmp     loc_1800506DA
0x1800501bf  mov     [rsp+0D80h+var_D30], 101h
0x1800501c6  mov     edx, 1; int
0x1800501cb  lea     rcx, [rbp+0C80h+var_CE8]; void **
0x1800501cf  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x1800501d4  mov     ebx, eax
0x1800501d6  test    eax, eax
0x1800501d8  jns     short loc_180050208
0x1800501da  mov     ecx, cs:dword_18012E170
0x1800501e0  cmp     ecx, 3
0x1800501e3  jbe     loc_1800506DA
0x1800501e9  lea     rax, aTrackcaller; "TrackCaller"
0x1800501f0  mov     [rsp+0D80h+pv], rax
0x1800501f5  lea     rax, aGetclienttoken; "GetClientToken"
0x1800501fc  lea     rdx, qword_18010D258
0x180050203  jmp     loc_180050178
0x180050208  xor     r8d, r8d; int
0x18005020b  mov     rdx, [rbp+0C80h+var_CE8]; void *
0x18005020f  lea     rcx, [rbp+0C80h+var_CD0]; this
0x180050213  call    ?Initialize@CUserName@@UEAAJ_KH@Z; CUserName::Initialize(unsigned __int64,int)
0x180050218  mov     ebx, eax
0x18005021a  test    eax, eax
0x18005021c  jns     short loc_18005024C
0x18005021e  mov     eax, cs:dword_18012E170
0x180050224  cmp     eax, 3
0x180050227  jbe     loc_1800506DA
0x18005022d  lea     rax, aTrackcaller; "TrackCaller"
0x180050234  mov     [rsp+0D80h+pv], rax
0x180050239  lea     rax, aUsernameInitia; "UserName.Initialize"
0x180050240  lea     rdx, byte_18010D297
0x180050247  jmp     loc_180050178
0x18005024c  lea     rdx, [rsp+0D80h+pv]; struct _SID **
0x180050251  lea     rcx, [rbp+0C80h+var_CD0]; this
0x180050255  call    ?GetUserSid@CUserName@@UEAAJPEAPEAU_SID@@@Z; CUserName::GetUserSid(_SID * *)
0x18005025a  mov     ebx, eax
0x18005025c  test    eax, eax
0x18005025e  jns     short loc_1800502BC
0x180050260  mov     eax, cs:dword_18012E170
0x180050266  cmp     eax, 3
0x180050269  jbe     loc_1800506C0
0x18005026f  lea     rax, aTrackcaller; "TrackCaller"
0x180050276  mov     [rsp+0D80h+Buffer], rax
0x18005027b  mov     [rsp+0D80h+var_D40], ebx
0x18005027f  lea     rax, aUsernameGetuse; "UserName.GetUserSid"
0x180050286  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x18005028b  lea     rax, aWarningHresult; "Warning HResult failed"
0x180050292  mov     [rsp+0D80h+var_D18], rax
0x180050297  lea     rax, [rsp+0D80h+Buffer]
0x18005029c  mov     [rsp+0D80h+var_D48], rax
0x1800502a1  lea     rax, [rsp+0D80h+var_D40]
0x1800502a6  mov     [rsp+0D80h+var_D50], rax
0x1800502ab  lea     rax, [rsp+0D80h+pSessionId]
0x1800502b0  lea     rdx, word_18010D2D6
0x1800502b7  jmp     loc_1800506AC
0x1800502bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800502c3  mov     ecx, 648h; unsigned __int64
0x1800502c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800502cd  mov     [rbp+0C80h+var_D00], rax
0x1800502d1  test    rax, rax
0x1800502d4  jz      short loc_1800502E3
0x1800502d6  mov     rcx, rax; this
0x1800502d9  call    ??0CTSRpcClient@CTSRpcClientTrackerMgr@@QEAA@XZ; CTSRpcClientTrackerMgr::CTSRpcClient::CTSRpcClient(void)
0x1800502de  mov     rdi, rax
0x1800502e1  jmp     short loc_1800502E5
0x1800502e3  xor     edi, edi
0x1800502e5  mov     [rbp+0C80h+var_CE0], rdi
0x1800502e9  test    rdi, rdi
0x1800502ec  jz      loc_180050654
0x1800502f2  mov     rax, [rdi]
0x1800502f5  mov     rcx, rdi
0x1800502f8  mov     rax, [rax+8]
0x1800502fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050301  mov     rdx, [rsp+0D80h+pv]; void *
0x180050306  mov     rcx, rdi; this
0x180050309  call    ?Initialize@CTSRpcClient@CTSRpcClientTrackerMgr@@QEAAJPEAX@Z; CTSRpcClientTrackerMgr::CTSRpcClient::Initialize(void *)
0x18005030e  mov     ebx, eax
0x180050310  test    eax, eax
0x180050312  jns     short loc_18005037A
0x180050314  mov     eax, cs:dword_18012E170
0x18005031a  cmp     eax, 3
0x18005031d  jbe     loc_1800506C0
0x180050323  lea     rax, aTrackcaller; "TrackCaller"
0x18005032a  mov     [rsp+0D80h+var_D18], rax
0x18005032f  mov     [rsp+0D80h+var_D40], ebx
0x180050333  lea     rax, aPtrrpcclientIn; "ptrRpcClient->Initialize"
0x18005033a  mov     [rsp+0D80h+Buffer], rax
0x18005033f  lea     rax, aWarningHresult; "Warning HResult failed"
0x180050346  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x18005034b  lea     rax, [rsp+0D80h+var_D18]
0x180050350  mov     [rsp+0D80h+var_D48], rax
0x180050355  lea     rax, [rsp+0D80h+var_D40]
0x18005035a  mov     [rsp+0D80h+var_D50], rax
0x18005035f  lea     rax, [rsp+0D80h+Buffer]
0x180050364  mov     [rsp+0D80h+var_D58], rax
0x180050369  lea     rax, [rsp+0D80h+pSessionId]
0x18005036e  lea     rdx, dword_18010D354
0x180050375  jmp     loc_1800506B6
0x18005037a  lea     rdx, [r14+638h]; struct CResource *
0x180050381  lea     rcx, [rbp+0C80h+var_D00]; this
0x180050385  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18005038a  nop
0x18005038b  add     r14, 6A0h
0x180050392  lea     r8, [rbp+0C80h+var_CF0]
0x180050396  mov     rdx, rdi
0x180050399  mov     rcx, r14
0x18005039c  call    ?Lookup@?$CListTree@VCTSRpcClient@CTSRpcClientTrackerMgr@@@@QEAAHPEAVCTSRpcClient@CTSRpcClientTrackerMgr@@PEAPEAV23@@Z; CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(CTSRpcClientTrackerMgr::CTSRpcClient *,CTSRpcClientTrackerMgr::CTSRpcClient * *)
0x1800503a1  test    eax, eax
0x1800503a3  jnz     loc_1800504F4
0x1800503a9  mov     [rsp+0D80h+Buffer], rdi
0x1800503ae  mov     [rsp+0D80h+NewElement], al
0x1800503b2  lea     r9, [rsp+0D80h+NewElement]; NewElement
0x1800503b7  lea     r8d, [rax+8]; BufferSize
0x1800503bb  lea     rdx, [rsp+0D80h+Buffer]; Buffer
0x1800503c0  mov     rcx, r14; Table
0x1800503c3  call    cs:__imp_RtlInsertElementGenericTable
0x1800503ca  nop     dword ptr [rax+rax+00h]
0x1800503cf  test    rax, rax
0x1800503d2  jnz     short loc_180050452
0x1800503d4  mov     ecx, 8007000Eh
0x1800503d9  mov     ebx, ecx
0x1800503db  mov     eax, cs:dword_18012E170
0x1800503e1  cmp     eax, 3
0x1800503e4  jbe     short loc_180050443
0x1800503e6  lea     rax, aTrackcaller; "TrackCaller"
0x1800503ed  mov     [rsp+0D80h+var_D18], rax
0x1800503f2  mov     [rsp+0D80h+var_D40], ecx
0x1800503f6  lea     rax, aMPtrrpcclientl; "m_ptrRpcClientList.Add"
0x1800503fd  mov     [rsp+0D80h+Buffer], rax
0x180050402  lea     rax, aWarningHresult; "Warning HResult failed"
0x180050409  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x18005040e  lea     rax, [rsp+0D80h+var_D18]
0x180050413  mov     [rsp+0D80h+var_D48], rax
0x180050418  lea     rax, [rsp+0D80h+var_D40]
0x18005041d  mov     [rsp+0D80h+var_D50], rax
0x180050422  lea     rax, [rsp+0D80h+Buffer]
0x180050427  mov     [rsp+0D80h+var_D58], rax
0x18005042c  lea     rax, [rsp+0D80h+pSessionId]
0x180050431  mov     [rsp+0D80h+var_D60], rax
0x180050436  lea     rdx, byte_18010D393
0x18005043d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180050442  nop
0x180050443  lea     rcx, [rbp+0C80h+var_D00]; this
0x180050447  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18005044c  nop
0x18005044d  jmp     loc_1800506C0
0x180050452  mov     rcx, [rsp+0D80h+Buffer]
0x180050457  mov     rax, [rcx]
0x18005045a  mov     rax, [rax+8]
0x18005045e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050463  xor     ebx, ebx
0x180050465  lea     r8, [rbp+0C80h+var_CF0]
0x180050469  mov     rdx, rdi
0x18005046c  mov     rcx, r14
0x18005046f  call    ?Lookup@?$CListTree@VCTSRpcClient@CTSRpcClientTrackerMgr@@@@QEAAHPEAVCTSRpcClient@CTSRpcClientTrackerMgr@@PEAPEAV23@@Z; CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(CTSRpcClientTrackerMgr::CTSRpcClient *,CTSRpcClientTrackerMgr::CTSRpcClient * *)
0x180050474  test    eax, eax
0x180050476  jnz     short loc_1800504F4
0x180050478  mov     ebx, 8007054Fh
0x18005047d  mov     eax, cs:dword_18012E170
0x180050483  cmp     eax, 3
0x180050486  jbe     short loc_1800504E5
0x180050488  lea     rax, aTrackcaller; "TrackCaller"
0x18005048f  mov     [rsp+0D80h+var_D18], rax
0x180050494  mov     [rsp+0D80h+var_D40], ebx
0x180050498  lea     rax, aMPtrrpcclientl_1; "m_ptrRpcClientList.Lookup"
0x18005049f  mov     [rsp+0D80h+Buffer], rax
0x1800504a4  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800504ab  mov     qword ptr [rsp+0D80h+pSessionId], rax
0x1800504b0  lea     rax, [rsp+0D80h+var_D18]
0x1800504b5  mov     [rsp+0D80h+var_D48], rax
0x1800504ba  lea     rax, [rsp+0D80h+var_D40]
0x1800504bf  mov     [rsp+0D80h+var_D50], rax
0x1800504c4  lea     rax, [rsp+0D80h+Buffer]
0x1800504c9  mov     [rsp+0D80h+var_D58], rax
0x1800504ce  lea     rax, [rsp+0D80h+pSessionId]
0x1800504d3  mov     [rsp+0D80h+var_D60], rax
0x1800504d8  lea     rdx, word_18010D3D2
0x1800504df  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800504e4  nop
0x1800504e5  lea     rcx, [rbp+0C80h+var_D00]; this
0x1800504e9  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800504ee  nop
0x1800504ef  jmp     loc_1800506C0
0x1800504f4  lea     rcx, [rbp+0C80h+var_D00]; this
0x1800504f8  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800504fd  nop
0x1800504fe  mov     rdi, [rbp+0C80h+var_CF0]
0x180050502  mov     eax, 1
0x180050507  lock xadd [rdi+644h], eax
0x18005050f  inc     eax
0x180050511  cmp     eax, r15d
0x180050514  jle     loc_1800505EA
0x18005051a  mov     [rsp+0D80h+var_D40], 0
0x180050522  mov     [rsp+0D80h+pSessionId], 0
0x18005052a  lea     r9, [rbp+0C80h+var_240]; unsigned __int16 *
0x180050531  mov     r8d, 104h; unsigned int
0x180050537  lea     rdx, [rsp+0D80h+var_D40]; unsigned int *
0x18005053c  lea     rcx, [rsp+0D80h+pSessionId]; pSessionId
0x180050541  call    ?GetRpcCallerInfo@CRpcUtils@@SAJPEAK0KPEAG@Z; CRpcUtils::GetRpcCallerInfo(ulong *,ulong *,ulong,ushort *)
0x180050546  mov     eax, cs:dword_18012E170
0x18005054c  cmp     eax, 1
0x18005054f  jbe     short loc_1800505AD
0x180050551  mov     eax, [rsp+0D80h+pSessionId]
0x180050555  mov     [rsp+0D80h+var_D18], rax
0x18005055a  mov     eax, [rsp+0D80h+var_D40]
0x18005055e  mov     [rsp+0D80h+Buffer], rax
0x180050563  lea     rax, [rbp+0C80h+var_240]
0x18005056a  mov     [rsp+0D80h+var_D08], rax
0x18005056f  lea     rax, aCallerFailedTo; "Caller failed to be added"
0x180050576  mov     [rbp+0C80h+var_D00], rax
0x18005057a  lea     rax, [rsp+0D80h+var_D18]
0x18005057f  mov     [rsp+0D80h+var_D48], rax
0x180050584  lea     rax, [rsp+0D80h+Buffer]
0x180050589  mov     [rsp+0D80h+var_D50], rax
0x18005058e  lea     rax, [rsp+0D80h+var_D08]
0x180050593  mov     [rsp+0D80h+var_D58], rax
0x180050598  lea     rax, [rbp+0C80h+var_D00]
0x18005059c  mov     [rsp+0D80h+var_D60], rax
0x1800505a1  lea     rdx, byte_18010D411
0x1800505a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800505ad  lock dec dword ptr [rdi+644h]
0x1800505b4  mov     ebx, 80070005h
0x1800505b9  mov     eax, cs:dword_18012E170
0x1800505bf  cmp     eax, 3
0x1800505c2  jbe     loc_1800506C0
0x1800505c8  lea     rax, aTrackcaller; "TrackCaller"
0x1800505cf  mov     [rbp+0C80h+var_D00], rax
0x1800505d3  mov     dword ptr [rsp+0D80h+Buffer], ebx
0x1800505d7  lea     rax, aPtrfoundIncrem; "ptrFound->IncrementCount() >= MaxCount"
0x1800505de  lea     rdx, word_18010D46E
0x1800505e5  jmp     loc_180050683
0x1800505ea  mov     eax, cs:dword_18012E170
0x1800505f0  cmp     eax, 5
0x1800505f3  jbe     short loc_18005063F
0x1800505f5  mov     eax, [rdi+644h]
0x1800505fb  mov     dword ptr [rsp+0D80h+Buffer], eax
0x1800505ff  call    ?GetClientProcessId@CRpcUtils@@SAKXZ; CRpcUtils::GetClientProcessId(void)
0x180050604  mov     eax, eax
0x180050606  mov     [rbp+0C80h+var_D00], rax
0x18005060a  lea     rax, aRpcclienttrack_0; "RpcClientTracker added successfully thi"...
0x180050611  mov     [rsp+0D80h+var_D08], rax
0x180050616  lea     rax, [rsp+0D80h+Buffer]
  ... truncated ...
```
