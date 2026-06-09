# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007e34`
- end: `0x1800080ea`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003360`
- `0x1800035e0`
- `0x180003894`
- `0x18000923c`
- `0x18000ddf0`
- `0x180015141`
- `0x180015275`
- `0x180015727`
- `0x180015b6d`

## callees

- `0x1800020e0`
- `0x180002b38`
- `0x180007e34`
- `0x18000953c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fe7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fe7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007f66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007f66`

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
          v7 = (const char *)&word_1800194F2;
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
0x180007e34  mov     [rsp+arg_18], rbx
0x180007e39  push    rbp
0x180007e3a  push    rsi
0x180007e3b  push    rdi
0x180007e3c  push    r14
0x180007e3e  push    r15
0x180007e40  sub     rsp, 250h
0x180007e47  mov     rax, cs:__security_cookie
0x180007e4e  xor     rax, rsp
0x180007e51  mov     [rsp+278h+var_38], rax
0x180007e59  mov     rbx, r8
0x180007e5c  mov     rsi, rdx
0x180007e5f  mov     r14, rcx
0x180007e62  xor     r15d, r15d
0x180007e65  test    rdx, rdx
0x180007e68  jz      loc_1800080C1
0x180007e6e  test    rcx, rcx
0x180007e71  jz      loc_1800080C1
0x180007e77  mov     [rcx], r15w
0x180007e7b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e82  test    rax, rax
0x180007e85  jz      short loc_180007EA8
0x180007e87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007e8e  jz      short loc_180007EA8
0x180007e90  mov     r8, rdx
0x180007e93  mov     rdx, rcx
0x180007e96  mov     rcx, rbx
0x180007e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e9e  cmp     [r14], r15w
0x180007ea2  jnz     loc_1800080C1
0x180007ea8  mov     ecx, [rbx]
0x180007eaa  mov     bpl, 8
0x180007ead  test    ecx, ecx
0x180007eaf  jz      short loc_180007EFA
0x180007eb1  sub     ecx, 1
0x180007eb4  jz      short loc_180007EE2
0x180007eb6  sub     ecx, 1
0x180007eb9  jz      short loc_180007ED2
0x180007ebb  cmp     ecx, 1
0x180007ebe  jz      short loc_180007EC9
0x180007ec0  lea     rdi, word_1800194F2
0x180007ec7  jmp     short loc_180007F01
0x180007ec9  lea     rdi, aFailfast; "FailFast"
0x180007ed0  jmp     short loc_180007F01
0x180007ed2  lea     rax, aLoghr; "LogHr"
0x180007ed9  lea     rdi, aLognt; "LogNt"
0x180007ee0  jmp     short loc_180007EF0
0x180007ee2  lea     rax, aReturnhr; "ReturnHr"
0x180007ee9  lea     rdi, aReturnnt; "ReturnNt"
0x180007ef0  test    [rbx+4], bpl
0x180007ef4  cmovz   rdi, rax
0x180007ef8  jmp     short loc_180007F01
0x180007efa  lea     rdi, aException; "Exception"
0x180007f01  xor     edx, edx; Val
0x180007f03  mov     r8d, 200h; Size
0x180007f09  lea     rcx, [rsp+278h+Buffer]; void *
0x180007f0e  call    memset_0
0x180007f13  test    [rbx+4], bpl
0x180007f17  jz      short loc_180007F3C
0x180007f19  mov     ebp, [rbx+0Ch]
0x180007f1c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007f23  test    rax, rax
0x180007f26  jz      short loc_180007F6C
0x180007f28  mov     r8d, 100h
0x180007f2e  lea     rdx, [rsp+278h+Buffer]
0x180007f33  mov     ecx, ebp
0x180007f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f3a  jmp     short loc_180007F6C
0x180007f3c  mov     ebp, [rbx+8]
0x180007f3f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007f44  mov     [rsp+278h+nSize], 100h; nSize
0x180007f4c  lea     rax, [rsp+278h+Buffer]
0x180007f51  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007f56  mov     r9d, 400h; dwLanguageId
0x180007f5c  mov     r8d, ebp; dwMessageId
0x180007f5f  xor     edx, edx; lpSource
0x180007f61  mov     ecx, 1200h; dwFlags
0x180007f66  call    cs:__imp_FormatMessageW
0x180007f6c  lea     rsi, [r14+rsi*2]
0x180007f70  mov     r9, [rbx+38h]; wchar_t *
0x180007f74  mov     rax, [rbx+88h]
0x180007f7b  mov     rcx, [rbx+80h]
0x180007f82  mov     rdx, rsi; wchar_t *
0x180007f85  test    r9, r9
0x180007f88  jz      short loc_180007FAC
0x180007f8a  mov     [rsp+278h+Arguments], rax
0x180007f8f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007f94  mov     eax, [rbx+40h]
0x180007f97  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007f9b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007fa2  mov     rcx, r14; this
0x180007fa5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007faa  jmp     short loc_180007FC3
0x180007fac  mov     [rsp+278h+lpBuffer], rax
0x180007fb1  mov     r9, rcx; wchar_t *
0x180007fb4  lea     r8, aHsP; "%hs!%p: "
0x180007fbb  mov     rcx, r14; this
0x180007fbe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007fc3  mov     r14, rax
0x180007fc6  mov     r9, [rbx+90h]; wchar_t *
0x180007fcd  test    r9, r9
0x180007fd0  jz      short loc_180007FE7
0x180007fd2  lea     r8, aCallerP; "(caller: %p) "
0x180007fd9  mov     rdx, rsi; wchar_t *
0x180007fdc  mov     rcx, rax; this
0x180007fdf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007fe4  mov     r14, rax
0x180007fe7  call    cs:__imp_GetCurrentThreadId
0x180007fed  lea     rcx, [rsp+278h+Buffer]
0x180007ff2  mov     [rsp+278h+var_240], rcx
0x180007ff7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007ffb  mov     [rsp+278h+nSize], eax
0x180007fff  mov     eax, [rbx+44h]
0x180008002  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008006  mov     r9, rdi; wchar_t *
0x180008009  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008010  mov     rdx, rsi; wchar_t *
0x180008013  mov     rcx, r14; this
0x180008016  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000801b  cmp     [rbx+18h], r15
0x18000801f  jnz     short loc_180008031
0x180008021  cmp     [rbx+48h], r15
0x180008025  jnz     short loc_180008031
0x180008027  cmp     [rbx+30h], r15
0x18000802b  jz      loc_1800080C1
0x180008031  lea     r8, asc_180019610; "    "
0x180008038  mov     rdx, rsi; wchar_t *
0x18000803b  mov     rcx, rax; this
0x18000803e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008043  mov     r9, [rbx+18h]; wchar_t *
0x180008047  test    r9, r9
0x18000804a  jz      short loc_18000805E
0x18000804c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008053  mov     rdx, rsi; wchar_t *
0x180008056  mov     rcx, rax; this
0x180008059  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000805e  mov     r9, [rbx+48h]; wchar_t *
0x180008062  test    r9, r9
0x180008065  jz      short loc_180008079
0x180008067  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000806e  mov     rdx, rsi; wchar_t *
0x180008071  mov     rcx, rax; this
0x180008074  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008079  mov     rcx, [rbx+28h]
0x18000807d  mov     r9, [rbx+30h]; wchar_t *
0x180008081  mov     rdx, rsi; wchar_t *
0x180008084  test    rcx, rcx
0x180008087  jz      short loc_18000809F
0x180008089  mov     [rsp+278h+lpBuffer], rcx
0x18000808e  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180008095  mov     rcx, rax; this
0x180008098  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000809d  jmp     short loc_1800080C1
0x18000809f  mov     rcx, rax; this
0x1800080a2  test    r9, r9
0x1800080a5  jz      short loc_1800080B5
0x1800080a7  lea     r8, aHs; "[%hs]\n"
0x1800080ae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800080b3  jmp     short loc_1800080C1
0x1800080b5  lea     r8, asc_180019688; "\n"
0x1800080bc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800080c1  xor     eax, eax
0x1800080c3  mov     rcx, [rsp+278h+var_38]
0x1800080cb  xor     rcx, rsp; StackCookie
0x1800080ce  call    __security_check_cookie
0x1800080d3  mov     rbx, [rsp+278h+arg_18]
0x1800080db  add     rsp, 250h
0x1800080e2  pop     r15
0x1800080e4  pop     r14
0x1800080e6  pop     rdi
0x1800080e7  pop     rsi
0x1800080e8  pop     rbp
0x1800080e9  retn
```
