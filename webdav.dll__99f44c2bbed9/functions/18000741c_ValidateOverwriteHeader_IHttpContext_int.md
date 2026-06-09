# ValidateOverwriteHeader(IHttpContext *,int *)

- ea: `0x18000741c`
- end: `0x180007525`
- name: `?ValidateOverwriteHeader@@YAJPEAVIHttpContext@@PEAH@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IHttpContext *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002740`

## callees

- `0x18000741c`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800074ab`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800074ab`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800074f2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800074f2`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800074c2`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800074c2`

## string_xrefs

- `0x180007455`: `Overwrite`
- `0x1800074d2`: `Overwrite: Header Invalid`

## pseudocode

```c
__int64 __fastcall ValidateOverwriteHeader(struct IHttpContext *a1, int *a2)
{
  unsigned int v4; // r14d
  __int64 v5; // rax
  const char *v6; // rax
  const char *v7; // rbp
  __int64 v8; // rsi
  __int64 v9; // rbx
  void (__fastcall *v10)(__int64, const wchar_t *, __int64, __int64, char); // rdi
  char v12; // [rsp+20h] [rbp-68h]
  _BYTE v13[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v14; // [rsp+50h] [rbp-38h]

  v4 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v6 = (const char *)(*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v5 + 24LL))(
                       v5,
                       "Overwrite",
                       0);
  v7 = v6;
  if ( v6 && *v6 && *v6 != 84 )
  {
    if ( *v6 == 70 )
    {
      *a2 = 0;
    }
    else
    {
      v4 = -2147024809;
      v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      STRU::STRU((STRU *)v13);
      v9 = 0;
      v10 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, __int64, char))(*(_QWORD *)v8 + 32LL);
      v12 = 3;
      if ( (int)STRU::CopyA((STRU *)v13, v7) >= 0 )
        v9 = v14;
      v10(v8, L"Overwrite: Header Invalid", v9, 2147942487LL, v12);
      STRU::~STRU((STRU *)v13);
    }
  }
  else
  {
    *a2 = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x18000741c  mov     [rsp+arg_10], rbx
0x180007421  mov     [rsp+arg_18], rbp
0x180007426  push    rsi
0x180007427  push    rdi
0x180007428  push    r14
0x18000742a  sub     rsp, 70h
0x18000742e  mov     rax, cs:__security_cookie
0x180007435  xor     rax, rsp
0x180007438  mov     [rsp+88h+var_20], rax
0x18000743d  mov     rax, [rcx]
0x180007440  mov     rbx, rdx
0x180007443  mov     rdi, rcx
0x180007446  xor     r14d, r14d
0x180007449  mov     rax, [rax+18h]
0x18000744d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007452  mov     rcx, rax
0x180007455  lea     rdx, aOverwrite; "Overwrite"
0x18000745c  xor     r8d, r8d
0x18000745f  mov     rax, [rax]
0x180007462  mov     rax, [rax+18h]
0x180007466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000746b  mov     rbp, rax
0x18000746e  test    rax, rax
0x180007471  jz      loc_1800074FA
0x180007477  cmp     [rax], r14b
0x18000747a  jz      short loc_1800074FA
0x18000747c  cmp     byte ptr [rax], 54h ; 'T'
0x18000747f  jz      short loc_1800074FA
0x180007481  cmp     byte ptr [rax], 46h ; 'F'
0x180007484  jnz     short loc_18000748B
0x180007486  mov     [rbx], r14d
0x180007489  jmp     short loc_180007500
0x18000748b  mov     rax, [rdi]
0x18000748e  mov     rcx, rdi
0x180007491  mov     r14d, 80070057h
0x180007497  mov     rax, [rax+110h]
0x18000749e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074a3  lea     rcx, [rsp+88h+var_58]
0x1800074a8  mov     rsi, rax
0x1800074ab  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800074b1  mov     rax, [rsi]
0x1800074b4  lea     rcx, [rsp+88h+var_58]
0x1800074b9  mov     rdx, rbp
0x1800074bc  xor     ebx, ebx
0x1800074be  mov     rdi, [rax+20h]
0x1800074c2  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x1800074c8  mov     r9d, r14d
0x1800074cb  mov     [rsp+88h+var_68], 3
0x1800074d0  test    eax, eax
0x1800074d2  lea     rdx, aOverwriteHeade; "Overwrite: Header Invalid"
0x1800074d9  mov     rcx, rsi
0x1800074dc  mov     rax, rdi
0x1800074df  cmovns  rbx, [rsp+88h+var_38]
0x1800074e5  mov     r8, rbx
0x1800074e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ed  lea     rcx, [rsp+88h+var_58]
0x1800074f2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800074f8  jmp     short loc_180007500
0x1800074fa  mov     dword ptr [rbx], 1
0x180007500  mov     eax, r14d
0x180007503  mov     rcx, [rsp+88h+var_20]
0x180007508  xor     rcx, rsp; StackCookie
0x18000750b  call    __security_check_cookie
0x180007510  lea     r11, [rsp+88h+var_18]
0x180007515  mov     rbx, [r11+30h]
0x180007519  mov     rbp, [r11+38h]
0x18000751d  mov     rsp, r11
0x180007520  pop     r14
0x180007522  pop     rdi
0x180007523  pop     rsi
0x180007524  retn
```
