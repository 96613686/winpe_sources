# IppOpenTcpipAdapterKey(ushort,_GUID const &,ulong)

- ea: `0x18001c4bc`
- end: `0x18001c80f`
- name: `?IppOpenTcpipAdapterKey@@YAPEAUHKEY__@@GAEBU_GUID@@K@Z`
- size: `851`
- prototype: `HKEY(unsigned __int16, const struct _GUID *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c3c0`
- `0x1800ba678`

## callees

- `0x18001c4bc`
- `0x18001c9cc`
- `0x1800596d8`
- `0x1800597c4`
- `0x1800a9e18`
- `0x1800b16a4`
- `0x1800bb560`
- `0x180106340`
- `0x180107330`
- `0x1801acf0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c6d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c6d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c798`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001c551`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001c737`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001c551`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001c737`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001c505`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001c505`

## string_xrefs

- `0x18001c539`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x18001c772`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x18001c7bd`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x18001c7f2`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x18001c71f`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c
HKEY __fastcall IppOpenTcpipAdapterKey(__int16 a1, const struct _GUID *a2, REGSAM a3)
{
  int PersistedStateLocation; // eax
  unsigned int v6; // r8d
  WCHAR *v7; // rax
  __int64 v8; // r8
  const char *v9; // r9
  __int64 v10; // r10
  const WCHAR *v11; // rcx
  __int64 v12; // rdi
  WCHAR *v13; // r11
  __int64 v14; // rax
  __int64 v15; // r8
  WCHAR *v16; // rcx
  __int64 v17; // r8
  WCHAR *v18; // rax
  __int64 v19; // r10
  WCHAR *v20; // r8
  OLECHAR *v21; // rax
  __int64 v22; // rdx
  WCHAR *v23; // rcx
  unsigned int v24; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[8]; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  hKey = 0;
  StringFromGUID2(a2, sz, 39);
  memset_0(SubKey, 0, 0x208u);
  if ( a1 == 2 )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"DHCP_CLIENT_INTERFACE",
                               0,
                               L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
                               0);
    if ( PersistedStateLocation >= 0 )
      goto LABEL_3;
    v26 = 52;
LABEL_31:
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)v26,
      v6,
      (const char *)(unsigned int)PersistedStateLocation,
      (int)SubKey);
    goto LABEL_39;
  }
  if ( a1 != 23 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
      (const char *)0x80070057LL,
      phkResult);
    goto LABEL_39;
  }
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"DHCPV6_CLIENT_INTERFACE",
                             0,
                             L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces",
                             0);
  if ( PersistedStateLocation < 0 )
  {
    v26 = 68;
    goto LABEL_31;
  }
LABEL_3:
  v7 = SubKey;
  v8 = 260;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = v8 == 0 ? (const char *)0x80070057LL : 0LL;
  v10 = (260 - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    goto LABEL_37;
  v11 = L"\\";
  v12 = 2147483646;
  v13 = &SubKey[v10];
  v14 = 2147483646;
  v15 = 260 - v10;
  if ( v10 != 260 )
  {
    do
    {
      if ( !v14 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v14;
      --v15;
    }
    while ( v15 );
  }
  v16 = v13 - 1;
  v9 = v15 == 0 ? (const char *)0x8007007ALL : 0LL;
  if ( v15 )
    v16 = v13;
  *v16 = 0;
  if ( !v15 )
  {
LABEL_37:
    v27 = 79;
    goto LABEL_38;
  }
  v17 = 260;
  v18 = SubKey;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  v9 = v17 == 0 ? (const char *)0x80070057LL : 0LL;
  v19 = (260 - v17) & -(__int64)(v17 != 0);
  if ( !v17 )
    goto LABEL_36;
  v20 = &SubKey[v19];
  v21 = sz;
  v22 = 260 - v19;
  if ( 260 != v19 )
  {
    do
    {
      if ( !v12 )
        break;
      if ( !*v21 )
        break;
      *v20++ = *v21++;
      --v12;
      --v22;
    }
    while ( v22 );
  }
  v23 = v20 - 1;
  v9 = v22 == 0 ? (const char *)0x8007007ALL : 0LL;
  if ( v22 )
    v23 = v20;
  *v23 = 0;
  if ( !v22 )
  {
LABEL_36:
    v27 = 84;
LABEL_38:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
      v9,
      (int)SubKey);
    goto LABEL_39;
  }
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v30);
    RegCloseKey(hKey);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v30);
  }
  hKey = 0;
  v24 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, a3, &hKey);
  if ( !v24 )
    return hKey;
  wil::details::in1diag3::Log_Win32Msg(
    retaddr,
    (void *)0x5C,
    (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
    (const char *)v24,
    (unsigned int)"key: %ws",
    (const char *)SubKey);
LABEL_39:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18001c4bc  mov     [rsp-8+arg_0], rbx
0x18001c4c1  push    rbp
0x18001c4c2  push    rsi
0x18001c4c3  push    rdi
0x18001c4c4  push    r14
0x18001c4c6  push    r15
0x18001c4c8  lea     rbp, [rsp-1C0h]
0x18001c4d0  sub     rsp, 2C0h
0x18001c4d7  mov     rax, cs:__security_cookie
0x18001c4de  xor     rax, rsp
0x18001c4e1  mov     [rbp+1E0h+var_30], rax
0x18001c4e8  mov     rax, rdx
0x18001c4eb  xor     r14d, r14d
0x18001c4ee  mov     esi, r8d
0x18001c4f1  mov     [rsp+2E0h+hKey], r14
0x18001c4f6  movzx   ebx, cx
0x18001c4f9  lea     rdx, [rsp+2E0h+sz]; lpsz
0x18001c4fe  mov     rcx, rax; rguid
0x18001c501  lea     r8d, [r14+27h]; cchMax
0x18001c505  call    cs:__imp_StringFromGUID2
0x18001c50b  mov     edi, 208h
0x18001c510  lea     rcx, [rbp+1E0h+SubKey]; void *
0x18001c514  mov     r8d, edi; Size
0x18001c517  xor     edx, edx; Val
0x18001c519  call    memset_0
0x18001c51e  lea     r15d, [r14+2]
0x18001c522  cmp     bx, r15w
0x18001c526  jnz     loc_18001C765
0x18001c52c  mov     [rsp+2E0h+var_2B0], r14
0x18001c531  lea     rax, [rbp+1E0h+SubKey]
0x18001c535  mov     dword ptr [rsp+2E0h+var_2B8], edi
0x18001c539  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Tc"...
0x18001c540  xor     r9d, r9d
0x18001c543  mov     [rsp+2E0h+phkResult], rax; int
0x18001c548  xor     edx, edx
0x18001c54a  lea     rcx, aDhcpClientInte; "DHCP_CLIENT_INTERFACE"
0x18001c551  call    cs:__imp_RtlGetPersistedStateLocation
0x18001c557  test    eax, eax
0x18001c559  js      loc_18001C75E
0x18001c55f  mov     edx, 104h
0x18001c564  lea     rax, [rbp+1E0h+SubKey]
0x18001c568  mov     r8d, edx
0x18001c56b  cmp     [rax], r14w
0x18001c56f  jz      short loc_18001C57A
0x18001c571  add     rax, r15
0x18001c574  sub     r8, 1
0x18001c578  jnz     short loc_18001C56B
0x18001c57a  mov     rax, r8
0x18001c57d  mov     ebx, 80070057h
0x18001c582  neg     rax
0x18001c585  mov     rcx, rdx
0x18001c588  mov     rax, r8
0x18001c58b  sbb     r9d, r9d
0x18001c58e  sub     rcx, r8
0x18001c591  not     r9d
0x18001c594  and     r9d, ebx; char *
0x18001c597  neg     rax
0x18001c59a  sbb     r10, r10
0x18001c59d  and     r10, rcx
0x18001c5a0  test    r8, r8
0x18001c5a3  jz      loc_18001C7E6
0x18001c5a9  mov     r8, rdx
0x18001c5ac  lea     r11, [rbp+1E0h+SubKey]
0x18001c5b0  lea     rcx, SubBlock; "\\"
0x18001c5b7  mov     edi, 7FFFFFFEh
0x18001c5bc  lea     r11, [r11+r10*2]
0x18001c5c0  mov     eax, edi
0x18001c5c2  sub     r8, r10
0x18001c5c5  jz      short loc_18001C5E9
0x18001c5c7  test    rax, rax
0x18001c5ca  jz      short loc_18001C5E9
0x18001c5cc  movzx   r9d, word ptr [rcx]
0x18001c5d0  test    r9w, r9w
0x18001c5d4  jz      short loc_18001C5E9
0x18001c5d6  mov     [r11], r9w
0x18001c5da  add     rcx, r15
0x18001c5dd  add     r11, r15
0x18001c5e0  dec     rax
0x18001c5e3  sub     r8, 1
0x18001c5e7  jnz     short loc_18001C5C7
0x18001c5e9  mov     rax, r8
0x18001c5ec  lea     rcx, [r11-2]
0x18001c5f0  neg     rax
0x18001c5f3  sbb     r9d, r9d
0x18001c5f6  not     r9d
0x18001c5f9  and     r9d, 8007007Ah
0x18001c600  test    r8, r8
0x18001c603  cmovnz  rcx, r11
0x18001c607  mov     [rcx], r14w
0x18001c60b  jz      loc_18001C7E6
0x18001c611  mov     r8, rdx
0x18001c614  lea     rax, [rbp+1E0h+SubKey]
0x18001c618  cmp     [rax], r14w
0x18001c61c  jz      short loc_18001C627
0x18001c61e  add     rax, r15
0x18001c621  sub     r8, 1
0x18001c625  jnz     short loc_18001C618
0x18001c627  mov     rax, r8
0x18001c62a  mov     rcx, rdx
0x18001c62d  neg     rax
0x18001c630  mov     rax, r8
0x18001c633  sbb     r9d, r9d
0x18001c636  sub     rcx, r8
0x18001c639  not     r9d
0x18001c63c  and     r9d, ebx
0x18001c63f  neg     rax
0x18001c642  sbb     r10, r10
0x18001c645  and     r10, rcx
0x18001c648  test    r8, r8
0x18001c64b  jz      loc_18001C7DF
0x18001c651  lea     r8, [rbp+1E0h+SubKey]
0x18001c655  lea     r8, [r8+r10*2]
0x18001c659  lea     rax, [rsp+2E0h+sz]
0x18001c65e  sub     rdx, r10
0x18001c661  jz      short loc_18001C683
0x18001c663  test    rdi, rdi
0x18001c666  jz      short loc_18001C683
0x18001c668  movzx   ecx, word ptr [rax]
0x18001c66b  test    cx, cx
0x18001c66e  jz      short loc_18001C683
0x18001c670  mov     [r8], cx
0x18001c674  add     rax, r15
0x18001c677  add     r8, r15
0x18001c67a  dec     rdi
0x18001c67d  sub     rdx, 1
0x18001c681  jnz     short loc_18001C663
0x18001c683  mov     rax, rdx
0x18001c686  lea     rcx, [r8-2]
0x18001c68a  neg     rax
0x18001c68d  sbb     r9d, r9d
0x18001c690  not     r9d
0x18001c693  and     r9d, 8007007Ah
0x18001c69a  test    rdx, rdx
0x18001c69d  cmovnz  rcx, r8
0x18001c6a1  mov     [rcx], r14w
0x18001c6a5  jz      loc_18001C7DF
0x18001c6ab  mov     rbx, [rsp+2E0h+hKey]
0x18001c6b0  test    rbx, rbx
0x18001c6b3  jnz     loc_18001C78B
0x18001c6b9  lea     rax, [rsp+2E0h+hKey]
0x18001c6be  mov     [rsp+2E0h+hKey], r14
0x18001c6c3  mov     r9d, esi; samDesired
0x18001c6c6  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18001c6cb  xor     r8d, r8d; ulOptions
0x18001c6ce  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x18001c6d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c6d9  call    cs:__imp_RegOpenKeyExW
0x18001c6df  test    eax, eax
0x18001c6e1  jnz     loc_18001C7AD
0x18001c6e7  mov     rax, [rsp+2E0h+hKey]
0x18001c6ec  mov     rcx, [rbp+1E0h+var_30]
0x18001c6f3  xor     rcx, rsp; StackCookie
0x18001c6f6  call    __security_check_cookie
0x18001c6fb  mov     rbx, [rsp+2E0h+arg_0]
0x18001c703  add     rsp, 2C0h
0x18001c70a  pop     r15
0x18001c70c  pop     r14
0x18001c70e  pop     rdi
0x18001c70f  pop     rsi
0x18001c710  pop     rbp
0x18001c711  retn
0x18001c712  mov     [rsp+2E0h+var_2B0], r14
0x18001c717  lea     rax, [rbp+1E0h+SubKey]
0x18001c71b  mov     dword ptr [rsp+2E0h+var_2B8], edi
0x18001c71f  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x18001c726  xor     r9d, r9d
0x18001c729  mov     [rsp+2E0h+phkResult], rax; int
0x18001c72e  xor     edx, edx
0x18001c730  lea     rcx, aDhcpv6ClientIn; "DHCPV6_CLIENT_INTERFACE"
0x18001c737  call    cs:__imp_RtlGetPersistedStateLocation
0x18001c73d  test    eax, eax
0x18001c73f  jns     loc_18001C55F
0x18001c745  mov     edx, 44h ; 'D'; void *
0x18001c74a  mov     rcx, [rbp+1E8h]; this
0x18001c751  mov     r9d, eax; char *
0x18001c754  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001c759  jmp     loc_18001C7FE
0x18001c75e  mov     edx, 34h ; '4'
0x18001c763  jmp     short loc_18001C74A
0x18001c765  cmp     bx, 17h
0x18001c769  jz      short loc_18001C712
0x18001c76b  mov     rcx, [rbp+1E8h]; this
0x18001c772  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18001c779  mov     r9d, 80070057h; char *
0x18001c77f  mov     edx, 4Bh ; 'K'; void *
0x18001c784  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c789  jmp     short loc_18001C7FE
0x18001c78b  lea     rcx, [rsp+2E0h+var_298]; this
0x18001c790  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c795  mov     rcx, rbx; hKey
0x18001c798  call    cs:__imp_RegCloseKey
0x18001c79e  lea     rcx, [rsp+2E0h+var_298]; this
0x18001c7a3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c7a8  jmp     loc_18001C6B9
0x18001c7ad  mov     rcx, [rbp+1E8h]; this
0x18001c7b4  lea     rdx, [rbp+1E0h+SubKey]
0x18001c7b8  mov     [rsp+2E0h+var_2B8], rdx; char *
0x18001c7bd  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18001c7c4  lea     rdx, aKeyWs; "key: %ws"
0x18001c7cb  mov     r9d, eax; char *
0x18001c7ce  mov     [rsp+2E0h+phkResult], rdx; unsigned int
0x18001c7d3  mov     edx, 5Ch ; '\'; void *
0x18001c7d8  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001c7dd  jmp     short loc_18001C7FE
0x18001c7df  mov     edx, 54h ; 'T'
0x18001c7e4  jmp     short loc_18001C7EB
0x18001c7e6  mov     edx, 4Fh ; 'O'; void *
0x18001c7eb  mov     rcx, [rbp+1E8h]; this
0x18001c7f2  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18001c7f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c7fe  lea     rcx, [rsp+2E0h+hKey]
0x18001c803  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c808  xor     eax, eax
0x18001c80a  jmp     loc_18001C6EC
```
