# ClusApi::DiskComparer::operator()(std::shared_ptr<ClusApi::IDisk> const &,std::shared_ptr<ClusApi::IDisk> const &)

- ea: `0x18003017c`
- end: `0x180030288`
- name: `??RDiskComparer@ClusApi@@QEBA_NAEBV?$shared_ptr@UIDisk@ClusApi@@@std@@0@Z`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002f318`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000dd74`
- `0x18003017c`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180030244`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180030244`

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
0x18003017c  mov     [rsp+arg_0], rbx
0x180030181  push    rsi
0x180030182  push    rdi
0x180030183  push    r14
0x180030185  sub     rsp, 80h
0x18003018c  mov     rax, cs:__security_cookie
0x180030193  xor     rax, rsp
0x180030196  mov     [rsp+98h+var_28], rax
0x18003019b  mov     r14, r8
0x18003019e  mov     rsi, rdx
0x1800301a1  mov     rcx, [rdx]
0x1800301a4  mov     rdi, [r8]
0x1800301a7  mov     rax, [rcx]
0x1800301aa  mov     rax, [rax]
0x1800301ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301b2  mov     ebx, eax
0x1800301b4  mov     rdx, [rdi]
0x1800301b7  mov     rcx, rdi
0x1800301ba  mov     rax, [rdx]
0x1800301bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301c2  cmp     ebx, eax
0x1800301c4  jz      short loc_1800301EE
0x1800301c6  mov     rcx, [rsi]
0x1800301c9  mov     rdi, [r14]
0x1800301cc  mov     rax, [rcx]
0x1800301cf  mov     rax, [rax]
0x1800301d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301d7  mov     ebx, eax
0x1800301d9  mov     rdx, [rdi]
0x1800301dc  mov     rcx, rdi
0x1800301df  mov     rax, [rdx]
0x1800301e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301e7  cmp     ebx, eax
0x1800301e9  setl    al
0x1800301ec  jmp     short loc_180030267
0x1800301ee  mov     rcx, [r14]
0x1800301f1  mov     rax, [rcx]
0x1800301f4  lea     rdx, [rsp+98h+var_48]
0x1800301f9  mov     rax, [rax+8]
0x1800301fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030202  nop
0x180030203  mov     rcx, rax
0x180030206  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003020b  mov     rbx, rax
0x18003020e  mov     rcx, [rsi]
0x180030211  mov     rdx, [rcx]
0x180030214  mov     rax, [rdx+8]
0x180030218  lea     rdx, [rsp+98h+var_68]
0x18003021d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030222  mov     rcx, rax
0x180030225  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003022a  or      r9d, 0FFFFFFFFh; cchCount1
0x18003022e  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x180030233  mov     [rsp+98h+lpString2], rbx; lpString2
0x180030238  mov     r8, rax; lpString1
0x18003023b  lea     edx, [r9+2]; dwCmpFlags
0x18003023f  mov     ecx, 400h; Locale
0x180030244  call    cs:__imp_CompareStringW
0x18003024a  lea     ebx, [rax-2]
0x18003024d  shr     ebx, 1Fh
0x180030250  lea     rcx, [rsp+98h+var_68]
0x180030255  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003025a  nop
0x18003025b  lea     rcx, [rsp+98h+var_48]
0x180030260  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030265  mov     al, bl
0x180030267  mov     rcx, [rsp+98h+var_28]
0x18003026c  xor     rcx, rsp; StackCookie
0x18003026f  call    __security_check_cookie
0x180030274  mov     rbx, [rsp+98h+arg_0]
0x18003027c  add     rsp, 80h
0x180030283  pop     r14
0x180030285  pop     rdi
0x180030286  pop     rsi
0x180030287  retn
```
