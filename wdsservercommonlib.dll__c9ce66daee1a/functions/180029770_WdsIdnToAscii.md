# WdsIdnToAscii

- ea: `0x180029770`
- end: `0x180029990`
- name: `WdsIdnToAscii`
- size: `544`
- prototype: `__int64 __fastcall(DWORD dwFlags, LPCWSTR lpUnicodeCharStr)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001c810`
- `0x1800295d0`
- `0x1800296a0`

## callees

- `0x18000179c`
- `0x1800063c4`
- `0x1800294f4`
- `0x180029770`
- `0x18002e468`
- `0x18002f3ba`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180029934`
- `KERNEL32!SetLastError` at `0x18002995e`
- `KERNEL32!SetLastError` at `0x180029934`
- `KERNEL32!SetLastError` at `0x18002995e`
- `KERNEL32!GetLastError` at `0x1800297d3`
- `KERNEL32!GetLastError` at `0x180029863`
- `KERNEL32!GetLastError` at `0x1800298ab`
- `KERNEL32!GetLastError` at `0x1800298f9`
- `KERNEL32!GetLastError` at `0x180029940`
- `KERNEL32!GetLastError` at `0x1800297d3`
- `KERNEL32!GetLastError` at `0x180029863`
- `KERNEL32!GetLastError` at `0x1800298ab`
- `KERNEL32!GetLastError` at `0x1800298f9`
- `KERNEL32!GetLastError` at `0x180029940`
- `Normaliz!IdnToAscii` at `0x1800297c0`
- `Normaliz!IdnToAscii` at `0x180029853`
- `Normaliz!IdnToAscii` at `0x1800297c0`
- `Normaliz!IdnToAscii` at `0x180029853`

## string_xrefs

- `0x1800298c7`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x180029912`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`

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
      &dword_1800331C4,
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
      &dword_1800331C4,
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
0x180029770  mov     [rsp+arg_0], rbx
0x180029775  mov     [rsp+arg_8], rbp
0x18002977a  mov     [rsp+arg_10], rsi
0x18002977f  push    rdi
0x180029780  push    r12
0x180029782  push    r13
0x180029784  push    r14
0x180029786  push    r15
0x180029788  sub     rsp, 40h
0x18002978c  xor     esi, esi
0x18002978e  mov     r15, r8
0x180029791  mov     ebx, esi
0x180029793  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029797  mov     rbp, rdx
0x18002979a  mov     r12d, ecx
0x18002979d  inc     rdi
0x1800297a0  cmp     [rdx+rdi*2], si
0x1800297a4  jnz     short loc_18002979D
0x1800297a6  inc     rdi
0x1800297a9  cmp     rdi, 7FFFFFFFh
0x1800297b0  ja      loc_18002989D
0x1800297b6  xor     r9d, r9d; lpASCIICharStr
0x1800297b9  mov     [rsp+68h+cchASCIIChar], esi; cchASCIIChar
0x1800297bd  mov     r8d, edi; cchUnicodeChar
0x1800297c0  call    cs:__imp_IdnToAscii
0x1800297c7  nop     dword ptr [rax+rax+00h]
0x1800297cc  movsxd  r14, eax
0x1800297cf  test    eax, eax
0x1800297d1  jnz     short loc_1800297FE
0x1800297d3  call    cs:__imp_GetLastError
0x1800297da  nop     dword ptr [rax+rax+00h]
0x1800297df  mov     ecx, eax
0x1800297e1  mov     r9d, 4Ah ; 'J'
0x1800297e7  call    ElValidateWin32_21
0x1800297ec  mov     ebx, eax
0x1800297ee  test    eax, eax
0x1800297f0  jnz     loc_18002996F
0x1800297f6  lea     ebx, [rax+1Fh]
0x1800297f9  jmp     loc_18002996F
0x1800297fe  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180029805  mov     eax, 2
0x18002980a  mul     r14
0x18002980d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029814  cmovo   rax, rcx
0x180029818  mov     rcx, rax; unsigned __int64
0x18002981b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029820  mov     rsi, rax
0x180029823  test    rax, rax
0x180029826  jnz     short loc_180029830
0x180029828  lea     ebx, [rax+8]
0x18002982b  jmp     loc_18002996F
0x180029830  lea     r8, ds:0[r14*2]; Size
0x180029838  xor     edx, edx; Val
0x18002983a  mov     rcx, rsi; void *
0x18002983d  call    memset_0
0x180029842  mov     r9, rsi; lpASCIICharStr
0x180029845  mov     [rsp+68h+cchASCIIChar], r14d; cchASCIIChar
0x18002984a  mov     r8d, edi; cchUnicodeChar
0x18002984d  mov     rdx, rbp; lpUnicodeCharStr
0x180029850  mov     ecx, r12d; dwFlags
0x180029853  call    cs:__imp_IdnToAscii
0x18002985a  nop     dword ptr [rax+rax+00h]
0x18002985f  test    eax, eax
0x180029861  jnz     short loc_180029895
0x180029863  call    cs:__imp_GetLastError
0x18002986a  nop     dword ptr [rax+rax+00h]
0x18002986f  mov     ecx, eax
0x180029871  mov     r9d, 5Ah ; 'Z'
0x180029877  call    ElValidateWin32_21
0x18002987c  test    eax, eax
0x18002987e  mov     ebx, 1Fh
0x180029883  mov     rcx, rsi; lpMem
0x180029886  cmovz   eax, ebx
0x180029889  mov     ebx, eax
0x18002988b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029890  jmp     loc_18002996F
0x180029895  mov     [r15], rsi
0x180029898  jmp     loc_18002996F
0x18002989d  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rsi; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800298a4  mov     edi, 80070216h
0x1800298a9  jz      short loc_1800298F0
0x1800298ab  call    cs:__imp_GetLastError
0x1800298b2  nop     dword ptr [rax+rax+00h]
0x1800298b7  lea     r9, dword_1800331C4
0x1800298be  mov     [rsp+68h+var_40], edi
0x1800298c2  mov     qword ptr [rsp+68h+cchASCIIChar], r9
0x1800298c7  lea     r8, aOnecoreBaseEco_34; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800298ce  mov     ebx, eax
0x1800298d0  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800298d7  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800298de  mov     r9d, 40h ; '@'
0x1800298e4  mov     ecx, 80000h
0x1800298e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298ee  jmp     short loc_180029932
0x1800298f0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rsi; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800298f7  jz      short loc_180029940
0x1800298f9  call    cs:__imp_GetLastError
0x180029900  nop     dword ptr [rax+rax+00h]
0x180029905  lea     r9, dword_1800331C4
0x18002990c  mov     [rsp+68h+cchASCIIChar], edi
0x180029910  mov     ebx, eax
0x180029912  lea     rdx, aOnecoreBaseEco_34; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029919  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180029920  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180029927  mov     r8d, 40h ; '@'
0x18002992d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029932  mov     ecx, ebx; dwErrCode
0x180029934  call    cs:__imp_SetLastError
0x18002993b  nop     dword ptr [rax+rax+00h]
0x180029940  call    cs:__imp_GetLastError
0x180029947  nop     dword ptr [rax+rax+00h]
0x18002994c  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180029953  mov     ebx, eax
0x180029955  jz      short loc_18002995C
0x180029957  call    ElTraceErrorInfo
0x18002995c  mov     ecx, ebx; dwErrCode
0x18002995e  call    cs:__imp_SetLastError
0x180029965  nop     dword ptr [rax+rax+00h]
0x18002996a  mov     ebx, 216h
0x18002996f  lea     r11, [rsp+68h+var_28]
0x180029974  mov     eax, ebx
0x180029976  mov     rbx, [r11+30h]
0x18002997a  mov     rbp, [r11+38h]
0x18002997e  mov     rsi, [r11+40h]
0x180029982  mov     rsp, r11
0x180029985  pop     r15
0x180029987  pop     r14
0x180029989  pop     r13
0x18002998b  pop     r12
0x18002998d  pop     rdi
0x18002998e  retn
```
