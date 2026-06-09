# ClusApi::StoragePool::IsEqual(std::shared_ptr<ClusApi::IStorage> const &)

- ea: `0x180086c30`
- end: `0x180086d15`
- name: `?IsEqual@StoragePool@ClusApi@@UEAA_NAEBV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000dd74`
- `0x180086c30`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086ccc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086ccc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ClusApi::StoragePool::IsEqual(__int64 a1, _QWORD *a2)
{
  int v4; // ebx
  __int64 v5; // rax
  const WCHAR *lpString2; // rbx
  __int64 v7; // rax
  const WCHAR *v8; // rax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v11[32]; // [rsp+50h] [rbp-38h] BYREF

  v4 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
  if ( (**(unsigned int (__fastcall ***)(_QWORD))*a2)(*a2) != v4 )
    return 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 8LL))(a1, v11);
  lpString2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v5);
  v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a2 + 8LL))(*a2, v10);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7);
  LOBYTE(lpString2) = CompareStringW(0x400u, 1u, v8, -1, lpString2, -1) == 2;
  std::wstring::_Tidy_deallocate(v10);
  std::wstring::_Tidy_deallocate(v11);
  return (char)lpString2;
}

```

## disassembly

```asm
0x180086c30  mov     [rsp+arg_10], rbx
0x180086c35  mov     [rsp+arg_18], rsi
0x180086c3a  push    rdi
0x180086c3b  sub     rsp, 80h
0x180086c42  mov     rax, cs:__security_cookie
0x180086c49  xor     rax, rsp
0x180086c4c  mov     [rsp+88h+var_18], rax
0x180086c51  mov     rsi, rdx
0x180086c54  mov     rdi, rcx
0x180086c57  mov     rax, [rcx]
0x180086c5a  mov     rax, [rax]
0x180086c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086c62  mov     ebx, eax
0x180086c64  mov     rcx, [rsi]
0x180086c67  mov     rdx, [rcx]
0x180086c6a  mov     rax, [rdx]
0x180086c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086c72  cmp     eax, ebx
0x180086c74  jnz     short loc_180086CF1
0x180086c76  mov     rax, [rdi]
0x180086c79  lea     rdx, [rsp+88h+var_38]
0x180086c7e  mov     rcx, rdi
0x180086c81  mov     rax, [rax+8]
0x180086c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086c8a  nop
0x180086c8b  mov     rcx, rax
0x180086c8e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180086c93  mov     rbx, rax
0x180086c96  mov     rcx, [rsi]
0x180086c99  mov     rdx, [rcx]
0x180086c9c  mov     rax, [rdx+8]
0x180086ca0  lea     rdx, [rsp+88h+var_58]
0x180086ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086caa  mov     rcx, rax
0x180086cad  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180086cb2  or      r9d, 0FFFFFFFFh; cchCount1
0x180086cb6  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x180086cbb  mov     [rsp+88h+lpString2], rbx; lpString2
0x180086cc0  mov     r8, rax; lpString1
0x180086cc3  lea     edx, [r9+2]; dwCmpFlags
0x180086cc7  mov     ecx, 400h; Locale
0x180086ccc  call    cs:__imp_CompareStringW
0x180086cd2  cmp     eax, 2
0x180086cd5  setz    bl
0x180086cd8  lea     rcx, [rsp+88h+var_58]
0x180086cdd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086ce2  nop
0x180086ce3  lea     rcx, [rsp+88h+var_38]
0x180086ce8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086ced  mov     al, bl
0x180086cef  jmp     short loc_180086CF3
0x180086cf1  xor     al, al
0x180086cf3  mov     rcx, [rsp+88h+var_18]
0x180086cf8  xor     rcx, rsp; StackCookie
0x180086cfb  call    __security_check_cookie
0x180086d00  lea     r11, [rsp+88h+var_8]
0x180086d08  mov     rbx, [r11+20h]
0x180086d0c  mov     rsi, [r11+28h]
0x180086d10  mov     rsp, r11
0x180086d13  pop     rdi
0x180086d14  retn
```
