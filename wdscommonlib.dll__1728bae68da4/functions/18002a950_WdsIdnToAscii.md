# WdsIdnToAscii

- ea: `0x18002a950`
- end: `0x18002ab77`
- name: `WdsIdnToAscii`
- size: `551`
- prototype: `__int64 __fastcall(DWORD dwFlags, LPCWSTR lpUnicodeCharStr)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001d730`
- `0x18002a790`
- `0x18002a870`

## callees

- `0x18000214c`
- `0x180006ea4`
- `0x18002a6b4`
- `0x18002a950`
- `0x180030362`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002aa6b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002aa6b`
- `KERNEL32!SetLastError` at `0x18002ab1b`
- `KERNEL32!SetLastError` at `0x18002ab45`
- `KERNEL32!SetLastError` at `0x18002ab1b`
- `KERNEL32!SetLastError` at `0x18002ab45`
- `KERNEL32!GetLastError` at `0x18002a9b3`
- `KERNEL32!GetLastError` at `0x18002aa43`
- `KERNEL32!GetLastError` at `0x18002aa92`
- `KERNEL32!GetLastError` at `0x18002aae0`
- `KERNEL32!GetLastError` at `0x18002ab27`
- `KERNEL32!GetLastError` at `0x18002a9b3`
- `KERNEL32!GetLastError` at `0x18002aa43`
- `KERNEL32!GetLastError` at `0x18002aa92`
- `KERNEL32!GetLastError` at `0x18002aae0`
- `KERNEL32!GetLastError` at `0x18002ab27`
- `Normaliz!IdnToAscii` at `0x18002a9a0`
- `Normaliz!IdnToAscii` at `0x18002aa33`
- `Normaliz!IdnToAscii` at `0x18002a9a0`
- `Normaliz!IdnToAscii` at `0x18002aa33`

## string_xrefs

- `0x18002aaae`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x18002aaf9`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`

## pseudocode

```c
__int64 __fastcall WdsIdnToAscii(DWORD dwFlags, LPCWSTR lpUnicodeCharStr, _QWORD *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  unsigned __int64 v8; // rdi
  int v9; // eax
  unsigned __int64 cchASCIIChar; // r14
  DWORD v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // rax
  void *v15; // rax
  void *v16; // rsi
  DWORD LastError; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  DWORD v21; // ebx
  DWORD v22; // ebx

  v4 = 0;
  v5 = -1;
  do
    ++v5;
  while ( lpUnicodeCharStr[v5] );
  v8 = v5 + 1;
  if ( v8 <= 0x7FFFFFFF )
  {
    v9 = IdnToAscii(dwFlags, lpUnicodeCharStr, v8, 0, 0);
    cchASCIIChar = v9;
    if ( v9 )
    {
      v14 = 2LL * v9;
      if ( !is_mul_ok(cchASCIIChar, 2u) )
        v14 = -1;
      v15 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
      v16 = v15;
      if ( v15 )
      {
        memset_0(v15, 0, 2 * cchASCIIChar);
        if ( IdnToAscii(dwFlags, lpUnicodeCharStr, v8, (LPWSTR)v16, cchASCIIChar) )
        {
          *a3 = v16;
        }
        else
        {
          LastError = GetLastError();
          v20 = ElValidateWin32_21(LastError, v18, v19, 90);
          if ( !v20 )
            v20 = 31;
          v4 = v20;
          operator delete(v16);
        }
      }
      else
      {
        return 8;
      }
    }
    else
    {
      v11 = GetLastError();
      v4 = ElValidateWin32_21(v11, v12, v13, 74);
      if ( !v4 )
        return 31;
    }
    return v4;
  }
  if ( g_ErrLibTraceFunctionEx )
  {
    v21 = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp",
      64,
      &dword_18003572C,
      -2147024362);
LABEL_20:
    SetLastError(v21);
    goto LABEL_21;
  }
  if ( g_ErrLibTraceFunction )
  {
    v21 = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp",
      64,
      &dword_18003572C,
      -2147024362);
    goto LABEL_20;
  }
LABEL_21:
  v22 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v22);
  return 534;
}

```

## disassembly

```asm
0x18002a950  mov     [rsp+arg_0], rbx
0x18002a955  mov     [rsp+arg_8], rbp
0x18002a95a  mov     [rsp+arg_10], rsi
0x18002a95f  push    rdi
0x18002a960  push    r12
0x18002a962  push    r13
0x18002a964  push    r14
0x18002a966  push    r15
0x18002a968  sub     rsp, 40h
0x18002a96c  xor     esi, esi
0x18002a96e  mov     r15, r8
0x18002a971  mov     ebx, esi
0x18002a973  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002a977  mov     rbp, rdx
0x18002a97a  mov     r12d, ecx
0x18002a97d  inc     rdi
0x18002a980  cmp     [rdx+rdi*2], si
0x18002a984  jnz     short loc_18002A97D
0x18002a986  inc     rdi
0x18002a989  cmp     rdi, 7FFFFFFFh
0x18002a990  ja      loc_18002AA84
0x18002a996  xor     r9d, r9d; lpASCIICharStr
0x18002a999  mov     [rsp+68h+cchASCIIChar], esi; cchASCIIChar
0x18002a99d  mov     r8d, edi; cchUnicodeChar
0x18002a9a0  call    cs:__imp_IdnToAscii
0x18002a9a7  nop     dword ptr [rax+rax+00h]
0x18002a9ac  movsxd  r14, eax
0x18002a9af  test    eax, eax
0x18002a9b1  jnz     short loc_18002A9DE
0x18002a9b3  call    cs:__imp_GetLastError
0x18002a9ba  nop     dword ptr [rax+rax+00h]
0x18002a9bf  mov     ecx, eax
0x18002a9c1  mov     r9d, 4Ah ; 'J'
0x18002a9c7  call    ElValidateWin32_21
0x18002a9cc  mov     ebx, eax
0x18002a9ce  test    eax, eax
0x18002a9d0  jnz     loc_18002AB56
0x18002a9d6  lea     ebx, [rax+1Fh]
0x18002a9d9  jmp     loc_18002AB56
0x18002a9de  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a9e5  mov     eax, 2
0x18002a9ea  mul     r14
0x18002a9ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002a9f4  cmovo   rax, rcx
0x18002a9f8  mov     rcx, rax; unsigned __int64
0x18002a9fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002aa00  mov     rsi, rax
0x18002aa03  test    rax, rax
0x18002aa06  jnz     short loc_18002AA10
0x18002aa08  lea     ebx, [rax+8]
0x18002aa0b  jmp     loc_18002AB56
0x18002aa10  lea     r8, ds:0[r14*2]; Size
0x18002aa18  xor     edx, edx; Val
0x18002aa1a  mov     rcx, rsi; void *
0x18002aa1d  call    memset_0
0x18002aa22  mov     r9, rsi; lpASCIICharStr
0x18002aa25  mov     [rsp+68h+cchASCIIChar], r14d; cchASCIIChar
0x18002aa2a  mov     r8d, edi; cchUnicodeChar
0x18002aa2d  mov     rdx, rbp; lpUnicodeCharStr
0x18002aa30  mov     ecx, r12d; dwFlags
0x18002aa33  call    cs:__imp_IdnToAscii
0x18002aa3a  nop     dword ptr [rax+rax+00h]
0x18002aa3f  test    eax, eax
0x18002aa41  jnz     short loc_18002AA7C
0x18002aa43  call    cs:__imp_GetLastError
0x18002aa4a  nop     dword ptr [rax+rax+00h]
0x18002aa4f  mov     ecx, eax
0x18002aa51  mov     r9d, 5Ah ; 'Z'
0x18002aa57  call    ElValidateWin32_21
0x18002aa5c  test    eax, eax
0x18002aa5e  mov     ebx, 1Fh
0x18002aa63  mov     rcx, rsi
0x18002aa66  cmovz   eax, ebx
0x18002aa69  mov     ebx, eax
0x18002aa6b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002aa72  nop     dword ptr [rax+rax+00h]
0x18002aa77  jmp     loc_18002AB56
0x18002aa7c  mov     [r15], rsi
0x18002aa7f  jmp     loc_18002AB56
0x18002aa84  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rsi; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002aa8b  mov     edi, 80070216h
0x18002aa90  jz      short loc_18002AAD7
0x18002aa92  call    cs:__imp_GetLastError
0x18002aa99  nop     dword ptr [rax+rax+00h]
0x18002aa9e  lea     r9, dword_18003572C
0x18002aaa5  mov     [rsp+68h+var_40], edi
0x18002aaa9  mov     qword ptr [rsp+68h+cchASCIIChar], r9
0x18002aaae  lea     r8, aOnecoreBaseEco_33; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002aab5  mov     ebx, eax
0x18002aab7  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002aabe  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002aac5  mov     r9d, 40h ; '@'
0x18002aacb  mov     ecx, 80000h
0x18002aad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aad5  jmp     short loc_18002AB19
0x18002aad7  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rsi; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002aade  jz      short loc_18002AB27
0x18002aae0  call    cs:__imp_GetLastError
0x18002aae7  nop     dword ptr [rax+rax+00h]
0x18002aaec  lea     r9, dword_18003572C
0x18002aaf3  mov     [rsp+68h+cchASCIIChar], edi
0x18002aaf7  mov     ebx, eax
0x18002aaf9  lea     rdx, aOnecoreBaseEco_33; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002ab00  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002ab07  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002ab0e  mov     r8d, 40h ; '@'
0x18002ab14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab19  mov     ecx, ebx; dwErrCode
0x18002ab1b  call    cs:__imp_SetLastError
0x18002ab22  nop     dword ptr [rax+rax+00h]
0x18002ab27  call    cs:__imp_GetLastError
0x18002ab2e  nop     dword ptr [rax+rax+00h]
0x18002ab33  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18002ab3a  mov     ebx, eax
0x18002ab3c  jz      short loc_18002AB43
0x18002ab3e  call    ElTraceErrorInfo
0x18002ab43  mov     ecx, ebx; dwErrCode
0x18002ab45  call    cs:__imp_SetLastError
0x18002ab4c  nop     dword ptr [rax+rax+00h]
0x18002ab51  mov     ebx, 216h
0x18002ab56  lea     r11, [rsp+68h+var_28]
0x18002ab5b  mov     eax, ebx
0x18002ab5d  mov     rbx, [r11+30h]
0x18002ab61  mov     rbp, [r11+38h]
0x18002ab65  mov     rsi, [r11+40h]
0x18002ab69  mov     rsp, r11
0x18002ab6c  pop     r15
0x18002ab6e  pop     r14
0x18002ab70  pop     r13
0x18002ab72  pop     r12
0x18002ab74  pop     rdi
0x18002ab75  retn
```
