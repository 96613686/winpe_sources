# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800091d4`
- end: `0x180009488`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a0f0`
- `0x18000a5e0`
- `0x18000b960`
- `0x18000bf50`
- `0x180025114`
- `0x180037417`
- `0x180037550`

## callees

- `0x180009168`
- `0x1800091d4`
- `0x18002fda9`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009385`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009304`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009304`

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
  v7 = (const char *)&word_18003C2E2;
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
0x1800091d4  mov     [rsp+arg_18], rbx
0x1800091d9  push    rbp
0x1800091da  push    rsi
0x1800091db  push    rdi
0x1800091dc  push    r14
0x1800091de  push    r15
0x1800091e0  sub     rsp, 250h
0x1800091e7  mov     rax, cs:__security_cookie
0x1800091ee  xor     rax, rsp
0x1800091f1  mov     [rsp+278h+var_38], rax
0x1800091f9  mov     rbx, r8
0x1800091fc  mov     rdi, rdx
0x1800091ff  mov     r14, rcx
0x180009202  xor     r15d, r15d
0x180009205  test    rdx, rdx
0x180009208  jz      loc_18000945F
0x18000920e  test    rcx, rcx
0x180009211  jz      loc_18000945F
0x180009217  mov     [rcx], r15w
0x18000921b  mov     rax, cs:g_pfnResultLoggingCallback
0x180009222  test    rax, rax
0x180009225  jz      short loc_180009248
0x180009227  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000922e  jz      short loc_180009248
0x180009230  mov     r8, rdx
0x180009233  mov     rdx, rcx
0x180009236  mov     rcx, rbx
0x180009239  call    _guard_dispatch_icall
0x18000923e  cmp     [r14], r15w
0x180009242  jnz     loc_18000945F
0x180009248  lea     rsi, word_18003C2E2
0x18000924f  mov     ecx, [rbx]
0x180009251  mov     bpl, 8
0x180009254  test    ecx, ecx
0x180009256  jz      short loc_180009298
0x180009258  sub     ecx, 1
0x18000925b  jz      short loc_180009280
0x18000925d  sub     ecx, 1
0x180009260  jz      short loc_180009270
0x180009262  cmp     ecx, 1
0x180009265  jnz     short loc_18000929F
0x180009267  lea     rsi, aFailfast; "FailFast"
0x18000926e  jmp     short loc_18000929F
0x180009270  lea     rax, aLoghr; "LogHr"
0x180009277  lea     rsi, aLognt; "LogNt"
0x18000927e  jmp     short loc_18000928E
0x180009280  lea     rax, aReturnhr; "ReturnHr"
0x180009287  lea     rsi, aReturnnt; "ReturnNt"
0x18000928e  test    [rbx+4], bpl
0x180009292  cmovz   rsi, rax
0x180009296  jmp     short loc_18000929F
0x180009298  lea     rsi, aException; "Exception"
0x18000929f  xor     edx, edx; Val
0x1800092a1  mov     r8d, 200h; Size
0x1800092a7  lea     rcx, [rsp+278h+Buffer]; void *
0x1800092ac  call    memset_0
0x1800092b1  test    [rbx+4], bpl
0x1800092b5  jz      short loc_1800092DA
0x1800092b7  mov     ebp, [rbx+0Ch]
0x1800092ba  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800092c1  test    rax, rax
0x1800092c4  jz      short loc_18000930A
0x1800092c6  mov     r8d, 100h
0x1800092cc  lea     rdx, [rsp+278h+Buffer]
0x1800092d1  mov     ecx, ebp
0x1800092d3  call    _guard_dispatch_icall
0x1800092d8  jmp     short loc_18000930A
0x1800092da  mov     ebp, [rbx+8]
0x1800092dd  mov     [rsp+278h+Arguments], r15; Arguments
0x1800092e2  mov     [rsp+278h+nSize], 100h; nSize
0x1800092ea  lea     rax, [rsp+278h+Buffer]
0x1800092ef  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800092f4  mov     r9d, 400h; dwLanguageId
0x1800092fa  mov     r8d, ebp; dwMessageId
0x1800092fd  xor     edx, edx; lpSource
0x1800092ff  mov     ecx, 1200h; dwFlags
0x180009304  call    cs:__imp_FormatMessageW
0x18000930a  lea     rdi, [r14+rdi*2]
0x18000930e  mov     r9, [rbx+38h]; wchar_t *
0x180009312  mov     rax, [rbx+88h]
0x180009319  mov     rcx, [rbx+80h]
0x180009320  mov     rdx, rdi; wchar_t *
0x180009323  test    r9, r9
0x180009326  jz      short loc_18000934A
0x180009328  mov     [rsp+278h+Arguments], rax
0x18000932d  mov     qword ptr [rsp+278h+nSize], rcx
0x180009332  mov     eax, [rbx+40h]
0x180009335  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009339  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009340  mov     rcx, r14; this
0x180009343  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009348  jmp     short loc_180009361
0x18000934a  mov     [rsp+278h+lpBuffer], rax
0x18000934f  mov     r9, rcx; wchar_t *
0x180009352  lea     r8, aHsP; "%hs!%p: "
0x180009359  mov     rcx, r14; this
0x18000935c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009361  mov     r14, rax
0x180009364  mov     r9, [rbx+90h]; wchar_t *
0x18000936b  test    r9, r9
0x18000936e  jz      short loc_180009385
0x180009370  lea     r8, aCallerP; "(caller: %p) "
0x180009377  mov     rdx, rdi; wchar_t *
0x18000937a  mov     rcx, rax; this
0x18000937d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009382  mov     r14, rax
0x180009385  call    cs:__imp_GetCurrentThreadId
0x18000938b  lea     rcx, [rsp+278h+Buffer]
0x180009390  mov     [rsp+278h+var_240], rcx
0x180009395  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009399  mov     [rsp+278h+nSize], eax
0x18000939d  mov     eax, [rbx+44h]
0x1800093a0  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800093a4  mov     r9, rsi; wchar_t *
0x1800093a7  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800093ae  mov     rdx, rdi; wchar_t *
0x1800093b1  mov     rcx, r14; this
0x1800093b4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800093b9  cmp     [rbx+18h], r15
0x1800093bd  jnz     short loc_1800093CF
0x1800093bf  cmp     [rbx+48h], r15
0x1800093c3  jnz     short loc_1800093CF
0x1800093c5  cmp     [rbx+30h], r15
0x1800093c9  jz      loc_18000945F
0x1800093cf  lea     r8, asc_18003C3D0; "    "
0x1800093d6  mov     rdx, rdi; wchar_t *
0x1800093d9  mov     rcx, rax; this
0x1800093dc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800093e1  mov     r9, [rbx+18h]; wchar_t *
0x1800093e5  test    r9, r9
0x1800093e8  jz      short loc_1800093FC
0x1800093ea  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800093f1  mov     rdx, rdi; wchar_t *
0x1800093f4  mov     rcx, rax; this
0x1800093f7  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800093fc  mov     r9, [rbx+48h]; wchar_t *
0x180009400  test    r9, r9
0x180009403  jz      short loc_180009417
0x180009405  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000940c  mov     rdx, rdi; wchar_t *
0x18000940f  mov     rcx, rax; this
0x180009412  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009417  mov     rcx, [rbx+28h]
0x18000941b  mov     r9, [rbx+30h]; wchar_t *
0x18000941f  mov     rdx, rdi; wchar_t *
0x180009422  test    rcx, rcx
0x180009425  jz      short loc_18000943D
0x180009427  mov     [rsp+278h+lpBuffer], rcx
0x18000942c  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009433  mov     rcx, rax; this
0x180009436  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000943b  jmp     short loc_18000945F
0x18000943d  mov     rcx, rax; this
0x180009440  test    r9, r9
0x180009443  jz      short loc_180009453
0x180009445  lea     r8, aHs; "[%hs]\n"
0x18000944c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009451  jmp     short loc_18000945F
0x180009453  lea     r8, asc_18003C448; "\n"
0x18000945a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000945f  xor     eax, eax
0x180009461  mov     rcx, [rsp+278h+var_38]
0x180009469  xor     rcx, rsp; StackCookie
0x18000946c  call    __security_check_cookie
0x180009471  mov     rbx, [rsp+278h+arg_18]
0x180009479  add     rsp, 250h
0x180009480  pop     r15
0x180009482  pop     r14
0x180009484  pop     rdi
0x180009485  pop     rsi
0x180009486  pop     rbp
0x180009487  retn
```
