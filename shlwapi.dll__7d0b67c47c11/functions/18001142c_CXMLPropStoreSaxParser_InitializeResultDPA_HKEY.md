# CXMLPropStoreSaxParser::_InitializeResultDPA(HKEY__ *)

- ea: `0x18001142c`
- end: `0x18001170b`
- name: `?_InitializeResultDPA@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(CXMLPropStoreSaxParser *__hidden this, HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002f1b0`

## callees

- `0x18001142c`
- `0x180012550`
- `0x18002d09c`
- `0x18002d1ec`
- `0x18002e61c`
- `0x18002fe7c`
- `0x180036000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001150b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011695`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001150b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011695`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011640`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011640`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800114df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011574`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800115f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800114df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011574`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800115f6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x1800115c5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x1800115c5`
- `SHELL32!__imp_GUIDFromStringW` at `0x180011543`
- `SHELL32!__imp_GUIDFromStringW` at `0x180011543`

## string_xrefs

- `0x1800114d5`: `OpenMetadata`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_InitializeResultDPA(CXMLPropStoreSaxParser *this, HKEY hKey)
{
  HDPA v4; // rax
  signed int v5; // ebx
  HKEY v6; // rcx
  unsigned int i; // r15d
  LSTATUS v8; // eax
  unsigned int v9; // r14d
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  HKEY v12; // rcx
  HKEY v13; // rcx
  HKEY hKeya; // [rsp+48h] [rbp-81h] BYREF
  int piRet; // [rsp+50h] [rbp-79h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-75h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v19; // [rsp+5Ch] [rbp-6Dh] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-69h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-61h] BYREF
  __int128 v22; // [rsp+70h] [rbp-59h] BYREF
  WCHAR pszString[16]; // [rsp+80h] [rbp-49h] BYREF
  WCHAR SubKey[40]; // [rsp+A0h] [rbp-29h] BYREF

  v4 = DPA_Create(10);
  *((_QWORD *)this + 3) = v4;
  if ( v4 )
  {
    v5 = CXMLPropStoreSaxParser::_AddEntryForContent(this, hKey, L"TextContent");
    if ( v5 >= 0 )
    {
      v5 = CXMLPropStoreSaxParser::_AddEntryForContent(this, hKey, L"AdditionalContent");
      if ( v5 >= 0 )
      {
        v5 = CXMLPropStoreSaxParser::_AddEntryForContent(this, hKey, L"BinaryContent");
        if ( v5 >= 0 )
        {
          v5 = 0;
          hKeya = 0;
          if ( !RegOpenKeyExW(hKey, L"OpenMetadata", 0, 0x20019u, &hKeya) )
            v5 = CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_7231eddedfda81c4fc45d67c49edc006_>(this, hKeya);
          v6 = hKeya;
          hKeya = 0;
          if ( v6 )
            RegCloseKey(v6);
        }
      }
    }
    for ( i = 0; ; ++i )
    {
      v19 = 39;
      if ( v5 < 0 || (unsigned int)HrRegEnumKeyEx(hKey, i, SubKey, &v19) )
        break;
      v22 = 0;
      if ( (unsigned int)GUIDFromStringW(SubKey, &v22) )
      {
        hKeya = 0;
        v8 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hKeya);
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        if ( v5 >= 0 )
        {
          v18 = 15;
          v9 = 0;
          do
          {
            if ( (unsigned int)HrRegEnumKeyEx(hKeya, v9, pszString, &v18) )
              break;
            piRet = 0;
            if ( StrToIntExW(pszString, 0, &piRet) )
            {
              phkResult = 0;
              v10 = RegOpenKeyExW(hKeya, pszString, 0, 0x20019u, &phkResult);
              v5 = v10;
              if ( v10 > 0 )
                v5 = (unsigned __int16)v10 | 0x80070000;
              if ( v5 >= 0 )
              {
                *(_DWORD *)Data = 0;
                cbData = 4;
                v11 = RegQueryValueExW(phkResult, L"VT", 0, 0, Data, &cbData);
                v5 = v11;
                if ( v11 > 0 )
                  v5 = (unsigned __int16)v11 | 0x80070000;
                if ( v5 >= 0 )
                  v5 = CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_1c34188375db90f340125b75aaaf55b8_>(
                         this,
                         phkResult);
              }
              v12 = phkResult;
              phkResult = 0;
              if ( v12 )
                RegCloseKey(v12);
            }
            else
            {
              v5 = -2147467259;
            }
            ++v9;
            v18 = 15;
          }
          while ( v5 >= 0 );
        }
        v13 = hKeya;
        hKeya = 0;
        if ( v13 )
          RegCloseKey(v13);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001142c  mov     [rsp-8+arg_10], rbx
0x180011431  push    rbp
0x180011432  push    rsi
0x180011433  push    rdi
0x180011434  push    r14
0x180011436  push    r15
0x180011438  lea     rbp, [rsp-37h]
0x18001143d  sub     rsp, 100h
0x180011444  mov     rax, cs:__security_cookie
0x18001144b  xor     rax, rsp
0x18001144e  mov     [rbp+57h+var_30], rax
0x180011452  mov     rdi, rcx
0x180011455  mov     rsi, rdx
0x180011458  mov     ecx, 0Ah; cItemGrow
0x18001145d  call    DPA_Create
0x180011462  mov     [rdi+18h], rax
0x180011466  test    rax, rax
0x180011469  jz      loc_1800116E1
0x18001146f  lea     r8, aTextcontent; "TextContent"
0x180011476  mov     rdx, rsi; hKey
0x180011479  mov     rcx, rdi; this
0x18001147c  call    ?_AddEntryForContent@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEBG@Z; CXMLPropStoreSaxParser::_AddEntryForContent(HKEY__ *,ushort const *)
0x180011481  mov     ebx, eax
0x180011483  test    eax, eax
0x180011485  js      loc_180011511
0x18001148b  lea     r8, aAdditionalcont; "AdditionalContent"
0x180011492  mov     rdx, rsi; hKey
0x180011495  mov     rcx, rdi; this
0x180011498  call    ?_AddEntryForContent@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEBG@Z; CXMLPropStoreSaxParser::_AddEntryForContent(HKEY__ *,ushort const *)
0x18001149d  mov     ebx, eax
0x18001149f  test    eax, eax
0x1800114a1  js      short loc_180011511
0x1800114a3  lea     r8, aBinarycontent; "BinaryContent"
0x1800114aa  mov     rdx, rsi; hKey
0x1800114ad  mov     rcx, rdi; this
0x1800114b0  call    ?_AddEntryForContent@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEBG@Z; CXMLPropStoreSaxParser::_AddEntryForContent(HKEY__ *,ushort const *)
0x1800114b5  mov     ebx, eax
0x1800114b7  test    eax, eax
0x1800114b9  js      short loc_180011511
0x1800114bb  lea     rax, [rsp+120h+hKey]
0x1800114c0  xor     ebx, ebx
0x1800114c2  mov     r9d, 20019h; samDesired
0x1800114c8  mov     [rsp+120h+hKey], rbx
0x1800114cd  xor     r8d, r8d; ulOptions
0x1800114d0  mov     [rsp+120h+phkResult], rax; phkResult
0x1800114d5  lea     rdx, aOpenmetadata; "OpenMetadata"
0x1800114dc  mov     rcx, rsi; hKey
0x1800114df  call    cs:__imp_RegOpenKeyExW
0x1800114e5  test    eax, eax
0x1800114e7  jnz     short loc_1800114F8
0x1800114e9  mov     rdx, [rsp+120h+hKey]; HKEY
0x1800114ee  mov     rcx, rdi; this
0x1800114f1  call    ??$_ExecuteForAllSubkeys@V_lambda_7231eddedfda81c4fc45d67c49edc006_@@@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@AEBV_lambda_7231eddedfda81c4fc45d67c49edc006_@@@Z; CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_7231eddedfda81c4fc45d67c49edc006_>(HKEY__ *,_lambda_7231eddedfda81c4fc45d67c49edc006_ const &)
0x1800114f6  mov     ebx, eax
0x1800114f8  mov     rcx, [rsp+120h+hKey]; hKey
0x1800114fd  mov     [rsp+120h+hKey], 0
0x180011506  test    rcx, rcx
0x180011509  jz      short loc_180011511
0x18001150b  call    cs:__imp_RegCloseKey
0x180011511  xor     r15d, r15d
0x180011514  jmp     loc_1800116D0
0x180011519  lea     r9, [rbp+57h+var_C4]; unsigned int *
0x18001151d  mov     edx, r15d; unsigned int
0x180011520  lea     r8, [rbp+57h+SubKey]; unsigned __int16 *
0x180011524  mov     rcx, rsi; HKEY
0x180011527  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *)
0x18001152c  test    eax, eax
0x18001152e  jnz     loc_1800116E6
0x180011534  xorps   xmm0, xmm0
0x180011537  lea     rdx, [rbp+57h+var_B0]
0x18001153b  lea     rcx, [rbp+57h+SubKey]
0x18001153f  movups  [rbp+57h+var_B0], xmm0
0x180011543  call    cs:__imp_GUIDFromStringW
0x180011549  test    eax, eax
0x18001154b  jz      loc_1800116CD
0x180011551  lea     rax, [rsp+120h+hKey]
0x180011556  mov     [rsp+120h+hKey], 0
0x18001155f  mov     r9d, 20019h; samDesired
0x180011565  mov     [rsp+120h+phkResult], rax; phkResult
0x18001156a  xor     r8d, r8d; ulOptions
0x18001156d  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180011571  mov     rcx, rsi; hKey
0x180011574  call    cs:__imp_RegOpenKeyExW
0x18001157a  mov     ebx, eax
0x18001157c  test    eax, eax
0x18001157e  jle     short loc_180011589
0x180011580  movzx   ebx, ax
0x180011583  or      ebx, 80070000h
0x180011589  test    ebx, ebx
0x18001158b  js      loc_1800116B4
0x180011591  mov     [rbp+57h+var_C8], 0Fh
0x180011598  xor     r14d, r14d
0x18001159b  mov     rcx, [rsp+120h+hKey]; HKEY
0x1800115a0  lea     r9, [rbp+57h+var_C8]; unsigned int *
0x1800115a4  lea     r8, [rbp+57h+pszString]; unsigned __int16 *
0x1800115a8  mov     edx, r14d; unsigned int
0x1800115ab  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *)
0x1800115b0  test    eax, eax
0x1800115b2  jnz     loc_1800116B4
0x1800115b8  lea     r8, [rbp+57h+piRet]; piRet
0x1800115bc  mov     [rbp+57h+piRet], eax
0x1800115bf  xor     edx, edx; dwFlags
0x1800115c1  lea     rcx, [rbp+57h+pszString]; pszString
0x1800115c5  call    cs:__imp_StrToIntExW
0x1800115cb  test    eax, eax
0x1800115cd  jz      loc_18001169D
0x1800115d3  mov     rcx, [rsp+120h+hKey]; hKey
0x1800115d8  lea     rax, [rbp+57h+var_C0]
0x1800115dc  mov     r9d, 20019h; samDesired
0x1800115e2  mov     [rsp+120h+phkResult], rax; phkResult
0x1800115e7  xor     r8d, r8d; ulOptions
0x1800115ea  mov     [rbp+57h+var_C0], 0
0x1800115f2  lea     rdx, [rbp+57h+pszString]; lpSubKey
0x1800115f6  call    cs:__imp_RegOpenKeyExW
0x1800115fc  mov     ebx, eax
0x1800115fe  test    eax, eax
0x180011600  jle     short loc_18001160B
0x180011602  movzx   ebx, ax
0x180011605  or      ebx, 80070000h
0x18001160b  test    ebx, ebx
0x18001160d  js      short loc_180011684
0x18001160f  mov     rcx, [rbp+57h+var_C0]; hKey
0x180011613  lea     rax, [rbp+57h+cbData]
0x180011617  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18001161c  lea     rdx, ValueName; "VT"
0x180011623  lea     rax, [rbp+57h+Data]
0x180011627  mov     dword ptr [rbp+57h+Data], 0
0x18001162e  xor     r9d, r9d; lpType
0x180011631  mov     [rsp+120h+phkResult], rax; lpData
0x180011636  xor     r8d, r8d; lpReserved
0x180011639  mov     [rbp+57h+cbData], 4
0x180011640  call    cs:__imp_RegQueryValueExW
0x180011646  mov     ebx, eax
0x180011648  test    eax, eax
0x18001164a  jle     short loc_180011655
0x18001164c  movzx   ebx, ax
0x18001164f  or      ebx, 80070000h
0x180011655  test    ebx, ebx
0x180011657  js      short loc_180011684
0x180011659  mov     eax, [rbp+57h+piRet]
0x18001165c  lea     r8, [rsp+120h+var_F0]
0x180011661  movups  xmm0, [rbp+57h+var_B0]
0x180011665  mov     rdx, [rbp+57h+var_C0]; HKEY
0x180011669  mov     rcx, rdi; this
0x18001166c  mov     [rsp+120h+var_E0], eax
0x180011670  mov     eax, dword ptr [rbp+57h+Data]
0x180011673  movdqu  [rsp+120h+var_F0], xmm0
0x180011679  mov     [rsp+120h+var_DC], eax
0x18001167d  call    ??$_ExecuteForAllSubkeys@V_lambda_1c34188375db90f340125b75aaaf55b8_@@@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@AEBV_lambda_1c34188375db90f340125b75aaaf55b8_@@@Z; CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_1c34188375db90f340125b75aaaf55b8_>(HKEY__ *,_lambda_1c34188375db90f340125b75aaaf55b8_ const &)
0x180011682  mov     ebx, eax
0x180011684  mov     rcx, [rbp+57h+var_C0]; hKey
0x180011688  mov     [rbp+57h+var_C0], 0
0x180011690  test    rcx, rcx
0x180011693  jz      short loc_1800116A2
0x180011695  call    cs:__imp_RegCloseKey
0x18001169b  jmp     short loc_1800116A2
0x18001169d  mov     ebx, 80004005h
0x1800116a2  inc     r14d
0x1800116a5  mov     [rbp+57h+var_C8], 0Fh
0x1800116ac  test    ebx, ebx
0x1800116ae  jns     loc_18001159B
0x1800116b4  mov     rcx, [rsp+120h+hKey]; hKey
0x1800116b9  mov     [rsp+120h+hKey], 0
0x1800116c2  test    rcx, rcx
0x1800116c5  jz      short loc_1800116CD
0x1800116c7  call    cs:__imp_RegCloseKey
0x1800116cd  inc     r15d
0x1800116d0  mov     [rbp+57h+var_C4], 27h ; '''
0x1800116d7  test    ebx, ebx
0x1800116d9  jns     loc_180011519
0x1800116df  jmp     short loc_1800116E6
0x1800116e1  mov     ebx, 8007000Eh
0x1800116e6  mov     eax, ebx
0x1800116e8  mov     rcx, [rbp+57h+var_30]
0x1800116ec  xor     rcx, rsp; StackCookie
0x1800116ef  call    __security_check_cookie
0x1800116f4  mov     rbx, [rsp+120h+arg_10]
0x1800116fc  add     rsp, 100h
0x180011703  pop     r15
0x180011705  pop     r14
0x180011707  pop     rdi
0x180011708  pop     rsi
0x180011709  pop     rbp
0x18001170a  retn
```
