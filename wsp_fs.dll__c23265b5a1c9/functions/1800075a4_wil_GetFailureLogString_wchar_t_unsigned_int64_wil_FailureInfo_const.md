# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800075a4`
- end: `0x180007867`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800055c4`
- `0x180005840`
- `0x180008194`
- `0x18000ae70`

## callees

- `0x180002ad0`
- `0x180003528`
- `0x1800075a4`
- `0x1800084a8`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000775d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000775d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800076d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800076d6`

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
          v7 = (const char *)&byte_1800EBC38;
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
0x1800075a4  mov     [rsp+arg_18], rbx
0x1800075a9  push    rbp
0x1800075aa  push    rsi
0x1800075ab  push    rdi
0x1800075ac  push    r14
0x1800075ae  push    r15
0x1800075b0  sub     rsp, 250h
0x1800075b7  mov     rax, cs:__security_cookie
0x1800075be  xor     rax, rsp
0x1800075c1  mov     [rsp+278h+var_38], rax
0x1800075c9  mov     rbx, r8
0x1800075cc  mov     rsi, rdx
0x1800075cf  mov     r14, rcx
0x1800075d2  xor     r15d, r15d
0x1800075d5  test    rdx, rdx
0x1800075d8  jz      loc_18000783D
0x1800075de  test    rcx, rcx
0x1800075e1  jz      loc_18000783D
0x1800075e7  mov     [rcx], r15w
0x1800075eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800075f2  test    rax, rax
0x1800075f5  jz      short loc_180007618
0x1800075f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800075fe  jz      short loc_180007618
0x180007600  mov     r8, rdx
0x180007603  mov     rdx, rcx
0x180007606  mov     rcx, rbx
0x180007609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000760e  cmp     [r14], r15w
0x180007612  jnz     loc_18000783D
0x180007618  mov     ecx, [rbx]
0x18000761a  mov     bpl, 8
0x18000761d  test    ecx, ecx
0x18000761f  jz      short loc_18000766A
0x180007621  sub     ecx, 1
0x180007624  jz      short loc_180007652
0x180007626  sub     ecx, 1
0x180007629  jz      short loc_180007642
0x18000762b  cmp     ecx, 1
0x18000762e  jz      short loc_180007639
0x180007630  lea     rdi, byte_1800EBC38
0x180007637  jmp     short loc_180007671
0x180007639  lea     rdi, aFailfast; "FailFast"
0x180007640  jmp     short loc_180007671
0x180007642  lea     rax, aLoghr; "LogHr"
0x180007649  lea     rdi, aLognt; "LogNt"
0x180007650  jmp     short loc_180007660
0x180007652  lea     rax, aReturnhr; "ReturnHr"
0x180007659  lea     rdi, aReturnnt; "ReturnNt"
0x180007660  test    [rbx+4], bpl
0x180007664  cmovz   rdi, rax
0x180007668  jmp     short loc_180007671
0x18000766a  lea     rdi, aException_0; "Exception"
0x180007671  xor     edx, edx; Val
0x180007673  mov     r8d, 200h; Size
0x180007679  lea     rcx, [rsp+278h+Buffer]; void *
0x18000767e  call    memset_0
0x180007683  test    [rbx+4], bpl
0x180007687  jz      short loc_1800076AC
0x180007689  mov     ebp, [rbx+0Ch]
0x18000768c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007693  test    rax, rax
0x180007696  jz      short loc_1800076E2
0x180007698  mov     r8d, 100h
0x18000769e  lea     rdx, [rsp+278h+Buffer]
0x1800076a3  mov     ecx, ebp
0x1800076a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076aa  jmp     short loc_1800076E2
0x1800076ac  mov     ebp, [rbx+8]
0x1800076af  mov     [rsp+278h+Arguments], r15; Arguments
0x1800076b4  mov     [rsp+278h+nSize], 100h; nSize
0x1800076bc  lea     rax, [rsp+278h+Buffer]
0x1800076c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800076c6  mov     r9d, 400h; dwLanguageId
0x1800076cc  mov     r8d, ebp; dwMessageId
0x1800076cf  xor     edx, edx; lpSource
0x1800076d1  mov     ecx, 1200h; dwFlags
0x1800076d6  call    cs:__imp_FormatMessageW
0x1800076dd  nop     dword ptr [rax+rax+00h]
0x1800076e2  lea     rsi, [r14+rsi*2]
0x1800076e6  mov     r9, [rbx+38h]; wchar_t *
0x1800076ea  mov     rax, [rbx+88h]
0x1800076f1  mov     rcx, [rbx+80h]
0x1800076f8  mov     rdx, rsi; wchar_t *
0x1800076fb  test    r9, r9
0x1800076fe  jz      short loc_180007722
0x180007700  mov     [rsp+278h+Arguments], rax
0x180007705  mov     qword ptr [rsp+278h+nSize], rcx
0x18000770a  mov     eax, [rbx+40h]
0x18000770d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007711  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007718  mov     rcx, r14; pszDest
0x18000771b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007720  jmp     short loc_180007739
0x180007722  mov     [rsp+278h+lpBuffer], rax
0x180007727  mov     r9, rcx; wchar_t *
0x18000772a  lea     r8, aHsP; "%hs!%p: "
0x180007731  mov     rcx, r14; pszDest
0x180007734  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007739  mov     r14, rax
0x18000773c  mov     r9, [rbx+90h]; wchar_t *
0x180007743  test    r9, r9
0x180007746  jz      short loc_18000775D
0x180007748  lea     r8, aCallerP; "(caller: %p) "
0x18000774f  mov     rdx, rsi; wchar_t *
0x180007752  mov     rcx, rax; pszDest
0x180007755  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000775a  mov     r14, rax
0x18000775d  call    cs:__imp_GetCurrentThreadId
0x180007764  nop     dword ptr [rax+rax+00h]
0x180007769  lea     rcx, [rsp+278h+Buffer]
0x18000776e  mov     [rsp+278h+var_240], rcx
0x180007773  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007777  mov     [rsp+278h+nSize], eax
0x18000777b  mov     eax, [rbx+44h]
0x18000777e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007782  mov     r9, rdi; wchar_t *
0x180007785  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000778c  mov     rdx, rsi; wchar_t *
0x18000778f  mov     rcx, r14; pszDest
0x180007792  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007797  cmp     [rbx+18h], r15
0x18000779b  jnz     short loc_1800077AD
0x18000779d  cmp     [rbx+48h], r15
0x1800077a1  jnz     short loc_1800077AD
0x1800077a3  cmp     [rbx+30h], r15
0x1800077a7  jz      loc_18000783D
0x1800077ad  lea     r8, asc_1800EBD30; "    "
0x1800077b4  mov     rdx, rsi; wchar_t *
0x1800077b7  mov     rcx, rax; pszDest
0x1800077ba  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800077bf  mov     r9, [rbx+18h]; wchar_t *
0x1800077c3  test    r9, r9
0x1800077c6  jz      short loc_1800077DA
0x1800077c8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800077cf  mov     rdx, rsi; wchar_t *
0x1800077d2  mov     rcx, rax; pszDest
0x1800077d5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800077da  mov     r9, [rbx+48h]; wchar_t *
0x1800077de  test    r9, r9
0x1800077e1  jz      short loc_1800077F5
0x1800077e3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800077ea  mov     rdx, rsi; wchar_t *
0x1800077ed  mov     rcx, rax; pszDest
0x1800077f0  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800077f5  mov     rcx, [rbx+28h]
0x1800077f9  mov     r9, [rbx+30h]; wchar_t *
0x1800077fd  mov     rdx, rsi; wchar_t *
0x180007800  test    rcx, rcx
0x180007803  jz      short loc_18000781B
0x180007805  mov     [rsp+278h+lpBuffer], rcx
0x18000780a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007811  mov     rcx, rax; pszDest
0x180007814  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007819  jmp     short loc_18000783D
0x18000781b  mov     rcx, rax; pszDest
0x18000781e  test    r9, r9
0x180007821  jz      short loc_180007831
0x180007823  lea     r8, aHs; "[%hs]\n"
0x18000782a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000782f  jmp     short loc_18000783D
0x180007831  lea     r8, asc_1800EBDA8; "\n"
0x180007838  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000783d  xor     eax, eax
0x18000783f  mov     rcx, [rsp+278h+var_38]
0x180007847  xor     rcx, rsp; StackCookie
0x18000784a  call    __security_check_cookie
0x18000784f  mov     rbx, [rsp+278h+arg_18]
0x180007857  add     rsp, 250h
0x18000785e  pop     r15
0x180007860  pop     r14
0x180007862  pop     rdi
0x180007863  pop     rsi
0x180007864  pop     rbp
0x180007865  retn
```
