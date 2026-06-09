# WdsIdnToAscii

- ea: `0x180012cd4`
- end: `0x180012e65`
- name: `WdsIdnToAscii`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180012e6c`

## callees

- `0x180012cd4`
- `0x180014d58`
- `0x180014ee0`
- `0x1800150b8`
- `0x1800157a4`
- `0x180015c9d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012d85`
- `KERNEL32!GetLastError` at `0x180012e0e`
- `KERNEL32!GetLastError` at `0x180012d85`
- `KERNEL32!GetLastError` at `0x180012e0e`
- `Normaliz!IdnToAscii` at `0x180012d78`
- `Normaliz!IdnToAscii` at `0x180012e04`
- `Normaliz!IdnToAscii` at `0x180012d78`
- `Normaliz!IdnToAscii` at `0x180012e04`

## string_xrefs

- `0x180012d1a`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x180012d91`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x180012e1a`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`

## pseudocode

```c
__int64 __fastcall WdsIdnToAscii(__int64 a1, const WCHAR *a2, WCHAR **a3)
{
  __int64 v5; // rax
  unsigned int v6; // ebx
  unsigned __int64 v7; // rbp
  int v8; // r14d
  int v9; // edi
  int v10; // eax
  unsigned __int64 cchASCIIChar; // rbp
  DWORD v12; // eax
  const char *v13; // rdx
  unsigned __int64 v14; // rax
  WCHAR *v15; // rax
  WCHAR *v16; // rdi
  DWORD LastError; // eax
  const char *v18; // rdx

  v5 = -1;
  v6 = 0;
  do
    ++v5;
  while ( a2[v5] );
  v7 = v5 + 1;
  v8 = -1;
  if ( (unsigned __int64)(v5 + 1) <= 0x7FFFFFFF )
    v8 = v5 + 1;
  v9 = v7 > 0x7FFFFFFF ? 0x80070216 : 0;
  if ( (int)ElValidateHr(v9, (const char *)a2, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0x40u) >= 0 )
  {
    v10 = IdnToAscii(1u, a2, v8, 0, 0);
    cchASCIIChar = v10;
    if ( v10 )
    {
      v14 = 2LL * v10;
      if ( !is_mul_ok(cchASCIIChar, 2u) )
        v14 = -1;
      v15 = (WCHAR *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
      v16 = v15;
      if ( v15 )
      {
        memset_0(v15, 0, 2 * cchASCIIChar);
        if ( IdnToAscii(1u, a2, v8, v16, cchASCIIChar) )
        {
          *a3 = v16;
          v16 = 0;
        }
        else
        {
          LastError = GetLastError();
          v6 = ElValidateWin32(LastError, v18, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0x5Au);
          if ( !v6 )
            v6 = 31;
        }
        if ( v16 )
          operator delete(v16);
      }
      else
      {
        return 8;
      }
    }
    else
    {
      v12 = GetLastError();
      v6 = ElValidateWin32(v12, v13, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0x4Au);
      if ( !v6 )
        return 31;
    }
  }
  else if ( v7 > 0x7FFFFFFF && (v7 > 0x7FFFFFFF ? 0x70000 : 0) == 0x70000 )
  {
    return (unsigned __int16)v9;
  }
  else
  {
    return v7 > 0x7FFFFFFF ? 0x80070216 : 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180012cd4  mov     [rsp+arg_0], rbx
0x180012cd9  mov     [rsp+arg_8], rbp
0x180012cde  mov     [rsp+arg_10], rsi
0x180012ce3  push    rdi
0x180012ce4  push    r12
0x180012ce6  push    r13
0x180012ce8  push    r14
0x180012cea  push    r15
0x180012cec  sub     rsp, 30h
0x180012cf0  xor     r13d, r13d
0x180012cf3  mov     r15, r8
0x180012cf6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180012cfa  mov     rsi, rdx
0x180012cfd  mov     rax, rcx
0x180012d00  mov     ebx, r13d
0x180012d03  inc     rax
0x180012d06  cmp     [rdx+rax*2], r13w
0x180012d0b  jnz     short loc_180012D03
0x180012d0d  lea     rbp, [rax+1]
0x180012d11  mov     r14d, ecx
0x180012d14  mov     r12d, 7FFFFFFFh
0x180012d1a  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180012d21  cmp     rbp, r12
0x180012d24  mov     r9d, 40h ; '@'; unsigned int
0x180012d2a  cmovbe  r14d, ebp
0x180012d2e  cmp     r12, rbp
0x180012d31  sbb     edi, edi
0x180012d33  and     edi, 80070216h
0x180012d39  mov     ecx, edi; int
0x180012d3b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180012d40  test    eax, eax
0x180012d42  jns     short loc_180012D66
0x180012d44  cmp     rbp, r12
0x180012d47  jbe     short loc_180012D5F
0x180012d49  mov     eax, edi
0x180012d4b  and     eax, 1FFF0000h
0x180012d50  cmp     eax, 70000h
0x180012d55  jnz     short loc_180012D5F
0x180012d57  movzx   ebx, di
0x180012d5a  jmp     loc_180012E46
0x180012d5f  mov     ebx, edi
0x180012d61  jmp     loc_180012E46
0x180012d66  xor     r9d, r9d; lpASCIICharStr
0x180012d69  mov     [rsp+58h+cchASCIIChar], r13d; cchASCIIChar
0x180012d6e  mov     r8d, r14d; cchUnicodeChar
0x180012d71  mov     rdx, rsi; lpUnicodeCharStr
0x180012d74  lea     ecx, [r9+1]; dwFlags
0x180012d78  call    cs:__imp_IdnToAscii
0x180012d7e  movsxd  rbp, eax
0x180012d81  test    eax, eax
0x180012d83  jnz     short loc_180012DB1
0x180012d85  call    cs:__imp_GetLastError
0x180012d8b  mov     r9d, 4Ah ; 'J'; unsigned int
0x180012d91  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180012d98  mov     ecx, eax; unsigned int
0x180012d9a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012d9f  mov     ebx, eax
0x180012da1  test    eax, eax
0x180012da3  jnz     loc_180012E46
0x180012da9  lea     ebx, [rax+1Fh]
0x180012dac  jmp     loc_180012E46
0x180012db1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012db8  mov     eax, 2
0x180012dbd  mul     rbp
0x180012dc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012dc7  cmovo   rax, rcx
0x180012dcb  mov     rcx, rax; unsigned __int64
0x180012dce  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012dd3  mov     rdi, rax
0x180012dd6  test    rax, rax
0x180012dd9  jnz     short loc_180012DE0
0x180012ddb  lea     ebx, [rax+8]
0x180012dde  jmp     short loc_180012E46
0x180012de0  lea     r8, ds:0[rbp*2]; Size
0x180012de8  xor     edx, edx; Val
0x180012dea  mov     rcx, rdi; void *
0x180012ded  call    memset_0
0x180012df2  mov     r9, rdi; lpASCIICharStr
0x180012df5  mov     [rsp+58h+cchASCIIChar], ebp; cchASCIIChar
0x180012df9  mov     r8d, r14d; cchUnicodeChar
0x180012dfc  mov     rdx, rsi; lpUnicodeCharStr
0x180012dff  mov     ecx, 1; dwFlags
0x180012e04  call    cs:__imp_IdnToAscii
0x180012e0a  test    eax, eax
0x180012e0c  jnz     short loc_180012E33
0x180012e0e  call    cs:__imp_GetLastError
0x180012e14  mov     r9d, 5Ah ; 'Z'; unsigned int
0x180012e1a  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180012e21  mov     ecx, eax; unsigned int
0x180012e23  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012e28  mov     ebx, eax
0x180012e2a  test    eax, eax
0x180012e2c  jnz     short loc_180012E39
0x180012e2e  lea     ebx, [rax+1Fh]
0x180012e31  jmp     short loc_180012E39
0x180012e33  mov     [r15], rdi
0x180012e36  mov     rdi, r13
0x180012e39  test    rdi, rdi
0x180012e3c  jz      short loc_180012E46
0x180012e3e  mov     rcx, rdi; Block
0x180012e41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012e46  mov     rbp, [rsp+58h+arg_8]
0x180012e4b  mov     eax, ebx
0x180012e4d  mov     rbx, [rsp+58h+arg_0]
0x180012e52  mov     rsi, [rsp+58h+arg_10]
0x180012e57  add     rsp, 30h
0x180012e5b  pop     r15
0x180012e5d  pop     r14
0x180012e5f  pop     r13
0x180012e61  pop     r12
0x180012e63  pop     rdi
0x180012e64  retn
```
