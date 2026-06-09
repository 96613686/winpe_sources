# smapi::FileServerContext::process_field(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::bitset<64> &)

- ea: `0x18004e9c4`
- end: `0x18004eb34`
- name: `?process_field@FileServerContext@smapi@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$bitset@$0EA@@4@@Z`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180041784`

## callees

- `0x18000dd74`
- `0x180043128`
- `0x18004e9c4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ea04`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ea32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ea6d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ea9b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ead9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004eb07`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ea04`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ea32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ea6d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ea9b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ead9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004eb07`

## string_xrefs

- `0x18004eabe`: `FileSharingProtocols`
- `0x18004eaec`: `FileSharingProtocolVersions`

## pseudocode

```c
char __fastcall smapi::FileServerContext::process_field(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *v5; // rax
  __int64 v6; // r8
  const WCHAR *v7; // rax
  const WCHAR *v8; // rax
  __int64 v9; // r8
  const WCHAR *v10; // rax
  const WCHAR *v11; // rax
  __int64 v12; // r8
  const WCHAR *v13; // rax

  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  if ( CompareStringW(0x400u, 1u, v5, -1, L"ObjectId", -1) == 2
    || (v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2),
        CompareStringW(0x400u, 1u, v7, -1, L"UniqueId", -1) == 2) )
  {
    LOBYTE(v6) = 1;
    std::bitset<64>::set(a3, 0, v6);
  }
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  if ( CompareStringW(0x400u, 1u, v8, -1, L"SupportsFileShareCreation", -1) == 2
    || (v10 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2),
        CompareStringW(0x400u, 1u, v10, -1, L"SupportsContinuouslyAvailable", -1) == 2) )
  {
    LOBYTE(v9) = 1;
    std::bitset<64>::set(a3, 4, v9);
  }
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  if ( CompareStringW(0x400u, 1u, v11, -1, L"FileSharingProtocols", -1) != 2 )
  {
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    if ( CompareStringW(0x400u, 1u, v13, -1, L"FileSharingProtocolVersions", -1) != 2 )
      return 0;
  }
  LOBYTE(v12) = 1;
  std::bitset<64>::set(a3, 5, v12);
  return 1;
}

```

## disassembly

```asm
0x18004e9c4  push    rbx
0x18004e9c6  push    rbp
0x18004e9c7  push    rsi
0x18004e9c8  push    rdi
0x18004e9c9  push    r14
0x18004e9cb  sub     rsp, 30h
0x18004e9cf  mov     rcx, rdx
0x18004e9d2  mov     rdi, r8
0x18004e9d5  mov     rbx, rdx
0x18004e9d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004e9dd  or      ebp, 0FFFFFFFFh
0x18004e9e0  lea     rcx, aObjectid; "ObjectId"
0x18004e9e7  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004e9eb  mov     r14d, 400h
0x18004e9f1  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004e9f6  mov     r9d, ebp; cchCount1
0x18004e9f9  mov     r8, rax; lpString1
0x18004e9fc  mov     ecx, r14d; Locale
0x18004e9ff  lea     esi, [rbp+2]
0x18004ea02  mov     edx, esi; dwCmpFlags
0x18004ea04  call    cs:__imp_CompareStringW
0x18004ea0a  cmp     eax, 2
0x18004ea0d  jz      short loc_18004EA3D
0x18004ea0f  mov     rcx, rbx
0x18004ea12  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004ea17  lea     rcx, aUniqueid; "UniqueId"
0x18004ea1e  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004ea22  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004ea27  mov     r9d, ebp; cchCount1
0x18004ea2a  mov     ecx, r14d; Locale
0x18004ea2d  mov     r8, rax; lpString1
0x18004ea30  mov     edx, esi; dwCmpFlags
0x18004ea32  call    cs:__imp_CompareStringW
0x18004ea38  cmp     eax, 2
0x18004ea3b  jnz     short loc_18004EA4A
0x18004ea3d  mov     r8b, sil
0x18004ea40  xor     edx, edx
0x18004ea42  mov     rcx, rdi
0x18004ea45  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18004ea4a  mov     rcx, rbx
0x18004ea4d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004ea52  lea     rcx, aSupportsfilesh; "SupportsFileShareCreation"
0x18004ea59  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004ea5d  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004ea62  mov     r9d, ebp; cchCount1
0x18004ea65  mov     ecx, r14d; Locale
0x18004ea68  mov     r8, rax; lpString1
0x18004ea6b  mov     edx, esi; dwCmpFlags
0x18004ea6d  call    cs:__imp_CompareStringW
0x18004ea73  cmp     eax, 2
0x18004ea76  jz      short loc_18004EAA6
0x18004ea78  mov     rcx, rbx
0x18004ea7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004ea80  lea     rcx, aSupportscontin_0; "SupportsContinuouslyAvailable"
0x18004ea87  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004ea8b  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004ea90  mov     r9d, ebp; cchCount1
0x18004ea93  mov     ecx, r14d; Locale
0x18004ea96  mov     r8, rax; lpString1
0x18004ea99  mov     edx, esi; dwCmpFlags
0x18004ea9b  call    cs:__imp_CompareStringW
0x18004eaa1  cmp     eax, 2
0x18004eaa4  jnz     short loc_18004EAB6
0x18004eaa6  mov     r8b, sil
0x18004eaa9  mov     edx, 4
0x18004eaae  mov     rcx, rdi
0x18004eab1  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18004eab6  mov     rcx, rbx
0x18004eab9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004eabe  lea     rcx, aFilesharingpro_0; "FileSharingProtocols"
0x18004eac5  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004eac9  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004eace  mov     r9d, ebp; cchCount1
0x18004ead1  mov     ecx, r14d; Locale
0x18004ead4  mov     r8, rax; lpString1
0x18004ead7  mov     edx, esi; dwCmpFlags
0x18004ead9  call    cs:__imp_CompareStringW
0x18004eadf  cmp     eax, 2
0x18004eae2  jz      short loc_18004EB16
0x18004eae4  mov     rcx, rbx
0x18004eae7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004eaec  lea     rdx, aFilesharingpro; "FileSharingProtocolVersions"
0x18004eaf3  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004eaf7  mov     [rsp+58h+lpString2], rdx; lpString2
0x18004eafc  mov     r9d, ebp; cchCount1
0x18004eaff  mov     edx, esi; dwCmpFlags
0x18004eb01  mov     r8, rax; lpString1
0x18004eb04  mov     ecx, r14d; Locale
0x18004eb07  call    cs:__imp_CompareStringW
0x18004eb0d  cmp     eax, 2
0x18004eb10  jz      short loc_18004EB16
0x18004eb12  xor     al, al
0x18004eb14  jmp     short loc_18004EB29
0x18004eb16  mov     r8b, sil
0x18004eb19  mov     edx, 5
0x18004eb1e  mov     rcx, rdi
0x18004eb21  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18004eb26  mov     al, sil
0x18004eb29  add     rsp, 30h
0x18004eb2d  pop     r14
0x18004eb2f  pop     rdi
0x18004eb30  pop     rsi
0x18004eb31  pop     rbp
0x18004eb32  pop     rbx
0x18004eb33  retn
```
