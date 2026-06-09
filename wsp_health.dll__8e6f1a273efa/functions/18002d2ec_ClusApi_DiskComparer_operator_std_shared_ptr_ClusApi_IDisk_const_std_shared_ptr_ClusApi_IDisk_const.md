# ClusApi::DiskComparer::operator()(std::shared_ptr<ClusApi::IDisk> const &,std::shared_ptr<ClusApi::IDisk> const &)

- ea: `0x18002d2ec`
- end: `0x18002d3ff`
- name: `??RDiskComparer@ClusApi@@QEBA_NAEBV?$shared_ptr@UIDisk@ClusApi@@@std@@0@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002c3b8`

## callees

- `0x180002b50`
- `0x18000da34`
- `0x18000daf8`
- `0x18002d2ec`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002d3b4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002d3b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall ClusApi::DiskComparer::operator()(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int (__fastcall ***v5)(_QWORD); // rdi
  int v6; // ebx
  int (__fastcall ***v7)(_QWORD); // rdi
  int v8; // ebx
  __int64 v10; // rax
  const WCHAR *lpString2; // rbx
  __int64 v12; // rax
  const WCHAR *v13; // rax
  _BYTE v14[32]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-48h] BYREF

  v5 = (unsigned int (__fastcall ***)(_QWORD))*a3;
  v6 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
  if ( v6 == (**v5)(v5) )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a3 + 8LL))(*a3, v15);
    lpString2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v10);
    v12 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a2 + 8LL))(*a2, v14);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v12);
    LODWORD(lpString2) = (unsigned int)(CompareStringW(0x400u, 1u, v13, -1, lpString2, -1) - 2) >> 31;
    std::wstring::_Tidy_deallocate(v14);
    std::wstring::_Tidy_deallocate(v15);
    return (char)lpString2;
  }
  else
  {
    v7 = (int (__fastcall ***)(_QWORD))*a3;
    v8 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
    return v8 < (**v7)(v7);
  }
}

```

## disassembly

```asm
0x18002d2ec  mov     [rsp+arg_0], rbx
0x18002d2f1  push    rsi
0x18002d2f2  push    rdi
0x18002d2f3  push    r14
0x18002d2f5  sub     rsp, 80h
0x18002d2fc  mov     rax, cs:__security_cookie
0x18002d303  xor     rax, rsp
0x18002d306  mov     [rsp+98h+var_28], rax
0x18002d30b  mov     r14, r8
0x18002d30e  mov     rsi, rdx
0x18002d311  mov     rcx, [rdx]
0x18002d314  mov     rdi, [r8]
0x18002d317  mov     rax, [rcx]
0x18002d31a  mov     rax, [rax]
0x18002d31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d322  mov     ebx, eax
0x18002d324  mov     rdx, [rdi]
0x18002d327  mov     rcx, rdi
0x18002d32a  mov     rax, [rdx]
0x18002d32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d332  cmp     ebx, eax
0x18002d334  jz      short loc_18002D35E
0x18002d336  mov     rcx, [rsi]
0x18002d339  mov     rdi, [r14]
0x18002d33c  mov     rax, [rcx]
0x18002d33f  mov     rax, [rax]
0x18002d342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d347  mov     ebx, eax
0x18002d349  mov     rdx, [rdi]
0x18002d34c  mov     rcx, rdi
0x18002d34f  mov     rax, [rdx]
0x18002d352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d357  cmp     ebx, eax
0x18002d359  setl    al
0x18002d35c  jmp     short loc_18002D3DD
0x18002d35e  mov     rcx, [r14]
0x18002d361  mov     rax, [rcx]
0x18002d364  lea     rdx, [rsp+98h+var_48]
0x18002d369  mov     rax, [rax+8]
0x18002d36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d372  nop
0x18002d373  mov     rcx, rax
0x18002d376  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d37b  mov     rbx, rax
0x18002d37e  mov     rcx, [rsi]
0x18002d381  mov     rdx, [rcx]
0x18002d384  mov     rax, [rdx+8]
0x18002d388  lea     rdx, [rsp+98h+var_68]
0x18002d38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d392  mov     rcx, rax
0x18002d395  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d39a  or      r9d, 0FFFFFFFFh; cchCount1
0x18002d39e  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x18002d3a3  mov     [rsp+98h+lpString2], rbx; lpString2
0x18002d3a8  mov     r8, rax; lpString1
0x18002d3ab  lea     edx, [r9+2]; dwCmpFlags
0x18002d3af  mov     ecx, 400h; Locale
0x18002d3b4  call    cs:__imp_CompareStringW
0x18002d3bb  nop     dword ptr [rax+rax+00h]
0x18002d3c0  lea     ebx, [rax-2]
0x18002d3c3  shr     ebx, 1Fh
0x18002d3c6  lea     rcx, [rsp+98h+var_68]
0x18002d3cb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d3d0  nop
0x18002d3d1  lea     rcx, [rsp+98h+var_48]
0x18002d3d6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d3db  mov     al, bl
0x18002d3dd  mov     rcx, [rsp+98h+var_28]
0x18002d3e2  xor     rcx, rsp; StackCookie
0x18002d3e5  call    __security_check_cookie
0x18002d3ea  mov     rbx, [rsp+98h+arg_0]
0x18002d3f2  add     rsp, 80h
0x18002d3f9  pop     r14
0x18002d3fb  pop     rdi
0x18002d3fc  pop     rsi
0x18002d3fd  retn
```
