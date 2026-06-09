# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007d64`
- end: `0x18000801a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180006f6c`
- `0x180008748`
- `0x180008c04`
- `0x180009c50`

## callees

- `0x180001590`
- `0x180007d64`
- `0x180008a48`
- `0x18000c370`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f17`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007e96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007e96`

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
          v7 = (const char *)&word_1800147CA;
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
0x180007d64  mov     [rsp+arg_18], rbx
0x180007d69  push    rbp
0x180007d6a  push    rsi
0x180007d6b  push    rdi
0x180007d6c  push    r14
0x180007d6e  push    r15
0x180007d70  sub     rsp, 250h
0x180007d77  mov     rax, cs:__security_cookie
0x180007d7e  xor     rax, rsp
0x180007d81  mov     [rsp+278h+var_38], rax
0x180007d89  mov     rbx, r8
0x180007d8c  mov     rsi, rdx
0x180007d8f  mov     r14, rcx
0x180007d92  xor     r15d, r15d
0x180007d95  test    rdx, rdx
0x180007d98  jz      loc_180007FF1
0x180007d9e  test    rcx, rcx
0x180007da1  jz      loc_180007FF1
0x180007da7  mov     [rcx], r15w
0x180007dab  mov     rax, cs:g_pfnResultLoggingCallback
0x180007db2  test    rax, rax
0x180007db5  jz      short loc_180007DD8
0x180007db7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007dbe  jz      short loc_180007DD8
0x180007dc0  mov     r8, rdx
0x180007dc3  mov     rdx, rcx
0x180007dc6  mov     rcx, rbx
0x180007dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dce  cmp     [r14], r15w
0x180007dd2  jnz     loc_180007FF1
0x180007dd8  mov     ecx, [rbx]
0x180007dda  mov     bpl, 8
0x180007ddd  test    ecx, ecx
0x180007ddf  jz      short loc_180007E2A
0x180007de1  sub     ecx, 1
0x180007de4  jz      short loc_180007E12
0x180007de6  sub     ecx, 1
0x180007de9  jz      short loc_180007E02
0x180007deb  cmp     ecx, 1
0x180007dee  jz      short loc_180007DF9
0x180007df0  lea     rdi, word_1800147CA
0x180007df7  jmp     short loc_180007E31
0x180007df9  lea     rdi, aFailfast; "FailFast"
0x180007e00  jmp     short loc_180007E31
0x180007e02  lea     rax, aLoghr; "LogHr"
0x180007e09  lea     rdi, aLognt; "LogNt"
0x180007e10  jmp     short loc_180007E20
0x180007e12  lea     rax, aReturnhr; "ReturnHr"
0x180007e19  lea     rdi, aReturnnt; "ReturnNt"
0x180007e20  test    [rbx+4], bpl
0x180007e24  cmovz   rdi, rax
0x180007e28  jmp     short loc_180007E31
0x180007e2a  lea     rdi, aException; "Exception"
0x180007e31  xor     edx, edx; Val
0x180007e33  mov     r8d, 200h; Size
0x180007e39  lea     rcx, [rsp+278h+Buffer]; void *
0x180007e3e  call    memset
0x180007e43  test    [rbx+4], bpl
0x180007e47  jz      short loc_180007E6C
0x180007e49  mov     ebp, [rbx+0Ch]
0x180007e4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007e53  test    rax, rax
0x180007e56  jz      short loc_180007E9C
0x180007e58  mov     r8d, 100h
0x180007e5e  lea     rdx, [rsp+278h+Buffer]
0x180007e63  mov     ecx, ebp
0x180007e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6a  jmp     short loc_180007E9C
0x180007e6c  mov     ebp, [rbx+8]
0x180007e6f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007e74  mov     [rsp+278h+nSize], 100h; nSize
0x180007e7c  lea     rax, [rsp+278h+Buffer]
0x180007e81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007e86  mov     r9d, 400h; dwLanguageId
0x180007e8c  mov     r8d, ebp; dwMessageId
0x180007e8f  xor     edx, edx; lpSource
0x180007e91  mov     ecx, 1200h; dwFlags
0x180007e96  call    cs:__imp_FormatMessageW
0x180007e9c  lea     rsi, [r14+rsi*2]
0x180007ea0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007ea4  mov     rax, [rbx+88h]
0x180007eab  mov     rcx, [rbx+80h]
0x180007eb2  mov     rdx, rsi; unsigned __int16 *
0x180007eb5  test    r9, r9
0x180007eb8  jz      short loc_180007EDC
0x180007eba  mov     [rsp+278h+Arguments], rax
0x180007ebf  mov     qword ptr [rsp+278h+nSize], rcx
0x180007ec4  mov     eax, [rbx+40h]
0x180007ec7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007ecb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007ed2  mov     rcx, r14; this
0x180007ed5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007eda  jmp     short loc_180007EF3
0x180007edc  mov     [rsp+278h+lpBuffer], rax
0x180007ee1  mov     r9, rcx; unsigned __int16 *
0x180007ee4  lea     r8, aHsP; "%hs!%p: "
0x180007eeb  mov     rcx, r14; this
0x180007eee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ef3  mov     r14, rax
0x180007ef6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007efd  test    r9, r9
0x180007f00  jz      short loc_180007F17
0x180007f02  lea     r8, aCallerP; "(caller: %p) "
0x180007f09  mov     rdx, rsi; unsigned __int16 *
0x180007f0c  mov     rcx, rax; this
0x180007f0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f14  mov     r14, rax
0x180007f17  call    cs:__imp_GetCurrentThreadId
0x180007f1d  lea     rcx, [rsp+278h+Buffer]
0x180007f22  mov     [rsp+278h+var_240], rcx
0x180007f27  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007f2b  mov     [rsp+278h+nSize], eax
0x180007f2f  mov     eax, [rbx+44h]
0x180007f32  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007f36  mov     r9, rdi; unsigned __int16 *
0x180007f39  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007f40  mov     rdx, rsi; unsigned __int16 *
0x180007f43  mov     rcx, r14; this
0x180007f46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f4b  cmp     [rbx+18h], r15
0x180007f4f  jnz     short loc_180007F61
0x180007f51  cmp     [rbx+48h], r15
0x180007f55  jnz     short loc_180007F61
0x180007f57  cmp     [rbx+30h], r15
0x180007f5b  jz      loc_180007FF1
0x180007f61  lea     r8, asc_1800148B8; "    "
0x180007f68  mov     rdx, rsi; unsigned __int16 *
0x180007f6b  mov     rcx, rax; this
0x180007f6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f73  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007f77  test    r9, r9
0x180007f7a  jz      short loc_180007F8E
0x180007f7c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007f83  mov     rdx, rsi; unsigned __int16 *
0x180007f86  mov     rcx, rax; this
0x180007f89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f8e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007f92  test    r9, r9
0x180007f95  jz      short loc_180007FA9
0x180007f97  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007f9e  mov     rdx, rsi; unsigned __int16 *
0x180007fa1  mov     rcx, rax; this
0x180007fa4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007fa9  mov     rcx, [rbx+28h]
0x180007fad  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007fb1  mov     rdx, rsi; unsigned __int16 *
0x180007fb4  test    rcx, rcx
0x180007fb7  jz      short loc_180007FCF
0x180007fb9  mov     [rsp+278h+lpBuffer], rcx
0x180007fbe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007fc5  mov     rcx, rax; this
0x180007fc8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007fcd  jmp     short loc_180007FF1
0x180007fcf  mov     rcx, rax; this
0x180007fd2  test    r9, r9
0x180007fd5  jz      short loc_180007FE5
0x180007fd7  lea     r8, aHs; "[%hs]\n"
0x180007fde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007fe3  jmp     short loc_180007FF1
0x180007fe5  lea     r8, asc_180014930; "\n"
0x180007fec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ff1  xor     eax, eax
0x180007ff3  mov     rcx, [rsp+278h+var_38]
0x180007ffb  xor     rcx, rsp; StackCookie
0x180007ffe  call    __security_check_cookie
0x180008003  mov     rbx, [rsp+278h+arg_18]
0x18000800b  add     rsp, 250h
0x180008012  pop     r15
0x180008014  pop     r14
0x180008016  pop     rdi
0x180008017  pop     rsi
0x180008018  pop     rbp
0x180008019  retn
```
