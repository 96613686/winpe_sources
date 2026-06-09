# CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_1c34188375db90f340125b75aaaf55b8_>(HKEY__ *,_lambda_1c34188375db90f340125b75aaaf55b8_ const &)

- ea: `0x18002d09c`
- end: `0x18002d1e3`
- name: `??$_ExecuteForAllSubkeys@V_lambda_1c34188375db90f340125b75aaaf55b8_@@@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@AEBV_lambda_1c34188375db90f340125b75aaaf55b8_@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(CXMLPropStoreSaxParser *this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001142c`

## callees

- `0x180012550`
- `0x18002d09c`
- `0x18002dc44`
- `0x18002e61c`
- `0x18002fdac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d1ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d1ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d14b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d14b`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_1c34188375db90f340125b75aaaf55b8_>(
        CXMLPropStoreSaxParser *this,
        HKEY a2,
        __int64 a3)
{
  signed int v6; // ebx
  unsigned int v7; // edi
  LSTATUS v8; // eax
  HKEY v9; // rcx
  struct PROPVALUERESULT *v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v11 = 0;
  if ( (int)CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(this, a2, &v11) < 0 )
  {
    v6 = 0;
    v12 = 260;
    v7 = 0;
    do
    {
      if ( (unsigned int)HrRegEnumKeyEx(a2, v7, SubKey, &v12) )
        break;
      hKey = 0;
      v8 = RegOpenKeyExW(a2, SubKey, 0, 0x20019u, &hKey);
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 >= 0 )
      {
        v6 = CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(this, hKey, &v11);
        if ( v6 >= 0 )
          v6 = _lambda_1c34188375db90f340125b75aaaf55b8_::operator()(a3, hKey, v11);
      }
      v9 = hKey;
      v12 = 260;
      hKey = 0;
      if ( v9 )
        RegCloseKey(v9);
      ++v7;
    }
    while ( v6 >= 0 );
  }
  else
  {
    return (unsigned int)_lambda_1c34188375db90f340125b75aaaf55b8_::operator()(a3, a2, v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002d09c  mov     [rsp-8+arg_10], rbx
0x18002d0a1  push    rbp
0x18002d0a2  push    rsi
0x18002d0a3  push    rdi
0x18002d0a4  push    r14
0x18002d0a6  push    r15
0x18002d0a8  lea     rbp, [rsp-170h]
0x18002d0b0  sub     rsp, 270h
0x18002d0b7  mov     rax, cs:__security_cookie
0x18002d0be  xor     rax, rsp
0x18002d0c1  mov     [rbp+190h+var_30], rax
0x18002d0c8  mov     r14, r8
0x18002d0cb  mov     [rsp+290h+var_260], 0
0x18002d0d4  lea     r8, [rsp+290h+var_260]; struct PROPVALUERESULT **
0x18002d0d9  mov     rsi, rdx
0x18002d0dc  mov     r15, rcx
0x18002d0df  call    ?_AddEntryAndRetrieveReference@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEAPEAUPROPVALUERESULT@@@Z; CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(HKEY__ *,PROPVALUERESULT * *)
0x18002d0e4  test    eax, eax
0x18002d0e6  js      short loc_18002D0FF
0x18002d0e8  mov     r8, [rsp+290h+var_260]
0x18002d0ed  mov     rdx, rsi
0x18002d0f0  mov     rcx, r14
0x18002d0f3  call    ??R_lambda_1c34188375db90f340125b75aaaf55b8_@@QEBAJPEAUHKEY__@@PEAUPROPVALUERESULT@@@Z; _lambda_1c34188375db90f340125b75aaaf55b8_::operator()(HKEY__ *,PROPVALUERESULT *)
0x18002d0f8  mov     ebx, eax
0x18002d0fa  jmp     loc_18002D1BB
0x18002d0ff  xor     ebx, ebx
0x18002d101  mov     [rsp+290h+var_258], 104h
0x18002d109  xor     edi, edi
0x18002d10b  lea     r9, [rsp+290h+var_258]; unsigned int *
0x18002d110  mov     edx, edi; unsigned int
0x18002d112  lea     r8, [rsp+290h+SubKey]; unsigned __int16 *
0x18002d117  mov     rcx, rsi; HKEY
0x18002d11a  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *)
0x18002d11f  test    eax, eax
0x18002d121  jnz     loc_18002D1BB
0x18002d127  lea     rax, [rsp+290h+hKey]
0x18002d12c  mov     [rsp+290h+hKey], 0
0x18002d135  mov     r9d, 20019h; samDesired
0x18002d13b  mov     [rsp+290h+phkResult], rax; phkResult
0x18002d140  xor     r8d, r8d; ulOptions
0x18002d143  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18002d148  mov     rcx, rsi; hKey
0x18002d14b  call    cs:__imp_RegOpenKeyExW
0x18002d151  mov     ebx, eax
0x18002d153  test    eax, eax
0x18002d155  jle     short loc_18002D160
0x18002d157  movzx   ebx, ax
0x18002d15a  or      ebx, 80070000h
0x18002d160  test    ebx, ebx
0x18002d162  js      short loc_18002D190
0x18002d164  mov     rdx, [rsp+290h+hKey]; HKEY
0x18002d169  lea     r8, [rsp+290h+var_260]; struct PROPVALUERESULT **
0x18002d16e  mov     rcx, r15; this
0x18002d171  call    ?_AddEntryAndRetrieveReference@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEAPEAUPROPVALUERESULT@@@Z; CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(HKEY__ *,PROPVALUERESULT * *)
0x18002d176  mov     ebx, eax
0x18002d178  test    eax, eax
0x18002d17a  js      short loc_18002D190
0x18002d17c  mov     r8, [rsp+290h+var_260]
0x18002d181  mov     rcx, r14
0x18002d184  mov     rdx, [rsp+290h+hKey]
0x18002d189  call    ??R_lambda_1c34188375db90f340125b75aaaf55b8_@@QEBAJPEAUHKEY__@@PEAUPROPVALUERESULT@@@Z; _lambda_1c34188375db90f340125b75aaaf55b8_::operator()(HKEY__ *,PROPVALUERESULT *)
0x18002d18e  mov     ebx, eax
0x18002d190  mov     rcx, [rsp+290h+hKey]; hKey
0x18002d195  mov     [rsp+290h+var_258], 104h
0x18002d19d  mov     [rsp+290h+hKey], 0
0x18002d1a6  test    rcx, rcx
0x18002d1a9  jz      short loc_18002D1B1
0x18002d1ab  call    cs:__imp_RegCloseKey
0x18002d1b1  inc     edi
0x18002d1b3  test    ebx, ebx
0x18002d1b5  jns     loc_18002D10B
0x18002d1bb  mov     eax, ebx
0x18002d1bd  mov     rcx, [rbp+190h+var_30]
0x18002d1c4  xor     rcx, rsp; StackCookie
0x18002d1c7  call    __security_check_cookie
0x18002d1cc  mov     rbx, [rsp+290h+arg_10]
0x18002d1d4  add     rsp, 270h
0x18002d1db  pop     r15
0x18002d1dd  pop     r14
0x18002d1df  pop     rdi
0x18002d1e0  pop     rsi
0x18002d1e1  pop     rbp
0x18002d1e2  retn
```
