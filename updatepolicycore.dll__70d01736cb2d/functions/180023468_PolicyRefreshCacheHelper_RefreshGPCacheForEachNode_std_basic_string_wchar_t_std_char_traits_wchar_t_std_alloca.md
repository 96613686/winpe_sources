# PolicyRefreshCacheHelper::RefreshGPCacheForEachNode(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ulong)

- ea: `0x180023468`
- end: `0x1800236b1`
- name: `?RefreshGPCacheForEachNode@PolicyRefreshCacheHelper@@CAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `585`
- prototype: `__int64 __fastcall(WCHAR *lpSubKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800236b8`

## callees

- `0x18000aac0`
- `0x180010260`
- `0x180022788`
- `0x180023468`
- `0x1800258bc`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800235ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800235ce`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180023603`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180023603`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800234fb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800234fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023572`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023572`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002359a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023676`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002359a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023676`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023531`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023531`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002351e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002358f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002351e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002358f`

## string_xrefs

- `0x180023612`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x180023648`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRefreshCacheHelper::RefreshGPCacheForEachNode(WCHAR *lpSubKey)
{
  WCHAR *v1; // rdi
  int GPCacheRegKeyPath; // eax
  unsigned int v3; // ebx
  unsigned __int64 v4; // r9
  __int64 v5; // rdx
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  HKEY v11; // rsi
  DWORD LastError; // ebx
  LSTATUS v13; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-59h]
  _OWORD v16[2]; // [rsp+50h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-9h] BYREF
  HKEY hKeySrc; // [rsp+78h] [rbp-1h] BYREF
  LPCWSTR lpSubKeya[2]; // [rsp+80h] [rbp+7h] BYREF
  __m128i si128; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v1 = lpSubKey;
  hKeySrc = 0;
  hKey = 0;
  *(_OWORD *)lpSubKeya = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKeya[0]) = 0;
  v16[0] = 0;
  v16[1] = si128;
  LOWORD(v16[0]) = 0;
  GPCacheRegKeyPath = PolicyRefreshCacheHelper::GetGPCacheRegKeyPath(lpSubKey);
  v3 = GPCacheRegKeyPath;
  if ( GPCacheRegKeyPath < 0 )
  {
    v4 = (unsigned int)GPCacheRegKeyPath;
    v5 = 280;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
      (const char *)v4,
      dwOptions);
    goto LABEL_30;
  }
  v6 = (const WCHAR *)lpSubKeya;
  if ( si128.m128i_i64[1] > 7uLL )
    v6 = lpSubKeya[0];
  v7 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v6);
  if ( (v7 & 0xFFFFFFFC) == 0 && v7 != 1 )
  {
    hKey = 0;
    v8 = (const WCHAR *)lpSubKeya;
    if ( si128.m128i_i64[1] > 7uLL )
      v8 = lpSubKeya[0];
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v9 )
    {
      v10 = 297;
LABEL_22:
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v10,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
             (const char *)v9,
             dwOptions);
      goto LABEL_30;
    }
    v11 = hKeySrc;
    if ( hKeySrc )
    {
      LastError = GetLastError();
      RegCloseKey(v11);
      SetLastError(LastError);
    }
    hKeySrc = 0;
    if ( *((_QWORD *)v1 + 3) > 7u )
      v1 = *(WCHAR **)v1;
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x20019u, &hKeySrc);
    if ( (unsigned int)(v13 - 2) > 1 )
    {
      if ( v13 )
      {
        v3 = (unsigned __int16)v13 | 0x80070000;
        if ( v13 <= 0 )
          v3 = v13;
        v5 = 302;
        goto LABEL_28;
      }
      v9 = RegCopyTreeW(hKeySrc, 0, hKey);
      if ( v9 )
      {
        v10 = 305;
        goto LABEL_22;
      }
    }
    v3 = 0;
    goto LABEL_30;
  }
  v3 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    v3 = v7;
  if ( (v3 & 0x80000000) != 0 )
  {
    v5 = 286;
LABEL_28:
    v4 = v3;
    goto LABEL_29;
  }
LABEL_30:
  std::wstring::~wstring(v16);
  std::wstring::~wstring(lpSubKeya);
  if ( hKey )
    RegCloseKey(hKey);
  if ( hKeySrc )
    RegCloseKey(hKeySrc);
  return v3;
}

```

## disassembly

```asm
0x180023468  mov     [rsp-8+arg_10], rbx
0x18002346d  push    rbp
0x18002346e  push    rsi
0x18002346f  push    rdi
0x180023470  push    r14
0x180023472  push    r15
0x180023474  lea     rbp, [rsp-37h]
0x180023479  sub     rsp, 0B0h
0x180023480  mov     rax, cs:__security_cookie
0x180023487  xor     rax, rsp
0x18002348a  mov     [rbp+57h+var_30], rax
0x18002348e  mov     rdi, rcx
0x180023491  xor     r14d, r14d
0x180023494  mov     [rbp+57h+hKeySrc], r14
0x180023498  mov     [rbp+57h+hKey], r14
0x18002349c  xorps   xmm0, xmm0
0x18002349f  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x1800234a3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800234ab  movdqu  [rbp+57h+var_40], xmm1
0x1800234b0  mov     word ptr [rbp+57h+lpSubKey], r14w
0x1800234b5  movups  [rbp+57h+var_80], xmm0
0x1800234b9  movdqu  [rbp+57h+var_70], xmm1
0x1800234be  mov     word ptr [rbp+57h+var_80], r14w
0x1800234c3  lea     r9, [rbp+57h+var_80]
0x1800234c7  lea     r8, [rbp+57h+lpSubKey]
0x1800234cb  call    ?GetGPCacheRegKeyPath@PolicyRefreshCacheHelper@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV23@1@Z; PolicyRefreshCacheHelper::GetGPCacheRegKeyPath(std::wstring const &,ulong,std::wstring &,std::wstring &)
0x1800234d0  mov     ebx, eax
0x1800234d2  test    eax, eax
0x1800234d4  jns     short loc_1800234E3
0x1800234d6  mov     r9d, eax
0x1800234d9  mov     edx, 118h
0x1800234de  jmp     loc_180023648
0x1800234e3  lea     rdx, [rbp+57h+lpSubKey]
0x1800234e7  cmp     qword ptr [rbp+57h+var_40+8], 7
0x1800234ec  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800234f1  mov     r15, 0FFFFFFFF80000002h
0x1800234f8  mov     rcx, r15; hKey
0x1800234fb  call    cs:__imp_RegDeleteTreeW
0x180023501  test    eax, 0FFFFFFFCh
0x180023506  jnz     loc_18002362E
0x18002350c  cmp     eax, 1
0x18002350f  jz      loc_18002362E
0x180023515  mov     rsi, [rbp+57h+hKey]
0x180023519  test    rsi, rsi
0x18002351c  jz      short loc_180023537
0x18002351e  call    cs:__imp_GetLastError
0x180023524  mov     ebx, eax
0x180023526  mov     rcx, rsi; hKey
0x180023529  call    cs:__imp_RegCloseKey
0x18002352f  mov     ecx, ebx; dwErrCode
0x180023531  call    cs:__imp_SetLastError
0x180023537  mov     [rbp+57h+hKey], r14
0x18002353b  lea     rdx, [rbp+57h+lpSubKey]
0x18002353f  cmp     qword ptr [rbp+57h+var_40+8], 7
0x180023544  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180023549  mov     [rsp+0D0h+lpdwDisposition], r14; lpdwDisposition
0x18002354e  lea     rax, [rbp+57h+hKey]
0x180023552  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180023557  mov     [rsp+0D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002355c  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x180023564  mov     [rsp+0D0h+dwOptions], r14d; dwOptions
0x180023569  xor     r9d, r9d; lpClass
0x18002356c  xor     r8d, r8d; Reserved
0x18002356f  mov     rcx, r15; hKey
0x180023572  call    cs:__imp_RegCreateKeyExW
0x180023578  test    eax, eax
0x18002357a  jz      short loc_180023586
0x18002357c  mov     edx, 129h
0x180023581  jmp     loc_180023612
0x180023586  mov     rsi, [rbp+57h+hKeySrc]
0x18002358a  test    rsi, rsi
0x18002358d  jz      short loc_1800235A8
0x18002358f  call    cs:__imp_GetLastError
0x180023595  mov     ebx, eax
0x180023597  mov     rcx, rsi; hKey
0x18002359a  call    cs:__imp_RegCloseKey
0x1800235a0  mov     ecx, ebx; dwErrCode
0x1800235a2  call    cs:__imp_SetLastError
0x1800235a8  mov     [rbp+57h+hKeySrc], r14
0x1800235ac  cmp     qword ptr [rdi+18h], 7
0x1800235b1  jbe     short loc_1800235B6
0x1800235b3  mov     rdi, [rdi]
0x1800235b6  lea     rax, [rbp+57h+hKeySrc]
0x1800235ba  mov     qword ptr [rsp+0D0h+dwOptions], rax; unsigned int
0x1800235bf  mov     r9d, 20019h; samDesired
0x1800235c5  xor     r8d, r8d; ulOptions
0x1800235c8  mov     rdx, rdi; lpSubKey
0x1800235cb  mov     rcx, r15; hKey
0x1800235ce  call    cs:__imp_RegOpenKeyExW
0x1800235d4  lea     ecx, [rax-2]
0x1800235d7  cmp     ecx, 1
0x1800235da  jbe     short loc_180023629
0x1800235dc  test    eax, eax
0x1800235de  jz      short loc_1800235F9
0x1800235e0  movzx   ebx, ax
0x1800235e3  or      ebx, 80070000h
0x1800235e9  test    eax, eax
0x1800235eb  cmovle  ebx, eax
0x1800235ee  test    ebx, ebx
0x1800235f0  jns     short loc_180023659
0x1800235f2  mov     edx, 12Eh
0x1800235f7  jmp     short loc_180023645
0x1800235f9  mov     r8, [rbp+57h+hKey]; hKeyDest
0x1800235fd  xor     edx, edx; lpSubKey
0x1800235ff  mov     rcx, [rbp+57h+hKeySrc]; hKeySrc
0x180023603  call    cs:__imp_RegCopyTreeW
0x180023609  test    eax, eax
0x18002360b  jz      short loc_180023629
0x18002360d  mov     edx, 131h; void *
0x180023612  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180023619  mov     r9d, eax; char *
0x18002361c  mov     rcx, [rbp+5Fh]; this
0x180023620  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023625  mov     ebx, eax
0x180023627  jmp     short loc_180023659
0x180023629  mov     ebx, r14d
0x18002362c  jmp     short loc_180023659
0x18002362e  movzx   ebx, ax
0x180023631  or      ebx, 80070000h
0x180023637  test    eax, eax
0x180023639  cmovle  ebx, eax
0x18002363c  test    ebx, ebx
0x18002363e  jns     short loc_180023659
0x180023640  mov     edx, 11Eh; void *
0x180023645  mov     r9d, ebx; char *
0x180023648  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18002364f  mov     rcx, [rbp+5Fh]; this
0x180023653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023658  nop
0x180023659  lea     rcx, [rbp+57h+var_80]; void *
0x18002365d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023662  nop
0x180023663  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180023667  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002366c  nop
0x18002366d  mov     rcx, [rbp+57h+hKey]; hKey
0x180023671  test    rcx, rcx
0x180023674  jz      short loc_18002367D
0x180023676  call    cs:__imp_RegCloseKey
0x18002367c  nop
0x18002367d  mov     rcx, [rbp+57h+hKeySrc]; hKey
0x180023681  test    rcx, rcx
0x180023684  jz      short loc_18002368C
0x180023686  call    cs:__imp_RegCloseKey
0x18002368c  mov     eax, ebx
0x18002368e  mov     rcx, [rbp+57h+var_30]
0x180023692  xor     rcx, rsp; StackCookie
0x180023695  call    __security_check_cookie
0x18002369a  mov     rbx, [rsp+0D0h+arg_10]
0x1800236a2  add     rsp, 0B0h
0x1800236a9  pop     r15
0x1800236ab  pop     r14
0x1800236ad  pop     rdi
0x1800236ae  pop     rsi
0x1800236af  pop     rbp
0x1800236b0  retn
```
