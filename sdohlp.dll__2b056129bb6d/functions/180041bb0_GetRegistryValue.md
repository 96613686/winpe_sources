# GetRegistryValue

- ea: `0x180041bb0`
- end: `0x18004204d`
- name: `GetRegistryValue`
- size: `1181`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18003a880`

## callees

- `0x1800241bb`
- `0x180025264`
- `0x18002cca4`
- `0x18002cd00`
- `0x18002cd74`
- `0x18002d08c`
- `0x18002efa0`
- `0x18002f08c`
- `0x180039924`
- `0x1800404a4`
- `0x180041bb0`
- `0x180042054`
- `0x180042a80`

## import_xrefs

- `msvcrt!free` at `0x180042033`
- `msvcrt!free` at `0x180042033`
- `ADVAPI32!RegOpenKeyExW` at `0x180041be9`
- `ADVAPI32!RegOpenKeyExW` at `0x180041be9`
- `ADVAPI32!RegQueryValueExW` at `0x180041c87`
- `ADVAPI32!RegQueryValueExW` at `0x180041da2`
- `ADVAPI32!RegQueryValueExW` at `0x180041c87`
- `ADVAPI32!RegQueryValueExW` at `0x180041da2`
- `ADVAPI32!RegCloseKey` at `0x180042025`
- `ADVAPI32!RegCloseKey` at `0x180042025`
- `OLEAUT32!__imp_SysAllocString` at `0x180041feb`
- `OLEAUT32!__imp_SysAllocString` at `0x180042012`
- `OLEAUT32!__imp_SysAllocString` at `0x180041feb`
- `OLEAUT32!__imp_SysAllocString` at `0x180042012`
- `OLEAUT32!__imp_VariantInit` at `0x180041e7f`
- `OLEAUT32!__imp_VariantInit` at `0x180041e7f`

## string_xrefs

- `0x180041c23`: `RegOpenKeyEx (HKLM\%S) failed with 0x%x`
- `0x180041d41`: `Not enough memory to allocate registry value`
- `0x180041e41`: `Mismatched registry value type %S`

## pseudocode

```c
__int64 __fastcall GetRegistryValue(HKEY a1, const WCHAR *a2, wchar_t *a3, const WCHAR *a4, VARIANTARG *pvarg)
{
  BYTE *v8; // rdi
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  const struct std::nothrow_t *v11; // rdx
  BYTE *v12; // rax
  LSTATUS v13; // eax
  int RegistryValueType; // eax
  const unsigned __int16 *v15; // r14
  __int64 v16; // rax
  const OLECHAR *v17; // rcx
  DWORD Type; // [rsp+40h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-3Ch] BYREF
  const OLECHAR **v21; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v23[8]; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v24[8]; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v25[8]; // [rsp+68h] [rbp-18h] BYREF
  _BYTE v26[16]; // [rsp+70h] [rbp-10h] BYREF

  hKey = 0;
  v8 = 0;
  v9 = RegOpenKeyExW(a1, a2, 0, 1u, &hKey);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("RegOpenKeyEx (HKLM\\%S) failed with 0x%x");
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        (__int64)a2,
        v9);
    }
    goto LABEL_47;
  }
  cbData = 0;
  Type = 0;
  v10 = RegQueryValueExW(hKey, a4, 0, &Type, 0, &cbData);
  v9 = v10;
  if ( v10 )
  {
    if ( v10 == 2
      || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_47;
    }
    goto LABEL_11;
  }
  v12 = (BYTE *)operator new[](cbData, v11);
  v8 = v12;
  if ( v12 )
  {
    memset_0(v12, 0, cbData);
    v13 = RegQueryValueExW(hKey, a4, 0, &Type, v8, &cbData);
    v9 = v13;
    if ( v13 )
    {
      if ( v13 == 2
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_47;
      }
LABEL_11:
      WppDbgPrint("RegQueryValueEx(%S\\%S) failed with 0x%x");
      WPP_SF_sSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a4, v9);
      goto LABEL_47;
    }
    RegistryValueType = GetRegistryValueType(a3);
    if ( Type == RegistryValueType )
    {
      VariantInit(pvarg);
      switch ( Type )
      {
        case 1u:
          pvarg->vt = 8;
          pvarg->llVal = (LONGLONG)SysAllocString((const OLECHAR *)v8);
          break;
        case 4u:
          pvarg->vt = 3;
          pvarg->lVal = *(_DWORD *)v8;
          break;
        case 7u:
          pvarg->vt = 8;
          v15 = (const unsigned __int16 *)v8;
          v21 = 0;
          if ( !*(_WORD *)v8 )
            goto LABEL_43;
          do
          {
            _bstr_t::_bstr_t((_bstr_t *)v23, L"\"");
            _bstr_t::operator+=((struct _bstr_t *)&v21, (struct _bstr_t *)v23);
            _bstr_t::_Free((_bstr_t *)v23);
            _bstr_t::_bstr_t((_bstr_t *)v24, v15);
            _bstr_t::operator+=((struct _bstr_t *)&v21, (struct _bstr_t *)v24);
            _bstr_t::_Free((_bstr_t *)v24);
            _bstr_t::_bstr_t((_bstr_t *)v25, L"\"");
            _bstr_t::operator+=((struct _bstr_t *)&v21, (struct _bstr_t *)v25);
            _bstr_t::_Free((_bstr_t *)v25);
            v16 = -1;
            do
              ++v16;
            while ( v15[v16] );
            v15 += v16 + 1;
            if ( !*v15 )
              break;
            _bstr_t::_bstr_t((_bstr_t *)v26, L",");
            _bstr_t::operator+=((struct _bstr_t *)&v21, (struct _bstr_t *)v26);
            _bstr_t::_Free((_bstr_t *)v26);
          }
          while ( *v15 );
          if ( v21 )
            v17 = *v21;
          else
LABEL_43:
            v17 = 0;
          pvarg->llVal = (LONGLONG)SysAllocString(v17);
          _bstr_t::_Free((_bstr_t *)&v21);
          break;
        default:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WppDbgPrint("Unexpected reg type %d");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
              (unsigned int)"NAPBASE",
              Type);
          }
          break;
      }
    }
    else
    {
      v9 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WppDbgPrint("Mismatched registry value type %S");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
          (unsigned int)"NAPBASE",
          (__int64)a3);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("Not enough memory to allocate registry value");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids, "NAPBASE");
    }
    v9 = 14;
  }
LABEL_47:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    free(v8);
  return v9;
}

```

## disassembly

```asm
0x180041bb0  push    rbp
0x180041bb2  push    rbx
0x180041bb3  push    rsi
0x180041bb4  push    rdi
0x180041bb5  push    r12
0x180041bb7  push    r14
0x180041bb9  push    r15
0x180041bbb  mov     rbp, rsp
0x180041bbe  sub     rsp, 80h
0x180041bc5  xor     r12d, r12d
0x180041bc8  lea     rax, [rbp+hKey]
0x180041bcc  mov     r14, r9
0x180041bcf  mov     [rbp+hKey], r12
0x180041bd3  mov     r15, r8
0x180041bd6  mov     [rsp+80h+phkResult], rax; phkResult
0x180041bdb  xor     r8d, r8d; ulOptions
0x180041bde  mov     rsi, rdx
0x180041be1  lea     r9d, [r12+1]; samDesired
0x180041be6  mov     edi, r12d
0x180041be9  call    cs:__imp_RegOpenKeyExW
0x180041bef  mov     ebx, eax
0x180041bf1  test    eax, eax
0x180041bf3  jz      short loc_180041C63
0x180041bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180041bfc  lea     rax, WPP_GLOBAL_Control
0x180041c03  cmp     rcx, rax
0x180041c06  jz      loc_18004201C
0x180041c0c  cmp     byte ptr [rcx+19h], 2
0x180041c10  jb      loc_18004201C
0x180041c16  test    byte ptr [rcx+1Ch], 1
0x180041c1a  jz      loc_18004201C
0x180041c20  mov     r8d, ebx
0x180041c23  lea     rcx, aRegopenkeyexHk; "RegOpenKeyEx (HKLM\\%S) failed with 0x%"...
0x180041c2a  mov     rdx, rsi
0x180041c2d  call    WppDbgPrint
0x180041c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c39  lea     edx, [r12+22h]
0x180041c3e  mov     dword ptr [rsp+80h+lpcbData], ebx
0x180041c42  lea     r9, aNapbase; "NAPBASE"
0x180041c49  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180041c50  mov     [rsp+80h+phkResult], rsi
0x180041c55  mov     rcx, [rcx+10h]
0x180041c59  call    WPP_SF_sSd
0x180041c5e  jmp     loc_18004201C
0x180041c63  mov     rcx, [rbp+hKey]; hKey
0x180041c67  lea     rax, [rbp+cbData]
0x180041c6b  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180041c70  lea     r9, [rbp+Type]; lpType
0x180041c74  xor     r8d, r8d; lpReserved
0x180041c77  mov     [rsp+80h+phkResult], r12; lpData
0x180041c7c  mov     rdx, r14; lpValueName
0x180041c7f  mov     [rbp+cbData], r12d
0x180041c83  mov     [rbp+Type], r12d
0x180041c87  call    cs:__imp_RegQueryValueExW
0x180041c8d  mov     ebx, eax
0x180041c8f  test    eax, eax
0x180041c91  jz      short loc_180041D12
0x180041c93  cmp     eax, 2
0x180041c96  jz      loc_18004201C
0x180041c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ca3  lea     rax, WPP_GLOBAL_Control
0x180041caa  cmp     rcx, rax
0x180041cad  jz      loc_18004201C
0x180041cb3  cmp     byte ptr [rcx+19h], 2
0x180041cb7  jb      loc_18004201C
0x180041cbd  test    byte ptr [rcx+1Ch], 1
0x180041cc1  jz      loc_18004201C
0x180041cc7  mov     r9d, ebx
0x180041cca  lea     rcx, aRegqueryvaluee; "RegQueryValueEx(%S\\%S) failed with 0x%"...
0x180041cd1  mov     r8, r14
0x180041cd4  mov     rdx, rsi
0x180041cd7  call    WppDbgPrint
0x180041cdc  mov     edx, 23h ; '#'
0x180041ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ce8  lea     r9, aNapbase; "NAPBASE"
0x180041cef  mov     dword ptr [rsp+80h+var_50], ebx; char
0x180041cf3  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180041cfa  mov     [rsp+80h+lpcbData], r14; __int64
0x180041cff  mov     [rsp+80h+phkResult], rsi; __int64
0x180041d04  mov     rcx, [rcx+10h]; LoggerHandle
0x180041d08  call    WPP_SF_sSSD
0x180041d0d  jmp     loc_18004201C
0x180041d12  mov     ecx, [rbp+cbData]; Size
0x180041d15  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180041d1a  mov     rdi, rax
0x180041d1d  test    rax, rax
0x180041d20  jnz     short loc_180041D78
0x180041d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d29  lea     rax, WPP_GLOBAL_Control
0x180041d30  cmp     rcx, rax
0x180041d33  jz      short loc_180041D6E
0x180041d35  cmp     byte ptr [rcx+19h], 2
0x180041d39  jb      short loc_180041D6E
0x180041d3b  test    byte ptr [rcx+1Ch], 1
0x180041d3f  jz      short loc_180041D6E
0x180041d41  lea     rcx, aNotEnoughMemor_0; "Not enough memory to allocate registry "...
0x180041d48  call    WppDbgPrint
0x180041d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d54  lea     edx, [rdi+24h]
0x180041d57  lea     r9, aNapbase; "NAPBASE"
0x180041d5e  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180041d65  mov     rcx, [rcx+10h]
0x180041d69  call    WPP_SF_s
0x180041d6e  mov     ebx, 0Eh
0x180041d73  jmp     loc_18004201C
0x180041d78  mov     r8d, [rbp+cbData]; Size
0x180041d7c  xor     edx, edx; Val
0x180041d7e  mov     rcx, rdi; void *
0x180041d81  call    memset_0
0x180041d86  mov     rcx, [rbp+hKey]; hKey
0x180041d8a  lea     rax, [rbp+cbData]
0x180041d8e  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180041d93  lea     r9, [rbp+Type]; lpType
0x180041d97  xor     r8d, r8d; lpReserved
0x180041d9a  mov     [rsp+80h+phkResult], rdi; lpData
0x180041d9f  mov     rdx, r14; lpValueName
0x180041da2  call    cs:__imp_RegQueryValueExW
0x180041da8  mov     ebx, eax
0x180041daa  test    eax, eax
0x180041dac  jz      short loc_180041E01
0x180041dae  cmp     eax, 2
0x180041db1  jz      loc_18004201C
0x180041db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180041dbe  lea     rax, WPP_GLOBAL_Control
0x180041dc5  cmp     rcx, rax
0x180041dc8  jz      loc_18004201C
0x180041dce  cmp     byte ptr [rcx+19h], 2
0x180041dd2  jb      loc_18004201C
0x180041dd8  test    byte ptr [rcx+1Ch], 1
0x180041ddc  jz      loc_18004201C
0x180041de2  mov     r9d, ebx
0x180041de5  lea     rcx, aRegqueryvaluee; "RegQueryValueEx(%S\\%S) failed with 0x%"...
0x180041dec  mov     r8, r14
0x180041def  mov     rdx, rsi
0x180041df2  call    WppDbgPrint
0x180041df7  mov     edx, 25h ; '%'
0x180041dfc  jmp     loc_180041CE1
0x180041e01  mov     rcx, r15; String1
0x180041e04  call    GetRegistryValueType
0x180041e09  cmp     [rbp+Type], eax
0x180041e0c  jz      short loc_180041E78
0x180041e0e  mov     ebx, 57h ; 'W'
0x180041e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e1a  lea     rax, WPP_GLOBAL_Control
0x180041e21  cmp     rcx, rax
0x180041e24  jz      loc_18004201C
0x180041e2a  cmp     byte ptr [rcx+19h], 2
0x180041e2e  jb      loc_18004201C
0x180041e34  test    byte ptr [rcx+1Ch], 1
0x180041e38  jz      loc_18004201C
0x180041e3e  mov     rdx, r15
0x180041e41  lea     rcx, aMismatchedRegi; "Mismatched registry value type %S"
0x180041e48  call    WppDbgPrint
0x180041e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e54  lea     edx, [rbx-31h]
0x180041e57  lea     r9, aNapbase; "NAPBASE"
0x180041e5e  mov     [rsp+80h+phkResult], r15
0x180041e63  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180041e6a  mov     rcx, [rcx+10h]
0x180041e6e  call    WPP_SF_sS
0x180041e73  jmp     loc_18004201C
0x180041e78  mov     rsi, [rbp+pvarg]
0x180041e7c  mov     rcx, rsi; pvarg
0x180041e7f  call    cs:__imp_VariantInit
0x180041e85  mov     edx, [rbp+Type]
0x180041e88  mov     eax, edx
0x180041e8a  sub     eax, 1
0x180041e8d  jz      loc_18004200A
0x180041e93  mov     ecx, 3
0x180041e98  sub     eax, ecx
0x180041e9a  jz      loc_180042000
0x180041ea0  cmp     eax, ecx
0x180041ea2  jz      short loc_180041F0A
0x180041ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180041eab  lea     rax, WPP_GLOBAL_Control
0x180041eb2  cmp     rcx, rax
0x180041eb5  jz      loc_18004201C
0x180041ebb  cmp     byte ptr [rcx+19h], 2
0x180041ebf  jb      loc_18004201C
0x180041ec5  test    byte ptr [rcx+1Ch], 1
0x180041ec9  jz      loc_18004201C
0x180041ecf  lea     rcx, aUnexpectedRegT; "Unexpected reg type %d"
0x180041ed6  call    WppDbgPrint
0x180041edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ee2  lea     r9, aNapbase; "NAPBASE"
0x180041ee9  mov     eax, [rbp+Type]
0x180041eec  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180041ef3  mov     edx, 27h ; '''
0x180041ef8  mov     dword ptr [rsp+80h+phkResult], eax
0x180041efc  mov     rcx, [rcx+10h]
0x180041f00  call    WPP_SF_sd
0x180041f05  jmp     loc_18004201C
0x180041f0a  mov     word ptr [rsi], 8
0x180041f0f  mov     r14, rdi
0x180041f12  mov     [rbp+var_38], r12
0x180041f16  cmp     [rdi], r12w
0x180041f1a  jz      loc_180041FE8
0x180041f20  lea     rdx, asc_180065CAC; "\""
0x180041f27  lea     rcx, [rbp+var_28]; this
0x180041f2b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180041f30  lea     rdx, [rbp+var_28]; struct _bstr_t *
0x180041f34  lea     rcx, [rbp+var_38]; struct _bstr_t *
0x180041f38  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180041f3d  lea     rcx, [rbp+var_28]; this
0x180041f41  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180041f46  mov     rdx, r14; unsigned __int16 *
0x180041f49  lea     rcx, [rbp+var_20]; this
0x180041f4d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180041f52  lea     rdx, [rbp+var_20]; struct _bstr_t *
0x180041f56  lea     rcx, [rbp+var_38]; struct _bstr_t *
0x180041f5a  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180041f5f  lea     rcx, [rbp+var_20]; this
0x180041f63  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180041f68  lea     rdx, asc_180065CAC; "\""
0x180041f6f  lea     rcx, [rbp+var_18]; this
0x180041f73  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180041f78  lea     rdx, [rbp+var_18]; struct _bstr_t *
0x180041f7c  lea     rcx, [rbp+var_38]; struct _bstr_t *
0x180041f80  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180041f85  lea     rcx, [rbp+var_18]; this
0x180041f89  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180041f8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041f92  inc     rax
0x180041f95  cmp     [r14+rax*2], r12w
0x180041f9a  jnz     short loc_180041F92
0x180041f9c  lea     r14, [r14+rax*2]
0x180041fa0  add     r14, 2
0x180041fa4  cmp     [r14], r12w
0x180041fa8  jz      short loc_180041FDA
0x180041faa  lea     rdx, asc_180065CB0; ","
0x180041fb1  lea     rcx, [rbp+var_10]; this
0x180041fb5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180041fba  lea     rdx, [rbp+var_10]; struct _bstr_t *
0x180041fbe  lea     rcx, [rbp+var_38]; struct _bstr_t *
0x180041fc2  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180041fc7  lea     rcx, [rbp+var_10]; this
0x180041fcb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180041fd0  cmp     [r14], r12w
0x180041fd4  jnz     loc_180041F20
0x180041fda  mov     rax, [rbp+var_38]
0x180041fde  test    rax, rax
0x180041fe1  jz      short loc_180041FE8
0x180041fe3  mov     rcx, [rax]
0x180041fe6  jmp     short loc_180041FEB
0x180041fe8  mov     rcx, r12; psz
0x180041feb  call    cs:__imp_SysAllocString
0x180041ff1  lea     rcx, [rbp+var_38]; this
0x180041ff5  mov     [rsi+8], rax
0x180041ff9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180041ffe  jmp     short loc_18004201C
0x180042000  mov     [rsi], cx
0x180042003  mov     eax, [rdi]
0x180042005  mov     [rsi+8], eax
0x180042008  jmp     short loc_18004201C
0x18004200a  mov     rcx, rdi; psz
0x18004200d  mov     word ptr [rsi], 8
0x180042012  call    cs:__imp_SysAllocString
0x180042018  mov     [rsi+8], rax
0x18004201c  mov     rcx, [rbp+hKey]; hKey
0x180042020  test    rcx, rcx
0x180042023  jz      short loc_18004202B
0x180042025  call    cs:__imp_RegCloseKey
0x18004202b  test    rdi, rdi
0x18004202e  jz      short loc_180042039
0x180042030  mov     rcx, rdi; Block
0x180042033  call    cs:__imp_free
0x180042039  mov     eax, ebx
0x18004203b  add     rsp, 80h
0x180042042  pop     r15
0x180042044  pop     r14
0x180042046  pop     r12
0x180042048  pop     rdi
0x180042049  pop     rsi
0x18004204a  pop     rbx
0x18004204b  pop     rbp
0x18004204c  retn
```
