# ClusApi::StoragePool::IsEqual(std::shared_ptr<ClusApi::IStorage> const &)

- ea: `0x180088da0`
- end: `0x180088e90`
- name: `?IsEqual@StoragePool@ClusApi@@UEAA_NAEBV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000e14c`
- `0x180088da0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088e40`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088e40`

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
0x180088da0  mov     [rsp+arg_10], rbx
0x180088da5  mov     [rsp+arg_18], rsi
0x180088daa  push    rdi
0x180088dab  sub     rsp, 80h
0x180088db2  mov     rax, cs:__security_cookie
0x180088db9  xor     rax, rsp
0x180088dbc  mov     [rsp+88h+var_18], rax
0x180088dc1  mov     rsi, rdx
0x180088dc4  mov     rdi, rcx
0x180088dc7  mov     rax, [rcx]
0x180088dca  mov     rax, [rax]
0x180088dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088dd2  mov     ebx, eax
0x180088dd4  mov     rcx, [rsi]
0x180088dd7  mov     rdx, [rcx]
0x180088dda  mov     rax, [rdx]
0x180088ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088de2  cmp     eax, ebx
0x180088de4  jnz     loc_180088E6B
0x180088dea  mov     rax, [rdi]
0x180088ded  lea     rdx, [rsp+88h+var_38]
0x180088df2  mov     rcx, rdi
0x180088df5  mov     rax, [rax+8]
0x180088df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088dfe  nop
0x180088dff  mov     rcx, rax
0x180088e02  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180088e07  mov     rbx, rax
0x180088e0a  mov     rcx, [rsi]
0x180088e0d  mov     rdx, [rcx]
0x180088e10  mov     rax, [rdx+8]
0x180088e14  lea     rdx, [rsp+88h+var_58]
0x180088e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e1e  mov     rcx, rax
0x180088e21  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180088e26  or      r9d, 0FFFFFFFFh; cchCount1
0x180088e2a  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x180088e2f  mov     [rsp+88h+lpString2], rbx; lpString2
0x180088e34  mov     r8, rax; lpString1
0x180088e37  lea     edx, [r9+2]; dwCmpFlags
0x180088e3b  mov     ecx, 400h; Locale
0x180088e40  call    cs:__imp_CompareStringW
0x180088e47  nop     dword ptr [rax+rax+00h]
0x180088e4c  cmp     eax, 2
0x180088e4f  setz    bl
0x180088e52  lea     rcx, [rsp+88h+var_58]
0x180088e57  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180088e5c  nop
0x180088e5d  lea     rcx, [rsp+88h+var_38]
0x180088e62  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180088e67  mov     al, bl
0x180088e69  jmp     short loc_180088E6D
0x180088e6b  xor     al, al
0x180088e6d  mov     rcx, [rsp+88h+var_18]
0x180088e72  xor     rcx, rsp; StackCookie
0x180088e75  call    __security_check_cookie
0x180088e7a  lea     r11, [rsp+88h+var_8]
0x180088e82  mov     rbx, [r11+20h]
0x180088e86  mov     rsi, [r11+28h]
0x180088e8a  mov     rsp, r11
0x180088e8d  pop     rdi
0x180088e8e  retn
```
