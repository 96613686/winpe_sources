# WdsIdnToAscii

- ea: `0x180025450`
- end: `0x1800255ee`
- name: `WdsIdnToAscii`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b290`

## callees

- `0x18001a9a8`
- `0x180025450`
- `0x180025850`
- `0x180025914`
- `0x1800259d8`
- `0x180026694`
- `0x180026d46`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025511`
- `KERNEL32!GetLastError` at `0x180025596`
- `KERNEL32!GetLastError` at `0x180025511`
- `KERNEL32!GetLastError` at `0x180025596`
- `Normaliz!IdnToAscii` at `0x180025504`
- `Normaliz!IdnToAscii` at `0x18002558c`
- `Normaliz!IdnToAscii` at `0x180025504`
- `Normaliz!IdnToAscii` at `0x18002558c`

## string_xrefs

- `0x180025496`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x18002551d`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x1800255a2`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`

## pseudocode

```c
__int64 __fastcall WdsIdnToAscii(__int64 a1, const char *a2, WCHAR **a3)
{
  __int64 v5; // rax
  unsigned int v6; // ebx
  unsigned __int64 v7; // rsi
  int v8; // r14d
  int v9; // edi
  const char *v10; // rdx
  const char *v11; // r8
  unsigned int v12; // r9d
  signed int v13; // eax
  int v14; // eax
  unsigned __int64 cchASCIIChar; // rsi
  DWORD v16; // eax
  const char *v17; // rdx
  unsigned __int64 v18; // rax
  WCHAR *v19; // rax
  WCHAR *v20; // rdi
  DWORD LastError; // eax
  const char *v22; // rdx

  v5 = -1;
  v6 = 0;
  do
    ++v5;
  while ( *(_WORD *)&a2[2 * v5] );
  v7 = v5 + 1;
  v8 = -1;
  if ( (unsigned __int64)(v5 + 1) <= 0x7FFFFFFF )
    v8 = v5 + 1;
  v9 = v7 > 0x7FFFFFFF ? 0x80070216 : 0;
  ElValidateHrLite(v9, a2, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0x40u);
  if ( v7 <= 0x7FFFFFFF )
    v13 = v7 > 0x7FFFFFFF ? 0x80070216 : 0;
  else
    v13 = ElValidateHr(v9, v10, v11, v12);
  if ( v13 >= 0 )
  {
    v14 = IdnToAscii(1u, (LPCWSTR)a2, v8, 0, 0);
    cchASCIIChar = v14;
    if ( v14 )
    {
      v18 = 2LL * v14;
      if ( !is_mul_ok(cchASCIIChar, 2u) )
        v18 = -1;
      v19 = (WCHAR *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
      v20 = v19;
      if ( v19 )
      {
        memset_0(v19, 0, 2 * cchASCIIChar);
        if ( IdnToAscii(1u, (LPCWSTR)a2, v8, v20, cchASCIIChar) )
        {
          *a3 = v20;
          v20 = 0;
        }
        else
        {
          LastError = GetLastError();
          v6 = ElValidateWin32(LastError, v22, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0x5Au);
          if ( !v6 )
            v6 = 31;
        }
        if ( v20 )
          operator delete(v20);
      }
      else
      {
        return 8;
      }
    }
    else
    {
      v16 = GetLastError();
      v6 = ElValidateWin32(v16, v17, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0x4Au);
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
0x180025450  mov     [rsp+arg_0], rbx
0x180025455  mov     [rsp+arg_8], rbp
0x18002545a  mov     [rsp+arg_10], rsi
0x18002545f  push    rdi
0x180025460  push    r12
0x180025462  push    r13
0x180025464  push    r14
0x180025466  push    r15
0x180025468  sub     rsp, 30h
0x18002546c  xor     r13d, r13d
0x18002546f  mov     r12, r8
0x180025472  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180025476  mov     rbp, rdx
0x180025479  mov     rax, rcx
0x18002547c  mov     ebx, r13d
0x18002547f  inc     rax
0x180025482  cmp     [rdx+rax*2], r13w
0x180025487  jnz     short loc_18002547F
0x180025489  lea     rsi, [rax+1]
0x18002548d  mov     r14d, ecx
0x180025490  mov     r15d, 7FFFFFFFh
0x180025496  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002549d  cmp     rsi, r15
0x1800254a0  mov     r9d, 40h ; '@'; unsigned int
0x1800254a6  cmovbe  r14d, esi
0x1800254aa  cmp     r15, rsi
0x1800254ad  sbb     edi, edi
0x1800254af  and     edi, 80070216h
0x1800254b5  mov     ecx, edi; int
0x1800254b7  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x1800254bc  cmp     rsi, r15
0x1800254bf  jbe     short loc_1800254CA
0x1800254c1  mov     ecx, edi; int
0x1800254c3  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800254c8  jmp     short loc_1800254CC
0x1800254ca  mov     eax, edi
0x1800254cc  test    eax, eax
0x1800254ce  jns     short loc_1800254F2
0x1800254d0  cmp     rsi, r15
0x1800254d3  jbe     short loc_1800254EB
0x1800254d5  mov     eax, edi
0x1800254d7  and     eax, 1FFF0000h
0x1800254dc  cmp     eax, 70000h
0x1800254e1  jnz     short loc_1800254EB
0x1800254e3  movzx   ebx, di
0x1800254e6  jmp     loc_1800255CF
0x1800254eb  mov     ebx, edi
0x1800254ed  jmp     loc_1800255CF
0x1800254f2  xor     r9d, r9d; lpASCIICharStr
0x1800254f5  mov     [rsp+58h+cchASCIIChar], r13d; cchASCIIChar
0x1800254fa  mov     r8d, r14d; cchUnicodeChar
0x1800254fd  mov     rdx, rbp; lpUnicodeCharStr
0x180025500  lea     ecx, [r9+1]; dwFlags
0x180025504  call    cs:__imp_IdnToAscii
0x18002550a  movsxd  rsi, eax
0x18002550d  test    eax, eax
0x18002550f  jnz     short loc_18002553D
0x180025511  call    cs:__imp_GetLastError
0x180025517  mov     r9d, 4Ah ; 'J'; unsigned int
0x18002551d  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180025524  mov     ecx, eax; unsigned int
0x180025526  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002552b  mov     ebx, eax
0x18002552d  test    eax, eax
0x18002552f  jnz     loc_1800255CF
0x180025535  lea     ebx, [rax+1Fh]
0x180025538  jmp     loc_1800255CF
0x18002553d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025544  mov     eax, 2
0x180025549  mul     rsi
0x18002554c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025553  cmovo   rax, rcx
0x180025557  mov     rcx, rax; unsigned __int64
0x18002555a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002555f  mov     rdi, rax
0x180025562  test    rax, rax
0x180025565  jnz     short loc_18002556C
0x180025567  lea     ebx, [rax+8]
0x18002556a  jmp     short loc_1800255CF
0x18002556c  lea     r8, [rsi+rsi]; Size
0x180025570  xor     edx, edx; Val
0x180025572  mov     rcx, rdi; void *
0x180025575  call    memset_0
0x18002557a  mov     r9, rdi; lpASCIICharStr
0x18002557d  mov     [rsp+58h+cchASCIIChar], esi; cchASCIIChar
0x180025581  mov     r8d, r14d; cchUnicodeChar
0x180025584  mov     rdx, rbp; lpUnicodeCharStr
0x180025587  mov     ecx, 1; dwFlags
0x18002558c  call    cs:__imp_IdnToAscii
0x180025592  test    eax, eax
0x180025594  jnz     short loc_1800255BB
0x180025596  call    cs:__imp_GetLastError
0x18002559c  mov     r9d, 5Ah ; 'Z'; unsigned int
0x1800255a2  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800255a9  mov     ecx, eax; unsigned int
0x1800255ab  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800255b0  mov     ebx, eax
0x1800255b2  test    eax, eax
0x1800255b4  jnz     short loc_1800255C2
0x1800255b6  lea     ebx, [rax+1Fh]
0x1800255b9  jmp     short loc_1800255C2
0x1800255bb  mov     [r12], rdi
0x1800255bf  mov     rdi, r13
0x1800255c2  test    rdi, rdi
0x1800255c5  jz      short loc_1800255CF
0x1800255c7  mov     rcx, rdi; void *
0x1800255ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800255cf  mov     rbp, [rsp+58h+arg_8]
0x1800255d4  mov     eax, ebx
0x1800255d6  mov     rbx, [rsp+58h+arg_0]
0x1800255db  mov     rsi, [rsp+58h+arg_10]
0x1800255e0  add     rsp, 30h
0x1800255e4  pop     r15
0x1800255e6  pop     r14
0x1800255e8  pop     r13
0x1800255ea  pop     r12
0x1800255ec  pop     rdi
0x1800255ed  retn
```
