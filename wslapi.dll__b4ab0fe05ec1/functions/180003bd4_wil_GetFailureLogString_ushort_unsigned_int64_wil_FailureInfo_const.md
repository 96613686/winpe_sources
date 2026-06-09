# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003bd4`
- end: `0x180003e8a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004538`
- `0x1800049f0`
- `0x180005b80`

## callees

- `0x180001dc0`
- `0x180002ab4`
- `0x180003bd4`
- `0x180004834`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d06`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
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
          v7 = (const char *)&word_18000EB82;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180003bd4  mov     [rsp+arg_18], rbx
0x180003bd9  push    rbp
0x180003bda  push    rsi
0x180003bdb  push    rdi
0x180003bdc  push    r14
0x180003bde  push    r15
0x180003be0  sub     rsp, 250h
0x180003be7  mov     rax, cs:__security_cookie
0x180003bee  xor     rax, rsp
0x180003bf1  mov     [rsp+278h+var_38], rax
0x180003bf9  mov     rbx, r8
0x180003bfc  mov     rsi, rdx
0x180003bff  mov     r14, rcx
0x180003c02  xor     r15d, r15d
0x180003c05  test    rdx, rdx
0x180003c08  jz      loc_180003E61
0x180003c0e  test    rcx, rcx
0x180003c11  jz      loc_180003E61
0x180003c17  mov     [rcx], r15w
0x180003c1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c22  test    rax, rax
0x180003c25  jz      short loc_180003C48
0x180003c27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003c2e  jz      short loc_180003C48
0x180003c30  mov     r8, rdx
0x180003c33  mov     rdx, rcx
0x180003c36  mov     rcx, rbx
0x180003c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c3e  cmp     [r14], r15w
0x180003c42  jnz     loc_180003E61
0x180003c48  mov     ecx, [rbx]
0x180003c4a  mov     bpl, 8
0x180003c4d  test    ecx, ecx
0x180003c4f  jz      short loc_180003C9A
0x180003c51  sub     ecx, 1
0x180003c54  jz      short loc_180003C82
0x180003c56  sub     ecx, 1
0x180003c59  jz      short loc_180003C72
0x180003c5b  cmp     ecx, 1
0x180003c5e  jz      short loc_180003C69
0x180003c60  lea     rdi, word_18000EB82
0x180003c67  jmp     short loc_180003CA1
0x180003c69  lea     rdi, aFailfast; "FailFast"
0x180003c70  jmp     short loc_180003CA1
0x180003c72  lea     rax, aLoghr; "LogHr"
0x180003c79  lea     rdi, aLognt; "LogNt"
0x180003c80  jmp     short loc_180003C90
0x180003c82  lea     rax, aReturnhr; "ReturnHr"
0x180003c89  lea     rdi, aReturnnt; "ReturnNt"
0x180003c90  test    [rbx+4], bpl
0x180003c94  cmovz   rdi, rax
0x180003c98  jmp     short loc_180003CA1
0x180003c9a  lea     rdi, aException; "Exception"
0x180003ca1  xor     edx, edx; Val
0x180003ca3  mov     r8d, 200h; Size
0x180003ca9  lea     rcx, [rsp+278h+Buffer]; void *
0x180003cae  call    memset_0
0x180003cb3  test    [rbx+4], bpl
0x180003cb7  jz      short loc_180003CDC
0x180003cb9  mov     ebp, [rbx+0Ch]
0x180003cbc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003cc3  test    rax, rax
0x180003cc6  jz      short loc_180003D0C
0x180003cc8  mov     r8d, 100h
0x180003cce  lea     rdx, [rsp+278h+Buffer]
0x180003cd3  mov     ecx, ebp
0x180003cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cda  jmp     short loc_180003D0C
0x180003cdc  mov     ebp, [rbx+8]
0x180003cdf  mov     [rsp+278h+Arguments], r15; Arguments
0x180003ce4  mov     [rsp+278h+nSize], 100h; nSize
0x180003cec  lea     rax, [rsp+278h+Buffer]
0x180003cf1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003cf6  mov     r9d, 400h; dwLanguageId
0x180003cfc  mov     r8d, ebp; dwMessageId
0x180003cff  xor     edx, edx; lpSource
0x180003d01  mov     ecx, 1200h; dwFlags
0x180003d06  call    cs:__imp_FormatMessageW
0x180003d0c  lea     rsi, [r14+rsi*2]
0x180003d10  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003d14  mov     rax, [rbx+88h]
0x180003d1b  mov     rcx, [rbx+80h]
0x180003d22  mov     rdx, rsi; unsigned __int16 *
0x180003d25  test    r9, r9
0x180003d28  jz      short loc_180003D4C
0x180003d2a  mov     [rsp+278h+Arguments], rax
0x180003d2f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003d34  mov     eax, [rbx+40h]
0x180003d37  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003d3b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003d42  mov     rcx, r14; this
0x180003d45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d4a  jmp     short loc_180003D63
0x180003d4c  mov     [rsp+278h+lpBuffer], rax
0x180003d51  mov     r9, rcx; unsigned __int16 *
0x180003d54  lea     r8, aHsP; "%hs!%p: "
0x180003d5b  mov     rcx, r14; this
0x180003d5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d63  mov     r14, rax
0x180003d66  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003d6d  test    r9, r9
0x180003d70  jz      short loc_180003D87
0x180003d72  lea     r8, aCallerP; "(caller: %p) "
0x180003d79  mov     rdx, rsi; unsigned __int16 *
0x180003d7c  mov     rcx, rax; this
0x180003d7f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d84  mov     r14, rax
0x180003d87  call    cs:__imp_GetCurrentThreadId
0x180003d8d  lea     rcx, [rsp+278h+Buffer]
0x180003d92  mov     [rsp+278h+var_240], rcx
0x180003d97  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003d9b  mov     [rsp+278h+nSize], eax
0x180003d9f  mov     eax, [rbx+44h]
0x180003da2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003da6  mov     r9, rdi; unsigned __int16 *
0x180003da9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003db0  mov     rdx, rsi; unsigned __int16 *
0x180003db3  mov     rcx, r14; this
0x180003db6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003dbb  cmp     [rbx+18h], r15
0x180003dbf  jnz     short loc_180003DD1
0x180003dc1  cmp     [rbx+48h], r15
0x180003dc5  jnz     short loc_180003DD1
0x180003dc7  cmp     [rbx+30h], r15
0x180003dcb  jz      loc_180003E61
0x180003dd1  lea     r8, asc_18000EC70; "    "
0x180003dd8  mov     rdx, rsi; unsigned __int16 *
0x180003ddb  mov     rcx, rax; this
0x180003dde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003de3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003de7  test    r9, r9
0x180003dea  jz      short loc_180003DFE
0x180003dec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003df3  mov     rdx, rsi; unsigned __int16 *
0x180003df6  mov     rcx, rax; this
0x180003df9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003dfe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003e02  test    r9, r9
0x180003e05  jz      short loc_180003E19
0x180003e07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003e0e  mov     rdx, rsi; unsigned __int16 *
0x180003e11  mov     rcx, rax; this
0x180003e14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e19  mov     rcx, [rbx+28h]
0x180003e1d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003e21  mov     rdx, rsi; unsigned __int16 *
0x180003e24  test    rcx, rcx
0x180003e27  jz      short loc_180003E3F
0x180003e29  mov     [rsp+278h+lpBuffer], rcx
0x180003e2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003e35  mov     rcx, rax; this
0x180003e38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e3d  jmp     short loc_180003E61
0x180003e3f  mov     rcx, rax; this
0x180003e42  test    r9, r9
0x180003e45  jz      short loc_180003E55
0x180003e47  lea     r8, aHs; "[%hs]\n"
0x180003e4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e53  jmp     short loc_180003E61
0x180003e55  lea     r8, asc_18000ECE8; "\n"
0x180003e5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e61  xor     eax, eax
0x180003e63  mov     rcx, [rsp+278h+var_38]
0x180003e6b  xor     rcx, rsp; StackCookie
0x180003e6e  call    __security_check_cookie
0x180003e73  mov     rbx, [rsp+278h+arg_18]
0x180003e7b  add     rsp, 250h
0x180003e82  pop     r15
0x180003e84  pop     r14
0x180003e86  pop     rdi
0x180003e87  pop     rsi
0x180003e88  pop     rbp
0x180003e89  retn
```
