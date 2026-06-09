# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002058`
- end: `0x180002326`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `718`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001d9c`

## callees

- `0x180001400`
- `0x180001ca2`
- `0x180002058`
- `0x1800024f0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000221c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000221c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002195`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002195`

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
0x180002058  mov     rax, rsp
0x18000205b  push    rbp
0x18000205c  push    rsi
0x18000205d  push    rdi
0x18000205e  push    r14
0x180002060  push    r15
0x180002062  sub     rsp, 260h
0x180002069  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x180002072  mov     [rax+20h], rbx
0x180002076  mov     rax, cs:__security_cookie
0x18000207d  xor     rax, rsp
0x180002080  mov     [rsp+288h+var_38], rax
0x180002088  mov     rbx, r8
0x18000208b  mov     rsi, rdx
0x18000208e  mov     r14, rcx
0x180002091  xor     r15d, r15d
0x180002094  test    rdx, rdx
0x180002097  jz      loc_1800022FC
0x18000209d  test    rcx, rcx
0x1800020a0  jz      loc_1800022FC
0x1800020a6  mov     [rcx], r15w
0x1800020aa  mov     rax, cs:g_pfnResultLoggingCallback
0x1800020b1  test    rax, rax
0x1800020b4  jz      short loc_1800020D7
0x1800020b6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800020bd  jz      short loc_1800020D7
0x1800020bf  mov     r8, rdx
0x1800020c2  mov     rdx, rcx
0x1800020c5  mov     rcx, rbx
0x1800020c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cd  cmp     [r14], r15w
0x1800020d1  jnz     loc_1800022FC
0x1800020d7  mov     ecx, [rbx]
0x1800020d9  mov     bpl, 8
0x1800020dc  test    ecx, ecx
0x1800020de  jz      short loc_180002129
0x1800020e0  sub     ecx, 1
0x1800020e3  jz      short loc_180002111
0x1800020e5  sub     ecx, 1
0x1800020e8  jz      short loc_180002101
0x1800020ea  cmp     ecx, 1
0x1800020ed  jz      short loc_1800020F8
0x1800020ef  lea     rdi, qword_180006D10
0x1800020f6  jmp     short loc_180002130
0x1800020f8  lea     rdi, aFailfast; "FailFast"
0x1800020ff  jmp     short loc_180002130
0x180002101  lea     rax, aLoghr; "LogHr"
0x180002108  lea     rdi, aLognt; "LogNt"
0x18000210f  jmp     short loc_18000211F
0x180002111  lea     rax, aReturnhr; "ReturnHr"
0x180002118  lea     rdi, aReturnnt; "ReturnNt"
0x18000211f  test    [rbx+4], bpl
0x180002123  cmovz   rdi, rax
0x180002127  jmp     short loc_180002130
0x180002129  lea     rdi, aException; "Exception"
0x180002130  xor     edx, edx; Val
0x180002132  mov     r8d, 200h; Size
0x180002138  lea     rcx, [rsp+288h+Buffer]; void *
0x18000213d  call    memset_0
0x180002142  test    [rbx+4], bpl
0x180002146  jz      short loc_18000216B
0x180002148  mov     ebp, [rbx+0Ch]
0x18000214b  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180002152  test    rax, rax
0x180002155  jz      short loc_1800021A1
0x180002157  mov     r8d, 100h
0x18000215d  lea     rdx, [rsp+288h+Buffer]
0x180002162  mov     ecx, ebp
0x180002164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002169  jmp     short loc_1800021A1
0x18000216b  mov     ebp, [rbx+8]
0x18000216e  mov     [rsp+288h+Arguments], r15; Arguments
0x180002173  mov     [rsp+288h+nSize], 100h; nSize
0x18000217b  lea     rax, [rsp+288h+Buffer]
0x180002180  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180002185  mov     r9d, 400h; dwLanguageId
0x18000218b  mov     r8d, ebp; dwMessageId
0x18000218e  xor     edx, edx; lpSource
0x180002190  mov     ecx, 1200h; dwFlags
0x180002195  call    cs:__imp_FormatMessageW
0x18000219c  nop     dword ptr [rax+rax+00h]
0x1800021a1  lea     rsi, [r14+rsi*2]
0x1800021a5  mov     r9, [rbx+38h]; wchar_t *
0x1800021a9  mov     rax, [rbx+88h]
0x1800021b0  mov     rcx, [rbx+80h]
0x1800021b7  mov     rdx, rsi; wchar_t *
0x1800021ba  test    r9, r9
0x1800021bd  jz      short loc_1800021E1
0x1800021bf  mov     [rsp+288h+Arguments], rax
0x1800021c4  mov     qword ptr [rsp+288h+nSize], rcx
0x1800021c9  mov     eax, [rbx+40h]
0x1800021cc  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800021d0  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800021d7  mov     rcx, r14; this
0x1800021da  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800021df  jmp     short loc_1800021F8
0x1800021e1  mov     [rsp+288h+lpBuffer], rax
0x1800021e6  mov     r9, rcx; wchar_t *
0x1800021e9  lea     r8, aHsP; "%hs!%p: "
0x1800021f0  mov     rcx, r14; this
0x1800021f3  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800021f8  mov     r14, rax
0x1800021fb  mov     r9, [rbx+90h]; wchar_t *
0x180002202  test    r9, r9
0x180002205  jz      short loc_18000221C
0x180002207  lea     r8, aCallerP; "(caller: %p) "
0x18000220e  mov     rdx, rsi; wchar_t *
0x180002211  mov     rcx, rax; this
0x180002214  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002219  mov     r14, rax
0x18000221c  call    cs:__imp_GetCurrentThreadId
0x180002223  nop     dword ptr [rax+rax+00h]
0x180002228  lea     rcx, [rsp+288h+Buffer]
0x18000222d  mov     [rsp+288h+var_250], rcx
0x180002232  mov     dword ptr [rsp+288h+Arguments], ebp
0x180002236  mov     [rsp+288h+nSize], eax
0x18000223a  mov     eax, [rbx+44h]
0x18000223d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180002241  mov     r9, rdi; wchar_t *
0x180002244  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000224b  mov     rdx, rsi; wchar_t *
0x18000224e  mov     rcx, r14; this
0x180002251  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002256  cmp     [rbx+18h], r15
0x18000225a  jnz     short loc_18000226C
0x18000225c  cmp     [rbx+48h], r15
0x180002260  jnz     short loc_18000226C
0x180002262  cmp     [rbx+30h], r15
0x180002266  jz      loc_1800022FC
0x18000226c  lea     r8, asc_180006E00; "    "
0x180002273  mov     rdx, rsi; wchar_t *
0x180002276  mov     rcx, rax; this
0x180002279  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000227e  mov     r9, [rbx+18h]; wchar_t *
0x180002282  test    r9, r9
0x180002285  jz      short loc_180002299
0x180002287  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000228e  mov     rdx, rsi; wchar_t *
0x180002291  mov     rcx, rax; this
0x180002294  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002299  mov     r9, [rbx+48h]; wchar_t *
0x18000229d  test    r9, r9
0x1800022a0  jz      short loc_1800022B4
0x1800022a2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800022a9  mov     rdx, rsi; wchar_t *
0x1800022ac  mov     rcx, rax; this
0x1800022af  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022b4  mov     rcx, [rbx+28h]
0x1800022b8  mov     r9, [rbx+30h]; wchar_t *
0x1800022bc  mov     rdx, rsi; wchar_t *
0x1800022bf  test    rcx, rcx
0x1800022c2  jz      short loc_1800022DA
0x1800022c4  mov     [rsp+288h+lpBuffer], rcx
0x1800022c9  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800022d0  mov     rcx, rax; this
0x1800022d3  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022d8  jmp     short loc_1800022FC
0x1800022da  mov     rcx, rax; this
0x1800022dd  test    r9, r9
0x1800022e0  jz      short loc_1800022F0
0x1800022e2  lea     r8, aHs; "[%hs]\n"
0x1800022e9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022ee  jmp     short loc_1800022FC
0x1800022f0  lea     r8, asc_180006E78; "\n"
0x1800022f7  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800022fc  xor     eax, eax
0x1800022fe  mov     rcx, [rsp+288h+var_38]
0x180002306  xor     rcx, rsp; StackCookie
0x180002309  call    __security_check_cookie
0x18000230e  mov     rbx, [rsp+288h+arg_18]
0x180002316  add     rsp, 260h
0x18000231d  pop     r15
0x18000231f  pop     r14
0x180002321  pop     rdi
0x180002322  pop     rsi
0x180002323  pop     rbp
0x180002324  retn
```
