# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007e04`
- end: `0x1800080c7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180006f7c`
- `0x180008858`
- `0x180008d28`
- `0x180009e50`

## callees

- `0x180001590`
- `0x180007e04`
- `0x180008b6c`
- `0x18000c650`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fbd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007f36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007f36`

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
0x180007e04  mov     [rsp+arg_18], rbx
0x180007e09  push    rbp
0x180007e0a  push    rsi
0x180007e0b  push    rdi
0x180007e0c  push    r14
0x180007e0e  push    r15
0x180007e10  sub     rsp, 250h
0x180007e17  mov     rax, cs:__security_cookie
0x180007e1e  xor     rax, rsp
0x180007e21  mov     [rsp+278h+var_38], rax
0x180007e29  mov     rbx, r8
0x180007e2c  mov     rsi, rdx
0x180007e2f  mov     r14, rcx
0x180007e32  xor     r15d, r15d
0x180007e35  test    rdx, rdx
0x180007e38  jz      loc_18000809D
0x180007e3e  test    rcx, rcx
0x180007e41  jz      loc_18000809D
0x180007e47  mov     [rcx], r15w
0x180007e4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e52  test    rax, rax
0x180007e55  jz      short loc_180007E78
0x180007e57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007e5e  jz      short loc_180007E78
0x180007e60  mov     r8, rdx
0x180007e63  mov     rdx, rcx
0x180007e66  mov     rcx, rbx
0x180007e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6e  cmp     [r14], r15w
0x180007e72  jnz     loc_18000809D
0x180007e78  mov     ecx, [rbx]
0x180007e7a  mov     bpl, 8
0x180007e7d  test    ecx, ecx
0x180007e7f  jz      short loc_180007ECA
0x180007e81  sub     ecx, 1
0x180007e84  jz      short loc_180007EB2
0x180007e86  sub     ecx, 1
0x180007e89  jz      short loc_180007EA2
0x180007e8b  cmp     ecx, 1
0x180007e8e  jz      short loc_180007E99
0x180007e90  lea     rdi, word_1800147CA
0x180007e97  jmp     short loc_180007ED1
0x180007e99  lea     rdi, aFailfast; "FailFast"
0x180007ea0  jmp     short loc_180007ED1
0x180007ea2  lea     rax, aLoghr; "LogHr"
0x180007ea9  lea     rdi, aLognt; "LogNt"
0x180007eb0  jmp     short loc_180007EC0
0x180007eb2  lea     rax, aReturnhr; "ReturnHr"
0x180007eb9  lea     rdi, aReturnnt; "ReturnNt"
0x180007ec0  test    [rbx+4], bpl
0x180007ec4  cmovz   rdi, rax
0x180007ec8  jmp     short loc_180007ED1
0x180007eca  lea     rdi, aException; "Exception"
0x180007ed1  xor     edx, edx; Val
0x180007ed3  mov     r8d, 200h; Size
0x180007ed9  lea     rcx, [rsp+278h+Buffer]; void *
0x180007ede  call    memset
0x180007ee3  test    [rbx+4], bpl
0x180007ee7  jz      short loc_180007F0C
0x180007ee9  mov     ebp, [rbx+0Ch]
0x180007eec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007ef3  test    rax, rax
0x180007ef6  jz      short loc_180007F42
0x180007ef8  mov     r8d, 100h
0x180007efe  lea     rdx, [rsp+278h+Buffer]
0x180007f03  mov     ecx, ebp
0x180007f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f0a  jmp     short loc_180007F42
0x180007f0c  mov     ebp, [rbx+8]
0x180007f0f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007f14  mov     [rsp+278h+nSize], 100h; nSize
0x180007f1c  lea     rax, [rsp+278h+Buffer]
0x180007f21  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007f26  mov     r9d, 400h; dwLanguageId
0x180007f2c  mov     r8d, ebp; dwMessageId
0x180007f2f  xor     edx, edx; lpSource
0x180007f31  mov     ecx, 1200h; dwFlags
0x180007f36  call    cs:__imp_FormatMessageW
0x180007f3d  nop     dword ptr [rax+rax+00h]
0x180007f42  lea     rsi, [r14+rsi*2]
0x180007f46  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007f4a  mov     rax, [rbx+88h]
0x180007f51  mov     rcx, [rbx+80h]
0x180007f58  mov     rdx, rsi; unsigned __int16 *
0x180007f5b  test    r9, r9
0x180007f5e  jz      short loc_180007F82
0x180007f60  mov     [rsp+278h+Arguments], rax
0x180007f65  mov     qword ptr [rsp+278h+nSize], rcx
0x180007f6a  mov     eax, [rbx+40h]
0x180007f6d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007f71  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007f78  mov     rcx, r14; this
0x180007f7b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f80  jmp     short loc_180007F99
0x180007f82  mov     [rsp+278h+lpBuffer], rax
0x180007f87  mov     r9, rcx; unsigned __int16 *
0x180007f8a  lea     r8, aHsP; "%hs!%p: "
0x180007f91  mov     rcx, r14; this
0x180007f94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f99  mov     r14, rax
0x180007f9c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007fa3  test    r9, r9
0x180007fa6  jz      short loc_180007FBD
0x180007fa8  lea     r8, aCallerP; "(caller: %p) "
0x180007faf  mov     rdx, rsi; unsigned __int16 *
0x180007fb2  mov     rcx, rax; this
0x180007fb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007fba  mov     r14, rax
0x180007fbd  call    cs:__imp_GetCurrentThreadId
0x180007fc4  nop     dword ptr [rax+rax+00h]
0x180007fc9  lea     rcx, [rsp+278h+Buffer]
0x180007fce  mov     [rsp+278h+var_240], rcx
0x180007fd3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007fd7  mov     [rsp+278h+nSize], eax
0x180007fdb  mov     eax, [rbx+44h]
0x180007fde  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007fe2  mov     r9, rdi; unsigned __int16 *
0x180007fe5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007fec  mov     rdx, rsi; unsigned __int16 *
0x180007fef  mov     rcx, r14; this
0x180007ff2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ff7  cmp     [rbx+18h], r15
0x180007ffb  jnz     short loc_18000800D
0x180007ffd  cmp     [rbx+48h], r15
0x180008001  jnz     short loc_18000800D
0x180008003  cmp     [rbx+30h], r15
0x180008007  jz      loc_18000809D
0x18000800d  lea     r8, asc_1800148B8; "    "
0x180008014  mov     rdx, rsi; unsigned __int16 *
0x180008017  mov     rcx, rax; this
0x18000801a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000801f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008023  test    r9, r9
0x180008026  jz      short loc_18000803A
0x180008028  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000802f  mov     rdx, rsi; unsigned __int16 *
0x180008032  mov     rcx, rax; this
0x180008035  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000803a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000803e  test    r9, r9
0x180008041  jz      short loc_180008055
0x180008043  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000804a  mov     rdx, rsi; unsigned __int16 *
0x18000804d  mov     rcx, rax; this
0x180008050  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008055  mov     rcx, [rbx+28h]
0x180008059  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000805d  mov     rdx, rsi; unsigned __int16 *
0x180008060  test    rcx, rcx
0x180008063  jz      short loc_18000807B
0x180008065  mov     [rsp+278h+lpBuffer], rcx
0x18000806a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008071  mov     rcx, rax; this
0x180008074  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008079  jmp     short loc_18000809D
0x18000807b  mov     rcx, rax; this
0x18000807e  test    r9, r9
0x180008081  jz      short loc_180008091
0x180008083  lea     r8, aHs; "[%hs]\n"
0x18000808a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000808f  jmp     short loc_18000809D
0x180008091  lea     r8, asc_180014930; "\n"
0x180008098  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000809d  xor     eax, eax
0x18000809f  mov     rcx, [rsp+278h+var_38]
0x1800080a7  xor     rcx, rsp; StackCookie
0x1800080aa  call    __security_check_cookie
0x1800080af  mov     rbx, [rsp+278h+arg_18]
0x1800080b7  add     rsp, 250h
0x1800080be  pop     r15
0x1800080c0  pop     r14
0x1800080c2  pop     rdi
0x1800080c3  pop     rsi
0x1800080c4  pop     rbp
0x1800080c5  retn
```
