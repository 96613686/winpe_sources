# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800064a4`
- end: `0x18000675a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003d30`
- `0x180003fb0`
- `0x180004244`
- `0x18000a440`
- `0x18002201c`
- `0x180031827`
- `0x18003195b`

## callees

- `0x180002590`
- `0x180003088`
- `0x1800064a4`
- `0x180006ef8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006657`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006657`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800065d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800065d6`

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
          v7 = (const char *)&qword_180036120;
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
0x1800064a4  mov     [rsp+arg_18], rbx
0x1800064a9  push    rbp
0x1800064aa  push    rsi
0x1800064ab  push    rdi
0x1800064ac  push    r14
0x1800064ae  push    r15
0x1800064b0  sub     rsp, 250h
0x1800064b7  mov     rax, cs:__security_cookie
0x1800064be  xor     rax, rsp
0x1800064c1  mov     [rsp+278h+var_38], rax
0x1800064c9  mov     rbx, r8
0x1800064cc  mov     rsi, rdx
0x1800064cf  mov     r14, rcx
0x1800064d2  xor     r15d, r15d
0x1800064d5  test    rdx, rdx
0x1800064d8  jz      loc_180006731
0x1800064de  test    rcx, rcx
0x1800064e1  jz      loc_180006731
0x1800064e7  mov     [rcx], r15w
0x1800064eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800064f2  test    rax, rax
0x1800064f5  jz      short loc_180006518
0x1800064f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800064fe  jz      short loc_180006518
0x180006500  mov     r8, rdx
0x180006503  mov     rdx, rcx
0x180006506  mov     rcx, rbx
0x180006509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650e  cmp     [r14], r15w
0x180006512  jnz     loc_180006731
0x180006518  mov     ecx, [rbx]
0x18000651a  mov     bpl, 8
0x18000651d  test    ecx, ecx
0x18000651f  jz      short loc_18000656A
0x180006521  sub     ecx, 1
0x180006524  jz      short loc_180006552
0x180006526  sub     ecx, 1
0x180006529  jz      short loc_180006542
0x18000652b  cmp     ecx, 1
0x18000652e  jz      short loc_180006539
0x180006530  lea     rdi, qword_180036120
0x180006537  jmp     short loc_180006571
0x180006539  lea     rdi, aFailfast; "FailFast"
0x180006540  jmp     short loc_180006571
0x180006542  lea     rax, aLoghr; "LogHr"
0x180006549  lea     rdi, aLognt; "LogNt"
0x180006550  jmp     short loc_180006560
0x180006552  lea     rax, aReturnhr; "ReturnHr"
0x180006559  lea     rdi, aReturnnt; "ReturnNt"
0x180006560  test    [rbx+4], bpl
0x180006564  cmovz   rdi, rax
0x180006568  jmp     short loc_180006571
0x18000656a  lea     rdi, aException; "Exception"
0x180006571  xor     edx, edx; Val
0x180006573  mov     r8d, 200h; Size
0x180006579  lea     rcx, [rsp+278h+Buffer]; void *
0x18000657e  call    memset_0
0x180006583  test    [rbx+4], bpl
0x180006587  jz      short loc_1800065AC
0x180006589  mov     ebp, [rbx+0Ch]
0x18000658c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006593  test    rax, rax
0x180006596  jz      short loc_1800065DC
0x180006598  mov     r8d, 100h
0x18000659e  lea     rdx, [rsp+278h+Buffer]
0x1800065a3  mov     ecx, ebp
0x1800065a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065aa  jmp     short loc_1800065DC
0x1800065ac  mov     ebp, [rbx+8]
0x1800065af  mov     [rsp+278h+Arguments], r15; Arguments
0x1800065b4  mov     [rsp+278h+nSize], 100h; nSize
0x1800065bc  lea     rax, [rsp+278h+Buffer]
0x1800065c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800065c6  mov     r9d, 400h; dwLanguageId
0x1800065cc  mov     r8d, ebp; dwMessageId
0x1800065cf  xor     edx, edx; lpSource
0x1800065d1  mov     ecx, 1200h; dwFlags
0x1800065d6  call    cs:__imp_FormatMessageW
0x1800065dc  lea     rsi, [r14+rsi*2]
0x1800065e0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800065e4  mov     rax, [rbx+88h]
0x1800065eb  mov     rcx, [rbx+80h]
0x1800065f2  mov     rdx, rsi; unsigned __int16 *
0x1800065f5  test    r9, r9
0x1800065f8  jz      short loc_18000661C
0x1800065fa  mov     [rsp+278h+Arguments], rax
0x1800065ff  mov     qword ptr [rsp+278h+nSize], rcx
0x180006604  mov     eax, [rbx+40h]
0x180006607  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000660b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006612  mov     rcx, r14; this
0x180006615  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000661a  jmp     short loc_180006633
0x18000661c  mov     [rsp+278h+lpBuffer], rax
0x180006621  mov     r9, rcx; unsigned __int16 *
0x180006624  lea     r8, aHsP; "%hs!%p: "
0x18000662b  mov     rcx, r14; this
0x18000662e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006633  mov     r14, rax
0x180006636  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000663d  test    r9, r9
0x180006640  jz      short loc_180006657
0x180006642  lea     r8, aCallerP; "(caller: %p) "
0x180006649  mov     rdx, rsi; unsigned __int16 *
0x18000664c  mov     rcx, rax; this
0x18000664f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006654  mov     r14, rax
0x180006657  call    cs:__imp_GetCurrentThreadId
0x18000665d  lea     rcx, [rsp+278h+Buffer]
0x180006662  mov     [rsp+278h+var_240], rcx
0x180006667  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000666b  mov     [rsp+278h+nSize], eax
0x18000666f  mov     eax, [rbx+44h]
0x180006672  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006676  mov     r9, rdi; unsigned __int16 *
0x180006679  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006680  mov     rdx, rsi; unsigned __int16 *
0x180006683  mov     rcx, r14; this
0x180006686  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000668b  cmp     [rbx+18h], r15
0x18000668f  jnz     short loc_1800066A1
0x180006691  cmp     [rbx+48h], r15
0x180006695  jnz     short loc_1800066A1
0x180006697  cmp     [rbx+30h], r15
0x18000669b  jz      loc_180006731
0x1800066a1  lea     r8, asc_180036228; "    "
0x1800066a8  mov     rdx, rsi; unsigned __int16 *
0x1800066ab  mov     rcx, rax; this
0x1800066ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800066b7  test    r9, r9
0x1800066ba  jz      short loc_1800066CE
0x1800066bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800066c3  mov     rdx, rsi; unsigned __int16 *
0x1800066c6  mov     rcx, rax; this
0x1800066c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800066d2  test    r9, r9
0x1800066d5  jz      short loc_1800066E9
0x1800066d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800066de  mov     rdx, rsi; unsigned __int16 *
0x1800066e1  mov     rcx, rax; this
0x1800066e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066e9  mov     rcx, [rbx+28h]
0x1800066ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800066f1  mov     rdx, rsi; unsigned __int16 *
0x1800066f4  test    rcx, rcx
0x1800066f7  jz      short loc_18000670F
0x1800066f9  mov     [rsp+278h+lpBuffer], rcx
0x1800066fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006705  mov     rcx, rax; this
0x180006708  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000670d  jmp     short loc_180006731
0x18000670f  mov     rcx, rax; this
0x180006712  test    r9, r9
0x180006715  jz      short loc_180006725
0x180006717  lea     r8, aHs; "[%hs]\n"
0x18000671e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006723  jmp     short loc_180006731
0x180006725  lea     r8, asc_1800362A0; "\n"
0x18000672c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006731  xor     eax, eax
0x180006733  mov     rcx, [rsp+278h+var_38]
0x18000673b  xor     rcx, rsp; StackCookie
0x18000673e  call    __security_check_cookie
0x180006743  mov     rbx, [rsp+278h+arg_18]
0x18000674b  add     rsp, 250h
0x180006752  pop     r15
0x180006754  pop     r14
0x180006756  pop     rdi
0x180006757  pop     rsi
0x180006758  pop     rbp
0x180006759  retn
```
