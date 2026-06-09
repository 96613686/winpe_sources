# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180009930`
- end: `0x180009cc9`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `921`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c170`
- `0x18000d5b4`

## callees

- `0x180009930`
- `0x18000aa78`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180009aaa`
- `msvcrt!wcscat_s` at `0x180009abe`
- `msvcrt!wcscat_s` at `0x180009b9f`
- `msvcrt!wcscat_s` at `0x180009bb3`
- `msvcrt!wcscat_s` at `0x180009aaa`
- `msvcrt!wcscat_s` at `0x180009abe`
- `msvcrt!wcscat_s` at `0x180009b9f`
- `msvcrt!wcscat_s` at `0x180009bb3`
- `msvcrt!wcscpy_s` at `0x180009a96`
- `msvcrt!wcscpy_s` at `0x180009b8b`
- `msvcrt!wcscpy_s` at `0x180009a96`
- `msvcrt!wcscpy_s` at `0x180009b8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009bee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009bee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c80`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009b48`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009c35`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009b48`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009c35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009b01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009b01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800099d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800099d5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009a7c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009a7c`

## string_xrefs

- `0x180009a88`: `CLSID\`
- `0x180009b7d`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // ecx
  HKEY v12; // rdi
  HKEY v13; // rbx
  LSTATUS v14; // esi
  HKEY v15; // rbx
  LSTATUS v16; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v21[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v22; // [rsp+98h] [rbp-68h] BYREF
  wchar_t Destination[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  ppv = 0;
  v4 = a2;
  v22 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    return 0;
  }
  if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
LABEL_36:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( !a3 )
      {
        StringFromGUID2(rguid, sz, 64);
        wcscpy_s(Destination, 0x80u, L"CLSID\\");
        wcscat_s(Destination, 0x80u, sz);
        wcscat_s(Destination, 0x80u, L"\\Required Categories");
        v12 = HKEY_CLASSES_ROOT;
        v21[1] = 0;
        v21[0] = 0xFFFFFFFF80000000uLL;
        v21[2] = 0;
        cSubKeys = 0;
        phkResult = 0;
        if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
        {
          v13 = phkResult;
          v14 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v13 )
            RegCloseKey(v13);
          if ( !v14 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v21, Destination);
            v12 = (HKEY)v21[0];
          }
        }
        wcscpy_s(Destination, 0x80u, L"CLSID\\");
        wcscat_s(Destination, 0x80u, sz);
        wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
        hKey = 0;
        if ( !RegOpenKeyExW(v12, Destination, 0, 0x20019u, &hKey) )
        {
          v15 = hKey;
          v16 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v15 )
            RegCloseKey(v15);
          if ( !v16 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v21, Destination);
            v12 = (HKEY)v21[0];
          }
        }
        if ( v12 )
          RegCloseKey(v12);
      }
      goto LABEL_36;
    }
    v22 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v22);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v22);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v22)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v22);
    v8 = v7;
    if ( v7 < 0 )
      break;
LABEL_19:
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x180009930  mov     [rsp-8+arg_10], rbx
0x180009935  mov     [rsp-8+arg_18], rsi
0x18000993a  push    rbp
0x18000993b  push    rdi
0x18000993c  push    r12
0x18000993e  push    r14
0x180009940  push    r15
0x180009942  lea     rbp, [rsp-140h]
0x18000994a  sub     rsp, 240h
0x180009951  mov     rax, cs:__security_cookie
0x180009958  xor     rax, rsp
0x18000995b  mov     [rbp+160h+var_30], rax
0x180009962  xor     r15d, r15d
0x180009965  xorps   xmm0, xmm0
0x180009968  mov     [rsp+260h+var_1F8], r15
0x18000996d  mov     r14d, r8d
0x180009970  mov     rdi, rdx
0x180009973  mov     rbx, rcx
0x180009976  movups  [rbp+160h+var_1C8], xmm0
0x18000997a  test    rdx, rdx
0x18000997d  jz      loc_180009C9C
0x180009983  mov     eax, cs:GUID_NULL.Data1
0x180009989  cmp     [rcx], eax
0x18000998b  jnz     short loc_1800099B2
0x18000998d  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180009993  cmp     [rcx+4], eax
0x180009996  jnz     short loc_1800099B2
0x180009998  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000999e  cmp     [rcx+8], eax
0x1800099a1  jnz     short loc_1800099B2
0x1800099a3  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x1800099a9  cmp     [rcx+0Ch], eax
0x1800099ac  jz      loc_180009C9C
0x1800099b2  lea     rax, [rsp+260h+var_1F8]
0x1800099b7  mov     r12d, 1
0x1800099bd  mov     r8d, r12d; dwClsContext
0x1800099c0  mov     [rsp+260h+ppv], rax; ppv
0x1800099c5  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800099cc  xor     edx, edx; pUnkOuter
0x1800099ce  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800099d5  call    cs:__imp_CoCreateInstance
0x1800099db  test    eax, eax
0x1800099dd  js      loc_180009C86
0x1800099e3  jmp     short loc_180009A5F
0x1800099e5  mov     rax, [rdi+8]
0x1800099e9  lea     r9, [rbp+160h+var_1C8]
0x1800099ed  mov     r8d, r12d
0x1800099f0  mov     rdx, rbx
0x1800099f3  movups  xmm0, xmmword ptr [rax]
0x1800099f6  movdqu  [rbp+160h+var_1C8], xmm0
0x1800099fb  test    r14d, r14d
0x1800099fe  jz      short loc_180009A3F
0x180009a00  cmp     ecx, r12d
0x180009a03  mov     rcx, [rsp+260h+var_1F8]
0x180009a08  mov     rax, [rcx]
0x180009a0b  jnz     short loc_180009A13
0x180009a0d  mov     rax, [rax+28h]
0x180009a11  jmp     short loc_180009A17
0x180009a13  mov     rax, [rax+38h]
0x180009a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a1c  mov     esi, eax
0x180009a1e  test    eax, eax
0x180009a20  jns     short loc_180009A5B
0x180009a22  mov     rcx, [rsp+260h+var_1F8]
0x180009a27  test    rcx, rcx
0x180009a2a  jz      short loc_180009A38
0x180009a2c  mov     rax, [rcx]
0x180009a2f  mov     rax, [rax+10h]
0x180009a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a38  mov     eax, esi
0x180009a3a  jmp     loc_180009C9E
0x180009a3f  cmp     ecx, r12d
0x180009a42  mov     rcx, [rsp+260h+var_1F8]
0x180009a47  mov     rax, [rcx]
0x180009a4a  jnz     short loc_180009A52
0x180009a4c  mov     rax, [rax+30h]
0x180009a50  jmp     short loc_180009A56
0x180009a52  mov     rax, [rax+40h]
0x180009a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a5b  add     rdi, 10h
0x180009a5f  mov     ecx, [rdi]
0x180009a61  test    ecx, ecx
0x180009a63  jnz     short loc_1800099E5
0x180009a65  test    r14d, r14d
0x180009a68  jnz     loc_180009C86
0x180009a6e  lea     r8d, [rcx+40h]; cchMax
0x180009a72  mov     rcx, rbx; rguid
0x180009a75  lea     rdx, [rbp+160h+sz]; lpsz
0x180009a7c  call    cs:__imp_StringFromGUID2
0x180009a82  mov     r14d, 80h
0x180009a88  lea     r8, aClsid; "CLSID\\"
0x180009a8f  mov     edx, r14d; SizeInWords
0x180009a92  lea     rcx, [rbp+160h+Destination]; Destination
0x180009a96  call    cs:__imp_wcscpy_s
0x180009a9c  lea     r8, [rbp+160h+sz]; Source
0x180009aa3  mov     edx, r14d; SizeInWords
0x180009aa6  lea     rcx, [rbp+160h+Destination]; Destination
0x180009aaa  call    cs:__imp_wcscat_s
0x180009ab0  lea     r8, aRequiredCatego; "\\Required Categories"
0x180009ab7  mov     edx, r14d; SizeInWords
0x180009aba  lea     rcx, [rbp+160h+Destination]; Destination
0x180009abe  call    cs:__imp_wcscat_s
0x180009ac4  mov     rdi, 0FFFFFFFF80000000h
0x180009acb  mov     [rbp+160h+var_1D8], r15
0x180009acf  lea     rax, [rsp+260h+phkResult]
0x180009ad4  mov     [rbp+160h+var_1E0], rdi
0x180009ad8  mov     r12d, 20019h
0x180009ade  mov     [rsp+260h+ppv], rax; phkResult
0x180009ae3  mov     r9d, r12d; samDesired
0x180009ae6  mov     [rbp+160h+var_1D0], r15
0x180009aea  mov     rcx, rdi; hKey
0x180009aed  mov     [rsp+260h+cSubKeys], r15d
0x180009af2  xor     r8d, r8d; ulOptions
0x180009af5  mov     [rsp+260h+phkResult], r15
0x180009afa  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180009afe  mov     rbx, r15
0x180009b01  call    cs:__imp_RegOpenKeyExW
0x180009b07  test    eax, eax
0x180009b09  jnz     short loc_180009B7D
0x180009b0b  mov     rbx, [rsp+260h+phkResult]
0x180009b10  lea     rax, [rsp+260h+cSubKeys]
0x180009b15  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009b1a  xor     r9d, r9d; lpReserved
0x180009b1d  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009b22  xor     r8d, r8d; lpcchClass
0x180009b25  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180009b2a  xor     edx, edx; lpClass
0x180009b2c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009b31  mov     rcx, rbx; hKey
0x180009b34  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180009b39  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009b3e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009b43  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180009b48  call    cs:__imp_RegQueryInfoKeyW
0x180009b4e  mov     esi, eax
0x180009b50  test    rbx, rbx
0x180009b53  jz      short loc_180009B61
0x180009b55  mov     rcx, rbx; hKey
0x180009b58  call    cs:__imp_RegCloseKey
0x180009b5e  mov     rbx, r15
0x180009b61  test    esi, esi
0x180009b63  jnz     short loc_180009B7D
0x180009b65  cmp     [rsp+260h+cSubKeys], r15d
0x180009b6a  jnz     short loc_180009B7D
0x180009b6c  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180009b70  lea     rcx, [rbp+160h+var_1E0]; this
0x180009b74  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009b79  mov     rdi, [rbp+160h+var_1E0]
0x180009b7d  lea     r8, aClsid; "CLSID\\"
0x180009b84  mov     rdx, r14; SizeInWords
0x180009b87  lea     rcx, [rbp+160h+Destination]; Destination
0x180009b8b  call    cs:__imp_wcscpy_s
0x180009b91  lea     r8, [rbp+160h+sz]; Source
0x180009b98  mov     rdx, r14; SizeInWords
0x180009b9b  lea     rcx, [rbp+160h+Destination]; Destination
0x180009b9f  call    cs:__imp_wcscat_s
0x180009ba5  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180009bac  mov     rdx, r14; SizeInWords
0x180009baf  lea     rcx, [rbp+160h+Destination]; Destination
0x180009bb3  call    cs:__imp_wcscat_s
0x180009bb9  lea     rax, [rsp+260h+hKey]
0x180009bbe  mov     [rsp+260h+hKey], r15
0x180009bc3  mov     r9d, r12d; samDesired
0x180009bc6  mov     [rsp+260h+ppv], rax; phkResult
0x180009bcb  xor     r8d, r8d; ulOptions
0x180009bce  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180009bd2  mov     rcx, rdi; hKey
0x180009bd5  call    cs:__imp_RegOpenKeyExW
0x180009bdb  test    eax, eax
0x180009bdd  jnz     loc_180009C6A
0x180009be3  mov     eax, r15d
0x180009be6  test    rbx, rbx
0x180009be9  jz      short loc_180009BF4
0x180009beb  mov     rcx, rbx; hKey
0x180009bee  call    cs:__imp_RegCloseKey
0x180009bf4  mov     rbx, [rsp+260h+hKey]
0x180009bf9  test    eax, eax
0x180009bfb  jnz     short loc_180009C6A
0x180009bfd  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009c02  lea     rax, [rsp+260h+cSubKeys]
0x180009c07  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009c0c  xor     r9d, r9d; lpReserved
0x180009c0f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180009c14  xor     r8d, r8d; lpcchClass
0x180009c17  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009c1c  xor     edx, edx; lpClass
0x180009c1e  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180009c23  mov     rcx, rbx; hKey
0x180009c26  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009c2b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009c30  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180009c35  call    cs:__imp_RegQueryInfoKeyW
0x180009c3b  mov     esi, eax
0x180009c3d  test    rbx, rbx
0x180009c40  jz      short loc_180009C4E
0x180009c42  mov     rcx, rbx; hKey
0x180009c45  call    cs:__imp_RegCloseKey
0x180009c4b  mov     rbx, r15
0x180009c4e  test    esi, esi
0x180009c50  jnz     short loc_180009C78
0x180009c52  cmp     [rsp+260h+cSubKeys], r15d
0x180009c57  jnz     short loc_180009C6A
0x180009c59  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180009c5d  lea     rcx, [rbp+160h+var_1E0]; this
0x180009c61  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009c66  mov     rdi, [rbp+160h+var_1E0]
0x180009c6a  test    rbx, rbx
0x180009c6d  jz      short loc_180009C78
0x180009c6f  mov     rcx, rbx; hKey
0x180009c72  call    cs:__imp_RegCloseKey
0x180009c78  test    rdi, rdi
0x180009c7b  jz      short loc_180009C86
0x180009c7d  mov     rcx, rdi; hKey
0x180009c80  call    cs:__imp_RegCloseKey
0x180009c86  mov     rcx, [rsp+260h+var_1F8]
0x180009c8b  test    rcx, rcx
0x180009c8e  jz      short loc_180009C9C
0x180009c90  mov     rax, [rcx]
0x180009c93  mov     rax, [rax+10h]
0x180009c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c9c  xor     eax, eax
0x180009c9e  mov     rcx, [rbp+160h+var_30]
0x180009ca5  xor     rcx, rsp; StackCookie
0x180009ca8  call    __security_check_cookie
0x180009cad  lea     r11, [rsp+260h+var_20]
0x180009cb5  mov     rbx, [r11+40h]
0x180009cb9  mov     rsi, [r11+48h]
0x180009cbd  mov     rsp, r11
0x180009cc0  pop     r15
0x180009cc2  pop     r14
0x180009cc4  pop     r12
0x180009cc6  pop     rdi
0x180009cc7  pop     rbp
0x180009cc8  retn
```
