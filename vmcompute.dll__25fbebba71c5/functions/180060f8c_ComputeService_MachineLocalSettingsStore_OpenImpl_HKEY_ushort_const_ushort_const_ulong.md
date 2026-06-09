# ComputeService::MachineLocalSettingsStore::OpenImpl(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180060f8c`
- end: `0x1800611c5`
- name: `?OpenImpl@MachineLocalSettingsStore@ComputeService@@IEAA_NPEAUHKEY__@@PEBG1K@Z`
- size: `569`
- prototype: `bool __fastcall(ComputeService::MachineLocalSettingsStore *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, REGSAM samDesired)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005f080`
- `0x1800607e0`

## callees

- `0x180002f50`
- `0x180006660`
- `0x180014870`
- `0x180022d10`
- `0x180024e74`
- `0x180051e14`
- `0x180060f8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061097`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061118`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061097`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061118`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800610cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800610cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006110a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061148`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006119c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006110a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061148`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006119c`

## string_xrefs

- `0x1800611b3`: `onecore\vm\compute\management\shared\compute\machinelocalsettingsstore.cpp`

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
  unsigned __int64 v7; // r8
  LPCWSTR *v8; // rax
  __int128 *v9; // rax
  HKEY v10; // rdi
  DWORD LastError; // ebx
  const WCHAR *v12; // rdx
  unsigned int v13; // eax
  HKEY *v14; // rdi
  HKEY v15; // r14
  HKEY v16; // rsi
  DWORD v17; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v22; // [rsp+48h] [rbp-38h]
  unsigned __int64 v23; // [rsp+50h] [rbp-30h]
  __int128 v24; // [rsp+58h] [rbp-28h] BYREF
  __int64 v25; // [rsp+68h] [rbp-18h]
  unsigned __int64 v26; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  hKey = 0;
  *(_OWORD *)lpSubKey = 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (__int64)lpSubKey,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\Containers",
    0x46u);
  if ( !a4 )
    a4 = (const unsigned __int16 *)&qword_18008E1B0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a4[v7] );
  std::wstring::_Construct<1,unsigned short const *>((__int64)&v24, a4, v7);
  if ( v25 && v22 )
  {
    v8 = lpSubKey;
    if ( v23 > 7 )
      v8 = (LPCWSTR *)lpSubKey[0];
    if ( *((_WORD *)v8 + v22 - 1) != 92 )
    {
      v9 = &v24;
      if ( v26 > 7 )
        v9 = (__int128 *)v24;
      if ( *(_WORD *)v9 != 92 )
        std::wstring::append(lpSubKey, (void *)L"\\");
    }
  }
  std::wstring::append(lpSubKey);
  v10 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v10);
    SetLastError(LastError);
  }
  hKey = 0;
  v12 = (const WCHAR *)lpSubKey;
  if ( v23 > 7 )
    v12 = lpSubKey[0];
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, samDesired, &hKey);
  if ( v13 )
  {
    if ( v13 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\machinelocalsettingsstore.cpp",
        (const char *)v13,
        phkResult);
    std::wstring::~wstring(&v24);
    std::wstring::~wstring(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v14 = (HKEY *)((char *)this + 8);
    if ( (HKEY *)((char *)this + 8) != &hKey )
    {
      v15 = hKey;
      v16 = *v14;
      if ( *v14 )
      {
        v17 = GetLastError();
        RegCloseKey(v16);
        SetLastError(v17);
      }
      *v14 = v15;
      hKey = 0;
    }
    std::wstring::~wstring(&v24);
    std::wstring::~wstring(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x180060f8c  mov     [rsp-28h+arg_8], rbx
0x180060f91  push    rbp
0x180060f92  push    rsi
0x180060f93  push    rdi
0x180060f94  push    r14
0x180060f96  push    r15
0x180060f98  mov     rbp, rsp
0x180060f9b  sub     rsp, 80h
0x180060fa2  mov     rax, cs:__security_cookie
0x180060fa9  xor     rax, rsp
0x180060fac  mov     [rbp+var_8], rax
0x180060fb0  mov     rbx, r9
0x180060fb3  mov     rsi, rcx
0x180060fb6  xor     r15d, r15d
0x180060fb9  mov     [rbp+hKey], r15
0x180060fbd  xorps   xmm0, xmm0
0x180060fc0  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180060fc4  mov     [rbp+var_38], r15
0x180060fc8  mov     [rbp+var_30], r15
0x180060fcc  lea     r8d, [r15+46h]
0x180060fd0  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180060fd7  lea     rcx, [rbp+lpSubKey]
0x180060fdb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180060fe0  nop
0x180060fe1  lea     rax, qword_18008E1B0
0x180060fe8  test    rbx, rbx
0x180060feb  cmovz   rbx, rax
0x180060fef  xorps   xmm0, xmm0
0x180060ff2  movups  [rbp+var_28], xmm0
0x180060ff6  mov     [rbp+var_18], r15
0x180060ffa  mov     [rbp+var_10], r15
0x180060ffe  or      r8, 0FFFFFFFFFFFFFFFFh
0x180061002  inc     r8
0x180061005  cmp     [rbx+r8*2], r15w
0x18006100a  jnz     short loc_180061002
0x18006100c  mov     rdx, rbx
0x18006100f  lea     rcx, [rbp+var_28]
0x180061013  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180061018  nop
0x180061019  cmp     [rbp+var_18], r15
0x18006101d  jz      short loc_180061062
0x18006101f  mov     rcx, [rbp+var_38]
0x180061023  test    rcx, rcx
0x180061026  jz      short loc_180061062
0x180061028  lea     rax, [rbp+lpSubKey]
0x18006102c  cmp     [rbp+var_30], 7
0x180061031  cmova   rax, [rbp+lpSubKey]
0x180061036  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18006103c  jz      short loc_180061062
0x18006103e  lea     rax, [rbp+var_28]
0x180061042  cmp     [rbp+var_10], 7
0x180061047  cmova   rax, qword ptr [rbp+var_28]
0x18006104c  cmp     word ptr [rax], 5Ch ; '\'
0x180061050  jz      short loc_180061062
0x180061052  lea     rdx, asc_18008E17C; "\\"
0x180061059  lea     rcx, [rbp+lpSubKey]; Src
0x18006105d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180061062  lea     rdx, [rbp+var_28]
0x180061066  lea     rcx, [rbp+lpSubKey]; Src
0x18006106a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18006106f  mov     rdi, [rbp+hKey]
0x180061073  test    rdi, rdi
0x180061076  jz      short loc_1800610A3
0x180061078  call    cs:__imp_GetLastError
0x18006107f  nop     dword ptr [rax+rax+00h]
0x180061084  mov     ebx, eax
0x180061086  mov     rcx, rdi; hKey
0x180061089  call    cs:__imp_RegCloseKey
0x180061090  nop     dword ptr [rax+rax+00h]
0x180061095  mov     ecx, ebx; dwErrCode
0x180061097  call    cs:__imp_SetLastError
0x18006109e  nop     dword ptr [rax+rax+00h]
0x1800610a3  mov     [rbp+hKey], r15
0x1800610a7  lea     rdx, [rbp+lpSubKey]
0x1800610ab  cmp     [rbp+var_30], 7
0x1800610b0  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x1800610b5  lea     rax, [rbp+hKey]
0x1800610b9  mov     qword ptr [rsp+80h+phkResult], rax; unsigned int
0x1800610be  mov     r9d, [rbp+samDesired]; samDesired
0x1800610c2  xor     r8d, r8d; ulOptions
0x1800610c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800610cc  call    cs:__imp_RegOpenKeyExW
0x1800610d3  nop     dword ptr [rax+rax+00h]
0x1800610d8  test    eax, eax
0x1800610da  jnz     loc_18006117A
0x1800610e0  lea     rdi, [rsi+8]
0x1800610e4  lea     rax, [rbp+hKey]
0x1800610e8  cmp     rdi, rax
0x1800610eb  jz      short loc_18006112B
0x1800610ed  mov     r14, [rbp+hKey]
0x1800610f1  mov     rsi, [rdi]
0x1800610f4  test    rsi, rsi
0x1800610f7  jz      short loc_180061124
0x1800610f9  call    cs:__imp_GetLastError
0x180061100  nop     dword ptr [rax+rax+00h]
0x180061105  mov     ebx, eax
0x180061107  mov     rcx, rsi; hKey
0x18006110a  call    cs:__imp_RegCloseKey
0x180061111  nop     dword ptr [rax+rax+00h]
0x180061116  mov     ecx, ebx; dwErrCode
0x180061118  call    cs:__imp_SetLastError
0x18006111f  nop     dword ptr [rax+rax+00h]
0x180061124  mov     [rdi], r14
0x180061127  mov     [rbp+hKey], r15
0x18006112b  lea     rcx, [rbp+var_28]
0x18006112f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180061134  nop
0x180061135  lea     rcx, [rbp+lpSubKey]
0x180061139  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006113e  nop
0x18006113f  mov     rcx, [rbp+hKey]; hKey
0x180061143  test    rcx, rcx
0x180061146  jz      short loc_180061154
0x180061148  call    cs:__imp_RegCloseKey
0x18006114f  nop     dword ptr [rax+rax+00h]
0x180061154  mov     al, 1
0x180061156  mov     rcx, [rbp+var_8]
0x18006115a  xor     rcx, rsp; StackCookie
0x18006115d  call    __security_check_cookie
0x180061162  mov     rbx, [rsp+80h+arg_8]
0x18006116a  add     rsp, 80h
0x180061171  pop     r15
0x180061173  pop     r14
0x180061175  pop     rdi
0x180061176  pop     rsi
0x180061177  pop     rbp
0x180061178  retn
0x18006117a  cmp     eax, 2
0x18006117d  jnz     short loc_1800611AC
0x18006117f  lea     rcx, [rbp+var_28]
0x180061183  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180061188  nop
0x180061189  lea     rcx, [rbp+lpSubKey]
0x18006118d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180061192  nop
0x180061193  mov     rcx, [rbp+hKey]; hKey
0x180061197  test    rcx, rcx
0x18006119a  jz      short loc_1800611A8
0x18006119c  call    cs:__imp_RegCloseKey
0x1800611a3  nop     dword ptr [rax+rax+00h]
0x1800611a8  xor     al, al
0x1800611aa  jmp     short loc_180061156
0x1800611ac  mov     rcx, [rbp+28h]; this
0x1800611b0  mov     r9d, eax; char *
0x1800611b3  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\management\\share"...
0x1800611ba  mov     edx, 188h; void *
0x1800611bf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
