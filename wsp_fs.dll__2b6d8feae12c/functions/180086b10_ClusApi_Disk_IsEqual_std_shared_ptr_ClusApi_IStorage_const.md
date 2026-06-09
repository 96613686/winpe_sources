# ClusApi::Disk::IsEqual(std::shared_ptr<ClusApi::IStorage> const &)

- ea: `0x180086b10`
- end: `0x180086c17`
- name: `?IsEqual@Disk@ClusApi@@UEAA_NAEBV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180086c20`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000dd74`
- `0x180086b10`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086bbf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086bbf`

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
0x180086b10  mov     [rsp+arg_10], rbx
0x180086b15  push    rsi
0x180086b16  push    rdi
0x180086b17  push    r14
0x180086b19  sub     rsp, 80h
0x180086b20  mov     rax, cs:__security_cookie
0x180086b27  xor     rax, rsp
0x180086b2a  mov     [rsp+98h+var_20], rax
0x180086b2f  mov     r14, rdx
0x180086b32  mov     rsi, rcx
0x180086b35  xor     edi, edi
0x180086b37  mov     [rsp+98h+var_68], edi
0x180086b3b  mov     rcx, [rdx]
0x180086b3e  mov     rax, [rcx]
0x180086b41  mov     rax, [rax]
0x180086b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086b49  mov     ebx, eax
0x180086b4b  mov     rcx, [rsi]
0x180086b4e  mov     rax, [rcx]
0x180086b51  mov     rcx, rsi
0x180086b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086b59  cmp     eax, ebx
0x180086b5b  jnz     short loc_180086BCE
0x180086b5d  mov     rax, [rsi]
0x180086b60  lea     rdx, [rsp+98h+var_40]
0x180086b65  mov     rcx, rsi
0x180086b68  mov     rax, [rax+8]
0x180086b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086b71  nop
0x180086b72  mov     [rsp+98h+var_68], 1
0x180086b7a  mov     rcx, rax
0x180086b7d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180086b82  mov     rbx, rax
0x180086b85  mov     rcx, [r14]
0x180086b88  mov     rdx, [rcx]
0x180086b8b  mov     rax, [rdx+8]
0x180086b8f  lea     rdx, [rsp+98h+var_60]
0x180086b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086b99  mov     edi, 3
0x180086b9e  mov     rcx, rax
0x180086ba1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180086ba6  or      r9d, 0FFFFFFFFh; cchCount1
0x180086baa  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x180086baf  mov     [rsp+98h+lpString2], rbx; lpString2
0x180086bb4  mov     r8, rax; lpString1
0x180086bb7  lea     edx, [rdi-2]; dwCmpFlags
0x180086bba  mov     ecx, 400h; Locale
0x180086bbf  call    cs:__imp_CompareStringW
0x180086bc5  cmp     eax, 2
0x180086bc8  jnz     short loc_180086BCE
0x180086bca  mov     bl, 1
0x180086bcc  jmp     short loc_180086BD0
0x180086bce  xor     bl, bl
0x180086bd0  test    dil, 2
0x180086bd4  jz      short loc_180086BE4
0x180086bd6  and     edi, 0FFFFFFFDh
0x180086bd9  lea     rcx, [rsp+98h+var_60]
0x180086bde  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086be3  nop
0x180086be4  test    dil, 1
0x180086be8  jz      short loc_180086BF4
0x180086bea  lea     rcx, [rsp+98h+var_40]
0x180086bef  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086bf4  mov     al, bl
0x180086bf6  mov     rcx, [rsp+98h+var_20]
0x180086bfb  xor     rcx, rsp; StackCookie
0x180086bfe  call    __security_check_cookie
0x180086c03  mov     rbx, [rsp+98h+arg_10]
0x180086c0b  add     rsp, 80h
0x180086c12  pop     r14
0x180086c14  pop     rdi
0x180086c15  pop     rsi
0x180086c16  retn
```
