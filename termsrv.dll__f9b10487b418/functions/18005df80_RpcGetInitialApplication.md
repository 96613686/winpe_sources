# RpcGetInitialApplication

- ea: `0x18005df80`
- end: `0x18005e708`
- name: `RpcGetInitialApplication`
- size: `1928`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int16 **, unsigned __int16 **, _BYTE *, bool *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001a30`
- `0x1800092f0`
- `0x18000a210`
- `0x18000bad0`
- `0x18000f1a0`
- `0x180013150`
- `0x1800148f0`
- `0x180016234`
- `0x1800321f0`
- `0x18003269c`
- `0x1800326dc`
- `0x1800330c4`
- `0x18004d884`
- `0x18004f340`
- `0x18005c144`
- `0x18005df80`
- `0x1800c4290`
- `0x1800c4e00`
- `0x1800c8010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18005e62f`
- `RPCRT4!RpcRevertToSelf` at `0x18005e62f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e23f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e4c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e5b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e23f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e4c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e5b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e66d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e67b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e66d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e67b`

## string_xrefs

- `0x18005e27d`: `StringCchCopy failed: 0x%x in %s`
- `0x18005e4f4`: `StringCchCopy failed: 0x%x in %s`
- `0x18005e5eb`: `StringCchCopy failed: 0x%x in %s`
- `0x18005e04c`: `ppWorkDirectory`
- `0x18005e32d`: `Session is worker, debug, or agent, return default`
- `0x18005e3f7`: `Session->GetConfigData failed: 0x%x in %s`

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
    if ( (**(int (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v51)(v51, qword_1800D7370, &v49) < 0 )
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
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v43 = (unsigned __int64)"Got queried for initial program in disconnected state, returning what we know";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v14,
        (unsigned int)&dword_1801093D4,
        -2147022646,
        v15,
        (__int64)&v43);
    }
    memset_0(v55, 0, 0x202u);
    (*(void (__fastcall **)(struct ITSSession *, unsigned __int16 *))(*(_QWORD *)v48 + 192LL))(v48, v55);
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v43 = (unsigned __int64)v55;
      v44 = (unsigned __int16 *)"Got InitialProgram from session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)byte_1801093A3,
        v18,
        v19,
        (__int64)&v44,
        (__int64)&v43);
    }
    if ( !v55[0] )
    {
      if ( (unsigned int)dword_180128170 > 5 )
      {
        v43 = (unsigned __int64)"Got empty InitialProgram from session, returning.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v17,
          (unsigned int)&byte_18010937F,
          v18,
          v19,
          (__int64)&v43);
      }
      *a5 = 1;
      goto LABEL_22;
    }
    if ( (unsigned int)dword_180128170 > 2 )
    {
      v43 = (unsigned __int64)"BUG: 23297910 - This is not the right way to return the initial program it will probably not work.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v17,
        (unsigned int)byte_18010935B,
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
0x18005df80  mov     [rsp-8+arg_0], rbx
0x18005df85  push    rbp
0x18005df86  push    rsi
0x18005df87  push    rdi
0x18005df88  push    r12
0x18005df8a  push    r13
0x18005df8c  push    r14
0x18005df8e  push    r15
0x18005df90  lea     rbp, [rsp-410h]
0x18005df98  sub     rsp, 510h
0x18005df9f  mov     rax, cs:__security_cookie
0x18005dfa6  xor     rax, rsp
0x18005dfa9  mov     [rbp+440h+var_40], rax
0x18005dfb0  mov     r15, [rbp+440h+arg_20]
0x18005dfb7  lea     rcx, [rbp+440h+var_4A0]; this
0x18005dfbb  mov     r12, [rbp+440h+arg_28]
0x18005dfc2  xor     r13d, r13d
0x18005dfc5  mov     rdi, r8
0x18005dfc8  mov     [rsp+540h+var_4F0], r8
0x18005dfcd  mov     ebx, edx
0x18005dfcf  mov     [rsp+540h+var_4C8], r9
0x18005dfd4  xorps   xmm0, xmm0
0x18005dfd7  mov     [rsp+540h+var_4D0], r13
0x18005dfdc  lea     edx, [r13+1]; int
0x18005dfe0  mov     [rsp+540h+var_4E0], r13
0x18005dfe5  lea     r8, aRpcgetinitiala; "RpcGetInitialApplication"
0x18005dfec  mov     [rsp+540h+var_4F8], r13d
0x18005dff1  mov     r14, r9
0x18005dff4  mov     [rsp+540h+var_500], r13
0x18005dff9  mov     esi, r13d
0x18005dffc  mov     [rsp+540h+var_508], r13
0x18005e001  mov     [rsp+540h+var_4F4], r13d
0x18005e006  mov     [rsp+540h+var_4D8], r13
0x18005e00b  movups  [rbp+440h+Buf2], xmm0
0x18005e00f  mov     [rsp+540h+var_4E8], r13
0x18005e014  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005e019  test    rdi, rdi
0x18005e01c  jnz     short loc_18005E047
0x18005e01e  lea     r8, aPpcmdline; "ppCmdLine"
0x18005e025  lea     r9, aRpcgetinitiala; "RpcGetInitialApplication"
0x18005e02c  mov     ecx, 8; int
0x18005e031  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005e038  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e03d  mov     ebx, 80070057h
0x18005e042  jmp     loc_18005E6AB
0x18005e047  test    r14, r14
0x18005e04a  jnz     short loc_18005E055
0x18005e04c  lea     r8, aPpworkdirector; "ppWorkDirectory"
0x18005e053  jmp     short loc_18005E025
0x18005e055  test    r15, r15
0x18005e058  jnz     short loc_18005E063
0x18005e05a  lea     r8, aPbappallowed; "pbAppAllowed"
0x18005e061  jmp     short loc_18005E025
0x18005e063  test    r12, r12
0x18005e066  jnz     short loc_18005E071
0x18005e068  lea     r8, aPbmaximize; "pbMaximize"
0x18005e06f  jmp     short loc_18005E025
0x18005e071  xor     eax, eax
0x18005e073  lea     r9, [rsp+540h+var_4D0]; struct ITerminal **
0x18005e078  mov     [rdi], rax
0x18005e07b  xor     r8d, r8d; int
0x18005e07e  mov     [r14], rax
0x18005e081  mov     ecx, ebx; unsigned int
0x18005e083  mov     [r15], al
0x18005e086  mov     [r12], al
0x18005e08a  mov     [rsp+540h+var_510], rax
0x18005e08f  lea     edx, [r8+1]; unsigned int
0x18005e093  lea     rax, [rsp+540h+var_4F8]
0x18005e098  mov     [rsp+540h+TokenHandle], rax; TokenHandle
0x18005e09d  lea     rax, [rsp+540h+var_4E8]
0x18005e0a2  mov     [rsp+540h+var_520], rax; struct ITSSession **
0x18005e0a7  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18005e0ac  mov     ebx, eax
0x18005e0ae  mov     edi, 8
0x18005e0b3  test    eax, eax
0x18005e0b5  jns     loc_18005E29A
0x18005e0bb  mov     r8d, 800708CAh
0x18005e0c1  cmp     eax, r8d
0x18005e0c4  jz      short loc_18005E0E0
0x18005e0c6  mov     r8d, eax
0x18005e0c9  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x18005e0d0  lea     ecx, [rdi-7]; int
0x18005e0d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e0d8  mov     r14, rsi
0x18005e0db  jmp     loc_18005E628
0x18005e0e0  mov     eax, cs:dword_180128170
0x18005e0e6  cmp     eax, 5
0x18005e0e9  jbe     short loc_18005E10D
0x18005e0eb  lea     rax, aGotQueriedForI; "Got queried for initial program in disc"...
0x18005e0f2  mov     [rsp+540h+var_508], rax
0x18005e0f7  lea     rdx, dword_1801093D4
0x18005e0fe  lea     rax, [rsp+540h+var_508]
0x18005e103  mov     [rsp+540h+var_520], rax
0x18005e108  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005e10d  mov     ebx, 202h
0x18005e112  lea     rcx, [rbp+440h+var_250]; void *
0x18005e119  mov     r8d, ebx; Size
0x18005e11c  xor     edx, edx; Val
0x18005e11e  call    memset_0
0x18005e123  mov     rcx, [rsp+540h+var_4E8]
0x18005e128  lea     rdx, [rbp+440h+var_250]
0x18005e12f  mov     rax, [rcx]
0x18005e132  mov     rax, [rax+0C0h]
0x18005e139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e13e  mov     eax, cs:dword_180128170
0x18005e144  cmp     eax, 5
0x18005e147  jbe     short loc_18005E181
0x18005e149  lea     rax, [rbp+440h+var_250]
0x18005e150  mov     [rsp+540h+var_508], rax
0x18005e155  lea     rdx, byte_1801093A3
0x18005e15c  lea     rax, aGotInitialprog; "Got InitialProgram from session"
0x18005e163  mov     [rsp+540h+var_500], rax
0x18005e168  lea     rax, [rsp+540h+var_508]
0x18005e16d  mov     [rsp+540h+TokenHandle], rax
0x18005e172  lea     rax, [rsp+540h+var_500]
0x18005e177  mov     [rsp+540h+var_520], rax
0x18005e17c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18005e181  mov     eax, cs:dword_180128170
0x18005e187  xor     r14d, r14d
0x18005e18a  cmp     [rbp+440h+var_250], r14w
0x18005e192  jnz     short loc_18005E1CA
0x18005e194  cmp     eax, 5
0x18005e197  jbe     short loc_18005E1BB
0x18005e199  lea     rax, aGotEmptyInitia; "Got empty InitialProgram from session, "...
0x18005e1a0  mov     [rsp+540h+var_508], rax
0x18005e1a5  lea     rdx, byte_18010937F
0x18005e1ac  lea     rax, [rsp+540h+var_508]
0x18005e1b1  mov     [rsp+540h+var_520], rax
0x18005e1b6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005e1bb  mov     byte ptr [r15], 1
0x18005e1bf  mov     ebx, r14d
0x18005e1c2  mov     r14, rbx
0x18005e1c5  jmp     loc_18005E628
0x18005e1ca  cmp     eax, 2
0x18005e1cd  jbe     short loc_18005E1F1
0x18005e1cf  lea     rax, aBug23297910Thi; "BUG: 23297910 - This is not the right w"...
0x18005e1d6  mov     [rsp+540h+var_508], rax
0x18005e1db  lea     rdx, byte_18010935B
0x18005e1e2  lea     rax, [rsp+540h+var_508]
0x18005e1e7  mov     [rsp+540h+var_520], rax
0x18005e1ec  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005e1f1  lea     r8, [rsp+540h+var_500]; unsigned __int64 *
0x18005e1f6  mov     byte ptr [r15], 1
0x18005e1fa  mov     rdx, rbx; unsigned __int64
0x18005e1fd  mov     [rsp+540h+var_500], r14
0x18005e202  lea     rcx, [rbp+440h+var_250]; unsigned __int16 *
0x18005e209  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005e20e  mov     ebx, eax
0x18005e210  test    eax, eax
0x18005e212  jns     short loc_18005E231
0x18005e214  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18005e21b  mov     r8d, eax
0x18005e21e  mov     ecx, edi; int
0x18005e220  lea     r9, aRpcgetinitiala; "RpcGetInitialApplication"
0x18005e227  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e22c  jmp     loc_18005E0D8
0x18005e231  mov     rbx, [rsp+540h+var_500]
0x18005e236  mov     ecx, 40h ; '@'; uFlags
0x18005e23b  lea     rdx, [rbx+2]; uBytes
0x18005e23f  call    cs:__imp_LocalAlloc
0x18005e245  mov     rsi, rax
0x18005e248  test    rax, rax
0x18005e24b  jnz     short loc_18005E25A
0x18005e24d  mov     ebx, 8007000Eh
0x18005e252  mov     r14, r13
0x18005e255  jmp     loc_18005E628
0x18005e25a  lea     r8, [rbp+440h+var_250]; unsigned __int16 *
0x18005e261  mov     rcx, rsi; unsigned __int16 *
0x18005e264  lea     rdx, [rbx+2]; unsigned __int64
0x18005e268  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18005e26d  mov     ebx, eax
0x18005e26f  test    eax, eax
0x18005e271  jns     short loc_18005E28D
0x18005e273  lea     r9, aRpcgetinitiala; "RpcGetInitialApplication"
0x18005e27a  mov     r8d, eax
0x18005e27d  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x18005e284  mov     ecx, edi; int
0x18005e286  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e28b  jmp     short loc_18005E252
0x18005e28d  mov     rax, [rsp+540h+var_4F0]
0x18005e292  mov     [rax], rsi
0x18005e295  jmp     loc_18005E1BF
0x18005e29a  mov     rcx, [rsp+540h+var_4E8]
0x18005e29f  lea     rdx, [rbp+440h+Buf2]
0x18005e2a3  mov     rax, [rcx]
0x18005e2a6  mov     rax, [rax+0A8h]
0x18005e2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2b2  xor     ebx, ebx
0x18005e2b4  test    eax, eax
0x18005e2b6  js      loc_18005E369
0x18005e2bc  lea     r8d, [rbx+10h]; Size
0x18005e2c0  lea     rdx, [rbp+440h+Buf2]; Buf2
0x18005e2c4  lea     rcx, TERMINAL_TYPE_WORKER; Buf1
0x18005e2cb  call    memcmp_0
0x18005e2d0  test    eax, eax
0x18005e2d2  jz      short loc_18005E314
0x18005e2d4  lea     r8d, [rbx+10h]; Size
0x18005e2d8  lea     rdx, [rbp+440h+Buf2]; Buf2
0x18005e2dc  lea     rcx, TERMINAL_TYPE_DEBUG; Buf1
0x18005e2e3  call    memcmp_0
0x18005e2e8  test    eax, eax
0x18005e2ea  jz      short loc_18005E314
0x18005e2ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement> `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl(void)'::`2'::impl
0x18005e2f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(void)
0x18005e2f8  test    al, al
0x18005e2fa  jz      short loc_18005E369
0x18005e2fc  lea     r8d, [rbx+10h]; Size
0x18005e300  lea     rdx, [rbp+440h+Buf2]; Buf2
0x18005e304  lea     rcx, TERMINAL_TYPE_AGENT; Buf1
0x18005e30b  call    memcmp_0
0x18005e310  test    eax, eax
0x18005e312  jnz     short loc_18005E369
0x18005e314  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement> `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl(void)'::`2'::impl
0x18005e31b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(void)
0x18005e320  test    al, al
0x18005e322  jz      short loc_18005E336
0x18005e324  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18005e32b  jz      short loc_18005E350
0x18005e32d  lea     rdx, aSessionIsWorke; "Session is worker, debug, or agent, ret"...
0x18005e334  jmp     short loc_18005E346
0x18005e336  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18005e33d  jz      short loc_18005E350
0x18005e33f  lea     rdx, aSessionIsWorke_0; "Session is worker or debug, return defa"...
0x18005e346  mov     ecx, 2; int
0x18005e34b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e350  mov     rax, [rsp+540h+var_4F0]
0x18005e355  mov     [rax], rbx
0x18005e358  mov     [r14], rbx
0x18005e35b  mov     byte ptr [r15], 1
0x18005e35f  mov     byte ptr [r12], 1
0x18005e364  jmp     loc_18005E1C2
0x18005e369  cmp     [rsp+540h+var_4F8], ebx
0x18005e36d  jnz     short loc_18005E374
0x18005e36f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "bImpersonating")
0x18005e374  mov     rcx, [rsp+540h+var_4D0]
0x18005e379  lea     r8, [rsp+540h+var_4E0]
0x18005e37e  lea     rdx, qword_1800D7370
0x18005e385  mov     rax, [rcx]
0x18005e388  mov     rax, [rax]
0x18005e38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e390  test    eax, eax
0x18005e392  jns     short loc_18005E3AE
0x18005e394  mov     r8d, 800708CAh
0x18005e39a  lea     rdx, aQiOnIidIremote; "QI on IID_IRemoteTerminal failed: 0x%x "...
0x18005e3a1  mov     ebx, r8d
0x18005e3a4  mov     ecx, 4
0x18005e3a9  jmp     loc_18005E220
0x18005e3ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005e3b5  mov     ecx, 0A68h; unsigned __int64
0x18005e3ba  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005e3bf  mov     r13, rax
0x18005e3c2  test    rax, rax
0x18005e3c5  jnz     short loc_18005E3D1
0x18005e3c7  mov     ebx, 8007000Eh
0x18005e3cc  jmp     loc_18005E0D8
0x18005e3d1  mov     rcx, [rsp+540h+var_4E0]
0x18005e3d6  mov     r8d, 0A68h
0x18005e3dc  mov     rdx, r13
0x18005e3df  mov     rax, [rcx]
0x18005e3e2  mov     rax, [rax+0F0h]
0x18005e3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3ee  xor     r14d, r14d
0x18005e3f1  mov     ebx, eax
0x18005e3f3  test    eax, eax
0x18005e3f5  jns     short loc_18005E403
0x18005e3f7  lea     rdx, aSessionGetconf; "Session->GetConfigData failed: 0x%x in "...
0x18005e3fe  jmp     loc_18005E21B
0x18005e403  mov     rcx, [rsp+540h+var_4E0]
0x18005e408  lea     rdx, [rsp+540h+var_4D8]
0x18005e40d  mov     rax, [rcx]
0x18005e410  mov     rax, [rax+170h]
0x18005e417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e41c  mov     ebx, eax
0x18005e41e  test    eax, eax
0x18005e420  jns     short loc_18005E42E
0x18005e422  lea     rdx, aGetconnectionF; "GetConnection failed: 0x%x in %s"
0x18005e429  jmp     loc_18005E21B
0x18005e42e  mov     rcx, [rsp+540h+var_4D8]; struct IConnection *
0x18005e433  lea     r9, [rsp+540h+var_4F4]; int *
0x18005e438  lea     r8, [rsp+540h+var_500]; unsigned __int16 **
0x18005e43d  lea     rdx, [r13+7Ch]; struct _USERCONFIGW *
0x18005e441  call    ?ApplyTSAllowPolicyToInitialProgram@@YAJPEAVIConnection@@PEAU_USERCONFIGW@@PEAPEAGPEAH@Z; ApplyTSAllowPolicyToInitialProgram(IConnection *,_USERCONFIGW *,ushort * *,int *)
0x18005e446  mov     ebx, eax
0x18005e448  cmp     eax, 0D0070002h
0x18005e44d  jz      loc_18005E563
0x18005e453  cmp     eax, 80070002h
0x18005e458  jz      loc_18005E563
0x18005e45e  test    eax, eax
0x18005e460  jns     short loc_18005E46C
0x18005e462  mov     rsi, [rsp+540h+var_500]
0x18005e467  jmp     loc_18005E60B
0x18005e46c  lea     rsi, [r13+0F0h]
0x18005e473  cmp     [rsi], r14w
0x18005e477  jz      loc_18005E4FD
0x18005e47d  lea     r8, [rsp+540h+var_508]; unsigned __int64 *
0x18005e482  mov     edx, 202h; unsigned __int64
0x18005e487  mov     rcx, rsi; unsigned __int16 *
0x18005e48a  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005e48f  mov     ebx, eax
0x18005e491  test    eax, eax
  ... truncated ...
```
