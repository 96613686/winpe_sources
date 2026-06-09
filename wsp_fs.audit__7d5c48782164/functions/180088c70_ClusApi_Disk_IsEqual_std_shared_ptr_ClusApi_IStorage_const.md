# ClusApi::Disk::IsEqual(std::shared_ptr<ClusApi::IStorage> const &)

- ea: `0x180088c70`
- end: `0x180088d7e`
- name: `?IsEqual@Disk@ClusApi@@UEAA_NAEBV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180088d90`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000e14c`
- `0x180088c70`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088d1f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088d1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall ClusApi::Disk::IsEqual(__int64 a1, _QWORD *a2)
{
  char v4; // di
  int v5; // ebx
  __int64 v6; // rax
  const WCHAR *lpString2; // rbx
  __int64 v8; // rax
  const WCHAR *v9; // rax
  bool v10; // bl
  _BYTE v12[32]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v13[32]; // [rsp+58h] [rbp-40h] BYREF

  v4 = 0;
  v5 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
  v10 = 0;
  if ( (**(unsigned int (__fastcall ***)(__int64))a1)(a1) == v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 8LL))(a1, v13);
    lpString2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
    v8 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a2 + 8LL))(*a2, v12);
    v4 = 3;
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v8);
    if ( CompareStringW(0x400u, 1u, v9, -1, lpString2, -1) == 2 )
      v10 = 1;
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    std::wstring::_Tidy_deallocate(v12);
  }
  if ( (v4 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v13);
  return v10;
}

```

## disassembly

```asm
0x180088c70  mov     [rsp+arg_10], rbx
0x180088c75  push    rsi
0x180088c76  push    rdi
0x180088c77  push    r14
0x180088c79  sub     rsp, 80h
0x180088c80  mov     rax, cs:__security_cookie
0x180088c87  xor     rax, rsp
0x180088c8a  mov     [rsp+98h+var_20], rax
0x180088c8f  mov     r14, rdx
0x180088c92  mov     rsi, rcx
0x180088c95  xor     edi, edi
0x180088c97  mov     [rsp+98h+var_68], edi
0x180088c9b  mov     rcx, [rdx]
0x180088c9e  mov     rax, [rcx]
0x180088ca1  mov     rax, [rax]
0x180088ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ca9  mov     ebx, eax
0x180088cab  mov     rcx, [rsi]
0x180088cae  mov     rax, [rcx]
0x180088cb1  mov     rcx, rsi
0x180088cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088cb9  cmp     eax, ebx
0x180088cbb  jnz     short loc_180088D34
0x180088cbd  mov     rax, [rsi]
0x180088cc0  lea     rdx, [rsp+98h+var_40]
0x180088cc5  mov     rcx, rsi
0x180088cc8  mov     rax, [rax+8]
0x180088ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088cd1  nop
0x180088cd2  mov     [rsp+98h+var_68], 1
0x180088cda  mov     rcx, rax
0x180088cdd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180088ce2  mov     rbx, rax
0x180088ce5  mov     rcx, [r14]
0x180088ce8  mov     rdx, [rcx]
0x180088ceb  mov     rax, [rdx+8]
0x180088cef  lea     rdx, [rsp+98h+var_60]
0x180088cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088cf9  mov     edi, 3
0x180088cfe  mov     rcx, rax
0x180088d01  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180088d06  or      r9d, 0FFFFFFFFh; cchCount1
0x180088d0a  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x180088d0f  mov     [rsp+98h+lpString2], rbx; lpString2
0x180088d14  mov     r8, rax; lpString1
0x180088d17  lea     edx, [rdi-2]; dwCmpFlags
0x180088d1a  mov     ecx, 400h; Locale
0x180088d1f  call    cs:__imp_CompareStringW
0x180088d26  nop     dword ptr [rax+rax+00h]
0x180088d2b  cmp     eax, 2
0x180088d2e  jnz     short loc_180088D34
0x180088d30  mov     bl, 1
0x180088d32  jmp     short loc_180088D36
0x180088d34  xor     bl, bl
0x180088d36  test    dil, 2
0x180088d3a  jz      short loc_180088D4A
0x180088d3c  and     edi, 0FFFFFFFDh
0x180088d3f  lea     rcx, [rsp+98h+var_60]
0x180088d44  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180088d49  nop
0x180088d4a  test    dil, 1
0x180088d4e  jz      short loc_180088D5A
0x180088d50  lea     rcx, [rsp+98h+var_40]
0x180088d55  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180088d5a  mov     al, bl
0x180088d5c  mov     rcx, [rsp+98h+var_20]
0x180088d61  xor     rcx, rsp; StackCookie
0x180088d64  call    __security_check_cookie
0x180088d69  mov     rbx, [rsp+98h+arg_10]
0x180088d71  add     rsp, 80h
0x180088d78  pop     r14
0x180088d7a  pop     rdi
0x180088d7b  pop     rsi
0x180088d7c  retn
```
