# TdhpEnumerateManifestProviders

- ea: `0x180015e08`
- end: `0x180016094`
- name: `TdhpEnumerateManifestProviders`
- size: `652`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800245f4`

## callees

- `0x180015e08`
- `0x18001609c`
- `0x18001634c`
- `0x1800207c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015fa2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015fa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001605b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001605b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015f92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001604d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015f92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001604d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015edd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015edd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180015f2d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180015f2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015e93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015f59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015e93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015f59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016042`

## pseudocode

```c
__int64 __fastcall TdhpEnumerateManifestProviders(__int64 a1, _DWORD *a2)
{
  void *v4; // rdi
  unsigned int ProviderNameFromRegistry; // ebx
  DWORD v6; // eax
  int v7; // r12d
  DWORD i; // r15d
  HANDLE ProcessHeap; // rax
  GUID *v10; // rax
  GUID *v11; // rdi
  GUID **v12; // rax
  HANDLE v13; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+64h] [rbp-9Ch]
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  void *v20; // [rsp+80h] [rbp-80h]
  WCHAR Name[38]; // [rsp+90h] [rbp-70h] BYREF
  char v22; // [rsp+DCh] [rbp-24h] BYREF

  cchName = 260;
  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  v4 = 0;
  v20 = 0;
  v16 = 0;
  if ( !a1 || !a2 )
    return 87;
  ProviderNameFromRegistry = RegOpenKeyExW(
                               HKEY_LOCAL_MACHINE,
                               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT\\Publishers",
                               0,
                               0x20119u,
                               &hKey);
  if ( !ProviderNameFromRegistry )
  {
    ProviderNameFromRegistry = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !ProviderNameFromRegistry )
    {
      v6 = cSubKeys;
      v7 = 0;
      if ( cSubKeys )
      {
        for ( i = 0; i < v6; ++i )
        {
          ProviderNameFromRegistry = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
          if ( ProviderNameFromRegistry )
            goto LABEL_22;
          ProviderNameFromRegistry = RegOpenKeyExW(hKey, Name, 0, 0x20119u, &phkResult);
          if ( ProviderNameFromRegistry )
            goto LABEL_22;
          ProviderNameFromRegistry = ReadProviderNameFromRegistry(phkResult);
          RegCloseKey(phkResult);
          phkResult = 0;
          if ( !ProviderNameFromRegistry )
          {
            ProcessHeap = GetProcessHeap();
            v10 = (GUID *)HeapAlloc(ProcessHeap, 8u, 0x30u);
            v11 = v10;
            if ( !v10 )
            {
              v4 = v20;
              goto LABEL_22;
            }
            *(_QWORD *)&v10[2].Data1 = v20;
            *(_DWORD *)v10[2].Data4 = v16;
            if ( Name[0] != 123 || &v22 != (char *)tlx::string_to_guid<wchar_t [260]>(&v10[1], Name) )
              v11[1] = g_NullGuid;
            *(_DWORD *)&v11[2].Data4[4] = 0;
            v12 = *(GUID ***)(a1 + 8);
            if ( *v12 != (GUID *)a1 )
              __fastfail(3u);
            *(_QWORD *)&v11->Data1 = a1;
            ++v7;
            *(_QWORD *)v11->Data4 = v12;
            *v12 = v11;
            *(_QWORD *)(a1 + 8) = v11;
          }
          v6 = cSubKeys;
          v4 = 0;
          v20 = 0;
          cchName = 260;
        }
      }
      else
      {
        ProviderNameFromRegistry = 1168;
      }
      *a2 = v7;
    }
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v4);
  }
  return ProviderNameFromRegistry;
}

```

## disassembly

```asm
0x180015e08  mov     [rsp-8+arg_10], rbx
0x180015e0d  push    rbp
0x180015e0e  push    rsi
0x180015e0f  push    rdi
0x180015e10  push    r12
0x180015e12  push    r13
0x180015e14  push    r14
0x180015e16  push    r15
0x180015e18  lea     rbp, [rsp-1B0h]
0x180015e20  sub     rsp, 2B0h
0x180015e27  mov     rax, cs:__security_cookie
0x180015e2e  xor     rax, rsp
0x180015e31  mov     [rbp+1E0h+var_40], rax
0x180015e38  xor     esi, esi
0x180015e3a  mov     [rsp+2E0h+cchName], 104h
0x180015e42  mov     [rsp+2E0h+hKey], rsi
0x180015e47  mov     r13, rdx
0x180015e4a  mov     [rsp+2E0h+var_268], rsi
0x180015e4f  mov     r14, rcx
0x180015e52  mov     [rsp+2E0h+cSubKeys], esi
0x180015e56  mov     edi, esi
0x180015e58  mov     [rbp+1E0h+var_260], rsi
0x180015e5c  mov     [rsp+2E0h+var_27C], esi
0x180015e60  test    rcx, rcx
0x180015e63  jz      loc_180016065
0x180015e69  test    rdx, rdx
0x180015e6c  jz      loc_180016065
0x180015e72  lea     rax, [rsp+2E0h+hKey]
0x180015e77  mov     r9d, 20119h; samDesired
0x180015e7d  xor     r8d, r8d; ulOptions
0x180015e80  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180015e85  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180015e8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015e93  call    cs:__imp_RegOpenKeyExW
0x180015e99  mov     ebx, eax
0x180015e9b  test    eax, eax
0x180015e9d  jnz     loc_180016038
0x180015ea3  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180015ea8  lea     rax, [rsp+2E0h+cSubKeys]
0x180015ead  mov     [rsp+2E0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180015eb2  xor     r9d, r9d; lpReserved
0x180015eb5  mov     [rsp+2E0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180015eba  xor     r8d, r8d; lpcchClass
0x180015ebd  mov     [rsp+2E0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180015ec2  xor     edx, edx; lpClass
0x180015ec4  mov     [rsp+2E0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180015ec9  mov     [rsp+2E0h+lpcValues], rsi; lpcValues
0x180015ece  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180015ed3  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180015ed8  mov     [rsp+2E0h+phkResult], rax; lpcSubKeys
0x180015edd  call    cs:__imp_RegQueryInfoKeyW
0x180015ee3  mov     ebx, eax
0x180015ee5  test    eax, eax
0x180015ee7  jnz     loc_180016038
0x180015eed  mov     eax, [rsp+2E0h+cSubKeys]
0x180015ef1  mov     r12d, esi
0x180015ef4  test    eax, eax
0x180015ef6  jz      loc_18001602F
0x180015efc  mov     r15d, esi
0x180015eff  cmp     r15d, eax
0x180015f02  jnb     loc_180016034
0x180015f08  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180015f0d  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180015f12  mov     [rsp+2E0h+lpcValues], rsi; lpftLastWriteTime
0x180015f17  lea     r8, [rbp+1E0h+Name]; lpName
0x180015f1b  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcchClass
0x180015f20  mov     edx, r15d; dwIndex
0x180015f23  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpClass
0x180015f28  mov     [rsp+2E0h+phkResult], rsi; lpReserved
0x180015f2d  call    cs:__imp_RegEnumKeyExW
0x180015f33  mov     ebx, eax
0x180015f35  test    eax, eax
0x180015f37  jnz     loc_180016038
0x180015f3d  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180015f42  lea     rax, [rsp+2E0h+var_268]
0x180015f47  mov     r9d, 20119h; samDesired
0x180015f4d  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180015f52  xor     r8d, r8d; ulOptions
0x180015f55  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x180015f59  call    cs:__imp_RegOpenKeyExW
0x180015f5f  mov     ebx, eax
0x180015f61  test    eax, eax
0x180015f63  jnz     loc_180016038
0x180015f69  mov     rcx, [rsp+2E0h+var_268]; hKey
0x180015f6e  lea     r8, [rsp+2E0h+var_27C]
0x180015f73  lea     rdx, [rbp+1E0h+var_260]
0x180015f77  call    ReadProviderNameFromRegistry
0x180015f7c  mov     rcx, [rsp+2E0h+var_268]; hKey
0x180015f81  mov     ebx, eax
0x180015f83  call    cs:__imp_RegCloseKey
0x180015f89  mov     [rsp+2E0h+var_268], rsi
0x180015f8e  test    ebx, ebx
0x180015f90  jnz     short loc_180016007
0x180015f92  call    cs:__imp_GetProcessHeap
0x180015f98  mov     rcx, rax; hHeap
0x180015f9b  lea     edx, [rbx+8]; dwFlags
0x180015f9e  lea     r8d, [rbx+30h]; dwBytes
0x180015fa2  call    cs:__imp_HeapAlloc
0x180015fa8  mov     rdi, rax
0x180015fab  test    rax, rax
0x180015fae  jz      short loc_180016029
0x180015fb0  mov     rcx, [rbp+1E0h+var_260]
0x180015fb4  mov     [rax+20h], rcx
0x180015fb8  mov     ecx, [rsp+2E0h+var_27C]
0x180015fbc  mov     [rax+28h], ecx
0x180015fbf  cmp     [rbp+1E0h+Name], 7Bh ; '{'
0x180015fc4  jnz     short loc_180015FDC
0x180015fc6  lea     rdx, [rbp+1E0h+Name]
0x180015fca  lea     rcx, [rax+10h]
0x180015fce  call    ??$string_to_guid@$$BY0BAE@_W@tlx@@YAPEB_WPEAU_GUID@@AEAY0BAE@$$CB_W@Z; tlx::string_to_guid<wchar_t [260]>(_GUID *,wchar_t const (&)[260])
0x180015fd3  lea     rcx, [rbp+1E0h+var_204]
0x180015fd7  cmp     rcx, rax
0x180015fda  jz      short loc_180015FE8
0x180015fdc  movups  xmm0, xmmword ptr cs:?g_NullGuid@@3U_GUID@@B.Data1; _GUID const g_NullGuid ...
0x180015fe3  movdqu  xmmword ptr [rdi+10h], xmm0
0x180015fe8  xor     esi, esi
0x180015fea  mov     [rdi+2Ch], esi
0x180015fed  mov     rax, [r14+8]
0x180015ff1  cmp     [rax], r14
0x180015ff4  jnz     short loc_180016022
0x180015ff6  mov     [rdi], r14
0x180015ff9  inc     r12d
0x180015ffc  mov     [rdi+8], rax
0x180016000  mov     [rax], rdi
0x180016003  mov     [r14+8], rdi
0x180016007  mov     eax, [rsp+2E0h+cSubKeys]
0x18001600b  mov     rdi, rsi
0x18001600e  mov     [rbp+1E0h+var_260], rsi
0x180016012  inc     r15d
0x180016015  mov     [rsp+2E0h+cchName], 104h
0x18001601d  jmp     loc_180015EFF
0x180016022  mov     ecx, 3
0x180016027  int     29h; Win8: RtlFailFast(ecx)
0x180016029  mov     rdi, [rbp+1E0h+var_260]
0x18001602d  jmp     short loc_180016038
0x18001602f  mov     ebx, 490h
0x180016034  mov     [r13+0], r12d
0x180016038  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001603d  test    rcx, rcx
0x180016040  jz      short loc_180016048
0x180016042  call    cs:__imp_RegCloseKey
0x180016048  test    rdi, rdi
0x18001604b  jz      short loc_180016061
0x18001604d  call    cs:__imp_GetProcessHeap
0x180016053  mov     r8, rdi; lpMem
0x180016056  xor     edx, edx; dwFlags
0x180016058  mov     rcx, rax; hHeap
0x18001605b  call    cs:__imp_HeapFree
0x180016061  mov     eax, ebx
0x180016063  jmp     short loc_18001606A
0x180016065  mov     eax, 57h ; 'W'
0x18001606a  mov     rcx, [rbp+1E0h+var_40]
0x180016071  xor     rcx, rsp; StackCookie
0x180016074  call    __security_check_cookie
0x180016079  mov     rbx, [rsp+2E0h+arg_10]
0x180016081  add     rsp, 2B0h
0x180016088  pop     r15
0x18001608a  pop     r14
0x18001608c  pop     r13
0x18001608e  pop     r12
0x180016090  pop     rdi
0x180016091  pop     rsi
0x180016092  pop     rbp
0x180016093  retn
```
