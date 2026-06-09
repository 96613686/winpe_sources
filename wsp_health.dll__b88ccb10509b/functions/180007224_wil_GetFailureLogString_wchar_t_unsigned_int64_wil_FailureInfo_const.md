# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007224`
- end: `0x1800074da`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000569c`
- `0x180005904`
- `0x180007da8`
- `0x18000a960`

## callees

- `0x180002ae0`
- `0x180003514`
- `0x180007224`
- `0x1800080a8`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800073d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800073d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007356`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007356`

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
          v7 = (const char *)&word_1800CC462;
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
0x180007224  mov     [rsp+arg_18], rbx
0x180007229  push    rbp
0x18000722a  push    rsi
0x18000722b  push    rdi
0x18000722c  push    r14
0x18000722e  push    r15
0x180007230  sub     rsp, 250h
0x180007237  mov     rax, cs:__security_cookie
0x18000723e  xor     rax, rsp
0x180007241  mov     [rsp+278h+var_38], rax
0x180007249  mov     rbx, r8
0x18000724c  mov     rsi, rdx
0x18000724f  mov     r14, rcx
0x180007252  xor     r15d, r15d
0x180007255  test    rdx, rdx
0x180007258  jz      loc_1800074B1
0x18000725e  test    rcx, rcx
0x180007261  jz      loc_1800074B1
0x180007267  mov     [rcx], r15w
0x18000726b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007272  test    rax, rax
0x180007275  jz      short loc_180007298
0x180007277  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000727e  jz      short loc_180007298
0x180007280  mov     r8, rdx
0x180007283  mov     rdx, rcx
0x180007286  mov     rcx, rbx
0x180007289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000728e  cmp     [r14], r15w
0x180007292  jnz     loc_1800074B1
0x180007298  mov     ecx, [rbx]
0x18000729a  mov     bpl, 8
0x18000729d  test    ecx, ecx
0x18000729f  jz      short loc_1800072EA
0x1800072a1  sub     ecx, 1
0x1800072a4  jz      short loc_1800072D2
0x1800072a6  sub     ecx, 1
0x1800072a9  jz      short loc_1800072C2
0x1800072ab  cmp     ecx, 1
0x1800072ae  jz      short loc_1800072B9
0x1800072b0  lea     rdi, word_1800CC462
0x1800072b7  jmp     short loc_1800072F1
0x1800072b9  lea     rdi, aFailfast; "FailFast"
0x1800072c0  jmp     short loc_1800072F1
0x1800072c2  lea     rax, aLoghr; "LogHr"
0x1800072c9  lea     rdi, aLognt; "LogNt"
0x1800072d0  jmp     short loc_1800072E0
0x1800072d2  lea     rax, aReturnhr; "ReturnHr"
0x1800072d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800072e0  test    [rbx+4], bpl
0x1800072e4  cmovz   rdi, rax
0x1800072e8  jmp     short loc_1800072F1
0x1800072ea  lea     rdi, aException_0; "Exception"
0x1800072f1  xor     edx, edx; Val
0x1800072f3  mov     r8d, 200h; Size
0x1800072f9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800072fe  call    memset_0
0x180007303  test    [rbx+4], bpl
0x180007307  jz      short loc_18000732C
0x180007309  mov     ebp, [rbx+0Ch]
0x18000730c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007313  test    rax, rax
0x180007316  jz      short loc_18000735C
0x180007318  mov     r8d, 100h
0x18000731e  lea     rdx, [rsp+278h+Buffer]
0x180007323  mov     ecx, ebp
0x180007325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000732a  jmp     short loc_18000735C
0x18000732c  mov     ebp, [rbx+8]
0x18000732f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007334  mov     [rsp+278h+nSize], 100h; nSize
0x18000733c  lea     rax, [rsp+278h+Buffer]
0x180007341  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007346  mov     r9d, 400h; dwLanguageId
0x18000734c  mov     r8d, ebp; dwMessageId
0x18000734f  xor     edx, edx; lpSource
0x180007351  mov     ecx, 1200h; dwFlags
0x180007356  call    cs:__imp_FormatMessageW
0x18000735c  lea     rsi, [r14+rsi*2]
0x180007360  mov     r9, [rbx+38h]; wchar_t *
0x180007364  mov     rax, [rbx+88h]
0x18000736b  mov     rcx, [rbx+80h]
0x180007372  mov     rdx, rsi; wchar_t *
0x180007375  test    r9, r9
0x180007378  jz      short loc_18000739C
0x18000737a  mov     [rsp+278h+Arguments], rax
0x18000737f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007384  mov     eax, [rbx+40h]
0x180007387  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000738b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007392  mov     rcx, r14; pszDest
0x180007395  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000739a  jmp     short loc_1800073B3
0x18000739c  mov     [rsp+278h+lpBuffer], rax
0x1800073a1  mov     r9, rcx; wchar_t *
0x1800073a4  lea     r8, aHsP; "%hs!%p: "
0x1800073ab  mov     rcx, r14; pszDest
0x1800073ae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800073b3  mov     r14, rax
0x1800073b6  mov     r9, [rbx+90h]; wchar_t *
0x1800073bd  test    r9, r9
0x1800073c0  jz      short loc_1800073D7
0x1800073c2  lea     r8, aCallerP; "(caller: %p) "
0x1800073c9  mov     rdx, rsi; wchar_t *
0x1800073cc  mov     rcx, rax; pszDest
0x1800073cf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800073d4  mov     r14, rax
0x1800073d7  call    cs:__imp_GetCurrentThreadId
0x1800073dd  lea     rcx, [rsp+278h+Buffer]
0x1800073e2  mov     [rsp+278h+var_240], rcx
0x1800073e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800073eb  mov     [rsp+278h+nSize], eax
0x1800073ef  mov     eax, [rbx+44h]
0x1800073f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800073f6  mov     r9, rdi; wchar_t *
0x1800073f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007400  mov     rdx, rsi; wchar_t *
0x180007403  mov     rcx, r14; pszDest
0x180007406  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000740b  cmp     [rbx+18h], r15
0x18000740f  jnz     short loc_180007421
0x180007411  cmp     [rbx+48h], r15
0x180007415  jnz     short loc_180007421
0x180007417  cmp     [rbx+30h], r15
0x18000741b  jz      loc_1800074B1
0x180007421  lea     r8, asc_1800CC550; "    "
0x180007428  mov     rdx, rsi; wchar_t *
0x18000742b  mov     rcx, rax; pszDest
0x18000742e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007433  mov     r9, [rbx+18h]; wchar_t *
0x180007437  test    r9, r9
0x18000743a  jz      short loc_18000744E
0x18000743c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007443  mov     rdx, rsi; wchar_t *
0x180007446  mov     rcx, rax; pszDest
0x180007449  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000744e  mov     r9, [rbx+48h]; wchar_t *
0x180007452  test    r9, r9
0x180007455  jz      short loc_180007469
0x180007457  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000745e  mov     rdx, rsi; wchar_t *
0x180007461  mov     rcx, rax; pszDest
0x180007464  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007469  mov     rcx, [rbx+28h]
0x18000746d  mov     r9, [rbx+30h]; wchar_t *
0x180007471  mov     rdx, rsi; wchar_t *
0x180007474  test    rcx, rcx
0x180007477  jz      short loc_18000748F
0x180007479  mov     [rsp+278h+lpBuffer], rcx
0x18000747e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007485  mov     rcx, rax; pszDest
0x180007488  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000748d  jmp     short loc_1800074B1
0x18000748f  mov     rcx, rax; pszDest
0x180007492  test    r9, r9
0x180007495  jz      short loc_1800074A5
0x180007497  lea     r8, aHs; "[%hs]\n"
0x18000749e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800074a3  jmp     short loc_1800074B1
0x1800074a5  lea     r8, asc_1800CC5C8; "\n"
0x1800074ac  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800074b1  xor     eax, eax
0x1800074b3  mov     rcx, [rsp+278h+var_38]
0x1800074bb  xor     rcx, rsp; StackCookie
0x1800074be  call    __security_check_cookie
0x1800074c3  mov     rbx, [rsp+278h+arg_18]
0x1800074cb  add     rsp, 250h
0x1800074d2  pop     r15
0x1800074d4  pop     r14
0x1800074d6  pop     rdi
0x1800074d7  pop     rsi
0x1800074d8  pop     rbp
0x1800074d9  retn
```
