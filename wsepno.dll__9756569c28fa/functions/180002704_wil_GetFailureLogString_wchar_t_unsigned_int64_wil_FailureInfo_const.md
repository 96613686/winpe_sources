# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002704`
- end: `0x1800029ba`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180003900`
- `0x1800043b8`
- `0x180004638`
- `0x180007a28`
- `0x18000d9a1`
- `0x18000dad5`
- `0x18000dddc`
- `0x18000e222`

## callees

- `0x180001770`
- `0x1800021f4`
- `0x180002704`
- `0x180002cb0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002836`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002836`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
      if ( *(_WORD *)this )
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
          v7 = (const char *)&qword_180010B00;
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
0x180002704  mov     [rsp+arg_18], rbx
0x180002709  push    rbp
0x18000270a  push    rsi
0x18000270b  push    rdi
0x18000270c  push    r14
0x18000270e  push    r15
0x180002710  sub     rsp, 250h
0x180002717  mov     rax, cs:__security_cookie
0x18000271e  xor     rax, rsp
0x180002721  mov     [rsp+278h+var_38], rax
0x180002729  mov     rbx, r8
0x18000272c  mov     rsi, rdx
0x18000272f  mov     r14, rcx
0x180002732  xor     r15d, r15d
0x180002735  test    rdx, rdx
0x180002738  jz      loc_180002991
0x18000273e  test    rcx, rcx
0x180002741  jz      loc_180002991
0x180002747  mov     [rcx], r15w
0x18000274b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002752  test    rax, rax
0x180002755  jz      short loc_180002778
0x180002757  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000275e  jz      short loc_180002778
0x180002760  mov     r8, rdx
0x180002763  mov     rdx, rcx
0x180002766  mov     rcx, rbx
0x180002769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276e  cmp     [r14], r15w
0x180002772  jnz     loc_180002991
0x180002778  mov     ecx, [rbx]
0x18000277a  mov     bpl, 8
0x18000277d  test    ecx, ecx
0x18000277f  jz      short loc_1800027CA
0x180002781  sub     ecx, 1
0x180002784  jz      short loc_1800027B2
0x180002786  sub     ecx, 1
0x180002789  jz      short loc_1800027A2
0x18000278b  cmp     ecx, 1
0x18000278e  jz      short loc_180002799
0x180002790  lea     rdi, qword_180010B00
0x180002797  jmp     short loc_1800027D1
0x180002799  lea     rdi, aFailfast; "FailFast"
0x1800027a0  jmp     short loc_1800027D1
0x1800027a2  lea     rax, aLoghr; "LogHr"
0x1800027a9  lea     rdi, aLognt; "LogNt"
0x1800027b0  jmp     short loc_1800027C0
0x1800027b2  lea     rax, aReturnhr; "ReturnHr"
0x1800027b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800027c0  test    [rbx+4], bpl
0x1800027c4  cmovz   rdi, rax
0x1800027c8  jmp     short loc_1800027D1
0x1800027ca  lea     rdi, aException; "Exception"
0x1800027d1  xor     edx, edx; Val
0x1800027d3  mov     r8d, 200h; Size
0x1800027d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800027de  call    memset_0
0x1800027e3  test    [rbx+4], bpl
0x1800027e7  jz      short loc_18000280C
0x1800027e9  mov     ebp, [rbx+0Ch]
0x1800027ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800027f3  test    rax, rax
0x1800027f6  jz      short loc_18000283C
0x1800027f8  mov     r8d, 100h
0x1800027fe  lea     rdx, [rsp+278h+Buffer]
0x180002803  mov     ecx, ebp
0x180002805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280a  jmp     short loc_18000283C
0x18000280c  mov     ebp, [rbx+8]
0x18000280f  mov     [rsp+278h+Arguments], r15; Arguments
0x180002814  mov     [rsp+278h+nSize], 100h; nSize
0x18000281c  lea     rax, [rsp+278h+Buffer]
0x180002821  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002826  mov     r9d, 400h; dwLanguageId
0x18000282c  mov     r8d, ebp; dwMessageId
0x18000282f  xor     edx, edx; lpSource
0x180002831  mov     ecx, 1200h; dwFlags
0x180002836  call    cs:__imp_FormatMessageW
0x18000283c  lea     rsi, [r14+rsi*2]
0x180002840  mov     r9, [rbx+38h]; wchar_t *
0x180002844  mov     rax, [rbx+88h]
0x18000284b  mov     rcx, [rbx+80h]
0x180002852  mov     rdx, rsi; wchar_t *
0x180002855  test    r9, r9
0x180002858  jz      short loc_18000287C
0x18000285a  mov     [rsp+278h+Arguments], rax
0x18000285f  mov     qword ptr [rsp+278h+nSize], rcx
0x180002864  mov     eax, [rbx+40h]
0x180002867  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000286b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180002872  mov     rcx, r14; this
0x180002875  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000287a  jmp     short loc_180002893
0x18000287c  mov     [rsp+278h+lpBuffer], rax
0x180002881  mov     r9, rcx; wchar_t *
0x180002884  lea     r8, aHsP; "%hs!%p: "
0x18000288b  mov     rcx, r14; this
0x18000288e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002893  mov     r14, rax
0x180002896  mov     r9, [rbx+90h]; wchar_t *
0x18000289d  test    r9, r9
0x1800028a0  jz      short loc_1800028B7
0x1800028a2  lea     r8, aCallerP; "(caller: %p) "
0x1800028a9  mov     rdx, rsi; wchar_t *
0x1800028ac  mov     rcx, rax; this
0x1800028af  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800028b4  mov     r14, rax
0x1800028b7  call    cs:__imp_GetCurrentThreadId
0x1800028bd  lea     rcx, [rsp+278h+Buffer]
0x1800028c2  mov     [rsp+278h+var_240], rcx
0x1800028c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800028cb  mov     [rsp+278h+nSize], eax
0x1800028cf  mov     eax, [rbx+44h]
0x1800028d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800028d6  mov     r9, rdi; wchar_t *
0x1800028d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800028e0  mov     rdx, rsi; wchar_t *
0x1800028e3  mov     rcx, r14; this
0x1800028e6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800028eb  cmp     [rbx+18h], r15
0x1800028ef  jnz     short loc_180002901
0x1800028f1  cmp     [rbx+48h], r15
0x1800028f5  jnz     short loc_180002901
0x1800028f7  cmp     [rbx+30h], r15
0x1800028fb  jz      loc_180002991
0x180002901  lea     r8, asc_180010C08; "    "
0x180002908  mov     rdx, rsi; wchar_t *
0x18000290b  mov     rcx, rax; this
0x18000290e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002913  mov     r9, [rbx+18h]; wchar_t *
0x180002917  test    r9, r9
0x18000291a  jz      short loc_18000292E
0x18000291c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002923  mov     rdx, rsi; wchar_t *
0x180002926  mov     rcx, rax; this
0x180002929  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000292e  mov     r9, [rbx+48h]; wchar_t *
0x180002932  test    r9, r9
0x180002935  jz      short loc_180002949
0x180002937  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000293e  mov     rdx, rsi; wchar_t *
0x180002941  mov     rcx, rax; this
0x180002944  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002949  mov     rcx, [rbx+28h]
0x18000294d  mov     r9, [rbx+30h]; wchar_t *
0x180002951  mov     rdx, rsi; wchar_t *
0x180002954  test    rcx, rcx
0x180002957  jz      short loc_18000296F
0x180002959  mov     [rsp+278h+lpBuffer], rcx
0x18000295e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180002965  mov     rcx, rax; this
0x180002968  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000296d  jmp     short loc_180002991
0x18000296f  mov     rcx, rax; this
0x180002972  test    r9, r9
0x180002975  jz      short loc_180002985
0x180002977  lea     r8, aHs; "[%hs]\n"
0x18000297e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002983  jmp     short loc_180002991
0x180002985  lea     r8, asc_180010C80; "\n"
0x18000298c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002991  xor     eax, eax
0x180002993  mov     rcx, [rsp+278h+var_38]
0x18000299b  xor     rcx, rsp; StackCookie
0x18000299e  call    __security_check_cookie
0x1800029a3  mov     rbx, [rsp+278h+arg_18]
0x1800029ab  add     rsp, 250h
0x1800029b2  pop     r15
0x1800029b4  pop     r14
0x1800029b6  pop     rdi
0x1800029b7  pop     rsi
0x1800029b8  pop     rbp
0x1800029b9  retn
```
