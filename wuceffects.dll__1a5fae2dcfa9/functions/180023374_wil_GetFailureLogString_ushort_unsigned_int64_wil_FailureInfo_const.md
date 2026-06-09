# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180023374`
- end: `0x18002362a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cabc`
- `0x180023d64`
- `0x180025280`

## callees

- `0x180021060`
- `0x180021cec`
- `0x180023374`
- `0x180023a94`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023527`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800234a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800234a6`

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
          v7 = (const char *)&qword_180035490;
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
0x180023374  mov     [rsp+arg_18], rbx
0x180023379  push    rbp
0x18002337a  push    rsi
0x18002337b  push    rdi
0x18002337c  push    r14
0x18002337e  push    r15
0x180023380  sub     rsp, 250h
0x180023387  mov     rax, cs:__security_cookie
0x18002338e  xor     rax, rsp
0x180023391  mov     [rsp+278h+var_38], rax
0x180023399  mov     rbx, r8
0x18002339c  mov     rsi, rdx
0x18002339f  mov     r14, rcx
0x1800233a2  xor     r15d, r15d
0x1800233a5  test    rdx, rdx
0x1800233a8  jz      loc_180023601
0x1800233ae  test    rcx, rcx
0x1800233b1  jz      loc_180023601
0x1800233b7  mov     [rcx], r15w
0x1800233bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800233c2  test    rax, rax
0x1800233c5  jz      short loc_1800233E8
0x1800233c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800233ce  jz      short loc_1800233E8
0x1800233d0  mov     r8, rdx
0x1800233d3  mov     rdx, rcx
0x1800233d6  mov     rcx, rbx
0x1800233d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233de  cmp     [r14], r15w
0x1800233e2  jnz     loc_180023601
0x1800233e8  mov     ecx, [rbx]
0x1800233ea  mov     bpl, 8
0x1800233ed  test    ecx, ecx
0x1800233ef  jz      short loc_18002343A
0x1800233f1  sub     ecx, 1
0x1800233f4  jz      short loc_180023422
0x1800233f6  sub     ecx, 1
0x1800233f9  jz      short loc_180023412
0x1800233fb  cmp     ecx, 1
0x1800233fe  jz      short loc_180023409
0x180023400  lea     rdi, qword_180035490
0x180023407  jmp     short loc_180023441
0x180023409  lea     rdi, aFailfast; "FailFast"
0x180023410  jmp     short loc_180023441
0x180023412  lea     rax, aLoghr; "LogHr"
0x180023419  lea     rdi, aLognt; "LogNt"
0x180023420  jmp     short loc_180023430
0x180023422  lea     rax, aReturnhr; "ReturnHr"
0x180023429  lea     rdi, aReturnnt; "ReturnNt"
0x180023430  test    [rbx+4], bpl
0x180023434  cmovz   rdi, rax
0x180023438  jmp     short loc_180023441
0x18002343a  lea     rdi, aException; "Exception"
0x180023441  xor     edx, edx; Val
0x180023443  mov     r8d, 200h; Size
0x180023449  lea     rcx, [rsp+278h+Buffer]; void *
0x18002344e  call    memset_0
0x180023453  test    [rbx+4], bpl
0x180023457  jz      short loc_18002347C
0x180023459  mov     ebp, [rbx+0Ch]
0x18002345c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180023463  test    rax, rax
0x180023466  jz      short loc_1800234AC
0x180023468  mov     r8d, 100h
0x18002346e  lea     rdx, [rsp+278h+Buffer]
0x180023473  mov     ecx, ebp
0x180023475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002347a  jmp     short loc_1800234AC
0x18002347c  mov     ebp, [rbx+8]
0x18002347f  mov     [rsp+278h+Arguments], r15; Arguments
0x180023484  mov     [rsp+278h+nSize], 100h; nSize
0x18002348c  lea     rax, [rsp+278h+Buffer]
0x180023491  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180023496  mov     r9d, 400h; dwLanguageId
0x18002349c  mov     r8d, ebp; dwMessageId
0x18002349f  xor     edx, edx; lpSource
0x1800234a1  mov     ecx, 1200h; dwFlags
0x1800234a6  call    cs:__imp_FormatMessageW
0x1800234ac  lea     rsi, [r14+rsi*2]
0x1800234b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800234b4  mov     rax, [rbx+88h]
0x1800234bb  mov     rcx, [rbx+80h]
0x1800234c2  mov     rdx, rsi; unsigned __int16 *
0x1800234c5  test    r9, r9
0x1800234c8  jz      short loc_1800234EC
0x1800234ca  mov     [rsp+278h+Arguments], rax
0x1800234cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800234d4  mov     eax, [rbx+40h]
0x1800234d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800234db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800234e2  mov     rcx, r14; this
0x1800234e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800234ea  jmp     short loc_180023503
0x1800234ec  mov     [rsp+278h+lpBuffer], rax
0x1800234f1  mov     r9, rcx; unsigned __int16 *
0x1800234f4  lea     r8, aHsP; "%hs!%p: "
0x1800234fb  mov     rcx, r14; this
0x1800234fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023503  mov     r14, rax
0x180023506  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002350d  test    r9, r9
0x180023510  jz      short loc_180023527
0x180023512  lea     r8, aCallerP; "(caller: %p) "
0x180023519  mov     rdx, rsi; unsigned __int16 *
0x18002351c  mov     rcx, rax; this
0x18002351f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023524  mov     r14, rax
0x180023527  call    cs:__imp_GetCurrentThreadId
0x18002352d  lea     rcx, [rsp+278h+Buffer]
0x180023532  mov     [rsp+278h+var_240], rcx
0x180023537  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002353b  mov     [rsp+278h+nSize], eax
0x18002353f  mov     eax, [rbx+44h]
0x180023542  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180023546  mov     r9, rdi; unsigned __int16 *
0x180023549  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180023550  mov     rdx, rsi; unsigned __int16 *
0x180023553  mov     rcx, r14; this
0x180023556  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002355b  cmp     [rbx+18h], r15
0x18002355f  jnz     short loc_180023571
0x180023561  cmp     [rbx+48h], r15
0x180023565  jnz     short loc_180023571
0x180023567  cmp     [rbx+30h], r15
0x18002356b  jz      loc_180023601
0x180023571  lea     r8, asc_180035598; "    "
0x180023578  mov     rdx, rsi; unsigned __int16 *
0x18002357b  mov     rcx, rax; this
0x18002357e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023583  mov     r9, [rbx+18h]; unsigned __int16 *
0x180023587  test    r9, r9
0x18002358a  jz      short loc_18002359E
0x18002358c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180023593  mov     rdx, rsi; unsigned __int16 *
0x180023596  mov     rcx, rax; this
0x180023599  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002359e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800235a2  test    r9, r9
0x1800235a5  jz      short loc_1800235B9
0x1800235a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800235ae  mov     rdx, rsi; unsigned __int16 *
0x1800235b1  mov     rcx, rax; this
0x1800235b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800235b9  mov     rcx, [rbx+28h]
0x1800235bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800235c1  mov     rdx, rsi; unsigned __int16 *
0x1800235c4  test    rcx, rcx
0x1800235c7  jz      short loc_1800235DF
0x1800235c9  mov     [rsp+278h+lpBuffer], rcx
0x1800235ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800235d5  mov     rcx, rax; this
0x1800235d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800235dd  jmp     short loc_180023601
0x1800235df  mov     rcx, rax; this
0x1800235e2  test    r9, r9
0x1800235e5  jz      short loc_1800235F5
0x1800235e7  lea     r8, aHs; "[%hs]\n"
0x1800235ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800235f3  jmp     short loc_180023601
0x1800235f5  lea     r8, asc_180035610; "\n"
0x1800235fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023601  xor     eax, eax
0x180023603  mov     rcx, [rsp+278h+var_38]
0x18002360b  xor     rcx, rsp; StackCookie
0x18002360e  call    __security_check_cookie
0x180023613  mov     rbx, [rsp+278h+arg_18]
0x18002361b  add     rsp, 250h
0x180023622  pop     r15
0x180023624  pop     r14
0x180023626  pop     rdi
0x180023627  pop     rsi
0x180023628  pop     rbp
0x180023629  retn
```
