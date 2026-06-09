# CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_7f34dda4c3a21f63818194a7724a5899_>(HKEY__ *,_lambda_7f34dda4c3a21f63818194a7724a5899_ const &)

- ea: `0x18002d334`
- end: `0x18002d48b`
- name: `??$_ExecuteForAllSubkeys@V_lambda_7f34dda4c3a21f63818194a7724a5899_@@@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@AEBV_lambda_7f34dda4c3a21f63818194a7724a5899_@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(CXMLPropStoreSaxParser *this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002fe7c`

## callees

- `0x180012550`
- `0x18002d334`
- `0x18002e61c`
- `0x18002fdac`
- `0x180032030`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d452`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d452`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d3ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d3ea`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_7f34dda4c3a21f63818194a7724a5899_>(
        CXMLPropStoreSaxParser *this,
        HKEY a2)
{
  signed int v4; // ebx
  unsigned int v5; // edi
  LSTATUS v6; // eax
  HKEY v7; // rcx
  struct PROPVALUERESULT *v9; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v9 = 0;
  if ( (int)CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(this, a2, &v9) < 0 )
  {
    v4 = 0;
    v10 = 260;
    v5 = 0;
    do
    {
      if ( (unsigned int)HrRegEnumKeyEx(a2, v5, SubKey, &v10) )
        break;
      hKey = 0;
      v6 = RegOpenKeyExW(a2, SubKey, 0, 0x20019u, &hKey);
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v4 >= 0 )
      {
        v4 = CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(this, hKey, &v9);
        if ( v4 >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
            (BYTE **)v9 + 4,
            hKey,
            L"ContentTypeAttribute");
          v4 = 0;
        }
      }
      v7 = hKey;
      v10 = 260;
      hKey = 0;
      if ( v7 )
        RegCloseKey(v7);
      ++v5;
    }
    while ( v4 >= 0 );
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
      (BYTE **)v9 + 4,
      a2,
      L"ContentTypeAttribute");
    return 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002d334  mov     [rsp-8+arg_10], rbx
0x18002d339  mov     [rsp-8+arg_18], rsi
0x18002d33e  push    rbp
0x18002d33f  push    rdi
0x18002d340  push    r14
0x18002d342  lea     rbp, [rsp-170h]
0x18002d34a  sub     rsp, 270h
0x18002d351  mov     rax, cs:__security_cookie
0x18002d358  xor     rax, rsp
0x18002d35b  mov     [rbp+180h+var_20], rax
0x18002d362  lea     r8, [rsp+280h+var_250]; struct PROPVALUERESULT **
0x18002d367  mov     [rsp+280h+var_250], 0
0x18002d370  mov     rsi, rdx
0x18002d373  mov     r14, rcx
0x18002d376  call    ?_AddEntryAndRetrieveReference@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEAPEAUPROPVALUERESULT@@@Z; CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(HKEY__ *,PROPVALUERESULT * *)
0x18002d37b  test    eax, eax
0x18002d37d  js      short loc_18002D39E
0x18002d37f  mov     rcx, [rsp+280h+var_250]
0x18002d384  lea     r8, aContenttypeatt; "ContentTypeAttribute"
0x18002d38b  add     rcx, 20h ; ' '
0x18002d38f  mov     rdx, rsi
0x18002d392  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18002d397  xor     ebx, ebx
0x18002d399  jmp     loc_18002D462
0x18002d39e  xor     ebx, ebx
0x18002d3a0  mov     [rsp+280h+var_248], 104h
0x18002d3a8  xor     edi, edi
0x18002d3aa  lea     r9, [rsp+280h+var_248]; unsigned int *
0x18002d3af  mov     edx, edi; unsigned int
0x18002d3b1  lea     r8, [rsp+280h+SubKey]; unsigned __int16 *
0x18002d3b6  mov     rcx, rsi; HKEY
0x18002d3b9  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *)
0x18002d3be  test    eax, eax
0x18002d3c0  jnz     loc_18002D462
0x18002d3c6  lea     rax, [rsp+280h+hKey]
0x18002d3cb  mov     [rsp+280h+hKey], 0
0x18002d3d4  mov     r9d, 20019h; samDesired
0x18002d3da  mov     [rsp+280h+phkResult], rax; phkResult
0x18002d3df  xor     r8d, r8d; ulOptions
0x18002d3e2  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18002d3e7  mov     rcx, rsi; hKey
0x18002d3ea  call    cs:__imp_RegOpenKeyExW
0x18002d3f0  mov     ebx, eax
0x18002d3f2  test    eax, eax
0x18002d3f4  jle     short loc_18002D3FF
0x18002d3f6  movzx   ebx, ax
0x18002d3f9  or      ebx, 80070000h
0x18002d3ff  test    ebx, ebx
0x18002d401  js      short loc_18002D437
0x18002d403  mov     rdx, [rsp+280h+hKey]; HKEY
0x18002d408  lea     r8, [rsp+280h+var_250]; struct PROPVALUERESULT **
0x18002d40d  mov     rcx, r14; this
0x18002d410  call    ?_AddEntryAndRetrieveReference@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEAPEAUPROPVALUERESULT@@@Z; CXMLPropStoreSaxParser::_AddEntryAndRetrieveReference(HKEY__ *,PROPVALUERESULT * *)
0x18002d415  mov     ebx, eax
0x18002d417  test    eax, eax
0x18002d419  js      short loc_18002D437
0x18002d41b  mov     rcx, [rsp+280h+var_250]
0x18002d420  lea     r8, aContenttypeatt; "ContentTypeAttribute"
0x18002d427  mov     rdx, [rsp+280h+hKey]
0x18002d42c  add     rcx, 20h ; ' '
0x18002d430  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18002d435  xor     ebx, ebx
0x18002d437  mov     rcx, [rsp+280h+hKey]; hKey
0x18002d43c  mov     [rsp+280h+var_248], 104h
0x18002d444  mov     [rsp+280h+hKey], 0
0x18002d44d  test    rcx, rcx
0x18002d450  jz      short loc_18002D458
0x18002d452  call    cs:__imp_RegCloseKey
0x18002d458  inc     edi
0x18002d45a  test    ebx, ebx
0x18002d45c  jns     loc_18002D3AA
0x18002d462  mov     eax, ebx
0x18002d464  mov     rcx, [rbp+180h+var_20]
0x18002d46b  xor     rcx, rsp; StackCookie
0x18002d46e  call    __security_check_cookie
0x18002d473  lea     r11, [rsp+280h+var_10]
0x18002d47b  mov     rbx, [r11+30h]
0x18002d47f  mov     rsi, [r11+38h]
0x18002d483  mov     rsp, r11
0x18002d486  pop     r14
0x18002d488  pop     rdi
0x18002d489  pop     rbp
0x18002d48a  retn
```
