# RpcGetInitialApplication

- ea: `0x180060ee0`
- end: `0x180061690`
- name: `RpcGetInitialApplication`
- size: `1968`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001a50`
- `0x180008920`
- `0x180009940`
- `0x18000ba50`
- `0x18000f760`
- `0x1800139c0`
- `0x180015310`
- `0x180016d6c`
- `0x180033f60`
- `0x18003440c`
- `0x18003444c`
- `0x180034e64`
- `0x18004fecc`
- `0x1800519e8`
- `0x18005ef60`
- `0x180060ee0`
- `0x1800ca374`
- `0x1800caed0`
- `0x1800ce010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800615a4`
- `RPCRT4!RpcRevertToSelf` at `0x1800615a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006119f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006142b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180061523`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006119f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006142b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180061523`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800615e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800615fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800615e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800615fc`

## string_xrefs

- `0x1800611e3`: `StringCchCopy failed: 0x%x in %s`
- `0x180061460`: `StringCchCopy failed: 0x%x in %s`
- `0x180061560`: `StringCchCopy failed: 0x%x in %s`
- `0x180060fac`: `ppWorkDirectory`
- `0x180061293`: `Session is worker, debug, or agent, return default`
- `0x18006135d`: `Session->GetConfigData failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcGetInitialApplication(
        __int64 a1,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        _BYTE *a5,
        bool *a6)
{
  char *v6; // r13
  unsigned __int16 *v10; // rsi
  const char *v11; // r8
  int v12; // ebx
  int v13; // eax
  int v14; // ecx
  int v15; // r9d
  unsigned __int16 *v16; // r14
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  const char *v21; // rdx
  unsigned __int16 *v22; // rbx
  unsigned __int16 *v23; // rax
  int v24; // eax
  char *v25; // rax
  int v26; // eax
  int v27; // eax
  unsigned __int64 v28; // rbx
  unsigned __int16 *v29; // rax
  int v30; // eax
  char v31; // r14
  const char *v32; // r9
  int v33; // eax
  unsigned __int64 v34; // rbx
  unsigned __int16 *v35; // rax
  int v36; // eax
  int v37; // eax
  bool v38; // sf
  __int64 v39; // rcx
  _BYTE *v40; // rax
  unsigned __int16 *v42; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v43; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v44; // [rsp+40h] [rbp-C0h] BYREF
  int TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  int v46; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 **v47; // [rsp+50h] [rbp-B0h]
  struct ITSSession *v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  struct IConnection *v50; // [rsp+68h] [rbp-98h] BYREF
  struct ITerminal *v51; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 **v52; // [rsp+78h] [rbp-88h]
  __int128 Buf2; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v54[592]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v55[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v6 = 0;
  v47 = a3;
  v52 = a4;
  v51 = 0;
  v49 = 0;
  TokenHandle = 0;
  v44 = 0;
  v10 = 0;
  v43 = 0;
  v46 = 0;
  v50 = 0;
  Buf2 = 0;
  v48 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v54, 1, "RpcGetInitialApplication");
  if ( !a3 )
  {
    v11 = "ppCmdLine";
LABEL_3:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v11, "RpcGetInitialApplication");
    v12 = -2147024809;
    goto LABEL_97;
  }
  if ( !a4 )
  {
    v11 = "ppWorkDirectory";
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v11 = "pbAppAllowed";
    goto LABEL_3;
  }
  if ( !a6 )
  {
    v11 = "pbMaximize";
    goto LABEL_3;
  }
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  v42 = 0;
  v13 = RCMRpcPrologueEx(a2, 1u, 0, &v51, &v48, &TokenHandle);
  v12 = v13;
  if ( v13 >= 0 )
  {
    v12 = 0;
    if ( (*(int (__fastcall **)(struct ITSSession *, __int128 *))(*(_QWORD *)v48 + 168LL))(v48, &Buf2) >= 0
      && (!memcmp_0(TERMINAL_TYPE_WORKER, &Buf2, 0x10u)
       || !memcmp_0(&TERMINAL_TYPE_DEBUG, &Buf2, 0x10u)
       || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl)
       && !memcmp_0(&TERMINAL_TYPE_AGENT, &Buf2, 0x10u)) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl) )
      {
        if ( (g_DebugTraceComponent & 1) != 0 )
          _DbgPrintMessage(2, "Session is worker, debug, or agent, return default");
      }
      else if ( (g_DebugTraceComponent & 1) != 0 )
      {
        _DbgPrintMessage(2, "Session is worker or debug, return default");
      }
      *v47 = 0;
      *a4 = 0;
      *a5 = 1;
      *a6 = 1;
      goto LABEL_23;
    }
    if ( !TokenHandle )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (**(int (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v51)(v51, qword_1800DD390, &v49) < 0 )
    {
      v12 = -2147022646;
      _DbgPrintMessage(4, "QI on IID_IRemoteTerminal failed: 0x%x in %s", 2147944650LL, "RpcGetInitialApplication");
      goto LABEL_13;
    }
    v25 = (char *)operator new(0xA68u, (const struct std::nothrow_t *)std::nothrow);
    v6 = v25;
    if ( !v25 )
    {
      v12 = -2147024882;
      goto LABEL_13;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v49 + 240LL))(v49, v25, 2664);
    v16 = 0;
    v12 = v20;
    if ( v20 < 0 )
    {
      v21 = "Session->GetConfigData failed: 0x%x in %s";
      goto LABEL_28;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, struct IConnection **))(*(_QWORD *)v49 + 368LL))(v49, &v50);
    v12 = v20;
    if ( v20 < 0 )
    {
      v21 = "GetConnection failed: 0x%x in %s";
      goto LABEL_28;
    }
    v26 = ApplyTSAllowPolicyToInitialProgram(v50, (struct _USERCONFIGW *)(v6 + 124), &v44, &v46);
    v12 = v26;
    if ( v26 == -804847614 || v26 == -2147024894 )
    {
      v43 = 0;
      v33 = StringCbLengthW((const unsigned __int16 *)v6 + 377, 0x202u, &v43);
      v12 = v33;
      if ( v33 >= 0 )
      {
        v34 = v43;
        v35 = (unsigned __int16 *)LocalAlloc(0x40u, v43 + 2);
        v10 = v35;
        if ( v35 )
        {
          v36 = StringCbCopyW(v35, v34 + 2, (const unsigned __int16 *)v6 + 377);
          v16 = 0;
          v12 = v36;
          if ( v36 < 0 )
          {
            _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v36, "RpcGetInitialApplication");
            goto LABEL_83;
          }
          v12 = -2147024894;
          *v47 = v10;
          v10 = 0;
          goto LABEL_81;
        }
        v12 = -2147024882;
      }
      else
      {
        _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", v33, "RpcGetInitialApplication");
        v10 = v44;
      }
LABEL_82:
      v16 = v42;
      goto LABEL_83;
    }
    if ( v26 < 0 )
    {
      v10 = v44;
LABEL_81:
      _DbgPrintMessage(8, "ApplyTSAllowPolicyToInitialProgram failed: 0x%x in %s", v12, "RpcGetInitialApplication");
      goto LABEL_82;
    }
    if ( *((_WORD *)v6 + 120) )
    {
      v27 = StringCbLengthW((const unsigned __int16 *)v6 + 120, 0x202u, &v43);
      v12 = v27;
      if ( v27 < 0 )
      {
        _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", (unsigned int)v27, "RpcGetInitialApplication");
LABEL_64:
        v10 = v44;
        goto LABEL_83;
      }
      v28 = v43;
      v29 = (unsigned __int16 *)LocalAlloc(0x40u, v43 + 2);
      v42 = v29;
      v16 = v29;
      if ( !v29 )
      {
        v12 = -2147024882;
        goto LABEL_64;
      }
      v30 = StringCbCopyW(v29, v28 + 2, (const unsigned __int16 *)v6 + 120);
      v12 = v30;
      if ( v30 < 0 )
      {
        _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", (unsigned int)v30, "RpcGetInitialApplication");
        goto LABEL_64;
      }
    }
    v10 = v44;
    v31 = v46;
    if ( (g_DebugTraceComponent & 1) != 0 )
    {
      v32 = "TRUE";
      if ( !v46 )
        v32 = "FALSE";
      _DbgPrintMessage(2, "Session initial program is %ws, app allowed to run is %s", v44, v32);
    }
    *v47 = v10;
    *v52 = v42;
    *a5 = v31;
    *a6 = (*((_DWORD *)v6 + 31) & 0x10000000) != 0;
    goto LABEL_82;
  }
  if ( v13 == -2147022646 )
  {
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v43 = (unsigned __int64)"Got queried for initial program in disconnected state, returning what we know";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v14,
        (unsigned int)&dword_18010F454,
        -2147022646,
        v15,
        (__int64)&v43);
    }
    memset_0(v55, 0, 0x202u);
    (*(void (__fastcall **)(struct ITSSession *, unsigned __int16 *))(*(_QWORD *)v48 + 192LL))(v48, v55);
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v43 = (unsigned __int64)v55;
      v44 = (unsigned __int16 *)"Got InitialProgram from session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)byte_18010F423,
        v18,
        v19,
        (__int64)&v44,
        (__int64)&v43);
    }
    if ( !v55[0] )
    {
      if ( (unsigned int)dword_18012E170 > 5 )
      {
        v43 = (unsigned __int64)"Got empty InitialProgram from session, returning.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v17,
          (unsigned int)&byte_18010F3FF,
          v18,
          v19,
          (__int64)&v43);
      }
      *a5 = 1;
      goto LABEL_22;
    }
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      v43 = (unsigned __int64)"BUG: 23297910 - This is not the right way to return the initial program it will probably not work.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v17,
        (unsigned int)byte_18010F3DB,
        v18,
        v19,
        (__int64)&v43);
    }
    *a5 = 1;
    v44 = 0;
    v20 = StringCbLengthW(v55, 0x202u, (unsigned __int64 *)&v44);
    v12 = v20;
    if ( v20 >= 0 )
    {
      v22 = v44;
      v23 = (unsigned __int16 *)LocalAlloc(0x40u, (SIZE_T)(v44 + 1));
      v10 = v23;
      if ( v23 )
      {
        v24 = StringCbCopyW(v23, (unsigned __int64)(v22 + 1), v55);
        v12 = v24;
        if ( v24 >= 0 )
        {
          *v47 = v10;
LABEL_22:
          v12 = 0;
LABEL_23:
          v16 = 0;
          goto LABEL_83;
        }
        _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v24, "RpcGetInitialApplication");
      }
      else
      {
        v12 = -2147024882;
      }
      v16 = 0;
      goto LABEL_83;
    }
    v21 = "StringCchLength failed: 0x%x in %s";
LABEL_28:
    _DbgPrintMessage(8, v21, (unsigned int)v20, "RpcGetInitialApplication");
    goto LABEL_13;
  }
  _DbgPrintMessage(1, "RCMRpcPrologue failed: 0x%x", v13);
LABEL_13:
  v16 = 0;
LABEL_83:
  if ( TokenHandle )
  {
    v37 = RpcRevertToSelf();
    v38 = v37 < 0;
    if ( v37 > 0 )
    {
      v37 = (unsigned __int16)v37 | 0x80070000;
      v38 = v37 < 0;
    }
    if ( v38 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v37);
      v12 = -2147024891;
LABEL_89:
      if ( v10 )
        LocalFree(v10);
      if ( v16 )
        LocalFree(v16);
      goto LABEL_93;
    }
  }
  if ( v12 < 0 )
    goto LABEL_89;
LABEL_93:
  if ( v6 )
  {
    v39 = 30;
    v40 = v6 + 210;
    do
    {
      *v40++ = 0;
      --v39;
    }
    while ( v39 );
    operator delete(v6);
  }
LABEL_97:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v54);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v48);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v50);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v49);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v51);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180060ee0  mov     [rsp-8+arg_0], rbx
0x180060ee5  push    rbp
0x180060ee6  push    rsi
0x180060ee7  push    rdi
0x180060ee8  push    r12
0x180060eea  push    r13
0x180060eec  push    r14
0x180060eee  push    r15
0x180060ef0  lea     rbp, [rsp-410h]
0x180060ef8  sub     rsp, 510h
0x180060eff  mov     rax, cs:__security_cookie
0x180060f06  xor     rax, rsp
0x180060f09  mov     [rbp+440h+var_40], rax
0x180060f10  mov     r15, [rbp+440h+arg_20]
0x180060f17  lea     rcx, [rbp+440h+var_4A0]; this
0x180060f1b  mov     r12, [rbp+440h+arg_28]
0x180060f22  xor     r13d, r13d
0x180060f25  mov     rdi, r8
0x180060f28  mov     [rsp+540h+var_4F0], r8
0x180060f2d  mov     ebx, edx
0x180060f2f  mov     [rsp+540h+var_4C8], r9
0x180060f34  xorps   xmm0, xmm0
0x180060f37  mov     [rsp+540h+var_4D0], r13
0x180060f3c  lea     edx, [r13+1]; int
0x180060f40  mov     [rsp+540h+var_4E0], r13
0x180060f45  lea     r8, aRpcgetinitiala; "RpcGetInitialApplication"
0x180060f4c  mov     [rsp+540h+var_4F8], r13d
0x180060f51  mov     r14, r9
0x180060f54  mov     [rsp+540h+var_500], r13
0x180060f59  mov     esi, r13d
0x180060f5c  mov     [rsp+540h+var_508], r13
0x180060f61  mov     [rsp+540h+var_4F4], r13d
0x180060f66  mov     [rsp+540h+var_4D8], r13
0x180060f6b  movups  [rbp+440h+Buf2], xmm0
0x180060f6f  mov     [rsp+540h+var_4E8], r13
0x180060f74  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180060f79  test    rdi, rdi
0x180060f7c  jnz     short loc_180060FA7
0x180060f7e  lea     r8, aPpcmdline; "ppCmdLine"
0x180060f85  lea     r9, aRpcgetinitiala; "RpcGetInitialApplication"
0x180060f8c  mov     ecx, 8; int
0x180060f91  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180060f98  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060f9d  mov     ebx, 80070057h
0x180060fa2  jmp     loc_180061632
0x180060fa7  test    r14, r14
0x180060faa  jnz     short loc_180060FB5
0x180060fac  lea     r8, aPpworkdirector; "ppWorkDirectory"
0x180060fb3  jmp     short loc_180060F85
0x180060fb5  test    r15, r15
0x180060fb8  jnz     short loc_180060FC3
0x180060fba  lea     r8, aPbappallowed; "pbAppAllowed"
0x180060fc1  jmp     short loc_180060F85
0x180060fc3  test    r12, r12
0x180060fc6  jnz     short loc_180060FD1
0x180060fc8  lea     r8, aPbmaximize; "pbMaximize"
0x180060fcf  jmp     short loc_180060F85
0x180060fd1  xor     eax, eax
0x180060fd3  lea     r9, [rsp+540h+var_4D0]; struct ITerminal **
0x180060fd8  mov     [rdi], rax
0x180060fdb  xor     r8d, r8d; int
0x180060fde  mov     [r14], rax
0x180060fe1  mov     ecx, ebx; unsigned int
0x180060fe3  mov     [r15], al
0x180060fe6  mov     [r12], al
0x180060fea  mov     [rsp+540h+var_510], rax
0x180060fef  lea     edx, [r8+1]; unsigned int
0x180060ff3  lea     rax, [rsp+540h+var_4F8]
0x180060ff8  mov     [rsp+540h+TokenHandle], rax; TokenHandle
0x180060ffd  lea     rax, [rsp+540h+var_4E8]
0x180061002  mov     [rsp+540h+var_520], rax; struct ITSSession **
0x180061007  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18006100c  mov     ebx, eax
0x18006100e  mov     edi, 8
0x180061013  test    eax, eax
0x180061015  jns     loc_180061200
0x18006101b  mov     r8d, 800708CAh
0x180061021  cmp     eax, r8d
0x180061024  jz      short loc_180061040
0x180061026  mov     r8d, eax
0x180061029  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x180061030  lea     ecx, [rdi-7]; int
0x180061033  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180061038  mov     r14, rsi
0x18006103b  jmp     loc_18006159D
0x180061040  mov     eax, cs:dword_18012E170
0x180061046  cmp     eax, 5
0x180061049  jbe     short loc_18006106D
0x18006104b  lea     rax, aGotQueriedForI; "Got queried for initial program in disc"...
0x180061052  mov     [rsp+540h+var_508], rax
0x180061057  lea     rdx, dword_18010F454
0x18006105e  lea     rax, [rsp+540h+var_508]
0x180061063  mov     [rsp+540h+var_520], rax
0x180061068  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006106d  mov     ebx, 202h
0x180061072  lea     rcx, [rbp+440h+var_250]; void *
0x180061079  mov     r8d, ebx; Size
0x18006107c  xor     edx, edx; Val
0x18006107e  call    memset_0
0x180061083  mov     rcx, [rsp+540h+var_4E8]
0x180061088  lea     rdx, [rbp+440h+var_250]
0x18006108f  mov     rax, [rcx]
0x180061092  mov     rax, [rax+0C0h]
0x180061099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006109e  mov     eax, cs:dword_18012E170
0x1800610a4  cmp     eax, 5
0x1800610a7  jbe     short loc_1800610E1
0x1800610a9  lea     rax, [rbp+440h+var_250]
0x1800610b0  mov     [rsp+540h+var_508], rax
0x1800610b5  lea     rdx, byte_18010F423
0x1800610bc  lea     rax, aGotInitialprog; "Got InitialProgram from session"
0x1800610c3  mov     [rsp+540h+var_500], rax
0x1800610c8  lea     rax, [rsp+540h+var_508]
0x1800610cd  mov     [rsp+540h+TokenHandle], rax
0x1800610d2  lea     rax, [rsp+540h+var_500]
0x1800610d7  mov     [rsp+540h+var_520], rax
0x1800610dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800610e1  mov     eax, cs:dword_18012E170
0x1800610e7  xor     r14d, r14d
0x1800610ea  cmp     [rbp+440h+var_250], r14w
0x1800610f2  jnz     short loc_18006112A
0x1800610f4  cmp     eax, 5
0x1800610f7  jbe     short loc_18006111B
0x1800610f9  lea     rax, aGotEmptyInitia; "Got empty InitialProgram from session, "...
0x180061100  mov     [rsp+540h+var_508], rax
0x180061105  lea     rdx, byte_18010F3FF
0x18006110c  lea     rax, [rsp+540h+var_508]
0x180061111  mov     [rsp+540h+var_520], rax
0x180061116  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006111b  mov     byte ptr [r15], 1
0x18006111f  mov     ebx, r14d
0x180061122  mov     r14, rbx
0x180061125  jmp     loc_18006159D
0x18006112a  cmp     eax, 2
0x18006112d  jbe     short loc_180061151
0x18006112f  lea     rax, aBug23297910Thi; "BUG: 23297910 - This is not the right w"...
0x180061136  mov     [rsp+540h+var_508], rax
0x18006113b  lea     rdx, byte_18010F3DB
0x180061142  lea     rax, [rsp+540h+var_508]
0x180061147  mov     [rsp+540h+var_520], rax
0x18006114c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180061151  lea     r8, [rsp+540h+var_500]; unsigned __int64 *
0x180061156  mov     byte ptr [r15], 1
0x18006115a  mov     rdx, rbx; unsigned __int64
0x18006115d  mov     [rsp+540h+var_500], r14
0x180061162  lea     rcx, [rbp+440h+var_250]; unsigned __int16 *
0x180061169  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006116e  mov     ebx, eax
0x180061170  test    eax, eax
0x180061172  jns     short loc_180061191
0x180061174  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18006117b  mov     r8d, eax
0x18006117e  mov     ecx, edi; int
0x180061180  lea     r9, aRpcgetinitiala; "RpcGetInitialApplication"
0x180061187  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006118c  jmp     loc_180061038
0x180061191  mov     rbx, [rsp+540h+var_500]
0x180061196  mov     ecx, 40h ; '@'; uFlags
0x18006119b  lea     rdx, [rbx+2]; uBytes
0x18006119f  call    cs:__imp_LocalAlloc
0x1800611a6  nop     dword ptr [rax+rax+00h]
0x1800611ab  mov     rsi, rax
0x1800611ae  test    rax, rax
0x1800611b1  jnz     short loc_1800611C0
0x1800611b3  mov     ebx, 8007000Eh
0x1800611b8  mov     r14, r13
0x1800611bb  jmp     loc_18006159D
0x1800611c0  lea     r8, [rbp+440h+var_250]; unsigned __int16 *
0x1800611c7  mov     rcx, rsi; unsigned __int16 *
0x1800611ca  lea     rdx, [rbx+2]; unsigned __int64
0x1800611ce  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800611d3  mov     ebx, eax
0x1800611d5  test    eax, eax
0x1800611d7  jns     short loc_1800611F3
0x1800611d9  lea     r9, aRpcgetinitiala; "RpcGetInitialApplication"
0x1800611e0  mov     r8d, eax
0x1800611e3  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x1800611ea  mov     ecx, edi; int
0x1800611ec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800611f1  jmp     short loc_1800611B8
0x1800611f3  mov     rax, [rsp+540h+var_4F0]
0x1800611f8  mov     [rax], rsi
0x1800611fb  jmp     loc_18006111F
0x180061200  mov     rcx, [rsp+540h+var_4E8]
0x180061205  lea     rdx, [rbp+440h+Buf2]
0x180061209  mov     rax, [rcx]
0x18006120c  mov     rax, [rax+0A8h]
0x180061213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061218  xor     ebx, ebx
0x18006121a  test    eax, eax
0x18006121c  js      loc_1800612CF
0x180061222  lea     r8d, [rbx+10h]; Size
0x180061226  lea     rdx, [rbp+440h+Buf2]; Buf2
0x18006122a  lea     rcx, TERMINAL_TYPE_WORKER; Buf1
0x180061231  call    memcmp_0
0x180061236  test    eax, eax
0x180061238  jz      short loc_18006127A
0x18006123a  lea     r8d, [rbx+10h]; Size
0x18006123e  lea     rdx, [rbp+440h+Buf2]; Buf2
0x180061242  lea     rcx, TERMINAL_TYPE_DEBUG; Buf1
0x180061249  call    memcmp_0
0x18006124e  test    eax, eax
0x180061250  jz      short loc_18006127A
0x180061252  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement> `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl(void)'::`2'::impl
0x180061259  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(void)
0x18006125e  test    al, al
0x180061260  jz      short loc_1800612CF
0x180061262  lea     r8d, [rbx+10h]; Size
0x180061266  lea     rdx, [rbp+440h+Buf2]; Buf2
0x18006126a  lea     rcx, TERMINAL_TYPE_AGENT; Buf1
0x180061271  call    memcmp_0
0x180061276  test    eax, eax
0x180061278  jnz     short loc_1800612CF
0x18006127a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement> `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl(void)'::`2'::impl
0x180061281  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(void)
0x180061286  test    al, al
0x180061288  jz      short loc_18006129C
0x18006128a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180061291  jz      short loc_1800612B6
0x180061293  lea     rdx, aSessionIsWorke; "Session is worker, debug, or agent, ret"...
0x18006129a  jmp     short loc_1800612AC
0x18006129c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800612a3  jz      short loc_1800612B6
0x1800612a5  lea     rdx, aSessionIsWorke_0; "Session is worker or debug, return defa"...
0x1800612ac  mov     ecx, 2; int
0x1800612b1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800612b6  mov     rax, [rsp+540h+var_4F0]
0x1800612bb  mov     [rax], rbx
0x1800612be  mov     [r14], rbx
0x1800612c1  mov     byte ptr [r15], 1
0x1800612c5  mov     byte ptr [r12], 1
0x1800612ca  jmp     loc_180061122
0x1800612cf  cmp     [rsp+540h+var_4F8], ebx
0x1800612d3  jnz     short loc_1800612DA
0x1800612d5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800612da  mov     rcx, [rsp+540h+var_4D0]
0x1800612df  lea     r8, [rsp+540h+var_4E0]
0x1800612e4  lea     rdx, qword_1800DD390
0x1800612eb  mov     rax, [rcx]
0x1800612ee  mov     rax, [rax]
0x1800612f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800612f6  test    eax, eax
0x1800612f8  jns     short loc_180061314
0x1800612fa  mov     r8d, 800708CAh
0x180061300  lea     rdx, aQiOnIidIremote; "QI on IID_IRemoteTerminal failed: 0x%x "...
0x180061307  mov     ebx, r8d
0x18006130a  mov     ecx, 4
0x18006130f  jmp     loc_180061180
0x180061314  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006131b  mov     ecx, 0A68h; unsigned __int64
0x180061320  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180061325  mov     r13, rax
0x180061328  test    rax, rax
0x18006132b  jnz     short loc_180061337
0x18006132d  mov     ebx, 8007000Eh
0x180061332  jmp     loc_180061038
0x180061337  mov     rcx, [rsp+540h+var_4E0]
0x18006133c  mov     r8d, 0A68h
0x180061342  mov     rdx, r13
0x180061345  mov     rax, [rcx]
0x180061348  mov     rax, [rax+0F0h]
0x18006134f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061354  xor     r14d, r14d
0x180061357  mov     ebx, eax
0x180061359  test    eax, eax
0x18006135b  jns     short loc_180061369
0x18006135d  lea     rdx, aSessionGetconf; "Session->GetConfigData failed: 0x%x in "...
0x180061364  jmp     loc_18006117B
0x180061369  mov     rcx, [rsp+540h+var_4E0]
0x18006136e  lea     rdx, [rsp+540h+var_4D8]
0x180061373  mov     rax, [rcx]
0x180061376  mov     rax, [rax+170h]
0x18006137d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061382  mov     ebx, eax
0x180061384  test    eax, eax
0x180061386  jns     short loc_180061394
0x180061388  lea     rdx, aGetconnectionF; "GetConnection failed: 0x%x in %s"
0x18006138f  jmp     loc_18006117B
0x180061394  mov     rcx, [rsp+540h+var_4D8]; struct IConnection *
0x180061399  lea     r9, [rsp+540h+var_4F4]; int *
0x18006139e  lea     r8, [rsp+540h+var_500]; unsigned __int16 **
0x1800613a3  lea     rdx, [r13+7Ch]; struct _USERCONFIGW *
0x1800613a7  call    ?ApplyTSAllowPolicyToInitialProgram@@YAJPEAVIConnection@@PEAU_USERCONFIGW@@PEAPEAGPEAH@Z; ApplyTSAllowPolicyToInitialProgram(IConnection *,_USERCONFIGW *,ushort * *,int *)
0x1800613ac  mov     ebx, eax
0x1800613ae  cmp     eax, 0D0070002h
0x1800613b3  jz      loc_1800614CF
0x1800613b9  cmp     eax, 80070002h
0x1800613be  jz      loc_1800614CF
0x1800613c4  test    eax, eax
0x1800613c6  jns     short loc_1800613D2
0x1800613c8  mov     rsi, [rsp+540h+var_500]
0x1800613cd  jmp     loc_180061580
0x1800613d2  lea     rsi, [r13+0F0h]
0x1800613d9  cmp     [rsi], r14w
0x1800613dd  jz      loc_180061469
0x1800613e3  lea     r8, [rsp+540h+var_508]; unsigned __int64 *
0x1800613e8  mov     edx, 202h; unsigned __int64
0x1800613ed  mov     rcx, rsi; unsigned __int16 *
0x1800613f0  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800613f5  mov     ebx, eax
  ... truncated ...
```
