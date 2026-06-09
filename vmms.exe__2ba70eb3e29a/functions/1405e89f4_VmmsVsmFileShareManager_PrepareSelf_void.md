# VmmsVsmFileShareManager::PrepareSelf(void)

- ea: `0x1405e89f4`
- end: `0x1405e904d`
- name: `?PrepareSelf@VmmsVsmFileShareManager@@EEAAXXZ`
- size: `1625`
- prototype: `void __fastcall(VmmsVsmFileShareManager *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1405e89e0`

## callees

- `0x14001993c`
- `0x140022640`
- `0x140034404`
- `0x14004bf10`
- `0x14004f3c4`
- `0x14005c630`
- `0x140092260`
- `0x1400923e8`
- `0x140093948`
- `0x1400acf04`
- `0x1400b971c`
- `0x1400ee880`
- `0x140115654`
- `0x140116354`
- `0x14017902c`
- `0x140188e18`
- `0x1401c86a4`
- `0x140234678`
- `0x140235a38`
- `0x140235d5c`
- `0x140237a2c`
- `0x140304734`
- `0x1404828e0`
- `0x1404835a0`
- `0x1405e8748`
- `0x1405e8814`
- `0x1405e89f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405e8c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405e8c9c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1405e8b32`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1405e8d58`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1405e8ec0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1405e8b32`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1405e8d58`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1405e8ec0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x1405e8ee5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x1405e8ee5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1405e8aed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1405e8aed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1405e8ab4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1405e8ab4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1405e8fe1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1405e8ff6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1405e8fe1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1405e8ff6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1405e8be7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1405e8be7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1405e8c88`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1405e8c88`
- `srvcli!NetShareDel` at `0x1405e8e4a`
- `srvcli!NetShareDel` at `0x1405e8e4a`

## string_xrefs

- `0x1405e8bcd`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1405e8bfe`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1405e8cdd`: `VSM temporary file share directory exists - cleaning it up!\n`
- `0x1405e8f8f`: `%hs cannot delete directory "%ws\%ws"! Path too long.\n`
- `0x1405e8f3c`: `Deleting VSM temporary file share directory "%ws"!\n`
- `0x1405e8e32`: `Deleting VSM temporary file share "%ws"!\n`
- `0x1405e8e7e`: `%hs failed to delete file share "%ws"! Status = %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall VmmsVsmFileShareManager::PrepareSelf(VmmsVsmFileShareManager *this)
{
  WCHAR *v2; // rcx
  const char *v3; // r9
  WCHAR *v4; // rcx
  WCHAR *v5; // rcx
  LPWSTR *v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  PSECURITY_DESCRIPTOR v10; // rdi
  const WCHAR *v11; // rcx
  DWORD LastError; // eax
  WCHAR *v13; // rcx
  LPWSTR *v14; // rax
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rdx
  int v17; // ecx
  int v18; // ecx
  DWORD v19; // eax
  DWORD v20; // ebx
  WCHAR *v21; // rcx
  WCHAR *v22; // rcx
  LPWSTR *v23; // rax
  __int64 v24; // rdx
  LPWSTR *v25; // r8
  const WCHAR *v26; // rcx
  LPWSTR *v27; // r9
  __int64 v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR pszPath[2]; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v32; // [rsp+60h] [rbp-A0h]
  LPWSTR lpBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  __m128i si128; // [rsp+80h] [rbp-80h]
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor[2]; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL hMem[3]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v38[80]; // [rsp+C0h] [rbp-40h] BYREF
  struct _WIN32_FIND_DATAW v39; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  *(_OWORD *)lpBuffer = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpBuffer[0]) = 0;
  TokenHandle = 0;
  memset_0(v38, 0, sizeof(v38));
  Vml::VmSid::VmSid((Vml::VmSid *)v38, 0);
  pSecurityDescriptor[1] = 0;
  pSecurityDescriptor[0] = 0;
  *(_OWORD *)hMem = 0;
  Vml::VmDacl::VmDacl((Vml::VmDacl *)hMem, 0);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  std::wstring::resize(lpBuffer);
  v2 = (WCHAR *)lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v2 = lpBuffer[0];
  if ( !GetSystemWindowsDirectoryW(v2, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\vm\\vmms\\migration\\vmmsvsmfilesharemanager.cpp",
      v3);
  v4 = (WCHAR *)lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = lpBuffer[0];
  if ( !PathStripToRootW(v4) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecore\\vm\\vmms\\migration\\vmmsvsmfilesharemanager.cpp",
      (const char *)0x10B,
      v28);
  v5 = (WCHAR *)lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = lpBuffer[0];
  if ( !PathAppendW(v5, L"$VSM$") )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\vm\\vmms\\migration\\vmmsvsmfilesharemanager.cpp",
      (const char *)0x6F,
      v28);
  v6 = lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v6 = (LPWSTR *)lpBuffer[0];
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)v6 + v7) );
  std::wstring::resize(lpBuffer);
  Vml::VmlGetProcessAccessToken(&TokenHandle, 8u, v8);
  Vml::VmAccessToken::GetDefaultDacl((Vml::VmAccessToken *)&TokenHandle, (struct Vml::VmDacl *)hMem);
  Vml::VmSecurityDescriptor::Initialize((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  Vml::VmSecurityDescriptor::SetDacl((Vml::VmSecurityDescriptor *)pSecurityDescriptor, (const struct _ACL *)hMem[0]);
  if ( !pSecurityDescriptor[0] )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xCA5,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)0x57,
      v28);
  if ( !SetSecurityDescriptorControl(pSecurityDescriptor[0], 0x1000u, 0x1000u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xCA9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v9);
  Vml::VmSecurityDescriptor::MakeSelfRelative((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  v10 = pSecurityDescriptor[0];
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor[0];
  Vml::VmPerfTraceComponent::UpdateTracingEnabled((Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace);
  if ( g_MigrationPerfTrace && (unsigned int)VmlIsDebugTraceEnabled(53349) )
    VmlDebugTraceEx(53349, &off_14091B688);
  v11 = (const WCHAR *)lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v11 = lpBuffer[0];
  if ( !CreateDirectoryW(v11, &SecurityAttributes) )
  {
    LastError = GetLastError();
    if ( LastError != 183 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecore\\vm\\vmms\\migration\\vmmsvsmfilesharemanager.cpp",
        (const char *)LastError,
        v28);
    if ( (unsigned int)VmlIsDebugTraceEnabled(32869) )
      VmlDebugTrace(32869, L"VSM temporary file share directory exists - cleaning it up!\n");
    v29 = -1;
    memset_0(&v39, 0, sizeof(v39));
    *(_OWORD *)pszPath = 0;
    v32 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(pszPath[0]) = 0;
    std::wstring::operator=(pszPath, lpBuffer);
    std::wstring::resize(pszPath);
    v13 = (WCHAR *)pszPath;
    if ( v32.m128i_i64[1] > 7uLL )
      v13 = pszPath[0];
    if ( !PathAppendW(v13, L"*") )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\vm\\vmms\\migration\\vmmsvsmfilesharemanager.cpp",
        (const char *)0x8000FFFFLL,
        v28);
    v14 = pszPath;
    if ( v32.m128i_i64[1] > 7uLL )
      v14 = (LPWSTR *)pszPath[0];
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    std::wstring::resize(pszPath);
    v16 = (const unsigned __int16 *)pszPath;
    if ( v32.m128i_i64[1] > 7uLL )
      v16 = pszPath[0];
    if ( Vml::VmEnumFiles::Begin((Vml::VmEnumFiles *)&v29, v16, &v39) )
    {
      do
      {
        v17 = 46 - v39.cFileName[0];
        if ( v39.cFileName[0] == 46 )
          v17 = -v39.cFileName[1];
        if ( v17 )
        {
          v18 = 46 - v39.cFileName[0];
          if ( v39.cFileName[0] == 46 )
          {
            v18 = 46 - v39.cFileName[1];
            if ( v39.cFileName[1] == 46 )
              v18 = -v39.cFileName[2];
          }
          if ( v18 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(32869) )
              VmlDebugTrace(32869, L"Deleting VSM temporary file share \"%ws\"!\n", v39.cFileName);
            v19 = NetShareDel(0, v39.cFileName, 0);
            v20 = v19;
            if ( v19 && v19 != 2310 && (unsigned int)VmlIsDebugTraceEnabled(32869) )
            {
              LODWORD(v28) = v20;
              VmlDebugTrace(
                32869,
                L"%hs failed to delete file share \"%ws\"! Status = %u\n",
                "VmmsVsmFileShareManager::PrepareSelf",
                v39.cFileName,
                v28);
            }
            std::wstring::operator=(pszPath, lpBuffer);
            std::wstring::resize(pszPath);
            v21 = (WCHAR *)pszPath;
            if ( v32.m128i_i64[1] > 7uLL )
              v21 = pszPath[0];
            if ( !PathAppendW(v21, v39.cFileName) )
              goto LABEL_85;
            v22 = (WCHAR *)pszPath;
            if ( v32.m128i_i64[1] > 7uLL )
              v22 = pszPath[0];
            if ( PathAddBackslashW(v22) )
            {
              v23 = pszPath;
              if ( v32.m128i_i64[1] > 7uLL )
                v23 = (LPWSTR *)pszPath[0];
              v24 = -1;
              do
                ++v24;
              while ( *((_WORD *)v23 + v24) );
              std::wstring::resize(pszPath);
              if ( (unsigned int)VmlIsDebugTraceEnabled(32869) )
              {
                v25 = pszPath;
                if ( v32.m128i_i64[1] > 7uLL )
                  v25 = (LPWSTR *)pszPath[0];
                VmlDebugTrace(32869, L"Deleting VSM temporary file share directory \"%ws\"!\n", v25);
              }
              v26 = (const WCHAR *)pszPath;
              if ( v32.m128i_i64[1] > 7uLL )
                v26 = pszPath[0];
              VmmsVsmFileShare::RemoveTemporaryDirectory(v26);
            }
            else
            {
LABEL_85:
              if ( (unsigned int)VmlIsDebugTraceEnabled(32869) )
              {
                v27 = lpBuffer;
                if ( si128.m128i_i64[1] > 7uLL )
                  v27 = (LPWSTR *)lpBuffer[0];
                VmlDebugTrace(
                  32869,
                  L"%hs cannot delete directory \"%ws\\%ws\"! Path too long.\n",
                  "VmmsVsmFileShareManager::PrepareSelf",
                  v27,
                  v39.cFileName);
              }
            }
          }
        }
      }
      while ( Vml::VmEnumFiles::Next((Vml::VmEnumFiles *)&v29, &v39) );
    }
    std::wstring::_Tidy_deallocate(pszPath);
    Vml::VmEnumFiles::~VmEnumFiles((Vml::VmEnumFiles *)&v29);
  }
  std::wstring::swap((char *)this - 40, lpBuffer);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( v10 )
    LocalFree(v10);
  Vml::VmSid::~VmSid((Vml::VmSid *)v38);
  Vml::VmAccessToken::~VmAccessToken((Vml::VmAccessToken *)&TokenHandle);
  std::wstring::_Tidy_deallocate(lpBuffer);
}

```

## disassembly

```asm
0x1405e89f4  mov     [rsp-8+arg_8], rbx
0x1405e89f9  mov     [rsp-8+arg_10], rsi
0x1405e89fe  push    rbp
0x1405e89ff  push    rdi
0x1405e8a00  push    r12
0x1405e8a02  push    r13
0x1405e8a04  push    r14
0x1405e8a06  lea     rbp, [rsp-270h]
0x1405e8a0e  sub     rsp, 370h
0x1405e8a15  mov     rax, cs:__security_cookie
0x1405e8a1c  xor     rax, rsp
0x1405e8a1f  mov     [rbp+290h+var_30], rax
0x1405e8a26  mov     rsi, rcx
0x1405e8a29  xorps   xmm0, xmm0
0x1405e8a2c  movups  xmmword ptr [rsp+390h+lpBuffer], xmm0
0x1405e8a31  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1405e8a39  movdqu  [rbp+290h+var_310], xmm1
0x1405e8a3e  xor     r14d, r14d
0x1405e8a41  mov     word ptr [rsp+390h+lpBuffer], r14w
0x1405e8a47  mov     [rbp+290h+TokenHandle], r14
0x1405e8a4b  xor     edx, edx; Val
0x1405e8a4d  lea     r8d, [r14+50h]; Size
0x1405e8a51  lea     rcx, [rbp+290h+var_2D0]; void *
0x1405e8a55  call    memset_0
0x1405e8a5a  xor     edx, edx; void *
0x1405e8a5c  lea     rcx, [rbp+290h+var_2D0]; this
0x1405e8a60  call    ??0VmSid@Vml@@QEAA@PEAX@Z; Vml::VmSid::VmSid(void *)
0x1405e8a65  nop
0x1405e8a66  xorps   xmm0, xmm0
0x1405e8a69  movups  xmmword ptr [rbp+290h+pSecurityDescriptor], xmm0
0x1405e8a6d  mov     [rbp+290h+pSecurityDescriptor], r14
0x1405e8a71  movups  xmmword ptr [rbp+290h+hMem], xmm0
0x1405e8a75  xor     edx, edx; struct _ACL *
0x1405e8a77  lea     rcx, [rbp+290h+hMem]; this
0x1405e8a7b  call    ??0VmDacl@Vml@@QEAA@PEBU_ACL@@@Z; Vml::VmDacl::VmDacl(_ACL const *)
0x1405e8a80  nop
0x1405e8a81  xorps   xmm0, xmm0
0x1405e8a84  xor     eax, eax
0x1405e8a86  movups  xmmword ptr [rsp+390h+SecurityAttributes.nLength], xmm0
0x1405e8a8b  mov     qword ptr [rsp+390h+SecurityAttributes.bInheritHandle], rax
0x1405e8a90  mov     edx, 104h
0x1405e8a95  lea     rcx, [rsp+390h+lpBuffer]; Src
0x1405e8a9a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1405e8a9f  lea     rcx, [rsp+390h+lpBuffer]
0x1405e8aa4  cmp     qword ptr [rbp+290h+var_310+8], 7
0x1405e8aa9  cmova   rcx, [rsp+390h+lpBuffer]; lpBuffer
0x1405e8aaf  mov     edx, 104h; uSize
0x1405e8ab4  call    cs:__imp_GetSystemWindowsDirectoryW
0x1405e8abb  nop     dword ptr [rax+rax+00h]
0x1405e8ac0  test    eax, eax
0x1405e8ac2  jnz     short loc_1405E8ADD
0x1405e8ac4  mov     rcx, [rbp+298h]; this
0x1405e8acb  lea     r8, aOnecoreVmVmmsM_28; "onecore\\vm\\vmms\\migration\\vmmsvsmfi"...
0x1405e8ad2  mov     edx, 0ADh; void *
0x1405e8ad7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1405e8add  lea     rcx, [rsp+390h+lpBuffer]
0x1405e8ae2  cmp     qword ptr [rbp+290h+var_310+8], 7
0x1405e8ae7  cmova   rcx, [rsp+390h+lpBuffer]; pszPath
0x1405e8aed  call    cs:__imp_PathStripToRootW
0x1405e8af4  nop     dword ptr [rax+rax+00h]
0x1405e8af9  test    eax, eax
0x1405e8afb  jnz     short loc_1405E8B1B
0x1405e8afd  mov     rcx, [rbp+298h]; this
0x1405e8b04  mov     r9d, 10Bh; char *
0x1405e8b0a  lea     r8, aOnecoreVmVmmsM_28; "onecore\\vm\\vmms\\migration\\vmmsvsmfi"...
0x1405e8b11  lea     edx, [r9-59h]; void *
0x1405e8b15  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1405e8b1b  lea     rcx, [rsp+390h+lpBuffer]
0x1405e8b20  cmp     qword ptr [rbp+290h+var_310+8], 7
0x1405e8b25  cmova   rcx, [rsp+390h+lpBuffer]; pszPath
0x1405e8b2b  lea     rdx, aVsm; "$VSM$"
0x1405e8b32  call    cs:__imp_PathAppendW
0x1405e8b39  nop     dword ptr [rax+rax+00h]
0x1405e8b3e  test    eax, eax
0x1405e8b40  jnz     short loc_1405E8B5E
0x1405e8b42  mov     rcx, [rbp+298h]; this
0x1405e8b49  lea     r9d, [rax+6Fh]; char *
0x1405e8b4d  lea     r8, aOnecoreVmVmmsM_28; "onecore\\vm\\vmms\\migration\\vmmsvsmfi"...
0x1405e8b54  lea     edx, [r9+48h]; void *
0x1405e8b58  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1405e8b5e  lea     rax, [rsp+390h+lpBuffer]
0x1405e8b63  cmp     qword ptr [rbp+290h+var_310+8], 7
0x1405e8b68  cmova   rax, [rsp+390h+lpBuffer]
0x1405e8b6e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1405e8b72  inc     rdx
0x1405e8b75  cmp     [rax+rdx*2], r14w
0x1405e8b7a  jnz     short loc_1405E8B72
0x1405e8b7c  lea     rcx, [rsp+390h+lpBuffer]; Src
0x1405e8b81  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1405e8b86  mov     edx, 8; DesiredAccess
0x1405e8b8b  lea     rcx, [rbp+290h+TokenHandle]; TokenHandle
0x1405e8b8f  call    ?VmlGetProcessAccessToken@Vml@@YAXAEAVVmAccessToken@1@K@Z; Vml::VmlGetProcessAccessToken(Vml::VmAccessToken &,ulong)
0x1405e8b94  lea     rdx, [rbp+290h+hMem]; struct Vml::VmDacl *
0x1405e8b98  lea     rcx, [rbp+290h+TokenHandle]; this
0x1405e8b9c  call    ?GetDefaultDacl@VmAccessToken@Vml@@QEBAXAEAVVmDacl@2@@Z; Vml::VmAccessToken::GetDefaultDacl(Vml::VmDacl &)
0x1405e8ba1  lea     rcx, [rbp+290h+pSecurityDescriptor]; this
0x1405e8ba5  call    ?Initialize@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::Initialize(void)
0x1405e8baa  mov     rdx, [rbp+290h+hMem]; struct _ACL *
0x1405e8bae  lea     rcx, [rbp+290h+pSecurityDescriptor]; this
0x1405e8bb2  call    ?SetDacl@VmSecurityDescriptor@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmSecurityDescriptor::SetDacl(_ACL const *)
0x1405e8bb7  mov     rcx, [rbp+290h+pSecurityDescriptor]; pSecurityDescriptor
0x1405e8bbb  test    rcx, rcx
0x1405e8bbe  jnz     short loc_1405E8BDF
0x1405e8bc0  mov     rcx, [rbp+298h]; this
0x1405e8bc7  mov     r9d, 57h ; 'W'; char *
0x1405e8bcd  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1405e8bd4  mov     edx, 0CA5h; void *
0x1405e8bd9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1405e8bdf  mov     edx, 1000h; ControlBitsOfInterest
0x1405e8be4  mov     r8d, edx; ControlBitsToSet
0x1405e8be7  call    cs:__imp_SetSecurityDescriptorControl
0x1405e8bee  nop     dword ptr [rax+rax+00h]
0x1405e8bf3  mov     rcx, [rbp+298h]; this
0x1405e8bfa  test    eax, eax
0x1405e8bfc  jnz     short loc_1405E8C10
0x1405e8bfe  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1405e8c05  mov     edx, 0CA9h; void *
0x1405e8c0a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1405e8c10  lea     rcx, [rbp+290h+pSecurityDescriptor]; this
0x1405e8c14  call    ?MakeSelfRelative@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeSelfRelative(void)
0x1405e8c19  mov     qword ptr [rsp+390h+SecurityAttributes.nLength], 18h
0x1405e8c22  mov     qword ptr [rsp+390h+SecurityAttributes.bInheritHandle], r14
0x1405e8c27  mov     rdi, [rbp+290h+pSecurityDescriptor]
0x1405e8c2b  mov     [rsp+390h+SecurityAttributes.lpSecurityDescriptor], rdi
0x1405e8c30  lea     rcx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; this
0x1405e8c37  call    ?UpdateTracingEnabled@VmPerfTraceComponent@Vml@@AEAAXXZ; Vml::VmPerfTraceComponent::UpdateTracingEnabled(void)
0x1405e8c3c  cmp     cs:?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A, r14d; Vml::VmPerfTraceComponent g_MigrationPerfTrace
0x1405e8c43  jz      short loc_1405E8C73
0x1405e8c45  mov     ebx, 0D065h
0x1405e8c4a  mov     ecx, ebx
0x1405e8c4c  call    VmlIsDebugTraceEnabled
0x1405e8c51  test    eax, eax
0x1405e8c53  jz      short loc_1405E8C73
0x1405e8c55  lea     r8, [rsp+390h+lpBuffer]
0x1405e8c5a  cmp     qword ptr [rbp+290h+var_310+8], 7
0x1405e8c5f  cmova   r8, [rsp+390h+lpBuffer]
0x1405e8c65  lea     rdx, off_14091B688; "Creating directory for file shares at "...
0x1405e8c6c  mov     ecx, ebx
0x1405e8c6e  call    VmlDebugTraceEx
0x1405e8c73  lea     rcx, [rsp+390h+lpBuffer]
0x1405e8c78  cmp     qword ptr [rbp+290h+var_310+8], 7
0x1405e8c7d  cmova   rcx, [rsp+390h+lpBuffer]; lpPathName
0x1405e8c83  lea     rdx, [rsp+390h+SecurityAttributes]; lpSecurityAttributes
0x1405e8c88  call    cs:__imp_CreateDirectoryW
0x1405e8c8f  nop     dword ptr [rax+rax+00h]
0x1405e8c94  test    eax, eax
0x1405e8c96  jnz     loc_1405E8FC9
0x1405e8c9c  call    cs:__imp_GetLastError
0x1405e8ca3  nop     dword ptr [rax+rax+00h]
0x1405e8ca8  cmp     eax, 0B7h
0x1405e8cad  jz      short loc_1405E8CCB
0x1405e8caf  mov     rcx, [rbp+298h]; this
0x1405e8cb6  mov     r9d, eax; char *
0x1405e8cb9  lea     r8, aOnecoreVmVmmsM_28; "onecore\\vm\\vmms\\migration\\vmmsvsmfi"...
0x1405e8cc0  mov     edx, 0D5h; void *
0x1405e8cc5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1405e8ccb  mov     r12d, 8065h
0x1405e8cd1  mov     ecx, r12d
0x1405e8cd4  call    VmlIsDebugTraceEnabled
0x1405e8cd9  test    eax, eax
0x1405e8cdb  jz      short loc_1405E8CEC
0x1405e8cdd  lea     rdx, aVsmTemporaryFi; "VSM temporary file share directory exis"...
0x1405e8ce4  mov     ecx, r12d
0x1405e8ce7  call    VmlDebugTrace
0x1405e8cec  mov     [rsp+390h+var_360], 0FFFFFFFFFFFFFFFFh
0x1405e8cf5  xor     edx, edx; Val
0x1405e8cf7  mov     r8d, 250h; Size
0x1405e8cfd  lea     rcx, [rbp+290h+var_280]; void *
0x1405e8d01  call    memset_0
0x1405e8d06  xorps   xmm0, xmm0
0x1405e8d09  movups  xmmword ptr [rsp+390h+pszPath], xmm0
0x1405e8d0e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1405e8d16  movdqu  [rsp+390h+var_330], xmm1
0x1405e8d1c  mov     word ptr [rsp+390h+pszPath], r14w
0x1405e8d22  lea     rdx, [rsp+390h+lpBuffer]
0x1405e8d27  lea     rcx, [rsp+390h+pszPath]
0x1405e8d2c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1405e8d31  mov     edx, 104h
0x1405e8d36  lea     rcx, [rsp+390h+pszPath]; Src
0x1405e8d3b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1405e8d40  lea     rcx, [rsp+390h+pszPath]
0x1405e8d45  cmp     qword ptr [rsp+390h+var_330+8], 7
0x1405e8d4b  cmova   rcx, [rsp+390h+pszPath]; pszPath
0x1405e8d51  lea     rdx, asc_1409618EC; "*"
0x1405e8d58  call    cs:__imp_PathAppendW
0x1405e8d5f  nop     dword ptr [rax+rax+00h]
0x1405e8d64  test    eax, eax
0x1405e8d66  jnz     short loc_1405E8D87
0x1405e8d68  mov     rcx, [rbp+298h]; this
0x1405e8d6f  mov     r9d, 8000FFFFh; char *
0x1405e8d75  lea     r8, aOnecoreVmVmmsM_28; "onecore\\vm\\vmms\\migration\\vmmsvsmfi"...
0x1405e8d7c  mov     edx, 0E7h; void *
0x1405e8d81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1405e8d87  lea     rax, [rsp+390h+pszPath]
0x1405e8d8c  cmp     qword ptr [rsp+390h+var_330+8], 7
0x1405e8d92  cmova   rax, [rsp+390h+pszPath]
0x1405e8d98  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1405e8d9c  inc     rdx
0x1405e8d9f  cmp     [rax+rdx*2], r14w
0x1405e8da4  jnz     short loc_1405E8D9C
0x1405e8da6  lea     rcx, [rsp+390h+pszPath]; Src
0x1405e8dab  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1405e8db0  lea     rdx, [rsp+390h+pszPath]
0x1405e8db5  cmp     qword ptr [rsp+390h+var_330+8], 7
0x1405e8dbb  cmova   rdx, [rsp+390h+pszPath]; unsigned __int16 *
0x1405e8dc1  lea     r8, [rbp+290h+var_280]; struct _WIN32_FIND_DATAW *
0x1405e8dc5  lea     rcx, [rsp+390h+var_360]; this
0x1405e8dca  call    ?Begin@VmEnumFiles@Vml@@QEAAHPEBGAEAU_WIN32_FIND_DATAW@@@Z; Vml::VmEnumFiles::Begin(ushort const *,_WIN32_FIND_DATAW &)
0x1405e8dcf  test    eax, eax
0x1405e8dd1  jz      loc_1405E8FB4
0x1405e8dd7  mov     r13d, 2Eh ; '.'
0x1405e8ddd  mov     ecx, r13d
0x1405e8de0  movzx   eax, [rbp+290h+var_280.cFileName]
0x1405e8de4  sub     ecx, eax
0x1405e8de6  jnz     short loc_1405E8DF2
0x1405e8de8  movzx   ecx, r14w
0x1405e8dec  movzx   eax, [rbp+290h+var_280.cFileName+2]
0x1405e8df0  sub     ecx, eax
0x1405e8df2  test    ecx, ecx
0x1405e8df4  jz      loc_1405E8F9E
0x1405e8dfa  mov     ecx, r13d
0x1405e8dfd  movzx   eax, [rbp+290h+var_280.cFileName]
0x1405e8e01  sub     ecx, eax
0x1405e8e03  jnz     short loc_1405E8E1A
0x1405e8e05  mov     ecx, r13d
0x1405e8e08  movzx   eax, [rbp+290h+var_280.cFileName+2]
0x1405e8e0c  sub     ecx, eax
0x1405e8e0e  jnz     short loc_1405E8E1A
0x1405e8e10  movzx   ecx, r14w
0x1405e8e14  movzx   eax, [rbp+290h+var_280.cFileName+4]
0x1405e8e18  sub     ecx, eax
0x1405e8e1a  test    ecx, ecx
0x1405e8e1c  jz      loc_1405E8F9E
0x1405e8e22  mov     ecx, r12d
0x1405e8e25  call    VmlIsDebugTraceEnabled
0x1405e8e2a  test    eax, eax
0x1405e8e2c  jz      short loc_1405E8E41
0x1405e8e2e  lea     r8, [rbp+290h+var_280.cFileName]
0x1405e8e32  lea     rdx, aDeletingVsmTem; "Deleting VSM temporary file share \"%ws"...
0x1405e8e39  mov     ecx, r12d
0x1405e8e3c  call    VmlDebugTrace
0x1405e8e41  xor     r8d, r8d; reserved
0x1405e8e44  lea     rdx, [rbp+290h+var_280.cFileName]; netname
0x1405e8e48  xor     ecx, ecx; servername
0x1405e8e4a  call    cs:__imp_NetShareDel
0x1405e8e51  nop     dword ptr [rax+rax+00h]
0x1405e8e56  mov     ebx, eax
0x1405e8e58  test    eax, eax
0x1405e8e5a  jz      short loc_1405E8E8D
0x1405e8e5c  cmp     eax, 906h
0x1405e8e61  jz      short loc_1405E8E8D
0x1405e8e63  mov     ecx, r12d
0x1405e8e66  call    VmlIsDebugTraceEnabled
0x1405e8e6b  test    eax, eax
0x1405e8e6d  jz      short loc_1405E8E8D
0x1405e8e6f  mov     dword ptr [rsp+390h+var_370], ebx
0x1405e8e73  lea     r9, [rbp+290h+var_280.cFileName]
0x1405e8e77  lea     r8, aVmmsvsmfilesha_3; "VmmsVsmFileShareManager::PrepareSelf"
0x1405e8e7e  lea     rdx, aHsFailedToDele_4; "%hs failed to delete file share \"%ws\""...
0x1405e8e85  mov     ecx, r12d
0x1405e8e88  call    VmlDebugTrace
0x1405e8e8d  lea     rdx, [rsp+390h+lpBuffer]
0x1405e8e92  lea     rcx, [rsp+390h+pszPath]
0x1405e8e97  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1405e8e9c  mov     edx, 104h
0x1405e8ea1  lea     rcx, [rsp+390h+pszPath]; Src
0x1405e8ea6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1405e8eab  lea     rcx, [rsp+390h+pszPath]
0x1405e8eb0  cmp     qword ptr [rsp+390h+var_330+8], 7
0x1405e8eb6  cmova   rcx, [rsp+390h+pszPath]; pszPath
0x1405e8ebc  lea     rdx, [rbp+290h+var_280.cFileName]; pszMore
0x1405e8ec0  call    cs:__imp_PathAppendW
0x1405e8ec7  nop     dword ptr [rax+rax+00h]
0x1405e8ecc  test    eax, eax
0x1405e8ece  jz      loc_1405E8F63
0x1405e8ed4  lea     rcx, [rsp+390h+pszPath]
0x1405e8ed9  cmp     qword ptr [rsp+390h+var_330+8], 7
0x1405e8edf  cmova   rcx, [rsp+390h+pszPath]; pszPath
0x1405e8ee5  call    cs:__imp_PathAddBackslashW
0x1405e8eec  nop     dword ptr [rax+rax+00h]
0x1405e8ef1  test    rax, rax
0x1405e8ef4  jz      short loc_1405E8F63
0x1405e8ef6  lea     rax, [rsp+390h+pszPath]
0x1405e8efb  cmp     qword ptr [rsp+390h+var_330+8], 7
0x1405e8f01  cmova   rax, [rsp+390h+pszPath]
0x1405e8f07  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1405e8f0b  inc     rdx
0x1405e8f0e  cmp     [rax+rdx*2], r14w
0x1405e8f13  jnz     short loc_1405E8F0B
0x1405e8f15  lea     rcx, [rsp+390h+pszPath]; Src
0x1405e8f1a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1405e8f1f  mov     ecx, r12d
0x1405e8f22  call    VmlIsDebugTraceEnabled
0x1405e8f27  test    eax, eax
0x1405e8f29  jz      short loc_1405E8F4B
0x1405e8f2b  lea     r8, [rsp+390h+pszPath]
0x1405e8f30  cmp     qword ptr [rsp+390h+var_330+8], 7
0x1405e8f36  cmova   r8, [rsp+390h+pszPath]
0x1405e8f3c  lea     rdx, aDeletingVsmTem_0; "Deleting VSM temporary file share direc"...
0x1405e8f43  mov     ecx, r12d
  ... truncated ...
```
