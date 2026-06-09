# SASetAccountInformation

- ea: `0x180015280`
- end: `0x1800157d2`
- name: `SASetAccountInformation`
- size: `1362`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, __int16)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x180004da4`
- `0x180004e1c`
- `0x1800053b8`
- `0x1800058f0`
- `0x18000635c`
- `0x180006b70`
- `0x180007488`
- `0x18000bccc`
- `0x18000c8f4`
- `0x180014450`
- `0x180015280`
- `0x1800242b4`
- `0x180025118`
- `0x180029b68`
- `0x18002af30`
- `0x18002b1b4`
- `0x18002b330`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!wcschr` at `0x180015354`
- `msvcrt!wcschr` at `0x180015369`
- `msvcrt!wcschr` at `0x180015354`
- `msvcrt!wcschr` at `0x180015369`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800154c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800154c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800154a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800154a7`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180015543`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180015543`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800155d0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001562e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800155d0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001562e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015638`
- `RPCRT4!RpcRevertToSelf` at `0x180015704`
- `RPCRT4!RpcRevertToSelf` at `0x180015767`
- `RPCRT4!RpcRevertToSelf` at `0x180015704`
- `RPCRT4!RpcRevertToSelf` at `0x180015767`
- `RPCRT4!RpcImpersonateClient` at `0x180015454`
- `RPCRT4!RpcImpersonateClient` at `0x180015454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015594`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015594`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015697`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015697`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800156fc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015750`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015758`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800156fc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015750`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015758`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180015680`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180015680`

## string_xrefs

- `0x180015690`: `CoInitializeEx failed inside SASetAccountInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SASetAccountInformation(
        __int64 a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
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
  DWORD v26; // r8d
  unsigned int v27; // edx
  unsigned __int16 *v28; // rax
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
              v28 = (unsigned __int16 *)a3;
            LastError = CompatibilityAdapter::RegisterWithRetry((__int64)Adapter, 1, (__int64)v25, a2, v28, a4);
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
0x180015280  push    rbx
0x180015282  push    rsi
0x180015283  push    rdi
0x180015284  push    r12
0x180015286  push    r13
0x180015288  push    r14
0x18001528a  push    r15
0x18001528c  sub     rsp, 510h
0x180015293  mov     rax, cs:__security_cookie
0x18001529a  xor     rax, rsp
0x18001529d  mov     [rsp+548h+var_48], rax
0x1800152a5  mov     r13, r9
0x1800152a8  mov     r14, r8
0x1800152ab  mov     rsi, rdx
0x1800152ae  xor     edi, edi
0x1800152b0  mov     [rsp+548h+var_508], edi
0x1800152b4  lea     rax, WPP_GLOBAL_Control
0x1800152bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152c2  cmp     rcx, rax
0x1800152c5  jz      short loc_1800152E9
0x1800152c7  test    byte ptr [rcx+1Ch], 2
0x1800152cb  jz      short loc_1800152E9
0x1800152cd  cmp     byte ptr [rcx+19h], 4
0x1800152d1  jb      short loc_1800152E9
0x1800152d3  lea     edx, [rdi+0Ah]
0x1800152d6  mov     r9, rsi
0x1800152d9  lea     r8, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids
0x1800152e0  mov     rcx, [rcx+10h]
0x1800152e4  call    WPP_SF_S
0x1800152e9  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x1800152ee  mov     r12, rax
0x1800152f1  test    rax, rax
0x1800152f4  jnz     short loc_180015300
0x1800152f6  mov     eax, 80004005h
0x1800152fb  jmp     loc_1800157AE
0x180015300  mov     rdx, rsi; unsigned __int16 *
0x180015303  lea     rcx, [rsp+548h+var_4D8]; this
0x180015308  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x18001530d  nop
0x18001530e  mov     edx, 2; DesiredAccess
0x180015313  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpFileName
0x18001531a  call    ?RPCFolderAccessCheck@@YAJPEBGK_N@Z; RPCFolderAccessCheck(ushort const *,ulong,bool)
0x18001531f  mov     ebx, eax
0x180015321  mov     [rsp+548h+var_508], eax
0x180015325  test    eax, eax
0x180015327  jns     short loc_18001533A
0x180015329  lea     rcx, [rsp+548h+var_4D8]; this
0x18001532e  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180015333  mov     eax, ebx
0x180015335  jmp     loc_1800157AE
0x18001533a  test    rsi, rsi
0x18001533d  jz      loc_180015797
0x180015343  test    r14, r14
0x180015346  jz      loc_180015797
0x18001534c  mov     edx, 5Ch ; '\'; Ch
0x180015351  mov     rcx, rsi; Str
0x180015354  call    cs:__imp_wcschr
0x18001535a  test    rax, rax
0x18001535d  jnz     loc_180015786
0x180015363  lea     edx, [rax+2Fh]; Ch
0x180015366  mov     rcx, rsi; Str
0x180015369  call    cs:__imp_wcschr
0x18001536f  test    rax, rax
0x180015372  jnz     loc_180015786
0x180015378  xor     edx, edx; Val
0x18001537a  mov     r8d, 20Ah; Size
0x180015380  lea     rcx, [rsp+548h+FileName]; void *
0x180015388  call    memset_0
0x18001538d  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180015394  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015398  mov     rcx, rax
0x18001539b  inc     rcx
0x18001539e  cmp     [r8+rcx*2], di
0x1800153a3  jnz     short loc_18001539B
0x1800153a5  inc     rax
0x1800153a8  cmp     [rsi+rax*2], di
0x1800153ac  jnz     short loc_1800153A5
0x1800153ae  add     rax, 2
0x1800153b2  add     rax, rcx
0x1800153b5  mov     ebx, 105h
0x1800153ba  cmp     rax, rbx
0x1800153bd  jbe     short loc_1800153D3
0x1800153bf  lea     rcx, [rsp+548h+var_4D8]; this
0x1800153c4  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800153c9  mov     eax, 8004130Dh
0x1800153ce  jmp     loc_1800157AE
0x1800153d3  mov     rdx, rbx; unsigned __int64
0x1800153d6  lea     rcx, [rsp+548h+FileName]; unsigned __int16 *
0x1800153de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800153e3  lea     r8, asc_18004F6BC; "\\"
0x1800153ea  mov     rdx, rbx; unsigned __int64
0x1800153ed  lea     rcx, [rsp+548h+FileName]; unsigned __int16 *
0x1800153f5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800153fa  mov     r8, rsi; unsigned __int16 *
0x1800153fd  mov     rdx, rbx; unsigned __int64
0x180015400  lea     rcx, [rsp+548h+FileName]; unsigned __int16 *
0x180015408  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001540d  mov     [rsp+548h+var_2C8], di
0x180015415  xorps   xmm0, xmm0
0x180015418  movups  xmmword ptr [rsp+548h+var_2C6], xmm0
0x180015420  movups  xmmword ptr [rsp+548h+var_2C6+0Eh], xmm0
0x180015428  lea     r9, [rsp+548h+var_2C8]; unsigned __int16 *
0x180015430  lea     rdx, [rsp+548h+var_2A8]; void *
0x180015438  mov     rcx, r14; unsigned __int16 *
0x18001543b  call    ?GetAccountSidAndDomain@@YAJPEBGPEAXKPEAGK@Z; GetAccountSidAndDomain(ushort const *,void *,ulong,ushort *,ulong)
0x180015440  mov     edi, eax
0x180015442  lea     r15, [rsp+548h+var_2A8]
0x18001544a  xor     eax, eax
0x18001544c  test    edi, edi
0x18001544e  cmovs   r15, rax
0x180015452  xor     ecx, ecx; BindingHandle
0x180015454  call    cs:__imp_RpcImpersonateClient
0x18001545a  mov     ebx, eax
0x18001545c  xor     eax, eax
0x18001545e  test    ebx, ebx
0x180015460  jz      short loc_1800154A2
0x180015462  mov     r9d, ebx; unsigned int
0x180015465  lea     r8, aSasetaccountin; "SASetAccountInformation"
0x18001546c  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180015473  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180015478  test    ebx, 1FFF0000h
0x18001547e  jnz     short loc_18001548D
0x180015480  test    ebx, ebx
0x180015482  jle     short loc_18001548D
0x180015484  movzx   ebx, bx
0x180015487  or      ebx, 80070000h
0x18001548d  mov     [rsp+548h+var_508], ebx
0x180015491  lea     rcx, [rsp+548h+var_4D8]; this
0x180015496  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x18001549b  mov     eax, ebx
0x18001549d  jmp     loc_1800157AE
0x1800154a2  mov     [rsp+548h+TokenHandle], rax
0x1800154a7  call    cs:__imp_GetCurrentThread
0x1800154ad  lea     r9, [rsp+548h+TokenHandle]; TokenHandle
0x1800154b2  mov     edx, 2000Eh; DesiredAccess
0x1800154b7  mov     r8d, 1; OpenAsSelf
0x1800154bd  mov     rcx, rax; ThreadHandle
0x1800154c0  call    cs:__imp_OpenThreadToken
0x1800154c6  test    eax, eax
0x1800154c8  jnz     short loc_180015502
0x1800154ca  call    cs:__imp_GetLastError
0x1800154d0  test    eax, 1FFF0000h
0x1800154d5  jz      short loc_1800154E4
0x1800154d7  call    cs:__imp_GetLastError
0x1800154dd  mov     ebx, eax
0x1800154df  jmp     loc_180015763
0x1800154e4  call    cs:__imp_GetLastError
0x1800154ea  mov     ebx, eax
0x1800154ec  test    eax, eax
0x1800154ee  jle     loc_180015763
0x1800154f4  movzx   ebx, ax
0x1800154f7  or      ebx, 80070000h
0x1800154fd  jmp     loc_180015763
0x180015502  mov     r8d, 2; DesiredAccess
0x180015508  mov     rdx, [rsp+548h+TokenHandle]; ClientToken
0x18001550d  lea     rcx, [rsp+548h+FileName]; lpFileName
0x180015515  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x18001551a  mov     ebx, eax
0x18001551c  mov     [rsp+548h+var_508], eax
0x180015520  test    eax, eax
0x180015522  js      loc_180015767
0x180015528  xor     ebx, ebx
0x18001552a  test    edi, edi
0x18001552c  jns     short loc_180015535
0x18001552e  mov     ebx, edi
0x180015530  jmp     loc_180015763
0x180015535  test    r13, r13
0x180015538  jnz     loc_180015679
0x18001553e  mov     rcx, [rsp+548h+TokenHandle]; TokenHandle
0x180015543  call    cs:__imp_IsTokenRestricted
0x180015549  test    eax, eax
0x18001554b  jz      short loc_18001555F
0x18001554d  lea     eax, [r13+5]
0x180015551  movzx   ebx, ax
0x180015554  or      ebx, 80070000h
0x18001555a  jmp     loc_180015668
0x18001555f  mov     [rsp+548h+hObject], rbx
0x180015564  lea     r9, [rsp+548h+hObject]; void **
0x180015569  mov     edx, 40000000h; dwDesiredAccess
0x18001556e  mov     r8d, 2; dwShareMode
0x180015574  lea     rcx, [rsp+548h+FileName]; lpFileName
0x18001557c  call    ?OpenFileWithRetry@@YAJPEBGKKPEAPEAX@Z; OpenFileWithRetry(ushort const *,ulong,ulong,void * *)
0x180015581  mov     ebx, eax
0x180015583  mov     [rsp+548h+var_508], eax
0x180015587  test    eax, eax
0x180015589  js      loc_18001566C
0x18001558f  mov     rcx, [rsp+548h+hObject]; hObject
0x180015594  call    cs:__imp_CloseHandle
0x18001559a  xor     eax, eax
0x18001559c  cmp     [r14], ax
0x1800155a0  jnz     short loc_180015602
0x1800155a2  lea     edi, [rax+1]
0x1800155a5  mov     [rsp+548h+IsMember], eax
0x1800155a9  mov     [rsp+548h+SidToCheck], 101h
0x1800155b1  mov     [rsp+548h+var_4E4], 5000000h
0x1800155b9  mov     [rsp+548h+var_4E0], 12h
0x1800155c1  lea     r8, [rsp+548h+IsMember]; IsMember
0x1800155c6  lea     rdx, [rsp+548h+SidToCheck]; SidToCheck
0x1800155cb  mov     rcx, [rsp+548h+TokenHandle]; TokenHandle
0x1800155d0  call    cs:__imp_CheckTokenMembership
0x1800155d6  xor     ecx, ecx
0x1800155d8  test    eax, eax
0x1800155da  jz      short loc_180015638
0x1800155dc  cmp     [rsp+548h+IsMember], ecx
0x1800155e0  jnz     loc_18001566C
0x1800155e6  mov     rcx, [rsp+548h+TokenHandle]; void *
0x1800155eb  call    ?IsThreadCallerAnAdmin@@YAHPEAX@Z; IsThreadCallerAnAdmin(void *)
0x1800155f0  test    eax, eax
0x1800155f2  jnz     short loc_18001566C
0x1800155f4  test    edi, edi
0x1800155f6  jz      short loc_18001561B
0x1800155f8  mov     ebx, 80070005h
0x1800155fd  jmp     loc_180015763
0x180015602  mov     edi, eax
0x180015604  test    [rsp+548h+arg_20], 2000h
0x18001560f  jnz     short loc_1800155A5
0x180015611  mov     ebx, 80041314h
0x180015616  jmp     loc_180015763
0x18001561b  xor     edi, edi
0x18001561d  mov     [rsp+548h+var_4F4], edi
0x180015621  lea     r8, [rsp+548h+var_4F4]; IsMember
0x180015626  mov     rdx, r15; SidToCheck
0x180015629  mov     rcx, [rsp+548h+TokenHandle]; TokenHandle
0x18001562e  call    cs:__imp_CheckTokenMembership
0x180015634  test    eax, eax
0x180015636  jnz     short loc_18001565D
0x180015638  call    cs:__imp_GetLastError
0x18001563e  test    eax, eax
0x180015640  jz      short loc_18001566C
0x180015642  test    eax, 1FFF0000h
0x180015647  jz      short loc_180015651
0x180015649  mov     ebx, eax
0x18001564b  mov     [rsp+548h+var_508], eax
0x18001564f  jmp     short loc_18001566C
0x180015651  test    eax, eax
0x180015653  jg      loc_180015551
0x180015659  mov     ebx, eax
0x18001565b  jmp     short loc_180015668
0x18001565d  cmp     [rsp+548h+var_4F4], edi
0x180015661  jnz     short loc_18001566C
0x180015663  mov     ebx, 80070005h
0x180015668  mov     [rsp+548h+var_508], ebx
0x18001566c  xor     r15d, r15d
0x18001566f  test    ebx, ebx
0x180015671  js      loc_180015767
0x180015677  jmp     short loc_18001567C
0x180015679  xor     r15d, r15d
0x18001567c  xor     edx, edx; dwCoInit
0x18001567e  xor     ecx, ecx; pvReserved
0x180015680  call    cs:__imp_CoInitializeEx
0x180015686  mov     ebx, eax
0x180015688  mov     [rsp+548h+var_508], eax
0x18001568c  test    eax, eax
0x18001568e  jns     short loc_1800156A2
0x180015690  lea     rcx, aCoinitializeex_1; "CoInitializeEx failed inside SASetAccou"...
0x180015697  call    cs:__imp_OutputDebugStringW
0x18001569d  jmp     loc_180015767
0x1800156a2  mov     ecx, 108h; Size
0x1800156a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800156ac  test    rax, rax
0x1800156af  jz      loc_180015758
0x1800156b5  mov     rcx, rax; this
0x1800156b8  call    ??0CJob@@QEAA@XZ; CJob::CJob(void)
0x1800156bd  mov     rdi, rax
0x1800156c0  mov     [rsp+548h+hObject], rax
0x1800156c5  test    rax, rax
0x1800156c8  jz      loc_180015758
0x1800156ce  mov     eax, 1
0x1800156d3  mov     [rsp+548h+var_528], eax; int
0x1800156d7  mov     r9d, eax; int
0x1800156da  lea     rdx, [rsp+548h+FileName]; lpFileName
0x1800156e2  mov     rcx, rdi; this
0x1800156e5  call    ?LoadP@CJob@@QEAAJPEBGKHH@Z; CJob::LoadP(ushort const *,ulong,int,int)
0x1800156ea  mov     ebx, eax
0x1800156ec  mov     [rsp+548h+var_508], eax
0x1800156f0  test    eax, eax
0x1800156f2  jns     short loc_180015704
0x1800156f4  mov     rcx, rdi; this
0x1800156f7  call    ??_GCJob@@QEAAPEAXI@Z; CJob::`scalar deleting destructor'(uint)
0x1800156fc  call    cs:__imp_CoUninitialize
0x180015702  jmp     short loc_180015767
0x180015704  call    cs:__imp_RpcRevertToSelf
0x18001570a  nop
0x18001570b  lea     rax, aSystem; "System"
0x180015712  cmp     [r14], r15w
0x180015716  cmovnz  rax, r14
0x18001571a  mov     [rsp+548h+var_520], r13
0x18001571f  mov     qword ptr [rsp+548h+var_528], rax
0x180015724  mov     r9, rsi
0x180015727  mov     r8, rdi
0x18001572a  mov     edx, 1
0x18001572f  mov     rcx, r12
0x180015732  call    ?RegisterWithRetry@CompatibilityAdapter@@QEAAJW4ImpersonateType@1@PEAVCJob@@PEBG22H@Z; CompatibilityAdapter::RegisterWithRetry(CompatibilityAdapter::ImpersonateType,CJob *,ushort const *,ushort const *,ushort const *,int)
0x180015737  mov     ebx, eax
0x180015739  mov     [rsp+548h+var_508], eax
0x18001573d  jmp     short loc_180015748
0x18001573f  mov     ebx, [rsp+548h+var_508]
0x180015743  mov     rdi, [rsp+548h+hObject]
0x180015748  mov     rcx, rdi; this
0x18001574b  call    ??_GCJob@@QEAAPEAXI@Z; CJob::`scalar deleting destructor'(uint)
  ... truncated ...
```
