# IsEventLoggedToLegacyChannel

- ea: `0x180038190`
- end: `0x180038222`
- name: `IsEventLoggedToLegacyChannel`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800353f8`

## callees

- `0x18002c1d8`
- `0x180038190`

## string_xrefs

- `0x1800381ca`: `SECURITY`

## pseudocode

```c
bool __fastcall IsEventLoggedToLegacyChannel(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  bool result; // al
  const wchar_t *v5; // [rsp+20h] [rbp-18h] BYREF
  __int64 v6; // [rsp+28h] [rbp-10h]

  result = 0;
  if ( a1 )
  {
    if ( *(_BYTE *)(a1 + 113) )
    {
      v6 = 6;
      v5 = L"SYSTEM";
      if ( (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<std::wstring,std::wstring_view,wchar_t,wchar_t,0>(
                              a1,
                              a1,
                              &v5) )
        return 1;
      v6 = 8;
      v5 = L"SECURITY";
      if ( (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<std::wstring,std::wstring_view,wchar_t,wchar_t,0>(
                              v2,
                              a1,
                              &v5) )
        return 1;
      v6 = 11;
      v5 = L"APPLICATION";
      if ( (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<std::wstring,std::wstring_view,wchar_t,wchar_t,0>(
                              v3,
                              a1,
                              &v5) )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180038190  push    rbx
0x180038192  sub     rsp, 30h
0x180038196  mov     rbx, rcx
0x180038199  test    rcx, rcx
0x18003819c  jz      short loc_18003821A
0x18003819e  cmp     byte ptr [rcx+71h], 0
0x1800381a2  jz      short loc_18003821A
0x1800381a4  lea     rax, aSystem; "SYSTEM"
0x1800381ab  mov     [rsp+38h+var_10], 6
0x1800381b4  lea     r8, [rsp+38h+var_18]
0x1800381b9  mov     [rsp+38h+var_18], rax
0x1800381be  mov     rdx, rcx
0x1800381c1  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<std::wstring,std::wstring_view,wchar_t,wchar_t,0>(std::wstring const &,std::wstring_view const &)
0x1800381c6  test    al, al
0x1800381c8  jnz     short loc_180038216
0x1800381ca  lea     rax, aSecurity_0; "SECURITY"
0x1800381d1  mov     [rsp+38h+var_10], 8
0x1800381da  lea     r8, [rsp+38h+var_18]
0x1800381df  mov     [rsp+38h+var_18], rax
0x1800381e4  mov     rdx, rbx
0x1800381e7  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<std::wstring,std::wstring_view,wchar_t,wchar_t,0>(std::wstring const &,std::wstring_view const &)
0x1800381ec  test    al, al
0x1800381ee  jnz     short loc_180038216
0x1800381f0  lea     rax, aApplication; "APPLICATION"
0x1800381f7  mov     [rsp+38h+var_10], 0Bh
0x180038200  lea     r8, [rsp+38h+var_18]
0x180038205  mov     [rsp+38h+var_18], rax
0x18003820a  mov     rdx, rbx
0x18003820d  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<std::wstring,std::wstring_view,wchar_t,wchar_t,0>(std::wstring const &,std::wstring_view const &)
0x180038212  test    al, al
0x180038214  jz      short loc_18003821A
0x180038216  mov     al, 1
0x180038218  jmp     short loc_18003821C
0x18003821a  xor     al, al
0x18003821c  add     rsp, 30h
0x180038220  pop     rbx
0x180038221  retn
```
