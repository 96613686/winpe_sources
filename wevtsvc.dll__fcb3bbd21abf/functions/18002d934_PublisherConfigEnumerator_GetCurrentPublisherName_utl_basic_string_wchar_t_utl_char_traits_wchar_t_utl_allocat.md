# PublisherConfigEnumerator::GetCurrentPublisherName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18002d934`
- end: `0x18002dac0`
- name: `?GetCurrentPublisherName@PublisherConfigEnumerator@@QEAA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18007b190`
- `0x18007feac`
- `0x1800a3a60`

## callees

- `0x180017b98`
- `0x18002d82c`
- `0x18002d934`
- `0x18002de48`
- `0x18002de9c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002d9ee`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002d9ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d9bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d9bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d986`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d986`

## pseudocode

```c
bool __fastcall PublisherConfigEnumerator::GetCurrentPublisherName(HKEY *a1, __int64 a2)
{
  HKEY v2; // rsi
  const WCHAR *v4; // rdx
  LSTATUS v5; // edi
  LSTATUS v6; // eax
  size_t v7; // rsi
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  size_t v10; // rcx
  _WORD *v11; // rdi
  _WORD *v12; // rcx
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  v2 = *a1;
  v4 = (const WCHAR *)a1[2];
  Type = 0;
  hKey = 0;
  cbData = 2 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1);
  if ( v4 && *v4 )
  {
    v5 = RegOpenKeyExW(v2, v4, 0, 0x20019u, &hKey);
    if ( !v5 )
    {
      v2 = hKey;
      goto LABEL_5;
    }
LABEL_22:
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
LABEL_5:
    while ( 1 )
    {
      v6 = RegQueryValueExW(v2, &pszFormat, 0, &Type, *(LPBYTE *)a2, &cbData);
      v5 = v6;
      if ( v6 != 234 )
        break;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                               a2,
                               (unsigned __int64)cbData >> 1) )
      {
        if ( hKey )
          RegCloseKey(hKey);
        v5 = 14;
        return v5 == 0;
      }
    }
    if ( v6 )
      goto LABEL_22;
    if ( Type - 1 > 1 )
    {
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      v5 = 1630;
    }
    else
    {
      v7 = wcsnlen(*(const wchar_t **)a2, (unsigned __int64)cbData >> 1);
      v8 = (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1;
      if ( v8 < v7 )
      {
        if ( v7 <= utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(a2)
          || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(
                                v9,
                                v7) )
        {
          v10 = v7 - v8;
          if ( v7 != v8 )
          {
            v11 = *(_WORD **)(a2 + 8);
            while ( v10 )
            {
              *v11++ = 0;
              --v10;
            }
          }
        }
        else
        {
          v7 = v8;
        }
      }
      v12 = (_WORD *)(*(_QWORD *)a2 + 2 * v7);
      *(_QWORD *)(a2 + 8) = v12;
      *v12 = 0;
      if ( hKey )
        RegCloseKey(hKey);
      v5 = 0;
    }
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x18002d934  push    rbp
0x18002d936  push    rbx
0x18002d937  push    rsi
0x18002d938  push    rdi
0x18002d939  push    r14
0x18002d93b  mov     rbp, rsp
0x18002d93e  sub     rsp, 30h
0x18002d942  mov     rsi, [rcx]
0x18002d945  mov     rbx, rdx
0x18002d948  mov     rdx, [rcx+10h]; lpSubKey
0x18002d94c  xor     r14d, r14d
0x18002d94f  mov     [rbp+Type], r14d
0x18002d953  mov     [rbp+hKey], r14
0x18002d957  mov     rax, [rbx+8]
0x18002d95b  sub     rax, [rbx]
0x18002d95e  sar     rax, 1
0x18002d961  add     eax, eax
0x18002d963  mov     [rbp+cbData], eax
0x18002d966  test    rdx, rdx
0x18002d969  jz      short loc_18002D99A
0x18002d96b  cmp     [rdx], r14w
0x18002d96f  jz      short loc_18002D99A
0x18002d971  lea     rax, [rbp+hKey]
0x18002d975  mov     r9d, 20019h; samDesired
0x18002d97b  xor     r8d, r8d; ulOptions
0x18002d97e  mov     [rsp+30h+phkResult], rax; phkResult
0x18002d983  mov     rcx, rsi; hKey
0x18002d986  call    cs:__imp_RegOpenKeyExW
0x18002d98c  mov     edi, eax
0x18002d98e  test    eax, eax
0x18002d990  jnz     loc_18002DA87
0x18002d996  mov     rsi, [rbp+hKey]
0x18002d99a  lea     rax, [rbp+cbData]
0x18002d99e  xor     r8d, r8d; lpReserved
0x18002d9a1  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002d9a6  lea     r9, [rbp+Type]; lpType
0x18002d9aa  mov     rax, [rbx]
0x18002d9ad  lea     rdx, pszFormat; lpValueName
0x18002d9b4  mov     rcx, rsi; hKey
0x18002d9b7  mov     [rsp+30h+phkResult], rax; lpData
0x18002d9bc  call    cs:__imp_RegQueryValueExW
0x18002d9c2  mov     edi, eax
0x18002d9c4  cmp     eax, 0EAh
0x18002d9c9  jz      loc_18002DA5B
0x18002d9cf  test    eax, eax
0x18002d9d1  jnz     loc_18002DA87
0x18002d9d7  mov     eax, [rbp+Type]
0x18002d9da  dec     eax
0x18002d9dc  cmp     eax, 1
0x18002d9df  ja      loc_18002DAB0
0x18002d9e5  mov     edx, [rbp+cbData]
0x18002d9e8  mov     rcx, [rbx]; Source
0x18002d9eb  shr     rdx, 1; MaxCount
0x18002d9ee  call    cs:__imp_wcsnlen
0x18002d9f4  mov     rdi, [rbx+8]
0x18002d9f8  mov     rsi, rax
0x18002d9fb  sub     rdi, [rbx]
0x18002d9fe  sar     rdi, 1
0x18002da01  cmp     rdi, rax
0x18002da04  jnb     short loc_18002DA2A
0x18002da06  mov     rcx, rbx
0x18002da09  call    ?capacity@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(void)
0x18002da0e  cmp     rsi, rax
0x18002da11  ja      loc_18002DA98
0x18002da17  mov     rcx, rsi
0x18002da1a  sub     rcx, rdi
0x18002da1d  jz      short loc_18002DA2A
0x18002da1f  mov     rdi, [rbx+8]
0x18002da23  movzx   eax, r14w
0x18002da27  rep stosw
0x18002da2a  mov     rax, [rbx]
0x18002da2d  lea     rcx, [rax+rsi*2]
0x18002da31  mov     [rbx+8], rcx
0x18002da35  mov     [rcx], r14w
0x18002da39  mov     rcx, [rbp+hKey]; hKey
0x18002da3d  test    rcx, rcx
0x18002da40  jz      short loc_18002DA48
0x18002da42  call    cs:__imp_RegCloseKey
0x18002da48  mov     edi, r14d
0x18002da4b  test    edi, edi
0x18002da4d  setz    al
0x18002da50  add     rsp, 30h
0x18002da54  pop     r14
0x18002da56  pop     rdi
0x18002da57  pop     rsi
0x18002da58  pop     rbx
0x18002da59  pop     rbp
0x18002da5a  retn
0x18002da5b  mov     edx, [rbp+cbData]
0x18002da5e  mov     rcx, rbx
0x18002da61  shr     rdx, 1
0x18002da64  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18002da69  test    al, al
0x18002da6b  jnz     loc_18002D99A
0x18002da71  mov     rcx, [rbp+hKey]; hKey
0x18002da75  test    rcx, rcx
0x18002da78  jz      short loc_18002DA80
0x18002da7a  call    cs:__imp_RegCloseKey
0x18002da80  mov     edi, 0Eh
0x18002da85  jmp     short loc_18002DA4B
0x18002da87  mov     rcx, [rbp+hKey]; hKey
0x18002da8b  test    rcx, rcx
0x18002da8e  jz      short loc_18002DA4B
0x18002da90  call    cs:__imp_RegCloseKey
0x18002da96  jmp     short loc_18002DA4B
0x18002da98  mov     rdx, rsi
0x18002da9b  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(unsigned __int64)
0x18002daa0  test    al, al
0x18002daa2  jnz     loc_18002DA17
0x18002daa8  mov     rsi, rdi
0x18002daab  jmp     loc_18002DA2A
0x18002dab0  lea     rcx, [rbp+hKey]
0x18002dab4  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18002dab9  mov     edi, 65Eh
0x18002dabe  jmp     short loc_18002DA4B
```
