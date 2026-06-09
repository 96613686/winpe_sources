# PolicyRefreshCacheHelper::GenerateHash(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180022fc4`
- end: `0x180023240`
- name: `?GenerateHash@PolicyRefreshCacheHelper@@CAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z`
- size: `636`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023288`
- `0x1800236b8`

## callees

- `0x18000aae4`
- `0x18000fcc4`
- `0x180010260`
- `0x180022fc4`
- `0x180024738`
- `0x1800255f4`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023048`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023035`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800230f7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800230f7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800230aa`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002320a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800230aa`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002320a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180023040`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180023094`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800231f8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180023040`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180023094`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800231f8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002301b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002301b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002306a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002306a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800230d0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800230d0`
- `CRYPT32!CryptBinaryToStringW` at `0x18002312a`
- `CRYPT32!CryptBinaryToStringW` at `0x18002316c`
- `CRYPT32!CryptBinaryToStringW` at `0x18002312a`
- `CRYPT32!CryptBinaryToStringW` at `0x18002316c`

## string_xrefs

- `0x18002307d`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x18002317a`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyRefreshCacheHelper::GenerateHash(_QWORD *a1, __int64 a2)
{
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  const BYTE *v7; // rdx
  WCHAR *v8; // r9
  const char *v9; // r9
  LPWSTR *v10; // rdx
  __int64 v11; // r8
  _OWORD v13[2]; // [rsp+30h] [rbp-59h] BYREF
  DWORD pcchString; // [rsp+50h] [rbp-39h] BYREF
  _QWORD *v15; // [rsp+58h] [rbp-31h]
  HCRYPTHASH hHash; // [rsp+60h] [rbp-29h] BYREF
  HCRYPTPROV phProv; // [rsp+68h] [rbp-21h] BYREF
  DWORD pdwDataLen; // [rsp+70h] [rbp-19h] BYREF
  LPWSTR pszString[3]; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int64 v20; // [rsp+90h] [rbp+7h]
  BYTE pbData[32]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v15 = a1;
  hHash = 0;
  pdwDataLen = 32;
  phProv = 0;
  if ( !CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000040) )
  {
    v5 = 190;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
                  v4);
LABEL_6:
    if ( hHash )
      CryptDestroyHash(hHash);
    if ( phProv )
      CryptReleaseContext(phProv, 0);
    goto LABEL_31;
  }
  hHash = 0;
  if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &hHash) )
  {
    v5 = 192;
    goto LABEL_5;
  }
  v7 = (const BYTE *)a1;
  if ( a1[3] > 7u )
    v7 = (const BYTE *)*a1;
  if ( !CryptHashData(hHash, v7, 2 * *((_DWORD *)a1 + 4), 0) )
  {
    v5 = 195;
    goto LABEL_5;
  }
  if ( !CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
  {
    v5 = 197;
    goto LABEL_5;
  }
  pcchString = 0;
  if ( !CryptBinaryToStringW(pbData, pdwDataLen, 0x40000001u, 0, &pcchString) )
  {
    v5 = 203;
    goto LABEL_5;
  }
  std::wstring::wstring(pszString, pcchString);
  v8 = (WCHAR *)pszString;
  if ( v20 > 7 )
    v8 = pszString[0];
  if ( !CryptBinaryToStringW(pbData, pdwDataLen, 0x40000001u, v8, &pcchString) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCF,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
                  v9);
    std::wstring::~wstring(pszString);
    goto LABEL_6;
  }
  v10 = pszString;
  if ( v20 > 7 )
    v10 = (LPWSTR *)pszString[0];
  memset(v13, 0, sizeof(v13));
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)v10 + v11) );
  std::wstring::_Construct<1,wchar_t const *>(v13);
  std::wstring::operator=(a2, v13);
  std::wstring::~wstring(v13);
  std::wstring::~wstring(pszString);
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  LastError = 0;
LABEL_31:
  std::wstring::~wstring(a1);
  return LastError;
}

```

## disassembly

```asm
0x180022fc4  mov     [rsp-8+arg_10], rbx
0x180022fc9  push    rbp
0x180022fca  push    rsi
0x180022fcb  push    rdi
0x180022fcc  push    r14
0x180022fce  push    r15
0x180022fd0  lea     rbp, [rsp-37h]
0x180022fd5  sub     rsp, 0C0h
0x180022fdc  mov     rax, cs:__security_cookie
0x180022fe3  xor     rax, rsp
0x180022fe6  mov     [rbp+57h+var_28], rax
0x180022fea  mov     r14, rdx
0x180022fed  mov     rdi, rcx
0x180022ff0  mov     [rbp+57h+var_88], rcx
0x180022ff4  xor     r15d, r15d
0x180022ff7  mov     [rbp+57h+hHash], r15
0x180022ffb  mov     [rbp+57h+pdwDataLen], 20h ; ' '
0x180023002  mov     [rbp+57h+phProv], r15
0x180023006  mov     [rsp+0E0h+dwFlags], 0F0000040h; dwFlags
0x18002300e  lea     r9d, [r15+18h]; dwProvType
0x180023012  xor     r8d, r8d; szProvider
0x180023015  xor     edx, edx; szContainer
0x180023017  lea     rcx, [rbp+57h+phProv]; phProv
0x18002301b  call    cs:__imp_CryptAcquireContextW
0x180023021  test    eax, eax
0x180023023  jnz     short loc_18002302C
0x180023025  mov     edx, 0BEh
0x18002302a  jmp     short loc_180023079
0x18002302c  mov     rsi, [rbp+57h+hHash]
0x180023030  test    rsi, rsi
0x180023033  jz      short loc_18002304E
0x180023035  call    cs:__imp_GetLastError
0x18002303b  mov     ebx, eax
0x18002303d  mov     rcx, rsi; hHash
0x180023040  call    cs:__imp_CryptDestroyHash
0x180023046  mov     ecx, ebx; dwErrCode
0x180023048  call    cs:__imp_SetLastError
0x18002304e  mov     [rbp+57h+hHash], r15
0x180023052  lea     rax, [rbp+57h+hHash]
0x180023056  mov     qword ptr [rsp+0E0h+dwFlags], rax; phHash
0x18002305b  xor     r9d, r9d; dwFlags
0x18002305e  xor     r8d, r8d; hKey
0x180023061  mov     edx, 800Ch; Algid
0x180023066  mov     rcx, [rbp+57h+phProv]; hProv
0x18002306a  call    cs:__imp_CryptCreateHash
0x180023070  test    eax, eax
0x180023072  jnz     short loc_1800230B5
0x180023074  mov     edx, 0C0h; void *
0x180023079  mov     rcx, [rbp+5Fh]; this
0x18002307d  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180023084  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023089  mov     ebx, eax
0x18002308b  mov     rcx, [rbp+57h+hHash]; hHash
0x18002308f  test    rcx, rcx
0x180023092  jz      short loc_18002309B
0x180023094  call    cs:__imp_CryptDestroyHash
0x18002309a  nop
0x18002309b  mov     rcx, [rbp+57h+phProv]; hProv
0x18002309f  test    rcx, rcx
0x1800230a2  jz      loc_180023213
0x1800230a8  xor     edx, edx; dwFlags
0x1800230aa  call    cs:__imp_CryptReleaseContext
0x1800230b0  jmp     loc_180023213
0x1800230b5  mov     r8d, [rdi+10h]
0x1800230b9  add     r8d, r8d; dwDataLen
0x1800230bc  mov     rdx, rdi
0x1800230bf  cmp     qword ptr [rdi+18h], 7
0x1800230c4  jbe     short loc_1800230C9
0x1800230c6  mov     rdx, [rdi]; pbData
0x1800230c9  xor     r9d, r9d; dwFlags
0x1800230cc  mov     rcx, [rbp+57h+hHash]; hHash
0x1800230d0  call    cs:__imp_CryptHashData
0x1800230d6  test    eax, eax
0x1800230d8  jnz     short loc_1800230E1
0x1800230da  mov     edx, 0C3h
0x1800230df  jmp     short loc_180023079
0x1800230e1  mov     [rsp+0E0h+dwFlags], r15d; dwFlags
0x1800230e6  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1800230ea  lea     r8, [rbp+57h+pbData]; pbData
0x1800230ee  mov     edx, 2; dwParam
0x1800230f3  mov     rcx, [rbp+57h+hHash]; hHash
0x1800230f7  call    cs:__imp_CryptGetHashParam
0x1800230fd  test    eax, eax
0x1800230ff  jnz     short loc_18002310B
0x180023101  mov     edx, 0C5h
0x180023106  jmp     loc_180023079
0x18002310b  mov     [rbp+57h+pcchString], r15d
0x18002310f  lea     rax, [rbp+57h+pcchString]
0x180023113  mov     qword ptr [rsp+0E0h+dwFlags], rax; pcchString
0x180023118  xor     r9d, r9d; pszString
0x18002311b  mov     ebx, 40000001h
0x180023120  mov     r8d, ebx; dwFlags
0x180023123  mov     edx, [rbp+57h+pdwDataLen]; cbBinary
0x180023126  lea     rcx, [rbp+57h+pbData]; pbBinary
0x18002312a  call    cs:__imp_CryptBinaryToStringW
0x180023130  test    eax, eax
0x180023132  jnz     short loc_18002313E
0x180023134  mov     edx, 0CBh
0x180023139  jmp     loc_180023079
0x18002313e  mov     edx, [rbp+57h+pcchString]
0x180023141  lea     rcx, [rbp+57h+pszString]
0x180023145  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18002314a  nop
0x18002314b  lea     r9, [rbp+57h+pszString]
0x18002314f  cmp     [rbp+57h+var_50], 7
0x180023154  cmova   r9, [rbp+57h+pszString]; pszString
0x180023159  lea     rax, [rbp+57h+pcchString]
0x18002315d  mov     qword ptr [rsp+0E0h+dwFlags], rax; pcchString
0x180023162  mov     r8d, ebx; dwFlags
0x180023165  mov     edx, [rbp+57h+pdwDataLen]; cbBinary
0x180023168  lea     rcx, [rbp+57h+pbData]; pbBinary
0x18002316c  call    cs:__imp_CryptBinaryToStringW
0x180023172  test    eax, eax
0x180023174  jnz     short loc_18002319B
0x180023176  mov     rcx, [rbp+5Fh]; this
0x18002317a  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180023181  mov     edx, 0CFh; void *
0x180023186  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002318b  mov     ebx, eax
0x18002318d  lea     rcx, [rbp+57h+pszString]; void *
0x180023191  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023196  jmp     loc_18002308B
0x18002319b  lea     rdx, [rbp+57h+pszString]
0x18002319f  cmp     [rbp+57h+var_50], 7
0x1800231a4  cmova   rdx, [rbp+57h+pszString]
0x1800231a9  xorps   xmm0, xmm0
0x1800231ac  movups  [rbp+57h+var_B0], xmm0
0x1800231b0  xorps   xmm1, xmm1
0x1800231b3  movdqu  [rbp+57h+var_A0], xmm1
0x1800231b8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800231bc  inc     r8
0x1800231bf  cmp     [rdx+r8*2], r15w
0x1800231c4  jnz     short loc_1800231BC
0x1800231c6  lea     rcx, [rbp+57h+var_B0]
0x1800231ca  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800231cf  lea     rdx, [rbp+57h+var_B0]
0x1800231d3  mov     rcx, r14
0x1800231d6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800231db  lea     rcx, [rbp+57h+var_B0]; void *
0x1800231df  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800231e4  nop
0x1800231e5  lea     rcx, [rbp+57h+pszString]; void *
0x1800231e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800231ee  nop
0x1800231ef  mov     rcx, [rbp+57h+hHash]; hHash
0x1800231f3  test    rcx, rcx
0x1800231f6  jz      short loc_1800231FF
0x1800231f8  call    cs:__imp_CryptDestroyHash
0x1800231fe  nop
0x1800231ff  mov     rcx, [rbp+57h+phProv]; hProv
0x180023203  test    rcx, rcx
0x180023206  jz      short loc_180023210
0x180023208  xor     edx, edx; dwFlags
0x18002320a  call    cs:__imp_CryptReleaseContext
0x180023210  mov     ebx, r15d
0x180023213  mov     rcx, rdi; void *
0x180023216  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002321b  mov     eax, ebx
0x18002321d  mov     rcx, [rbp+57h+var_28]
0x180023221  xor     rcx, rsp; StackCookie
0x180023224  call    __security_check_cookie
0x180023229  mov     rbx, [rsp+0E0h+arg_10]
0x180023231  add     rsp, 0C0h
0x180023238  pop     r15
0x18002323a  pop     r14
0x18002323c  pop     rdi
0x18002323d  pop     rsi
0x18002323e  pop     rbp
0x18002323f  retn
```
