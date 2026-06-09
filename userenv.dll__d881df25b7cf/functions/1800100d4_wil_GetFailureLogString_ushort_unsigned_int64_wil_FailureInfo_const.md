# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800100d4`
- end: `0x180010397`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180010ab0`
- `0x180010fa4`
- `0x180011be4`

## callees

- `0x18000e640`
- `0x18000efe0`
- `0x1800100d4`
- `0x1800104d8`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001028d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001028d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180010206`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180010206`

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
          v7 = (const char *)&byte_18001FF4B;
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
0x1800100d4  mov     [rsp+arg_18], rbx
0x1800100d9  push    rbp
0x1800100da  push    rsi
0x1800100db  push    rdi
0x1800100dc  push    r14
0x1800100de  push    r15
0x1800100e0  sub     rsp, 250h
0x1800100e7  mov     rax, cs:__security_cookie
0x1800100ee  xor     rax, rsp
0x1800100f1  mov     [rsp+278h+var_38], rax
0x1800100f9  mov     rbx, r8
0x1800100fc  mov     rsi, rdx
0x1800100ff  mov     r14, rcx
0x180010102  xor     r15d, r15d
0x180010105  test    rdx, rdx
0x180010108  jz      loc_18001036D
0x18001010e  test    rcx, rcx
0x180010111  jz      loc_18001036D
0x180010117  mov     [rcx], r15w
0x18001011b  mov     rax, cs:g_pfnResultLoggingCallback
0x180010122  test    rax, rax
0x180010125  jz      short loc_180010148
0x180010127  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001012e  jz      short loc_180010148
0x180010130  mov     r8, rdx
0x180010133  mov     rdx, rcx
0x180010136  mov     rcx, rbx
0x180010139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001013e  cmp     [r14], r15w
0x180010142  jnz     loc_18001036D
0x180010148  mov     ecx, [rbx]
0x18001014a  mov     bpl, 8
0x18001014d  test    ecx, ecx
0x18001014f  jz      short loc_18001019A
0x180010151  sub     ecx, 1
0x180010154  jz      short loc_180010182
0x180010156  sub     ecx, 1
0x180010159  jz      short loc_180010172
0x18001015b  cmp     ecx, 1
0x18001015e  jz      short loc_180010169
0x180010160  lea     rdi, byte_18001FF4B
0x180010167  jmp     short loc_1800101A1
0x180010169  lea     rdi, aFailfast; "FailFast"
0x180010170  jmp     short loc_1800101A1
0x180010172  lea     rax, aLoghr; "LogHr"
0x180010179  lea     rdi, aLognt; "LogNt"
0x180010180  jmp     short loc_180010190
0x180010182  lea     rax, aReturnhr; "ReturnHr"
0x180010189  lea     rdi, aReturnnt; "ReturnNt"
0x180010190  test    [rbx+4], bpl
0x180010194  cmovz   rdi, rax
0x180010198  jmp     short loc_1800101A1
0x18001019a  lea     rdi, aException; "Exception"
0x1800101a1  xor     edx, edx; Val
0x1800101a3  mov     r8d, 200h; Size
0x1800101a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800101ae  call    memset_0
0x1800101b3  test    [rbx+4], bpl
0x1800101b7  jz      short loc_1800101DC
0x1800101b9  mov     ebp, [rbx+0Ch]
0x1800101bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800101c3  test    rax, rax
0x1800101c6  jz      short loc_180010212
0x1800101c8  mov     r8d, 100h
0x1800101ce  lea     rdx, [rsp+278h+Buffer]
0x1800101d3  mov     ecx, ebp
0x1800101d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101da  jmp     short loc_180010212
0x1800101dc  mov     ebp, [rbx+8]
0x1800101df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800101e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800101ec  lea     rax, [rsp+278h+Buffer]
0x1800101f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800101f6  mov     r9d, 400h; dwLanguageId
0x1800101fc  mov     r8d, ebp; dwMessageId
0x1800101ff  xor     edx, edx; lpSource
0x180010201  mov     ecx, 1200h; dwFlags
0x180010206  call    cs:__imp_FormatMessageW
0x18001020d  nop     dword ptr [rax+rax+00h]
0x180010212  lea     rsi, [r14+rsi*2]
0x180010216  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001021a  mov     rax, [rbx+88h]
0x180010221  mov     rcx, [rbx+80h]
0x180010228  mov     rdx, rsi; unsigned __int16 *
0x18001022b  test    r9, r9
0x18001022e  jz      short loc_180010252
0x180010230  mov     [rsp+278h+Arguments], rax
0x180010235  mov     qword ptr [rsp+278h+nSize], rcx
0x18001023a  mov     eax, [rbx+40h]
0x18001023d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180010241  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180010248  mov     rcx, r14; this
0x18001024b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010250  jmp     short loc_180010269
0x180010252  mov     [rsp+278h+lpBuffer], rax
0x180010257  mov     r9, rcx; unsigned __int16 *
0x18001025a  lea     r8, aHsP; "%hs!%p: "
0x180010261  mov     rcx, r14; this
0x180010264  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010269  mov     r14, rax
0x18001026c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180010273  test    r9, r9
0x180010276  jz      short loc_18001028D
0x180010278  lea     r8, aCallerP; "(caller: %p) "
0x18001027f  mov     rdx, rsi; unsigned __int16 *
0x180010282  mov     rcx, rax; this
0x180010285  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001028a  mov     r14, rax
0x18001028d  call    cs:__imp_GetCurrentThreadId
0x180010294  nop     dword ptr [rax+rax+00h]
0x180010299  lea     rcx, [rsp+278h+Buffer]
0x18001029e  mov     [rsp+278h+var_240], rcx
0x1800102a3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800102a7  mov     [rsp+278h+nSize], eax
0x1800102ab  mov     eax, [rbx+44h]
0x1800102ae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800102b2  mov     r9, rdi; unsigned __int16 *
0x1800102b5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800102bc  mov     rdx, rsi; unsigned __int16 *
0x1800102bf  mov     rcx, r14; this
0x1800102c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800102c7  cmp     [rbx+18h], r15
0x1800102cb  jnz     short loc_1800102DD
0x1800102cd  cmp     [rbx+48h], r15
0x1800102d1  jnz     short loc_1800102DD
0x1800102d3  cmp     [rbx+30h], r15
0x1800102d7  jz      loc_18001036D
0x1800102dd  lea     r8, asc_180020050; "    "
0x1800102e4  mov     rdx, rsi; unsigned __int16 *
0x1800102e7  mov     rcx, rax; this
0x1800102ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800102ef  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800102f3  test    r9, r9
0x1800102f6  jz      short loc_18001030A
0x1800102f8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800102ff  mov     rdx, rsi; unsigned __int16 *
0x180010302  mov     rcx, rax; this
0x180010305  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001030a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001030e  test    r9, r9
0x180010311  jz      short loc_180010325
0x180010313  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001031a  mov     rdx, rsi; unsigned __int16 *
0x18001031d  mov     rcx, rax; this
0x180010320  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010325  mov     rcx, [rbx+28h]
0x180010329  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001032d  mov     rdx, rsi; unsigned __int16 *
0x180010330  test    rcx, rcx
0x180010333  jz      short loc_18001034B
0x180010335  mov     [rsp+278h+lpBuffer], rcx
0x18001033a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180010341  mov     rcx, rax; this
0x180010344  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010349  jmp     short loc_18001036D
0x18001034b  mov     rcx, rax; this
0x18001034e  test    r9, r9
0x180010351  jz      short loc_180010361
0x180010353  lea     r8, aHs; "[%hs]\n"
0x18001035a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001035f  jmp     short loc_18001036D
0x180010361  lea     r8, asc_1800200C8; "\n"
0x180010368  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001036d  xor     eax, eax
0x18001036f  mov     rcx, [rsp+278h+var_38]
0x180010377  xor     rcx, rsp; StackCookie
0x18001037a  call    __security_check_cookie
0x18001037f  mov     rbx, [rsp+278h+arg_18]
0x180010387  add     rsp, 250h
0x18001038e  pop     r15
0x180010390  pop     r14
0x180010392  pop     rdi
0x180010393  pop     rsi
0x180010394  pop     rbp
0x180010395  retn
```
