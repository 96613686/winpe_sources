# ClusApi::ClusterRegistry::SetValue(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong,uchar * const,ulong)

- ea: `0x180033bd8`
- end: `0x180033c17`
- name: `?SetValue@ClusterRegistry@ClusApi@@IEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KQEAEK@Z`
- size: `63`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800290d0`
- `0x180033b9c`

## callees

- `0x18000d618`
- `0x180033bd8`

## import_xrefs

- `CLUSAPI!ClusterRegSetValue` at `0x180033c00`
- `CLUSAPI!ClusterRegSetValue` at `0x180033c00`

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
0x180033bd8  sub     rsp, 38h
0x180033bdc  mov     r10, [rcx+8]
0x180033be0  mov     eax, 80071720h
0x180033be5  test    r10, r10
0x180033be8  jz      short loc_180033C12
0x180033bea  mov     rcx, rdx
0x180033bed  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180033bf2  mov     rdx, rax; lpszValueName
0x180033bf5  mov     rcx, r10; hKey
0x180033bf8  mov     eax, [rsp+38h+arg_20]
0x180033bfc  mov     [rsp+38h+cbData], eax; cbData
0x180033c00  call    cs:__imp_ClusterRegSetValue
0x180033c06  test    eax, eax
0x180033c08  jle     short loc_180033C12
0x180033c0a  movzx   eax, ax
0x180033c0d  or      eax, 80070000h
0x180033c12  add     rsp, 38h
0x180033c16  retn
```
