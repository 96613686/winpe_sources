# CAccountFilter::_InitializeOnce(void)

- ea: `0x18000b660`
- end: `0x18000b81f`
- name: `?_InitializeOnce@CAccountFilter@@AEAAJXZ`
- size: `447`
- prototype: `__int64 __fastcall(CAccountFilter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b630`

## callees

- `0x18000b660`
- `0x18000d764`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b695`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b695`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b6ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b6ef`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000b7a8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000b7a8`

## pseudocode

```c
LSTATUS __fastcall CAccountFilter::_InitializeOnce(CAccountFilter *this)
{
  unsigned int v2; // ebx
  LSTATUS result; // eax
  LSTATUS v4; // eax
  unsigned __int64 v5; // rax
  void *v6; // rax
  DWORD i; // esi
  __int64 v8; // rdx
  LPDWORD lpcbMaxClassLen; // [rsp+30h] [rbp-58h]
  DWORD cchValueName; // [rsp+60h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-20h] BYREF
  DWORD cValues; // [rsp+98h] [rbp+10h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+20h] BYREF

  hKey = 0;
  v2 = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\SpecialAccounts\\UserList",
             0,
             1u,
             &hKey);
  if ( !result )
  {
    cValues = 0;
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    if ( v4 )
    {
      if ( v4 != 2 )
      {
        if ( v4 > 0 )
          v2 = (unsigned __int16)v4 | 0x80070000;
        else
          v2 = v4;
      }
    }
    else if ( cValues )
    {
      v5 = 520LL * cValues;
      if ( !is_mul_ok(cValues, 0x208u) )
        v5 = -1;
      v6 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 2) = v6;
      if ( v6 )
      {
        for ( i = 0; i < cValues; ++i )
        {
          v8 = 520LL * *((unsigned int *)this + 6);
          Type = 0;
          lpcbMaxClassLen = (LPDWORD)(*((_QWORD *)this + 2) + v8);
          cchValueName = 257;
          cbData = 4;
          if ( !RegEnumValueW(
                  hKey,
                  i,
                  (LPWSTR)lpcbMaxClassLen + 2,
                  &cchValueName,
                  0,
                  &Type,
                  (LPBYTE)lpcbMaxClassLen,
                  &cbData)
            && Type == 4 )
          {
            ++*((_DWORD *)this + 6);
          }
        }
      }
      else
      {
        v2 = -2147024882;
      }
    }
    RegCloseKey(hKey);
    return v2;
  }
  if ( result == 2 )
    return v2;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000b660  push    rbx
0x18000b662  push    rbp
0x18000b663  push    rdi
0x18000b664  sub     rsp, 70h
0x18000b668  mov     rdi, rcx
0x18000b66b  lea     rax, [rsp+88h+hKey]
0x18000b670  xor     ebp, ebp
0x18000b672  mov     [rsp+88h+phkResult], rax; phkResult
0x18000b677  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b67e  mov     [rsp+88h+hKey], rbp
0x18000b683  mov     r9d, 1; samDesired
0x18000b689  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000b690  xor     r8d, r8d; ulOptions
0x18000b693  mov     ebx, ebp
0x18000b695  call    cs:__imp_RegOpenKeyExW
0x18000b69b  test    eax, eax
0x18000b69d  jnz     loc_18000B806
0x18000b6a3  mov     rcx, [rsp+88h+hKey]; hKey
0x18000b6a8  lea     rax, [rsp+88h+cValues]
0x18000b6b0  mov     [rsp+88h+lpftLastWriteTime], rbp; lpftLastWriteTime
0x18000b6b5  xor     r9d, r9d; lpReserved
0x18000b6b8  mov     [rsp+88h+lpcbSecurityDescriptor], rbp; lpcbSecurityDescriptor
0x18000b6bd  xor     r8d, r8d; lpcchClass
0x18000b6c0  mov     [rsp+88h+lpcbMaxValueLen], rbp; lpcbMaxValueLen
0x18000b6c5  xor     edx, edx; lpClass
0x18000b6c7  mov     [rsp+88h+lpcbMaxValueNameLen], rbp; lpcbMaxValueNameLen
0x18000b6cc  mov     [rsp+88h+lpcValues], rax; lpcValues
0x18000b6d1  mov     [rsp+88h+lpcbMaxClassLen], rbp; lpcbMaxClassLen
0x18000b6d6  mov     [rsp+88h+lpcbMaxSubKeyLen], rbp; lpcbMaxSubKeyLen
0x18000b6db  mov     [rsp+88h+phkResult], rbp; lpcSubKeys
0x18000b6e0  mov     [rsp+88h+arg_0], rsi
0x18000b6e8  mov     [rsp+88h+cValues], ebp
0x18000b6ef  call    cs:__imp_RegQueryInfoKeyW
0x18000b6f5  test    eax, eax
0x18000b6f7  jnz     loc_18000B7D3
0x18000b6fd  mov     eax, [rsp+88h+cValues]
0x18000b704  test    eax, eax
0x18000b706  jz      loc_18000B7E9
0x18000b70c  mov     ecx, eax
0x18000b70e  mov     eax, 208h
0x18000b713  mul     rcx
0x18000b716  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b71d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b724  cmovb   rax, rcx
0x18000b728  mov     rcx, rax; unsigned __int64
0x18000b72b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b730  mov     [rdi+10h], rax
0x18000b734  test    rax, rax
0x18000b737  jz      loc_18000B7CC
0x18000b73d  mov     esi, ebp
0x18000b73f  cmp     [rsp+88h+cValues], ebx
0x18000b746  jbe     loc_18000B7E9
0x18000b74c  mov     eax, [rdi+18h]
0x18000b74f  lea     r9, [rsp+88h+cchValueName]; lpcchValueName
0x18000b754  mov     rcx, [rsp+88h+hKey]; hKey
0x18000b759  imul    rdx, rax, 208h
0x18000b760  lea     rax, [rsp+88h+cbData]
0x18000b768  mov     [rsp+88h+Type], ebp
0x18000b76f  add     rdx, [rdi+10h]
0x18000b773  mov     [rsp+88h+lpcValues], rax; lpcbData
0x18000b778  lea     rax, [rsp+88h+Type]
0x18000b780  mov     [rsp+88h+lpcbMaxClassLen], rdx; lpData
0x18000b785  mov     [rsp+88h+lpcbMaxSubKeyLen], rax; lpType
0x18000b78a  lea     r8, [rdx+4]; lpValueName
0x18000b78e  mov     [rsp+88h+cchValueName], 101h
0x18000b796  mov     edx, esi; dwIndex
0x18000b798  mov     [rsp+88h+cbData], 4
0x18000b7a3  mov     [rsp+88h+phkResult], rbp; lpReserved
0x18000b7a8  call    cs:__imp_RegEnumValueW
0x18000b7ae  test    eax, eax
0x18000b7b0  jnz     short loc_18000B7BF
0x18000b7b2  cmp     [rsp+88h+Type], 4
0x18000b7ba  jnz     short loc_18000B7BF
0x18000b7bc  inc     dword ptr [rdi+18h]
0x18000b7bf  inc     esi
0x18000b7c1  cmp     esi, [rsp+88h+cValues]
0x18000b7c8  jb      short loc_18000B74C
0x18000b7ca  jmp     short loc_18000B7E9
0x18000b7cc  mov     ebx, 8007000Eh
0x18000b7d1  jmp     short loc_18000B7E9
0x18000b7d3  cmp     eax, 2
0x18000b7d6  jz      short loc_18000B7E9
0x18000b7d8  test    eax, eax
0x18000b7da  jg      short loc_18000B7E0
0x18000b7dc  mov     ebx, eax
0x18000b7de  jmp     short loc_18000B7E9
0x18000b7e0  movzx   ebx, ax
0x18000b7e3  or      ebx, 80070000h
0x18000b7e9  mov     rcx, [rsp+88h+hKey]; hKey
0x18000b7ee  call    cs:__imp_RegCloseKey
0x18000b7f4  mov     rsi, [rsp+88h+arg_0]
0x18000b7fc  mov     eax, ebx
0x18000b7fe  add     rsp, 70h
0x18000b802  pop     rdi
0x18000b803  pop     rbp
0x18000b804  pop     rbx
0x18000b805  retn
0x18000b806  cmp     eax, 2
0x18000b809  jz      short loc_18000B7FC
0x18000b80b  test    eax, eax
0x18000b80d  jle     short loc_18000B7FE
0x18000b80f  movzx   eax, ax
0x18000b812  or      eax, 80070000h
0x18000b817  add     rsp, 70h
0x18000b81b  pop     rdi
0x18000b81c  pop     rbp
0x18000b81d  pop     rbx
0x18000b81e  retn
```
