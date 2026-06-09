# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180097a94`
- end: `0x180097d4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800676c0`
- `0x180098074`
- `0x180099710`

## callees

- `0x180095130`
- `0x180095b4c`
- `0x180097a94`
- `0x180098024`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097c47`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180097bc6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180097bc6`

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
          v7 = (const char *)&qword_1800F81A8;
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
0x180097a94  mov     [rsp+arg_18], rbx
0x180097a99  push    rbp
0x180097a9a  push    rsi
0x180097a9b  push    rdi
0x180097a9c  push    r14
0x180097a9e  push    r15
0x180097aa0  sub     rsp, 250h
0x180097aa7  mov     rax, cs:__security_cookie
0x180097aae  xor     rax, rsp
0x180097ab1  mov     [rsp+278h+var_38], rax
0x180097ab9  mov     rbx, r8
0x180097abc  mov     rsi, rdx
0x180097abf  mov     r14, rcx
0x180097ac2  xor     r15d, r15d
0x180097ac5  test    rdx, rdx
0x180097ac8  jz      loc_180097D21
0x180097ace  test    rcx, rcx
0x180097ad1  jz      loc_180097D21
0x180097ad7  mov     [rcx], r15w
0x180097adb  mov     rax, cs:g_pfnResultLoggingCallback
0x180097ae2  test    rax, rax
0x180097ae5  jz      short loc_180097B08
0x180097ae7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180097aee  jz      short loc_180097B08
0x180097af0  mov     r8, rdx
0x180097af3  mov     rdx, rcx
0x180097af6  mov     rcx, rbx
0x180097af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097afe  cmp     [r14], r15w
0x180097b02  jnz     loc_180097D21
0x180097b08  mov     ecx, [rbx]
0x180097b0a  mov     bpl, 8
0x180097b0d  test    ecx, ecx
0x180097b0f  jz      short loc_180097B5A
0x180097b11  sub     ecx, 1
0x180097b14  jz      short loc_180097B42
0x180097b16  sub     ecx, 1
0x180097b19  jz      short loc_180097B32
0x180097b1b  cmp     ecx, 1
0x180097b1e  jz      short loc_180097B29
0x180097b20  lea     rdi, qword_1800F81A8
0x180097b27  jmp     short loc_180097B61
0x180097b29  lea     rdi, aFailfast; "FailFast"
0x180097b30  jmp     short loc_180097B61
0x180097b32  lea     rax, aLoghr; "LogHr"
0x180097b39  lea     rdi, aLognt; "LogNt"
0x180097b40  jmp     short loc_180097B50
0x180097b42  lea     rax, aReturnhr; "ReturnHr"
0x180097b49  lea     rdi, aReturnnt; "ReturnNt"
0x180097b50  test    [rbx+4], bpl
0x180097b54  cmovz   rdi, rax
0x180097b58  jmp     short loc_180097B61
0x180097b5a  lea     rdi, aException; "Exception"
0x180097b61  xor     edx, edx; Val
0x180097b63  mov     r8d, 200h; Size
0x180097b69  lea     rcx, [rsp+278h+Buffer]; void *
0x180097b6e  call    memset_0
0x180097b73  test    [rbx+4], bpl
0x180097b77  jz      short loc_180097B9C
0x180097b79  mov     ebp, [rbx+0Ch]
0x180097b7c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180097b83  test    rax, rax
0x180097b86  jz      short loc_180097BCC
0x180097b88  mov     r8d, 100h
0x180097b8e  lea     rdx, [rsp+278h+Buffer]
0x180097b93  mov     ecx, ebp
0x180097b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b9a  jmp     short loc_180097BCC
0x180097b9c  mov     ebp, [rbx+8]
0x180097b9f  mov     [rsp+278h+Arguments], r15; Arguments
0x180097ba4  mov     [rsp+278h+nSize], 100h; nSize
0x180097bac  lea     rax, [rsp+278h+Buffer]
0x180097bb1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180097bb6  mov     r9d, 400h; dwLanguageId
0x180097bbc  mov     r8d, ebp; dwMessageId
0x180097bbf  xor     edx, edx; lpSource
0x180097bc1  mov     ecx, 1200h; dwFlags
0x180097bc6  call    cs:__imp_FormatMessageW
0x180097bcc  lea     rsi, [r14+rsi*2]
0x180097bd0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180097bd4  mov     rax, [rbx+88h]
0x180097bdb  mov     rcx, [rbx+80h]
0x180097be2  mov     rdx, rsi; unsigned __int16 *
0x180097be5  test    r9, r9
0x180097be8  jz      short loc_180097C0C
0x180097bea  mov     [rsp+278h+Arguments], rax
0x180097bef  mov     qword ptr [rsp+278h+nSize], rcx
0x180097bf4  mov     eax, [rbx+40h]
0x180097bf7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180097bfb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180097c02  mov     rcx, r14; this
0x180097c05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097c0a  jmp     short loc_180097C23
0x180097c0c  mov     [rsp+278h+lpBuffer], rax
0x180097c11  mov     r9, rcx; unsigned __int16 *
0x180097c14  lea     r8, aHsP; "%hs!%p: "
0x180097c1b  mov     rcx, r14; this
0x180097c1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097c23  mov     r14, rax
0x180097c26  mov     r9, [rbx+90h]; unsigned __int16 *
0x180097c2d  test    r9, r9
0x180097c30  jz      short loc_180097C47
0x180097c32  lea     r8, aCallerP; "(caller: %p) "
0x180097c39  mov     rdx, rsi; unsigned __int16 *
0x180097c3c  mov     rcx, rax; this
0x180097c3f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097c44  mov     r14, rax
0x180097c47  call    cs:__imp_GetCurrentThreadId
0x180097c4d  lea     rcx, [rsp+278h+Buffer]
0x180097c52  mov     [rsp+278h+var_240], rcx
0x180097c57  mov     dword ptr [rsp+278h+Arguments], ebp
0x180097c5b  mov     [rsp+278h+nSize], eax
0x180097c5f  mov     eax, [rbx+44h]
0x180097c62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180097c66  mov     r9, rdi; unsigned __int16 *
0x180097c69  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180097c70  mov     rdx, rsi; unsigned __int16 *
0x180097c73  mov     rcx, r14; this
0x180097c76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097c7b  cmp     [rbx+18h], r15
0x180097c7f  jnz     short loc_180097C91
0x180097c81  cmp     [rbx+48h], r15
0x180097c85  jnz     short loc_180097C91
0x180097c87  cmp     [rbx+30h], r15
0x180097c8b  jz      loc_180097D21
0x180097c91  lea     r8, asc_1800F82B8; "    "
0x180097c98  mov     rdx, rsi; unsigned __int16 *
0x180097c9b  mov     rcx, rax; this
0x180097c9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097ca3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180097ca7  test    r9, r9
0x180097caa  jz      short loc_180097CBE
0x180097cac  lea     r8, aMsgWs; "Msg:[%ws] "
0x180097cb3  mov     rdx, rsi; unsigned __int16 *
0x180097cb6  mov     rcx, rax; this
0x180097cb9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097cbe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180097cc2  test    r9, r9
0x180097cc5  jz      short loc_180097CD9
0x180097cc7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180097cce  mov     rdx, rsi; unsigned __int16 *
0x180097cd1  mov     rcx, rax; this
0x180097cd4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097cd9  mov     rcx, [rbx+28h]
0x180097cdd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180097ce1  mov     rdx, rsi; unsigned __int16 *
0x180097ce4  test    rcx, rcx
0x180097ce7  jz      short loc_180097CFF
0x180097ce9  mov     [rsp+278h+lpBuffer], rcx
0x180097cee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180097cf5  mov     rcx, rax; this
0x180097cf8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097cfd  jmp     short loc_180097D21
0x180097cff  mov     rcx, rax; this
0x180097d02  test    r9, r9
0x180097d05  jz      short loc_180097D15
0x180097d07  lea     r8, aHs; "[%hs]\n"
0x180097d0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097d13  jmp     short loc_180097D21
0x180097d15  lea     r8, asc_1800F8330; "\n"
0x180097d1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180097d21  xor     eax, eax
0x180097d23  mov     rcx, [rsp+278h+var_38]
0x180097d2b  xor     rcx, rsp; StackCookie
0x180097d2e  call    __security_check_cookie
0x180097d33  mov     rbx, [rsp+278h+arg_18]
0x180097d3b  add     rsp, 250h
0x180097d42  pop     r15
0x180097d44  pop     r14
0x180097d46  pop     rdi
0x180097d47  pop     rsi
0x180097d48  pop     rbp
0x180097d49  retn
```
