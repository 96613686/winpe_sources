# CClientLibrary::InitializeRpcSession(CClientLibrary::Session *,WDS_CRED *)

- ea: `0x18000726c`
- end: `0x1800077ed`
- name: `?InitializeRpcSession@CClientLibrary@@AEAAKPEAUSession@1@PEAUWDS_CRED@@@Z`
- size: `1409`
- prototype: `unsigned int __fastcall(CClientLibrary *__hidden this, struct Session *, struct WDS_CRED *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009b30`

## callees

- `0x1800018dc`
- `0x180005064`
- `0x18000726c`
- `0x18000bd5c`
- `0x18000e010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000777c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007795`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800077ad`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000777c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007795`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800077ad`
- `KERNEL32!CreateEventW` at `0x1800072c2`
- `KERNEL32!CreateEventW` at `0x1800072c2`
- `KERNEL32!GetLastError` at `0x1800072d6`
- `KERNEL32!GetLastError` at `0x180007333`
- `KERNEL32!GetLastError` at `0x18000736e`
- `KERNEL32!GetLastError` at `0x1800072d6`
- `KERNEL32!GetLastError` at `0x180007333`
- `KERNEL32!GetLastError` at `0x18000736e`
- `KERNEL32!CloseHandle` at `0x180007722`
- `KERNEL32!CloseHandle` at `0x180007737`
- `KERNEL32!CloseHandle` at `0x180007722`
- `KERNEL32!CloseHandle` at `0x180007737`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18000735e`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18000735e`
- `ADVAPI32!RevertToSelf` at `0x180007767`
- `ADVAPI32!RevertToSelf` at `0x180007767`
- `ADVAPI32!LogonUserW` at `0x180007323`
- `ADVAPI32!LogonUserW` at `0x180007323`
- `RPCRT4!RpcBindingFree` at `0x18000774d`
- `RPCRT4!RpcBindingFree` at `0x18000774d`
- `RPCRT4!RpcStringFreeW` at `0x1800077c3`
- `RPCRT4!RpcStringFreeW` at `0x1800077c3`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007441`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007441`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800076b6`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800076b6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000749b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000749b`
- `NTDSAPI!DsMakeSpnW` at `0x1800075b9`
- `NTDSAPI!DsMakeSpnW` at `0x180007661`
- `NTDSAPI!DsMakeSpnW` at `0x1800075b9`
- `NTDSAPI!DsMakeSpnW` at `0x180007661`
- `WdsCommonLib!?ResolveIpToHostName@CNetworkAddress@@SAKPEBGPEAPEAG@Z` at `0x18000755c`
- `WdsCommonLib!?ResolveIpToHostName@CNetworkAddress@@SAKPEBGPEAPEAG@Z` at `0x18000755c`
- `WdsCommonLib!?IsDomainJoined@@YAKPEAH@Z` at `0x1800074e2`
- `WdsCommonLib!?IsDomainJoined@@YAKPEAH@Z` at `0x1800074e2`
- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x1800073ee`
- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x1800073ee`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800075fc`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800075fc`

## pseudocode

```c
__int64 __fastcall CClientLibrary::InitializeRpcSession(CClientLibrary *this, struct Session *a2, struct WDS_CRED *a3)
{
  unsigned __int16 *v5; // r14
  int v6; // r12d
  HANDLE EventW; // r15
  DWORD v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rbx
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdx
  const wchar_t *v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rax
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // kr00_8
  WCHAR *pszSpn; // rax
  DWORD SpnW; // eax
  __int64 v35; // rdx
  __int64 v36; // rdx
  unsigned int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rdx
  HANDLE v40; // rcx
  DWORD dwLogonProvider[2]; // [rsp+20h] [rbp-59h]
  PHANDLE phToken; // [rsp+28h] [rbp-51h]
  HANDLE hToken; // [rsp+70h] [rbp-9h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+78h] [rbp-1h] BYREF
  LPCWSTR ServiceName; // [rsp+80h] [rbp+7h] BYREF
  RPC_WSTR StringBinding; // [rsp+88h] [rbp+Fh] BYREF
  RPC_WSTR ObjUuid; // [rsp+90h] [rbp+17h] BYREF
  DWORD pcSpnLength; // [rsp+E0h] [rbp+67h] BYREF
  int v50; // [rsp+E4h] [rbp+6Bh]
  int v51; // [rsp+F8h] [rbp+7Fh] BYREF

  v50 = HIDWORD(this);
  hToken = 0;
  Binding = 0;
  ObjUuid = 0;
  StringBinding = 0;
  ServiceName = 0;
  v5 = 0;
  v51 = 0;
  v6 = 0;
  pcSpnLength = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    if ( a3 )
    {
      if ( !LogonUserW(*(LPCWSTR *)a3, *((LPCWSTR *)a3 + 1), *((LPCWSTR *)a3 + 2), *((_DWORD *)a3 + 6), 0, &hToken) )
      {
        LastError = GetLastError();
        v13 = 804;
LABEL_6:
        v14 = ElValidateWin32(LastError, v12, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", v13);
LABEL_7:
        LODWORD(v10) = v14;
LABEL_40:
        CloseHandle(EventW);
        goto LABEL_41;
      }
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        LastError = GetLastError();
        v13 = 810;
        goto LABEL_6;
      }
      v6 = 1;
    }
    LODWORD(phToken) = 17747;
    dwLogonProvider[0] = 13614;
    LODWORD(v10) = FormatString(
                     &ObjUuid,
                     0x40u,
                     L"%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X",
                     445805460,
                     *(_QWORD *)dwLogonProvider,
                     phToken,
                     174,
                     63,
                     124,
                     244,
                     170,
                     252,
                     166,
                     32);
    if ( (unsigned int)ElValidateWin32((unsigned int)v10, v15, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 824) )
      goto LABEL_40;
    v16 = RpcStringBindingComposeW(ObjUuid, (RPC_WSTR)L"ncacn_ip_tcp", (RPC_WSTR)a2 + 540, 0, 0, &StringBinding);
    v10 = (unsigned int)ElValidateWin32(v16, v17, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 837);
    if ( (unsigned int)ElValidateWin32(v10, v18, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 839) )
      goto LABEL_40;
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(L"CClientLibrary::InitializeRpcSession: Binding String=%s", StringBinding);
    v19 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    LODWORD(v10) = ElValidateWin32(v19, v20, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 843);
    if ( (unsigned int)ElValidateWin32((unsigned int)v10, v21, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 844) )
      goto LABEL_40;
    if ( (*((_BYTE *)a2 + 1060) & 1) != 0 )
    {
      v22 = IsDomainJoined(&v51);
      v10 = (unsigned int)ElValidateWin32(v22, v23, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 853);
      if ( (unsigned int)ElValidateWin32(v10, v24, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 854) )
        goto LABEL_40;
      if ( g_ErrLibTraceFunction )
      {
        v25 = L"Yes";
        if ( !v51 )
          v25 = L"No";
        g_ErrLibTraceFunction(L"CClientLibrary::InitializeRpcSession: Domain Joined=%s", v25);
      }
      if ( v51 )
      {
        v26 = CNetworkAddress::ResolveIpToHostName(
                (const unsigned __int16 *)a2 + 540,
                (unsigned __int16 **)&ServiceName);
        LODWORD(v10) = ElValidateWin32(v26, v27, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 869);
        if ( (unsigned int)ElValidateWin32((unsigned int)v10, v28, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 871) )
          goto LABEL_40;
        if ( DsMakeSpnW(L"host", ServiceName, 0, 0, 0, &pcSpnLength, 0) == 111 )
        {
          LODWORD(v30) = pcSpnLength;
        }
        else
        {
          v29 = -1;
          do
            ++v29;
          while ( ServiceName[v29] );
          v30 = v29 + 1029;
          if ( v30 > 0xFFFFFFFF )
          {
            pcSpnLength = -1;
            v14 = WIN32_FROM_HRESULT(-2147024362);
            goto LABEL_7;
          }
          pcSpnLength = v30;
        }
        v32 = (unsigned int)v30;
        v31 = 2LL * (unsigned int)v30;
        if ( !is_mul_ok(v32, 2u) )
          v31 = -1;
        pszSpn = (WCHAR *)operator new[](v31, (const struct std::nothrow_t *)&std::nothrow);
        v5 = pszSpn;
        if ( !pszSpn )
        {
          LODWORD(v10) = 8;
          goto LABEL_40;
        }
        SpnW = DsMakeSpnW(L"host", ServiceName, 0, 0, 0, &pcSpnLength, pszSpn);
        LODWORD(v10) = ElValidateWin32(SpnW, v35, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 911);
        if ( (unsigned int)ElValidateWin32((unsigned int)v10, v36, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 913) )
          goto LABEL_40;
      }
      v37 = RpcBindingSetAuthInfoW(Binding, v5, 6u, 9u, 0, 0xFFFFFFFF);
      LODWORD(v10) = ElValidateWin32(v37, v38, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 925);
      if ( (unsigned int)ElValidateWin32((unsigned int)v10, v39, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 927) )
        goto LABEL_40;
    }
    v40 = 0;
    *((_QWORD *)a2 + 268) = hToken;
    *((_QWORD *)a2 + 267) = Binding;
    *((_QWORD *)a2 + 266) = EventW;
    hToken = 0;
    Binding = 0;
    goto LABEL_42;
  }
  v8 = GetLastError();
  LODWORD(v10) = ElValidateWin32(v8, v9, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 788);
LABEL_41:
  v40 = hToken;
LABEL_42:
  if ( v40 )
    CloseHandle(v40);
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( (_DWORD)v10 )
    CClientLibrary::DumpRpcErrors((CClientLibrary *)v40);
  if ( v6 )
    RevertToSelf();
  if ( ObjUuid )
  {
    operator delete[](ObjUuid);
    ObjUuid = 0;
  }
  if ( ServiceName )
  {
    operator delete[]((void *)ServiceName);
    ServiceName = 0;
  }
  if ( v5 )
    operator delete[](v5);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000726c  mov     [rsp-8+arg_8], rbx
0x180007271  mov     qword ptr [rsp-8+pcSpnLength], rcx
0x180007276  push    rbp
0x180007277  push    rsi
0x180007278  push    rdi
0x180007279  push    r12
0x18000727b  push    r13
0x18000727d  push    r14
0x18000727f  push    r15
0x180007281  lea     rbp, [rsp-27h]
0x180007286  sub     rsp, 0A0h
0x18000728d  xor     r13d, r13d
0x180007290  mov     rbx, r8
0x180007293  mov     rsi, rdx
0x180007296  mov     [rbp+57h+hToken], r13
0x18000729a  xor     r8d, r8d; bInitialState
0x18000729d  mov     [rbp+57h+Binding], r13
0x1800072a1  xor     edx, edx; bManualReset
0x1800072a3  mov     [rbp+57h+ObjUuid], r13
0x1800072a7  xor     r9d, r9d; lpName
0x1800072aa  mov     [rbp+57h+StringBinding], r13
0x1800072ae  xor     ecx, ecx; lpEventAttributes
0x1800072b0  mov     [rbp+57h+ServiceName], r13
0x1800072b4  mov     r14d, r13d
0x1800072b7  mov     [rbp+57h+arg_18], r13d
0x1800072bb  mov     r12d, r13d
0x1800072be  mov     [rbp+57h+pcSpnLength], r13d
0x1800072c2  call    cs:__imp_CreateEventW
0x1800072c9  nop     dword ptr [rax+rax+00h]
0x1800072ce  mov     r15, rax
0x1800072d1  test    rax, rax
0x1800072d4  jnz     short loc_1800072FD
0x1800072d6  call    cs:__imp_GetLastError
0x1800072dd  nop     dword ptr [rax+rax+00h]
0x1800072e2  mov     r9d, 314h
0x1800072e8  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x1800072ef  mov     ecx, eax
0x1800072f1  call    ElValidateWin32
0x1800072f6  mov     ebx, eax
0x1800072f8  jmp     loc_18000772E
0x1800072fd  test    rbx, rbx
0x180007300  jz      loc_180007388
0x180007306  mov     r9d, [rbx+18h]; dwLogonType
0x18000730a  lea     rax, [rbp+57h+hToken]
0x18000730e  mov     r8, [rbx+10h]; lpszPassword
0x180007312  mov     rdx, [rbx+8]; lpszDomain
0x180007316  mov     rcx, [rbx]; lpszUsername
0x180007319  mov     [rsp+0D0h+phToken], rax; phToken
0x18000731e  mov     [rsp+0D0h+dwLogonProvider], r13d; dwLogonProvider
0x180007323  call    cs:__imp_LogonUserW
0x18000732a  nop     dword ptr [rax+rax+00h]
0x18000732f  test    eax, eax
0x180007331  jnz     short loc_18000735A
0x180007333  call    cs:__imp_GetLastError
0x18000733a  nop     dword ptr [rax+rax+00h]
0x18000733f  mov     r9d, 324h
0x180007345  mov     ecx, eax
0x180007347  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x18000734e  call    ElValidateWin32
0x180007353  mov     ebx, eax
0x180007355  jmp     loc_18000771F
0x18000735a  mov     rcx, [rbp+57h+hToken]; hToken
0x18000735e  call    cs:__imp_ImpersonateLoggedOnUser
0x180007365  nop     dword ptr [rax+rax+00h]
0x18000736a  test    eax, eax
0x18000736c  jnz     short loc_180007382
0x18000736e  call    cs:__imp_GetLastError
0x180007375  nop     dword ptr [rax+rax+00h]
0x18000737a  mov     r9d, 32Ah
0x180007380  jmp     short loc_180007345
0x180007382  mov     r12d, 1
0x180007388  mov     [rsp+0D0h+var_68], 20h ; ' '
0x180007390  lea     r8, a08x04x04x02x02; "%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02"...
0x180007397  mov     [rsp+0D0h+var_70], 0A6h
0x18000739f  lea     rcx, [rbp+57h+ObjUuid]
0x1800073a3  mov     [rsp+0D0h+var_78], 0FCh
0x1800073ab  mov     r9d, 1A927394h
0x1800073b1  mov     [rsp+0D0h+var_80], 0AAh
0x1800073b9  mov     edx, 40h ; '@'
0x1800073be  mov     [rsp+0D0h+var_88], 0F4h
0x1800073c6  mov     [rsp+0D0h+var_90], 7Ch ; '|'
0x1800073ce  mov     [rsp+0D0h+var_98], 3Fh ; '?'
0x1800073d6  mov     dword ptr [rsp+0D0h+pszSpn], 0AEh
0x1800073de  mov     dword ptr [rsp+0D0h+phToken], 4553h
0x1800073e6  mov     [rsp+0D0h+dwLogonProvider], 352Eh; Options
0x1800073ee  call    cs:__imp_?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x1800073f5  nop     dword ptr [rax+rax+00h]
0x1800073fa  lea     rdi, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180007401  mov     r9d, 338h
0x180007407  mov     r8, rdi
0x18000740a  mov     ecx, eax
0x18000740c  mov     ebx, eax
0x18000740e  call    ElValidateWin32
0x180007413  test    eax, eax
0x180007415  jnz     loc_18000771F
0x18000741b  mov     rcx, [rbp+57h+ObjUuid]; ObjUuid
0x18000741f  lea     rax, [rbp+57h+StringBinding]
0x180007423  mov     [rsp+0D0h+phToken], rax; StringBinding
0x180007428  lea     r13, [rsi+438h]
0x18000742f  and     qword ptr [rsp+0D0h+dwLogonProvider], r14
0x180007434  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18000743b  mov     r8, r13; NetworkAddr
0x18000743e  xor     r9d, r9d; Endpoint
0x180007441  call    cs:__imp_RpcStringBindingComposeW
0x180007448  nop     dword ptr [rax+rax+00h]
0x18000744d  mov     r9d, 345h
0x180007453  mov     r8, rdi
0x180007456  mov     ecx, eax
0x180007458  call    ElValidateWin32
0x18000745d  mov     r9d, 347h
0x180007463  mov     r8, rdi
0x180007466  mov     ecx, eax
0x180007468  mov     ebx, eax
0x18000746a  call    ElValidateWin32
0x18000746f  test    eax, eax
0x180007471  jnz     loc_18000771C
0x180007477  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000747e  test    rax, rax
0x180007481  jz      short loc_180007493
0x180007483  mov     rdx, [rbp+57h+StringBinding]
0x180007487  lea     rcx, aCclientlibrary_0; "CClientLibrary::InitializeRpcSession: B"...
0x18000748e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007493  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x180007497  lea     rdx, [rbp+57h+Binding]; Binding
0x18000749b  call    cs:__imp_RpcBindingFromStringBindingW
0x1800074a2  nop     dword ptr [rax+rax+00h]
0x1800074a7  mov     r9d, 34Bh
0x1800074ad  mov     r8, rdi
0x1800074b0  mov     ecx, eax
0x1800074b2  call    ElValidateWin32
0x1800074b7  mov     r9d, 34Ch
0x1800074bd  mov     r8, rdi
0x1800074c0  mov     ecx, eax
0x1800074c2  mov     ebx, eax
0x1800074c4  call    ElValidateWin32
0x1800074c9  test    eax, eax
0x1800074cb  jnz     loc_18000771C
0x1800074d1  test    byte ptr [rsi+424h], 1
0x1800074d8  jz      loc_1800076EF
0x1800074de  lea     rcx, [rbp+57h+arg_18]
0x1800074e2  call    cs:__imp_?IsDomainJoined@@YAKPEAH@Z; IsDomainJoined(int *)
0x1800074e9  nop     dword ptr [rax+rax+00h]
0x1800074ee  mov     r9d, 355h
0x1800074f4  mov     r8, rdi
0x1800074f7  mov     ecx, eax
0x1800074f9  call    ElValidateWin32
0x1800074fe  mov     r9d, 356h
0x180007504  mov     r8, rdi
0x180007507  mov     ecx, eax
0x180007509  mov     ebx, eax
0x18000750b  call    ElValidateWin32
0x180007510  test    eax, eax
0x180007512  jnz     loc_18000771C
0x180007518  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000751f  test    rax, rax
0x180007522  jz      short loc_180007546
0x180007524  cmp     [rbp+57h+arg_18], r14d
0x180007528  lea     rcx, aNo; "No"
0x18000752f  lea     rdx, aYes; "Yes"
0x180007536  cmovz   rdx, rcx
0x18000753a  lea     rcx, aCclientlibrary; "CClientLibrary::InitializeRpcSession: D"...
0x180007541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007546  mov     eax, 0FFFFFFFFh
0x18000754b  cmp     [rbp+57h+arg_18], r14d
0x18000754f  jz      loc_1800076EA
0x180007555  lea     rdx, [rbp+57h+ServiceName]
0x180007559  mov     rcx, r13
0x18000755c  call    cs:__imp_?ResolveIpToHostName@CNetworkAddress@@SAKPEBGPEAPEAG@Z; CNetworkAddress::ResolveIpToHostName(ushort const *,ushort * *)
0x180007563  nop     dword ptr [rax+rax+00h]
0x180007568  mov     r9d, 365h
0x18000756e  mov     r8, rdi
0x180007571  mov     ecx, eax
0x180007573  call    ElValidateWin32
0x180007578  mov     r9d, 367h
0x18000757e  mov     r8, rdi
0x180007581  mov     ecx, eax
0x180007583  mov     ebx, eax
0x180007585  call    ElValidateWin32
0x18000758a  xor     r13d, r13d
0x18000758d  test    eax, eax
0x18000758f  jnz     loc_18000771F
0x180007595  mov     rdx, [rbp+57h+ServiceName]; ServiceName
0x180007599  lea     rax, [rbp+57h+pcSpnLength]
0x18000759d  mov     [rsp+0D0h+pszSpn], r13; pszSpn
0x1800075a2  lea     rcx, ServiceClass; "host"
0x1800075a9  mov     [rsp+0D0h+phToken], rax; pcSpnLength
0x1800075ae  xor     r9d, r9d; InstancePort
0x1800075b1  xor     r8d, r8d; InstanceName
0x1800075b4  mov     qword ptr [rsp+0D0h+dwLogonProvider], r13; Referrer
0x1800075b9  call    cs:__imp_DsMakeSpnW
0x1800075c0  nop     dword ptr [rax+rax+00h]
0x1800075c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800075c9  cmp     eax, 6Fh ; 'o'
0x1800075cc  jz      short loc_18000760D
0x1800075ce  mov     rcx, [rbp+57h+ServiceName]
0x1800075d2  mov     rax, r8
0x1800075d5  inc     rax
0x1800075d8  cmp     [rcx+rax*2], r13w
0x1800075dd  jnz     short loc_1800075D5
0x1800075df  add     rax, 405h
0x1800075e5  mov     ecx, 0FFFFFFFFh
0x1800075ea  cmp     rax, rcx
0x1800075ed  ja      short loc_1800075F4
0x1800075ef  mov     [rbp+57h+pcSpnLength], eax
0x1800075f2  jmp     short loc_180007610
0x1800075f4  mov     [rbp+57h+pcSpnLength], ecx
0x1800075f7  mov     ecx, 80070216h
0x1800075fc  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180007603  nop     dword ptr [rax+rax+00h]
0x180007608  jmp     loc_180007353
0x18000760d  mov     eax, [rbp+57h+pcSpnLength]
0x180007610  mov     ecx, eax
0x180007612  mov     eax, 2
0x180007617  mul     rcx
0x18000761a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007621  cmovo   rax, r8
0x180007625  mov     rcx, rax; unsigned __int64
0x180007628  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000762d  mov     r14, rax
0x180007630  test    rax, rax
0x180007633  jnz     short loc_18000763D
0x180007635  lea     ebx, [rax+8]
0x180007638  jmp     loc_18000771F
0x18000763d  mov     rdx, [rbp+57h+ServiceName]; ServiceName
0x180007641  lea     rcx, ServiceClass; "host"
0x180007648  mov     [rsp+0D0h+pszSpn], rax; pszSpn
0x18000764d  xor     r9d, r9d; InstancePort
0x180007650  lea     rax, [rbp+57h+pcSpnLength]
0x180007654  xor     r8d, r8d; InstanceName
0x180007657  mov     [rsp+0D0h+phToken], rax; pcSpnLength
0x18000765c  mov     qword ptr [rsp+0D0h+dwLogonProvider], r13; Referrer
0x180007661  call    cs:__imp_DsMakeSpnW
0x180007668  nop     dword ptr [rax+rax+00h]
0x18000766d  mov     r9d, 38Fh
0x180007673  mov     r8, rdi
0x180007676  mov     ecx, eax
0x180007678  call    ElValidateWin32
0x18000767d  mov     r9d, 391h
0x180007683  mov     r8, rdi
0x180007686  mov     ecx, eax
0x180007688  mov     ebx, eax
0x18000768a  call    ElValidateWin32
0x18000768f  test    eax, eax
0x180007691  jnz     loc_18000771F
0x180007697  mov     eax, 0FFFFFFFFh
0x18000769c  mov     rcx, [rbp+57h+Binding]; Binding
0x1800076a0  mov     r9d, 9; AuthnSvc
0x1800076a6  mov     dword ptr [rsp+0D0h+phToken], eax; AuthzSvc
0x1800076aa  mov     rdx, r14; ServerPrincName
0x1800076ad  mov     qword ptr [rsp+0D0h+dwLogonProvider], r13; AuthIdentity
0x1800076b2  lea     r8d, [r9-3]; AuthnLevel
0x1800076b6  call    cs:__imp_RpcBindingSetAuthInfoW
0x1800076bd  nop     dword ptr [rax+rax+00h]
0x1800076c2  mov     r9d, 39Dh
0x1800076c8  mov     r8, rdi
0x1800076cb  mov     ecx, eax
0x1800076cd  call    ElValidateWin32
0x1800076d2  mov     r9d, 39Fh
0x1800076d8  mov     r8, rdi
0x1800076db  mov     ecx, eax
0x1800076dd  mov     ebx, eax
0x1800076df  call    ElValidateWin32
0x1800076e4  test    eax, eax
0x1800076e6  jnz     short loc_18000771F
0x1800076e8  jmp     short loc_1800076F2
0x1800076ea  xor     r13d, r13d
0x1800076ed  jmp     short loc_18000769C
0x1800076ef  xor     r13d, r13d
0x1800076f2  mov     rax, [rbp+57h+hToken]
0x1800076f6  mov     rcx, r13
0x1800076f9  mov     [rsi+860h], rax
0x180007700  mov     rax, [rbp+57h+Binding]
0x180007704  mov     [rsi+858h], rax
0x18000770b  mov     [rsi+850h], r15
0x180007712  mov     [rbp+57h+hToken], rcx
0x180007716  mov     [rbp+57h+Binding], r13
0x18000771a  jmp     short loc_180007732
0x18000771c  xor     r13d, r13d
0x18000771f  mov     rcx, r15; hObject
0x180007722  call    cs:__imp_CloseHandle
0x180007729  nop     dword ptr [rax+rax+00h]
0x18000772e  mov     rcx, [rbp+57h+hToken]; hObject
0x180007732  test    rcx, rcx
0x180007735  jz      short loc_180007743
0x180007737  call    cs:__imp_CloseHandle
0x18000773e  nop     dword ptr [rax+rax+00h]
0x180007743  cmp     [rbp+57h+Binding], r13
0x180007747  jz      short loc_180007759
0x180007749  lea     rcx, [rbp+57h+Binding]; Binding
0x18000774d  call    cs:__imp_RpcBindingFree
0x180007754  nop     dword ptr [rax+rax+00h]
0x180007759  test    ebx, ebx
0x18000775b  jz      short loc_180007762
0x18000775d  call    ?DumpRpcErrors@CClientLibrary@@AEAAXXZ; CClientLibrary::DumpRpcErrors(void)
0x180007762  test    r12d, r12d
0x180007765  jz      short loc_180007773
0x180007767  call    cs:__imp_RevertToSelf
0x18000776e  nop     dword ptr [rax+rax+00h]
0x180007773  mov     rcx, [rbp+57h+ObjUuid]
0x180007777  test    rcx, rcx
  ... truncated ...
```
