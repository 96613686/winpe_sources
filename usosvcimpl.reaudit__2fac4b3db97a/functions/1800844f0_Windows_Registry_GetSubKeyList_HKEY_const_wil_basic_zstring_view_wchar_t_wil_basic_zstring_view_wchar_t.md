# Windows::Registry::GetSubKeyList(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x1800844f0`
- end: `0x180084769`
- name: `?GetSubKeyList@Registry@Windows@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18006e890`

## callees

- `0x1800108b4`
- `0x180010e80`
- `0x180011680`
- `0x1800631ec`
- `0x1800638e4`
- `0x180081458`
- `0x180083c20`
- `0x1800844f0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800845e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800845e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084707`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084707`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084595`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084595`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008465c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008465c`

## string_xrefs

- `0x180084742`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180084757`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Registry::GetSubKeyList(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4, _OWORD *a5)
{
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  DWORD v8; // edi
  __m128i si128; // xmm6
  unsigned int v10; // eax
  __int64 v11; // r8
  _OWORD *v12; // rdx
  unsigned int phkResult; // [rsp+28h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+28h] [rbp-E0h]
  _QWORD v16[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i v17; // [rsp+88h] [rbp-80h]
  __int64 v18; // [rsp+98h] [rbp-70h]
  DWORD cbMaxSubKeyLen; // [rsp+A0h] [rbp-68h] BYREF
  DWORD cSubKeys; // [rsp+A4h] [rbp-64h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-60h] BYREF
  DWORD cchName; // [rsp+B0h] [rbp-58h] BYREF
  LPWSTR lpName[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v24; // [rsp+C8h] [rbp-40h]
  LPCWSTR lpSubKey[4]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+28h]

  v18 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_OWORD *)&v16[1] = *a5;
  *(_OWORD *)lpName = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, lpName, &v16[1]);
  hKey = 0;
  v6 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v6 = lpSubKey[0];
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey) )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)v7,
        phkResult);
    if ( cSubKeys )
    {
      ++cbMaxSubKeyLen;
      *(_OWORD *)lpName = 0;
      v24 = 0;
      std::vector<wchar_t>::vector<wchar_t>(lpName, cbMaxSubKeyLen);
      v8 = 0;
      if ( cSubKeys )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        do
        {
          cchName = cbMaxSubKeyLen;
          v10 = RegEnumKeyExW(hKey, v8, lpName[0], &cchName, 0, 0, 0, 0);
          if ( v10 == 259 )
            break;
          if ( v10 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x1DD,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
              (const char *)v10,
              phkResulta);
          *(_OWORD *)&v16[1] = 0;
          v17 = 0;
          v11 = -1;
          do
            ++v11;
          while ( lpName[0][v11] );
          std::wstring::_Construct<1,wchar_t const *>(&v16[1], lpName[0], v11);
          v12 = *(_OWORD **)(a2 + 8);
          if ( v12 == *(_OWORD **)(a2 + 16) )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a2, v12, &v16[1]);
          }
          else
          {
            *v12 = *(_OWORD *)&v16[1];
            v12[1] = v17;
            v17 = si128;
            LOWORD(v16[1]) = 0;
            *(_QWORD *)(a2 + 8) += 32LL;
          }
          std::wstring::~wstring(&v16[1]);
          ++v8;
        }
        while ( v8 < cSubKeys );
      }
      std::vector<wchar_t>::~vector<wchar_t>(lpName);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
  return a2;
}

```

## disassembly

```asm
0x1800844f0  mov     rax, rsp
0x1800844f3  mov     [rax+8], rbx
0x1800844f7  push    rbp
0x1800844f8  push    rsi
0x1800844f9  push    rdi
0x1800844fa  lea     rbp, [rax-28h]
0x1800844fe  sub     rsp, 110h
0x180084505  movaps  xmmword ptr [rax-28h], xmm6
0x180084509  mov     rax, cs:__security_cookie
0x180084510  xor     rax, rsp
0x180084513  mov     [rbp+20h+var_30], rax
0x180084517  mov     rbx, rdx
0x18008451a  mov     [rbp+20h+var_90], rdx
0x18008451e  mov     rax, [rbp+20h+arg_20]
0x180084522  mov     [rsp+120h+var_C0], 1
0x18008452a  xorps   xmm0, xmm0
0x18008452d  movups  xmmword ptr [rdx], xmm0
0x180084530  xor     esi, esi
0x180084532  mov     [rdx], rsi
0x180084535  mov     [rdx+8], rsi
0x180084539  mov     [rdx+10h], rsi
0x18008453d  mov     [rsp+120h+var_C0], 1
0x180084545  movaps  xmm0, xmmword ptr [rax]
0x180084548  movdqa  xmmword ptr [rsp+120h+var_B8+8], xmm0
0x18008454e  movaps  xmm1, xmmword ptr [r9]
0x180084552  movdqa  xmmword ptr [rbp+20h+lpName], xmm1
0x180084557  lea     r9, [rsp+120h+var_B8+8]
0x18008455c  lea     r8, [rbp+20h+lpName]
0x180084560  lea     rdx, [rbp+20h+lpSubKey]
0x180084564  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180084569  nop
0x18008456a  mov     [rbp+20h+hKey], rsi
0x18008456e  lea     rdx, [rbp+20h+lpSubKey]
0x180084572  cmp     [rbp+20h+var_38], 7
0x180084577  cmova   rdx, [rbp+20h+lpSubKey]; lpSubKey
0x18008457c  lea     rax, [rbp+20h+hKey]
0x180084580  mov     [rsp+120h+phkResult], rax; phkResult
0x180084585  mov     r9d, 20019h; samDesired
0x18008458b  xor     r8d, r8d; ulOptions
0x18008458e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084595  call    cs:__imp_RegOpenKeyExW
0x18008459b  test    eax, eax
0x18008459d  jnz     loc_1800846FE
0x1800845a3  mov     [rbp+20h+cSubKeys], esi
0x1800845a6  mov     [rbp+20h+cbMaxSubKeyLen], esi
0x1800845a9  mov     [rsp+120h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800845ae  mov     [rsp+120h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800845b3  mov     [rsp+120h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800845b8  mov     [rsp+120h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1800845bd  mov     [rsp+120h+lpcValues], rsi; lpcValues
0x1800845c2  mov     [rsp+120h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800845c7  lea     rax, [rbp+20h+cbMaxSubKeyLen]
0x1800845cb  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800845d0  lea     rax, [rbp+20h+cSubKeys]
0x1800845d4  mov     [rsp+120h+phkResult], rax; unsigned int
0x1800845d9  xor     r9d, r9d; lpReserved
0x1800845dc  xor     r8d, r8d; lpcchClass
0x1800845df  xor     edx, edx; lpClass
0x1800845e1  mov     rcx, [rbp+20h+hKey]; hKey
0x1800845e5  call    cs:__imp_RegQueryInfoKeyW
0x1800845eb  mov     rcx, [rbp+28h]; this
0x1800845ef  test    eax, eax
0x1800845f1  jnz     loc_18008473F
0x1800845f7  cmp     [rbp+20h+cSubKeys], esi
0x1800845fa  jbe     loc_1800846FE
0x180084600  mov     eax, [rbp+20h+cbMaxSubKeyLen]
0x180084603  inc     eax
0x180084605  mov     [rbp+20h+cbMaxSubKeyLen], eax
0x180084608  mov     edx, eax
0x18008460a  xorps   xmm0, xmm0
0x18008460d  xor     eax, eax
0x18008460f  movups  xmmword ptr [rbp+20h+lpName], xmm0
0x180084613  mov     [rbp+20h+var_60], rax
0x180084617  lea     rcx, [rbp+20h+lpName]
0x18008461b  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180084620  nop
0x180084621  mov     edi, esi
0x180084623  cmp     [rbp+20h+cSubKeys], esi
0x180084626  jbe     loc_1800846F4
0x18008462c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180084634  mov     eax, [rbp+20h+cbMaxSubKeyLen]
0x180084637  mov     [rbp+20h+cchName], eax
0x18008463a  mov     [rsp+120h+lpcValues], rsi; lpftLastWriteTime
0x18008463f  mov     [rsp+120h+lpcbMaxClassLen], rsi; lpcchClass
0x180084644  mov     [rsp+120h+lpcbMaxSubKeyLen], rsi; lpClass
0x180084649  mov     [rsp+120h+phkResult], rsi; unsigned int
0x18008464e  lea     r9, [rbp+20h+cchName]; lpcchName
0x180084652  mov     r8, [rbp+20h+lpName]; lpName
0x180084656  mov     edx, edi; dwIndex
0x180084658  mov     rcx, [rbp+20h+hKey]; hKey
0x18008465c  call    cs:__imp_RegEnumKeyExW
0x180084662  cmp     eax, 103h
0x180084667  jz      loc_1800846F4
0x18008466d  mov     rcx, [rbp+28h]; this
0x180084671  test    eax, eax
0x180084673  jnz     loc_180084754
0x180084679  xorps   xmm0, xmm0
0x18008467c  movups  xmmword ptr [rsp+120h+var_B8+8], xmm0
0x180084681  xorps   xmm1, xmm1
0x180084684  movdqu  [rbp+20h+var_A0], xmm1
0x180084689  mov     rdx, [rbp+20h+lpName]
0x18008468d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180084691  inc     r8
0x180084694  cmp     [rdx+r8*2], si
0x180084699  jnz     short loc_180084691
0x18008469b  lea     rcx, [rsp+120h+var_B8+8]
0x1800846a0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800846a5  nop
0x1800846a6  mov     rdx, [rbx+8]
0x1800846aa  cmp     rdx, [rbx+10h]
0x1800846ae  jz      short loc_1800846D1
0x1800846b0  movups  xmm0, xmmword ptr [rsp+120h+var_B8+8]
0x1800846b5  movups  xmmword ptr [rdx], xmm0
0x1800846b8  movups  xmm1, [rbp+20h+var_A0]
0x1800846bc  movups  xmmword ptr [rdx+10h], xmm1
0x1800846c0  movdqu  [rbp+20h+var_A0], xmm6
0x1800846c5  mov     word ptr [rsp+120h+var_B8+8], si
0x1800846ca  add     qword ptr [rbx+8], 20h ; ' '
0x1800846cf  jmp     short loc_1800846DF
0x1800846d1  lea     r8, [rsp+120h+var_B8+8]
0x1800846d6  mov     rcx, rbx
0x1800846d9  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800846de  nop
0x1800846df  lea     rcx, [rsp+120h+var_B8+8]; void *
0x1800846e4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800846e9  inc     edi
0x1800846eb  cmp     edi, [rbp+20h+cSubKeys]
0x1800846ee  jb      loc_180084634
0x1800846f4  lea     rcx, [rbp+20h+lpName]
0x1800846f8  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1800846fd  nop
0x1800846fe  mov     rcx, [rbp+20h+hKey]; hKey
0x180084702  test    rcx, rcx
0x180084705  jz      short loc_18008470E
0x180084707  call    cs:__imp_RegCloseKey
0x18008470d  nop
0x18008470e  lea     rcx, [rbp+20h+lpSubKey]; void *
0x180084712  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084717  nop
0x180084718  mov     rax, rbx
0x18008471b  mov     rcx, [rbp+20h+var_30]
0x18008471f  xor     rcx, rsp; StackCookie
0x180084722  call    __security_check_cookie
0x180084727  lea     r11, [rsp+120h+var_10]
0x18008472f  mov     rbx, [r11+20h]
0x180084733  movaps  xmm6, xmmword ptr [r11-10h]
0x180084738  mov     rsp, r11
0x18008473b  pop     rdi
0x18008473c  pop     rsi
0x18008473d  pop     rbp
0x18008473e  retn
0x18008473f  mov     r9d, eax; char *
0x180084742  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180084749  mov     edx, 1CCh; void *
0x18008474e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180084754  mov     r9d, eax; char *
0x180084757  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18008475e  mov     edx, 1DDh; void *
0x180084763  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
