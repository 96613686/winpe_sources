# ClusApi::StoragePool::IsEqual(std::shared_ptr<ClusApi::IStorage> const &)

- ea: `0x18004a340`
- end: `0x18004a425`
- name: `?IsEqual@StoragePool@ClusApi@@UEAA_NAEBV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002ae0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18004a340`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a3dc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a3dc`

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
0x18004a340  mov     [rsp+arg_10], rbx
0x18004a345  mov     [rsp+arg_18], rsi
0x18004a34a  push    rdi
0x18004a34b  sub     rsp, 80h
0x18004a352  mov     rax, cs:__security_cookie
0x18004a359  xor     rax, rsp
0x18004a35c  mov     [rsp+88h+var_18], rax
0x18004a361  mov     rsi, rdx
0x18004a364  mov     rdi, rcx
0x18004a367  mov     rax, [rcx]
0x18004a36a  mov     rax, [rax]
0x18004a36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a372  mov     ebx, eax
0x18004a374  mov     rcx, [rsi]
0x18004a377  mov     rdx, [rcx]
0x18004a37a  mov     rax, [rdx]
0x18004a37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a382  cmp     eax, ebx
0x18004a384  jnz     short loc_18004A401
0x18004a386  mov     rax, [rdi]
0x18004a389  lea     rdx, [rsp+88h+var_38]
0x18004a38e  mov     rcx, rdi
0x18004a391  mov     rax, [rax+8]
0x18004a395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a39a  nop
0x18004a39b  mov     rcx, rax
0x18004a39e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004a3a3  mov     rbx, rax
0x18004a3a6  mov     rcx, [rsi]
0x18004a3a9  mov     rdx, [rcx]
0x18004a3ac  mov     rax, [rdx+8]
0x18004a3b0  lea     rdx, [rsp+88h+var_58]
0x18004a3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3ba  mov     rcx, rax
0x18004a3bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004a3c2  or      r9d, 0FFFFFFFFh; cchCount1
0x18004a3c6  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x18004a3cb  mov     [rsp+88h+lpString2], rbx; lpString2
0x18004a3d0  mov     r8, rax; lpString1
0x18004a3d3  lea     edx, [r9+2]; dwCmpFlags
0x18004a3d7  mov     ecx, 400h; Locale
0x18004a3dc  call    cs:__imp_CompareStringW
0x18004a3e2  cmp     eax, 2
0x18004a3e5  setz    bl
0x18004a3e8  lea     rcx, [rsp+88h+var_58]
0x18004a3ed  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a3f2  nop
0x18004a3f3  lea     rcx, [rsp+88h+var_38]
0x18004a3f8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a3fd  mov     al, bl
0x18004a3ff  jmp     short loc_18004A403
0x18004a401  xor     al, al
0x18004a403  mov     rcx, [rsp+88h+var_18]
0x18004a408  xor     rcx, rsp; StackCookie
0x18004a40b  call    __security_check_cookie
0x18004a410  lea     r11, [rsp+88h+var_8]
0x18004a418  mov     rbx, [r11+20h]
0x18004a41c  mov     rsi, [r11+28h]
0x18004a420  mov     rsp, r11
0x18004a423  pop     rdi
0x18004a424  retn
```
