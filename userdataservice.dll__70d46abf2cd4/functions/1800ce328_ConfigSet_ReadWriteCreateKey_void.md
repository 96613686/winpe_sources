# ConfigSet::ReadWriteCreateKey(void)

- ea: `0x1800ce328`
- end: `0x1800ce4b4`
- name: `?ReadWriteCreateKey@ConfigSet@@QEAAJXZ`
- size: `396`
- prototype: `__int64 __fastcall(ConfigSet *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cd300`

## callees

- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180068404`
- `0x18008dcdc`
- `0x1800cc8f4`
- `0x1800ce328`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ce3a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ce3ee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ce3a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ce3ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce48a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce48a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ce425`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ce425`

## string_xrefs

- `0x1800ce450`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x1800ce410`: `\Service\CallIDMatchOverrides`

## pseudocode

```c
__int64 __fastcall ConfigSet::ReadWriteCreateKey(ConfigSet *this)
{
  int RegistryPath; // eax
  int Key; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 v6; // rcx
  HKEY *phkResult; // rax
  HKEY *v8; // rax
  _WORD *v9; // rax
  HKEY *v10; // rax
  LPCWSTR v12[4]; // [rsp+50h] [rbp-68h] BYREF
  LPCWSTR lpSubKey[9]; // [rsp+70h] [rbp-48h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v12);
  RegistryPath = ConfigSet::GetRegistryPath(this, lpSubKey, v12);
  Key = RegistryPath;
  if ( RegistryPath < 0 )
  {
    v4 = 1038;
    v5 = 1;
    v6 = (unsigned int)RegistryPath;
LABEL_14:
    Log_HREvent(v6, v5, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v4);
    goto LABEL_18;
  }
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((HKEY *)this + 10);
  Key = RegCreateKeyExW(*((HKEY *)this + 13), lpSubKey[0], 0, 0, 0, 0x13u, 0, phkResult, 0);
  if ( Key == 1021 )
  {
    v8 = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((HKEY *)this + 10);
    Key = RegCreateKeyExW(*((HKEY *)this + 13), lpSubKey[0], 0, 0, 1u, 0x13u, 0, v8, 0);
  }
  if ( Key == 5 )
  {
    v9 = (_WORD *)*((_QWORD *)this + 15);
    if ( (!v9 || *v9)
      && CompareStringOrdinal(L"\\Service\\CallIDMatchOverrides", -1, *((LPCWCH *)this + 16), -1, 1) != 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    goto LABEL_12;
  }
  if ( Key )
  {
    if ( Key <= 0 )
    {
LABEL_13:
      v4 = 1069;
      v5 = 0;
      v6 = (unsigned int)Key;
      goto LABEL_14;
    }
LABEL_12:
    Key = (unsigned __int16)Key | 0x80070000;
    goto LABEL_13;
  }
  if ( v12[0] != v12[1] )
  {
    v10 = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((HKEY *)this + 11);
    RegOpenKeyExW(*((HKEY *)this + 13), v12[0], 0, 0x11u, v10);
  }
  Key = 0;
LABEL_18:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v12);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x1800ce328  push    rbx
0x1800ce32a  push    rbp
0x1800ce32b  push    rsi
0x1800ce32c  push    rdi
0x1800ce32d  sub     rsp, 98h
0x1800ce334  mov     rdi, rcx
0x1800ce337  lea     rcx, [rsp+0B8h+lpSubKey]; void *
0x1800ce33c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800ce341  lea     rcx, [rsp+0B8h+var_68]; void *
0x1800ce346  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800ce34b  lea     r8, [rsp+0B8h+var_68]
0x1800ce350  mov     rcx, rdi
0x1800ce353  lea     rdx, [rsp+0B8h+lpSubKey]
0x1800ce358  call    ?GetRegistryPath@ConfigSet@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z; ConfigSet::GetRegistryPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800ce35d  xor     ebp, ebp
0x1800ce35f  mov     ebx, eax
0x1800ce361  test    eax, eax
0x1800ce363  jns     short loc_1800CE375
0x1800ce365  mov     r9d, 40Eh
0x1800ce36b  lea     edx, [rbp+1]
0x1800ce36e  mov     ecx, eax
0x1800ce370  jmp     loc_1800CE450
0x1800ce375  lea     rcx, [rdi+50h]
0x1800ce379  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x1800ce37e  mov     rdx, [rsp+0B8h+lpSubKey]; lpSubKey
0x1800ce383  xor     r9d, r9d; lpClass
0x1800ce386  mov     rcx, [rdi+68h]; hKey
0x1800ce38a  xor     r8d, r8d; Reserved
0x1800ce38d  mov     [rsp+0B8h+lpdwDisposition], rbp; lpdwDisposition
0x1800ce392  mov     [rsp+0B8h+phkResult], rax; phkResult
0x1800ce397  mov     [rsp+0B8h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1800ce39c  mov     [rsp+0B8h+samDesired], 13h; samDesired
0x1800ce3a4  mov     [rsp+0B8h+dwOptions], ebp; dwOptions
0x1800ce3a8  call    cs:__imp_RegCreateKeyExW
0x1800ce3ae  mov     ebx, eax
0x1800ce3b0  cmp     eax, 3FDh
0x1800ce3b5  jnz     short loc_1800CE3F6
0x1800ce3b7  lea     rcx, [rdi+50h]
0x1800ce3bb  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x1800ce3c0  mov     rdx, [rsp+0B8h+lpSubKey]; lpSubKey
0x1800ce3c5  xor     r9d, r9d; lpClass
0x1800ce3c8  mov     rcx, [rdi+68h]; hKey
0x1800ce3cc  xor     r8d, r8d; Reserved
0x1800ce3cf  mov     [rsp+0B8h+lpdwDisposition], rbp; lpdwDisposition
0x1800ce3d4  mov     [rsp+0B8h+phkResult], rax; phkResult
0x1800ce3d9  mov     [rsp+0B8h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1800ce3de  mov     [rsp+0B8h+samDesired], 13h; samDesired
0x1800ce3e6  mov     [rsp+0B8h+dwOptions], 1; dwOptions
0x1800ce3ee  call    cs:__imp_RegCreateKeyExW
0x1800ce3f4  mov     ebx, eax
0x1800ce3f6  cmp     ebx, 5
0x1800ce3f9  jnz     short loc_1800CE437
0x1800ce3fb  mov     rax, [rdi+78h]
0x1800ce3ff  test    rax, rax
0x1800ce402  jz      short loc_1800CE409
0x1800ce404  cmp     [rax], bp
0x1800ce407  jz      short loc_1800CE43D
0x1800ce409  mov     r8, [rdi+80h]; lpString2
0x1800ce410  lea     rcx, aServiceCallidm; "\\Service\\CallIDMatchOverrides"
0x1800ce417  or      edx, 0FFFFFFFFh; cchCount1
0x1800ce41a  mov     [rsp+0B8h+dwOptions], 1; bIgnoreCase
0x1800ce422  mov     r9d, edx; cchCount2
0x1800ce425  call    cs:__imp_CompareStringOrdinal
0x1800ce42b  cmp     eax, 2
0x1800ce42e  jz      short loc_1800CE43D
0x1800ce430  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ce435  jmp     short loc_1800CE43D
0x1800ce437  test    ebx, ebx
0x1800ce439  jz      short loc_1800CE45E
0x1800ce43b  jle     short loc_1800CE446
0x1800ce43d  movzx   ebx, bx
0x1800ce440  or      ebx, 80070000h
0x1800ce446  mov     r9d, 42Dh
0x1800ce44c  xor     edx, edx
0x1800ce44e  mov     ecx, ebx
0x1800ce450  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x1800ce457  call    Log_HREvent
0x1800ce45c  jmp     short loc_1800CE492
0x1800ce45e  mov     rax, [rsp+0B8h+var_60]
0x1800ce463  cmp     [rsp+0B8h+var_68], rax
0x1800ce468  jz      short loc_1800CE490
0x1800ce46a  lea     rcx, [rdi+58h]
0x1800ce46e  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x1800ce473  mov     rdx, [rsp+0B8h+var_68]; lpSubKey
0x1800ce478  mov     r9d, 11h; samDesired
0x1800ce47e  mov     rcx, [rdi+68h]; hKey
0x1800ce482  xor     r8d, r8d; ulOptions
0x1800ce485  mov     qword ptr [rsp+0B8h+dwOptions], rax; phkResult
0x1800ce48a  call    cs:__imp_RegOpenKeyExW
0x1800ce490  mov     ebx, ebp
0x1800ce492  lea     rcx, [rsp+0B8h+var_68]; void *
0x1800ce497  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ce49c  lea     rcx, [rsp+0B8h+lpSubKey]; void *
0x1800ce4a1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ce4a6  mov     eax, ebx
0x1800ce4a8  add     rsp, 98h
0x1800ce4af  pop     rdi
0x1800ce4b0  pop     rsi
0x1800ce4b1  pop     rbp
0x1800ce4b2  pop     rbx
0x1800ce4b3  retn
```
