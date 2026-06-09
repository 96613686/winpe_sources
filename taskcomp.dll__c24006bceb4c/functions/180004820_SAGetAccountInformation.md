# SAGetAccountInformation

- ea: `0x180004820`
- end: `0x180004d7e`
- name: `SAGetAccountInformation`
- size: `1374`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800031a0`
- `0x180003ec0`
- `0x180003ef0`
- `0x180003f64`
- `0x180004820`
- `0x180004d84`
- `0x180004da4`
- `0x180004e1c`
- `0x180004e50`
- `0x180005034`
- `0x1800050fc`
- `0x18000518c`
- `0x1800053b8`
- `0x1800058f0`
- `0x18000635c`
- `0x180009afc`
- `0x18000aabc`
- `0x18000c8f4`
- `0x180010e44`
- `0x1800113cc`
- `0x18002b1b4`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800048f0`
- `msvcrt!wcschr` at `0x180004905`
- `msvcrt!wcschr` at `0x1800048f0`
- `msvcrt!wcschr` at `0x180004905`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004ac6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004ac6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004aad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ad0`
- `RPCRT4!RpcRevertToSelf` at `0x180004ae9`
- `RPCRT4!RpcRevertToSelf` at `0x180004b4e`
- `RPCRT4!RpcRevertToSelf` at `0x180004be6`
- `RPCRT4!RpcRevertToSelf` at `0x180004c26`
- `RPCRT4!RpcRevertToSelf` at `0x180004ae9`
- `RPCRT4!RpcRevertToSelf` at `0x180004b4e`
- `RPCRT4!RpcRevertToSelf` at `0x180004be6`
- `RPCRT4!RpcRevertToSelf` at `0x180004c26`
- `RPCRT4!RpcImpersonateClient` at `0x180004a5d`
- `RPCRT4!RpcImpersonateClient` at `0x180004a5d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a32`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a32`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004a4a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004a1b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004a1b`

## string_xrefs

- `0x180004a2b`: `CoInitializeEx failed inside SAGetAccountInformation`

## pseudocode

```c
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
0x180004820  push    rbx
0x180004822  push    rsi
0x180004823  push    rdi
0x180004824  push    r14
0x180004826  push    r15
0x180004828  sub     rsp, 6B0h
0x18000482f  mov     rax, cs:__security_cookie
0x180004836  xor     rax, rsp
0x180004839  mov     [rsp+6D8h+var_38], rax
0x180004841  mov     rsi, r9
0x180004844  mov     r14d, r8d
0x180004847  mov     rbx, rdx
0x18000484a  xor     r15d, r15d
0x18000484d  mov     [rsp+6D8h+var_6A8], r15d
0x180004852  lea     rax, WPP_GLOBAL_Control
0x180004859  mov     rcx, cs:WPP_GLOBAL_Control
0x180004860  cmp     rcx, rax
0x180004863  jz      short loc_180004888
0x180004865  test    byte ptr [rcx+1Ch], 2
0x180004869  jz      short loc_180004888
0x18000486b  cmp     byte ptr [rcx+19h], 4
0x18000486f  jb      short loc_180004888
0x180004871  lea     edx, [r15+0Bh]
0x180004875  mov     r9, rbx
0x180004878  lea     r8, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids
0x18000487f  mov     rcx, [rcx+10h]
0x180004883  call    WPP_SF_S
0x180004888  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x18000488d  test    rax, rax
0x180004890  jnz     short loc_18000489C
0x180004892  mov     eax, 80004005h
0x180004897  jmp     loc_180004D5E
0x18000489c  mov     rdx, rbx; unsigned __int16 *
0x18000489f  lea     rcx, [rsp+6D8h+var_668]; this
0x1800048a4  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x1800048a9  nop
0x1800048aa  mov     edx, 1; DesiredAccess
0x1800048af  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpFileName
0x1800048b6  call    ?RPCFolderAccessCheck@@YAJPEBGK_N@Z; RPCFolderAccessCheck(ushort const *,ulong,bool)
0x1800048bb  mov     edi, eax
0x1800048bd  mov     [rsp+6D8h+var_6A8], eax
0x1800048c1  test    eax, eax
0x1800048c3  jns     short loc_1800048D6
0x1800048c5  lea     rcx, [rsp+6D8h+var_668]; this
0x1800048ca  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800048cf  mov     eax, edi
0x1800048d1  jmp     loc_180004D5E
0x1800048d6  test    rbx, rbx
0x1800048d9  jz      loc_180004D47
0x1800048df  test    rsi, rsi
0x1800048e2  jz      loc_180004D47
0x1800048e8  mov     edx, 5Ch ; '\'; Ch
0x1800048ed  mov     rcx, rbx; Str
0x1800048f0  call    cs:__imp_wcschr
0x1800048f6  test    rax, rax
0x1800048f9  jnz     loc_180004D36
0x1800048ff  lea     edx, [rax+2Fh]; Ch
0x180004902  mov     rcx, rbx; Str
0x180004905  call    cs:__imp_wcschr
0x18000490b  test    rax, rax
0x18000490e  jnz     loc_180004D36
0x180004914  xor     edx, edx; Val
0x180004916  mov     r8d, 20Ah; Size
0x18000491c  lea     rcx, [rsp+6D8h+FileName]; void *
0x180004924  call    memset_0
0x180004929  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180004930  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004934  mov     rcx, rax
0x180004937  inc     rcx
0x18000493a  cmp     [r8+rcx*2], r15w
0x18000493f  jnz     short loc_180004937
0x180004941  inc     rax
0x180004944  cmp     [rbx+rax*2], r15w
0x180004949  jnz     short loc_180004941
0x18000494b  add     rax, 2
0x18000494f  add     rax, rcx
0x180004952  mov     edi, 105h
0x180004957  cmp     rax, rdi
0x18000495a  jbe     short loc_180004970
0x18000495c  lea     rcx, [rsp+6D8h+var_668]; this
0x180004961  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004966  mov     eax, 8004130Dh
0x18000496b  jmp     loc_180004D5E
0x180004970  mov     rdx, rdi; unsigned __int64
0x180004973  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x18000497b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004980  lea     r8, asc_18004F6BC; "\\"
0x180004987  mov     rdx, rdi; unsigned __int64
0x18000498a  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x180004992  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004997  mov     r8, rbx; unsigned __int16 *
0x18000499a  mov     rdx, rdi; unsigned __int64
0x18000499d  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x1800049a5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800049aa  mov     edx, 1; DesiredAccess
0x1800049af  lea     rcx, [rsp+6D8h+FileName]; lpFileName
0x1800049b7  call    ?RPCFolderAccessCheck@@YAJPEBGK_N@Z; RPCFolderAccessCheck(ushort const *,ulong,bool)
0x1800049bc  mov     edi, eax
0x1800049be  mov     [rsp+6D8h+var_6A8], eax
0x1800049c2  test    eax, eax
0x1800049c4  jns     short loc_1800049D7
0x1800049c6  lea     rcx, [rsp+6D8h+var_668]; this
0x1800049cb  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800049d0  mov     eax, edi
0x1800049d2  jmp     loc_180004D5E
0x1800049d7  xor     edx, edx; Val
0x1800049d9  mov     r8d, 20Ah; Size
0x1800049df  lea     rcx, [rsp+6D8h+var_248]; void *
0x1800049e7  call    memset_0
0x1800049ec  lea     rdx, [rsp+6D8h+var_248]; unsigned __int16 *
0x1800049f4  mov     rcx, rbx; unsigned __int16 *
0x1800049f7  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x1800049fc  mov     ebx, eax
0x1800049fe  mov     [rsp+6D8h+var_6A8], eax
0x180004a02  test    eax, eax
0x180004a04  jns     short loc_180004A17
0x180004a06  lea     rcx, [rsp+6D8h+var_668]; this
0x180004a0b  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004a10  mov     eax, ebx
0x180004a12  jmp     loc_180004D5E
0x180004a17  xor     edx, edx; dwCoInit
0x180004a19  xor     ecx, ecx; pvReserved
0x180004a1b  call    cs:__imp_CoInitializeEx
0x180004a21  mov     ebx, eax
0x180004a23  mov     [rsp+6D8h+var_6A8], eax
0x180004a27  test    eax, eax
0x180004a29  jns     short loc_180004A4A
0x180004a2b  lea     rcx, OutputString; "CoInitializeEx failed inside SAGetAccou"...
0x180004a32  call    cs:__imp_OutputDebugStringW
0x180004a38  nop
0x180004a39  lea     rcx, [rsp+6D8h+var_668]; this
0x180004a3e  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004a43  mov     eax, ebx
0x180004a45  jmp     loc_180004D5E
0x180004a4a  mov     rax, cs:__imp_CoUninitialize
0x180004a51  mov     [rsp+6D8h+var_688], r15b
0x180004a56  mov     [rsp+6D8h+var_680], rax
0x180004a5b  xor     ecx, ecx; BindingHandle
0x180004a5d  call    cs:__imp_RpcImpersonateClient
0x180004a63  mov     ebx, eax
0x180004a65  test    eax, eax
0x180004a67  jz      short loc_180004AA8
0x180004a69  mov     r9d, eax; unsigned int
0x180004a6c  lea     r8, aSagetaccountin; "SAGetAccountInformation"
0x180004a73  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180004a7a  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180004a7f  test    ebx, ebx
0x180004a81  jle     short loc_180004A8C
0x180004a83  movzx   ebx, bx
0x180004a86  or      ebx, 80070000h
0x180004a8c  lea     rcx, [rsp+6D8h+var_688]
0x180004a91  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004a96  nop
0x180004a97  lea     rcx, [rsp+6D8h+var_668]; this
0x180004a9c  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004aa1  mov     eax, ebx
0x180004aa3  jmp     loc_180004D5E
0x180004aa8  mov     [rsp+6D8h+TokenHandle], r15
0x180004aad  call    cs:__imp_GetCurrentThread
0x180004ab3  lea     r9, [rsp+6D8h+TokenHandle]; TokenHandle
0x180004ab8  mov     edx, 2000Eh; DesiredAccess
0x180004abd  mov     r8d, 1; OpenAsSelf
0x180004ac3  mov     rcx, rax; ThreadHandle
0x180004ac6  call    cs:__imp_OpenThreadToken
0x180004acc  test    eax, eax
0x180004ace  jnz     short loc_180004B4E
0x180004ad0  call    cs:__imp_GetLastError
0x180004ad6  mov     edi, eax
0x180004ad8  test    eax, eax
0x180004ada  jle     short loc_180004AE5
0x180004adc  movzx   edi, ax
0x180004adf  or      edi, 80070000h
0x180004ae5  mov     [rsp+6D8h+var_6A8], edi
0x180004ae9  call    cs:__imp_RpcRevertToSelf
0x180004aef  mov     ebx, eax
0x180004af1  test    eax, eax
0x180004af3  jz      short loc_180004B27
0x180004af5  jle     short loc_180004B00
0x180004af7  movzx   ebx, ax
0x180004afa  or      ebx, 80070000h
0x180004b00  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004b05  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004b0a  nop
0x180004b0b  lea     rcx, [rsp+6D8h+var_688]
0x180004b10  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004b15  nop
0x180004b16  lea     rcx, [rsp+6D8h+var_668]; this
0x180004b1b  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004b20  mov     eax, ebx
0x180004b22  jmp     loc_180004D5E
0x180004b27  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004b2c  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004b31  nop
0x180004b32  lea     rcx, [rsp+6D8h+var_688]
0x180004b37  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004b3c  nop
0x180004b3d  lea     rcx, [rsp+6D8h+var_668]; this
0x180004b42  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004b47  mov     eax, edi
0x180004b49  jmp     loc_180004D5E
0x180004b4e  call    cs:__imp_RpcRevertToSelf
0x180004b54  mov     ebx, eax
0x180004b56  test    eax, eax
0x180004b58  jz      short loc_180004B8C
0x180004b5a  jle     short loc_180004B65
0x180004b5c  movzx   ebx, ax
0x180004b5f  or      ebx, 80070000h
0x180004b65  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004b6a  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004b6f  nop
0x180004b70  lea     rcx, [rsp+6D8h+var_688]
0x180004b75  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004b7a  nop
0x180004b7b  lea     rcx, [rsp+6D8h+var_668]; this
0x180004b80  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004b85  mov     eax, ebx
0x180004b87  jmp     loc_180004D5E
0x180004b8c  mov     [rsp+6D8h+var_690], r15
0x180004b91  lea     rdx, aSagetaccountin; "SAGetAccountInformation"
0x180004b98  lea     rcx, [rsp+6D8h+var_6A0]; this
0x180004b9d  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x180004ba2  nop
0x180004ba3  mov     [rsp+6D8h+var_6A4], r15b
0x180004ba8  lea     r9, [rsp+6D8h+var_6A4]; bool *
0x180004bad  lea     r8, [rsp+6D8h+var_690]; struct _bstr_t *
0x180004bb2  lea     rdx, [rsp+6D8h+var_248]; unsigned __int16 *
0x180004bba  call    ?GetUserInfo@CompatibilityAdapter@@QEAAJPEBGAEAV_bstr_t@@AEA_N@Z; CompatibilityAdapter::GetUserInfo(ushort const *,_bstr_t &,bool &)
0x180004bbf  mov     ebx, eax
0x180004bc1  mov     [rsp+6D8h+var_6A8], eax
0x180004bc5  mov     ecx, eax; this
0x180004bc7  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180004bcc  test    al, al
0x180004bce  jz      short loc_180004BDB
0x180004bd0  mov     ebx, 8004130Fh
0x180004bd5  mov     [rsp+6D8h+var_6A8], ebx
0x180004bd9  jmp     short loc_180004BDF
0x180004bdb  test    ebx, ebx
0x180004bdd  jns     short loc_180004C1F
0x180004bdf  cmp     dword ptr [rsp+6D8h+var_6A0], r15d
0x180004be4  jz      short loc_180004BED
0x180004be6  call    cs:__imp_RpcRevertToSelf
0x180004bec  nop
0x180004bed  lea     rcx, [rsp+6D8h+var_690]; this
0x180004bf2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004bf7  nop
0x180004bf8  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004bfd  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004c02  nop
0x180004c03  lea     rcx, [rsp+6D8h+var_688]
0x180004c08  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004c0d  nop
0x180004c0e  lea     rcx, [rsp+6D8h+var_668]; this
0x180004c13  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004c18  mov     eax, ebx
0x180004c1a  jmp     loc_180004D5E
0x180004c1f  cmp     dword ptr [rsp+6D8h+var_6A0], r15d
0x180004c24  jz      short loc_180004C2C
0x180004c26  call    cs:__imp_RpcRevertToSelf
0x180004c2c  mov     [rsp+6D8h+var_6A0], r15
0x180004c31  mov     rax, [rsp+6D8h+var_690]
0x180004c36  test    rax, rax
0x180004c39  jz      short loc_180004C40
0x180004c3b  mov     rdx, [rax]
0x180004c3e  jmp     short loc_180004C43
0x180004c40  mov     rdx, r15; lpAccountName
0x180004c43  lea     rcx, [rsp+6D8h+var_6A0]; this
0x180004c48  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x180004c4d  mov     ebx, eax
0x180004c4f  mov     [rsp+6D8h+var_6A8], eax
0x180004c53  test    eax, eax
0x180004c55  jns     short loc_180004C94
0x180004c57  lea     rcx, [rsp+6D8h+var_6A0]
0x180004c5c  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180004c61  nop
0x180004c62  lea     rcx, [rsp+6D8h+var_690]; this
0x180004c67  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004c6c  nop
0x180004c6d  lea     rcx, [rsp+6D8h+TokenHandle]; this
0x180004c72  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180004c77  nop
0x180004c78  lea     rcx, [rsp+6D8h+var_688]
0x180004c7d  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004c82  nop
0x180004c83  lea     rcx, [rsp+6D8h+var_668]; this
0x180004c88  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180004c8d  mov     eax, ebx
0x180004c8f  jmp     loc_180004D5E
0x180004c94  lea     rcx, [rsp+6D8h+var_6A0]; this
0x180004c99  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x180004c9e  test    al, al
0x180004ca0  jz      short loc_180004CA8
0x180004ca2  mov     [rsi], r15w
0x180004ca6  jmp     short loc_180004CFD
0x180004ca8  lea     rdx, [rsp+6D8h+var_678]
0x180004cad  lea     rcx, [rsp+6D8h+var_6A0]
0x180004cb2  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180004cb7  lea     rcx, [rsp+6D8h+var_678]; this
0x180004cbc  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180004cc1  inc     eax
0x180004cc3  cmp     r14d, eax
  ... truncated ...
```
