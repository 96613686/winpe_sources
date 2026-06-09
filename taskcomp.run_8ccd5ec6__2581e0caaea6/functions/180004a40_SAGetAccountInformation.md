# SAGetAccountInformation

- ea: `0x180004a40`
- end: `0x180004fea`
- name: `SAGetAccountInformation`
- size: `1450`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003320`
- `0x180004090`
- `0x1800040c0`
- `0x180004138`
- `0x180004a40`
- `0x180004ff0`
- `0x180005010`
- `0x180005094`
- `0x1800050d0`
- `0x1800052d8`
- `0x1800053bc`
- `0x1800053e8`
- `0x180005650`
- `0x180005c10`
- `0x180006764`
- `0x18000a044`
- `0x18000b0ac`
- `0x18000d128`
- `0x180011894`
- `0x180011e6c`
- `0x18002cdb0`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `msvcrt!wcschr` at `0x180004b10`
- `msvcrt!wcschr` at `0x180004b2b`
- `msvcrt!wcschr` at `0x180004b10`
- `msvcrt!wcschr` at `0x180004b2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004d0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004d0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004ceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1e`
- `RPCRT4!RpcRevertToSelf` at `0x180004d3d`
- `RPCRT4!RpcRevertToSelf` at `0x180004da8`
- `RPCRT4!RpcRevertToSelf` at `0x180004e46`
- `RPCRT4!RpcRevertToSelf` at `0x180004e8c`
- `RPCRT4!RpcRevertToSelf` at `0x180004d3d`
- `RPCRT4!RpcRevertToSelf` at `0x180004da8`
- `RPCRT4!RpcRevertToSelf` at `0x180004e46`
- `RPCRT4!RpcRevertToSelf` at `0x180004e8c`
- `RPCRT4!RpcImpersonateClient` at `0x180004c95`
- `RPCRT4!RpcImpersonateClient` at `0x180004c95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c64`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c64`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004c82`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004c47`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004c47`

## string_xrefs

- `0x180004c5d`: `CoInitializeEx failed inside SAGetAccountInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall SAGetAccountInformation(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  unsigned __int64 v5; // r14
  bool v8; // r8
  int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rcx
  bool v12; // r8
  int v13; // ebx
  HRESULT v14; // ebx
  RPC_STATUS v15; // eax
  EventManager *v16; // rcx
  signed int v17; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v20; // edi
  RPC_STATUS v21; // eax
  unsigned int v22; // ebx
  RPC_STATUS v23; // eax
  int v24; // r8d
  CompatibilityAdapter *v25; // rcx
  int UserInfo; // ebx
  int v27; // edx
  const WCHAR *v28; // rdx
  int v29; // ebx
  const unsigned __int16 *v30; // r8
  void *v31; // [rsp+20h] [rbp-6B8h]
  const struct _GUID *v32; // [rsp+28h] [rbp-6B0h]
  bool v33; // [rsp+34h] [rbp-6A4h] BYREF
  __int64 v34; // [rsp+38h] [rbp-6A0h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-698h] BYREF
  const WCHAR **v36; // [rsp+48h] [rbp-690h] BYREF
  _BYTE v37[8]; // [rsp+50h] [rbp-688h] BYREF
  void (__stdcall *v38)(); // [rsp+58h] [rbp-680h]
  _QWORD v39[2]; // [rsp+60h] [rbp-678h] BYREF
  _BYTE v40[528]; // [rsp+70h] [rbp-668h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-458h] BYREF
  unsigned __int16 v42[264]; // [rsp+490h] [rbp-248h] BYREF

  v5 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids, a2);
  }
  if ( !CompatibilityAdapter::GetAdapter() )
    return 2147500037LL;
  TaskLock::TaskLock((TaskLock *)v40, a2);
  v9 = RPCFolderAccessCheck(g_TasksFolderInfo, 1u, v8);
  if ( v9 < 0 )
    goto LABEL_8;
  if ( !a2 || !a4 || wcschr(a2, 0x5Cu) || wcschr(a2, 0x2Fu) )
  {
    TaskLock::~TaskLock((TaskLock *)v40);
    return 2147942487LL;
  }
  memset_0(FileName, 0, 0x20Au);
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( g_TasksFolderInfo[v11] );
  do
    ++v10;
  while ( a2[v10] );
  if ( (unsigned __int64)(v11 + v10 + 2) > 0x105 )
  {
    TaskLock::~TaskLock((TaskLock *)v40);
    return 2147750669LL;
  }
  StringCchCopyW(FileName, 0x105u, g_TasksFolderInfo);
  StringCchCatW(FileName, 0x105u, L"\\");
  StringCchCatW(FileName, 0x105u, a2);
  v9 = RPCFolderAccessCheck(FileName, 1u, v12);
  if ( v9 < 0 )
  {
LABEL_8:
    TaskLock::~TaskLock((TaskLock *)v40);
    return (unsigned int)v9;
  }
  memset_0(v42, 0, 0x20Au);
  v13 = FilenameToUri(a2, v42);
  if ( v13 < 0 )
  {
    TaskLock::~TaskLock((TaskLock *)v40);
    return (unsigned int)v13;
  }
  v14 = CoInitializeEx(0, 0);
  if ( v14 < 0 )
  {
    OutputDebugStringW(L"CoInitializeEx failed inside SAGetAccountInformation");
    TaskLock::~TaskLock((TaskLock *)v40);
    return (unsigned int)v14;
  }
  v37[0] = 0;
  v38 = CoUninitialize;
  v15 = RpcImpersonateClient(0);
  v17 = v15;
  if ( v15 )
  {
    EventManager::EvtReport(v16, &IMPERSONATION_FAILURE, L"SAGetAccountInformation", v15, v31, v32);
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v37);
    TaskLock::~TaskLock((TaskLock *)v40);
    return (unsigned int)v17;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v20 = LastError;
    if ( LastError > 0 )
      v20 = (unsigned __int16)LastError | 0x80070000;
    v21 = RpcRevertToSelf();
    v22 = v21;
    if ( !v21 )
    {
      wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
      wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v37);
      TaskLock::~TaskLock((TaskLock *)v40);
      return v20;
    }
    if ( v21 > 0 )
      v22 = (unsigned __int16)v21 | 0x80070000;
LABEL_33:
    wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
    wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v37);
    TaskLock::~TaskLock((TaskLock *)v40);
    return v22;
  }
  v23 = RpcRevertToSelf();
  v22 = v23;
  if ( v23 )
  {
    if ( v23 > 0 )
      v22 = (unsigned __int16)v23 | 0x80070000;
    goto LABEL_33;
  }
  v36 = 0;
  RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v34, L"SAGetAccountInformation", v24);
  v33 = 0;
  UserInfo = CompatibilityAdapter::GetUserInfo(v25, v42, (struct _bstr_t *)&v36, &v33);
  if ( tsched::IsErrorNotFound((tsched *)(unsigned int)UserInfo, v27) )
  {
    UserInfo = -2147216625;
LABEL_42:
    if ( (_DWORD)v34 )
      RpcRevertToSelf();
    _bstr_t::~_bstr_t((_bstr_t *)&v36);
    wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
    wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v37);
    TaskLock::~TaskLock((TaskLock *)v40);
    return (unsigned int)UserInfo;
  }
  if ( UserInfo < 0 )
    goto LABEL_42;
  if ( (_DWORD)v34 )
    RpcRevertToSelf();
  v34 = 0;
  if ( v36 )
    v28 = *v36;
  else
    v28 = 0;
  v29 = User::FromUsername((struct User *)&v34, v28);
  if ( v29 >= 0 )
  {
    if ( User::IsLocalSystem((User *)&v34) )
    {
      *a4 = 0;
    }
    else
    {
      User::GetDomainAccount(&v34, v39);
      if ( (unsigned int)v5 <= _bstr_t::length((_bstr_t *)v39) + 1 )
      {
        v29 = -2147024774;
      }
      else
      {
        if ( v39[0] )
          v30 = *(const unsigned __int16 **)v39[0];
        else
          v30 = 0;
        v29 = StringCchCopyW(a4, v5, v30);
      }
      _bstr_t::~_bstr_t((_bstr_t *)v39);
    }
  }
  wmi::AutoRef<User::UserEntry>::Release(&v34);
  _bstr_t::~_bstr_t((_bstr_t *)&v36);
  wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
  wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v37);
  TaskLock::~TaskLock((TaskLock *)v40);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180004a40  push    rbx
0x180004a42  push    rsi
0x180004a43  push    rdi
0x180004a44  push    r14
0x180004a46  push    r15
0x180004a48  sub     rsp, 6B0h
0x180004a4f  mov     rax, cs:__security_cookie
0x180004a56  xor     rax, rsp
0x180004a59  mov     [rsp+6D8h+var_38], rax
0x180004a61  mov     rsi, r9
0x180004a64  mov     r14d, r8d
0x180004a67  mov     rbx, rdx
0x180004a6a  xor     r15d, r15d
0x180004a6d  mov     [rsp+6D8h+var_6A8], r15d
0x180004a72  lea     rax, WPP_GLOBAL_Control
0x180004a79  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a80  cmp     rcx, rax
0x180004a83  jz      short loc_180004AA8
0x180004a85  test    byte ptr [rcx+1Ch], 2
0x180004a89  jz      short loc_180004AA8
0x180004a8b  cmp     byte ptr [rcx+19h], 4
0x180004a8f  jb      short loc_180004AA8
0x180004a91  lea     edx, [r15+0Bh]
0x180004a95  mov     r9, rbx
0x180004a98  lea     r8, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids
0x180004a9f  mov     rcx, [rcx+10h]
0x180004aa3  call    WPP_SF_S
0x180004aa8  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180004aad  test    rax, rax
0x180004ab0  jnz     short loc_180004ABC
0x180004ab2  mov     eax, 80004005h
0x180004ab7  jmp     loc_180004FCA
0x180004abc  mov     rdx, rbx; unsigned __int16 *
0x180004abf  lea     rcx, [rsp+6D8h+var_668]; this
0x180004ac4  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x180004ac9  nop
0x180004aca  mov     edx, 1; DesiredAccess
0x180004acf  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpFileName
0x180004ad6  call    ?RPCFolderAccessCheck@@YAJPEBGK_N@Z; RPCFolderAccessCheck(ushort const *,ulong,bool)
0x180004adb  mov     edi, eax
0x180004add  mov     [rsp+6D8h+var_6A8], eax
0x180004ae1  test    eax, eax
0x180004ae3  jns     short loc_180004AF6
0x180004ae5  lea     rcx, [rsp+6D8h+var_668]; this
0x180004aea  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004aef  mov     eax, edi
0x180004af1  jmp     loc_180004FCA
0x180004af6  test    rbx, rbx
0x180004af9  jz      loc_180004FB3
0x180004aff  test    rsi, rsi
0x180004b02  jz      loc_180004FB3
0x180004b08  mov     edx, 5Ch ; '\'; Ch
0x180004b0d  mov     rcx, rbx; Str
0x180004b10  call    cs:__imp_wcschr
0x180004b17  nop     dword ptr [rax+rax+00h]
0x180004b1c  test    rax, rax
0x180004b1f  jnz     loc_180004FA2
0x180004b25  lea     edx, [rax+2Fh]; Ch
0x180004b28  mov     rcx, rbx; Str
0x180004b2b  call    cs:__imp_wcschr
0x180004b32  nop     dword ptr [rax+rax+00h]
0x180004b37  test    rax, rax
0x180004b3a  jnz     loc_180004FA2
0x180004b40  xor     edx, edx; Val
0x180004b42  mov     r8d, 20Ah; Size
0x180004b48  lea     rcx, [rsp+6D8h+FileName]; void *
0x180004b50  call    memset_0
0x180004b55  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180004b5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004b60  mov     rcx, rax
0x180004b63  inc     rcx
0x180004b66  cmp     [r8+rcx*2], r15w
0x180004b6b  jnz     short loc_180004B63
0x180004b6d  inc     rax
0x180004b70  cmp     [rbx+rax*2], r15w
0x180004b75  jnz     short loc_180004B6D
0x180004b77  add     rax, 2
0x180004b7b  add     rax, rcx
0x180004b7e  mov     edi, 105h
0x180004b83  cmp     rax, rdi
0x180004b86  jbe     short loc_180004B9C
0x180004b88  lea     rcx, [rsp+6D8h+var_668]; this
0x180004b8d  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004b92  mov     eax, 8004130Dh
0x180004b97  jmp     loc_180004FCA
0x180004b9c  mov     rdx, rdi; unsigned __int64
0x180004b9f  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x180004ba7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004bac  lea     r8, asc_1800516CC; "\\"
0x180004bb3  mov     rdx, rdi; unsigned __int64
0x180004bb6  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x180004bbe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004bc3  mov     r8, rbx; unsigned __int16 *
0x180004bc6  mov     rdx, rdi; unsigned __int64
0x180004bc9  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x180004bd1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004bd6  mov     edx, 1; DesiredAccess
0x180004bdb  lea     rcx, [rsp+6D8h+FileName]; lpFileName
0x180004be3  call    ?RPCFolderAccessCheck@@YAJPEBGK_N@Z; RPCFolderAccessCheck(ushort const *,ulong,bool)
0x180004be8  mov     edi, eax
0x180004bea  mov     [rsp+6D8h+var_6A8], eax
0x180004bee  test    eax, eax
0x180004bf0  jns     short loc_180004C03
0x180004bf2  lea     rcx, [rsp+6D8h+var_668]; this
0x180004bf7  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004bfc  mov     eax, edi
0x180004bfe  jmp     loc_180004FCA
0x180004c03  xor     edx, edx; Val
0x180004c05  mov     r8d, 20Ah; Size
0x180004c0b  lea     rcx, [rsp+6D8h+var_248]; void *
0x180004c13  call    memset_0
0x180004c18  lea     rdx, [rsp+6D8h+var_248]; unsigned __int16 *
0x180004c20  mov     rcx, rbx; unsigned __int16 *
0x180004c23  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x180004c28  mov     ebx, eax
0x180004c2a  mov     [rsp+6D8h+var_6A8], eax
0x180004c2e  test    eax, eax
0x180004c30  jns     short loc_180004C43
0x180004c32  lea     rcx, [rsp+6D8h+var_668]; this
0x180004c37  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004c3c  mov     eax, ebx
0x180004c3e  jmp     loc_180004FCA
0x180004c43  xor     edx, edx; dwCoInit
0x180004c45  xor     ecx, ecx; pvReserved
0x180004c47  call    cs:__imp_CoInitializeEx
0x180004c4e  nop     dword ptr [rax+rax+00h]
0x180004c53  mov     ebx, eax
0x180004c55  mov     [rsp+6D8h+var_6A8], eax
0x180004c59  test    eax, eax
0x180004c5b  jns     short loc_180004C82
0x180004c5d  lea     rcx, OutputString; "CoInitializeEx failed inside SAGetAccou"...
0x180004c64  call    cs:__imp_OutputDebugStringW
0x180004c6b  nop     dword ptr [rax+rax+00h]
0x180004c70  nop
0x180004c71  lea     rcx, [rsp+6D8h+var_668]; this
0x180004c76  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004c7b  mov     eax, ebx
0x180004c7d  jmp     loc_180004FCA
0x180004c82  mov     rax, cs:__imp_CoUninitialize
0x180004c89  mov     [rsp+6D8h+var_688], r15b
0x180004c8e  mov     [rsp+6D8h+var_680], rax
0x180004c93  xor     ecx, ecx; BindingHandle
0x180004c95  call    cs:__imp_RpcImpersonateClient
0x180004c9c  nop     dword ptr [rax+rax+00h]
0x180004ca1  mov     ebx, eax
0x180004ca3  test    eax, eax
0x180004ca5  jz      short loc_180004CE6
0x180004ca7  mov     r9d, eax; unsigned int
0x180004caa  lea     r8, aSagetaccountin; "SAGetAccountInformation"
0x180004cb1  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180004cb8  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180004cbd  test    ebx, ebx
0x180004cbf  jle     short loc_180004CCA
0x180004cc1  movzx   ebx, bx
0x180004cc4  or      ebx, 80070000h
0x180004cca  lea     rcx, [rsp+6D8h+var_688]
0x180004ccf  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004cd4  nop
0x180004cd5  lea     rcx, [rsp+6D8h+var_668]; this
0x180004cda  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004cdf  mov     eax, ebx
0x180004ce1  jmp     loc_180004FCA
0x180004ce6  mov     [rsp+6D8h+TokenHandle], r15
0x180004ceb  call    cs:__imp_GetCurrentThread
0x180004cf2  nop     dword ptr [rax+rax+00h]
0x180004cf7  lea     r9, [rsp+6D8h+TokenHandle]; TokenHandle
0x180004cfc  mov     edx, 2000Eh; DesiredAccess
0x180004d01  mov     r8d, 1; OpenAsSelf
0x180004d07  mov     rcx, rax; ThreadHandle
0x180004d0a  call    cs:__imp_OpenThreadToken
0x180004d11  nop     dword ptr [rax+rax+00h]
0x180004d16  test    eax, eax
0x180004d18  jnz     loc_180004DA8
0x180004d1e  call    cs:__imp_GetLastError
0x180004d25  nop     dword ptr [rax+rax+00h]
0x180004d2a  mov     edi, eax
0x180004d2c  test    eax, eax
0x180004d2e  jle     short loc_180004D39
0x180004d30  movzx   edi, ax
0x180004d33  or      edi, 80070000h
0x180004d39  mov     [rsp+6D8h+var_6A8], edi
0x180004d3d  call    cs:__imp_RpcRevertToSelf
0x180004d44  nop     dword ptr [rax+rax+00h]
0x180004d49  mov     ebx, eax
0x180004d4b  test    eax, eax
0x180004d4d  jz      short loc_180004D81
0x180004d4f  jle     short loc_180004D5A
0x180004d51  movzx   ebx, ax
0x180004d54  or      ebx, 80070000h
0x180004d5a  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004d5f  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004d64  nop
0x180004d65  lea     rcx, [rsp+6D8h+var_688]
0x180004d6a  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004d6f  nop
0x180004d70  lea     rcx, [rsp+6D8h+var_668]; this
0x180004d75  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004d7a  mov     eax, ebx
0x180004d7c  jmp     loc_180004FCA
0x180004d81  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004d86  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004d8b  nop
0x180004d8c  lea     rcx, [rsp+6D8h+var_688]
0x180004d91  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004d96  nop
0x180004d97  lea     rcx, [rsp+6D8h+var_668]; this
0x180004d9c  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004da1  mov     eax, edi
0x180004da3  jmp     loc_180004FCA
0x180004da8  call    cs:__imp_RpcRevertToSelf
0x180004daf  nop     dword ptr [rax+rax+00h]
0x180004db4  mov     ebx, eax
0x180004db6  test    eax, eax
0x180004db8  jz      short loc_180004DEC
0x180004dba  jle     short loc_180004DC5
0x180004dbc  movzx   ebx, ax
0x180004dbf  or      ebx, 80070000h
0x180004dc5  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004dca  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004dcf  nop
0x180004dd0  lea     rcx, [rsp+6D8h+var_688]
0x180004dd5  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004dda  nop
0x180004ddb  lea     rcx, [rsp+6D8h+var_668]; this
0x180004de0  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004de5  mov     eax, ebx
0x180004de7  jmp     loc_180004FCA
0x180004dec  mov     [rsp+6D8h+var_690], r15
0x180004df1  lea     rdx, aSagetaccountin; "SAGetAccountInformation"
0x180004df8  lea     rcx, [rsp+6D8h+var_6A0]; this
0x180004dfd  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x180004e02  nop
0x180004e03  mov     [rsp+6D8h+var_6A4], r15b
0x180004e08  lea     r9, [rsp+6D8h+var_6A4]; bool *
0x180004e0d  lea     r8, [rsp+6D8h+var_690]; struct _bstr_t *
0x180004e12  lea     rdx, [rsp+6D8h+var_248]; unsigned __int16 *
0x180004e1a  call    ?GetUserInfo@CompatibilityAdapter@@QEAAJPEBGAEAV_bstr_t@@AEA_N@Z; CompatibilityAdapter::GetUserInfo(ushort const *,_bstr_t &,bool &)
0x180004e1f  mov     ebx, eax
0x180004e21  mov     [rsp+6D8h+var_6A8], eax
0x180004e25  mov     ecx, eax; this
0x180004e27  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180004e2c  test    al, al
0x180004e2e  jz      short loc_180004E3B
0x180004e30  mov     ebx, 8004130Fh
0x180004e35  mov     [rsp+6D8h+var_6A8], ebx
0x180004e39  jmp     short loc_180004E3F
0x180004e3b  test    ebx, ebx
0x180004e3d  jns     short loc_180004E85
0x180004e3f  cmp     dword ptr [rsp+6D8h+var_6A0], r15d
0x180004e44  jz      short loc_180004E53
0x180004e46  call    cs:__imp_RpcRevertToSelf
0x180004e4d  nop     dword ptr [rax+rax+00h]
0x180004e52  nop
0x180004e53  lea     rcx, [rsp+6D8h+var_690]; this
0x180004e58  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004e5d  nop
0x180004e5e  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004e63  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004e68  nop
0x180004e69  lea     rcx, [rsp+6D8h+var_688]
0x180004e6e  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004e73  nop
0x180004e74  lea     rcx, [rsp+6D8h+var_668]; this
0x180004e79  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004e7e  mov     eax, ebx
0x180004e80  jmp     loc_180004FCA
0x180004e85  cmp     dword ptr [rsp+6D8h+var_6A0], r15d
0x180004e8a  jz      short loc_180004E98
0x180004e8c  call    cs:__imp_RpcRevertToSelf
0x180004e93  nop     dword ptr [rax+rax+00h]
0x180004e98  mov     [rsp+6D8h+var_6A0], r15
0x180004e9d  mov     rax, [rsp+6D8h+var_690]
0x180004ea2  test    rax, rax
0x180004ea5  jz      short loc_180004EAC
0x180004ea7  mov     rdx, [rax]
0x180004eaa  jmp     short loc_180004EAF
0x180004eac  mov     rdx, r15; lpAccountName
0x180004eaf  lea     rcx, [rsp+6D8h+var_6A0]; this
0x180004eb4  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x180004eb9  mov     ebx, eax
0x180004ebb  mov     [rsp+6D8h+var_6A8], eax
0x180004ebf  test    eax, eax
0x180004ec1  jns     short loc_180004F00
0x180004ec3  lea     rcx, [rsp+6D8h+var_6A0]
0x180004ec8  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180004ecd  nop
0x180004ece  lea     rcx, [rsp+6D8h+var_690]; this
0x180004ed3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004ed8  nop
0x180004ed9  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004ede  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004ee3  nop
0x180004ee4  lea     rcx, [rsp+6D8h+var_688]
0x180004ee9  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004eee  nop
0x180004eef  lea     rcx, [rsp+6D8h+var_668]; this
0x180004ef4  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004ef9  mov     eax, ebx
0x180004efb  jmp     loc_180004FCA
0x180004f00  lea     rcx, [rsp+6D8h+var_6A0]; this
  ... truncated ...
```
