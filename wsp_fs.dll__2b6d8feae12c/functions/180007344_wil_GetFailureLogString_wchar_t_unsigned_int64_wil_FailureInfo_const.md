# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007344`
- end: `0x1800075fa`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000551c`
- `0x180005784`
- `0x180007ec8`
- `0x18000aba0`

## callees

- `0x180002a70`
- `0x180003498`
- `0x180007344`
- `0x1800081c8`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007476`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007476`

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
          v7 = (const char *)&byte_1800E9C18;
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
0x180007344  mov     [rsp+arg_18], rbx
0x180007349  push    rbp
0x18000734a  push    rsi
0x18000734b  push    rdi
0x18000734c  push    r14
0x18000734e  push    r15
0x180007350  sub     rsp, 250h
0x180007357  mov     rax, cs:__security_cookie
0x18000735e  xor     rax, rsp
0x180007361  mov     [rsp+278h+var_38], rax
0x180007369  mov     rbx, r8
0x18000736c  mov     rsi, rdx
0x18000736f  mov     r14, rcx
0x180007372  xor     r15d, r15d
0x180007375  test    rdx, rdx
0x180007378  jz      loc_1800075D1
0x18000737e  test    rcx, rcx
0x180007381  jz      loc_1800075D1
0x180007387  mov     [rcx], r15w
0x18000738b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007392  test    rax, rax
0x180007395  jz      short loc_1800073B8
0x180007397  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000739e  jz      short loc_1800073B8
0x1800073a0  mov     r8, rdx
0x1800073a3  mov     rdx, rcx
0x1800073a6  mov     rcx, rbx
0x1800073a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ae  cmp     [r14], r15w
0x1800073b2  jnz     loc_1800075D1
0x1800073b8  mov     ecx, [rbx]
0x1800073ba  mov     bpl, 8
0x1800073bd  test    ecx, ecx
0x1800073bf  jz      short loc_18000740A
0x1800073c1  sub     ecx, 1
0x1800073c4  jz      short loc_1800073F2
0x1800073c6  sub     ecx, 1
0x1800073c9  jz      short loc_1800073E2
0x1800073cb  cmp     ecx, 1
0x1800073ce  jz      short loc_1800073D9
0x1800073d0  lea     rdi, byte_1800E9C18
0x1800073d7  jmp     short loc_180007411
0x1800073d9  lea     rdi, aFailfast; "FailFast"
0x1800073e0  jmp     short loc_180007411
0x1800073e2  lea     rax, aLoghr; "LogHr"
0x1800073e9  lea     rdi, aLognt; "LogNt"
0x1800073f0  jmp     short loc_180007400
0x1800073f2  lea     rax, aReturnhr; "ReturnHr"
0x1800073f9  lea     rdi, aReturnnt; "ReturnNt"
0x180007400  test    [rbx+4], bpl
0x180007404  cmovz   rdi, rax
0x180007408  jmp     short loc_180007411
0x18000740a  lea     rdi, aException_0; "Exception"
0x180007411  xor     edx, edx; Val
0x180007413  mov     r8d, 200h; Size
0x180007419  lea     rcx, [rsp+278h+Buffer]; void *
0x18000741e  call    memset_0
0x180007423  test    [rbx+4], bpl
0x180007427  jz      short loc_18000744C
0x180007429  mov     ebp, [rbx+0Ch]
0x18000742c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007433  test    rax, rax
0x180007436  jz      short loc_18000747C
0x180007438  mov     r8d, 100h
0x18000743e  lea     rdx, [rsp+278h+Buffer]
0x180007443  mov     ecx, ebp
0x180007445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000744a  jmp     short loc_18000747C
0x18000744c  mov     ebp, [rbx+8]
0x18000744f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007454  mov     [rsp+278h+nSize], 100h; nSize
0x18000745c  lea     rax, [rsp+278h+Buffer]
0x180007461  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007466  mov     r9d, 400h; dwLanguageId
0x18000746c  mov     r8d, ebp; dwMessageId
0x18000746f  xor     edx, edx; lpSource
0x180007471  mov     ecx, 1200h; dwFlags
0x180007476  call    cs:__imp_FormatMessageW
0x18000747c  lea     rsi, [r14+rsi*2]
0x180007480  mov     r9, [rbx+38h]; wchar_t *
0x180007484  mov     rax, [rbx+88h]
0x18000748b  mov     rcx, [rbx+80h]
0x180007492  mov     rdx, rsi; wchar_t *
0x180007495  test    r9, r9
0x180007498  jz      short loc_1800074BC
0x18000749a  mov     [rsp+278h+Arguments], rax
0x18000749f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800074a4  mov     eax, [rbx+40h]
0x1800074a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800074ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800074b2  mov     rcx, r14; pszDest
0x1800074b5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800074ba  jmp     short loc_1800074D3
0x1800074bc  mov     [rsp+278h+lpBuffer], rax
0x1800074c1  mov     r9, rcx; wchar_t *
0x1800074c4  lea     r8, aHsP; "%hs!%p: "
0x1800074cb  mov     rcx, r14; pszDest
0x1800074ce  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800074d3  mov     r14, rax
0x1800074d6  mov     r9, [rbx+90h]; wchar_t *
0x1800074dd  test    r9, r9
0x1800074e0  jz      short loc_1800074F7
0x1800074e2  lea     r8, aCallerP; "(caller: %p) "
0x1800074e9  mov     rdx, rsi; wchar_t *
0x1800074ec  mov     rcx, rax; pszDest
0x1800074ef  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800074f4  mov     r14, rax
0x1800074f7  call    cs:__imp_GetCurrentThreadId
0x1800074fd  lea     rcx, [rsp+278h+Buffer]
0x180007502  mov     [rsp+278h+var_240], rcx
0x180007507  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000750b  mov     [rsp+278h+nSize], eax
0x18000750f  mov     eax, [rbx+44h]
0x180007512  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007516  mov     r9, rdi; wchar_t *
0x180007519  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007520  mov     rdx, rsi; wchar_t *
0x180007523  mov     rcx, r14; pszDest
0x180007526  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000752b  cmp     [rbx+18h], r15
0x18000752f  jnz     short loc_180007541
0x180007531  cmp     [rbx+48h], r15
0x180007535  jnz     short loc_180007541
0x180007537  cmp     [rbx+30h], r15
0x18000753b  jz      loc_1800075D1
0x180007541  lea     r8, asc_1800E9D10; "    "
0x180007548  mov     rdx, rsi; wchar_t *
0x18000754b  mov     rcx, rax; pszDest
0x18000754e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007553  mov     r9, [rbx+18h]; wchar_t *
0x180007557  test    r9, r9
0x18000755a  jz      short loc_18000756E
0x18000755c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007563  mov     rdx, rsi; wchar_t *
0x180007566  mov     rcx, rax; pszDest
0x180007569  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000756e  mov     r9, [rbx+48h]; wchar_t *
0x180007572  test    r9, r9
0x180007575  jz      short loc_180007589
0x180007577  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000757e  mov     rdx, rsi; wchar_t *
0x180007581  mov     rcx, rax; pszDest
0x180007584  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007589  mov     rcx, [rbx+28h]
0x18000758d  mov     r9, [rbx+30h]; wchar_t *
0x180007591  mov     rdx, rsi; wchar_t *
0x180007594  test    rcx, rcx
0x180007597  jz      short loc_1800075AF
0x180007599  mov     [rsp+278h+lpBuffer], rcx
0x18000759e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800075a5  mov     rcx, rax; pszDest
0x1800075a8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800075ad  jmp     short loc_1800075D1
0x1800075af  mov     rcx, rax; pszDest
0x1800075b2  test    r9, r9
0x1800075b5  jz      short loc_1800075C5
0x1800075b7  lea     r8, aHs; "[%hs]\n"
0x1800075be  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800075c3  jmp     short loc_1800075D1
0x1800075c5  lea     r8, asc_1800E9D88; "\n"
0x1800075cc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800075d1  xor     eax, eax
0x1800075d3  mov     rcx, [rsp+278h+var_38]
0x1800075db  xor     rcx, rsp; StackCookie
0x1800075de  call    __security_check_cookie
0x1800075e3  mov     rbx, [rsp+278h+arg_18]
0x1800075eb  add     rsp, 250h
0x1800075f2  pop     r15
0x1800075f4  pop     r14
0x1800075f6  pop     rdi
0x1800075f7  pop     rsi
0x1800075f8  pop     rbp
0x1800075f9  retn
```
