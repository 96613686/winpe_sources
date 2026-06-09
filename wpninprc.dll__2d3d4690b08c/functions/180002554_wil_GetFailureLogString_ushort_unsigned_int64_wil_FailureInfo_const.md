# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002554`
- end: `0x18000280a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003560`
- `0x1800039c0`
- `0x180003c30`
- `0x180004d2c`

## callees

- `0x180001510`
- `0x18000209e`
- `0x180002554`
- `0x180002b00`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002707`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002707`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002686`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002686`

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
          v7 = (const char *)&qword_1800086F0;
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
0x180002554  mov     [rsp+arg_18], rbx
0x180002559  push    rbp
0x18000255a  push    rsi
0x18000255b  push    rdi
0x18000255c  push    r14
0x18000255e  push    r15
0x180002560  sub     rsp, 250h
0x180002567  mov     rax, cs:__security_cookie
0x18000256e  xor     rax, rsp
0x180002571  mov     [rsp+278h+var_38], rax
0x180002579  mov     rbx, r8
0x18000257c  mov     rsi, rdx
0x18000257f  mov     r14, rcx
0x180002582  xor     r15d, r15d
0x180002585  test    rdx, rdx
0x180002588  jz      loc_1800027E1
0x18000258e  test    rcx, rcx
0x180002591  jz      loc_1800027E1
0x180002597  mov     [rcx], r15w
0x18000259b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800025a2  test    rax, rax
0x1800025a5  jz      short loc_1800025C8
0x1800025a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800025ae  jz      short loc_1800025C8
0x1800025b0  mov     r8, rdx
0x1800025b3  mov     rdx, rcx
0x1800025b6  mov     rcx, rbx
0x1800025b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025be  cmp     [r14], r15w
0x1800025c2  jnz     loc_1800027E1
0x1800025c8  mov     ecx, [rbx]
0x1800025ca  mov     bpl, 8
0x1800025cd  test    ecx, ecx
0x1800025cf  jz      short loc_18000261A
0x1800025d1  sub     ecx, 1
0x1800025d4  jz      short loc_180002602
0x1800025d6  sub     ecx, 1
0x1800025d9  jz      short loc_1800025F2
0x1800025db  cmp     ecx, 1
0x1800025de  jz      short loc_1800025E9
0x1800025e0  lea     rdi, qword_1800086F0
0x1800025e7  jmp     short loc_180002621
0x1800025e9  lea     rdi, aFailfast; "FailFast"
0x1800025f0  jmp     short loc_180002621
0x1800025f2  lea     rax, aLoghr; "LogHr"
0x1800025f9  lea     rdi, aLognt; "LogNt"
0x180002600  jmp     short loc_180002610
0x180002602  lea     rax, aReturnhr; "ReturnHr"
0x180002609  lea     rdi, aReturnnt; "ReturnNt"
0x180002610  test    [rbx+4], bpl
0x180002614  cmovz   rdi, rax
0x180002618  jmp     short loc_180002621
0x18000261a  lea     rdi, aException; "Exception"
0x180002621  xor     edx, edx; Val
0x180002623  mov     r8d, 200h; Size
0x180002629  lea     rcx, [rsp+278h+Buffer]; void *
0x18000262e  call    memset_0
0x180002633  test    [rbx+4], bpl
0x180002637  jz      short loc_18000265C
0x180002639  mov     ebp, [rbx+0Ch]
0x18000263c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180002643  test    rax, rax
0x180002646  jz      short loc_18000268C
0x180002648  mov     r8d, 100h
0x18000264e  lea     rdx, [rsp+278h+Buffer]
0x180002653  mov     ecx, ebp
0x180002655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000265a  jmp     short loc_18000268C
0x18000265c  mov     ebp, [rbx+8]
0x18000265f  mov     [rsp+278h+Arguments], r15; Arguments
0x180002664  mov     [rsp+278h+nSize], 100h; nSize
0x18000266c  lea     rax, [rsp+278h+Buffer]
0x180002671  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002676  mov     r9d, 400h; dwLanguageId
0x18000267c  mov     r8d, ebp; dwMessageId
0x18000267f  xor     edx, edx; lpSource
0x180002681  mov     ecx, 1200h; dwFlags
0x180002686  call    cs:__imp_FormatMessageW
0x18000268c  lea     rsi, [r14+rsi*2]
0x180002690  mov     r9, [rbx+38h]; unsigned __int16 *
0x180002694  mov     rax, [rbx+88h]
0x18000269b  mov     rcx, [rbx+80h]
0x1800026a2  mov     rdx, rsi; unsigned __int16 *
0x1800026a5  test    r9, r9
0x1800026a8  jz      short loc_1800026CC
0x1800026aa  mov     [rsp+278h+Arguments], rax
0x1800026af  mov     qword ptr [rsp+278h+nSize], rcx
0x1800026b4  mov     eax, [rbx+40h]
0x1800026b7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800026bb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800026c2  mov     rcx, r14; this
0x1800026c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800026ca  jmp     short loc_1800026E3
0x1800026cc  mov     [rsp+278h+lpBuffer], rax
0x1800026d1  mov     r9, rcx; unsigned __int16 *
0x1800026d4  lea     r8, aHsP; "%hs!%p: "
0x1800026db  mov     rcx, r14; this
0x1800026de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800026e3  mov     r14, rax
0x1800026e6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800026ed  test    r9, r9
0x1800026f0  jz      short loc_180002707
0x1800026f2  lea     r8, aCallerP; "(caller: %p) "
0x1800026f9  mov     rdx, rsi; unsigned __int16 *
0x1800026fc  mov     rcx, rax; this
0x1800026ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002704  mov     r14, rax
0x180002707  call    cs:__imp_GetCurrentThreadId
0x18000270d  lea     rcx, [rsp+278h+Buffer]
0x180002712  mov     [rsp+278h+var_240], rcx
0x180002717  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000271b  mov     [rsp+278h+nSize], eax
0x18000271f  mov     eax, [rbx+44h]
0x180002722  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002726  mov     r9, rdi; unsigned __int16 *
0x180002729  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002730  mov     rdx, rsi; unsigned __int16 *
0x180002733  mov     rcx, r14; this
0x180002736  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000273b  cmp     [rbx+18h], r15
0x18000273f  jnz     short loc_180002751
0x180002741  cmp     [rbx+48h], r15
0x180002745  jnz     short loc_180002751
0x180002747  cmp     [rbx+30h], r15
0x18000274b  jz      loc_1800027E1
0x180002751  lea     r8, asc_1800087F8; "    "
0x180002758  mov     rdx, rsi; unsigned __int16 *
0x18000275b  mov     rcx, rax; this
0x18000275e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002763  mov     r9, [rbx+18h]; unsigned __int16 *
0x180002767  test    r9, r9
0x18000276a  jz      short loc_18000277E
0x18000276c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002773  mov     rdx, rsi; unsigned __int16 *
0x180002776  mov     rcx, rax; this
0x180002779  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000277e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180002782  test    r9, r9
0x180002785  jz      short loc_180002799
0x180002787  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000278e  mov     rdx, rsi; unsigned __int16 *
0x180002791  mov     rcx, rax; this
0x180002794  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002799  mov     rcx, [rbx+28h]
0x18000279d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800027a1  mov     rdx, rsi; unsigned __int16 *
0x1800027a4  test    rcx, rcx
0x1800027a7  jz      short loc_1800027BF
0x1800027a9  mov     [rsp+278h+lpBuffer], rcx
0x1800027ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800027b5  mov     rcx, rax; this
0x1800027b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800027bd  jmp     short loc_1800027E1
0x1800027bf  mov     rcx, rax; this
0x1800027c2  test    r9, r9
0x1800027c5  jz      short loc_1800027D5
0x1800027c7  lea     r8, aHs; "[%hs]\n"
0x1800027ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800027d3  jmp     short loc_1800027E1
0x1800027d5  lea     r8, asc_180008870; "\n"
0x1800027dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800027e1  xor     eax, eax
0x1800027e3  mov     rcx, [rsp+278h+var_38]
0x1800027eb  xor     rcx, rsp; StackCookie
0x1800027ee  call    __security_check_cookie
0x1800027f3  mov     rbx, [rsp+278h+arg_18]
0x1800027fb  add     rsp, 250h
0x180002802  pop     r15
0x180002804  pop     r14
0x180002806  pop     rdi
0x180002807  pop     rsi
0x180002808  pop     rbp
0x180002809  retn
```
