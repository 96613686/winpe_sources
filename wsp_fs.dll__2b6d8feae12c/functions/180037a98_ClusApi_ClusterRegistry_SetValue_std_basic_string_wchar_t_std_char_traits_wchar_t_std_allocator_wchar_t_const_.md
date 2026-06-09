# ClusApi::ClusterRegistry::SetValue(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong,uchar * const,ulong)

- ea: `0x180037a98`
- end: `0x180037ad7`
- name: `?SetValue@ClusterRegistry@ClusApi@@IEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KQEAEK@Z`
- size: `63`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002ce10`
- `0x180037a5c`

## callees

- `0x18000dd74`
- `0x180037a98`

## import_xrefs

- `CLUSAPI!ClusterRegSetValue` at `0x180037ac0`
- `CLUSAPI!ClusterRegSetValue` at `0x180037ac0`

## pseudocode

```c
signed int __fastcall ClusApi::ClusterRegistry::SetValue(__int64 a1, __int64 a2, __int64 a3, __int64 a4, DWORD cbData)
{
  signed int result; // eax
  const WCHAR *v6; // rax
  DWORD v7; // r8d
  const BYTE *v8; // r9
  HKEY v9; // r10

  result = -2147018976;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    result = ClusterRegSetValue(v9, v6, v7, v8, cbData);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180037a98  sub     rsp, 38h
0x180037a9c  mov     r10, [rcx+8]
0x180037aa0  mov     eax, 80071720h
0x180037aa5  test    r10, r10
0x180037aa8  jz      short loc_180037AD2
0x180037aaa  mov     rcx, rdx
0x180037aad  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180037ab2  mov     rdx, rax; lpszValueName
0x180037ab5  mov     rcx, r10; hKey
0x180037ab8  mov     eax, [rsp+38h+arg_20]
0x180037abc  mov     [rsp+38h+cbData], eax; cbData
0x180037ac0  call    cs:__imp_ClusterRegSetValue
0x180037ac6  test    eax, eax
0x180037ac8  jle     short loc_180037AD2
0x180037aca  movzx   eax, ax
0x180037acd  or      eax, 80070000h
0x180037ad2  add     rsp, 38h
0x180037ad6  retn
```
