# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400030b4`
- end: `0x14000336a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140001f48`
- `0x1400021b0`
- `0x140003a14`

## callees

- `0x140001a63`
- `0x1400030b4`
- `0x140003d14`
- `0x140014910`
- `0x140015010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1400031e6`
- `KERNEL32!FormatMessageW` at `0x1400031e6`
- `KERNEL32!GetCurrentThreadId` at `0x140003267`
- `KERNEL32!GetCurrentThreadId` at `0x140003267`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
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
        else
          v8 = (const char *)&qword_140016C40;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
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
0x1400030b4  mov     [rsp+arg_18], rbx
0x1400030b9  push    rbp
0x1400030ba  push    rsi
0x1400030bb  push    rdi
0x1400030bc  push    r14
0x1400030be  push    r15
0x1400030c0  sub     rsp, 250h
0x1400030c7  mov     rax, cs:__security_cookie
0x1400030ce  xor     rax, rsp
0x1400030d1  mov     [rsp+278h+var_38], rax
0x1400030d9  xor     r15d, r15d
0x1400030dc  mov     rbx, r8
0x1400030df  mov     rsi, rdx
0x1400030e2  mov     r14, rcx
0x1400030e5  test    rdx, rdx
0x1400030e8  jz      loc_140003341
0x1400030ee  test    rcx, rcx
0x1400030f1  jz      loc_140003341
0x1400030f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400030fe  mov     [rcx], r15w
0x140003102  test    rax, rax
0x140003105  jz      short loc_140003128
0x140003107  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000310e  jz      short loc_140003128
0x140003110  mov     r8, rdx
0x140003113  mov     rdx, rcx
0x140003116  mov     rcx, rbx
0x140003119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000311e  cmp     [r14], r15w
0x140003122  jnz     loc_140003341
0x140003128  mov     ecx, [rbx]
0x14000312a  mov     bpl, 8
0x14000312d  test    ecx, ecx
0x14000312f  jz      short loc_14000317A
0x140003131  sub     ecx, 1
0x140003134  jz      short loc_140003162
0x140003136  sub     ecx, 1
0x140003139  jz      short loc_140003152
0x14000313b  cmp     ecx, 1
0x14000313e  jz      short loc_140003149
0x140003140  lea     rdi, qword_140016C40
0x140003147  jmp     short loc_140003181
0x140003149  lea     rdi, aFailfast; "FailFast"
0x140003150  jmp     short loc_140003181
0x140003152  lea     rax, aLoghr; "LogHr"
0x140003159  lea     rdi, aLognt; "LogNt"
0x140003160  jmp     short loc_140003170
0x140003162  lea     rax, aReturnhr; "ReturnHr"
0x140003169  lea     rdi, aReturnnt; "ReturnNt"
0x140003170  test    [rbx+4], bpl
0x140003174  cmovz   rdi, rax
0x140003178  jmp     short loc_140003181
0x14000317a  lea     rdi, aException; "Exception"
0x140003181  xor     edx, edx; Val
0x140003183  lea     rcx, [rsp+278h+Buffer]; void *
0x140003188  mov     r8d, 200h; Size
0x14000318e  call    memset_0
0x140003193  test    [rbx+4], bpl
0x140003197  jz      short loc_1400031BC
0x140003199  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400031a0  mov     ebp, [rbx+0Ch]
0x1400031a3  test    rax, rax
0x1400031a6  jz      short loc_1400031EC
0x1400031a8  mov     r8d, 100h
0x1400031ae  lea     rdx, [rsp+278h+Buffer]
0x1400031b3  mov     ecx, ebp
0x1400031b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031ba  jmp     short loc_1400031EC
0x1400031bc  mov     ebp, [rbx+8]
0x1400031bf  lea     rax, [rsp+278h+Buffer]
0x1400031c4  mov     [rsp+278h+Arguments], r15; Arguments
0x1400031c9  mov     r8d, ebp; dwMessageId
0x1400031cc  mov     [rsp+278h+nSize], 100h; nSize
0x1400031d4  mov     r9d, 400h; dwLanguageId
0x1400031da  xor     edx, edx; lpSource
0x1400031dc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400031e1  mov     ecx, 1200h; dwFlags
0x1400031e6  call    cs:__imp_FormatMessageW
0x1400031ec  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400031f0  lea     rsi, [r14+rsi*2]
0x1400031f4  mov     rax, [rbx+88h]
0x1400031fb  mov     rdx, rsi; unsigned __int16 *
0x1400031fe  mov     rcx, [rbx+80h]
0x140003205  test    r9, r9
0x140003208  jz      short loc_14000322C
0x14000320a  mov     [rsp+278h+Arguments], rax
0x14000320f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003216  mov     eax, [rbx+40h]
0x140003219  mov     qword ptr [rsp+278h+nSize], rcx
0x14000321e  mov     rcx, r14; this
0x140003221  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003225  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000322a  jmp     short loc_140003243
0x14000322c  mov     r9, rcx; unsigned __int16 *
0x14000322f  mov     [rsp+278h+lpBuffer], rax
0x140003234  mov     rcx, r14; this
0x140003237  lea     r8, aHsP; "%hs!%p: "
0x14000323e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003243  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000324a  mov     r14, rax
0x14000324d  test    r9, r9
0x140003250  jz      short loc_140003267
0x140003252  lea     r8, aCallerP; "(caller: %p) "
0x140003259  mov     rdx, rsi; unsigned __int16 *
0x14000325c  mov     rcx, rax; this
0x14000325f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003264  mov     r14, rax
0x140003267  call    cs:__imp_GetCurrentThreadId
0x14000326d  lea     rcx, [rsp+278h+Buffer]
0x140003272  mov     r9, rdi; unsigned __int16 *
0x140003275  mov     [rsp+278h+var_240], rcx
0x14000327a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003281  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003285  mov     rdx, rsi; unsigned __int16 *
0x140003288  mov     [rsp+278h+nSize], eax
0x14000328c  mov     rcx, r14; this
0x14000328f  mov     eax, [rbx+44h]
0x140003292  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003296  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000329b  cmp     [rbx+18h], r15
0x14000329f  jnz     short loc_1400032B1
0x1400032a1  cmp     [rbx+48h], r15
0x1400032a5  jnz     short loc_1400032B1
0x1400032a7  cmp     [rbx+30h], r15
0x1400032ab  jz      loc_140003341
0x1400032b1  lea     r8, asc_140016D40; "    "
0x1400032b8  mov     rdx, rsi; unsigned __int16 *
0x1400032bb  mov     rcx, rax; this
0x1400032be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400032c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400032c7  test    r9, r9
0x1400032ca  jz      short loc_1400032DE
0x1400032cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400032d3  mov     rdx, rsi; unsigned __int16 *
0x1400032d6  mov     rcx, rax; this
0x1400032d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400032de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400032e2  test    r9, r9
0x1400032e5  jz      short loc_1400032F9
0x1400032e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400032ee  mov     rdx, rsi; unsigned __int16 *
0x1400032f1  mov     rcx, rax; this
0x1400032f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400032f9  mov     rcx, [rbx+28h]
0x1400032fd  mov     rdx, rsi; unsigned __int16 *
0x140003300  mov     r9, [rbx+30h]; unsigned __int16 *
0x140003304  test    rcx, rcx
0x140003307  jz      short loc_14000331F
0x140003309  mov     [rsp+278h+lpBuffer], rcx
0x14000330e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003315  mov     rcx, rax; this
0x140003318  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000331d  jmp     short loc_140003341
0x14000331f  mov     rcx, rax; this
0x140003322  test    r9, r9
0x140003325  jz      short loc_140003335
0x140003327  lea     r8, aHs; "[%hs]\n"
0x14000332e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003333  jmp     short loc_140003341
0x140003335  lea     r8, asc_140016DB8; "\n"
0x14000333c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003341  xor     eax, eax
0x140003343  mov     rcx, [rsp+278h+var_38]
0x14000334b  xor     rcx, rsp; StackCookie
0x14000334e  call    __security_check_cookie
0x140003353  mov     rbx, [rsp+278h+arg_18]
0x14000335b  add     rsp, 250h
0x140003362  pop     r15
0x140003364  pop     r14
0x140003366  pop     rdi
0x140003367  pop     rsi
0x140003368  pop     rbp
0x140003369  retn
```
