# smapi::StorageHealthContext::process_field(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::bitset<64> &)

- ea: `0x1800552fc`
- end: `0x180055398`
- name: `?process_field@StorageHealthContext@smapi@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$bitset@$0EA@@4@@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180036cb4`

## callees

- `0x18000d618`
- `0x180052220`
- `0x1800552fc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180055338`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005536f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180055338`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005536f`

## pseudocode

```c
char __fastcall smapi::StorageHealthContext::process_field(__int64 a1, __int64 a2, __int64 a3)
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
  std::bitset<64>::set(a3, 0, v6);
  return 1;
}

```

## disassembly

```asm
0x1800552fc  mov     [rsp+arg_0], rbx
0x180055301  push    rdi
0x180055302  sub     rsp, 30h
0x180055306  mov     rcx, rdx
0x180055309  mov     rbx, r8
0x18005530c  mov     rdi, rdx
0x18005530f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180055314  lea     rcx, aObjectid; "ObjectId"
0x18005531b  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180055323  or      r9d, 0FFFFFFFFh; cchCount1
0x180055327  mov     [rsp+38h+lpString2], rcx; lpString2
0x18005532c  mov     r8, rax; lpString1
0x18005532f  mov     ecx, 400h; Locale
0x180055334  lea     edx, [r9+2]; dwCmpFlags
0x180055338  call    cs:__imp_CompareStringW
0x18005533e  cmp     eax, 2
0x180055341  jz      short loc_18005537E
0x180055343  mov     rcx, rdi
0x180055346  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005534b  lea     rdx, aUniqueid; "UniqueId"
0x180055352  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005535a  or      r9d, 0FFFFFFFFh; cchCount1
0x18005535e  mov     [rsp+38h+lpString2], rdx; lpString2
0x180055363  mov     r8, rax; lpString1
0x180055366  mov     ecx, 400h; Locale
0x18005536b  lea     edx, [r9+2]; dwCmpFlags
0x18005536f  call    cs:__imp_CompareStringW
0x180055375  cmp     eax, 2
0x180055378  jz      short loc_18005537E
0x18005537a  xor     al, al
0x18005537c  jmp     short loc_18005538D
0x18005537e  mov     r8b, 1
0x180055381  xor     edx, edx
0x180055383  mov     rcx, rbx
0x180055386  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18005538b  mov     al, 1
0x18005538d  mov     rbx, [rsp+38h+arg_0]
0x180055392  add     rsp, 30h
0x180055396  pop     rdi
0x180055397  retn
```
