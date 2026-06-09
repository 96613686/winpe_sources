# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800085b4`
- end: `0x18000886a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800069d0`
- `0x180008f6c`
- `0x18000bec0`

## callees

- `0x180005320`
- `0x180005cac`
- `0x1800085b4`
- `0x18000926c`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008767`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800086e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800086e6`

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
          v7 = (const char *)&dword_18001828C;
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
0x1800085b4  mov     [rsp+arg_18], rbx
0x1800085b9  push    rbp
0x1800085ba  push    rsi
0x1800085bb  push    rdi
0x1800085bc  push    r14
0x1800085be  push    r15
0x1800085c0  sub     rsp, 250h
0x1800085c7  mov     rax, cs:__security_cookie
0x1800085ce  xor     rax, rsp
0x1800085d1  mov     [rsp+278h+var_38], rax
0x1800085d9  mov     rbx, r8
0x1800085dc  mov     rsi, rdx
0x1800085df  mov     r14, rcx
0x1800085e2  xor     r15d, r15d
0x1800085e5  test    rdx, rdx
0x1800085e8  jz      loc_180008841
0x1800085ee  test    rcx, rcx
0x1800085f1  jz      loc_180008841
0x1800085f7  mov     [rcx], r15w
0x1800085fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180008602  test    rax, rax
0x180008605  jz      short loc_180008628
0x180008607  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000860e  jz      short loc_180008628
0x180008610  mov     r8, rdx
0x180008613  mov     rdx, rcx
0x180008616  mov     rcx, rbx
0x180008619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000861e  cmp     [r14], r15w
0x180008622  jnz     loc_180008841
0x180008628  mov     ecx, [rbx]
0x18000862a  mov     bpl, 8
0x18000862d  test    ecx, ecx
0x18000862f  jz      short loc_18000867A
0x180008631  sub     ecx, 1
0x180008634  jz      short loc_180008662
0x180008636  sub     ecx, 1
0x180008639  jz      short loc_180008652
0x18000863b  cmp     ecx, 1
0x18000863e  jz      short loc_180008649
0x180008640  lea     rdi, dword_18001828C
0x180008647  jmp     short loc_180008681
0x180008649  lea     rdi, aFailfast; "FailFast"
0x180008650  jmp     short loc_180008681
0x180008652  lea     rax, aLoghr; "LogHr"
0x180008659  lea     rdi, aLognt; "LogNt"
0x180008660  jmp     short loc_180008670
0x180008662  lea     rax, aReturnhr; "ReturnHr"
0x180008669  lea     rdi, aReturnnt; "ReturnNt"
0x180008670  test    [rbx+4], bpl
0x180008674  cmovz   rdi, rax
0x180008678  jmp     short loc_180008681
0x18000867a  lea     rdi, aException; "Exception"
0x180008681  xor     edx, edx; Val
0x180008683  mov     r8d, 200h; Size
0x180008689  lea     rcx, [rsp+278h+Buffer]; void *
0x18000868e  call    memset_0
0x180008693  test    [rbx+4], bpl
0x180008697  jz      short loc_1800086BC
0x180008699  mov     ebp, [rbx+0Ch]
0x18000869c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800086a3  test    rax, rax
0x1800086a6  jz      short loc_1800086EC
0x1800086a8  mov     r8d, 100h
0x1800086ae  lea     rdx, [rsp+278h+Buffer]
0x1800086b3  mov     ecx, ebp
0x1800086b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ba  jmp     short loc_1800086EC
0x1800086bc  mov     ebp, [rbx+8]
0x1800086bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800086c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800086cc  lea     rax, [rsp+278h+Buffer]
0x1800086d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800086d6  mov     r9d, 400h; dwLanguageId
0x1800086dc  mov     r8d, ebp; dwMessageId
0x1800086df  xor     edx, edx; lpSource
0x1800086e1  mov     ecx, 1200h; dwFlags
0x1800086e6  call    cs:__imp_FormatMessageW
0x1800086ec  lea     rsi, [r14+rsi*2]
0x1800086f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800086f4  mov     rax, [rbx+88h]
0x1800086fb  mov     rcx, [rbx+80h]
0x180008702  mov     rdx, rsi; unsigned __int16 *
0x180008705  test    r9, r9
0x180008708  jz      short loc_18000872C
0x18000870a  mov     [rsp+278h+Arguments], rax
0x18000870f  mov     qword ptr [rsp+278h+nSize], rcx
0x180008714  mov     eax, [rbx+40h]
0x180008717  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000871b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008722  mov     rcx, r14; this
0x180008725  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000872a  jmp     short loc_180008743
0x18000872c  mov     [rsp+278h+lpBuffer], rax
0x180008731  mov     r9, rcx; unsigned __int16 *
0x180008734  lea     r8, aHsP; "%hs!%p: "
0x18000873b  mov     rcx, r14; this
0x18000873e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008743  mov     r14, rax
0x180008746  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000874d  test    r9, r9
0x180008750  jz      short loc_180008767
0x180008752  lea     r8, aCallerP; "(caller: %p) "
0x180008759  mov     rdx, rsi; unsigned __int16 *
0x18000875c  mov     rcx, rax; this
0x18000875f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008764  mov     r14, rax
0x180008767  call    cs:__imp_GetCurrentThreadId
0x18000876d  lea     rcx, [rsp+278h+Buffer]
0x180008772  mov     [rsp+278h+var_240], rcx
0x180008777  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000877b  mov     [rsp+278h+nSize], eax
0x18000877f  mov     eax, [rbx+44h]
0x180008782  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008786  mov     r9, rdi; unsigned __int16 *
0x180008789  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008790  mov     rdx, rsi; unsigned __int16 *
0x180008793  mov     rcx, r14; this
0x180008796  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000879b  cmp     [rbx+18h], r15
0x18000879f  jnz     short loc_1800087B1
0x1800087a1  cmp     [rbx+48h], r15
0x1800087a5  jnz     short loc_1800087B1
0x1800087a7  cmp     [rbx+30h], r15
0x1800087ab  jz      loc_180008841
0x1800087b1  lea     r8, asc_180018390; "    "
0x1800087b8  mov     rdx, rsi; unsigned __int16 *
0x1800087bb  mov     rcx, rax; this
0x1800087be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800087c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800087c7  test    r9, r9
0x1800087ca  jz      short loc_1800087DE
0x1800087cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800087d3  mov     rdx, rsi; unsigned __int16 *
0x1800087d6  mov     rcx, rax; this
0x1800087d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800087de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800087e2  test    r9, r9
0x1800087e5  jz      short loc_1800087F9
0x1800087e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800087ee  mov     rdx, rsi; unsigned __int16 *
0x1800087f1  mov     rcx, rax; this
0x1800087f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800087f9  mov     rcx, [rbx+28h]
0x1800087fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008801  mov     rdx, rsi; unsigned __int16 *
0x180008804  test    rcx, rcx
0x180008807  jz      short loc_18000881F
0x180008809  mov     [rsp+278h+lpBuffer], rcx
0x18000880e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008815  mov     rcx, rax; this
0x180008818  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000881d  jmp     short loc_180008841
0x18000881f  mov     rcx, rax; this
0x180008822  test    r9, r9
0x180008825  jz      short loc_180008835
0x180008827  lea     r8, aHs; "[%hs]\n"
0x18000882e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008833  jmp     short loc_180008841
0x180008835  lea     r8, asc_180018408; "\n"
0x18000883c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008841  xor     eax, eax
0x180008843  mov     rcx, [rsp+278h+var_38]
0x18000884b  xor     rcx, rsp; StackCookie
0x18000884e  call    __security_check_cookie
0x180008853  mov     rbx, [rsp+278h+arg_18]
0x18000885b  add     rsp, 250h
0x180008862  pop     r15
0x180008864  pop     r14
0x180008866  pop     rdi
0x180008867  pop     rsi
0x180008868  pop     rbp
0x180008869  retn
```
