# RemoveExpiredCallbackInfo(void)

- ea: `0x1801307a8`
- end: `0x180130a50`
- name: `?RemoveExpiredCallbackInfo@@YAXXZ`
- size: `680`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002e158`

## callees

- `0x18012de38`
- `0x1801307a8`
- `0x180131a30`
- `0x180132004`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801307fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801308dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130a06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130a22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801307fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801308dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130a06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130a22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013082e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130907`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013082e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130907`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180130876`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801309ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180130876`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801309ee`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1801308c5`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180130954`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1801308c5`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180130954`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801309a4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801309a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801307ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801307ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void RemoveExpiredCallbackInfo(void)
{
  __int64 v0; // rdx
  __int64 v1; // r8
  wchar_t **v2; // r9
  const WCHAR *RegKeyPath; // rax
  DWORD v4; // edi
  DWORD v5; // ebx
  LSTATUS v6; // eax
  int v7; // r8d
  HKEY phkResult; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cSubKeys[2]; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-90h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-88h] BYREF
  struct _FILETIME v12; // [rsp+88h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+2A8h] [rbp+1A0h] BYREF

  hKey = 0;
  cSubKeys[1] = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  RegKeyPath = (const WCHAR *)GetRegKeyPath(23, v0, v1, v2);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegKeyPath, 0, 0x20019u, &hKey)
    && !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys[1], 0, 0, 0, 0, 0, 0, 0)
    && cSubKeys[1] )
  {
    v4 = 0;
    do
    {
      memset(Name, 0, 0x208u);
      phkResult = 0;
      cSubKeys[0] = 0;
      v5 = 0;
      if ( !RegEnumKeyW(hKey, v4, Name, 0x104u) )
      {
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
        {
          while ( !RegQueryInfoKeyW(phkResult, 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
          {
            if ( !cSubKeys[0] )
              break;
            if ( v5 == cSubKeys[0] )
              break;
            memset(SubKey, 0, 0x208u);
            v12 = 0;
            v6 = RegEnumKeyW(phkResult, v5, SubKey, 0x104u);
            if ( v6 == 259 )
              break;
            if ( v6
              || (int)RegQueryFileTimeValue(phkResult, SubKey, L"LastRefreshTime", &v12) >= 0
              && (unsigned int)TimeDiff(&v12, &SystemTimeAsFileTime, v7) < 0xED4E00
              || RegDeleteKeyW(phkResult, SubKey) )
            {
              ++v5;
            }
            else
            {
              v5 = 0;
            }
          }
        }
      }
      if ( phkResult )
        RegCloseKey(phkResult);
      ++v4;
    }
    while ( v4 < cSubKeys[1] );
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1801307a8  mov     rax, rsp
0x1801307ab  mov     [rax+8], rbx
0x1801307af  mov     [rax+10h], rsi
0x1801307b3  mov     [rax+18h], rdi
0x1801307b7  push    rbp
0x1801307b8  lea     rbp, [rax-3C8h]
0x1801307bf  sub     rsp, 4C0h
0x1801307c6  mov     rax, cs:__security_cookie
0x1801307cd  xor     rax, rsp
0x1801307d0  mov     [rbp+3C0h+var_10], rax
0x1801307d7  xor     esi, esi
0x1801307d9  mov     [rsp+4C0h+hKey], rsi
0x1801307de  mov     [rsp+4C0h+cSubKeys+4], esi
0x1801307e2  mov     qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1801307e7  lea     rcx, [rsp+4C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801307ec  call    cs:__imp_GetSystemTimeAsFileTime
0x1801307f2  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1801307f7  test    rcx, rcx
0x1801307fa  jz      short loc_180130807
0x1801307fc  call    cs:__imp_RegCloseKey
0x180130802  mov     [rsp+4C0h+hKey], rsi
0x180130807  mov     ecx, 17h
0x18013080c  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x180130811  lea     rcx, [rsp+4C0h+hKey]
0x180130816  mov     [rsp+4C0h+phkResult], rcx; phkResult
0x18013081b  mov     r9d, 20019h; samDesired
0x180130821  xor     r8d, r8d; ulOptions
0x180130824  mov     rdx, rax; lpSubKey
0x180130827  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013082e  call    cs:__imp_RegOpenKeyExW
0x180130834  test    eax, eax
0x180130836  jnz     loc_180130A18
0x18013083c  mov     [rsp+4C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180130841  mov     [rsp+4C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180130846  mov     [rsp+4C0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18013084b  mov     [rsp+4C0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180130850  mov     [rsp+4C0h+lpcValues], rsi; lpcValues
0x180130855  mov     [rsp+4C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18013085a  mov     [rsp+4C0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18013085f  lea     rax, [rsp+4C0h+cSubKeys+4]
0x180130864  mov     [rsp+4C0h+phkResult], rax; lpcSubKeys
0x180130869  xor     r9d, r9d; lpReserved
0x18013086c  xor     r8d, r8d; lpcchClass
0x18013086f  xor     edx, edx; lpClass
0x180130871  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180130876  call    cs:__imp_RegQueryInfoKeyW
0x18013087c  test    eax, eax
0x18013087e  jnz     loc_180130A18
0x180130884  mov     eax, [rsp+4C0h+cSubKeys+4]
0x180130888  test    eax, eax
0x18013088a  jz      loc_180130A18
0x180130890  mov     edi, esi
0x180130892  xor     edx, edx; Val
0x180130894  mov     r8d, 208h; Size
0x18013089a  lea     rcx, [rbp+3C0h+Name]; void *
0x1801308a1  call    memset
0x1801308a6  mov     [rsp+4C0h+var_460], rsi
0x1801308ab  mov     [rsp+4C0h+cSubKeys], esi
0x1801308af  mov     ebx, esi
0x1801308b1  mov     r9d, 104h; cchName
0x1801308b7  lea     r8, [rbp+3C0h+Name]; lpName
0x1801308be  mov     edx, edi; dwIndex
0x1801308c0  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1801308c5  call    cs:__imp_RegEnumKeyW
0x1801308cb  test    eax, eax
0x1801308cd  jnz     loc_1801309FC
0x1801308d3  mov     rcx, [rsp+4C0h+var_460]; hKey
0x1801308d8  test    rcx, rcx
0x1801308db  jz      short loc_1801308E8
0x1801308dd  call    cs:__imp_RegCloseKey
0x1801308e3  mov     [rsp+4C0h+var_460], rsi
0x1801308e8  lea     rax, [rsp+4C0h+var_460]
0x1801308ed  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1801308f2  mov     r9d, 20019h; samDesired
0x1801308f8  xor     r8d, r8d; ulOptions
0x1801308fb  lea     rdx, [rbp+3C0h+Name]; lpSubKey
0x180130902  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180130907  call    cs:__imp_RegOpenKeyExW
0x18013090d  test    eax, eax
0x18013090f  jnz     loc_1801309FC
0x180130915  jmp     loc_1801309B4
0x18013091a  mov     eax, [rsp+4C0h+cSubKeys]
0x18013091e  test    eax, eax
0x180130920  jz      loc_1801309FC
0x180130926  cmp     ebx, eax
0x180130928  jz      loc_1801309FC
0x18013092e  xor     edx, edx; Val
0x180130930  mov     r8d, 208h; Size
0x180130936  lea     rcx, [rbp+3C0h+SubKey]; void *
0x18013093a  call    memset
0x18013093f  mov     qword ptr [rbp+3C0h+var_440.dwLowDateTime], rsi
0x180130943  mov     r9d, 104h; cchName
0x180130949  lea     r8, [rbp+3C0h+SubKey]; lpName
0x18013094d  mov     edx, ebx; dwIndex
0x18013094f  mov     rcx, [rsp+4C0h+var_460]; hKey
0x180130954  call    cs:__imp_RegEnumKeyW
0x18013095a  cmp     eax, 103h
0x18013095f  jz      loc_1801309FC
0x180130965  test    eax, eax
0x180130967  jnz     short loc_1801309B2
0x180130969  lea     r9, [rbp+3C0h+var_440]
0x18013096d  lea     r8, aLastrefreshtim; "LastRefreshTime"
0x180130974  lea     rdx, [rbp+3C0h+SubKey]
0x180130978  mov     rcx, [rsp+4C0h+var_460]
0x18013097d  call    ?RegQueryFileTimeValue@@YAJPEAUHKEY__@@PEB_W1PEAU_FILETIME@@W4RegistryHiveType@@@Z; RegQueryFileTimeValue(HKEY__ *,wchar_t const *,wchar_t const *,_FILETIME *,RegistryHiveType)
0x180130982  test    eax, eax
0x180130984  js      short loc_18013099B
0x180130986  lea     rdx, [rsp+4C0h+SystemTimeAsFileTime]; struct _FILETIME *
0x18013098b  lea     rcx, [rbp+3C0h+var_440]; struct _FILETIME *
0x18013098f  call    ?TimeDiff@@YAHAEBU_FILETIME@@0H@Z; TimeDiff(_FILETIME const &,_FILETIME const &,int)
0x180130994  cmp     eax, 0ED4E00h
0x180130999  jb      short loc_1801309B2
0x18013099b  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x18013099f  mov     rcx, [rsp+4C0h+var_460]; hKey
0x1801309a4  call    cs:__imp_RegDeleteKeyW
0x1801309aa  test    eax, eax
0x1801309ac  jnz     short loc_1801309B2
0x1801309ae  mov     ebx, esi
0x1801309b0  jmp     short loc_1801309B4
0x1801309b2  inc     ebx
0x1801309b4  mov     [rsp+4C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1801309b9  mov     [rsp+4C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1801309be  mov     [rsp+4C0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1801309c3  mov     [rsp+4C0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1801309c8  mov     [rsp+4C0h+lpcValues], rsi; lpcValues
0x1801309cd  mov     [rsp+4C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1801309d2  mov     [rsp+4C0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1801309d7  lea     rax, [rsp+4C0h+cSubKeys]
0x1801309dc  mov     [rsp+4C0h+phkResult], rax; lpcSubKeys
0x1801309e1  xor     r9d, r9d; lpReserved
0x1801309e4  xor     r8d, r8d; lpcchClass
0x1801309e7  xor     edx, edx; lpClass
0x1801309e9  mov     rcx, [rsp+4C0h+var_460]; hKey
0x1801309ee  call    cs:__imp_RegQueryInfoKeyW
0x1801309f4  test    eax, eax
0x1801309f6  jz      loc_18013091A
0x1801309fc  mov     rcx, [rsp+4C0h+var_460]; hKey
0x180130a01  test    rcx, rcx
0x180130a04  jz      short loc_180130A0C
0x180130a06  call    cs:__imp_RegCloseKey
0x180130a0c  inc     edi
0x180130a0e  cmp     edi, [rsp+4C0h+cSubKeys+4]
0x180130a12  jb      loc_180130892
0x180130a18  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180130a1d  test    rcx, rcx
0x180130a20  jz      short loc_180130A28
0x180130a22  call    cs:__imp_RegCloseKey
0x180130a28  mov     rcx, [rbp+3C0h+var_10]
0x180130a2f  xor     rcx, rsp; StackCookie
0x180130a32  call    __security_check_cookie
0x180130a37  lea     r11, [rsp+4C0h+var_s0]
0x180130a3f  mov     rbx, [r11+10h]
0x180130a43  mov     rsi, [r11+18h]
0x180130a47  mov     rdi, [r11+20h]
0x180130a4b  mov     rsp, r11
0x180130a4e  pop     rbp
0x180130a4f  retn
```
