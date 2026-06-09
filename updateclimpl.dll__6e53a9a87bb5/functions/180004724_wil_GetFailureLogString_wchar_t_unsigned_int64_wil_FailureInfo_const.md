# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004724`
- end: `0x1800049d8`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180005560`
- `0x180005a50`
- `0x180006cf4`
- `0x18000739c`
- `0x18000d66c`
- `0x1800155bd`
- `0x1800156f6`

## callees

- `0x1800046b8`
- `0x180004724`
- `0x180010310`
- `0x1800148e0`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048d5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004854`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004854`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rdi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
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
  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v7 = (const char *)&word_180018022;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = (wil::details *)v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004724  mov     [rsp+arg_18], rbx
0x180004729  push    rbp
0x18000472a  push    rsi
0x18000472b  push    rdi
0x18000472c  push    r14
0x18000472e  push    r15
0x180004730  sub     rsp, 250h
0x180004737  mov     rax, cs:__security_cookie
0x18000473e  xor     rax, rsp
0x180004741  mov     [rsp+278h+var_38], rax
0x180004749  mov     rbx, r8
0x18000474c  mov     rdi, rdx
0x18000474f  mov     r14, rcx
0x180004752  xor     r15d, r15d
0x180004755  test    rdx, rdx
0x180004758  jz      loc_1800049AF
0x18000475e  test    rcx, rcx
0x180004761  jz      loc_1800049AF
0x180004767  mov     [rcx], r15w
0x18000476b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004772  test    rax, rax
0x180004775  jz      short loc_180004798
0x180004777  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000477e  jz      short loc_180004798
0x180004780  mov     r8, rdx
0x180004783  mov     rdx, rcx
0x180004786  mov     rcx, rbx
0x180004789  call    _guard_dispatch_icall
0x18000478e  cmp     [r14], r15w
0x180004792  jnz     loc_1800049AF
0x180004798  lea     rsi, word_180018022
0x18000479f  mov     ecx, [rbx]
0x1800047a1  mov     bpl, 8
0x1800047a4  test    ecx, ecx
0x1800047a6  jz      short loc_1800047E8
0x1800047a8  sub     ecx, 1
0x1800047ab  jz      short loc_1800047D0
0x1800047ad  sub     ecx, 1
0x1800047b0  jz      short loc_1800047C0
0x1800047b2  cmp     ecx, 1
0x1800047b5  jnz     short loc_1800047EF
0x1800047b7  lea     rsi, aFailfast; "FailFast"
0x1800047be  jmp     short loc_1800047EF
0x1800047c0  lea     rax, aLoghr; "LogHr"
0x1800047c7  lea     rsi, aLognt; "LogNt"
0x1800047ce  jmp     short loc_1800047DE
0x1800047d0  lea     rax, aReturnhr; "ReturnHr"
0x1800047d7  lea     rsi, aReturnnt; "ReturnNt"
0x1800047de  test    [rbx+4], bpl
0x1800047e2  cmovz   rsi, rax
0x1800047e6  jmp     short loc_1800047EF
0x1800047e8  lea     rsi, aException; "Exception"
0x1800047ef  xor     edx, edx; Val
0x1800047f1  mov     r8d, 200h; Size
0x1800047f7  lea     rcx, [rsp+278h+Buffer]; void *
0x1800047fc  call    memset
0x180004801  test    [rbx+4], bpl
0x180004805  jz      short loc_18000482A
0x180004807  mov     ebp, [rbx+0Ch]
0x18000480a  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180004811  test    rax, rax
0x180004814  jz      short loc_18000485A
0x180004816  mov     r8d, 100h
0x18000481c  lea     rdx, [rsp+278h+Buffer]
0x180004821  mov     ecx, ebp
0x180004823  call    _guard_dispatch_icall
0x180004828  jmp     short loc_18000485A
0x18000482a  mov     ebp, [rbx+8]
0x18000482d  mov     [rsp+278h+Arguments], r15; Arguments
0x180004832  mov     [rsp+278h+nSize], 100h; nSize
0x18000483a  lea     rax, [rsp+278h+Buffer]
0x18000483f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004844  mov     r9d, 400h; dwLanguageId
0x18000484a  mov     r8d, ebp; dwMessageId
0x18000484d  xor     edx, edx; lpSource
0x18000484f  mov     ecx, 1200h; dwFlags
0x180004854  call    cs:__imp_FormatMessageW
0x18000485a  lea     rdi, [r14+rdi*2]
0x18000485e  mov     r9, [rbx+38h]; wchar_t *
0x180004862  mov     rax, [rbx+88h]
0x180004869  mov     rcx, [rbx+80h]
0x180004870  mov     rdx, rdi; wchar_t *
0x180004873  test    r9, r9
0x180004876  jz      short loc_18000489A
0x180004878  mov     [rsp+278h+Arguments], rax
0x18000487d  mov     qword ptr [rsp+278h+nSize], rcx
0x180004882  mov     eax, [rbx+40h]
0x180004885  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004889  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004890  mov     rcx, r14; this
0x180004893  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004898  jmp     short loc_1800048B1
0x18000489a  mov     [rsp+278h+lpBuffer], rax
0x18000489f  mov     r9, rcx; wchar_t *
0x1800048a2  lea     r8, aHsP; "%hs!%p: "
0x1800048a9  mov     rcx, r14; this
0x1800048ac  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800048b1  mov     r14, rax
0x1800048b4  mov     r9, [rbx+90h]; wchar_t *
0x1800048bb  test    r9, r9
0x1800048be  jz      short loc_1800048D5
0x1800048c0  lea     r8, aCallerP; "(caller: %p) "
0x1800048c7  mov     rdx, rdi; wchar_t *
0x1800048ca  mov     rcx, rax; this
0x1800048cd  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800048d2  mov     r14, rax
0x1800048d5  call    cs:__imp_GetCurrentThreadId
0x1800048db  lea     rcx, [rsp+278h+Buffer]
0x1800048e0  mov     [rsp+278h+var_240], rcx
0x1800048e5  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800048e9  mov     [rsp+278h+nSize], eax
0x1800048ed  mov     eax, [rbx+44h]
0x1800048f0  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800048f4  mov     r9, rsi; wchar_t *
0x1800048f7  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800048fe  mov     rdx, rdi; wchar_t *
0x180004901  mov     rcx, r14; this
0x180004904  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004909  cmp     [rbx+18h], r15
0x18000490d  jnz     short loc_18000491F
0x18000490f  cmp     [rbx+48h], r15
0x180004913  jnz     short loc_18000491F
0x180004915  cmp     [rbx+30h], r15
0x180004919  jz      loc_1800049AF
0x18000491f  lea     r8, asc_180018128; "    "
0x180004926  mov     rdx, rdi; wchar_t *
0x180004929  mov     rcx, rax; this
0x18000492c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004931  mov     r9, [rbx+18h]; wchar_t *
0x180004935  test    r9, r9
0x180004938  jz      short loc_18000494C
0x18000493a  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004941  mov     rdx, rdi; wchar_t *
0x180004944  mov     rcx, rax; this
0x180004947  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000494c  mov     r9, [rbx+48h]; wchar_t *
0x180004950  test    r9, r9
0x180004953  jz      short loc_180004967
0x180004955  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000495c  mov     rdx, rdi; wchar_t *
0x18000495f  mov     rcx, rax; this
0x180004962  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004967  mov     rcx, [rbx+28h]
0x18000496b  mov     r9, [rbx+30h]; wchar_t *
0x18000496f  mov     rdx, rdi; wchar_t *
0x180004972  test    rcx, rcx
0x180004975  jz      short loc_18000498D
0x180004977  mov     [rsp+278h+lpBuffer], rcx
0x18000497c  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004983  mov     rcx, rax; this
0x180004986  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000498b  jmp     short loc_1800049AF
0x18000498d  mov     rcx, rax; this
0x180004990  test    r9, r9
0x180004993  jz      short loc_1800049A3
0x180004995  lea     r8, aHs; "[%hs]\n"
0x18000499c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800049a1  jmp     short loc_1800049AF
0x1800049a3  lea     r8, asc_1800181A0; "\n"
0x1800049aa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800049af  xor     eax, eax
0x1800049b1  mov     rcx, [rsp+278h+var_38]
0x1800049b9  xor     rcx, rsp; StackCookie
0x1800049bc  call    __security_check_cookie
0x1800049c1  mov     rbx, [rsp+278h+arg_18]
0x1800049c9  add     rsp, 250h
0x1800049d0  pop     r15
0x1800049d2  pop     r14
0x1800049d4  pop     rdi
0x1800049d5  pop     rsi
0x1800049d6  pop     rbp
0x1800049d7  retn
```
