# ClusApi::Disk::IsEqual(std::shared_ptr<ClusApi::IStorage> const &)

- ea: `0x18004a220`
- end: `0x18004a327`
- name: `?IsEqual@Disk@ClusApi@@UEAA_NAEBV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004a330`

## callees

- `0x180002ae0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18004a220`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a2cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a2cf`

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
0x18004a220  mov     [rsp+arg_10], rbx
0x18004a225  push    rsi
0x18004a226  push    rdi
0x18004a227  push    r14
0x18004a229  sub     rsp, 80h
0x18004a230  mov     rax, cs:__security_cookie
0x18004a237  xor     rax, rsp
0x18004a23a  mov     [rsp+98h+var_20], rax
0x18004a23f  mov     r14, rdx
0x18004a242  mov     rsi, rcx
0x18004a245  xor     edi, edi
0x18004a247  mov     [rsp+98h+var_68], edi
0x18004a24b  mov     rcx, [rdx]
0x18004a24e  mov     rax, [rcx]
0x18004a251  mov     rax, [rax]
0x18004a254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a259  mov     ebx, eax
0x18004a25b  mov     rcx, [rsi]
0x18004a25e  mov     rax, [rcx]
0x18004a261  mov     rcx, rsi
0x18004a264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a269  cmp     eax, ebx
0x18004a26b  jnz     short loc_18004A2DE
0x18004a26d  mov     rax, [rsi]
0x18004a270  lea     rdx, [rsp+98h+var_40]
0x18004a275  mov     rcx, rsi
0x18004a278  mov     rax, [rax+8]
0x18004a27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a281  nop
0x18004a282  mov     [rsp+98h+var_68], 1
0x18004a28a  mov     rcx, rax
0x18004a28d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004a292  mov     rbx, rax
0x18004a295  mov     rcx, [r14]
0x18004a298  mov     rdx, [rcx]
0x18004a29b  mov     rax, [rdx+8]
0x18004a29f  lea     rdx, [rsp+98h+var_60]
0x18004a2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2a9  mov     edi, 3
0x18004a2ae  mov     rcx, rax
0x18004a2b1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004a2b6  or      r9d, 0FFFFFFFFh; cchCount1
0x18004a2ba  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x18004a2bf  mov     [rsp+98h+lpString2], rbx; lpString2
0x18004a2c4  mov     r8, rax; lpString1
0x18004a2c7  lea     edx, [rdi-2]; dwCmpFlags
0x18004a2ca  mov     ecx, 400h; Locale
0x18004a2cf  call    cs:__imp_CompareStringW
0x18004a2d5  cmp     eax, 2
0x18004a2d8  jnz     short loc_18004A2DE
0x18004a2da  mov     bl, 1
0x18004a2dc  jmp     short loc_18004A2E0
0x18004a2de  xor     bl, bl
0x18004a2e0  test    dil, 2
0x18004a2e4  jz      short loc_18004A2F4
0x18004a2e6  and     edi, 0FFFFFFFDh
0x18004a2e9  lea     rcx, [rsp+98h+var_60]
0x18004a2ee  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a2f3  nop
0x18004a2f4  test    dil, 1
0x18004a2f8  jz      short loc_18004A304
0x18004a2fa  lea     rcx, [rsp+98h+var_40]
0x18004a2ff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a304  mov     al, bl
0x18004a306  mov     rcx, [rsp+98h+var_20]
0x18004a30b  xor     rcx, rsp; StackCookie
0x18004a30e  call    __security_check_cookie
0x18004a313  mov     rbx, [rsp+98h+arg_10]
0x18004a31b  add     rsp, 80h
0x18004a322  pop     r14
0x18004a324  pop     rdi
0x18004a325  pop     rsi
0x18004a326  retn
```
