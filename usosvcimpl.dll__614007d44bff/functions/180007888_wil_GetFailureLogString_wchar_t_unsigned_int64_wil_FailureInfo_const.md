# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007888`
- end: `0x180007b3c`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800087a0`
- `0x180009d14`
- `0x18000a294`
- `0x18000a59c`
- `0x180010f60`
- `0x1800e52e9`
- `0x1800e5422`
- `0x1800eb60e`
- `0x1800eba17`

## callees

- `0x18000781c`
- `0x180007888`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a39`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800079b8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800079b8`

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
  v7 = (const char *)&byte_1800F555A;
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
0x180007888  mov     [rsp+arg_18], rbx
0x18000788d  push    rbp
0x18000788e  push    rsi
0x18000788f  push    rdi
0x180007890  push    r14
0x180007892  push    r15
0x180007894  sub     rsp, 250h
0x18000789b  mov     rax, cs:__security_cookie
0x1800078a2  xor     rax, rsp
0x1800078a5  mov     [rsp+278h+var_38], rax
0x1800078ad  mov     rbx, r8
0x1800078b0  mov     rdi, rdx
0x1800078b3  mov     r14, rcx
0x1800078b6  xor     r15d, r15d
0x1800078b9  test    rdx, rdx
0x1800078bc  jz      loc_180007B13
0x1800078c2  test    rcx, rcx
0x1800078c5  jz      loc_180007B13
0x1800078cb  mov     [rcx], r15w
0x1800078cf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800078d6  test    rax, rax
0x1800078d9  jz      short loc_1800078FC
0x1800078db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800078e2  jz      short loc_1800078FC
0x1800078e4  mov     r8, rdx
0x1800078e7  mov     rdx, rcx
0x1800078ea  mov     rcx, rbx
0x1800078ed  call    _guard_dispatch_icall
0x1800078f2  cmp     [r14], r15w
0x1800078f6  jnz     loc_180007B13
0x1800078fc  lea     rsi, byte_1800F555A
0x180007903  mov     ecx, [rbx]
0x180007905  mov     bpl, 8
0x180007908  test    ecx, ecx
0x18000790a  jz      short loc_18000794C
0x18000790c  sub     ecx, 1
0x18000790f  jz      short loc_180007934
0x180007911  sub     ecx, 1
0x180007914  jz      short loc_180007924
0x180007916  cmp     ecx, 1
0x180007919  jnz     short loc_180007953
0x18000791b  lea     rsi, aFailfast; "FailFast"
0x180007922  jmp     short loc_180007953
0x180007924  lea     rax, aLoghr; "LogHr"
0x18000792b  lea     rsi, aLognt; "LogNt"
0x180007932  jmp     short loc_180007942
0x180007934  lea     rax, aReturnhr; "ReturnHr"
0x18000793b  lea     rsi, aReturnnt; "ReturnNt"
0x180007942  test    [rbx+4], bpl
0x180007946  cmovz   rsi, rax
0x18000794a  jmp     short loc_180007953
0x18000794c  lea     rsi, aException; "Exception"
0x180007953  xor     edx, edx; Val
0x180007955  mov     r8d, 200h; Size
0x18000795b  lea     rcx, [rsp+278h+Buffer]; void *
0x180007960  call    memset
0x180007965  test    [rbx+4], bpl
0x180007969  jz      short loc_18000798E
0x18000796b  mov     ebp, [rbx+0Ch]
0x18000796e  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007975  test    rax, rax
0x180007978  jz      short loc_1800079BE
0x18000797a  mov     r8d, 100h
0x180007980  lea     rdx, [rsp+278h+Buffer]
0x180007985  mov     ecx, ebp
0x180007987  call    _guard_dispatch_icall
0x18000798c  jmp     short loc_1800079BE
0x18000798e  mov     ebp, [rbx+8]
0x180007991  mov     [rsp+278h+Arguments], r15; Arguments
0x180007996  mov     [rsp+278h+nSize], 100h; nSize
0x18000799e  lea     rax, [rsp+278h+Buffer]
0x1800079a3  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800079a8  mov     r9d, 400h; dwLanguageId
0x1800079ae  mov     r8d, ebp; dwMessageId
0x1800079b1  xor     edx, edx; lpSource
0x1800079b3  mov     ecx, 1200h; dwFlags
0x1800079b8  call    cs:__imp_FormatMessageW
0x1800079be  lea     rdi, [r14+rdi*2]
0x1800079c2  mov     r9, [rbx+38h]; wchar_t *
0x1800079c6  mov     rax, [rbx+88h]
0x1800079cd  mov     rcx, [rbx+80h]
0x1800079d4  mov     rdx, rdi; wchar_t *
0x1800079d7  test    r9, r9
0x1800079da  jz      short loc_1800079FE
0x1800079dc  mov     [rsp+278h+Arguments], rax
0x1800079e1  mov     qword ptr [rsp+278h+nSize], rcx
0x1800079e6  mov     eax, [rbx+40h]
0x1800079e9  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800079ed  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800079f4  mov     rcx, r14; this
0x1800079f7  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800079fc  jmp     short loc_180007A15
0x1800079fe  mov     [rsp+278h+lpBuffer], rax
0x180007a03  mov     r9, rcx; wchar_t *
0x180007a06  lea     r8, aHsP; "%hs!%p: "
0x180007a0d  mov     rcx, r14; this
0x180007a10  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007a15  mov     r14, rax
0x180007a18  mov     r9, [rbx+90h]; wchar_t *
0x180007a1f  test    r9, r9
0x180007a22  jz      short loc_180007A39
0x180007a24  lea     r8, aCallerP; "(caller: %p) "
0x180007a2b  mov     rdx, rdi; wchar_t *
0x180007a2e  mov     rcx, rax; this
0x180007a31  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007a36  mov     r14, rax
0x180007a39  call    cs:__imp_GetCurrentThreadId
0x180007a3f  lea     rcx, [rsp+278h+Buffer]
0x180007a44  mov     [rsp+278h+var_240], rcx
0x180007a49  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007a4d  mov     [rsp+278h+nSize], eax
0x180007a51  mov     eax, [rbx+44h]
0x180007a54  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007a58  mov     r9, rsi; wchar_t *
0x180007a5b  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007a62  mov     rdx, rdi; wchar_t *
0x180007a65  mov     rcx, r14; this
0x180007a68  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007a6d  cmp     [rbx+18h], r15
0x180007a71  jnz     short loc_180007A83
0x180007a73  cmp     [rbx+48h], r15
0x180007a77  jnz     short loc_180007A83
0x180007a79  cmp     [rbx+30h], r15
0x180007a7d  jz      loc_180007B13
0x180007a83  lea     r8, asc_1800F5648; "    "
0x180007a8a  mov     rdx, rdi; wchar_t *
0x180007a8d  mov     rcx, rax; this
0x180007a90  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007a95  mov     r9, [rbx+18h]; wchar_t *
0x180007a99  test    r9, r9
0x180007a9c  jz      short loc_180007AB0
0x180007a9e  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007aa5  mov     rdx, rdi; wchar_t *
0x180007aa8  mov     rcx, rax; this
0x180007aab  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007ab0  mov     r9, [rbx+48h]; wchar_t *
0x180007ab4  test    r9, r9
0x180007ab7  jz      short loc_180007ACB
0x180007ab9  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007ac0  mov     rdx, rdi; wchar_t *
0x180007ac3  mov     rcx, rax; this
0x180007ac6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007acb  mov     rcx, [rbx+28h]
0x180007acf  mov     r9, [rbx+30h]; wchar_t *
0x180007ad3  mov     rdx, rdi; wchar_t *
0x180007ad6  test    rcx, rcx
0x180007ad9  jz      short loc_180007AF1
0x180007adb  mov     [rsp+278h+lpBuffer], rcx
0x180007ae0  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007ae7  mov     rcx, rax; this
0x180007aea  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007aef  jmp     short loc_180007B13
0x180007af1  mov     rcx, rax; this
0x180007af4  test    r9, r9
0x180007af7  jz      short loc_180007B07
0x180007af9  lea     r8, aHs; "[%hs]\n"
0x180007b00  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007b05  jmp     short loc_180007B13
0x180007b07  lea     r8, asc_1800F56C0; "\n"
0x180007b0e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007b13  xor     eax, eax
0x180007b15  mov     rcx, [rsp+278h+var_38]
0x180007b1d  xor     rcx, rsp; StackCookie
0x180007b20  call    __security_check_cookie
0x180007b25  mov     rbx, [rsp+278h+arg_18]
0x180007b2d  add     rsp, 250h
0x180007b34  pop     r15
0x180007b36  pop     r14
0x180007b38  pop     rdi
0x180007b39  pop     rsi
0x180007b3a  pop     rbp
0x180007b3b  retn
```
