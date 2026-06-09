# std::_Hash<std::tr1::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>,0>>::_Hashval(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180011d98`
- end: `0x180011e0e`
- name: `?_Hashval@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011e50`
- `0x180012858`
- `0x180012910`
- `0x180012ef8`

## callees

- `0x18000f744`
- `0x180011d98`
- `0x1800124fc`

## import_xrefs

- `OLEAUT32!__imp_LHashValOfNameSys` at `0x180011dd0`
- `OLEAUT32!__imp_LHashValOfNameSys` at `0x180011dd0`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Hashval(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  const OLECHAR *v5; // r8
  ULONG v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rbx
  unsigned __int64 result; // rax
  _BYTE v10[56]; // [rsp+20h] [rbp-38h] BYREF

  v3 = std::wstring::wstring(v10, a2);
  v4 = v3;
  if ( *(_QWORD *)(v3 + 24) < 8u )
    v5 = (const OLECHAR *)v3;
  else
    v5 = *(const OLECHAR **)v3;
  v6 = LHashValOfNameSys(SYS_WIN32, 0x800u, v5);
  LOBYTE(v7) = 1;
  v8 = v6;
  std::wstring::_Tidy(v4, v7, 0);
  result = v8 & *(_QWORD *)(a1 + 64);
  if ( *(_QWORD *)(a1 + 72) <= result )
    return result - (*(_QWORD *)(a1 + 64) >> 1) - 1;
  return result;
}

```

## disassembly

```asm
0x180011d98  mov     [rsp+arg_8], rbx
0x180011d9d  mov     [rsp+arg_10], rsi
0x180011da2  push    rdi
0x180011da3  sub     rsp, 50h
0x180011da7  mov     rsi, rcx
0x180011daa  lea     rcx, [rsp+58h+var_38]
0x180011daf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011db4  mov     rdi, rax
0x180011db7  cmp     qword ptr [rax+18h], 8
0x180011dbc  jb      short loc_180011DC3
0x180011dbe  mov     r8, [rax]
0x180011dc1  jmp     short loc_180011DC6
0x180011dc3  mov     r8, rdi; szName
0x180011dc6  mov     edx, 800h; lcid
0x180011dcb  mov     ecx, 1; syskind
0x180011dd0  call    cs:__imp_LHashValOfNameSys
0x180011dd6  xor     r8d, r8d
0x180011dd9  mov     dl, 1
0x180011ddb  mov     rcx, rdi
0x180011dde  mov     ebx, eax
0x180011de0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011de5  mov     rcx, [rsi+40h]
0x180011de9  mov     rax, rcx
0x180011dec  and     rax, rbx
0x180011def  cmp     [rsi+48h], rax
0x180011df3  ja      short loc_180011DFE
0x180011df5  shr     rcx, 1
0x180011df8  sub     rax, rcx
0x180011dfb  dec     rax
0x180011dfe  mov     rbx, [rsp+58h+arg_8]
0x180011e03  mov     rsi, [rsp+58h+arg_10]
0x180011e08  add     rsp, 50h
0x180011e0c  pop     rdi
0x180011e0d  retn
```
