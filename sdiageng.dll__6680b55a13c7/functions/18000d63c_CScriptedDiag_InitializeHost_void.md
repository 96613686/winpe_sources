# CScriptedDiag::InitializeHost(void)

- ea: `0x18000d63c`
- end: `0x18000dacb`
- name: `?InitializeHost@CScriptedDiag@@AEAAJXZ`
- size: `1167`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ad80`

## callees

- `0x1800012a4`
- `0x18000b674`
- `0x18000cd40`
- `0x18000d63c`
- `0x1800130d0`
- `0x18001e6c0`
- `0x18001e95c`
- `0x180026fa0`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d7d5`
- `KERNEL32!GetLastError` at `0x18000da1d`
- `KERNEL32!GetLastError` at `0x18000d7d5`
- `KERNEL32!GetLastError` at `0x18000da1d`
- `ADVAPI32!RevertToSelf` at `0x18000d7cb`
- `ADVAPI32!RevertToSelf` at `0x18000da13`
- `ADVAPI32!RevertToSelf` at `0x18000d7cb`
- `ADVAPI32!RevertToSelf` at `0x18000da13`
- `ole32!CoSetProxyBlanket` at `0x18000d7ac`
- `ole32!CoSetProxyBlanket` at `0x18000d847`
- `ole32!CoSetProxyBlanket` at `0x18000d7ac`
- `ole32!CoSetProxyBlanket` at `0x18000d847`
- `ole32!CoCreateInstance` at `0x18000d766`
- `ole32!CoCreateInstance` at `0x18000d766`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d868`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d8c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d921`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d868`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d8c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d921`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da76`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da88`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da96`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da76`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da88`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da96`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::InitializeHost(CScriptedDiag *this)
{
  __int64 v2; // rcx
  OLECHAR *v3; // r15
  OLECHAR *v4; // r13
  OLECHAR *v5; // r14
  int v6; // r12d
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r8
  int ActivationContext; // eax
  CScriptedDiag *v13; // rcx
  int active; // eax
  HRESULT Instance; // eax
  HRESULT v16; // eax
  signed int LastError; // eax
  int v18; // eax
  HRESULT v19; // eax
  int ResultPath; // eax
  int Locale; // eax
  __int64 v22; // r8
  int v23; // eax
  IUnknown *v24; // rbx
  __int64 v25; // rsi
  __int64 v26; // rcx
  IUnknown *pProxy; // [rsp+40h] [rbp-39h] BYREF
  tagCLSCTX v29; // [rsp+48h] [rbp-31h] BYREF
  IUnknown *v30; // [rsp+50h] [rbp-29h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-21h] BYREF
  OLECHAR *v32; // [rsp+60h] [rbp-19h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-11h]
  BSTR v34; // [rsp+70h] [rbp-9h]
  _BYTE v35[16]; // [rsp+78h] [rbp-1h] BYREF

  v2 = *((_QWORD *)this + 3);
  v3 = 0;
  pProxy = 0;
  v4 = 0;
  v30 = 0;
  v5 = 0;
  psz = 0;
  bstrString = 0;
  v6 = 0;
  v34 = 0;
  v32 = 0;
  v29 = 0;
  if ( !v2 )
  {
    v7 = 1105;
LABEL_3:
    v8 = -2147467261;
LABEL_4:
    v9 = v8;
LABEL_5:
    SdpDebugTrace(1u, L"CScriptedDiag::InitializeHost", v7, v8);
    goto LABEL_47;
  }
  if ( _InterlockedExchange((volatile __int32 *)(v2 + 60), *(_DWORD *)(v2 + 60)) )
  {
    v9 = -2143551232;
    v7 = 1116;
    v8 = -2143551232;
    goto LABEL_5;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, SCRIPTED_DIAGNOSTICS_EVENT_PERF_HOST_START, 0, 1, v35);
  ActivationContext = CScriptedDiag::GetActivationContext(this, &v29);
  v9 = ActivationContext;
  if ( ActivationContext < 0 )
  {
    v8 = ActivationContext;
    v7 = 1122;
    goto LABEL_5;
  }
  v6 = *(_DWORD *)(*((_QWORD *)this + 3) + 56LL) & 0x20000;
  if ( v6 )
  {
    active = CScriptedDiag::ImpersonateActiveUser(v13);
    v9 = active;
    if ( active < 0 )
    {
      v8 = active;
      v7 = 1129;
      goto LABEL_5;
    }
  }
  Instance = CoCreateInstance(
               &CLSID_CScriptedDiagNativeHost,
               0,
               v29 | 0x110004,
               &IID_IScriptedDiagnosticHost,
               (LPVOID *)&pProxy);
  v9 = Instance;
  if ( Instance < 0 )
  {
    v8 = Instance;
    v7 = 1139;
    goto LABEL_5;
  }
  v16 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 6u, 2u, 0, 0x40u);
  v9 = v16;
  if ( v16 < 0 )
  {
    v8 = v16;
    v7 = 1149;
    goto LABEL_5;
  }
  if ( v6 )
  {
    if ( !RevertToSelf() )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError < 0 )
      {
        v8 = LastError;
        v7 = 1153;
        goto LABEL_5;
      }
    }
  }
  v18 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
          pProxy,
          &IID_IUnknown,
          &v30);
  v9 = v18;
  if ( v18 < 0 )
  {
    v8 = v18;
    v7 = 1162;
    goto LABEL_5;
  }
  v19 = CoSetProxyBlanket(v30, 0xFFFFFFFF, 0xFFFFFFFF, 0, 6u, 2u, 0, 0x40u);
  v9 = v19;
  if ( v19 < 0 )
  {
    v8 = v19;
    v7 = 1172;
    goto LABEL_5;
  }
  bstrString = SysAllocString(L"1.0");
  if ( !bstrString )
  {
    v8 = -2147024882;
    v7 = 1175;
    goto LABEL_4;
  }
  ResultPath = Settings::get_ResultPath(*((Settings **)this + 3), &psz);
  v9 = ResultPath;
  if ( ResultPath >= 0 )
  {
    v3 = psz;
    v34 = SysAllocString(psz);
    if ( !v34 )
    {
      v8 = -2147024882;
      v7 = 1181;
      goto LABEL_4;
    }
    Locale = Settings::get_Locale(*((Settings **)this + 3), &v32);
    v9 = Locale;
    if ( Locale >= 0 )
    {
      v5 = v32;
      if ( v32 )
      {
        v4 = SysAllocString(v32);
        if ( !v4 )
        {
          v8 = -2147024882;
          v7 = 1188;
          goto LABEL_4;
        }
      }
      v22 = *((_QWORD *)this + 5);
      if ( !v22 )
      {
        v7 = 1191;
        goto LABEL_3;
      }
      v23 = ((__int64 (__fastcall *)(IUnknown *, BSTR, __int64, OLECHAR *, BSTR))pProxy->lpVtbl[1].QueryInterface)(
              pProxy,
              bstrString,
              v22,
              v4,
              v34);
      v9 = v23;
      if ( v23 < 0 )
      {
        v8 = v23;
        v7 = 1197;
        goto LABEL_5;
      }
      v24 = pProxy;
      if ( !pProxy )
      {
        v9 = -2147024809;
        SdpDebugTrace(1u, L"Settings::set_Host", 407, -2147024809);
        v8 = -2147024809;
        v7 = 1200;
        goto LABEL_5;
      }
      v25 = *((_QWORD *)this + 3);
      v26 = *(_QWORD *)(v25 + 48);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      *(_QWORD *)(v25 + 48) = v24;
      ((void (__fastcall *)(IUnknown *))v24->lpVtbl->AddRef)(v24);
      v9 = 0;
    }
    else
    {
      SdpDebugTrace(1u, L"CScriptedDiag::InitializeHost", 1184, Locale);
      v5 = v32;
    }
  }
  else
  {
    SdpDebugTrace(1u, L"CScriptedDiag::InitializeHost", 1178, ResultPath);
    v3 = psz;
  }
LABEL_47:
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v10, SCRIPTED_DIAGNOSTICS_EVENT_PERF_HOST_STOP, v11, 1, v35);
  if ( v6 && v9 < 0 && !RevertToSelf() )
    GetLastError();
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  if ( v30 )
  {
    ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
    v30 = 0;
  }
  if ( v3 )
    operator delete(v3);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v34 )
    SysFreeString(v34);
  if ( v4 )
    SysFreeString(v4);
  if ( v5 )
    operator delete(v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000d63c  push    rbp
0x18000d63e  push    rbx
0x18000d63f  push    rsi
0x18000d640  push    rdi
0x18000d641  push    r12
0x18000d643  push    r13
0x18000d645  push    r14
0x18000d647  push    r15
0x18000d649  lea     rbp, [rsp-1Fh]
0x18000d64e  sub     rsp, 98h
0x18000d655  mov     rax, cs:__security_cookie
0x18000d65c  xor     rax, rsp
0x18000d65f  mov     [rbp+57h+var_48], rax
0x18000d663  xor     r8d, r8d
0x18000d666  mov     rsi, rcx
0x18000d669  mov     rcx, [rcx+18h]
0x18000d66d  mov     r15d, r8d
0x18000d670  mov     [rbp+57h+pProxy], r8
0x18000d674  mov     r13d, r8d
0x18000d677  mov     [rbp+57h+var_80], r8
0x18000d67b  mov     r14d, r8d
0x18000d67e  mov     [rbp+57h+psz], r8
0x18000d682  lea     edi, [r8+1]
0x18000d686  mov     [rbp+57h+bstrString], r8
0x18000d68a  mov     r12d, r8d
0x18000d68d  mov     [rbp+57h+var_60], r8
0x18000d691  mov     [rbp+57h+var_70], r8
0x18000d695  mov     [rbp+57h+var_88], r8d
0x18000d699  test    rcx, rcx
0x18000d69c  jnz     short loc_18000D6C0
0x18000d69e  mov     r8d, 451h; int
0x18000d6a4  mov     r9d, 80004003h; int
0x18000d6aa  mov     ebx, r9d
0x18000d6ad  lea     rdx, aCscripteddiagI_4; "CScriptedDiag::InitializeHost"
0x18000d6b4  mov     ecx, edi; Level
0x18000d6b6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000d6bb  jmp     loc_18000D9E9
0x18000d6c0  mov     eax, [rcx+3Ch]
0x18000d6c3  xchg    eax, [rcx+3Ch]
0x18000d6c6  test    eax, eax
0x18000d6c8  jz      short loc_18000D6DA
0x18000d6ca  mov     ebx, 803C0100h
0x18000d6cf  mov     r8d, 45Ch
0x18000d6d5  mov     r9d, ebx
0x18000d6d8  jmp     short loc_18000D6AD
0x18000d6da  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 10h
0x18000d6e1  jz      short loc_18000D6FB
0x18000d6e3  lea     rax, [rbp+57h+var_58]
0x18000d6e7  mov     r9d, edi
0x18000d6ea  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_HOST_START
0x18000d6f1  mov     [rsp+0D0h+ppv], rax
0x18000d6f6  call    McGenEventWrite_EventWriteTransfer
0x18000d6fb  lea     rdx, [rbp+57h+var_88]; enum tagCLSCTX *
0x18000d6ff  mov     rcx, rsi; this
0x18000d702  call    ?GetActivationContext@CScriptedDiag@@AEAAJPEAW4tagCLSCTX@@@Z; CScriptedDiag::GetActivationContext(tagCLSCTX *)
0x18000d707  mov     ebx, eax
0x18000d709  test    eax, eax
0x18000d70b  jns     short loc_18000D718
0x18000d70d  mov     r9d, eax
0x18000d710  mov     r8d, 462h
0x18000d716  jmp     short loc_18000D6AD
0x18000d718  mov     rax, [rsi+18h]
0x18000d71c  mov     r12d, [rax+38h]
0x18000d720  and     r12d, 20000h
0x18000d727  jz      short loc_18000D742
0x18000d729  call    ?ImpersonateActiveUser@CScriptedDiag@@AEAAJXZ; CScriptedDiag::ImpersonateActiveUser(void)
0x18000d72e  mov     ebx, eax
0x18000d730  test    eax, eax
0x18000d732  jns     short loc_18000D742
0x18000d734  mov     r9d, eax
0x18000d737  mov     r8d, 469h
0x18000d73d  jmp     loc_18000D6AD
0x18000d742  mov     r8d, [rbp+57h+var_88]
0x18000d746  lea     rax, [rbp+57h+pProxy]
0x18000d74a  or      r8d, 110004h; dwClsContext
0x18000d751  mov     [rsp+0D0h+ppv], rax; ppv
0x18000d756  lea     r9, IID_IScriptedDiagnosticHost; riid
0x18000d75d  xor     edx, edx; pUnkOuter
0x18000d75f  lea     rcx, CLSID_CScriptedDiagNativeHost; rclsid
0x18000d766  call    cs:__imp_CoCreateInstance
0x18000d76c  mov     ebx, eax
0x18000d76e  test    eax, eax
0x18000d770  jns     short loc_18000D780
0x18000d772  mov     r9d, eax
0x18000d775  mov     r8d, 473h
0x18000d77b  jmp     loc_18000D6AD
0x18000d780  mov     rcx, [rbp+57h+pProxy]; pProxy
0x18000d784  or      eax, 0FFFFFFFFh
0x18000d787  mov     [rsp+0D0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18000d78f  mov     r8d, eax; dwAuthzSvc
0x18000d792  mov     [rsp+0D0h+pAuthInfo], r13; pAuthInfo
0x18000d797  mov     edx, eax; dwAuthnSvc
0x18000d799  mov     [rsp+0D0h+dwImpLevel], 2; dwImpLevel
0x18000d7a1  xor     r9d, r9d; pServerPrincName
0x18000d7a4  mov     dword ptr [rsp+0D0h+ppv], 6; dwAuthnLevel
0x18000d7ac  call    cs:__imp_CoSetProxyBlanket
0x18000d7b2  mov     ebx, eax
0x18000d7b4  test    eax, eax
0x18000d7b6  jns     short loc_18000D7C6
0x18000d7b8  mov     r9d, eax
0x18000d7bb  mov     r8d, 47Dh
0x18000d7c1  jmp     loc_18000D6AD
0x18000d7c6  test    r12d, r12d
0x18000d7c9  jz      short loc_18000D7EF
0x18000d7cb  call    cs:__imp_RevertToSelf
0x18000d7d1  test    eax, eax
0x18000d7d3  jnz     short loc_18000D7EF
0x18000d7d5  call    cs:__imp_GetLastError
0x18000d7db  mov     ebx, eax
0x18000d7dd  test    eax, eax
0x18000d7df  jns     short loc_18000D7EF
0x18000d7e1  mov     r9d, eax
0x18000d7e4  mov     r8d, 481h
0x18000d7ea  jmp     loc_18000D6AD
0x18000d7ef  mov     rcx, [rbp+57h+pProxy]
0x18000d7f3  lea     r8, [rbp+57h+var_80]
0x18000d7f7  lea     rdx, IID_IUnknown
0x18000d7fe  mov     rax, [rcx]
0x18000d801  mov     rax, [rax]
0x18000d804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d809  mov     ebx, eax
0x18000d80b  test    eax, eax
0x18000d80d  jns     short loc_18000D81D
0x18000d80f  mov     r9d, eax
0x18000d812  mov     r8d, 48Ah
0x18000d818  jmp     loc_18000D6AD
0x18000d81d  mov     rcx, [rbp+57h+var_80]; pProxy
0x18000d821  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000d824  mov     [rsp+0D0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18000d82c  mov     r8d, edx; dwAuthzSvc
0x18000d82f  mov     [rsp+0D0h+pAuthInfo], r13; pAuthInfo
0x18000d834  xor     r9d, r9d; pServerPrincName
0x18000d837  mov     [rsp+0D0h+dwImpLevel], 2; dwImpLevel
0x18000d83f  mov     dword ptr [rsp+0D0h+ppv], 6; dwAuthnLevel
0x18000d847  call    cs:__imp_CoSetProxyBlanket
0x18000d84d  mov     ebx, eax
0x18000d84f  test    eax, eax
0x18000d851  jns     short loc_18000D861
0x18000d853  mov     r9d, eax
0x18000d856  mov     r8d, 494h
0x18000d85c  jmp     loc_18000D6AD
0x18000d861  lea     rcx, a10; "1.0"
0x18000d868  call    cs:__imp_SysAllocString
0x18000d86e  mov     [rbp+57h+bstrString], rax
0x18000d872  test    rax, rax
0x18000d875  jnz     short loc_18000D888
0x18000d877  mov     r9d, 8007000Eh
0x18000d87d  mov     r8d, 497h
0x18000d883  jmp     loc_18000D6AA
0x18000d888  mov     rcx, [rsi+18h]; this
0x18000d88c  lea     rdx, [rbp+57h+psz]; unsigned __int16 **
0x18000d890  call    ?get_ResultPath@Settings@@QEAAJPEAPEAG@Z; Settings::get_ResultPath(ushort * *)
0x18000d895  mov     ebx, eax
0x18000d897  test    eax, eax
0x18000d899  jns     short loc_18000D8BB
0x18000d89b  mov     r9d, eax; int
0x18000d89e  lea     rdx, aCscripteddiagI_4; "CScriptedDiag::InitializeHost"
0x18000d8a5  mov     r8d, 49Ah; int
0x18000d8ab  mov     ecx, edi; Level
0x18000d8ad  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000d8b2  mov     r15, [rbp+57h+psz]
0x18000d8b6  jmp     loc_18000D9E9
0x18000d8bb  mov     r15, [rbp+57h+psz]
0x18000d8bf  mov     rcx, r15; psz
0x18000d8c2  call    cs:__imp_SysAllocString
0x18000d8c8  mov     [rbp+57h+var_60], rax
0x18000d8cc  test    rax, rax
0x18000d8cf  jnz     short loc_18000D8E2
0x18000d8d1  mov     r9d, 8007000Eh
0x18000d8d7  mov     r8d, 49Dh
0x18000d8dd  jmp     loc_18000D6AA
0x18000d8e2  mov     rcx, [rsi+18h]; this
0x18000d8e6  lea     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x18000d8ea  call    ?get_Locale@Settings@@QEAAJPEAPEAG@Z; Settings::get_Locale(ushort * *)
0x18000d8ef  mov     ebx, eax
0x18000d8f1  test    eax, eax
0x18000d8f3  jns     short loc_18000D915
0x18000d8f5  mov     r9d, eax; int
0x18000d8f8  lea     rdx, aCscripteddiagI_4; "CScriptedDiag::InitializeHost"
0x18000d8ff  mov     r8d, 4A0h; int
0x18000d905  mov     ecx, edi; Level
0x18000d907  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000d90c  mov     r14, [rbp+57h+var_70]
0x18000d910  jmp     loc_18000D9E9
0x18000d915  mov     r14, [rbp+57h+var_70]
0x18000d919  test    r14, r14
0x18000d91c  jz      short loc_18000D940
0x18000d91e  mov     rcx, r14; psz
0x18000d921  call    cs:__imp_SysAllocString
0x18000d927  mov     r13, rax
0x18000d92a  test    rax, rax
0x18000d92d  jnz     short loc_18000D940
0x18000d92f  mov     r9d, 8007000Eh
0x18000d935  mov     r8d, 4A4h
0x18000d93b  jmp     loc_18000D6AA
0x18000d940  mov     r8, [rsi+28h]
0x18000d944  test    r8, r8
0x18000d947  jnz     short loc_18000D954
0x18000d949  mov     r8d, 4A7h
0x18000d94f  jmp     loc_18000D6A4
0x18000d954  mov     rcx, [rbp+57h+pProxy]
0x18000d958  mov     r9, r13
0x18000d95b  mov     rdx, [rbp+57h+var_60]
0x18000d95f  mov     [rsp+0D0h+ppv], rdx
0x18000d964  mov     rdx, [rbp+57h+bstrString]
0x18000d968  mov     rax, [rcx]
0x18000d96b  mov     rax, [rax+18h]
0x18000d96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d974  mov     ebx, eax
0x18000d976  test    eax, eax
0x18000d978  jns     short loc_18000D988
0x18000d97a  mov     r9d, eax
0x18000d97d  mov     r8d, 4ADh
0x18000d983  jmp     loc_18000D6AD
0x18000d988  mov     rbx, [rbp+57h+pProxy]
0x18000d98c  test    rbx, rbx
0x18000d98f  jnz     short loc_18000D9BB
0x18000d991  mov     ebx, 80070057h
0x18000d996  lea     rdx, aSettingsSetHos; "Settings::set_Host"
0x18000d99d  mov     r9d, ebx; int
0x18000d9a0  mov     r8d, 197h; int
0x18000d9a6  mov     ecx, edi; Level
0x18000d9a8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000d9ad  mov     r9d, ebx
0x18000d9b0  mov     r8d, 4B0h
0x18000d9b6  jmp     loc_18000D6AD
0x18000d9bb  mov     rsi, [rsi+18h]
0x18000d9bf  mov     rcx, [rsi+30h]
0x18000d9c3  test    rcx, rcx
0x18000d9c6  jz      short loc_18000D9D4
0x18000d9c8  mov     rax, [rcx]
0x18000d9cb  mov     rax, [rax+10h]
0x18000d9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d4  mov     [rsi+30h], rbx
0x18000d9d8  mov     rcx, rbx
0x18000d9db  mov     rax, [rbx]
0x18000d9de  mov     rax, [rax+8]
0x18000d9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9e7  xor     ebx, ebx
0x18000d9e9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 10h
0x18000d9f0  jz      short loc_18000DA0A
0x18000d9f2  lea     rax, [rbp+57h+var_58]
0x18000d9f6  mov     r9d, edi
0x18000d9f9  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_HOST_STOP
0x18000da00  mov     [rsp+0D0h+ppv], rax
0x18000da05  call    McGenEventWrite_EventWriteTransfer
0x18000da0a  test    r12d, r12d
0x18000da0d  jz      short loc_18000DA23
0x18000da0f  test    ebx, ebx
0x18000da11  jns     short loc_18000DA23
0x18000da13  call    cs:__imp_RevertToSelf
0x18000da19  test    eax, eax
0x18000da1b  jnz     short loc_18000DA23
0x18000da1d  call    cs:__imp_GetLastError
0x18000da23  mov     rcx, [rbp+57h+pProxy]
0x18000da27  test    rcx, rcx
0x18000da2a  jz      short loc_18000DA40
0x18000da2c  mov     rax, [rcx]
0x18000da2f  mov     rax, [rax+10h]
0x18000da33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da38  mov     [rbp+57h+pProxy], 0
0x18000da40  mov     rcx, [rbp+57h+var_80]
0x18000da44  test    rcx, rcx
0x18000da47  jz      short loc_18000DA5D
0x18000da49  mov     rax, [rcx]
0x18000da4c  mov     rax, [rax+10h]
0x18000da50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da55  mov     [rbp+57h+var_80], 0
0x18000da5d  test    r15, r15
0x18000da60  jz      short loc_18000DA6A
0x18000da62  mov     rcx, r15; Block
0x18000da65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000da6a  mov     rax, [rbp+57h+bstrString]
0x18000da6e  test    rax, rax
0x18000da71  jz      short loc_18000DA7C
0x18000da73  mov     rcx, rax; bstrString
0x18000da76  call    cs:__imp_SysFreeString
0x18000da7c  mov     rax, [rbp+57h+var_60]
0x18000da80  test    rax, rax
0x18000da83  jz      short loc_18000DA8E
0x18000da85  mov     rcx, rax; bstrString
0x18000da88  call    cs:__imp_SysFreeString
0x18000da8e  test    r13, r13
0x18000da91  jz      short loc_18000DA9C
0x18000da93  mov     rcx, r13; bstrString
0x18000da96  call    cs:__imp_SysFreeString
0x18000da9c  test    r14, r14
0x18000da9f  jz      short loc_18000DAA9
0x18000daa1  mov     rcx, r14; Block
0x18000daa4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000daa9  mov     eax, ebx
0x18000daab  mov     rcx, [rbp+57h+var_48]
0x18000daaf  xor     rcx, rsp; StackCookie
0x18000dab2  call    __security_check_cookie
0x18000dab7  add     rsp, 98h
0x18000dabe  pop     r15
0x18000dac0  pop     r14
0x18000dac2  pop     r13
0x18000dac4  pop     r12
0x18000dac6  pop     rdi
  ... truncated ...
```
