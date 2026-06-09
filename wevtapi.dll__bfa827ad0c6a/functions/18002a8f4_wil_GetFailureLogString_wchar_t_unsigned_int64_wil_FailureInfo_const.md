# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002a8f4`
- end: `0x18002abaa`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002b218`

## callees

- `0x180024a50`
- `0x180025514`
- `0x18002a8f4`
- `0x18002b514`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002aa26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002aa26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aaa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aaa7`

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
          v7 = (const char *)&word_18004024A;
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
0x18002a8f4  mov     [rsp+arg_18], rbx
0x18002a8f9  push    rbp
0x18002a8fa  push    rsi
0x18002a8fb  push    rdi
0x18002a8fc  push    r14
0x18002a8fe  push    r15
0x18002a900  sub     rsp, 250h
0x18002a907  mov     rax, cs:__security_cookie
0x18002a90e  xor     rax, rsp
0x18002a911  mov     [rsp+278h+var_38], rax
0x18002a919  mov     rbx, r8
0x18002a91c  mov     rsi, rdx
0x18002a91f  mov     r14, rcx
0x18002a922  xor     r15d, r15d
0x18002a925  test    rdx, rdx
0x18002a928  jz      loc_18002AB81
0x18002a92e  test    rcx, rcx
0x18002a931  jz      loc_18002AB81
0x18002a937  mov     [rcx], r15w
0x18002a93b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a942  test    rax, rax
0x18002a945  jz      short loc_18002A968
0x18002a947  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002a94e  jz      short loc_18002A968
0x18002a950  mov     r8, rdx
0x18002a953  mov     rdx, rcx
0x18002a956  mov     rcx, rbx
0x18002a959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a95e  cmp     [r14], r15w
0x18002a962  jnz     loc_18002AB81
0x18002a968  mov     ecx, [rbx]
0x18002a96a  mov     bpl, 8
0x18002a96d  test    ecx, ecx
0x18002a96f  jz      short loc_18002A9BA
0x18002a971  sub     ecx, 1
0x18002a974  jz      short loc_18002A9A2
0x18002a976  sub     ecx, 1
0x18002a979  jz      short loc_18002A992
0x18002a97b  cmp     ecx, 1
0x18002a97e  jz      short loc_18002A989
0x18002a980  lea     rdi, word_18004024A
0x18002a987  jmp     short loc_18002A9C1
0x18002a989  lea     rdi, aFailfast; "FailFast"
0x18002a990  jmp     short loc_18002A9C1
0x18002a992  lea     rax, aLoghr; "LogHr"
0x18002a999  lea     rdi, aLognt; "LogNt"
0x18002a9a0  jmp     short loc_18002A9B0
0x18002a9a2  lea     rax, aReturnhr; "ReturnHr"
0x18002a9a9  lea     rdi, aReturnnt; "ReturnNt"
0x18002a9b0  test    [rbx+4], bpl
0x18002a9b4  cmovz   rdi, rax
0x18002a9b8  jmp     short loc_18002A9C1
0x18002a9ba  lea     rdi, aException; "Exception"
0x18002a9c1  xor     edx, edx; Val
0x18002a9c3  mov     r8d, 200h; Size
0x18002a9c9  lea     rcx, [rsp+278h+Buffer]; void *
0x18002a9ce  call    memset_0
0x18002a9d3  test    [rbx+4], bpl
0x18002a9d7  jz      short loc_18002A9FC
0x18002a9d9  mov     ebp, [rbx+0Ch]
0x18002a9dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18002a9e3  test    rax, rax
0x18002a9e6  jz      short loc_18002AA2C
0x18002a9e8  mov     r8d, 100h
0x18002a9ee  lea     rdx, [rsp+278h+Buffer]
0x18002a9f3  mov     ecx, ebp
0x18002a9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9fa  jmp     short loc_18002AA2C
0x18002a9fc  mov     ebp, [rbx+8]
0x18002a9ff  mov     [rsp+278h+Arguments], r15; Arguments
0x18002aa04  mov     [rsp+278h+nSize], 100h; nSize
0x18002aa0c  lea     rax, [rsp+278h+Buffer]
0x18002aa11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002aa16  mov     r9d, 400h; dwLanguageId
0x18002aa1c  mov     r8d, ebp; dwMessageId
0x18002aa1f  xor     edx, edx; lpSource
0x18002aa21  mov     ecx, 1200h; dwFlags
0x18002aa26  call    cs:__imp_FormatMessageW
0x18002aa2c  lea     rsi, [r14+rsi*2]
0x18002aa30  mov     r9, [rbx+38h]; wchar_t *
0x18002aa34  mov     rax, [rbx+88h]
0x18002aa3b  mov     rcx, [rbx+80h]
0x18002aa42  mov     rdx, rsi; wchar_t *
0x18002aa45  test    r9, r9
0x18002aa48  jz      short loc_18002AA6C
0x18002aa4a  mov     [rsp+278h+Arguments], rax
0x18002aa4f  mov     qword ptr [rsp+278h+nSize], rcx
0x18002aa54  mov     eax, [rbx+40h]
0x18002aa57  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002aa5b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002aa62  mov     rcx, r14; this
0x18002aa65  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aa6a  jmp     short loc_18002AA83
0x18002aa6c  mov     [rsp+278h+lpBuffer], rax
0x18002aa71  mov     r9, rcx; wchar_t *
0x18002aa74  lea     r8, aHsP; "%hs!%p: "
0x18002aa7b  mov     rcx, r14; this
0x18002aa7e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aa83  mov     r14, rax
0x18002aa86  mov     r9, [rbx+90h]; wchar_t *
0x18002aa8d  test    r9, r9
0x18002aa90  jz      short loc_18002AAA7
0x18002aa92  lea     r8, aCallerP; "(caller: %p) "
0x18002aa99  mov     rdx, rsi; wchar_t *
0x18002aa9c  mov     rcx, rax; this
0x18002aa9f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aaa4  mov     r14, rax
0x18002aaa7  call    cs:__imp_GetCurrentThreadId
0x18002aaad  lea     rcx, [rsp+278h+Buffer]
0x18002aab2  mov     [rsp+278h+var_240], rcx
0x18002aab7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002aabb  mov     [rsp+278h+nSize], eax
0x18002aabf  mov     eax, [rbx+44h]
0x18002aac2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002aac6  mov     r9, rdi; wchar_t *
0x18002aac9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002aad0  mov     rdx, rsi; wchar_t *
0x18002aad3  mov     rcx, r14; this
0x18002aad6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aadb  cmp     [rbx+18h], r15
0x18002aadf  jnz     short loc_18002AAF1
0x18002aae1  cmp     [rbx+48h], r15
0x18002aae5  jnz     short loc_18002AAF1
0x18002aae7  cmp     [rbx+30h], r15
0x18002aaeb  jz      loc_18002AB81
0x18002aaf1  lea     r8, asc_180041648; "    "
0x18002aaf8  mov     rdx, rsi; wchar_t *
0x18002aafb  mov     rcx, rax; this
0x18002aafe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002ab03  mov     r9, [rbx+18h]; wchar_t *
0x18002ab07  test    r9, r9
0x18002ab0a  jz      short loc_18002AB1E
0x18002ab0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002ab13  mov     rdx, rsi; wchar_t *
0x18002ab16  mov     rcx, rax; this
0x18002ab19  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002ab1e  mov     r9, [rbx+48h]; wchar_t *
0x18002ab22  test    r9, r9
0x18002ab25  jz      short loc_18002AB39
0x18002ab27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002ab2e  mov     rdx, rsi; wchar_t *
0x18002ab31  mov     rcx, rax; this
0x18002ab34  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002ab39  mov     rcx, [rbx+28h]
0x18002ab3d  mov     r9, [rbx+30h]; wchar_t *
0x18002ab41  mov     rdx, rsi; wchar_t *
0x18002ab44  test    rcx, rcx
0x18002ab47  jz      short loc_18002AB5F
0x18002ab49  mov     [rsp+278h+lpBuffer], rcx
0x18002ab4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002ab55  mov     rcx, rax; this
0x18002ab58  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002ab5d  jmp     short loc_18002AB81
0x18002ab5f  mov     rcx, rax; this
0x18002ab62  test    r9, r9
0x18002ab65  jz      short loc_18002AB75
0x18002ab67  lea     r8, aHs; "[%hs]\n"
0x18002ab6e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002ab73  jmp     short loc_18002AB81
0x18002ab75  lea     r8, asc_1800416C0; "\n"
0x18002ab7c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002ab81  xor     eax, eax
0x18002ab83  mov     rcx, [rsp+278h+var_38]
0x18002ab8b  xor     rcx, rsp; StackCookie
0x18002ab8e  call    __security_check_cookie
0x18002ab93  mov     rbx, [rsp+278h+arg_18]
0x18002ab9b  add     rsp, 250h
0x18002aba2  pop     r15
0x18002aba4  pop     r14
0x18002aba6  pop     rdi
0x18002aba7  pop     rsi
0x18002aba8  pop     rbp
0x18002aba9  retn
```
