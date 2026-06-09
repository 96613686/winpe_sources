# smapi::HealthActionContext::process_field(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::bitset<64> &)

- ea: `0x180057a8c`
- end: `0x180057b38`
- name: `?process_field@HealthActionContext@smapi@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$bitset@$0EA@@4@@Z`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180039df4`

## callees

- `0x18000da34`
- `0x180053c18`
- `0x180057a8c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057ac8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057b05`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057ac8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057b05`

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
0x180057a8c  mov     [rsp+arg_0], rbx
0x180057a91  push    rdi
0x180057a92  sub     rsp, 30h
0x180057a96  mov     rcx, rdx
0x180057a99  mov     rbx, r8
0x180057a9c  mov     rdi, rdx
0x180057a9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180057aa4  lea     rcx, aObjectid; "ObjectId"
0x180057aab  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180057ab3  or      r9d, 0FFFFFFFFh; cchCount1
0x180057ab7  mov     [rsp+38h+lpString2], rcx; lpString2
0x180057abc  mov     r8, rax; lpString1
0x180057abf  mov     ecx, 400h; Locale
0x180057ac4  lea     edx, [r9+2]; dwCmpFlags
0x180057ac8  call    cs:__imp_CompareStringW
0x180057acf  nop     dword ptr [rax+rax+00h]
0x180057ad4  cmp     eax, 2
0x180057ad7  jz      short loc_180057B1A
0x180057ad9  mov     rcx, rdi
0x180057adc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180057ae1  lea     rdx, aUniqueid; "UniqueId"
0x180057ae8  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180057af0  or      r9d, 0FFFFFFFFh; cchCount1
0x180057af4  mov     [rsp+38h+lpString2], rdx; lpString2
0x180057af9  mov     r8, rax; lpString1
0x180057afc  mov     ecx, 400h; Locale
0x180057b01  lea     edx, [r9+2]; dwCmpFlags
0x180057b05  call    cs:__imp_CompareStringW
0x180057b0c  nop     dword ptr [rax+rax+00h]
0x180057b11  cmp     eax, 2
0x180057b14  jz      short loc_180057B1A
0x180057b16  xor     al, al
0x180057b18  jmp     short loc_180057B2C
0x180057b1a  mov     r8b, 1
0x180057b1d  mov     edx, 0Bh
0x180057b22  mov     rcx, rbx
0x180057b25  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x180057b2a  mov     al, 1
0x180057b2c  mov     rbx, [rsp+38h+arg_0]
0x180057b31  add     rsp, 30h
0x180057b35  pop     rdi
0x180057b36  retn
```
