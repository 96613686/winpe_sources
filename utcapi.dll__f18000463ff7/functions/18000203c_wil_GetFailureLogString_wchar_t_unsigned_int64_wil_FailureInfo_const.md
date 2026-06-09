# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000203c`
- end: `0x1800022fd`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001d94`

## callees

- `0x180001400`
- `0x180001ca2`
- `0x18000203c`
- `0x1800024c8`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800021fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800021fa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002179`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002179`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&qword_180006D10;
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
                          Buffer,
                          -2);
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
0x18000203c  mov     rax, rsp
0x18000203f  push    rbp
0x180002040  push    rsi
0x180002041  push    rdi
0x180002042  push    r14
0x180002044  push    r15
0x180002046  sub     rsp, 260h
0x18000204d  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x180002056  mov     [rax+20h], rbx
0x18000205a  mov     rax, cs:__security_cookie
0x180002061  xor     rax, rsp
0x180002064  mov     [rsp+288h+var_38], rax
0x18000206c  mov     rbx, r8
0x18000206f  mov     rsi, rdx
0x180002072  mov     r14, rcx
0x180002075  xor     r15d, r15d
0x180002078  test    rdx, rdx
0x18000207b  jz      loc_1800022D4
0x180002081  test    rcx, rcx
0x180002084  jz      loc_1800022D4
0x18000208a  mov     [rcx], r15w
0x18000208e  mov     rax, cs:g_pfnResultLoggingCallback
0x180002095  test    rax, rax
0x180002098  jz      short loc_1800020BB
0x18000209a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800020a1  jz      short loc_1800020BB
0x1800020a3  mov     r8, rdx
0x1800020a6  mov     rdx, rcx
0x1800020a9  mov     rcx, rbx
0x1800020ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020b1  cmp     [r14], r15w
0x1800020b5  jnz     loc_1800022D4
0x1800020bb  mov     ecx, [rbx]
0x1800020bd  mov     bpl, 8
0x1800020c0  test    ecx, ecx
0x1800020c2  jz      short loc_18000210D
0x1800020c4  sub     ecx, 1
0x1800020c7  jz      short loc_1800020F5
0x1800020c9  sub     ecx, 1
0x1800020cc  jz      short loc_1800020E5
0x1800020ce  cmp     ecx, 1
0x1800020d1  jz      short loc_1800020DC
0x1800020d3  lea     rdi, qword_180006D10
0x1800020da  jmp     short loc_180002114
0x1800020dc  lea     rdi, aFailfast; "FailFast"
0x1800020e3  jmp     short loc_180002114
0x1800020e5  lea     rax, aLoghr; "LogHr"
0x1800020ec  lea     rdi, aLognt; "LogNt"
0x1800020f3  jmp     short loc_180002103
0x1800020f5  lea     rax, aReturnhr; "ReturnHr"
0x1800020fc  lea     rdi, aReturnnt; "ReturnNt"
0x180002103  test    [rbx+4], bpl
0x180002107  cmovz   rdi, rax
0x18000210b  jmp     short loc_180002114
0x18000210d  lea     rdi, aException; "Exception"
0x180002114  xor     edx, edx; Val
0x180002116  mov     r8d, 200h; Size
0x18000211c  lea     rcx, [rsp+288h+Buffer]; void *
0x180002121  call    memset_0
0x180002126  test    [rbx+4], bpl
0x18000212a  jz      short loc_18000214F
0x18000212c  mov     ebp, [rbx+0Ch]
0x18000212f  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180002136  test    rax, rax
0x180002139  jz      short loc_18000217F
0x18000213b  mov     r8d, 100h
0x180002141  lea     rdx, [rsp+288h+Buffer]
0x180002146  mov     ecx, ebp
0x180002148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000214d  jmp     short loc_18000217F
0x18000214f  mov     ebp, [rbx+8]
0x180002152  mov     [rsp+288h+Arguments], r15; Arguments
0x180002157  mov     [rsp+288h+nSize], 100h; nSize
0x18000215f  lea     rax, [rsp+288h+Buffer]
0x180002164  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180002169  mov     r9d, 400h; dwLanguageId
0x18000216f  mov     r8d, ebp; dwMessageId
0x180002172  xor     edx, edx; lpSource
0x180002174  mov     ecx, 1200h; dwFlags
0x180002179  call    cs:__imp_FormatMessageW
0x18000217f  lea     rsi, [r14+rsi*2]
0x180002183  mov     r9, [rbx+38h]; wchar_t *
0x180002187  mov     rax, [rbx+88h]
0x18000218e  mov     rcx, [rbx+80h]
0x180002195  mov     rdx, rsi; wchar_t *
0x180002198  test    r9, r9
0x18000219b  jz      short loc_1800021BF
0x18000219d  mov     [rsp+288h+Arguments], rax
0x1800021a2  mov     qword ptr [rsp+288h+nSize], rcx
0x1800021a7  mov     eax, [rbx+40h]
0x1800021aa  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800021ae  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800021b5  mov     rcx, r14; this
0x1800021b8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800021bd  jmp     short loc_1800021D6
0x1800021bf  mov     [rsp+288h+lpBuffer], rax
0x1800021c4  mov     r9, rcx; wchar_t *
0x1800021c7  lea     r8, aHsP; "%hs!%p: "
0x1800021ce  mov     rcx, r14; this
0x1800021d1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800021d6  mov     r14, rax
0x1800021d9  mov     r9, [rbx+90h]; wchar_t *
0x1800021e0  test    r9, r9
0x1800021e3  jz      short loc_1800021FA
0x1800021e5  lea     r8, aCallerP; "(caller: %p) "
0x1800021ec  mov     rdx, rsi; wchar_t *
0x1800021ef  mov     rcx, rax; this
0x1800021f2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800021f7  mov     r14, rax
0x1800021fa  call    cs:__imp_GetCurrentThreadId
0x180002200  lea     rcx, [rsp+288h+Buffer]
0x180002205  mov     [rsp+288h+var_250], rcx
0x18000220a  mov     dword ptr [rsp+288h+Arguments], ebp
0x18000220e  mov     [rsp+288h+nSize], eax
0x180002212  mov     eax, [rbx+44h]
0x180002215  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180002219  mov     r9, rdi; wchar_t *
0x18000221c  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002223  mov     rdx, rsi; wchar_t *
0x180002226  mov     rcx, r14; this
0x180002229  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000222e  cmp     [rbx+18h], r15
0x180002232  jnz     short loc_180002244
0x180002234  cmp     [rbx+48h], r15
0x180002238  jnz     short loc_180002244
0x18000223a  cmp     [rbx+30h], r15
0x18000223e  jz      loc_1800022D4
0x180002244  lea     r8, asc_180006E00; "    "
0x18000224b  mov     rdx, rsi; wchar_t *
0x18000224e  mov     rcx, rax; this
0x180002251  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002256  mov     r9, [rbx+18h]; wchar_t *
0x18000225a  test    r9, r9
0x18000225d  jz      short loc_180002271
0x18000225f  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002266  mov     rdx, rsi; wchar_t *
0x180002269  mov     rcx, rax; this
0x18000226c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002271  mov     r9, [rbx+48h]; wchar_t *
0x180002275  test    r9, r9
0x180002278  jz      short loc_18000228C
0x18000227a  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180002281  mov     rdx, rsi; wchar_t *
0x180002284  mov     rcx, rax; this
0x180002287  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000228c  mov     rcx, [rbx+28h]
0x180002290  mov     r9, [rbx+30h]; wchar_t *
0x180002294  mov     rdx, rsi; wchar_t *
0x180002297  test    rcx, rcx
0x18000229a  jz      short loc_1800022B2
0x18000229c  mov     [rsp+288h+lpBuffer], rcx
0x1800022a1  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800022a8  mov     rcx, rax; this
0x1800022ab  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022b0  jmp     short loc_1800022D4
0x1800022b2  mov     rcx, rax; this
0x1800022b5  test    r9, r9
0x1800022b8  jz      short loc_1800022C8
0x1800022ba  lea     r8, aHs; "[%hs]\n"
0x1800022c1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022c6  jmp     short loc_1800022D4
0x1800022c8  lea     r8, asc_180006E78; "\n"
0x1800022cf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022d4  xor     eax, eax
0x1800022d6  mov     rcx, [rsp+288h+var_38]
0x1800022de  xor     rcx, rsp; StackCookie
0x1800022e1  call    __security_check_cookie
0x1800022e6  mov     rbx, [rsp+288h+arg_18]
0x1800022ee  add     rsp, 260h
0x1800022f5  pop     r15
0x1800022f7  pop     r14
0x1800022f9  pop     rdi
0x1800022fa  pop     rsi
0x1800022fb  pop     rbp
0x1800022fc  retn
```
