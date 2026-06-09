# ClusApi::StoragePool::IsEqual(std::shared_ptr<ClusApi::IStorage> const &)

- ea: `0x18004bc90`
- end: `0x18004bd80`
- name: `?IsEqual@StoragePool@ClusApi@@UEAA_NAEBV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002b50`
- `0x18000da34`
- `0x18000daf8`
- `0x18004bc90`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004bd30`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004bd30`

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
0x18004bc90  mov     [rsp+arg_10], rbx
0x18004bc95  mov     [rsp+arg_18], rsi
0x18004bc9a  push    rdi
0x18004bc9b  sub     rsp, 80h
0x18004bca2  mov     rax, cs:__security_cookie
0x18004bca9  xor     rax, rsp
0x18004bcac  mov     [rsp+88h+var_18], rax
0x18004bcb1  mov     rsi, rdx
0x18004bcb4  mov     rdi, rcx
0x18004bcb7  mov     rax, [rcx]
0x18004bcba  mov     rax, [rax]
0x18004bcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcc2  mov     ebx, eax
0x18004bcc4  mov     rcx, [rsi]
0x18004bcc7  mov     rdx, [rcx]
0x18004bcca  mov     rax, [rdx]
0x18004bccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcd2  cmp     eax, ebx
0x18004bcd4  jnz     loc_18004BD5B
0x18004bcda  mov     rax, [rdi]
0x18004bcdd  lea     rdx, [rsp+88h+var_38]
0x18004bce2  mov     rcx, rdi
0x18004bce5  mov     rax, [rax+8]
0x18004bce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcee  nop
0x18004bcef  mov     rcx, rax
0x18004bcf2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004bcf7  mov     rbx, rax
0x18004bcfa  mov     rcx, [rsi]
0x18004bcfd  mov     rdx, [rcx]
0x18004bd00  mov     rax, [rdx+8]
0x18004bd04  lea     rdx, [rsp+88h+var_58]
0x18004bd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd0e  mov     rcx, rax
0x18004bd11  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004bd16  or      r9d, 0FFFFFFFFh; cchCount1
0x18004bd1a  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x18004bd1f  mov     [rsp+88h+lpString2], rbx; lpString2
0x18004bd24  mov     r8, rax; lpString1
0x18004bd27  lea     edx, [r9+2]; dwCmpFlags
0x18004bd2b  mov     ecx, 400h; Locale
0x18004bd30  call    cs:__imp_CompareStringW
0x18004bd37  nop     dword ptr [rax+rax+00h]
0x18004bd3c  cmp     eax, 2
0x18004bd3f  setz    bl
0x18004bd42  lea     rcx, [rsp+88h+var_58]
0x18004bd47  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bd4c  nop
0x18004bd4d  lea     rcx, [rsp+88h+var_38]
0x18004bd52  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bd57  mov     al, bl
0x18004bd59  jmp     short loc_18004BD5D
0x18004bd5b  xor     al, al
0x18004bd5d  mov     rcx, [rsp+88h+var_18]
0x18004bd62  xor     rcx, rsp; StackCookie
0x18004bd65  call    __security_check_cookie
0x18004bd6a  lea     r11, [rsp+88h+var_8]
0x18004bd72  mov     rbx, [r11+20h]
0x18004bd76  mov     rsi, [r11+28h]
0x18004bd7a  mov     rsp, r11
0x18004bd7d  pop     rdi
0x18004bd7e  retn
```
