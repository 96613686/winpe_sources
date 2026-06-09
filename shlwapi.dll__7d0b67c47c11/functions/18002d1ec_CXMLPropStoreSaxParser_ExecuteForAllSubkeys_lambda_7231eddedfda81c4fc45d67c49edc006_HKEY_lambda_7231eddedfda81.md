# CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_7231eddedfda81c4fc45d67c49edc006_>(HKEY__ *,_lambda_7231eddedfda81c4fc45d67c49edc006_ const &)

- ea: `0x18002d1ec`
- end: `0x18002d32d`
- name: `??$_ExecuteForAllSubkeys@V_lambda_7231eddedfda81c4fc45d67c49edc006_@@@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@AEBV_lambda_7231eddedfda81c4fc45d67c49edc006_@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(CXMLPropStoreSaxParser *this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001142c`

## callees

- `0x180012550`
- `0x18002d1ec`
- `0x18002dc84`
- `0x18002e61c`
- `0x18002fdac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d297`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d297`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_7231eddedfda81c4fc45d67c49edc006_>(
        CXMLPropStoreSaxParser *this,
        HKEY a2)
{
  __int64 v4; // rcx
  signed int v5; // ebx
  unsigned int v6; // edi
  LSTATUS v7; // eax
  __int64 v8; // rcx
  HKEY v9; // rcx
  struct PROPVALUERESULT *v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v11 = 0;
  if ( (int)CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(this, a2, &v11) < 0 )
  {
    v5 = 0;
    v12 = 260;
    v6 = 0;
    do
    {
      if ( (unsigned int)HrRegEnumKeyEx(a2, v6, SubKey, &v12) )
        break;
      hKey = 0;
      v7 = RegOpenKeyExW(a2, SubKey, 0, 0x20019u, &hKey);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 >= 0 )
      {
        v5 = CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(this, hKey, &v11);
        if ( v5 >= 0 )
          v5 = _lambda_7231eddedfda81c4fc45d67c49edc006_::operator()(v8, hKey, v11);
      }
      v9 = hKey;
      v12 = 260;
      hKey = 0;
      if ( v9 )
        RegCloseKey(v9);
      ++v6;
    }
    while ( v5 >= 0 );
  }
  else
  {
    return (unsigned int)_lambda_7231eddedfda81c4fc45d67c49edc006_::operator()(v4, a2, v11);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002d1ec  mov     [rsp-8+arg_10], rbx
0x18002d1f1  mov     [rsp-8+arg_18], rsi
0x18002d1f6  push    rbp
0x18002d1f7  push    rdi
0x18002d1f8  push    r14
0x18002d1fa  lea     rbp, [rsp-170h]
0x18002d202  sub     rsp, 270h
0x18002d209  mov     rax, cs:__security_cookie
0x18002d210  xor     rax, rsp
0x18002d213  mov     [rbp+180h+var_20], rax
0x18002d21a  lea     r8, [rsp+280h+var_250]; struct PROPVALUERESULT **
0x18002d21f  mov     [rsp+280h+var_250], 0
0x18002d228  mov     rsi, rdx
0x18002d22b  mov     r14, rcx
0x18002d22e  call    ?_AddEntryAndRetrieveReference@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEAPEAUPROPVALUERESULT@@@Z; CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(HKEY__ *,PROPVALUERESULT * *)
0x18002d233  test    eax, eax
0x18002d235  js      short loc_18002D24B
0x18002d237  mov     r8, [rsp+280h+var_250]
0x18002d23c  mov     rdx, rsi
0x18002d23f  call    ??R_lambda_7231eddedfda81c4fc45d67c49edc006_@@QEBAJPEAUHKEY__@@PEAUPROPVALUERESULT@@@Z; _lambda_7231eddedfda81c4fc45d67c49edc006_::operator()(HKEY__ *,PROPVALUERESULT *)
0x18002d244  mov     ebx, eax
0x18002d246  jmp     loc_18002D304
0x18002d24b  xor     ebx, ebx
0x18002d24d  mov     [rsp+280h+var_248], 104h
0x18002d255  xor     edi, edi
0x18002d257  lea     r9, [rsp+280h+var_248]; unsigned int *
0x18002d25c  mov     edx, edi; unsigned int
0x18002d25e  lea     r8, [rsp+280h+SubKey]; unsigned __int16 *
0x18002d263  mov     rcx, rsi; HKEY
0x18002d266  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *)
0x18002d26b  test    eax, eax
0x18002d26d  jnz     loc_18002D304
0x18002d273  lea     rax, [rsp+280h+hKey]
0x18002d278  mov     [rsp+280h+hKey], 0
0x18002d281  mov     r9d, 20019h; samDesired
0x18002d287  mov     [rsp+280h+phkResult], rax; phkResult
0x18002d28c  xor     r8d, r8d; ulOptions
0x18002d28f  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18002d294  mov     rcx, rsi; hKey
0x18002d297  call    cs:__imp_RegOpenKeyExW
0x18002d29d  mov     ebx, eax
0x18002d29f  test    eax, eax
0x18002d2a1  jle     short loc_18002D2AC
0x18002d2a3  movzx   ebx, ax
0x18002d2a6  or      ebx, 80070000h
0x18002d2ac  test    ebx, ebx
0x18002d2ae  js      short loc_18002D2D9
0x18002d2b0  mov     rdx, [rsp+280h+hKey]; HKEY
0x18002d2b5  lea     r8, [rsp+280h+var_250]; struct PROPVALUERESULT **
0x18002d2ba  mov     rcx, r14; this
0x18002d2bd  call    ?_AddEntryAndRetrieveReference@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEAPEAUPROPVALUERESULT@@@Z; CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(HKEY__ *,PROPVALUERESULT * *)
0x18002d2c2  mov     ebx, eax
0x18002d2c4  test    eax, eax
0x18002d2c6  js      short loc_18002D2D9
0x18002d2c8  mov     r8, [rsp+280h+var_250]
0x18002d2cd  mov     rdx, [rsp+280h+hKey]
0x18002d2d2  call    ??R_lambda_7231eddedfda81c4fc45d67c49edc006_@@QEBAJPEAUHKEY__@@PEAUPROPVALUERESULT@@@Z; _lambda_7231eddedfda81c4fc45d67c49edc006_::operator()(HKEY__ *,PROPVALUERESULT *)
0x18002d2d7  mov     ebx, eax
0x18002d2d9  mov     rcx, [rsp+280h+hKey]; hKey
0x18002d2de  mov     [rsp+280h+var_248], 104h
0x18002d2e6  mov     [rsp+280h+hKey], 0
0x18002d2ef  test    rcx, rcx
0x18002d2f2  jz      short loc_18002D2FA
0x18002d2f4  call    cs:__imp_RegCloseKey
0x18002d2fa  inc     edi
0x18002d2fc  test    ebx, ebx
0x18002d2fe  jns     loc_18002D257
0x18002d304  mov     eax, ebx
0x18002d306  mov     rcx, [rbp+180h+var_20]
0x18002d30d  xor     rcx, rsp; StackCookie
0x18002d310  call    __security_check_cookie
0x18002d315  lea     r11, [rsp+280h+var_10]
0x18002d31d  mov     rbx, [r11+30h]
0x18002d321  mov     rsi, [r11+38h]
0x18002d325  mov     rsp, r11
0x18002d328  pop     r14
0x18002d32a  pop     rdi
0x18002d32b  pop     rbp
0x18002d32c  retn
```
