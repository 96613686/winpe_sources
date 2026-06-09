# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b8f0`
- end: `0x18000bbb1`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180009408`
- `0x180009680`
- `0x18000c7f4`

## callees

- `0x18000b8f0`
- `0x18000cb04`
- `0x180011a62`
- `0x180011a90`
- `0x180013010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000ba20`
- `KERNEL32!FormatMessageW` at `0x18000ba20`
- `KERNEL32!GetCurrentThreadId` at `0x18000baa7`
- `KERNEL32!GetCurrentThreadId` at `0x18000baa7`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rsi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdi
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
  v8 = (const char *)&word_1800160FE;
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
        goto LABEL_17;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_17;
  }
  v8 = "Exception";
LABEL_17:
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
0x18000b8f0  mov     [rsp+arg_18], rbx
0x18000b8f5  push    rbp
0x18000b8f6  push    rsi
0x18000b8f7  push    rdi
0x18000b8f8  push    r14
0x18000b8fa  push    r15
0x18000b8fc  sub     rsp, 250h
0x18000b903  mov     rax, cs:__security_cookie
0x18000b90a  xor     rax, rsp
0x18000b90d  mov     [rsp+278h+var_38], rax
0x18000b915  xor     r15d, r15d
0x18000b918  mov     rbx, r8
0x18000b91b  mov     rdi, rdx
0x18000b91e  mov     r14, rcx
0x18000b921  test    rdx, rdx
0x18000b924  jz      loc_18000BB87
0x18000b92a  test    rcx, rcx
0x18000b92d  jz      loc_18000BB87
0x18000b933  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b93a  mov     [rcx], r15w
0x18000b93e  test    rax, rax
0x18000b941  jz      short loc_18000B964
0x18000b943  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b94a  jz      short loc_18000B964
0x18000b94c  mov     r8, rdx
0x18000b94f  mov     rdx, rcx
0x18000b952  mov     rcx, rbx
0x18000b955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b95a  cmp     [r14], r15w
0x18000b95e  jnz     loc_18000BB87
0x18000b964  mov     ecx, [rbx]
0x18000b966  lea     rsi, word_1800160FE
0x18000b96d  mov     bpl, 8
0x18000b970  test    ecx, ecx
0x18000b972  jz      short loc_18000B9B4
0x18000b974  sub     ecx, 1
0x18000b977  jz      short loc_18000B99C
0x18000b979  sub     ecx, 1
0x18000b97c  jz      short loc_18000B98C
0x18000b97e  cmp     ecx, 1
0x18000b981  jnz     short loc_18000B9BB
0x18000b983  lea     rsi, aFailfast; "FailFast"
0x18000b98a  jmp     short loc_18000B9BB
0x18000b98c  lea     rax, aLoghr; "LogHr"
0x18000b993  lea     rsi, aLognt; "LogNt"
0x18000b99a  jmp     short loc_18000B9AA
0x18000b99c  lea     rax, aReturnhr; "ReturnHr"
0x18000b9a3  lea     rsi, aReturnnt; "ReturnNt"
0x18000b9aa  test    [rbx+4], bpl
0x18000b9ae  cmovz   rsi, rax
0x18000b9b2  jmp     short loc_18000B9BB
0x18000b9b4  lea     rsi, aException; "Exception"
0x18000b9bb  xor     edx, edx; Val
0x18000b9bd  lea     rcx, [rsp+278h+Buffer]; void *
0x18000b9c2  mov     r8d, 200h; Size
0x18000b9c8  call    memset_0
0x18000b9cd  test    [rbx+4], bpl
0x18000b9d1  jz      short loc_18000B9F6
0x18000b9d3  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000b9da  mov     ebp, [rbx+0Ch]
0x18000b9dd  test    rax, rax
0x18000b9e0  jz      short loc_18000BA2C
0x18000b9e2  mov     r8d, 100h
0x18000b9e8  lea     rdx, [rsp+278h+Buffer]
0x18000b9ed  mov     ecx, ebp
0x18000b9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f4  jmp     short loc_18000BA2C
0x18000b9f6  mov     ebp, [rbx+8]
0x18000b9f9  lea     rax, [rsp+278h+Buffer]
0x18000b9fe  mov     [rsp+278h+Arguments], r15; Arguments
0x18000ba03  mov     r8d, ebp; dwMessageId
0x18000ba06  mov     [rsp+278h+nSize], 100h; nSize
0x18000ba0e  mov     r9d, 400h; dwLanguageId
0x18000ba14  xor     edx, edx; lpSource
0x18000ba16  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000ba1b  mov     ecx, 1200h; dwFlags
0x18000ba20  call    cs:__imp_FormatMessageW
0x18000ba27  nop     dword ptr [rax+rax+00h]
0x18000ba2c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000ba30  lea     rdi, [r14+rdi*2]
0x18000ba34  mov     rax, [rbx+88h]
0x18000ba3b  mov     rdx, rdi; unsigned __int16 *
0x18000ba3e  mov     rcx, [rbx+80h]
0x18000ba45  test    r9, r9
0x18000ba48  jz      short loc_18000BA6C
0x18000ba4a  mov     [rsp+278h+Arguments], rax
0x18000ba4f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000ba56  mov     eax, [rbx+40h]
0x18000ba59  mov     qword ptr [rsp+278h+nSize], rcx
0x18000ba5e  mov     rcx, r14; this
0x18000ba61  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ba65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ba6a  jmp     short loc_18000BA83
0x18000ba6c  mov     r9, rcx; unsigned __int16 *
0x18000ba6f  mov     [rsp+278h+lpBuffer], rax
0x18000ba74  mov     rcx, r14; this
0x18000ba77  lea     r8, aHsP; "%hs!%p: "
0x18000ba7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ba83  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000ba8a  mov     r14, rax
0x18000ba8d  test    r9, r9
0x18000ba90  jz      short loc_18000BAA7
0x18000ba92  lea     r8, aCallerP; "(caller: %p) "
0x18000ba99  mov     rdx, rdi; unsigned __int16 *
0x18000ba9c  mov     rcx, rax; this
0x18000ba9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000baa4  mov     r14, rax
0x18000baa7  call    cs:__imp_GetCurrentThreadId
0x18000baae  nop     dword ptr [rax+rax+00h]
0x18000bab3  mov     ecx, [rbx+44h]
0x18000bab6  lea     rdx, [rsp+278h+Buffer]
0x18000babb  mov     [rsp+278h+var_240], rdx
0x18000bac0  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000bac7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000bacb  mov     r9, rsi; unsigned __int16 *
0x18000bace  mov     [rsp+278h+nSize], eax
0x18000bad2  mov     rdx, rdi; unsigned __int16 *
0x18000bad5  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x18000bad9  mov     rcx, r14; this
0x18000badc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bae1  cmp     [rbx+18h], r15
0x18000bae5  jnz     short loc_18000BAF7
0x18000bae7  cmp     [rbx+48h], r15
0x18000baeb  jnz     short loc_18000BAF7
0x18000baed  cmp     [rbx+30h], r15
0x18000baf1  jz      loc_18000BB87
0x18000baf7  lea     r8, asc_180017008; "    "
0x18000bafe  mov     rdx, rdi; unsigned __int16 *
0x18000bb01  mov     rcx, rax; this
0x18000bb04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb09  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000bb0d  test    r9, r9
0x18000bb10  jz      short loc_18000BB24
0x18000bb12  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000bb19  mov     rdx, rdi; unsigned __int16 *
0x18000bb1c  mov     rcx, rax; this
0x18000bb1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb24  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000bb28  test    r9, r9
0x18000bb2b  jz      short loc_18000BB3F
0x18000bb2d  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000bb34  mov     rdx, rdi; unsigned __int16 *
0x18000bb37  mov     rcx, rax; this
0x18000bb3a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb3f  mov     rcx, [rbx+28h]
0x18000bb43  mov     rdx, rdi; unsigned __int16 *
0x18000bb46  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000bb4a  test    rcx, rcx
0x18000bb4d  jz      short loc_18000BB65
0x18000bb4f  mov     [rsp+278h+lpBuffer], rcx
0x18000bb54  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000bb5b  mov     rcx, rax; this
0x18000bb5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb63  jmp     short loc_18000BB87
0x18000bb65  mov     rcx, rax; this
0x18000bb68  test    r9, r9
0x18000bb6b  jz      short loc_18000BB7B
0x18000bb6d  lea     r8, aHs; "[%hs]\n"
0x18000bb74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb79  jmp     short loc_18000BB87
0x18000bb7b  lea     r8, asc_180017080; "\n"
0x18000bb82  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb87  xor     eax, eax
0x18000bb89  mov     rcx, [rsp+278h+var_38]
0x18000bb91  xor     rcx, rsp; StackCookie
0x18000bb94  call    __security_check_cookie
0x18000bb99  mov     rbx, [rsp+278h+arg_18]
0x18000bba1  add     rsp, 250h
0x18000bba8  pop     r15
0x18000bbaa  pop     r14
0x18000bbac  pop     rdi
0x18000bbad  pop     rsi
0x18000bbae  pop     rbp
0x18000bbaf  retn
```
