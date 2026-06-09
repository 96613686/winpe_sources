# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a8d4`
- end: `0x18000ab8a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000af78`
- `0x18000b3f4`
- `0x18000c680`

## callees

- `0x180008320`
- `0x180009018`
- `0x18000a8d4`
- `0x18000b274`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000aa06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000aa06`

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
          v7 = (const char *)&qword_18002C468;
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
0x18000a8d4  mov     [rsp+arg_18], rbx
0x18000a8d9  push    rbp
0x18000a8da  push    rsi
0x18000a8db  push    rdi
0x18000a8dc  push    r14
0x18000a8de  push    r15
0x18000a8e0  sub     rsp, 250h
0x18000a8e7  mov     rax, cs:__security_cookie
0x18000a8ee  xor     rax, rsp
0x18000a8f1  mov     [rsp+278h+var_38], rax
0x18000a8f9  mov     rbx, r8
0x18000a8fc  mov     rsi, rdx
0x18000a8ff  mov     r14, rcx
0x18000a902  xor     r15d, r15d
0x18000a905  test    rdx, rdx
0x18000a908  jz      loc_18000AB61
0x18000a90e  test    rcx, rcx
0x18000a911  jz      loc_18000AB61
0x18000a917  mov     [rcx], r15w
0x18000a91b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a922  test    rax, rax
0x18000a925  jz      short loc_18000A948
0x18000a927  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a92e  jz      short loc_18000A948
0x18000a930  mov     r8, rdx
0x18000a933  mov     rdx, rcx
0x18000a936  mov     rcx, rbx
0x18000a939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a93e  cmp     [r14], r15w
0x18000a942  jnz     loc_18000AB61
0x18000a948  mov     ecx, [rbx]
0x18000a94a  mov     bpl, 8
0x18000a94d  test    ecx, ecx
0x18000a94f  jz      short loc_18000A99A
0x18000a951  sub     ecx, 1
0x18000a954  jz      short loc_18000A982
0x18000a956  sub     ecx, 1
0x18000a959  jz      short loc_18000A972
0x18000a95b  cmp     ecx, 1
0x18000a95e  jz      short loc_18000A969
0x18000a960  lea     rdi, qword_18002C468
0x18000a967  jmp     short loc_18000A9A1
0x18000a969  lea     rdi, aFailfast; "FailFast"
0x18000a970  jmp     short loc_18000A9A1
0x18000a972  lea     rax, aLoghr; "LogHr"
0x18000a979  lea     rdi, aLognt; "LogNt"
0x18000a980  jmp     short loc_18000A990
0x18000a982  lea     rax, aReturnhr; "ReturnHr"
0x18000a989  lea     rdi, aReturnnt; "ReturnNt"
0x18000a990  test    [rbx+4], bpl
0x18000a994  cmovz   rdi, rax
0x18000a998  jmp     short loc_18000A9A1
0x18000a99a  lea     rdi, aException; "Exception"
0x18000a9a1  xor     edx, edx; Val
0x18000a9a3  mov     r8d, 200h; Size
0x18000a9a9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a9ae  call    memset_0
0x18000a9b3  test    [rbx+4], bpl
0x18000a9b7  jz      short loc_18000A9DC
0x18000a9b9  mov     ebp, [rbx+0Ch]
0x18000a9bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000a9c3  test    rax, rax
0x18000a9c6  jz      short loc_18000AA0C
0x18000a9c8  mov     r8d, 100h
0x18000a9ce  lea     rdx, [rsp+278h+Buffer]
0x18000a9d3  mov     ecx, ebp
0x18000a9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9da  jmp     short loc_18000AA0C
0x18000a9dc  mov     ebp, [rbx+8]
0x18000a9df  mov     [rsp+278h+Arguments], r15; Arguments
0x18000a9e4  mov     [rsp+278h+nSize], 100h; nSize
0x18000a9ec  lea     rax, [rsp+278h+Buffer]
0x18000a9f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000a9f6  mov     r9d, 400h; dwLanguageId
0x18000a9fc  mov     r8d, ebp; dwMessageId
0x18000a9ff  xor     edx, edx; lpSource
0x18000aa01  mov     ecx, 1200h; dwFlags
0x18000aa06  call    cs:__imp_FormatMessageW
0x18000aa0c  lea     rsi, [r14+rsi*2]
0x18000aa10  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000aa14  mov     rax, [rbx+88h]
0x18000aa1b  mov     rcx, [rbx+80h]
0x18000aa22  mov     rdx, rsi; unsigned __int16 *
0x18000aa25  test    r9, r9
0x18000aa28  jz      short loc_18000AA4C
0x18000aa2a  mov     [rsp+278h+Arguments], rax
0x18000aa2f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000aa34  mov     eax, [rbx+40h]
0x18000aa37  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000aa3b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000aa42  mov     rcx, r14; this
0x18000aa45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aa4a  jmp     short loc_18000AA63
0x18000aa4c  mov     [rsp+278h+lpBuffer], rax
0x18000aa51  mov     r9, rcx; unsigned __int16 *
0x18000aa54  lea     r8, aHsP; "%hs!%p: "
0x18000aa5b  mov     rcx, r14; this
0x18000aa5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aa63  mov     r14, rax
0x18000aa66  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000aa6d  test    r9, r9
0x18000aa70  jz      short loc_18000AA87
0x18000aa72  lea     r8, aCallerP; "(caller: %p) "
0x18000aa79  mov     rdx, rsi; unsigned __int16 *
0x18000aa7c  mov     rcx, rax; this
0x18000aa7f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aa84  mov     r14, rax
0x18000aa87  call    cs:__imp_GetCurrentThreadId
0x18000aa8d  lea     rcx, [rsp+278h+Buffer]
0x18000aa92  mov     [rsp+278h+var_240], rcx
0x18000aa97  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000aa9b  mov     [rsp+278h+nSize], eax
0x18000aa9f  mov     eax, [rbx+44h]
0x18000aaa2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000aaa6  mov     r9, rdi; unsigned __int16 *
0x18000aaa9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000aab0  mov     rdx, rsi; unsigned __int16 *
0x18000aab3  mov     rcx, r14; this
0x18000aab6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aabb  cmp     [rbx+18h], r15
0x18000aabf  jnz     short loc_18000AAD1
0x18000aac1  cmp     [rbx+48h], r15
0x18000aac5  jnz     short loc_18000AAD1
0x18000aac7  cmp     [rbx+30h], r15
0x18000aacb  jz      loc_18000AB61
0x18000aad1  lea     r8, asc_18002C570; "    "
0x18000aad8  mov     rdx, rsi; unsigned __int16 *
0x18000aadb  mov     rcx, rax; this
0x18000aade  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aae3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000aae7  test    r9, r9
0x18000aaea  jz      short loc_18000AAFE
0x18000aaec  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000aaf3  mov     rdx, rsi; unsigned __int16 *
0x18000aaf6  mov     rcx, rax; this
0x18000aaf9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aafe  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000ab02  test    r9, r9
0x18000ab05  jz      short loc_18000AB19
0x18000ab07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000ab0e  mov     rdx, rsi; unsigned __int16 *
0x18000ab11  mov     rcx, rax; this
0x18000ab14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab19  mov     rcx, [rbx+28h]
0x18000ab1d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000ab21  mov     rdx, rsi; unsigned __int16 *
0x18000ab24  test    rcx, rcx
0x18000ab27  jz      short loc_18000AB3F
0x18000ab29  mov     [rsp+278h+lpBuffer], rcx
0x18000ab2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000ab35  mov     rcx, rax; this
0x18000ab38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab3d  jmp     short loc_18000AB61
0x18000ab3f  mov     rcx, rax; this
0x18000ab42  test    r9, r9
0x18000ab45  jz      short loc_18000AB55
0x18000ab47  lea     r8, aHs; "[%hs]\n"
0x18000ab4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab53  jmp     short loc_18000AB61
0x18000ab55  lea     r8, asc_18002C5E8; "\n"
0x18000ab5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab61  xor     eax, eax
0x18000ab63  mov     rcx, [rsp+278h+var_38]
0x18000ab6b  xor     rcx, rsp; StackCookie
0x18000ab6e  call    __security_check_cookie
0x18000ab73  mov     rbx, [rsp+278h+arg_18]
0x18000ab7b  add     rsp, 250h
0x18000ab82  pop     r15
0x18000ab84  pop     r14
0x18000ab86  pop     rdi
0x18000ab87  pop     rsi
0x18000ab88  pop     rbp
0x18000ab89  retn
```
