# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002064`
- end: `0x180002318`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002f80`
- `0x180003470`
- `0x180004eac`
- `0x18000549c`
- `0x180038060`
- `0x180049e79`
- `0x180049fb2`

## callees

- `0x180001ff8`
- `0x180002064`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002215`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002194`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002194`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v7 = (const char *)&pszCabPath;
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
0x180002064  mov     [rsp+arg_18], rbx
0x180002069  push    rbp
0x18000206a  push    rsi
0x18000206b  push    rdi
0x18000206c  push    r14
0x18000206e  push    r15
0x180002070  sub     rsp, 250h
0x180002077  mov     rax, cs:__security_cookie
0x18000207e  xor     rax, rsp
0x180002081  mov     [rsp+278h+var_38], rax
0x180002089  mov     rbx, r8
0x18000208c  mov     rdi, rdx
0x18000208f  mov     r14, rcx
0x180002092  xor     r15d, r15d
0x180002095  test    rdx, rdx
0x180002098  jz      loc_1800022EF
0x18000209e  test    rcx, rcx
0x1800020a1  jz      loc_1800022EF
0x1800020a7  mov     [rcx], r15w
0x1800020ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800020b2  test    rax, rax
0x1800020b5  jz      short loc_1800020D8
0x1800020b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800020be  jz      short loc_1800020D8
0x1800020c0  mov     r8, rdx
0x1800020c3  mov     rdx, rcx
0x1800020c6  mov     rcx, rbx
0x1800020c9  call    _guard_dispatch_icall
0x1800020ce  cmp     [r14], r15w
0x1800020d2  jnz     loc_1800022EF
0x1800020d8  lea     rsi, pszCabPath
0x1800020df  mov     ecx, [rbx]
0x1800020e1  mov     bpl, 8
0x1800020e4  test    ecx, ecx
0x1800020e6  jz      short loc_180002128
0x1800020e8  sub     ecx, 1
0x1800020eb  jz      short loc_180002110
0x1800020ed  sub     ecx, 1
0x1800020f0  jz      short loc_180002100
0x1800020f2  cmp     ecx, 1
0x1800020f5  jnz     short loc_18000212F
0x1800020f7  lea     rsi, aFailfast; "FailFast"
0x1800020fe  jmp     short loc_18000212F
0x180002100  lea     rax, aLoghr; "LogHr"
0x180002107  lea     rsi, aLognt; "LogNt"
0x18000210e  jmp     short loc_18000211E
0x180002110  lea     rax, aReturnhr; "ReturnHr"
0x180002117  lea     rsi, aReturnnt; "ReturnNt"
0x18000211e  test    [rbx+4], bpl
0x180002122  cmovz   rsi, rax
0x180002126  jmp     short loc_18000212F
0x180002128  lea     rsi, aException; "Exception"
0x18000212f  xor     edx, edx; Val
0x180002131  mov     r8d, 200h; Size
0x180002137  lea     rcx, [rsp+278h+Buffer]; void *
0x18000213c  call    memset
0x180002141  test    [rbx+4], bpl
0x180002145  jz      short loc_18000216A
0x180002147  mov     ebp, [rbx+0Ch]
0x18000214a  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180002151  test    rax, rax
0x180002154  jz      short loc_18000219A
0x180002156  mov     r8d, 100h
0x18000215c  lea     rdx, [rsp+278h+Buffer]
0x180002161  mov     ecx, ebp
0x180002163  call    _guard_dispatch_icall
0x180002168  jmp     short loc_18000219A
0x18000216a  mov     ebp, [rbx+8]
0x18000216d  mov     [rsp+278h+Arguments], r15; Arguments
0x180002172  mov     [rsp+278h+nSize], 100h; nSize
0x18000217a  lea     rax, [rsp+278h+Buffer]
0x18000217f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002184  mov     r9d, 400h; dwLanguageId
0x18000218a  mov     r8d, ebp; dwMessageId
0x18000218d  xor     edx, edx; lpSource
0x18000218f  mov     ecx, 1200h; dwFlags
0x180002194  call    cs:__imp_FormatMessageW
0x18000219a  lea     rdi, [r14+rdi*2]
0x18000219e  mov     r9, [rbx+38h]; wchar_t *
0x1800021a2  mov     rax, [rbx+88h]
0x1800021a9  mov     rcx, [rbx+80h]
0x1800021b0  mov     rdx, rdi; wchar_t *
0x1800021b3  test    r9, r9
0x1800021b6  jz      short loc_1800021DA
0x1800021b8  mov     [rsp+278h+Arguments], rax
0x1800021bd  mov     qword ptr [rsp+278h+nSize], rcx
0x1800021c2  mov     eax, [rbx+40h]
0x1800021c5  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800021c9  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800021d0  mov     rcx, r14; this
0x1800021d3  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800021d8  jmp     short loc_1800021F1
0x1800021da  mov     [rsp+278h+lpBuffer], rax
0x1800021df  mov     r9, rcx; wchar_t *
0x1800021e2  lea     r8, aHsP; "%hs!%p: "
0x1800021e9  mov     rcx, r14; this
0x1800021ec  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800021f1  mov     r14, rax
0x1800021f4  mov     r9, [rbx+90h]; wchar_t *
0x1800021fb  test    r9, r9
0x1800021fe  jz      short loc_180002215
0x180002200  lea     r8, aCallerP; "(caller: %p) "
0x180002207  mov     rdx, rdi; wchar_t *
0x18000220a  mov     rcx, rax; this
0x18000220d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002212  mov     r14, rax
0x180002215  call    cs:__imp_GetCurrentThreadId
0x18000221b  lea     rcx, [rsp+278h+Buffer]
0x180002220  mov     [rsp+278h+var_240], rcx
0x180002225  mov     dword ptr [rsp+278h+Arguments], ebp
0x180002229  mov     [rsp+278h+nSize], eax
0x18000222d  mov     eax, [rbx+44h]
0x180002230  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002234  mov     r9, rsi; wchar_t *
0x180002237  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000223e  mov     rdx, rdi; wchar_t *
0x180002241  mov     rcx, r14; this
0x180002244  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002249  cmp     [rbx+18h], r15
0x18000224d  jnz     short loc_18000225F
0x18000224f  cmp     [rbx+48h], r15
0x180002253  jnz     short loc_18000225F
0x180002255  cmp     [rbx+30h], r15
0x180002259  jz      loc_1800022EF
0x18000225f  lea     r8, asc_18004D858; "    "
0x180002266  mov     rdx, rdi; wchar_t *
0x180002269  mov     rcx, rax; this
0x18000226c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002271  mov     r9, [rbx+18h]; wchar_t *
0x180002275  test    r9, r9
0x180002278  jz      short loc_18000228C
0x18000227a  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002281  mov     rdx, rdi; wchar_t *
0x180002284  mov     rcx, rax; this
0x180002287  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000228c  mov     r9, [rbx+48h]; wchar_t *
0x180002290  test    r9, r9
0x180002293  jz      short loc_1800022A7
0x180002295  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000229c  mov     rdx, rdi; wchar_t *
0x18000229f  mov     rcx, rax; this
0x1800022a2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022a7  mov     rcx, [rbx+28h]
0x1800022ab  mov     r9, [rbx+30h]; wchar_t *
0x1800022af  mov     rdx, rdi; wchar_t *
0x1800022b2  test    rcx, rcx
0x1800022b5  jz      short loc_1800022CD
0x1800022b7  mov     [rsp+278h+lpBuffer], rcx
0x1800022bc  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800022c3  mov     rcx, rax; this
0x1800022c6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022cb  jmp     short loc_1800022EF
0x1800022cd  mov     rcx, rax; this
0x1800022d0  test    r9, r9
0x1800022d3  jz      short loc_1800022E3
0x1800022d5  lea     r8, aHs; "[%hs]\n"
0x1800022dc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022e1  jmp     short loc_1800022EF
0x1800022e3  lea     r8, asc_18004D8D0; "\n"
0x1800022ea  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022ef  xor     eax, eax
0x1800022f1  mov     rcx, [rsp+278h+var_38]
0x1800022f9  xor     rcx, rsp; StackCookie
0x1800022fc  call    __security_check_cookie
0x180002301  mov     rbx, [rsp+278h+arg_18]
0x180002309  add     rsp, 250h
0x180002310  pop     r15
0x180002312  pop     r14
0x180002314  pop     rdi
0x180002315  pop     rsi
0x180002316  pop     rbp
0x180002317  retn
```
