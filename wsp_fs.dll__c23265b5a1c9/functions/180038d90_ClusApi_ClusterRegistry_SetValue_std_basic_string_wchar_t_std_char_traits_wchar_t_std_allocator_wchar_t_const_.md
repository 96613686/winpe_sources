# ClusApi::ClusterRegistry::SetValue(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong,uchar * const,ulong)

- ea: `0x180038d90`
- end: `0x180038dd6`
- name: `?SetValue@ClusterRegistry@ClusApi@@IEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KQEAEK@Z`
- size: `70`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002dba0`
- `0x180038d50`

## callees

- `0x18000e14c`
- `0x180038d90`

## import_xrefs

- `CLUSAPI!ClusterRegSetValue` at `0x180038db8`
- `CLUSAPI!ClusterRegSetValue` at `0x180038db8`

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
0x180038d90  sub     rsp, 38h
0x180038d94  mov     r10, [rcx+8]
0x180038d98  mov     eax, 80071720h
0x180038d9d  test    r10, r10
0x180038da0  jz      short loc_180038DD0
0x180038da2  mov     rcx, rdx
0x180038da5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038daa  mov     rdx, rax; lpszValueName
0x180038dad  mov     rcx, r10; hKey
0x180038db0  mov     eax, [rsp+38h+arg_20]
0x180038db4  mov     [rsp+38h+cbData], eax; cbData
0x180038db8  call    cs:__imp_ClusterRegSetValue
0x180038dbf  nop     dword ptr [rax+rax+00h]
0x180038dc4  test    eax, eax
0x180038dc6  jle     short loc_180038DD0
0x180038dc8  movzx   eax, ax
0x180038dcb  or      eax, 80070000h
0x180038dd0  add     rsp, 38h
0x180038dd4  retn
```
