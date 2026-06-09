# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000e0a4`
- end: `0x18000e35a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c138`
- `0x18000ee98`
- `0x18000f4d4`
- `0x180012760`

## callees

- `0x180009e82`
- `0x18000e0a4`
- `0x18000f198`
- `0x18003c240`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e257`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e1d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e1d6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const unsigned __int16 *v16; // r9
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !pszDest )
    return 0;
  *pszDest = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, pszDest, a2);
      if ( *pszDest )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v8 = "ReturnHr";
      v7 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v7 = "FailFast";
        else
          v7 = (const char *)&word_18004387A;
        goto LABEL_18;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_18;
  }
  v7 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v9, Buffer, 0x100u);
  }
  else
  {
    v9 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v9, 0x400u, Buffer, 0x100u, 0);
  }
  v10 = &pszDest[(_QWORD)a2];
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v15,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v7,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e0a4  mov     [rsp+arg_18], rbx
0x18000e0a9  push    rbp
0x18000e0aa  push    rsi
0x18000e0ab  push    rdi
0x18000e0ac  push    r14
0x18000e0ae  push    r15
0x18000e0b0  sub     rsp, 250h
0x18000e0b7  mov     rax, cs:__security_cookie
0x18000e0be  xor     rax, rsp
0x18000e0c1  mov     [rsp+278h+var_38], rax
0x18000e0c9  mov     rbx, r8
0x18000e0cc  mov     rsi, rdx
0x18000e0cf  mov     r14, rcx
0x18000e0d2  xor     r15d, r15d
0x18000e0d5  test    rdx, rdx
0x18000e0d8  jz      loc_18000E331
0x18000e0de  test    rcx, rcx
0x18000e0e1  jz      loc_18000E331
0x18000e0e7  mov     [rcx], r15w
0x18000e0eb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e0f2  test    rax, rax
0x18000e0f5  jz      short loc_18000E118
0x18000e0f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000e0fe  jz      short loc_18000E118
0x18000e100  mov     r8, rdx
0x18000e103  mov     rdx, rcx
0x18000e106  mov     rcx, rbx
0x18000e109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e10e  cmp     [r14], r15w
0x18000e112  jnz     loc_18000E331
0x18000e118  mov     ecx, [rbx]
0x18000e11a  mov     bpl, 8
0x18000e11d  test    ecx, ecx
0x18000e11f  jz      short loc_18000E16A
0x18000e121  sub     ecx, 1
0x18000e124  jz      short loc_18000E152
0x18000e126  sub     ecx, 1
0x18000e129  jz      short loc_18000E142
0x18000e12b  cmp     ecx, 1
0x18000e12e  jz      short loc_18000E139
0x18000e130  lea     rdi, word_18004387A
0x18000e137  jmp     short loc_18000E171
0x18000e139  lea     rdi, aFailfast; "FailFast"
0x18000e140  jmp     short loc_18000E171
0x18000e142  lea     rax, aLoghr; "LogHr"
0x18000e149  lea     rdi, aLognt; "LogNt"
0x18000e150  jmp     short loc_18000E160
0x18000e152  lea     rax, aReturnhr; "ReturnHr"
0x18000e159  lea     rdi, aReturnnt; "ReturnNt"
0x18000e160  test    [rbx+4], bpl
0x18000e164  cmovz   rdi, rax
0x18000e168  jmp     short loc_18000E171
0x18000e16a  lea     rdi, aException; "Exception"
0x18000e171  xor     edx, edx; Val
0x18000e173  mov     r8d, 200h; Size
0x18000e179  lea     rcx, [rsp+278h+Buffer]; void *
0x18000e17e  call    memset_0
0x18000e183  test    [rbx+4], bpl
0x18000e187  jz      short loc_18000E1AC
0x18000e189  mov     ebp, [rbx+0Ch]
0x18000e18c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000e193  test    rax, rax
0x18000e196  jz      short loc_18000E1DC
0x18000e198  mov     r8d, 100h
0x18000e19e  lea     rdx, [rsp+278h+Buffer]
0x18000e1a3  mov     ecx, ebp
0x18000e1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1aa  jmp     short loc_18000E1DC
0x18000e1ac  mov     ebp, [rbx+8]
0x18000e1af  mov     [rsp+278h+Arguments], r15; Arguments
0x18000e1b4  mov     [rsp+278h+nSize], 100h; nSize
0x18000e1bc  lea     rax, [rsp+278h+Buffer]
0x18000e1c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000e1c6  mov     r9d, 400h; dwLanguageId
0x18000e1cc  mov     r8d, ebp; dwMessageId
0x18000e1cf  xor     edx, edx; lpSource
0x18000e1d1  mov     ecx, 1200h; dwFlags
0x18000e1d6  call    cs:__imp_FormatMessageW
0x18000e1dc  lea     rsi, [r14+rsi*2]
0x18000e1e0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000e1e4  mov     rax, [rbx+88h]
0x18000e1eb  mov     rcx, [rbx+80h]
0x18000e1f2  mov     rdx, rsi; unsigned __int16 *
0x18000e1f5  test    r9, r9
0x18000e1f8  jz      short loc_18000E21C
0x18000e1fa  mov     [rsp+278h+Arguments], rax
0x18000e1ff  mov     qword ptr [rsp+278h+nSize], rcx
0x18000e204  mov     eax, [rbx+40h]
0x18000e207  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000e20b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000e212  mov     rcx, r14; pszDest
0x18000e215  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e21a  jmp     short loc_18000E233
0x18000e21c  mov     [rsp+278h+lpBuffer], rax
0x18000e221  mov     r9, rcx; unsigned __int16 *
0x18000e224  lea     r8, aHsP; "%hs!%p: "
0x18000e22b  mov     rcx, r14; pszDest
0x18000e22e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e233  mov     r14, rax
0x18000e236  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000e23d  test    r9, r9
0x18000e240  jz      short loc_18000E257
0x18000e242  lea     r8, aCallerP; "(caller: %p) "
0x18000e249  mov     rdx, rsi; unsigned __int16 *
0x18000e24c  mov     rcx, rax; pszDest
0x18000e24f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e254  mov     r14, rax
0x18000e257  call    cs:__imp_GetCurrentThreadId
0x18000e25d  lea     rcx, [rsp+278h+Buffer]
0x18000e262  mov     [rsp+278h+var_240], rcx
0x18000e267  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000e26b  mov     [rsp+278h+nSize], eax
0x18000e26f  mov     eax, [rbx+44h]
0x18000e272  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000e276  mov     r9, rdi; unsigned __int16 *
0x18000e279  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000e280  mov     rdx, rsi; unsigned __int16 *
0x18000e283  mov     rcx, r14; pszDest
0x18000e286  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e28b  cmp     [rbx+18h], r15
0x18000e28f  jnz     short loc_18000E2A1
0x18000e291  cmp     [rbx+48h], r15
0x18000e295  jnz     short loc_18000E2A1
0x18000e297  cmp     [rbx+30h], r15
0x18000e29b  jz      loc_18000E331
0x18000e2a1  lea     r8, asc_180043968; "    "
0x18000e2a8  mov     rdx, rsi; unsigned __int16 *
0x18000e2ab  mov     rcx, rax; pszDest
0x18000e2ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e2b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000e2b7  test    r9, r9
0x18000e2ba  jz      short loc_18000E2CE
0x18000e2bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000e2c3  mov     rdx, rsi; unsigned __int16 *
0x18000e2c6  mov     rcx, rax; pszDest
0x18000e2c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e2ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000e2d2  test    r9, r9
0x18000e2d5  jz      short loc_18000E2E9
0x18000e2d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000e2de  mov     rdx, rsi; unsigned __int16 *
0x18000e2e1  mov     rcx, rax; pszDest
0x18000e2e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e2e9  mov     rcx, [rbx+28h]
0x18000e2ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000e2f1  mov     rdx, rsi; unsigned __int16 *
0x18000e2f4  test    rcx, rcx
0x18000e2f7  jz      short loc_18000E30F
0x18000e2f9  mov     [rsp+278h+lpBuffer], rcx
0x18000e2fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000e305  mov     rcx, rax; pszDest
0x18000e308  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e30d  jmp     short loc_18000E331
0x18000e30f  mov     rcx, rax; pszDest
0x18000e312  test    r9, r9
0x18000e315  jz      short loc_18000E325
0x18000e317  lea     r8, aHs; "[%hs]\n"
0x18000e31e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e323  jmp     short loc_18000E331
0x18000e325  lea     r8, asc_1800439E0; "\n"
0x18000e32c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e331  xor     eax, eax
0x18000e333  mov     rcx, [rsp+278h+var_38]
0x18000e33b  xor     rcx, rsp; StackCookie
0x18000e33e  call    __security_check_cookie
0x18000e343  mov     rbx, [rsp+278h+arg_18]
0x18000e34b  add     rsp, 250h
0x18000e352  pop     r15
0x18000e354  pop     r14
0x18000e356  pop     rdi
0x18000e357  pop     rsi
0x18000e358  pop     rbp
0x18000e359  retn
```
