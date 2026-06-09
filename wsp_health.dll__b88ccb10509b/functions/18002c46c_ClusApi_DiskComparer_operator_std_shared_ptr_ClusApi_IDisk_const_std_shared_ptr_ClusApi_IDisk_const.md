# ClusApi::DiskComparer::operator()(std::shared_ptr<ClusApi::IDisk> const &,std::shared_ptr<ClusApi::IDisk> const &)

- ea: `0x18002c46c`
- end: `0x18002c578`
- name: `??RDiskComparer@ClusApi@@QEBA_NAEBV?$shared_ptr@UIDisk@ClusApi@@@std@@0@Z`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002b5ec`

## callees

- `0x180002ae0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18002c46c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c534`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c534`

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
0x18002c46c  mov     [rsp+arg_0], rbx
0x18002c471  push    rsi
0x18002c472  push    rdi
0x18002c473  push    r14
0x18002c475  sub     rsp, 80h
0x18002c47c  mov     rax, cs:__security_cookie
0x18002c483  xor     rax, rsp
0x18002c486  mov     [rsp+98h+var_28], rax
0x18002c48b  mov     r14, r8
0x18002c48e  mov     rsi, rdx
0x18002c491  mov     rcx, [rdx]
0x18002c494  mov     rdi, [r8]
0x18002c497  mov     rax, [rcx]
0x18002c49a  mov     rax, [rax]
0x18002c49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4a2  mov     ebx, eax
0x18002c4a4  mov     rdx, [rdi]
0x18002c4a7  mov     rcx, rdi
0x18002c4aa  mov     rax, [rdx]
0x18002c4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4b2  cmp     ebx, eax
0x18002c4b4  jz      short loc_18002C4DE
0x18002c4b6  mov     rcx, [rsi]
0x18002c4b9  mov     rdi, [r14]
0x18002c4bc  mov     rax, [rcx]
0x18002c4bf  mov     rax, [rax]
0x18002c4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4c7  mov     ebx, eax
0x18002c4c9  mov     rdx, [rdi]
0x18002c4cc  mov     rcx, rdi
0x18002c4cf  mov     rax, [rdx]
0x18002c4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4d7  cmp     ebx, eax
0x18002c4d9  setl    al
0x18002c4dc  jmp     short loc_18002C557
0x18002c4de  mov     rcx, [r14]
0x18002c4e1  mov     rax, [rcx]
0x18002c4e4  lea     rdx, [rsp+98h+var_48]
0x18002c4e9  mov     rax, [rax+8]
0x18002c4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4f2  nop
0x18002c4f3  mov     rcx, rax
0x18002c4f6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c4fb  mov     rbx, rax
0x18002c4fe  mov     rcx, [rsi]
0x18002c501  mov     rdx, [rcx]
0x18002c504  mov     rax, [rdx+8]
0x18002c508  lea     rdx, [rsp+98h+var_68]
0x18002c50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c512  mov     rcx, rax
0x18002c515  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c51a  or      r9d, 0FFFFFFFFh; cchCount1
0x18002c51e  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x18002c523  mov     [rsp+98h+lpString2], rbx; lpString2
0x18002c528  mov     r8, rax; lpString1
0x18002c52b  lea     edx, [r9+2]; dwCmpFlags
0x18002c52f  mov     ecx, 400h; Locale
0x18002c534  call    cs:__imp_CompareStringW
0x18002c53a  lea     ebx, [rax-2]
0x18002c53d  shr     ebx, 1Fh
0x18002c540  lea     rcx, [rsp+98h+var_68]
0x18002c545  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c54a  nop
0x18002c54b  lea     rcx, [rsp+98h+var_48]
0x18002c550  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c555  mov     al, bl
0x18002c557  mov     rcx, [rsp+98h+var_28]
0x18002c55c  xor     rcx, rsp; StackCookie
0x18002c55f  call    __security_check_cookie
0x18002c564  mov     rbx, [rsp+98h+arg_0]
0x18002c56c  add     rsp, 80h
0x18002c573  pop     r14
0x18002c575  pop     rdi
0x18002c576  pop     rsi
0x18002c577  retn
```
