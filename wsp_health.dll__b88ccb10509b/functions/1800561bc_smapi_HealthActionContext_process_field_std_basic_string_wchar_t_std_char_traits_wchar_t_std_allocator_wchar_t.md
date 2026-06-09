# smapi::HealthActionContext::process_field(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::bitset<64> &)

- ea: `0x1800561bc`
- end: `0x18005625b`
- name: `?process_field@HealthActionContext@smapi@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$bitset@$0EA@@4@@Z`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180038a24`

## callees

- `0x18000d618`
- `0x180052220`
- `0x1800561bc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800561f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005622f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800561f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005622f`

## pseudocode

```c
char __fastcall smapi::HealthActionContext::process_field(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *v5; // rax
  __int64 v6; // r8
  const WCHAR *v7; // rax

  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  if ( CompareStringW(0x400u, 1u, v5, -1, L"ObjectId", -1) != 2 )
  {
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    if ( CompareStringW(0x400u, 1u, v7, -1, L"UniqueId", -1) != 2 )
      return 0;
  }
  LOBYTE(v6) = 1;
  std::bitset<64>::set(a3, 11, v6);
  return 1;
}

```

## disassembly

```asm
0x1800561bc  mov     [rsp+arg_0], rbx
0x1800561c1  push    rdi
0x1800561c2  sub     rsp, 30h
0x1800561c6  mov     rcx, rdx
0x1800561c9  mov     rbx, r8
0x1800561cc  mov     rdi, rdx
0x1800561cf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800561d4  lea     rcx, aObjectid; "ObjectId"
0x1800561db  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800561e3  or      r9d, 0FFFFFFFFh; cchCount1
0x1800561e7  mov     [rsp+38h+lpString2], rcx; lpString2
0x1800561ec  mov     r8, rax; lpString1
0x1800561ef  mov     ecx, 400h; Locale
0x1800561f4  lea     edx, [r9+2]; dwCmpFlags
0x1800561f8  call    cs:__imp_CompareStringW
0x1800561fe  cmp     eax, 2
0x180056201  jz      short loc_18005623E
0x180056203  mov     rcx, rdi
0x180056206  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005620b  lea     rdx, aUniqueid; "UniqueId"
0x180056212  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005621a  or      r9d, 0FFFFFFFFh; cchCount1
0x18005621e  mov     [rsp+38h+lpString2], rdx; lpString2
0x180056223  mov     r8, rax; lpString1
0x180056226  mov     ecx, 400h; Locale
0x18005622b  lea     edx, [r9+2]; dwCmpFlags
0x18005622f  call    cs:__imp_CompareStringW
0x180056235  cmp     eax, 2
0x180056238  jz      short loc_18005623E
0x18005623a  xor     al, al
0x18005623c  jmp     short loc_180056250
0x18005623e  mov     r8b, 1
0x180056241  mov     edx, 0Bh
0x180056246  mov     rcx, rbx
0x180056249  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18005624e  mov     al, 1
0x180056250  mov     rbx, [rsp+38h+arg_0]
0x180056255  add     rsp, 30h
0x180056259  pop     rdi
0x18005625a  retn
```
