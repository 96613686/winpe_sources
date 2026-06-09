# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004354`
- end: `0x14000460a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140002f78`
- `0x1400031e8`
- `0x140004cc0`
- `0x140006380`
- `0x140006aec`

## callees

- `0x140002130`
- `0x140002c38`
- `0x140004354`
- `0x140004fc0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004507`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004507`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004486`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004486`

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
          v7 = (const char *)&byte_14000D9AF;
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
0x140004354  mov     [rsp+arg_18], rbx
0x140004359  push    rbp
0x14000435a  push    rsi
0x14000435b  push    rdi
0x14000435c  push    r14
0x14000435e  push    r15
0x140004360  sub     rsp, 250h
0x140004367  mov     rax, cs:__security_cookie
0x14000436e  xor     rax, rsp
0x140004371  mov     [rsp+278h+var_38], rax
0x140004379  mov     rbx, r8
0x14000437c  mov     rsi, rdx
0x14000437f  mov     r14, rcx
0x140004382  xor     r15d, r15d
0x140004385  test    rdx, rdx
0x140004388  jz      loc_1400045E1
0x14000438e  test    rcx, rcx
0x140004391  jz      loc_1400045E1
0x140004397  mov     [rcx], r15w
0x14000439b  mov     rax, cs:g_pfnResultLoggingCallback
0x1400043a2  test    rax, rax
0x1400043a5  jz      short loc_1400043C8
0x1400043a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400043ae  jz      short loc_1400043C8
0x1400043b0  mov     r8, rdx
0x1400043b3  mov     rdx, rcx
0x1400043b6  mov     rcx, rbx
0x1400043b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043be  cmp     [r14], r15w
0x1400043c2  jnz     loc_1400045E1
0x1400043c8  mov     ecx, [rbx]
0x1400043ca  mov     bpl, 8
0x1400043cd  test    ecx, ecx
0x1400043cf  jz      short loc_14000441A
0x1400043d1  sub     ecx, 1
0x1400043d4  jz      short loc_140004402
0x1400043d6  sub     ecx, 1
0x1400043d9  jz      short loc_1400043F2
0x1400043db  cmp     ecx, 1
0x1400043de  jz      short loc_1400043E9
0x1400043e0  lea     rdi, byte_14000D9AF
0x1400043e7  jmp     short loc_140004421
0x1400043e9  lea     rdi, aFailfast; "FailFast"
0x1400043f0  jmp     short loc_140004421
0x1400043f2  lea     rax, aLoghr; "LogHr"
0x1400043f9  lea     rdi, aLognt; "LogNt"
0x140004400  jmp     short loc_140004410
0x140004402  lea     rax, aReturnhr; "ReturnHr"
0x140004409  lea     rdi, aReturnnt; "ReturnNt"
0x140004410  test    [rbx+4], bpl
0x140004414  cmovz   rdi, rax
0x140004418  jmp     short loc_140004421
0x14000441a  lea     rdi, aException; "Exception"
0x140004421  xor     edx, edx; Val
0x140004423  mov     r8d, 200h; Size
0x140004429  lea     rcx, [rsp+278h+Buffer]; void *
0x14000442e  call    memset_0
0x140004433  test    [rbx+4], bpl
0x140004437  jz      short loc_14000445C
0x140004439  mov     ebp, [rbx+0Ch]
0x14000443c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004443  test    rax, rax
0x140004446  jz      short loc_14000448C
0x140004448  mov     r8d, 100h
0x14000444e  lea     rdx, [rsp+278h+Buffer]
0x140004453  mov     ecx, ebp
0x140004455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000445a  jmp     short loc_14000448C
0x14000445c  mov     ebp, [rbx+8]
0x14000445f  mov     [rsp+278h+Arguments], r15; Arguments
0x140004464  mov     [rsp+278h+nSize], 100h; nSize
0x14000446c  lea     rax, [rsp+278h+Buffer]
0x140004471  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004476  mov     r9d, 400h; dwLanguageId
0x14000447c  mov     r8d, ebp; dwMessageId
0x14000447f  xor     edx, edx; lpSource
0x140004481  mov     ecx, 1200h; dwFlags
0x140004486  call    cs:__imp_FormatMessageW
0x14000448c  lea     rsi, [r14+rsi*2]
0x140004490  mov     r9, [rbx+38h]; unsigned __int16 *
0x140004494  mov     rax, [rbx+88h]
0x14000449b  mov     rcx, [rbx+80h]
0x1400044a2  mov     rdx, rsi; unsigned __int16 *
0x1400044a5  test    r9, r9
0x1400044a8  jz      short loc_1400044CC
0x1400044aa  mov     [rsp+278h+Arguments], rax
0x1400044af  mov     qword ptr [rsp+278h+nSize], rcx
0x1400044b4  mov     eax, [rbx+40h]
0x1400044b7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400044bb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400044c2  mov     rcx, r14; this
0x1400044c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044ca  jmp     short loc_1400044E3
0x1400044cc  mov     [rsp+278h+lpBuffer], rax
0x1400044d1  mov     r9, rcx; unsigned __int16 *
0x1400044d4  lea     r8, aHsP; "%hs!%p: "
0x1400044db  mov     rcx, r14; this
0x1400044de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044e3  mov     r14, rax
0x1400044e6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400044ed  test    r9, r9
0x1400044f0  jz      short loc_140004507
0x1400044f2  lea     r8, aCallerP; "(caller: %p) "
0x1400044f9  mov     rdx, rsi; unsigned __int16 *
0x1400044fc  mov     rcx, rax; this
0x1400044ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004504  mov     r14, rax
0x140004507  call    cs:__imp_GetCurrentThreadId
0x14000450d  lea     rcx, [rsp+278h+Buffer]
0x140004512  mov     [rsp+278h+var_240], rcx
0x140004517  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000451b  mov     [rsp+278h+nSize], eax
0x14000451f  mov     eax, [rbx+44h]
0x140004522  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004526  mov     r9, rdi; unsigned __int16 *
0x140004529  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004530  mov     rdx, rsi; unsigned __int16 *
0x140004533  mov     rcx, r14; this
0x140004536  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000453b  cmp     [rbx+18h], r15
0x14000453f  jnz     short loc_140004551
0x140004541  cmp     [rbx+48h], r15
0x140004545  jnz     short loc_140004551
0x140004547  cmp     [rbx+30h], r15
0x14000454b  jz      loc_1400045E1
0x140004551  lea     r8, asc_14000DAB0; "    "
0x140004558  mov     rdx, rsi; unsigned __int16 *
0x14000455b  mov     rcx, rax; this
0x14000455e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004563  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004567  test    r9, r9
0x14000456a  jz      short loc_14000457E
0x14000456c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004573  mov     rdx, rsi; unsigned __int16 *
0x140004576  mov     rcx, rax; this
0x140004579  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000457e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140004582  test    r9, r9
0x140004585  jz      short loc_140004599
0x140004587  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000458e  mov     rdx, rsi; unsigned __int16 *
0x140004591  mov     rcx, rax; this
0x140004594  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004599  mov     rcx, [rbx+28h]
0x14000459d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400045a1  mov     rdx, rsi; unsigned __int16 *
0x1400045a4  test    rcx, rcx
0x1400045a7  jz      short loc_1400045BF
0x1400045a9  mov     [rsp+278h+lpBuffer], rcx
0x1400045ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400045b5  mov     rcx, rax; this
0x1400045b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045bd  jmp     short loc_1400045E1
0x1400045bf  mov     rcx, rax; this
0x1400045c2  test    r9, r9
0x1400045c5  jz      short loc_1400045D5
0x1400045c7  lea     r8, aHs; "[%hs]\n"
0x1400045ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045d3  jmp     short loc_1400045E1
0x1400045d5  lea     r8, asc_14000DB28; "\n"
0x1400045dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045e1  xor     eax, eax
0x1400045e3  mov     rcx, [rsp+278h+var_38]
0x1400045eb  xor     rcx, rsp; StackCookie
0x1400045ee  call    __security_check_cookie
0x1400045f3  mov     rbx, [rsp+278h+arg_18]
0x1400045fb  add     rsp, 250h
0x140004602  pop     r15
0x140004604  pop     r14
0x140004606  pop     rdi
0x140004607  pop     rsi
0x140004608  pop     rbp
0x140004609  retn
```
