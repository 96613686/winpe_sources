# smapi::FileServerContext::process_field(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::bitset<64> &)

- ea: `0x18004fa04`
- end: `0x18004fb99`
- name: `?process_field@FileServerContext@smapi@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$bitset@$0EA@@4@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180042ab4`

## callees

- `0x18000e14c`
- `0x1800443a0`
- `0x18004fa04`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fa44`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fa78`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fab9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004faed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fb31`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fb65`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fa44`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fa78`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fab9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004faed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fb31`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fb65`

## string_xrefs

- `0x18004fb16`: `FileSharingProtocols`
- `0x18004fb4a`: `FileSharingProtocolVersions`

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
0x18004fa04  push    rbx
0x18004fa06  push    rbp
0x18004fa07  push    rsi
0x18004fa08  push    rdi
0x18004fa09  push    r14
0x18004fa0b  sub     rsp, 30h
0x18004fa0f  mov     rcx, rdx
0x18004fa12  mov     rdi, r8
0x18004fa15  mov     rbx, rdx
0x18004fa18  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004fa1d  or      ebp, 0FFFFFFFFh
0x18004fa20  lea     rcx, aObjectid; "ObjectId"
0x18004fa27  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004fa2b  mov     r14d, 400h
0x18004fa31  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004fa36  mov     r9d, ebp; cchCount1
0x18004fa39  mov     r8, rax; lpString1
0x18004fa3c  mov     ecx, r14d; Locale
0x18004fa3f  lea     esi, [rbp+2]
0x18004fa42  mov     edx, esi; dwCmpFlags
0x18004fa44  call    cs:__imp_CompareStringW
0x18004fa4b  nop     dword ptr [rax+rax+00h]
0x18004fa50  cmp     eax, 2
0x18004fa53  jz      short loc_18004FA89
0x18004fa55  mov     rcx, rbx
0x18004fa58  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004fa5d  lea     rcx, aUniqueid; "UniqueId"
0x18004fa64  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004fa68  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004fa6d  mov     r9d, ebp; cchCount1
0x18004fa70  mov     ecx, r14d; Locale
0x18004fa73  mov     r8, rax; lpString1
0x18004fa76  mov     edx, esi; dwCmpFlags
0x18004fa78  call    cs:__imp_CompareStringW
0x18004fa7f  nop     dword ptr [rax+rax+00h]
0x18004fa84  cmp     eax, 2
0x18004fa87  jnz     short loc_18004FA96
0x18004fa89  mov     r8b, sil
0x18004fa8c  xor     edx, edx
0x18004fa8e  mov     rcx, rdi
0x18004fa91  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18004fa96  mov     rcx, rbx
0x18004fa99  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004fa9e  lea     rcx, aSupportsfilesh; "SupportsFileShareCreation"
0x18004faa5  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004faa9  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004faae  mov     r9d, ebp; cchCount1
0x18004fab1  mov     ecx, r14d; Locale
0x18004fab4  mov     r8, rax; lpString1
0x18004fab7  mov     edx, esi; dwCmpFlags
0x18004fab9  call    cs:__imp_CompareStringW
0x18004fac0  nop     dword ptr [rax+rax+00h]
0x18004fac5  cmp     eax, 2
0x18004fac8  jz      short loc_18004FAFE
0x18004faca  mov     rcx, rbx
0x18004facd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004fad2  lea     rcx, aSupportscontin_0; "SupportsContinuouslyAvailable"
0x18004fad9  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004fadd  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004fae2  mov     r9d, ebp; cchCount1
0x18004fae5  mov     ecx, r14d; Locale
0x18004fae8  mov     r8, rax; lpString1
0x18004faeb  mov     edx, esi; dwCmpFlags
0x18004faed  call    cs:__imp_CompareStringW
0x18004faf4  nop     dword ptr [rax+rax+00h]
0x18004faf9  cmp     eax, 2
0x18004fafc  jnz     short loc_18004FB0E
0x18004fafe  mov     r8b, sil
0x18004fb01  mov     edx, 4
0x18004fb06  mov     rcx, rdi
0x18004fb09  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18004fb0e  mov     rcx, rbx
0x18004fb11  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004fb16  lea     rcx, aFilesharingpro_0; "FileSharingProtocols"
0x18004fb1d  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004fb21  mov     [rsp+58h+lpString2], rcx; lpString2
0x18004fb26  mov     r9d, ebp; cchCount1
0x18004fb29  mov     ecx, r14d; Locale
0x18004fb2c  mov     r8, rax; lpString1
0x18004fb2f  mov     edx, esi; dwCmpFlags
0x18004fb31  call    cs:__imp_CompareStringW
0x18004fb38  nop     dword ptr [rax+rax+00h]
0x18004fb3d  cmp     eax, 2
0x18004fb40  jz      short loc_18004FB7A
0x18004fb42  mov     rcx, rbx
0x18004fb45  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004fb4a  lea     rdx, aFilesharingpro; "FileSharingProtocolVersions"
0x18004fb51  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18004fb55  mov     [rsp+58h+lpString2], rdx; lpString2
0x18004fb5a  mov     r9d, ebp; cchCount1
0x18004fb5d  mov     edx, esi; dwCmpFlags
0x18004fb5f  mov     r8, rax; lpString1
0x18004fb62  mov     ecx, r14d; Locale
0x18004fb65  call    cs:__imp_CompareStringW
0x18004fb6c  nop     dword ptr [rax+rax+00h]
0x18004fb71  cmp     eax, 2
0x18004fb74  jz      short loc_18004FB7A
0x18004fb76  xor     al, al
0x18004fb78  jmp     short loc_18004FB8D
0x18004fb7a  mov     r8b, sil
0x18004fb7d  mov     edx, 5
0x18004fb82  mov     rcx, rdi
0x18004fb85  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18004fb8a  mov     al, sil
0x18004fb8d  add     rsp, 30h
0x18004fb91  pop     r14
0x18004fb93  pop     rdi
0x18004fb94  pop     rsi
0x18004fb95  pop     rbp
0x18004fb96  pop     rbx
0x18004fb97  retn
```
