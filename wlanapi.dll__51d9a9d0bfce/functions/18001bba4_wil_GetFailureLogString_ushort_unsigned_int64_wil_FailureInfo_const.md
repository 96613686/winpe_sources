# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001bba4`
- end: `0x18001be5a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bfdc`
- `0x18001c750`
- `0x18001c9b8`
- `0x18001d01c`

## callees

- `0x180019a20`
- `0x18001a5bc`
- `0x18001bba4`
- `0x18001bf8c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bd57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bd57`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001bcd6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001bcd6`

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
          v7 = (const char *)&dword_180070C84;
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
0x18001bba4  mov     [rsp+arg_18], rbx
0x18001bba9  push    rbp
0x18001bbaa  push    rsi
0x18001bbab  push    rdi
0x18001bbac  push    r14
0x18001bbae  push    r15
0x18001bbb0  sub     rsp, 250h
0x18001bbb7  mov     rax, cs:__security_cookie
0x18001bbbe  xor     rax, rsp
0x18001bbc1  mov     [rsp+278h+var_38], rax
0x18001bbc9  mov     rbx, r8
0x18001bbcc  mov     rsi, rdx
0x18001bbcf  mov     r14, rcx
0x18001bbd2  xor     r15d, r15d
0x18001bbd5  test    rdx, rdx
0x18001bbd8  jz      loc_18001BE31
0x18001bbde  test    rcx, rcx
0x18001bbe1  jz      loc_18001BE31
0x18001bbe7  mov     [rcx], r15w
0x18001bbeb  mov     rax, cs:g_pfnResultLoggingCallback
0x18001bbf2  test    rax, rax
0x18001bbf5  jz      short loc_18001BC18
0x18001bbf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001bbfe  jz      short loc_18001BC18
0x18001bc00  mov     r8, rdx
0x18001bc03  mov     rdx, rcx
0x18001bc06  mov     rcx, rbx
0x18001bc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc0e  cmp     [r14], r15w
0x18001bc12  jnz     loc_18001BE31
0x18001bc18  mov     ecx, [rbx]
0x18001bc1a  mov     bpl, 8
0x18001bc1d  test    ecx, ecx
0x18001bc1f  jz      short loc_18001BC6A
0x18001bc21  sub     ecx, 1
0x18001bc24  jz      short loc_18001BC52
0x18001bc26  sub     ecx, 1
0x18001bc29  jz      short loc_18001BC42
0x18001bc2b  cmp     ecx, 1
0x18001bc2e  jz      short loc_18001BC39
0x18001bc30  lea     rdi, dword_180070C84
0x18001bc37  jmp     short loc_18001BC71
0x18001bc39  lea     rdi, aFailfast; "FailFast"
0x18001bc40  jmp     short loc_18001BC71
0x18001bc42  lea     rax, aLoghr; "LogHr"
0x18001bc49  lea     rdi, aLognt; "LogNt"
0x18001bc50  jmp     short loc_18001BC60
0x18001bc52  lea     rax, aReturnhr; "ReturnHr"
0x18001bc59  lea     rdi, aReturnnt; "ReturnNt"
0x18001bc60  test    [rbx+4], bpl
0x18001bc64  cmovz   rdi, rax
0x18001bc68  jmp     short loc_18001BC71
0x18001bc6a  lea     rdi, aException; "Exception"
0x18001bc71  xor     edx, edx; Val
0x18001bc73  mov     r8d, 200h; Size
0x18001bc79  lea     rcx, [rsp+278h+Buffer]; void *
0x18001bc7e  call    memset_0
0x18001bc83  test    [rbx+4], bpl
0x18001bc87  jz      short loc_18001BCAC
0x18001bc89  mov     ebp, [rbx+0Ch]
0x18001bc8c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001bc93  test    rax, rax
0x18001bc96  jz      short loc_18001BCDC
0x18001bc98  mov     r8d, 100h
0x18001bc9e  lea     rdx, [rsp+278h+Buffer]
0x18001bca3  mov     ecx, ebp
0x18001bca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcaa  jmp     short loc_18001BCDC
0x18001bcac  mov     ebp, [rbx+8]
0x18001bcaf  mov     [rsp+278h+Arguments], r15; Arguments
0x18001bcb4  mov     [rsp+278h+nSize], 100h; nSize
0x18001bcbc  lea     rax, [rsp+278h+Buffer]
0x18001bcc1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001bcc6  mov     r9d, 400h; dwLanguageId
0x18001bccc  mov     r8d, ebp; dwMessageId
0x18001bccf  xor     edx, edx; lpSource
0x18001bcd1  mov     ecx, 1200h; dwFlags
0x18001bcd6  call    cs:__imp_FormatMessageW
0x18001bcdc  lea     rsi, [r14+rsi*2]
0x18001bce0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001bce4  mov     rax, [rbx+88h]
0x18001bceb  mov     rcx, [rbx+80h]
0x18001bcf2  mov     rdx, rsi; unsigned __int16 *
0x18001bcf5  test    r9, r9
0x18001bcf8  jz      short loc_18001BD1C
0x18001bcfa  mov     [rsp+278h+Arguments], rax
0x18001bcff  mov     qword ptr [rsp+278h+nSize], rcx
0x18001bd04  mov     eax, [rbx+40h]
0x18001bd07  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001bd0b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001bd12  mov     rcx, r14; this
0x18001bd15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd1a  jmp     short loc_18001BD33
0x18001bd1c  mov     [rsp+278h+lpBuffer], rax
0x18001bd21  mov     r9, rcx; unsigned __int16 *
0x18001bd24  lea     r8, aHsP; "%hs!%p: "
0x18001bd2b  mov     rcx, r14; this
0x18001bd2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd33  mov     r14, rax
0x18001bd36  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001bd3d  test    r9, r9
0x18001bd40  jz      short loc_18001BD57
0x18001bd42  lea     r8, aCallerP; "(caller: %p) "
0x18001bd49  mov     rdx, rsi; unsigned __int16 *
0x18001bd4c  mov     rcx, rax; this
0x18001bd4f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd54  mov     r14, rax
0x18001bd57  call    cs:__imp_GetCurrentThreadId
0x18001bd5d  lea     rcx, [rsp+278h+Buffer]
0x18001bd62  mov     [rsp+278h+var_240], rcx
0x18001bd67  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001bd6b  mov     [rsp+278h+nSize], eax
0x18001bd6f  mov     eax, [rbx+44h]
0x18001bd72  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001bd76  mov     r9, rdi; unsigned __int16 *
0x18001bd79  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001bd80  mov     rdx, rsi; unsigned __int16 *
0x18001bd83  mov     rcx, r14; this
0x18001bd86  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd8b  cmp     [rbx+18h], r15
0x18001bd8f  jnz     short loc_18001BDA1
0x18001bd91  cmp     [rbx+48h], r15
0x18001bd95  jnz     short loc_18001BDA1
0x18001bd97  cmp     [rbx+30h], r15
0x18001bd9b  jz      loc_18001BE31
0x18001bda1  lea     r8, asc_180071120; "    "
0x18001bda8  mov     rdx, rsi; unsigned __int16 *
0x18001bdab  mov     rcx, rax; this
0x18001bdae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bdb3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001bdb7  test    r9, r9
0x18001bdba  jz      short loc_18001BDCE
0x18001bdbc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001bdc3  mov     rdx, rsi; unsigned __int16 *
0x18001bdc6  mov     rcx, rax; this
0x18001bdc9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bdce  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001bdd2  test    r9, r9
0x18001bdd5  jz      short loc_18001BDE9
0x18001bdd7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001bdde  mov     rdx, rsi; unsigned __int16 *
0x18001bde1  mov     rcx, rax; this
0x18001bde4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bde9  mov     rcx, [rbx+28h]
0x18001bded  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001bdf1  mov     rdx, rsi; unsigned __int16 *
0x18001bdf4  test    rcx, rcx
0x18001bdf7  jz      short loc_18001BE0F
0x18001bdf9  mov     [rsp+278h+lpBuffer], rcx
0x18001bdfe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001be05  mov     rcx, rax; this
0x18001be08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001be0d  jmp     short loc_18001BE31
0x18001be0f  mov     rcx, rax; this
0x18001be12  test    r9, r9
0x18001be15  jz      short loc_18001BE25
0x18001be17  lea     r8, aHs; "[%hs]\n"
0x18001be1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001be23  jmp     short loc_18001BE31
0x18001be25  lea     r8, psz; "\n"
0x18001be2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001be31  xor     eax, eax
0x18001be33  mov     rcx, [rsp+278h+var_38]
0x18001be3b  xor     rcx, rsp; StackCookie
0x18001be3e  call    __security_check_cookie
0x18001be43  mov     rbx, [rsp+278h+arg_18]
0x18001be4b  add     rsp, 250h
0x18001be52  pop     r15
0x18001be54  pop     r14
0x18001be56  pop     rdi
0x18001be57  pop     rsi
0x18001be58  pop     rbp
0x18001be59  retn
```
