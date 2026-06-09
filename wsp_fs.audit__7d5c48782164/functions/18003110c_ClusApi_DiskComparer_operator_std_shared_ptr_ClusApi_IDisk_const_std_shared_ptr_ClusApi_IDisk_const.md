# ClusApi::DiskComparer::operator()(std::shared_ptr<ClusApi::IDisk> const &,std::shared_ptr<ClusApi::IDisk> const &)

- ea: `0x18003110c`
- end: `0x18003121f`
- name: `??RDiskComparer@ClusApi@@QEBA_NAEBV?$shared_ptr@UIDisk@ClusApi@@@std@@0@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800301f8`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000e14c`
- `0x18003110c`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800311d4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800311d4`

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
0x18003110c  mov     [rsp+arg_0], rbx
0x180031111  push    rsi
0x180031112  push    rdi
0x180031113  push    r14
0x180031115  sub     rsp, 80h
0x18003111c  mov     rax, cs:__security_cookie
0x180031123  xor     rax, rsp
0x180031126  mov     [rsp+98h+var_28], rax
0x18003112b  mov     r14, r8
0x18003112e  mov     rsi, rdx
0x180031131  mov     rcx, [rdx]
0x180031134  mov     rdi, [r8]
0x180031137  mov     rax, [rcx]
0x18003113a  mov     rax, [rax]
0x18003113d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031142  mov     ebx, eax
0x180031144  mov     rdx, [rdi]
0x180031147  mov     rcx, rdi
0x18003114a  mov     rax, [rdx]
0x18003114d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031152  cmp     ebx, eax
0x180031154  jz      short loc_18003117E
0x180031156  mov     rcx, [rsi]
0x180031159  mov     rdi, [r14]
0x18003115c  mov     rax, [rcx]
0x18003115f  mov     rax, [rax]
0x180031162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031167  mov     ebx, eax
0x180031169  mov     rdx, [rdi]
0x18003116c  mov     rcx, rdi
0x18003116f  mov     rax, [rdx]
0x180031172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031177  cmp     ebx, eax
0x180031179  setl    al
0x18003117c  jmp     short loc_1800311FD
0x18003117e  mov     rcx, [r14]
0x180031181  mov     rax, [rcx]
0x180031184  lea     rdx, [rsp+98h+var_48]
0x180031189  mov     rax, [rax+8]
0x18003118d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031192  nop
0x180031193  mov     rcx, rax
0x180031196  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003119b  mov     rbx, rax
0x18003119e  mov     rcx, [rsi]
0x1800311a1  mov     rdx, [rcx]
0x1800311a4  mov     rax, [rdx+8]
0x1800311a8  lea     rdx, [rsp+98h+var_68]
0x1800311ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311b2  mov     rcx, rax
0x1800311b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800311ba  or      r9d, 0FFFFFFFFh; cchCount1
0x1800311be  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x1800311c3  mov     [rsp+98h+lpString2], rbx; lpString2
0x1800311c8  mov     r8, rax; lpString1
0x1800311cb  lea     edx, [r9+2]; dwCmpFlags
0x1800311cf  mov     ecx, 400h; Locale
0x1800311d4  call    cs:__imp_CompareStringW
0x1800311db  nop     dword ptr [rax+rax+00h]
0x1800311e0  lea     ebx, [rax-2]
0x1800311e3  shr     ebx, 1Fh
0x1800311e6  lea     rcx, [rsp+98h+var_68]
0x1800311eb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800311f0  nop
0x1800311f1  lea     rcx, [rsp+98h+var_48]
0x1800311f6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800311fb  mov     al, bl
0x1800311fd  mov     rcx, [rsp+98h+var_28]
0x180031202  xor     rcx, rsp; StackCookie
0x180031205  call    __security_check_cookie
0x18003120a  mov     rbx, [rsp+98h+arg_0]
0x180031212  add     rsp, 80h
0x180031219  pop     r14
0x18003121b  pop     rdi
0x18003121c  pop     rsi
0x18003121d  retn
```
