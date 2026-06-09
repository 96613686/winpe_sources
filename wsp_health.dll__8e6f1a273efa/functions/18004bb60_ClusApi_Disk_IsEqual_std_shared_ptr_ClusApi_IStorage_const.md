# ClusApi::Disk::IsEqual(std::shared_ptr<ClusApi::IStorage> const &)

- ea: `0x18004bb60`
- end: `0x18004bc6e`
- name: `?IsEqual@Disk@ClusApi@@UEAA_NAEBV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004bc80`

## callees

- `0x180002b50`
- `0x18000da34`
- `0x18000daf8`
- `0x18004bb60`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004bc0f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004bc0f`

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
0x18004bb60  mov     [rsp+arg_10], rbx
0x18004bb65  push    rsi
0x18004bb66  push    rdi
0x18004bb67  push    r14
0x18004bb69  sub     rsp, 80h
0x18004bb70  mov     rax, cs:__security_cookie
0x18004bb77  xor     rax, rsp
0x18004bb7a  mov     [rsp+98h+var_20], rax
0x18004bb7f  mov     r14, rdx
0x18004bb82  mov     rsi, rcx
0x18004bb85  xor     edi, edi
0x18004bb87  mov     [rsp+98h+var_68], edi
0x18004bb8b  mov     rcx, [rdx]
0x18004bb8e  mov     rax, [rcx]
0x18004bb91  mov     rax, [rax]
0x18004bb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb99  mov     ebx, eax
0x18004bb9b  mov     rcx, [rsi]
0x18004bb9e  mov     rax, [rcx]
0x18004bba1  mov     rcx, rsi
0x18004bba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bba9  cmp     eax, ebx
0x18004bbab  jnz     short loc_18004BC24
0x18004bbad  mov     rax, [rsi]
0x18004bbb0  lea     rdx, [rsp+98h+var_40]
0x18004bbb5  mov     rcx, rsi
0x18004bbb8  mov     rax, [rax+8]
0x18004bbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbc1  nop
0x18004bbc2  mov     [rsp+98h+var_68], 1
0x18004bbca  mov     rcx, rax
0x18004bbcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004bbd2  mov     rbx, rax
0x18004bbd5  mov     rcx, [r14]
0x18004bbd8  mov     rdx, [rcx]
0x18004bbdb  mov     rax, [rdx+8]
0x18004bbdf  lea     rdx, [rsp+98h+var_60]
0x18004bbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbe9  mov     edi, 3
0x18004bbee  mov     rcx, rax
0x18004bbf1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004bbf6  or      r9d, 0FFFFFFFFh; cchCount1
0x18004bbfa  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x18004bbff  mov     [rsp+98h+lpString2], rbx; lpString2
0x18004bc04  mov     r8, rax; lpString1
0x18004bc07  lea     edx, [rdi-2]; dwCmpFlags
0x18004bc0a  mov     ecx, 400h; Locale
0x18004bc0f  call    cs:__imp_CompareStringW
0x18004bc16  nop     dword ptr [rax+rax+00h]
0x18004bc1b  cmp     eax, 2
0x18004bc1e  jnz     short loc_18004BC24
0x18004bc20  mov     bl, 1
0x18004bc22  jmp     short loc_18004BC26
0x18004bc24  xor     bl, bl
0x18004bc26  test    dil, 2
0x18004bc2a  jz      short loc_18004BC3A
0x18004bc2c  and     edi, 0FFFFFFFDh
0x18004bc2f  lea     rcx, [rsp+98h+var_60]
0x18004bc34  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bc39  nop
0x18004bc3a  test    dil, 1
0x18004bc3e  jz      short loc_18004BC4A
0x18004bc40  lea     rcx, [rsp+98h+var_40]
0x18004bc45  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bc4a  mov     al, bl
0x18004bc4c  mov     rcx, [rsp+98h+var_20]
0x18004bc51  xor     rcx, rsp; StackCookie
0x18004bc54  call    __security_check_cookie
0x18004bc59  mov     rbx, [rsp+98h+arg_10]
0x18004bc61  add     rsp, 80h
0x18004bc68  pop     r14
0x18004bc6a  pop     rdi
0x18004bc6b  pop     rsi
0x18004bc6c  retn
```
