# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000ba8c`
- end: `0x18000bd42`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180007f20`
- `0x18000c750`
- `0x18001cf94`
- `0x18001f940`

## callees

- `0x180003110`
- `0x180003c88`
- `0x18000ba8c`
- `0x18000ca50`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc3f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bbbe`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bbbe`

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
          v7 = (const char *)&qword_18005F908;
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
0x18000ba8c  mov     [rsp+arg_18], rbx
0x18000ba91  push    rbp
0x18000ba92  push    rsi
0x18000ba93  push    rdi
0x18000ba94  push    r14
0x18000ba96  push    r15
0x18000ba98  sub     rsp, 250h
0x18000ba9f  mov     rax, cs:__security_cookie
0x18000baa6  xor     rax, rsp
0x18000baa9  mov     [rsp+278h+var_38], rax
0x18000bab1  mov     rbx, r8
0x18000bab4  mov     rsi, rdx
0x18000bab7  mov     r14, rcx
0x18000baba  xor     r15d, r15d
0x18000babd  test    rdx, rdx
0x18000bac0  jz      loc_18000BD19
0x18000bac6  test    rcx, rcx
0x18000bac9  jz      loc_18000BD19
0x18000bacf  mov     [rcx], r15w
0x18000bad3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bada  test    rax, rax
0x18000badd  jz      short loc_18000BB00
0x18000badf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000bae6  jz      short loc_18000BB00
0x18000bae8  mov     r8, rdx
0x18000baeb  mov     rdx, rcx
0x18000baee  mov     rcx, rbx
0x18000baf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf6  cmp     [r14], r15w
0x18000bafa  jnz     loc_18000BD19
0x18000bb00  mov     ecx, [rbx]
0x18000bb02  mov     bpl, 8
0x18000bb05  test    ecx, ecx
0x18000bb07  jz      short loc_18000BB52
0x18000bb09  sub     ecx, 1
0x18000bb0c  jz      short loc_18000BB3A
0x18000bb0e  sub     ecx, 1
0x18000bb11  jz      short loc_18000BB2A
0x18000bb13  cmp     ecx, 1
0x18000bb16  jz      short loc_18000BB21
0x18000bb18  lea     rdi, qword_18005F908
0x18000bb1f  jmp     short loc_18000BB59
0x18000bb21  lea     rdi, aFailfast; "FailFast"
0x18000bb28  jmp     short loc_18000BB59
0x18000bb2a  lea     rax, aLoghr; "LogHr"
0x18000bb31  lea     rdi, aLognt; "LogNt"
0x18000bb38  jmp     short loc_18000BB48
0x18000bb3a  lea     rax, aReturnhr; "ReturnHr"
0x18000bb41  lea     rdi, aReturnnt; "ReturnNt"
0x18000bb48  test    [rbx+4], bpl
0x18000bb4c  cmovz   rdi, rax
0x18000bb50  jmp     short loc_18000BB59
0x18000bb52  lea     rdi, aException; "Exception"
0x18000bb59  xor     edx, edx; Val
0x18000bb5b  mov     r8d, 200h; Size
0x18000bb61  lea     rcx, [rsp+278h+Buffer]; void *
0x18000bb66  call    memset_0
0x18000bb6b  test    [rbx+4], bpl
0x18000bb6f  jz      short loc_18000BB94
0x18000bb71  mov     ebp, [rbx+0Ch]
0x18000bb74  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000bb7b  test    rax, rax
0x18000bb7e  jz      short loc_18000BBC4
0x18000bb80  mov     r8d, 100h
0x18000bb86  lea     rdx, [rsp+278h+Buffer]
0x18000bb8b  mov     ecx, ebp
0x18000bb8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb92  jmp     short loc_18000BBC4
0x18000bb94  mov     ebp, [rbx+8]
0x18000bb97  mov     [rsp+278h+Arguments], r15; Arguments
0x18000bb9c  mov     [rsp+278h+nSize], 100h; nSize
0x18000bba4  lea     rax, [rsp+278h+Buffer]
0x18000bba9  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000bbae  mov     r9d, 400h; dwLanguageId
0x18000bbb4  mov     r8d, ebp; dwMessageId
0x18000bbb7  xor     edx, edx; lpSource
0x18000bbb9  mov     ecx, 1200h; dwFlags
0x18000bbbe  call    cs:__imp_FormatMessageW
0x18000bbc4  lea     rsi, [r14+rsi*2]
0x18000bbc8  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000bbcc  mov     rax, [rbx+88h]
0x18000bbd3  mov     rcx, [rbx+80h]
0x18000bbda  mov     rdx, rsi; unsigned __int16 *
0x18000bbdd  test    r9, r9
0x18000bbe0  jz      short loc_18000BC04
0x18000bbe2  mov     [rsp+278h+Arguments], rax
0x18000bbe7  mov     qword ptr [rsp+278h+nSize], rcx
0x18000bbec  mov     eax, [rbx+40h]
0x18000bbef  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bbf3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000bbfa  mov     rcx, r14; this
0x18000bbfd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc02  jmp     short loc_18000BC1B
0x18000bc04  mov     [rsp+278h+lpBuffer], rax
0x18000bc09  mov     r9, rcx; unsigned __int16 *
0x18000bc0c  lea     r8, aHsP; "%hs!%p: "
0x18000bc13  mov     rcx, r14; this
0x18000bc16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc1b  mov     r14, rax
0x18000bc1e  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000bc25  test    r9, r9
0x18000bc28  jz      short loc_18000BC3F
0x18000bc2a  lea     r8, aCallerP; "(caller: %p) "
0x18000bc31  mov     rdx, rsi; unsigned __int16 *
0x18000bc34  mov     rcx, rax; this
0x18000bc37  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc3c  mov     r14, rax
0x18000bc3f  call    cs:__imp_GetCurrentThreadId
0x18000bc45  lea     rcx, [rsp+278h+Buffer]
0x18000bc4a  mov     [rsp+278h+var_240], rcx
0x18000bc4f  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000bc53  mov     [rsp+278h+nSize], eax
0x18000bc57  mov     eax, [rbx+44h]
0x18000bc5a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bc5e  mov     r9, rdi; unsigned __int16 *
0x18000bc61  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000bc68  mov     rdx, rsi; unsigned __int16 *
0x18000bc6b  mov     rcx, r14; this
0x18000bc6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc73  cmp     [rbx+18h], r15
0x18000bc77  jnz     short loc_18000BC89
0x18000bc79  cmp     [rbx+48h], r15
0x18000bc7d  jnz     short loc_18000BC89
0x18000bc7f  cmp     [rbx+30h], r15
0x18000bc83  jz      loc_18000BD19
0x18000bc89  lea     r8, asc_18005F9F8; "    "
0x18000bc90  mov     rdx, rsi; unsigned __int16 *
0x18000bc93  mov     rcx, rax; this
0x18000bc96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc9b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000bc9f  test    r9, r9
0x18000bca2  jz      short loc_18000BCB6
0x18000bca4  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000bcab  mov     rdx, rsi; unsigned __int16 *
0x18000bcae  mov     rcx, rax; this
0x18000bcb1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bcb6  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000bcba  test    r9, r9
0x18000bcbd  jz      short loc_18000BCD1
0x18000bcbf  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000bcc6  mov     rdx, rsi; unsigned __int16 *
0x18000bcc9  mov     rcx, rax; this
0x18000bccc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bcd1  mov     rcx, [rbx+28h]
0x18000bcd5  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000bcd9  mov     rdx, rsi; unsigned __int16 *
0x18000bcdc  test    rcx, rcx
0x18000bcdf  jz      short loc_18000BCF7
0x18000bce1  mov     [rsp+278h+lpBuffer], rcx
0x18000bce6  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000bced  mov     rcx, rax; this
0x18000bcf0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bcf5  jmp     short loc_18000BD19
0x18000bcf7  mov     rcx, rax; this
0x18000bcfa  test    r9, r9
0x18000bcfd  jz      short loc_18000BD0D
0x18000bcff  lea     r8, aHs; "[%hs]\n"
0x18000bd06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bd0b  jmp     short loc_18000BD19
0x18000bd0d  lea     r8, asc_18005FA70; "\n"
0x18000bd14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bd19  xor     eax, eax
0x18000bd1b  mov     rcx, [rsp+278h+var_38]
0x18000bd23  xor     rcx, rsp; StackCookie
0x18000bd26  call    __security_check_cookie
0x18000bd2b  mov     rbx, [rsp+278h+arg_18]
0x18000bd33  add     rsp, 250h
0x18000bd3a  pop     r15
0x18000bd3c  pop     r14
0x18000bd3e  pop     rdi
0x18000bd3f  pop     rsi
0x18000bd40  pop     rbp
0x18000bd41  retn
```
