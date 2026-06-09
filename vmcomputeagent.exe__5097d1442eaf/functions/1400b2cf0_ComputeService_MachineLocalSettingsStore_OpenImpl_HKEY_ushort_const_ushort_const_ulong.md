# ComputeService::MachineLocalSettingsStore::OpenImpl(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x1400b2cf0`
- end: `0x1400b2ef9`
- name: `?OpenImpl@MachineLocalSettingsStore@ComputeService@@IEAA_NPEAUHKEY__@@PEBG1K@Z`
- size: `521`
- prototype: `bool(ComputeService::MachineLocalSettingsStore *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `10`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000b4d0`
- `0x14000b4fc`
- `0x140030c28`
- `0x1400314e0`
- `0x1400403ec`
- `0x140063e10`
- `0x1400b1070`
- `0x1400b10a0`
- `0x1400ba68c`
- `0x1400bb0e4`

## callees

- `0x140005360`
- `0x140008760`
- `0x14001e4f4`
- `0x140030078`
- `0x1400341ac`
- `0x140044afc`
- `0x1400b2cf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400b2e03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400b2e64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400b2e03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400b2e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b2df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b2e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b2df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b2e51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b2dfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b2e5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b2e8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b2ed6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b2dfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b2e5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b2e8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b2ed6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400b2e2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400b2e2e`

## string_xrefs

- `0x1400b2ee7`: `onecore\vm\compute\management\shared\compute\machinelocalsettingsstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ComputeService::MachineLocalSettingsStore::OpenImpl(
        ComputeService::MachineLocalSettingsStore *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        REGSAM samDesired)
{
  const WCHAR *v6; // rax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r8
  LPCWSTR *v11; // rax
  __int128 *v12; // rax
  HKEY v13; // rdi
  DWORD LastError; // ebx
  const WCHAR *v15; // rdx
  unsigned int v16; // eax
  HKEY *v17; // rdi
  HKEY v18; // r14
  HKEY v19; // rsi
  DWORD v20; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h]
  unsigned __int64 v26; // [rsp+50h] [rbp-30h]
  __int128 v27; // [rsp+58h] [rbp-28h] BYREF
  __int64 v28; // [rsp+68h] [rbp-18h]
  unsigned __int64 v29; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v6 = a3;
  hKey = 0;
  if ( !a3 )
    v6 = &szPassword;
  *(_OWORD *)lpSubKey = 0;
  v25 = 0;
  v26 = 0;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v6[v10] );
  std::wstring::_Construct<1,unsigned short const *>((__int64)lpSubKey, v6, v10);
  if ( !a4 )
    a4 = &szPassword;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  do
    ++v9;
  while ( a4[v9] );
  std::wstring::_Construct<1,unsigned short const *>((__int64)&v27, a4, v9);
  if ( v28 && v25 )
  {
    v11 = lpSubKey;
    if ( v26 > 7 )
      v11 = (LPCWSTR *)lpSubKey[0];
    if ( *((_WORD *)v11 + v25 - 1) != 92 )
    {
      v12 = &v27;
      if ( v29 > 7 )
        v12 = (__int128 *)v27;
      if ( *(_WORD *)v12 != 92 )
        std::wstring::operator+=(lpSubKey, L"\\");
    }
  }
  std::wstring::append(lpSubKey);
  v13 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v13);
    SetLastError(LastError);
  }
  hKey = 0;
  v15 = (const WCHAR *)lpSubKey;
  if ( v26 > 7 )
    v15 = lpSubKey[0];
  v16 = RegOpenKeyExW(a2, v15, 0, samDesired, &hKey);
  if ( v16 )
  {
    if ( v16 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\machinelocalsettingsstore.cpp",
        (const char *)v16,
        phkResult);
    std::wstring::~wstring(&v27);
    std::wstring::~wstring(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v17 = (HKEY *)((char *)this + 8);
    if ( (HKEY *)((char *)this + 8) != &hKey )
    {
      v18 = hKey;
      v19 = *v17;
      if ( *v17 )
      {
        v20 = GetLastError();
        RegCloseKey(v19);
        SetLastError(v20);
      }
      *v17 = v18;
      hKey = 0;
    }
    std::wstring::~wstring(&v27);
    std::wstring::~wstring(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x1400b2cf0  push    rbp
0x1400b2cf2  push    rbx
0x1400b2cf3  push    rsi
0x1400b2cf4  push    rdi
0x1400b2cf5  push    r12
0x1400b2cf7  push    r14
0x1400b2cf9  push    r15
0x1400b2cfb  mov     rbp, rsp
0x1400b2cfe  sub     rsp, 80h
0x1400b2d05  mov     rax, cs:__security_cookie
0x1400b2d0c  xor     rax, rsp
0x1400b2d0f  mov     [rbp+var_8], rax
0x1400b2d13  mov     rdi, r9
0x1400b2d16  mov     rax, r8
0x1400b2d19  mov     r14, rdx
0x1400b2d1c  mov     rsi, rcx
0x1400b2d1f  xor     r15d, r15d
0x1400b2d22  mov     [rbp+hKey], r15
0x1400b2d26  lea     r12, szPassword
0x1400b2d2d  test    r8, r8
0x1400b2d30  cmovz   rax, r12
0x1400b2d34  xorps   xmm0, xmm0
0x1400b2d37  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x1400b2d3b  mov     [rbp+var_38], r15
0x1400b2d3f  mov     [rbp+var_30], r15
0x1400b2d43  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400b2d47  mov     r8, rbx
0x1400b2d4a  inc     r8
0x1400b2d4d  cmp     [rax+r8*2], r15w
0x1400b2d52  jnz     short loc_1400B2D4A
0x1400b2d54  mov     rdx, rax
0x1400b2d57  lea     rcx, [rbp+lpSubKey]
0x1400b2d5b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400b2d60  nop
0x1400b2d61  test    rdi, rdi
0x1400b2d64  cmovz   rdi, r12
0x1400b2d68  xorps   xmm0, xmm0
0x1400b2d6b  movups  [rbp+var_28], xmm0
0x1400b2d6f  mov     [rbp+var_18], r15
0x1400b2d73  mov     [rbp+var_10], r15
0x1400b2d77  inc     rbx
0x1400b2d7a  cmp     [rdi+rbx*2], r15w
0x1400b2d7f  jnz     short loc_1400B2D77
0x1400b2d81  mov     r8, rbx
0x1400b2d84  mov     rdx, rdi
0x1400b2d87  lea     rcx, [rbp+var_28]
0x1400b2d8b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400b2d90  nop
0x1400b2d91  cmp     [rbp+var_18], r15
0x1400b2d95  jz      short loc_1400B2DDA
0x1400b2d97  mov     rcx, [rbp+var_38]
0x1400b2d9b  test    rcx, rcx
0x1400b2d9e  jz      short loc_1400B2DDA
0x1400b2da0  lea     rax, [rbp+lpSubKey]
0x1400b2da4  cmp     [rbp+var_30], 7
0x1400b2da9  cmova   rax, [rbp+lpSubKey]
0x1400b2dae  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400b2db4  jz      short loc_1400B2DDA
0x1400b2db6  lea     rax, [rbp+var_28]
0x1400b2dba  cmp     [rbp+var_10], 7
0x1400b2dbf  cmova   rax, qword ptr [rbp+var_28]
0x1400b2dc4  cmp     word ptr [rax], 5Ch ; '\'
0x1400b2dc8  jz      short loc_1400B2DDA
0x1400b2dca  lea     rdx, asc_1401168B0; "\\"
0x1400b2dd1  lea     rcx, [rbp+lpSubKey]; Src
0x1400b2dd5  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400b2dda  lea     rdx, [rbp+var_28]
0x1400b2dde  lea     rcx, [rbp+lpSubKey]; Src
0x1400b2de2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1400b2de7  mov     rdi, [rbp+hKey]
0x1400b2deb  test    rdi, rdi
0x1400b2dee  jz      short loc_1400B2E09
0x1400b2df0  call    cs:__imp_GetLastError
0x1400b2df6  mov     ebx, eax
0x1400b2df8  mov     rcx, rdi; hKey
0x1400b2dfb  call    cs:__imp_RegCloseKey
0x1400b2e01  mov     ecx, ebx; dwErrCode
0x1400b2e03  call    cs:__imp_SetLastError
0x1400b2e09  mov     [rbp+hKey], r15
0x1400b2e0d  lea     rdx, [rbp+lpSubKey]
0x1400b2e11  cmp     [rbp+var_30], 7
0x1400b2e16  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x1400b2e1b  lea     rax, [rbp+hKey]
0x1400b2e1f  mov     qword ptr [rsp+80h+phkResult], rax; unsigned int
0x1400b2e24  mov     r9d, [rbp+samDesired]; samDesired
0x1400b2e28  xor     r8d, r8d; ulOptions
0x1400b2e2b  mov     rcx, r14; hKey
0x1400b2e2e  call    cs:__imp_RegOpenKeyExW
0x1400b2e34  test    eax, eax
0x1400b2e36  jnz     short loc_1400B2EB4
0x1400b2e38  lea     rdi, [rsi+8]
0x1400b2e3c  lea     rax, [rbp+hKey]
0x1400b2e40  cmp     rdi, rax
0x1400b2e43  jz      short loc_1400B2E71
0x1400b2e45  mov     r14, [rbp+hKey]
0x1400b2e49  mov     rsi, [rdi]
0x1400b2e4c  test    rsi, rsi
0x1400b2e4f  jz      short loc_1400B2E6A
0x1400b2e51  call    cs:__imp_GetLastError
0x1400b2e57  mov     ebx, eax
0x1400b2e59  mov     rcx, rsi; hKey
0x1400b2e5c  call    cs:__imp_RegCloseKey
0x1400b2e62  mov     ecx, ebx; dwErrCode
0x1400b2e64  call    cs:__imp_SetLastError
0x1400b2e6a  mov     [rdi], r14
0x1400b2e6d  mov     [rbp+hKey], r15
0x1400b2e71  lea     rcx, [rbp+var_28]; void *
0x1400b2e75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b2e7a  nop
0x1400b2e7b  lea     rcx, [rbp+lpSubKey]; void *
0x1400b2e7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b2e84  nop
0x1400b2e85  mov     rcx, [rbp+hKey]; hKey
0x1400b2e89  test    rcx, rcx
0x1400b2e8c  jz      short loc_1400B2E94
0x1400b2e8e  call    cs:__imp_RegCloseKey
0x1400b2e94  mov     al, 1
0x1400b2e96  mov     rcx, [rbp+var_8]
0x1400b2e9a  xor     rcx, rsp; StackCookie
0x1400b2e9d  call    __security_check_cookie
0x1400b2ea2  add     rsp, 80h
0x1400b2ea9  pop     r15
0x1400b2eab  pop     r14
0x1400b2ead  pop     r12
0x1400b2eaf  pop     rdi
0x1400b2eb0  pop     rsi
0x1400b2eb1  pop     rbx
0x1400b2eb2  pop     rbp
0x1400b2eb3  retn
0x1400b2eb4  cmp     eax, 2
0x1400b2eb7  jnz     short loc_1400B2EE0
0x1400b2eb9  lea     rcx, [rbp+var_28]; void *
0x1400b2ebd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b2ec2  nop
0x1400b2ec3  lea     rcx, [rbp+lpSubKey]; void *
0x1400b2ec7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b2ecc  nop
0x1400b2ecd  mov     rcx, [rbp+hKey]; hKey
0x1400b2ed1  test    rcx, rcx
0x1400b2ed4  jz      short loc_1400B2EDC
0x1400b2ed6  call    cs:__imp_RegCloseKey
0x1400b2edc  xor     al, al
0x1400b2ede  jmp     short loc_1400B2E96
0x1400b2ee0  mov     rcx, [rbp+38h]; this
0x1400b2ee4  mov     r9d, eax; char *
0x1400b2ee7  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\management\\share"...
0x1400b2eee  mov     edx, 188h; void *
0x1400b2ef3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
