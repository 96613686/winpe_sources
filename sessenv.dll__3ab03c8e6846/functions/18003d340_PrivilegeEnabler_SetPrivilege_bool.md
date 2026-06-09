# PrivilegeEnabler::SetPrivilege(bool)

- ea: `0x18003d340`
- end: `0x18003d62d`
- name: `?SetPrivilege@PrivilegeEnabler@@AEAA_N_N@Z`
- size: `749`
- prototype: `bool __fastcall(LPCWSTR lpName, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b8ec`
- `0x18003c1ac`

## callees

- `0x18001a280`
- `0x18001ad68`
- `0x18003a8d4`
- `0x18003bfcc`
- `0x18003c004`
- `0x18003c134`
- `0x18003c664`
- `0x18003d340`
- `0x18003e238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d38e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d38e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d537`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d593`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d373`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d373`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003d386`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003d386`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003d4b8`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003d529`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003d4b8`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003d529`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003d402`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003d402`

## string_xrefs

- `0x18003d3a7`: `Failed to open process token. Error = `
- `0x18003d423`: `Failed to get privilege Id. Error = `
- `0x18003d5dc`: `AdjustTokenPrivileges failed. Error = `
- `0x18003d550`: `Failed to adjust process privileges.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall PrivilegeEnabler::SetPrivilege(const WCHAR *lpName, unsigned __int8 a2)
{
  int v2; // esi
  HANDLE CurrentProcess; // rax
  BOOL v5; // edi
  DWORD LastError; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  BOOL v10; // ebx
  DWORD v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  DWORD v15; // eax
  const char *v16; // rdx
  DWORD Attributes; // eax
  DWORD v18; // eax
  DWORD v19; // ebx
  DWORD v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  void *v24; // rcx
  __int64 v26; // rax
  void *TokenHandle; // [rsp+30h] [rbp-B8h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-B0h] BYREF
  struct _LUID Luid; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v31[24]; // [rsp+60h] [rbp-88h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+78h] [rbp-70h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+88h] [rbp-60h] BYREF
  _BYTE v34[32]; // [rsp+98h] [rbp-50h] BYREF
  _BYTE v35[32]; // [rsp+B8h] [rbp-30h] BYREF

  v2 = a2;
  TokenHandle = 0;
  try
  {
    CurrentProcess = GetCurrentProcess();
    v5 = OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle);
    LastError = GetLastError();
    v7 = std::to_string(v35, LastError);
    v8 = std::operator+<char>(v34, "Failed to open process token. Error = ", v7);
    LOBYTE(v9) = v5;
    CHECK_BOOL_THROW_SUPCREDEXCEPTION(v9, v8);
    std::string::~string(v34);
    std::string::~string(v35);
    Luid = 0;
    if ( *((_QWORD *)lpName + 3) > 7u )
      lpName = *(const WCHAR **)lpName;
    v10 = LookupPrivilegeValueW(0, lpName, &Luid);
    v11 = GetLastError();
    v12 = std::to_string(v34, v11);
    v13 = std::operator+<char>(v35, "Failed to get privilege Id. Error = ", v12);
    LOBYTE(v14) = v10;
    CHECK_BOOL_THROW_SUPCREDEXCEPTION(v14, v13);
    std::string::~string(v35);
    std::string::~string(v34);
    PreviousState = 0;
    ReturnLength = 16;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = Luid;
    NewState.Privileges[0].Attributes = 2 * v2;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
    v15 = GetLastError();
    if ( v15 )
    {
      if ( v15 != 1300 )
      {
        v26 = std::to_string(v35, v15);
        std::operator+<char>(v34, "AdjustTokenPrivileges failed. Error = ", v26);
        SupplementalCredentialsManagerException::SupplementalCredentialsManagerException((std::exception *)pExceptionObject);
        throw (SupplementalCredentialsManagerException *)pExceptionObject;
      }
      SupplementalCredentialsManagerException::SupplementalCredentialsManagerException(
        (SupplementalCredentialsManagerException *)v31,
        v16);
      throw (SupplementalCredentialsManagerException *)v31;
    }
    if ( PreviousState.PrivilegeCount )
    {
      Attributes = PreviousState.Privileges[0].Attributes;
    }
    else
    {
      Attributes = 0;
      PreviousState.Privileges[0].Attributes = 0;
    }
    if ( (_BYTE)v2 )
      v18 = Attributes | 2;
    else
      v18 = Attributes & 0xFFFFFFFD;
    NewState.Privileges[0].Attributes = v18;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0);
    v19 = GetLastError();
    v20 = GetLastError();
    v21 = std::to_string(v34, v20);
    v22 = std::operator+<char>(v35, "Failed to adjust process privileges.", v21);
    LOBYTE(v23) = v19 == 0;
    CHECK_BOOL_THROW_SUPCREDEXCEPTION(v23, v22);
    std::string::~string(v35);
    std::string::~string(v34);
    v24 = TokenHandle;
  }
  catch ( ... )
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    throw;
  }
  CloseHandle(v24);
  return (PreviousState.Privileges[0].Attributes & 2) != 0;
}

```

## disassembly

```asm
0x18003d340  mov     [rsp+arg_8], rbx
0x18003d345  mov     [rsp+arg_10], rsi
0x18003d34a  push    rdi
0x18003d34b  sub     rsp, 0E0h
0x18003d352  mov     rax, cs:__security_cookie
0x18003d359  xor     rax, rsp
0x18003d35c  mov     [rsp+0E8h+var_10], rax
0x18003d364  movzx   esi, dl
0x18003d367  mov     rbx, rcx
0x18003d36a  mov     [rsp+0E8h+TokenHandle], 0
0x18003d373  call    cs:__imp_GetCurrentProcess
0x18003d379  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x18003d37e  mov     edx, 28h ; '('; DesiredAccess
0x18003d383  mov     rcx, rax; ProcessHandle
0x18003d386  call    cs:__imp_OpenProcessToken
0x18003d38c  mov     edi, eax
0x18003d38e  call    cs:__imp_GetLastError
0x18003d394  mov     edx, eax
0x18003d396  lea     rcx, [rsp+0E8h+var_30]
0x18003d39e  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@K@Z; std::to_string(ulong)
0x18003d3a3  nop
0x18003d3a4  mov     r8, rax
0x18003d3a7  lea     rdx, aFailedToOpenPr; "Failed to open process token. Error = "
0x18003d3ae  lea     rcx, [rsp+0E8h+var_50]
0x18003d3b6  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18003d3bb  nop
0x18003d3bc  test    edi, edi
0x18003d3be  setnz   cl
0x18003d3c1  mov     rdx, rax
0x18003d3c4  call    ?CHECK_BOOL_THROW_SUPCREDEXCEPTION@@YAX_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CHECK_BOOL_THROW_SUPCREDEXCEPTION(bool,std::string const &)
0x18003d3c9  nop
0x18003d3ca  lea     rcx, [rsp+0E8h+var_50]
0x18003d3d2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d3d7  nop
0x18003d3d8  lea     rcx, [rsp+0E8h+var_30]
0x18003d3e0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d3e5  mov     qword ptr [rsp+0E8h+Luid.LowPart], 0
0x18003d3ee  cmp     qword ptr [rbx+18h], 7
0x18003d3f3  jbe     short loc_18003D3F8
0x18003d3f5  mov     rbx, [rbx]
0x18003d3f8  lea     r8, [rsp+0E8h+Luid]; lpLuid
0x18003d3fd  mov     rdx, rbx; lpName
0x18003d400  xor     ecx, ecx; lpSystemName
0x18003d402  call    cs:__imp_LookupPrivilegeValueW
0x18003d408  mov     ebx, eax
0x18003d40a  call    cs:__imp_GetLastError
0x18003d410  mov     edx, eax
0x18003d412  lea     rcx, [rsp+0E8h+var_50]
0x18003d41a  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@K@Z; std::to_string(ulong)
0x18003d41f  nop
0x18003d420  mov     r8, rax
0x18003d423  lea     rdx, aFailedToGetPri; "Failed to get privilege Id. Error = "
0x18003d42a  lea     rcx, [rsp+0E8h+var_30]
0x18003d432  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18003d437  nop
0x18003d438  test    ebx, ebx
0x18003d43a  setnz   cl
0x18003d43d  mov     rdx, rax
0x18003d440  call    ?CHECK_BOOL_THROW_SUPCREDEXCEPTION@@YAX_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CHECK_BOOL_THROW_SUPCREDEXCEPTION(bool,std::string const &)
0x18003d445  nop
0x18003d446  lea     rcx, [rsp+0E8h+var_30]
0x18003d44e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d453  nop
0x18003d454  lea     rcx, [rsp+0E8h+var_50]
0x18003d45c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d461  xorps   xmm0, xmm0
0x18003d464  movups  xmmword ptr [rsp+0E8h+var_60.PrivilegeCount], xmm0
0x18003d46c  mov     ebx, 10h
0x18003d471  mov     [rsp+0E8h+var_B0], ebx
0x18003d475  mov     [rsp+0E8h+NewState.PrivilegeCount], 1
0x18003d47d  mov     rax, qword ptr [rsp+0E8h+Luid.LowPart]
0x18003d482  mov     qword ptr [rsp+0E8h+NewState.Privileges.Luid.LowPart], rax
0x18003d487  mov     eax, esi
0x18003d489  add     eax, eax
0x18003d48b  mov     [rsp+0E8h+NewState.Privileges.Attributes], eax
0x18003d492  lea     rax, [rsp+0E8h+var_B0]
0x18003d497  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x18003d49c  lea     rax, [rsp+0E8h+var_60]
0x18003d4a4  mov     [rsp+0E8h+PreviousState], rax; PreviousState
0x18003d4a9  mov     r9d, ebx; BufferLength
0x18003d4ac  lea     r8, [rsp+0E8h+NewState]; NewState
0x18003d4b1  xor     edx, edx; DisableAllPrivileges
0x18003d4b3  mov     rcx, [rsp+0E8h+TokenHandle]; TokenHandle
0x18003d4b8  call    cs:__imp_AdjustTokenPrivileges
0x18003d4be  call    cs:__imp_GetLastError
0x18003d4c4  test    eax, eax
0x18003d4c6  jz      short loc_18003D4D8
0x18003d4c8  cmp     eax, 514h
0x18003d4cd  jz      loc_18003D610
0x18003d4d3  jmp     loc_18003D5C9
0x18003d4d8  cmp     [rsp+0E8h+var_60.PrivilegeCount], 0
0x18003d4e0  jnz     short loc_18003D4ED
0x18003d4e2  xor     eax, eax
0x18003d4e4  mov     [rsp+0E8h+var_60.Privileges.Attributes], eax
0x18003d4eb  jmp     short loc_18003D4F4
0x18003d4ed  mov     eax, [rsp+0E8h+var_60.Privileges.Attributes]
0x18003d4f4  test    sil, sil
0x18003d4f7  jz      short loc_18003D4FE
0x18003d4f9  or      eax, 2
0x18003d4fc  jmp     short loc_18003D501
0x18003d4fe  and     eax, 0FFFFFFFDh
0x18003d501  mov     [rsp+0E8h+NewState.Privileges.Attributes], eax
0x18003d508  mov     [rsp+0E8h+ReturnLength], 0; ReturnLength
0x18003d511  mov     [rsp+0E8h+PreviousState], 0; PreviousState
0x18003d51a  mov     r9d, ebx; BufferLength
0x18003d51d  lea     r8, [rsp+0E8h+NewState]; NewState
0x18003d522  xor     edx, edx; DisableAllPrivileges
0x18003d524  mov     rcx, [rsp+0E8h+TokenHandle]; TokenHandle
0x18003d529  call    cs:__imp_AdjustTokenPrivileges
0x18003d52f  call    cs:__imp_GetLastError
0x18003d535  mov     ebx, eax
0x18003d537  call    cs:__imp_GetLastError
0x18003d53d  mov     edx, eax
0x18003d53f  lea     rcx, [rsp+0E8h+var_50]
0x18003d547  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@K@Z; std::to_string(ulong)
0x18003d54c  nop
0x18003d54d  mov     r8, rax
0x18003d550  lea     rdx, aFailedToAdjust; "Failed to adjust process privileges."
0x18003d557  lea     rcx, [rsp+0E8h+var_30]
0x18003d55f  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18003d564  nop
0x18003d565  test    ebx, ebx
0x18003d567  setz    cl
0x18003d56a  mov     rdx, rax
0x18003d56d  call    ?CHECK_BOOL_THROW_SUPCREDEXCEPTION@@YAX_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CHECK_BOOL_THROW_SUPCREDEXCEPTION(bool,std::string const &)
0x18003d572  nop
0x18003d573  lea     rcx, [rsp+0E8h+var_30]
0x18003d57b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d580  nop
0x18003d581  lea     rcx, [rsp+0E8h+var_50]
0x18003d589  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d58e  mov     rcx, [rsp+0E8h+TokenHandle]; hObject
0x18003d593  call    cs:__imp_CloseHandle
0x18003d599  mov     eax, [rsp+0E8h+var_60.Privileges.Attributes]
0x18003d5a0  shr     eax, 1
0x18003d5a2  and     al, 1
0x18003d5a4  mov     rcx, [rsp+0E8h+var_10]
0x18003d5ac  xor     rcx, rsp; StackCookie
0x18003d5af  call    __security_check_cookie
0x18003d5b4  lea     r11, [rsp+0E8h+var_8]
0x18003d5bc  mov     rbx, [r11+18h]
0x18003d5c0  mov     rsi, [r11+20h]
0x18003d5c4  mov     rsp, r11
0x18003d5c7  pop     rdi
0x18003d5c8  retn
0x18003d5c9  mov     edx, eax
0x18003d5cb  lea     rcx, [rsp+0E8h+var_30]
0x18003d5d3  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@K@Z; std::to_string(ulong)
0x18003d5d8  nop
0x18003d5d9  mov     r8, rax
0x18003d5dc  lea     rdx, aAdjusttokenpri; "AdjustTokenPrivileges failed. Error = "
0x18003d5e3  lea     rcx, [rsp+0E8h+var_50]
0x18003d5eb  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18003d5f0  nop
0x18003d5f1  mov     rdx, rax
0x18003d5f4  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x18003d5f9  call    ??0SupplementalCredentialsManagerException@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; SupplementalCredentialsManagerException::SupplementalCredentialsManagerException(std::string const &)
0x18003d5fe  lea     rdx, _TI3?AVSupplementalCredentialsManagerException@@; pThrowInfo
0x18003d605  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18003d60a  call    _CxxThrowException_0
0x18003d610  lea     rcx, [rsp+0E8h+var_88]; this
0x18003d615  call    ??0SupplementalCredentialsManagerException@@QEAA@PEBD@Z; SupplementalCredentialsManagerException::SupplementalCredentialsManagerException(char const *)
0x18003d61a  lea     rdx, _TI3?AVSupplementalCredentialsManagerException@@; pThrowInfo
0x18003d621  lea     rcx, [rsp+0E8h+var_88]; pExceptionObject
0x18003d626  call    _CxxThrowException_0
```
