# smapi::StorageHealthContext::process_field(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::bitset<64> &)

- ea: `0x180056d1c`
- end: `0x180056dc5`
- name: `?process_field@StorageHealthContext@smapi@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$bitset@$0EA@@4@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180037fd4`

## callees

- `0x18000da34`
- `0x180053c18`
- `0x180056d1c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180056d58`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180056d95`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180056d58`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180056d95`

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
0x180056d1c  mov     [rsp+arg_0], rbx
0x180056d21  push    rdi
0x180056d22  sub     rsp, 30h
0x180056d26  mov     rcx, rdx
0x180056d29  mov     rbx, r8
0x180056d2c  mov     rdi, rdx
0x180056d2f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180056d34  lea     rcx, aObjectid; "ObjectId"
0x180056d3b  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180056d43  or      r9d, 0FFFFFFFFh; cchCount1
0x180056d47  mov     [rsp+38h+lpString2], rcx; lpString2
0x180056d4c  mov     r8, rax; lpString1
0x180056d4f  mov     ecx, 400h; Locale
0x180056d54  lea     edx, [r9+2]; dwCmpFlags
0x180056d58  call    cs:__imp_CompareStringW
0x180056d5f  nop     dword ptr [rax+rax+00h]
0x180056d64  cmp     eax, 2
0x180056d67  jz      short loc_180056DAA
0x180056d69  mov     rcx, rdi
0x180056d6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180056d71  lea     rdx, aUniqueid; "UniqueId"
0x180056d78  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180056d80  or      r9d, 0FFFFFFFFh; cchCount1
0x180056d84  mov     [rsp+38h+lpString2], rdx; lpString2
0x180056d89  mov     r8, rax; lpString1
0x180056d8c  mov     ecx, 400h; Locale
0x180056d91  lea     edx, [r9+2]; dwCmpFlags
0x180056d95  call    cs:__imp_CompareStringW
0x180056d9c  nop     dword ptr [rax+rax+00h]
0x180056da1  cmp     eax, 2
0x180056da4  jz      short loc_180056DAA
0x180056da6  xor     al, al
0x180056da8  jmp     short loc_180056DB9
0x180056daa  mov     r8b, 1
0x180056dad  xor     edx, edx
0x180056daf  mov     rcx, rbx
0x180056db2  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x180056db7  mov     al, 1
0x180056db9  mov     rbx, [rsp+38h+arg_0]
0x180056dbe  add     rsp, 30h
0x180056dc2  pop     rdi
0x180056dc3  retn
```
