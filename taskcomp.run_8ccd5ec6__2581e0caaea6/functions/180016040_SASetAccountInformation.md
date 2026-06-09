# SASetAccountInformation

- ea: `0x180016040`
- end: `0x18001660e`
- name: `SASetAccountInformation`
- size: `1486`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x180005010`
- `0x180005094`
- `0x180005650`
- `0x180005c10`
- `0x180006764`
- `0x180006fb8`
- `0x180007948`
- `0x18000c4c8`
- `0x18000d128`
- `0x1800150c4`
- `0x180016040`
- `0x180025974`
- `0x180026890`
- `0x18002b5a0`
- `0x18002cad4`
- `0x18002cdb0`
- `0x18002cf68`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `msvcrt!wcschr` at `0x180016114`
- `msvcrt!wcschr` at `0x18001612f`
- `msvcrt!wcschr` at `0x180016114`
- `msvcrt!wcschr` at `0x18001612f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016298`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016298`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016279`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016279`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180016333`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180016333`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800163cc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016434`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800163cc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016444`
- `RPCRT4!RpcRevertToSelf` at `0x180016528`
- `RPCRT4!RpcRevertToSelf` at `0x18001659d`
- `RPCRT4!RpcRevertToSelf` at `0x180016528`
- `RPCRT4!RpcRevertToSelf` at `0x18001659d`
- `RPCRT4!RpcImpersonateClient` at `0x180016220`
- `RPCRT4!RpcImpersonateClient` at `0x180016220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001638a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001638a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800164af`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800164af`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001651a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001657a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016588`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001651a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001657a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016588`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016492`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016492`

## string_xrefs

- `0x1800164a8`: `CoInitializeEx failed inside SASetAccountInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall SASetAccountInformation(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int16 a5)
{
  struct CompatibilityAdapter *Adapter; // r12
  bool v10; // r8
  int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // r8d
  int AccountSidAndDomain; // edi
  _BYTE *v16; // r15
  EventManager *v17; // rcx
  int v18; // ebx
  HANDLE CurrentThread; // rax
  int LastError; // ebx
  signed int v21; // eax
  signed int v22; // eax
  int v23; // edi
  CJob *v24; // rax
  CJob *v25; // rdi
  unsigned int v26; // r8d
  unsigned int v27; // edx
  const wchar_t *v28; // rax
  unsigned int v29; // edx
  tsched *v30; // rcx
  int v31; // r8d
  char *v32; // r9
  int *v33; // [rsp+28h] [rbp-520h]
  char v34[32]; // [rsp+0h] [rbp-548h] BYREF
  int v35[2]; // [rsp+20h] [rbp-528h]
  const struct _GUID *v36; // [rsp+28h] [rbp-520h]
  int v37; // [rsp+40h] [rbp-508h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-500h] BYREF
  WINBOOL IsMember; // [rsp+50h] [rbp-4F8h] BYREF
  WINBOOL v40; // [rsp+54h] [rbp-4F4h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-4F0h] BYREF
  _DWORD SidToCheck[4]; // [rsp+60h] [rbp-4E8h] BYREF
  _BYTE v43[528]; // [rsp+70h] [rbp-4D8h] BYREF
  unsigned __int16 v44[16]; // [rsp+280h] [rbp-2C8h] BYREF
  _BYTE v45[80]; // [rsp+2A0h] [rbp-2A8h] BYREF
  WCHAR FileName[264]; // [rsp+2F0h] [rbp-258h] BYREF

  v37 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids, a2);
  }
  Adapter = CompatibilityAdapter::GetAdapter();
  if ( !Adapter )
    return 2147500037LL;
  TaskLock::TaskLock((TaskLock *)v43, a2);
  v11 = RPCFolderAccessCheck(g_TasksFolderInfo, 2u, v10);
  v37 = v11;
  if ( v11 < 0 )
  {
    TaskLock::~TaskLock((TaskLock *)v43);
    return (unsigned int)v11;
  }
  if ( !a2 || !a3 || wcschr(a2, 0x5Cu) || wcschr(a2, 0x2Fu) )
  {
    TaskLock::~TaskLock((TaskLock *)v43);
    return 2147942487LL;
  }
  memset_0(FileName, 0, 0x20Au);
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( g_TasksFolderInfo[v13] );
  do
    ++v12;
  while ( a2[v12] );
  if ( (unsigned __int64)(v13 + v12 + 2) > 0x105 )
  {
    TaskLock::~TaskLock((TaskLock *)v43);
    return 2147750669LL;
  }
  StringCchCopyW(FileName, 0x105u, g_TasksFolderInfo);
  StringCchCatW(FileName, 0x105u, L"\\");
  StringCchCatW(FileName, 0x105u, a2);
  memset(v44, 0, sizeof(v44));
  AccountSidAndDomain = GetAccountSidAndDomain(a3, v45, v14, v44, v35[0]);
  v16 = v45;
  if ( AccountSidAndDomain < 0 )
    v16 = 0;
  v18 = RpcImpersonateClient(0);
  if ( !v18 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
    {
      if ( (GetLastError() & 0x1FFF0000) != 0 )
      {
        LastError = GetLastError();
      }
      else
      {
        v21 = GetLastError();
        LastError = v21;
        if ( v21 > 0 )
          LastError = (unsigned __int16)v21 | 0x80070000;
      }
      goto LABEL_69;
    }
    LastError = FolderAccessCheck(FileName, TokenHandle, 2u);
    v37 = LastError;
    if ( LastError < 0 )
      goto LABEL_70;
    if ( AccountSidAndDomain < 0 )
    {
      LastError = AccountSidAndDomain;
LABEL_69:
      v37 = LastError;
      goto LABEL_70;
    }
    if ( a4 )
    {
LABEL_57:
      LastError = CoInitializeEx(0, 0);
      v37 = LastError;
      if ( LastError >= 0 )
      {
        v24 = (CJob *)operator new(0x108u);
        if ( !v24 || (v25 = CJob::CJob(v24), (hObject = v25) == 0) )
        {
          CoUninitialize();
          LastError = -2147024882;
          goto LABEL_69;
        }
        LastError = CJob::LoadP(v25, FileName, v26, 1, 1);
        v37 = LastError;
        if ( LastError >= 0 )
        {
          RpcRevertToSelf();
          try
          {
            v28 = L"System";
            if ( *a3 )
              v28 = a3;
            LastError = CompatibilityAdapter::RegisterWithRetry(Adapter, 1, v25, a2, v28, a4);
            v37 = LastError;
          }
          catch ( ... )
          {
            tsched::KnownExceptionToHResult(v30, v34, v31, v32, (unsigned __int8)&v37, v33);
          }
          CJob::`scalar deleting destructor'(v25, v29);
          CoUninitialize();
          goto LABEL_71;
        }
        CJob::`scalar deleting destructor'(v25, v27);
        CoUninitialize();
      }
      else
      {
        OutputDebugStringW(L"CoInitializeEx failed inside SASetAccountInformation");
      }
LABEL_70:
      RpcRevertToSelf();
LABEL_71:
      wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
      TaskLock::~TaskLock((TaskLock *)v43);
      return (unsigned int)LastError;
    }
    if ( IsTokenRestricted(TokenHandle) )
    {
      LOWORD(v22) = 5;
    }
    else
    {
      hObject = 0;
      LastError = OpenFileWithRetry(FileName, 0x40000000u, 2u, &hObject);
      v37 = LastError;
      if ( LastError < 0 )
        goto LABEL_56;
      CloseHandle(hObject);
      if ( *a3 )
      {
        v23 = 0;
        if ( (a5 & 0x2000) == 0 )
        {
          LastError = -2147216620;
          goto LABEL_69;
        }
      }
      else
      {
        v23 = 1;
      }
      IsMember = 0;
      SidToCheck[0] = 257;
      SidToCheck[1] = 83886080;
      SidToCheck[2] = 18;
      if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      {
        if ( IsMember || (unsigned int)IsThreadCallerAnAdmin(TokenHandle) )
        {
LABEL_56:
          if ( LastError < 0 )
            goto LABEL_70;
          goto LABEL_57;
        }
        if ( v23 )
        {
          LastError = -2147024891;
          goto LABEL_69;
        }
        v40 = 0;
        if ( CheckTokenMembership(TokenHandle, v16, &v40) )
        {
          if ( v40 )
            goto LABEL_56;
          LastError = -2147024891;
          goto LABEL_55;
        }
      }
      v22 = GetLastError();
      if ( !v22 )
        goto LABEL_56;
      if ( (v22 & 0x1FFF0000) != 0 )
      {
        LastError = v22;
        v37 = v22;
        goto LABEL_56;
      }
      if ( v22 <= 0 )
      {
        LastError = v22;
        goto LABEL_55;
      }
    }
    LastError = (unsigned __int16)v22 | 0x80070000;
LABEL_55:
    v37 = LastError;
    goto LABEL_56;
  }
  EventManager::EvtReport(v17, &IMPERSONATION_FAILURE, L"SASetAccountInformation", v18, *(void **)v35, v36);
  if ( (v18 & 0x1FFF0000) == 0 && v18 > 0 )
    v18 = (unsigned __int16)v18 | 0x80070000;
  v37 = v18;
  TaskLock::~TaskLock((TaskLock *)v43);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180016040  push    rbx
0x180016042  push    rsi
0x180016043  push    rdi
0x180016044  push    r12
0x180016046  push    r13
0x180016048  push    r14
0x18001604a  push    r15
0x18001604c  sub     rsp, 510h
0x180016053  mov     rax, cs:__security_cookie
0x18001605a  xor     rax, rsp
0x18001605d  mov     [rsp+548h+var_48], rax
0x180016065  mov     r13, r9
0x180016068  mov     r14, r8
0x18001606b  mov     rsi, rdx
0x18001606e  xor     edi, edi
0x180016070  mov     [rsp+548h+var_508], edi
0x180016074  lea     rax, WPP_GLOBAL_Control
0x18001607b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016082  cmp     rcx, rax
0x180016085  jz      short loc_1800160A9
0x180016087  test    byte ptr [rcx+1Ch], 2
0x18001608b  jz      short loc_1800160A9
0x18001608d  cmp     byte ptr [rcx+19h], 4
0x180016091  jb      short loc_1800160A9
0x180016093  lea     edx, [rdi+0Ah]
0x180016096  mov     r9, rsi
0x180016099  lea     r8, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids
0x1800160a0  mov     rcx, [rcx+10h]
0x1800160a4  call    WPP_SF_S
0x1800160a9  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x1800160ae  mov     r12, rax
0x1800160b1  test    rax, rax
0x1800160b4  jnz     short loc_1800160C0
0x1800160b6  mov     eax, 80004005h
0x1800160bb  jmp     loc_1800165EA
0x1800160c0  mov     rdx, rsi; unsigned __int16 *
0x1800160c3  lea     rcx, [rsp+548h+var_4D8]; this
0x1800160c8  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x1800160cd  nop
0x1800160ce  mov     edx, 2; DesiredAccess
0x1800160d3  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpFileName
0x1800160da  call    ?RPCFolderAccessCheck@@YAJPEBGK_N@Z; RPCFolderAccessCheck(ushort const *,ulong,bool)
0x1800160df  mov     ebx, eax
0x1800160e1  mov     [rsp+548h+var_508], eax
0x1800160e5  test    eax, eax
0x1800160e7  jns     short loc_1800160FA
0x1800160e9  lea     rcx, [rsp+548h+var_4D8]; this
0x1800160ee  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800160f3  mov     eax, ebx
0x1800160f5  jmp     loc_1800165EA
0x1800160fa  test    rsi, rsi
0x1800160fd  jz      loc_1800165D3
0x180016103  test    r14, r14
0x180016106  jz      loc_1800165D3
0x18001610c  mov     edx, 5Ch ; '\'; Ch
0x180016111  mov     rcx, rsi; Str
0x180016114  call    cs:__imp_wcschr
0x18001611b  nop     dword ptr [rax+rax+00h]
0x180016120  test    rax, rax
0x180016123  jnz     loc_1800165C2
0x180016129  lea     edx, [rax+2Fh]; Ch
0x18001612c  mov     rcx, rsi; Str
0x18001612f  call    cs:__imp_wcschr
0x180016136  nop     dword ptr [rax+rax+00h]
0x18001613b  test    rax, rax
0x18001613e  jnz     loc_1800165C2
0x180016144  xor     edx, edx; Val
0x180016146  mov     r8d, 20Ah; Size
0x18001614c  lea     rcx, [rsp+548h+FileName]; void *
0x180016154  call    memset_0
0x180016159  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180016160  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016164  mov     rcx, rax
0x180016167  inc     rcx
0x18001616a  cmp     [r8+rcx*2], di
0x18001616f  jnz     short loc_180016167
0x180016171  inc     rax
0x180016174  cmp     [rsi+rax*2], di
0x180016178  jnz     short loc_180016171
0x18001617a  add     rax, 2
0x18001617e  add     rax, rcx
0x180016181  mov     ebx, 105h
0x180016186  cmp     rax, rbx
0x180016189  jbe     short loc_18001619F
0x18001618b  lea     rcx, [rsp+548h+var_4D8]; this
0x180016190  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180016195  mov     eax, 8004130Dh
0x18001619a  jmp     loc_1800165EA
0x18001619f  mov     rdx, rbx; unsigned __int64
0x1800161a2  lea     rcx, [rsp+548h+FileName]; unsigned __int16 *
0x1800161aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800161af  lea     r8, asc_1800516CC; "\\"
0x1800161b6  mov     rdx, rbx; unsigned __int64
0x1800161b9  lea     rcx, [rsp+548h+FileName]; unsigned __int16 *
0x1800161c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800161c6  mov     r8, rsi; unsigned __int16 *
0x1800161c9  mov     rdx, rbx; unsigned __int64
0x1800161cc  lea     rcx, [rsp+548h+FileName]; unsigned __int16 *
0x1800161d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800161d9  mov     [rsp+548h+var_2C8], di
0x1800161e1  xorps   xmm0, xmm0
0x1800161e4  movups  xmmword ptr [rsp+548h+var_2C6], xmm0
0x1800161ec  movups  xmmword ptr [rsp+548h+var_2C6+0Eh], xmm0
0x1800161f4  lea     r9, [rsp+548h+var_2C8]; unsigned __int16 *
0x1800161fc  lea     rdx, [rsp+548h+var_2A8]; void *
0x180016204  mov     rcx, r14; unsigned __int16 *
0x180016207  call    ?GetAccountSidAndDomain@@YAJPEBGPEAXKPEAGK@Z; GetAccountSidAndDomain(ushort const *,void *,ulong,ushort *,ulong)
0x18001620c  mov     edi, eax
0x18001620e  lea     r15, [rsp+548h+var_2A8]
0x180016216  xor     eax, eax
0x180016218  test    edi, edi
0x18001621a  cmovs   r15, rax
0x18001621e  xor     ecx, ecx; BindingHandle
0x180016220  call    cs:__imp_RpcImpersonateClient
0x180016227  nop     dword ptr [rax+rax+00h]
0x18001622c  mov     ebx, eax
0x18001622e  xor     eax, eax
0x180016230  test    ebx, ebx
0x180016232  jz      short loc_180016274
0x180016234  mov     r9d, ebx; unsigned int
0x180016237  lea     r8, aSasetaccountin; "SASetAccountInformation"
0x18001623e  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180016245  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18001624a  test    ebx, 1FFF0000h
0x180016250  jnz     short loc_18001625F
0x180016252  test    ebx, ebx
0x180016254  jle     short loc_18001625F
0x180016256  movzx   ebx, bx
0x180016259  or      ebx, 80070000h
0x18001625f  mov     [rsp+548h+var_508], ebx
0x180016263  lea     rcx, [rsp+548h+var_4D8]; this
0x180016268  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x18001626d  mov     eax, ebx
0x18001626f  jmp     loc_1800165EA
0x180016274  mov     [rsp+548h+TokenHandle], rax
0x180016279  call    cs:__imp_GetCurrentThread
0x180016280  nop     dword ptr [rax+rax+00h]
0x180016285  lea     r9, [rsp+548h+TokenHandle]; TokenHandle
0x18001628a  mov     edx, 2000Eh; DesiredAccess
0x18001628f  mov     r8d, 1; OpenAsSelf
0x180016295  mov     rcx, rax; ThreadHandle
0x180016298  call    cs:__imp_OpenThreadToken
0x18001629f  nop     dword ptr [rax+rax+00h]
0x1800162a4  test    eax, eax
0x1800162a6  jnz     short loc_1800162F2
0x1800162a8  call    cs:__imp_GetLastError
0x1800162af  nop     dword ptr [rax+rax+00h]
0x1800162b4  test    eax, 1FFF0000h
0x1800162b9  jz      short loc_1800162CE
0x1800162bb  call    cs:__imp_GetLastError
0x1800162c2  nop     dword ptr [rax+rax+00h]
0x1800162c7  mov     ebx, eax
0x1800162c9  jmp     loc_180016599
0x1800162ce  call    cs:__imp_GetLastError
0x1800162d5  nop     dword ptr [rax+rax+00h]
0x1800162da  mov     ebx, eax
0x1800162dc  test    eax, eax
0x1800162de  jle     loc_180016599
0x1800162e4  movzx   ebx, ax
0x1800162e7  or      ebx, 80070000h
0x1800162ed  jmp     loc_180016599
0x1800162f2  mov     r8d, 2; DesiredAccess
0x1800162f8  mov     rdx, [rsp+548h+TokenHandle]; ClientToken
0x1800162fd  lea     rcx, [rsp+548h+FileName]; lpFileName
0x180016305  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x18001630a  mov     ebx, eax
0x18001630c  mov     [rsp+548h+var_508], eax
0x180016310  test    eax, eax
0x180016312  js      loc_18001659D
0x180016318  xor     ebx, ebx
0x18001631a  test    edi, edi
0x18001631c  jns     short loc_180016325
0x18001631e  mov     ebx, edi
0x180016320  jmp     loc_180016599
0x180016325  test    r13, r13
0x180016328  jnz     loc_18001648B
0x18001632e  mov     rcx, [rsp+548h+TokenHandle]; TokenHandle
0x180016333  call    cs:__imp_IsTokenRestricted
0x18001633a  nop     dword ptr [rax+rax+00h]
0x18001633f  test    eax, eax
0x180016341  jz      short loc_180016355
0x180016343  lea     eax, [r13+5]
0x180016347  movzx   ebx, ax
0x18001634a  or      ebx, 80070000h
0x180016350  jmp     loc_18001647A
0x180016355  mov     [rsp+548h+hObject], rbx
0x18001635a  lea     r9, [rsp+548h+hObject]; void **
0x18001635f  mov     edx, 40000000h; dwDesiredAccess
0x180016364  mov     r8d, 2; dwShareMode
0x18001636a  lea     rcx, [rsp+548h+FileName]; lpFileName
0x180016372  call    ?OpenFileWithRetry@@YAJPEBGKKPEAPEAX@Z; OpenFileWithRetry(ushort const *,ulong,ulong,void * *)
0x180016377  mov     ebx, eax
0x180016379  mov     [rsp+548h+var_508], eax
0x18001637d  test    eax, eax
0x18001637f  js      loc_18001647E
0x180016385  mov     rcx, [rsp+548h+hObject]; hObject
0x18001638a  call    cs:__imp_CloseHandle
0x180016391  nop     dword ptr [rax+rax+00h]
0x180016396  xor     eax, eax
0x180016398  cmp     [r14], ax
0x18001639c  jnz     short loc_180016408
0x18001639e  lea     edi, [rax+1]
0x1800163a1  mov     [rsp+548h+IsMember], eax
0x1800163a5  mov     [rsp+548h+SidToCheck], 101h
0x1800163ad  mov     [rsp+548h+var_4E4], 5000000h
0x1800163b5  mov     [rsp+548h+var_4E0], 12h
0x1800163bd  lea     r8, [rsp+548h+IsMember]; IsMember
0x1800163c2  lea     rdx, [rsp+548h+SidToCheck]; SidToCheck
0x1800163c7  mov     rcx, [rsp+548h+TokenHandle]; TokenHandle
0x1800163cc  call    cs:__imp_CheckTokenMembership
0x1800163d3  nop     dword ptr [rax+rax+00h]
0x1800163d8  xor     ecx, ecx
0x1800163da  test    eax, eax
0x1800163dc  jz      short loc_180016444
0x1800163de  cmp     [rsp+548h+IsMember], ecx
0x1800163e2  jnz     loc_18001647E
0x1800163e8  mov     rcx, [rsp+548h+TokenHandle]; void *
0x1800163ed  call    ?IsThreadCallerAnAdmin@@YAHPEAX@Z; IsThreadCallerAnAdmin(void *)
0x1800163f2  test    eax, eax
0x1800163f4  jnz     loc_18001647E
0x1800163fa  test    edi, edi
0x1800163fc  jz      short loc_180016421
0x1800163fe  mov     ebx, 80070005h
0x180016403  jmp     loc_180016599
0x180016408  mov     edi, eax
0x18001640a  test    [rsp+548h+arg_20], 2000h
0x180016415  jnz     short loc_1800163A1
0x180016417  mov     ebx, 80041314h
0x18001641c  jmp     loc_180016599
0x180016421  xor     edi, edi
0x180016423  mov     [rsp+548h+var_4F4], edi
0x180016427  lea     r8, [rsp+548h+var_4F4]; IsMember
0x18001642c  mov     rdx, r15; SidToCheck
0x18001642f  mov     rcx, [rsp+548h+TokenHandle]; TokenHandle
0x180016434  call    cs:__imp_CheckTokenMembership
0x18001643b  nop     dword ptr [rax+rax+00h]
0x180016440  test    eax, eax
0x180016442  jnz     short loc_18001646F
0x180016444  call    cs:__imp_GetLastError
0x18001644b  nop     dword ptr [rax+rax+00h]
0x180016450  test    eax, eax
0x180016452  jz      short loc_18001647E
0x180016454  test    eax, 1FFF0000h
0x180016459  jz      short loc_180016463
0x18001645b  mov     ebx, eax
0x18001645d  mov     [rsp+548h+var_508], eax
0x180016461  jmp     short loc_18001647E
0x180016463  test    eax, eax
0x180016465  jg      loc_180016347
0x18001646b  mov     ebx, eax
0x18001646d  jmp     short loc_18001647A
0x18001646f  cmp     [rsp+548h+var_4F4], edi
0x180016473  jnz     short loc_18001647E
0x180016475  mov     ebx, 80070005h
0x18001647a  mov     [rsp+548h+var_508], ebx
0x18001647e  xor     r15d, r15d
0x180016481  test    ebx, ebx
0x180016483  js      loc_18001659D
0x180016489  jmp     short loc_18001648E
0x18001648b  xor     r15d, r15d
0x18001648e  xor     edx, edx; dwCoInit
0x180016490  xor     ecx, ecx; pvReserved
0x180016492  call    cs:__imp_CoInitializeEx
0x180016499  nop     dword ptr [rax+rax+00h]
0x18001649e  mov     ebx, eax
0x1800164a0  mov     [rsp+548h+var_508], eax
0x1800164a4  test    eax, eax
0x1800164a6  jns     short loc_1800164C0
0x1800164a8  lea     rcx, aCoinitializeex_1; "CoInitializeEx failed inside SASetAccou"...
0x1800164af  call    cs:__imp_OutputDebugStringW
0x1800164b6  nop     dword ptr [rax+rax+00h]
0x1800164bb  jmp     loc_18001659D
0x1800164c0  mov     ecx, 108h; Size
0x1800164c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800164ca  test    rax, rax
0x1800164cd  jz      loc_180016588
0x1800164d3  mov     rcx, rax; this
0x1800164d6  call    ??0CJob@@QEAA@XZ; CJob::CJob(void)
0x1800164db  mov     rdi, rax
0x1800164de  mov     [rsp+548h+hObject], rax
0x1800164e3  test    rax, rax
0x1800164e6  jz      loc_180016588
0x1800164ec  mov     eax, 1
0x1800164f1  mov     [rsp+548h+var_528], eax; int
0x1800164f5  mov     r9d, eax; int
0x1800164f8  lea     rdx, [rsp+548h+FileName]; lpFileName
0x180016500  mov     rcx, rdi; this
0x180016503  call    ?LoadP@CJob@@QEAAJPEBGKHH@Z; CJob::LoadP(ushort const *,ulong,int,int)
0x180016508  mov     ebx, eax
0x18001650a  mov     [rsp+548h+var_508], eax
0x18001650e  test    eax, eax
0x180016510  jns     short loc_180016528
0x180016512  mov     rcx, rdi; this
0x180016515  call    ??_GCJob@@QEAAPEAXI@Z; CJob::`scalar deleting destructor'(uint)
0x18001651a  call    cs:__imp_CoUninitialize
0x180016521  nop     dword ptr [rax+rax+00h]
0x180016526  jmp     short loc_18001659D
0x180016528  call    cs:__imp_RpcRevertToSelf
0x18001652f  nop     dword ptr [rax+rax+00h]
0x180016534  nop
  ... truncated ...
```
