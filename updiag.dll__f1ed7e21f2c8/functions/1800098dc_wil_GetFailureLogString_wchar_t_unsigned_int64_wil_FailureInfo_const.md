# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800098dc`
- end: `0x180009b90`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180008f14`
- `0x1800091d8`
- `0x180009b98`
- `0x180009ec4`
- `0x18000a800`
- `0x180096edc`
- `0x180097015`
- `0x1800971ea`
- `0x1800975f3`

## callees

- `0x180009870`
- `0x1800098dc`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a8d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009a0c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009a0c`

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
  v7 = (const char *)&word_1800A006A;
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
0x1800098dc  mov     [rsp+arg_18], rbx
0x1800098e1  push    rbp
0x1800098e2  push    rsi
0x1800098e3  push    rdi
0x1800098e4  push    r14
0x1800098e6  push    r15
0x1800098e8  sub     rsp, 250h
0x1800098ef  mov     rax, cs:__security_cookie
0x1800098f6  xor     rax, rsp
0x1800098f9  mov     [rsp+278h+var_38], rax
0x180009901  mov     rbx, r8
0x180009904  mov     rdi, rdx
0x180009907  mov     r14, rcx
0x18000990a  xor     r15d, r15d
0x18000990d  test    rdx, rdx
0x180009910  jz      loc_180009B67
0x180009916  test    rcx, rcx
0x180009919  jz      loc_180009B67
0x18000991f  mov     [rcx], r15w
0x180009923  mov     rax, cs:g_pfnResultLoggingCallback
0x18000992a  test    rax, rax
0x18000992d  jz      short loc_180009950
0x18000992f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009936  jz      short loc_180009950
0x180009938  mov     r8, rdx
0x18000993b  mov     rdx, rcx
0x18000993e  mov     rcx, rbx
0x180009941  call    _guard_dispatch_icall
0x180009946  cmp     [r14], r15w
0x18000994a  jnz     loc_180009B67
0x180009950  lea     rsi, word_1800A006A
0x180009957  mov     ecx, [rbx]
0x180009959  mov     bpl, 8
0x18000995c  test    ecx, ecx
0x18000995e  jz      short loc_1800099A0
0x180009960  sub     ecx, 1
0x180009963  jz      short loc_180009988
0x180009965  sub     ecx, 1
0x180009968  jz      short loc_180009978
0x18000996a  cmp     ecx, 1
0x18000996d  jnz     short loc_1800099A7
0x18000996f  lea     rsi, aFailfast; "FailFast"
0x180009976  jmp     short loc_1800099A7
0x180009978  lea     rax, aLoghr; "LogHr"
0x18000997f  lea     rsi, aLognt; "LogNt"
0x180009986  jmp     short loc_180009996
0x180009988  lea     rax, aReturnhr; "ReturnHr"
0x18000998f  lea     rsi, aReturnnt; "ReturnNt"
0x180009996  test    [rbx+4], bpl
0x18000999a  cmovz   rsi, rax
0x18000999e  jmp     short loc_1800099A7
0x1800099a0  lea     rsi, aException; "Exception"
0x1800099a7  xor     edx, edx; Val
0x1800099a9  mov     r8d, 200h; Size
0x1800099af  lea     rcx, [rsp+278h+Buffer]; void *
0x1800099b4  call    memset
0x1800099b9  test    [rbx+4], bpl
0x1800099bd  jz      short loc_1800099E2
0x1800099bf  mov     ebp, [rbx+0Ch]
0x1800099c2  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800099c9  test    rax, rax
0x1800099cc  jz      short loc_180009A12
0x1800099ce  mov     r8d, 100h
0x1800099d4  lea     rdx, [rsp+278h+Buffer]
0x1800099d9  mov     ecx, ebp
0x1800099db  call    _guard_dispatch_icall
0x1800099e0  jmp     short loc_180009A12
0x1800099e2  mov     ebp, [rbx+8]
0x1800099e5  mov     [rsp+278h+Arguments], r15; Arguments
0x1800099ea  mov     [rsp+278h+nSize], 100h; nSize
0x1800099f2  lea     rax, [rsp+278h+Buffer]
0x1800099f7  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800099fc  mov     r9d, 400h; dwLanguageId
0x180009a02  mov     r8d, ebp; dwMessageId
0x180009a05  xor     edx, edx; lpSource
0x180009a07  mov     ecx, 1200h; dwFlags
0x180009a0c  call    cs:__imp_FormatMessageW
0x180009a12  lea     rdi, [r14+rdi*2]
0x180009a16  mov     r9, [rbx+38h]; wchar_t *
0x180009a1a  mov     rax, [rbx+88h]
0x180009a21  mov     rcx, [rbx+80h]
0x180009a28  mov     rdx, rdi; wchar_t *
0x180009a2b  test    r9, r9
0x180009a2e  jz      short loc_180009A52
0x180009a30  mov     [rsp+278h+Arguments], rax
0x180009a35  mov     qword ptr [rsp+278h+nSize], rcx
0x180009a3a  mov     eax, [rbx+40h]
0x180009a3d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009a41  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009a48  mov     rcx, r14; this
0x180009a4b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009a50  jmp     short loc_180009A69
0x180009a52  mov     [rsp+278h+lpBuffer], rax
0x180009a57  mov     r9, rcx; wchar_t *
0x180009a5a  lea     r8, aHsP; "%hs!%p: "
0x180009a61  mov     rcx, r14; this
0x180009a64  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009a69  mov     r14, rax
0x180009a6c  mov     r9, [rbx+90h]; wchar_t *
0x180009a73  test    r9, r9
0x180009a76  jz      short loc_180009A8D
0x180009a78  lea     r8, aCallerP; "(caller: %p) "
0x180009a7f  mov     rdx, rdi; wchar_t *
0x180009a82  mov     rcx, rax; this
0x180009a85  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009a8a  mov     r14, rax
0x180009a8d  call    cs:__imp_GetCurrentThreadId
0x180009a93  lea     rcx, [rsp+278h+Buffer]
0x180009a98  mov     [rsp+278h+var_240], rcx
0x180009a9d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009aa1  mov     [rsp+278h+nSize], eax
0x180009aa5  mov     eax, [rbx+44h]
0x180009aa8  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009aac  mov     r9, rsi; wchar_t *
0x180009aaf  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009ab6  mov     rdx, rdi; wchar_t *
0x180009ab9  mov     rcx, r14; this
0x180009abc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009ac1  cmp     [rbx+18h], r15
0x180009ac5  jnz     short loc_180009AD7
0x180009ac7  cmp     [rbx+48h], r15
0x180009acb  jnz     short loc_180009AD7
0x180009acd  cmp     [rbx+30h], r15
0x180009ad1  jz      loc_180009B67
0x180009ad7  lea     r8, asc_1800A2C08; "    "
0x180009ade  mov     rdx, rdi; wchar_t *
0x180009ae1  mov     rcx, rax; this
0x180009ae4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009ae9  mov     r9, [rbx+18h]; wchar_t *
0x180009aed  test    r9, r9
0x180009af0  jz      short loc_180009B04
0x180009af2  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009af9  mov     rdx, rdi; wchar_t *
0x180009afc  mov     rcx, rax; this
0x180009aff  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009b04  mov     r9, [rbx+48h]; wchar_t *
0x180009b08  test    r9, r9
0x180009b0b  jz      short loc_180009B1F
0x180009b0d  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009b14  mov     rdx, rdi; wchar_t *
0x180009b17  mov     rcx, rax; this
0x180009b1a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009b1f  mov     rcx, [rbx+28h]
0x180009b23  mov     r9, [rbx+30h]; wchar_t *
0x180009b27  mov     rdx, rdi; wchar_t *
0x180009b2a  test    rcx, rcx
0x180009b2d  jz      short loc_180009B45
0x180009b2f  mov     [rsp+278h+lpBuffer], rcx
0x180009b34  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009b3b  mov     rcx, rax; this
0x180009b3e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009b43  jmp     short loc_180009B67
0x180009b45  mov     rcx, rax; this
0x180009b48  test    r9, r9
0x180009b4b  jz      short loc_180009B5B
0x180009b4d  lea     r8, aHs; "[%hs]\n"
0x180009b54  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009b59  jmp     short loc_180009B67
0x180009b5b  lea     r8, asc_1800A2C80; "\n"
0x180009b62  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009b67  xor     eax, eax
0x180009b69  mov     rcx, [rsp+278h+var_38]
0x180009b71  xor     rcx, rsp; StackCookie
0x180009b74  call    __security_check_cookie
0x180009b79  mov     rbx, [rsp+278h+arg_18]
0x180009b81  add     rsp, 250h
0x180009b88  pop     r15
0x180009b8a  pop     r14
0x180009b8c  pop     rdi
0x180009b8d  pop     rsi
0x180009b8e  pop     rbp
0x180009b8f  retn
```
