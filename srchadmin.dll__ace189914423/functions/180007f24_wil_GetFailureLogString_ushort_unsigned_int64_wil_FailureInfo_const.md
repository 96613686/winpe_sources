# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007f24`
- end: `0x1800081da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000860c`
- `0x180008ac0`
- `0x180009ce0`

## callees

- `0x180005cc0`
- `0x18000687c`
- `0x180007f24`
- `0x180008908`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008056`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008056`

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
          v7 = (const char *)&qword_180035EB0;
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
0x180007f24  mov     [rsp+arg_18], rbx
0x180007f29  push    rbp
0x180007f2a  push    rsi
0x180007f2b  push    rdi
0x180007f2c  push    r14
0x180007f2e  push    r15
0x180007f30  sub     rsp, 250h
0x180007f37  mov     rax, cs:__security_cookie
0x180007f3e  xor     rax, rsp
0x180007f41  mov     [rsp+278h+var_38], rax
0x180007f49  mov     rbx, r8
0x180007f4c  mov     rsi, rdx
0x180007f4f  mov     r14, rcx
0x180007f52  xor     r15d, r15d
0x180007f55  test    rdx, rdx
0x180007f58  jz      loc_1800081B1
0x180007f5e  test    rcx, rcx
0x180007f61  jz      loc_1800081B1
0x180007f67  mov     [rcx], r15w
0x180007f6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007f72  test    rax, rax
0x180007f75  jz      short loc_180007F98
0x180007f77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007f7e  jz      short loc_180007F98
0x180007f80  mov     r8, rdx
0x180007f83  mov     rdx, rcx
0x180007f86  mov     rcx, rbx
0x180007f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8e  cmp     [r14], r15w
0x180007f92  jnz     loc_1800081B1
0x180007f98  mov     ecx, [rbx]
0x180007f9a  mov     bpl, 8
0x180007f9d  test    ecx, ecx
0x180007f9f  jz      short loc_180007FEA
0x180007fa1  sub     ecx, 1
0x180007fa4  jz      short loc_180007FD2
0x180007fa6  sub     ecx, 1
0x180007fa9  jz      short loc_180007FC2
0x180007fab  cmp     ecx, 1
0x180007fae  jz      short loc_180007FB9
0x180007fb0  lea     rdi, qword_180035EB0
0x180007fb7  jmp     short loc_180007FF1
0x180007fb9  lea     rdi, aFailfast; "FailFast"
0x180007fc0  jmp     short loc_180007FF1
0x180007fc2  lea     rax, aLoghr; "LogHr"
0x180007fc9  lea     rdi, aLognt; "LogNt"
0x180007fd0  jmp     short loc_180007FE0
0x180007fd2  lea     rax, aReturnhr; "ReturnHr"
0x180007fd9  lea     rdi, aReturnnt; "ReturnNt"
0x180007fe0  test    [rbx+4], bpl
0x180007fe4  cmovz   rdi, rax
0x180007fe8  jmp     short loc_180007FF1
0x180007fea  lea     rdi, aException; "Exception"
0x180007ff1  xor     edx, edx; Val
0x180007ff3  mov     r8d, 200h; Size
0x180007ff9  lea     rcx, [rsp+278h+Buffer]; void *
0x180007ffe  call    memset_0
0x180008003  test    [rbx+4], bpl
0x180008007  jz      short loc_18000802C
0x180008009  mov     ebp, [rbx+0Ch]
0x18000800c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008013  test    rax, rax
0x180008016  jz      short loc_18000805C
0x180008018  mov     r8d, 100h
0x18000801e  lea     rdx, [rsp+278h+Buffer]
0x180008023  mov     ecx, ebp
0x180008025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000802a  jmp     short loc_18000805C
0x18000802c  mov     ebp, [rbx+8]
0x18000802f  mov     [rsp+278h+Arguments], r15; Arguments
0x180008034  mov     [rsp+278h+nSize], 100h; nSize
0x18000803c  lea     rax, [rsp+278h+Buffer]
0x180008041  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008046  mov     r9d, 400h; dwLanguageId
0x18000804c  mov     r8d, ebp; dwMessageId
0x18000804f  xor     edx, edx; lpSource
0x180008051  mov     ecx, 1200h; dwFlags
0x180008056  call    cs:__imp_FormatMessageW
0x18000805c  lea     rsi, [r14+rsi*2]
0x180008060  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008064  mov     rax, [rbx+88h]
0x18000806b  mov     rcx, [rbx+80h]
0x180008072  mov     rdx, rsi; unsigned __int16 *
0x180008075  test    r9, r9
0x180008078  jz      short loc_18000809C
0x18000807a  mov     [rsp+278h+Arguments], rax
0x18000807f  mov     qword ptr [rsp+278h+nSize], rcx
0x180008084  mov     eax, [rbx+40h]
0x180008087  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000808b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008092  mov     rcx, r14; this
0x180008095  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000809a  jmp     short loc_1800080B3
0x18000809c  mov     [rsp+278h+lpBuffer], rax
0x1800080a1  mov     r9, rcx; unsigned __int16 *
0x1800080a4  lea     r8, aHsP; "%hs!%p: "
0x1800080ab  mov     rcx, r14; this
0x1800080ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800080b3  mov     r14, rax
0x1800080b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800080bd  test    r9, r9
0x1800080c0  jz      short loc_1800080D7
0x1800080c2  lea     r8, aCallerP; "(caller: %p) "
0x1800080c9  mov     rdx, rsi; unsigned __int16 *
0x1800080cc  mov     rcx, rax; this
0x1800080cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800080d4  mov     r14, rax
0x1800080d7  call    cs:__imp_GetCurrentThreadId
0x1800080dd  lea     rcx, [rsp+278h+Buffer]
0x1800080e2  mov     [rsp+278h+var_240], rcx
0x1800080e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800080eb  mov     [rsp+278h+nSize], eax
0x1800080ef  mov     eax, [rbx+44h]
0x1800080f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800080f6  mov     r9, rdi; unsigned __int16 *
0x1800080f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008100  mov     rdx, rsi; unsigned __int16 *
0x180008103  mov     rcx, r14; this
0x180008106  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000810b  cmp     [rbx+18h], r15
0x18000810f  jnz     short loc_180008121
0x180008111  cmp     [rbx+48h], r15
0x180008115  jnz     short loc_180008121
0x180008117  cmp     [rbx+30h], r15
0x18000811b  jz      loc_1800081B1
0x180008121  lea     r8, asc_180035FB8; "    "
0x180008128  mov     rdx, rsi; unsigned __int16 *
0x18000812b  mov     rcx, rax; this
0x18000812e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008133  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008137  test    r9, r9
0x18000813a  jz      short loc_18000814E
0x18000813c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008143  mov     rdx, rsi; unsigned __int16 *
0x180008146  mov     rcx, rax; this
0x180008149  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000814e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008152  test    r9, r9
0x180008155  jz      short loc_180008169
0x180008157  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000815e  mov     rdx, rsi; unsigned __int16 *
0x180008161  mov     rcx, rax; this
0x180008164  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008169  mov     rcx, [rbx+28h]
0x18000816d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008171  mov     rdx, rsi; unsigned __int16 *
0x180008174  test    rcx, rcx
0x180008177  jz      short loc_18000818F
0x180008179  mov     [rsp+278h+lpBuffer], rcx
0x18000817e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008185  mov     rcx, rax; this
0x180008188  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000818d  jmp     short loc_1800081B1
0x18000818f  mov     rcx, rax; this
0x180008192  test    r9, r9
0x180008195  jz      short loc_1800081A5
0x180008197  lea     r8, aHs; "[%hs]\n"
0x18000819e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800081a3  jmp     short loc_1800081B1
0x1800081a5  lea     r8, asc_180036030; "\n"
0x1800081ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800081b1  xor     eax, eax
0x1800081b3  mov     rcx, [rsp+278h+var_38]
0x1800081bb  xor     rcx, rsp; StackCookie
0x1800081be  call    __security_check_cookie
0x1800081c3  mov     rbx, [rsp+278h+arg_18]
0x1800081cb  add     rsp, 250h
0x1800081d2  pop     r15
0x1800081d4  pop     r14
0x1800081d6  pop     rdi
0x1800081d7  pop     rsi
0x1800081d8  pop     rbp
0x1800081d9  retn
```
