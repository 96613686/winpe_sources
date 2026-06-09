# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007494`
- end: `0x180007757`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005754`
- `0x1800059d0`
- `0x180008084`
- `0x18000ac30`

## callees

- `0x180002b50`
- `0x1800035b4`
- `0x180007494`
- `0x180008398`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000764d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000764d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800075c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800075c6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        wchar_t *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const wchar_t *v16; // r9
  wchar_t *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
          v7 = (const char *)&word_1800CE482;
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
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v15,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          (const wchar_t *)v7,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180007494  mov     [rsp+arg_18], rbx
0x180007499  push    rbp
0x18000749a  push    rsi
0x18000749b  push    rdi
0x18000749c  push    r14
0x18000749e  push    r15
0x1800074a0  sub     rsp, 250h
0x1800074a7  mov     rax, cs:__security_cookie
0x1800074ae  xor     rax, rsp
0x1800074b1  mov     [rsp+278h+var_38], rax
0x1800074b9  mov     rbx, r8
0x1800074bc  mov     rsi, rdx
0x1800074bf  mov     r14, rcx
0x1800074c2  xor     r15d, r15d
0x1800074c5  test    rdx, rdx
0x1800074c8  jz      loc_18000772D
0x1800074ce  test    rcx, rcx
0x1800074d1  jz      loc_18000772D
0x1800074d7  mov     [rcx], r15w
0x1800074db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800074e2  test    rax, rax
0x1800074e5  jz      short loc_180007508
0x1800074e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800074ee  jz      short loc_180007508
0x1800074f0  mov     r8, rdx
0x1800074f3  mov     rdx, rcx
0x1800074f6  mov     rcx, rbx
0x1800074f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074fe  cmp     [r14], r15w
0x180007502  jnz     loc_18000772D
0x180007508  mov     ecx, [rbx]
0x18000750a  mov     bpl, 8
0x18000750d  test    ecx, ecx
0x18000750f  jz      short loc_18000755A
0x180007511  sub     ecx, 1
0x180007514  jz      short loc_180007542
0x180007516  sub     ecx, 1
0x180007519  jz      short loc_180007532
0x18000751b  cmp     ecx, 1
0x18000751e  jz      short loc_180007529
0x180007520  lea     rdi, word_1800CE482
0x180007527  jmp     short loc_180007561
0x180007529  lea     rdi, aFailfast; "FailFast"
0x180007530  jmp     short loc_180007561
0x180007532  lea     rax, aLoghr; "LogHr"
0x180007539  lea     rdi, aLognt; "LogNt"
0x180007540  jmp     short loc_180007550
0x180007542  lea     rax, aReturnhr; "ReturnHr"
0x180007549  lea     rdi, aReturnnt; "ReturnNt"
0x180007550  test    [rbx+4], bpl
0x180007554  cmovz   rdi, rax
0x180007558  jmp     short loc_180007561
0x18000755a  lea     rdi, aException_0; "Exception"
0x180007561  xor     edx, edx; Val
0x180007563  mov     r8d, 200h; Size
0x180007569  lea     rcx, [rsp+278h+Buffer]; void *
0x18000756e  call    memset_0
0x180007573  test    [rbx+4], bpl
0x180007577  jz      short loc_18000759C
0x180007579  mov     ebp, [rbx+0Ch]
0x18000757c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007583  test    rax, rax
0x180007586  jz      short loc_1800075D2
0x180007588  mov     r8d, 100h
0x18000758e  lea     rdx, [rsp+278h+Buffer]
0x180007593  mov     ecx, ebp
0x180007595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000759a  jmp     short loc_1800075D2
0x18000759c  mov     ebp, [rbx+8]
0x18000759f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800075a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800075ac  lea     rax, [rsp+278h+Buffer]
0x1800075b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800075b6  mov     r9d, 400h; dwLanguageId
0x1800075bc  mov     r8d, ebp; dwMessageId
0x1800075bf  xor     edx, edx; lpSource
0x1800075c1  mov     ecx, 1200h; dwFlags
0x1800075c6  call    cs:__imp_FormatMessageW
0x1800075cd  nop     dword ptr [rax+rax+00h]
0x1800075d2  lea     rsi, [r14+rsi*2]
0x1800075d6  mov     r9, [rbx+38h]; wchar_t *
0x1800075da  mov     rax, [rbx+88h]
0x1800075e1  mov     rcx, [rbx+80h]
0x1800075e8  mov     rdx, rsi; wchar_t *
0x1800075eb  test    r9, r9
0x1800075ee  jz      short loc_180007612
0x1800075f0  mov     [rsp+278h+Arguments], rax
0x1800075f5  mov     qword ptr [rsp+278h+nSize], rcx
0x1800075fa  mov     eax, [rbx+40h]
0x1800075fd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007601  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007608  mov     rcx, r14; pszDest
0x18000760b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007610  jmp     short loc_180007629
0x180007612  mov     [rsp+278h+lpBuffer], rax
0x180007617  mov     r9, rcx; wchar_t *
0x18000761a  lea     r8, aHsP; "%hs!%p: "
0x180007621  mov     rcx, r14; pszDest
0x180007624  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007629  mov     r14, rax
0x18000762c  mov     r9, [rbx+90h]; wchar_t *
0x180007633  test    r9, r9
0x180007636  jz      short loc_18000764D
0x180007638  lea     r8, aCallerP; "(caller: %p) "
0x18000763f  mov     rdx, rsi; wchar_t *
0x180007642  mov     rcx, rax; pszDest
0x180007645  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000764a  mov     r14, rax
0x18000764d  call    cs:__imp_GetCurrentThreadId
0x180007654  nop     dword ptr [rax+rax+00h]
0x180007659  lea     rcx, [rsp+278h+Buffer]
0x18000765e  mov     [rsp+278h+var_240], rcx
0x180007663  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007667  mov     [rsp+278h+nSize], eax
0x18000766b  mov     eax, [rbx+44h]
0x18000766e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007672  mov     r9, rdi; wchar_t *
0x180007675  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000767c  mov     rdx, rsi; wchar_t *
0x18000767f  mov     rcx, r14; pszDest
0x180007682  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007687  cmp     [rbx+18h], r15
0x18000768b  jnz     short loc_18000769D
0x18000768d  cmp     [rbx+48h], r15
0x180007691  jnz     short loc_18000769D
0x180007693  cmp     [rbx+30h], r15
0x180007697  jz      loc_18000772D
0x18000769d  lea     r8, asc_1800CE570; "    "
0x1800076a4  mov     rdx, rsi; wchar_t *
0x1800076a7  mov     rcx, rax; pszDest
0x1800076aa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800076af  mov     r9, [rbx+18h]; wchar_t *
0x1800076b3  test    r9, r9
0x1800076b6  jz      short loc_1800076CA
0x1800076b8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800076bf  mov     rdx, rsi; wchar_t *
0x1800076c2  mov     rcx, rax; pszDest
0x1800076c5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800076ca  mov     r9, [rbx+48h]; wchar_t *
0x1800076ce  test    r9, r9
0x1800076d1  jz      short loc_1800076E5
0x1800076d3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800076da  mov     rdx, rsi; wchar_t *
0x1800076dd  mov     rcx, rax; pszDest
0x1800076e0  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800076e5  mov     rcx, [rbx+28h]
0x1800076e9  mov     r9, [rbx+30h]; wchar_t *
0x1800076ed  mov     rdx, rsi; wchar_t *
0x1800076f0  test    rcx, rcx
0x1800076f3  jz      short loc_18000770B
0x1800076f5  mov     [rsp+278h+lpBuffer], rcx
0x1800076fa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007701  mov     rcx, rax; pszDest
0x180007704  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007709  jmp     short loc_18000772D
0x18000770b  mov     rcx, rax; pszDest
0x18000770e  test    r9, r9
0x180007711  jz      short loc_180007721
0x180007713  lea     r8, aHs; "[%hs]\n"
0x18000771a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000771f  jmp     short loc_18000772D
0x180007721  lea     r8, asc_1800CE5E8; "\n"
0x180007728  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000772d  xor     eax, eax
0x18000772f  mov     rcx, [rsp+278h+var_38]
0x180007737  xor     rcx, rsp; StackCookie
0x18000773a  call    __security_check_cookie
0x18000773f  mov     rbx, [rsp+278h+arg_18]
0x180007747  add     rsp, 250h
0x18000774e  pop     r15
0x180007750  pop     r14
0x180007752  pop     rdi
0x180007753  pop     rsi
0x180007754  pop     rbp
0x180007755  retn
```
