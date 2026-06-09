# RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18002c6f4`
- end: `0x18002c907`
- name: `?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `28`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004c74`
- `0x180006824`
- `0x180028fb0`
- `0x18003a2e4`
- `0x1800409f8`
- `0x180056930`
- `0x18005714c`
- `0x1800576e4`
- `0x180057870`
- `0x18005a814`
- `0x18005cab8`
- `0x18005d854`
- `0x18005de2c`
- `0x18006da88`
- `0x18006de14`
- `0x18006de84`
- `0x18006dee0`
- `0x18007b190`
- `0x18007feac`
- `0x18008cca0`
- `0x180095b04`
- `0x180097ed8`
- `0x1800a25f0`
- `0x1800a3a60`
- `0x1800be5c0`
- `0x1800be7d0`
- `0x1800c1078`
- `0x1800c5c1c`

## callees

- `0x180017b98`
- `0x18002c6f4`
- `0x18002d82c`
- `0x18002de48`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002c7af`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002c7af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c77d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c77d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c80d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c88a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c8b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c80d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c88a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c8b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c74b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c74b`

## pseudocode

```c
__int64 __fastcall RegReadStringValueNoThrow(HKEY hKey, const WCHAR *a2, const WCHAR *a3, __int64 a4)
{
  DWORD v6; // eax
  HKEY v7; // r15
  unsigned int v8; // edi
  LSTATUS v9; // eax
  __int64 v10; // rdx
  size_t v11; // rax
  size_t v12; // rsi
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rcx
  size_t v15; // rcx
  _WORD *v16; // rdi
  _WORD *v17; // rcx
  char v19; // r14
  unsigned __int64 v20; // rdi
  unsigned __int64 v21; // rsi
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  _WORD *v24; // rdi
  _WORD *v25; // rcx
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKeya; // [rsp+88h] [rbp+58h] BYREF

  v6 = 2 * ((__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1);
  Type = 0;
  cbData = v6;
  v7 = hKey;
  hKeya = 0;
  if ( a2 && *a2 )
  {
    v8 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &hKeya);
    if ( !v8 )
    {
      v7 = hKeya;
      goto LABEL_5;
    }
LABEL_30:
    if ( hKeya )
      RegCloseKey(hKeya);
    return v8;
  }
  else
  {
LABEL_5:
    while ( 1 )
    {
      v9 = RegQueryValueExW(v7, a3, 0, &Type, *(LPBYTE *)a4, &cbData);
      v8 = v9;
      if ( v9 != 234 )
        break;
      v19 = 1;
      v20 = (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1;
      v21 = (unsigned __int64)cbData >> 1;
      if ( v20 < v21 )
      {
        if ( v21 <= utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(a4, v10)
          || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(
                                v22,
                                v21) )
        {
          v23 = v21 - v20;
          if ( v21 != v20 )
          {
            v24 = *(_WORD **)(a4 + 8);
            while ( v23 )
            {
              *v24++ = 0;
              --v23;
            }
          }
        }
        else
        {
          v19 = 0;
          v21 = v20;
        }
      }
      v25 = (_WORD *)(*(_QWORD *)a4 + 2 * v21);
      *(_QWORD *)(a4 + 8) = v25;
      *v25 = 0;
      if ( !v19 )
      {
        if ( hKeya )
          RegCloseKey(hKeya);
        return 14;
      }
    }
    if ( v9 )
      goto LABEL_30;
    if ( Type - 1 > 1 )
    {
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKeya);
      return 1630;
    }
    else
    {
      v11 = wcsnlen(*(const wchar_t **)a4, (unsigned __int64)cbData >> 1);
      v12 = v11;
      v13 = (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1;
      if ( v13 < v11 )
      {
        if ( *(_QWORD *)a4 == a4 + 16 )
          v14 = 7;
        else
          v14 = (__int64)(*(_QWORD *)(a4 + 16) - *(_QWORD *)a4) >> 1;
        if ( v11 <= v14
          || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(
                                a4,
                                v11) )
        {
          v15 = v12 - v13;
          if ( v12 != v13 )
          {
            v16 = *(_WORD **)(a4 + 8);
            while ( v15 )
            {
              *v16++ = 0;
              --v15;
            }
          }
        }
        else
        {
          v12 = v13;
        }
      }
      v17 = (_WORD *)(*(_QWORD *)a4 + 2 * v12);
      *(_QWORD *)(a4 + 8) = v17;
      *v17 = 0;
      if ( hKeya )
        RegCloseKey(hKeya);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18002c6f4  mov     [rsp-38h+arg_10], rbx
0x18002c6f9  push    rbp
0x18002c6fa  push    rsi
0x18002c6fb  push    rdi
0x18002c6fc  push    r12
0x18002c6fe  push    r13
0x18002c700  push    r14
0x18002c702  push    r15
0x18002c704  mov     rbp, rsp
0x18002c707  sub     rsp, 30h
0x18002c70b  mov     rax, [r9+8]
0x18002c70f  xor     r13d, r13d
0x18002c712  sub     rax, [r9]
0x18002c715  mov     rbx, r9
0x18002c718  sar     rax, 1
0x18002c71b  mov     r12, r8
0x18002c71e  add     eax, eax
0x18002c720  mov     [rbp+Type], r13d
0x18002c724  mov     [rbp+cbData], eax
0x18002c727  mov     r15, rcx
0x18002c72a  mov     [rbp+hKey], r13
0x18002c72e  test    rdx, rdx
0x18002c731  jz      short loc_18002C75F
0x18002c733  cmp     [rdx], r13w
0x18002c737  jz      short loc_18002C75F
0x18002c739  lea     rax, [rbp+hKey]
0x18002c73d  mov     r9d, 20019h; samDesired
0x18002c743  xor     r8d, r8d; ulOptions
0x18002c746  mov     [rsp+30h+phkResult], rax; phkResult
0x18002c74b  call    cs:__imp_RegOpenKeyExW
0x18002c751  mov     edi, eax
0x18002c753  test    eax, eax
0x18002c755  jnz     loc_18002C8A8
0x18002c75b  mov     r15, [rbp+hKey]
0x18002c75f  lea     rax, [rbp+cbData]
0x18002c763  xor     r8d, r8d; lpReserved
0x18002c766  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002c76b  lea     r9, [rbp+Type]; lpType
0x18002c76f  mov     rax, [rbx]
0x18002c772  mov     rdx, r12; lpValueName
0x18002c775  mov     rcx, r15; hKey
0x18002c778  mov     [rsp+30h+phkResult], rax; lpData
0x18002c77d  call    cs:__imp_RegQueryValueExW
0x18002c783  mov     edi, eax
0x18002c785  cmp     eax, 0EAh
0x18002c78a  jz      loc_18002C82D
0x18002c790  test    eax, eax
0x18002c792  jnz     loc_18002C8A8
0x18002c798  mov     eax, [rbp+Type]
0x18002c79b  dec     eax
0x18002c79d  cmp     eax, 1
0x18002c7a0  ja      loc_18002C8F4
0x18002c7a6  mov     edx, [rbp+cbData]
0x18002c7a9  mov     rcx, [rbx]; Source
0x18002c7ac  shr     rdx, 1; MaxCount
0x18002c7af  call    cs:__imp_wcsnlen
0x18002c7b5  mov     rdi, [rbx+8]
0x18002c7b9  mov     rsi, rax
0x18002c7bc  sub     rdi, [rbx]
0x18002c7bf  sar     rdi, 1
0x18002c7c2  cmp     rdi, rax
0x18002c7c5  jnb     short loc_18002C7F5
0x18002c7c7  lea     rcx, [rbx+10h]
0x18002c7cb  cmp     [rbx], rcx
0x18002c7ce  jnz     loc_18002C89A
0x18002c7d4  mov     ecx, 7
0x18002c7d9  cmp     rsi, rcx
0x18002c7dc  ja      loc_18002C8BE
0x18002c7e2  mov     rcx, rsi
0x18002c7e5  sub     rcx, rdi
0x18002c7e8  jz      short loc_18002C7F5
0x18002c7ea  mov     rdi, [rbx+8]
0x18002c7ee  movzx   eax, r13w
0x18002c7f2  rep stosw
0x18002c7f5  mov     rax, [rbx]
0x18002c7f8  lea     rcx, [rax+rsi*2]
0x18002c7fc  mov     [rbx+8], rcx
0x18002c800  mov     [rcx], r13w
0x18002c804  mov     rcx, [rbp+hKey]; hKey
0x18002c808  test    rcx, rcx
0x18002c80b  jz      short loc_18002C813
0x18002c80d  call    cs:__imp_RegCloseKey
0x18002c813  xor     eax, eax
0x18002c815  mov     rbx, [rsp+30h+arg_10]
0x18002c81d  add     rsp, 30h
0x18002c821  pop     r15
0x18002c823  pop     r14
0x18002c825  pop     r13
0x18002c827  pop     r12
0x18002c829  pop     rdi
0x18002c82a  pop     rsi
0x18002c82b  pop     rbp
0x18002c82c  retn
0x18002c82d  mov     rdi, [rbx+8]
0x18002c831  mov     r14b, 1
0x18002c834  sub     rdi, [rbx]
0x18002c837  mov     esi, [rbp+cbData]
0x18002c83a  sar     rdi, 1
0x18002c83d  shr     rsi, 1
0x18002c840  cmp     rdi, rsi
0x18002c843  jnb     short loc_18002C869
0x18002c845  mov     rcx, rbx
0x18002c848  call    ?capacity@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(void)
0x18002c84d  cmp     rsi, rax
0x18002c850  ja      loc_18002C8D9
0x18002c856  mov     rcx, rsi
0x18002c859  sub     rcx, rdi
0x18002c85c  jz      short loc_18002C869
0x18002c85e  mov     rdi, [rbx+8]
0x18002c862  movzx   eax, r13w
0x18002c866  rep stosw
0x18002c869  mov     rax, [rbx]
0x18002c86c  lea     rcx, [rax+rsi*2]
0x18002c870  mov     [rbx+8], rcx
0x18002c874  mov     [rcx], r13w
0x18002c878  test    r14b, r14b
0x18002c87b  jnz     loc_18002C75F
0x18002c881  mov     rcx, [rbp+hKey]; hKey
0x18002c885  test    rcx, rcx
0x18002c888  jz      short loc_18002C890
0x18002c88a  call    cs:__imp_RegCloseKey
0x18002c890  mov     eax, 0Eh
0x18002c895  jmp     loc_18002C815
0x18002c89a  mov     rcx, [rcx]
0x18002c89d  sub     rcx, [rbx]
0x18002c8a0  sar     rcx, 1
0x18002c8a3  jmp     loc_18002C7D9
0x18002c8a8  mov     rcx, [rbp+hKey]; hKey
0x18002c8ac  test    rcx, rcx
0x18002c8af  jz      short loc_18002C8B7
0x18002c8b1  call    cs:__imp_RegCloseKey
0x18002c8b7  mov     eax, edi
0x18002c8b9  jmp     loc_18002C815
0x18002c8be  mov     rdx, rsi
0x18002c8c1  mov     rcx, rbx
0x18002c8c4  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(unsigned __int64)
0x18002c8c9  test    al, al
0x18002c8cb  jnz     loc_18002C7E2
0x18002c8d1  mov     rsi, rdi
0x18002c8d4  jmp     loc_18002C7F5
0x18002c8d9  mov     rdx, rsi
0x18002c8dc  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(unsigned __int64)
0x18002c8e1  test    al, al
0x18002c8e3  jnz     loc_18002C856
0x18002c8e9  mov     r14b, r13b
0x18002c8ec  mov     rsi, rdi
0x18002c8ef  jmp     loc_18002C869
0x18002c8f4  lea     rcx, [rbp+hKey]
0x18002c8f8  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18002c8fd  mov     eax, 65Eh
0x18002c902  jmp     loc_18002C815
```
