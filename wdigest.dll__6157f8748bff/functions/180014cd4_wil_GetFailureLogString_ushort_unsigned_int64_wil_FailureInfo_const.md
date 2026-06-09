# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180014cd4`
- end: `0x180014f8a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180015594`
- `0x180034160`

## callees

- `0x180012880`
- `0x180013304`
- `0x180014cd4`
- `0x180015890`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180014e06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180014e06`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&word_18003B6BE;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014cd4  mov     [rsp+arg_18], rbx
0x180014cd9  push    rbp
0x180014cda  push    rsi
0x180014cdb  push    rdi
0x180014cdc  push    r14
0x180014cde  push    r15
0x180014ce0  sub     rsp, 250h
0x180014ce7  mov     rax, cs:__security_cookie
0x180014cee  xor     rax, rsp
0x180014cf1  mov     [rsp+278h+var_38], rax
0x180014cf9  xor     r15d, r15d
0x180014cfc  mov     rbx, r8
0x180014cff  mov     rsi, rdx
0x180014d02  mov     r14, rcx
0x180014d05  test    rdx, rdx
0x180014d08  jz      loc_180014F61
0x180014d0e  test    rcx, rcx
0x180014d11  jz      loc_180014F61
0x180014d17  mov     rax, cs:g_pfnResultLoggingCallback
0x180014d1e  mov     [rcx], r15w
0x180014d22  test    rax, rax
0x180014d25  jz      short loc_180014D48
0x180014d27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180014d2e  jz      short loc_180014D48
0x180014d30  mov     r8, rdx
0x180014d33  mov     rdx, rcx
0x180014d36  mov     rcx, rbx
0x180014d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d3e  cmp     [r14], r15w
0x180014d42  jnz     loc_180014F61
0x180014d48  mov     ecx, [rbx]
0x180014d4a  mov     bpl, 8
0x180014d4d  test    ecx, ecx
0x180014d4f  jz      short loc_180014D9A
0x180014d51  sub     ecx, 1
0x180014d54  jz      short loc_180014D82
0x180014d56  sub     ecx, 1
0x180014d59  jz      short loc_180014D72
0x180014d5b  cmp     ecx, 1
0x180014d5e  jz      short loc_180014D69
0x180014d60  lea     rdi, word_18003B6BE
0x180014d67  jmp     short loc_180014DA1
0x180014d69  lea     rdi, aFailfast; "FailFast"
0x180014d70  jmp     short loc_180014DA1
0x180014d72  lea     rax, aLoghr; "LogHr"
0x180014d79  lea     rdi, aLognt; "LogNt"
0x180014d80  jmp     short loc_180014D90
0x180014d82  lea     rax, aReturnhr; "ReturnHr"
0x180014d89  lea     rdi, aReturnnt; "ReturnNt"
0x180014d90  test    [rbx+4], bpl
0x180014d94  cmovz   rdi, rax
0x180014d98  jmp     short loc_180014DA1
0x180014d9a  lea     rdi, aException; "Exception"
0x180014da1  xor     edx, edx; Val
0x180014da3  lea     rcx, [rsp+278h+Buffer]; void *
0x180014da8  mov     r8d, 200h; Size
0x180014dae  call    memset_0
0x180014db3  test    [rbx+4], bpl
0x180014db7  jz      short loc_180014DDC
0x180014db9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180014dc0  mov     ebp, [rbx+0Ch]
0x180014dc3  test    rax, rax
0x180014dc6  jz      short loc_180014E0C
0x180014dc8  mov     r8d, 100h
0x180014dce  lea     rdx, [rsp+278h+Buffer]
0x180014dd3  mov     ecx, ebp
0x180014dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dda  jmp     short loc_180014E0C
0x180014ddc  mov     ebp, [rbx+8]
0x180014ddf  lea     rax, [rsp+278h+Buffer]
0x180014de4  mov     [rsp+278h+Arguments], r15; Arguments
0x180014de9  mov     r8d, ebp; dwMessageId
0x180014dec  mov     [rsp+278h+nSize], 100h; nSize
0x180014df4  mov     r9d, 400h; dwLanguageId
0x180014dfa  xor     edx, edx; lpSource
0x180014dfc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180014e01  mov     ecx, 1200h; dwFlags
0x180014e06  call    cs:__imp_FormatMessageW
0x180014e0c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180014e10  lea     rsi, [r14+rsi*2]
0x180014e14  mov     rax, [rbx+88h]
0x180014e1b  mov     rdx, rsi; unsigned __int16 *
0x180014e1e  mov     rcx, [rbx+80h]
0x180014e25  test    r9, r9
0x180014e28  jz      short loc_180014E4C
0x180014e2a  mov     [rsp+278h+Arguments], rax
0x180014e2f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180014e36  mov     eax, [rbx+40h]
0x180014e39  mov     qword ptr [rsp+278h+nSize], rcx
0x180014e3e  mov     rcx, r14; this
0x180014e41  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180014e45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014e4a  jmp     short loc_180014E63
0x180014e4c  mov     r9, rcx; unsigned __int16 *
0x180014e4f  mov     [rsp+278h+lpBuffer], rax
0x180014e54  mov     rcx, r14; this
0x180014e57  lea     r8, aHsP; "%hs!%p: "
0x180014e5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014e63  mov     r9, [rbx+90h]; unsigned __int16 *
0x180014e6a  mov     r14, rax
0x180014e6d  test    r9, r9
0x180014e70  jz      short loc_180014E87
0x180014e72  lea     r8, aCallerP; "(caller: %p) "
0x180014e79  mov     rdx, rsi; unsigned __int16 *
0x180014e7c  mov     rcx, rax; this
0x180014e7f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014e84  mov     r14, rax
0x180014e87  call    cs:__imp_GetCurrentThreadId
0x180014e8d  lea     rcx, [rsp+278h+Buffer]
0x180014e92  mov     r9, rdi; unsigned __int16 *
0x180014e95  mov     [rsp+278h+var_240], rcx
0x180014e9a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180014ea1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180014ea5  mov     rdx, rsi; unsigned __int16 *
0x180014ea8  mov     [rsp+278h+nSize], eax
0x180014eac  mov     rcx, r14; this
0x180014eaf  mov     eax, [rbx+44h]
0x180014eb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180014eb6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014ebb  cmp     [rbx+18h], r15
0x180014ebf  jnz     short loc_180014ED1
0x180014ec1  cmp     [rbx+48h], r15
0x180014ec5  jnz     short loc_180014ED1
0x180014ec7  cmp     [rbx+30h], r15
0x180014ecb  jz      loc_180014F61
0x180014ed1  lea     r8, asc_18003BB20; "    "
0x180014ed8  mov     rdx, rsi; unsigned __int16 *
0x180014edb  mov     rcx, rax; this
0x180014ede  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014ee3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180014ee7  test    r9, r9
0x180014eea  jz      short loc_180014EFE
0x180014eec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180014ef3  mov     rdx, rsi; unsigned __int16 *
0x180014ef6  mov     rcx, rax; this
0x180014ef9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014efe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180014f02  test    r9, r9
0x180014f05  jz      short loc_180014F19
0x180014f07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180014f0e  mov     rdx, rsi; unsigned __int16 *
0x180014f11  mov     rcx, rax; this
0x180014f14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014f19  mov     rcx, [rbx+28h]
0x180014f1d  mov     rdx, rsi; unsigned __int16 *
0x180014f20  mov     r9, [rbx+30h]; unsigned __int16 *
0x180014f24  test    rcx, rcx
0x180014f27  jz      short loc_180014F3F
0x180014f29  mov     [rsp+278h+lpBuffer], rcx
0x180014f2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180014f35  mov     rcx, rax; this
0x180014f38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014f3d  jmp     short loc_180014F61
0x180014f3f  mov     rcx, rax; this
0x180014f42  test    r9, r9
0x180014f45  jz      short loc_180014F55
0x180014f47  lea     r8, aHs; "[%hs]\n"
0x180014f4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014f53  jmp     short loc_180014F61
0x180014f55  lea     r8, asc_18003BB98; "\n"
0x180014f5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014f61  xor     eax, eax
0x180014f63  mov     rcx, [rsp+278h+var_38]
0x180014f6b  xor     rcx, rsp; StackCookie
0x180014f6e  call    __security_check_cookie
0x180014f73  mov     rbx, [rsp+278h+arg_18]
0x180014f7b  add     rsp, 250h
0x180014f82  pop     r15
0x180014f84  pop     r14
0x180014f86  pop     rdi
0x180014f87  pop     rsi
0x180014f88  pop     rbp
0x180014f89  retn
```
