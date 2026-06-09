# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800243c4`
- end: `0x180024685`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180021fb8`
- `0x180024f64`
- `0x18002a050`

## callees

- `0x1800151bb`
- `0x1800243c4`
- `0x18002526c`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024582`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024582`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180024501`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180024501`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&qword_180037200;
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
                          Buffer,
                          -2);
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
0x1800243c4  mov     rax, rsp
0x1800243c7  push    rbp
0x1800243c8  push    rsi
0x1800243c9  push    rdi
0x1800243ca  push    r14
0x1800243cc  push    r15
0x1800243ce  sub     rsp, 260h
0x1800243d5  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800243de  mov     [rax+20h], rbx
0x1800243e2  mov     rax, cs:__security_cookie
0x1800243e9  xor     rax, rsp
0x1800243ec  mov     [rsp+288h+var_38], rax
0x1800243f4  mov     rbx, r8
0x1800243f7  mov     rsi, rdx
0x1800243fa  mov     r14, rcx
0x1800243fd  xor     r15d, r15d
0x180024400  test    rdx, rdx
0x180024403  jz      loc_18002465C
0x180024409  test    rcx, rcx
0x18002440c  jz      loc_18002465C
0x180024412  mov     [rcx], r15w
0x180024416  mov     rax, cs:g_pfnResultLoggingCallback
0x18002441d  test    rax, rax
0x180024420  jz      short loc_180024443
0x180024422  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180024429  jz      short loc_180024443
0x18002442b  mov     r8, rdx
0x18002442e  mov     rdx, rcx
0x180024431  mov     rcx, rbx
0x180024434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024439  cmp     [r14], r15w
0x18002443d  jnz     loc_18002465C
0x180024443  mov     ecx, [rbx]
0x180024445  mov     bpl, 8
0x180024448  test    ecx, ecx
0x18002444a  jz      short loc_180024495
0x18002444c  sub     ecx, 1
0x18002444f  jz      short loc_18002447D
0x180024451  sub     ecx, 1
0x180024454  jz      short loc_18002446D
0x180024456  cmp     ecx, 1
0x180024459  jz      short loc_180024464
0x18002445b  lea     rdi, qword_180037200
0x180024462  jmp     short loc_18002449C
0x180024464  lea     rdi, aFailfast; "FailFast"
0x18002446b  jmp     short loc_18002449C
0x18002446d  lea     rax, aLoghr; "LogHr"
0x180024474  lea     rdi, aLognt; "LogNt"
0x18002447b  jmp     short loc_18002448B
0x18002447d  lea     rax, aReturnhr; "ReturnHr"
0x180024484  lea     rdi, aReturnnt; "ReturnNt"
0x18002448b  test    [rbx+4], bpl
0x18002448f  cmovz   rdi, rax
0x180024493  jmp     short loc_18002449C
0x180024495  lea     rdi, aException; "Exception"
0x18002449c  xor     edx, edx; Val
0x18002449e  mov     r8d, 200h; Size
0x1800244a4  lea     rcx, [rsp+288h+Buffer]; void *
0x1800244a9  call    memset_0
0x1800244ae  test    [rbx+4], bpl
0x1800244b2  jz      short loc_1800244D7
0x1800244b4  mov     ebp, [rbx+0Ch]
0x1800244b7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800244be  test    rax, rax
0x1800244c1  jz      short loc_180024507
0x1800244c3  mov     r8d, 100h
0x1800244c9  lea     rdx, [rsp+288h+Buffer]
0x1800244ce  mov     ecx, ebp
0x1800244d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244d5  jmp     short loc_180024507
0x1800244d7  mov     ebp, [rbx+8]
0x1800244da  mov     [rsp+288h+Arguments], r15; Arguments
0x1800244df  mov     [rsp+288h+nSize], 100h; nSize
0x1800244e7  lea     rax, [rsp+288h+Buffer]
0x1800244ec  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1800244f1  mov     r9d, 400h; dwLanguageId
0x1800244f7  mov     r8d, ebp; dwMessageId
0x1800244fa  xor     edx, edx; lpSource
0x1800244fc  mov     ecx, 1200h; dwFlags
0x180024501  call    cs:__imp_FormatMessageW
0x180024507  lea     rsi, [r14+rsi*2]
0x18002450b  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002450f  mov     rax, [rbx+88h]
0x180024516  mov     rcx, [rbx+80h]
0x18002451d  mov     rdx, rsi; unsigned __int16 *
0x180024520  test    r9, r9
0x180024523  jz      short loc_180024547
0x180024525  mov     [rsp+288h+Arguments], rax
0x18002452a  mov     qword ptr [rsp+288h+nSize], rcx
0x18002452f  mov     eax, [rbx+40h]
0x180024532  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180024536  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002453d  mov     rcx, r14; this
0x180024540  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024545  jmp     short loc_18002455E
0x180024547  mov     [rsp+288h+lpBuffer], rax
0x18002454c  mov     r9, rcx; unsigned __int16 *
0x18002454f  lea     r8, aHsP; "%hs!%p: "
0x180024556  mov     rcx, r14; this
0x180024559  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002455e  mov     r14, rax
0x180024561  mov     r9, [rbx+90h]; unsigned __int16 *
0x180024568  test    r9, r9
0x18002456b  jz      short loc_180024582
0x18002456d  lea     r8, aCallerP; "(caller: %p) "
0x180024574  mov     rdx, rsi; unsigned __int16 *
0x180024577  mov     rcx, rax; this
0x18002457a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002457f  mov     r14, rax
0x180024582  call    cs:__imp_GetCurrentThreadId
0x180024588  lea     rcx, [rsp+288h+Buffer]
0x18002458d  mov     [rsp+288h+var_250], rcx
0x180024592  mov     dword ptr [rsp+288h+Arguments], ebp
0x180024596  mov     [rsp+288h+nSize], eax
0x18002459a  mov     eax, [rbx+44h]
0x18002459d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800245a1  mov     r9, rdi; unsigned __int16 *
0x1800245a4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800245ab  mov     rdx, rsi; unsigned __int16 *
0x1800245ae  mov     rcx, r14; this
0x1800245b1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800245b6  cmp     [rbx+18h], r15
0x1800245ba  jnz     short loc_1800245CC
0x1800245bc  cmp     [rbx+48h], r15
0x1800245c0  jnz     short loc_1800245CC
0x1800245c2  cmp     [rbx+30h], r15
0x1800245c6  jz      loc_18002465C
0x1800245cc  lea     r8, asc_180038CC0; "    "
0x1800245d3  mov     rdx, rsi; unsigned __int16 *
0x1800245d6  mov     rcx, rax; this
0x1800245d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800245de  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800245e2  test    r9, r9
0x1800245e5  jz      short loc_1800245F9
0x1800245e7  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800245ee  mov     rdx, rsi; unsigned __int16 *
0x1800245f1  mov     rcx, rax; this
0x1800245f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800245f9  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800245fd  test    r9, r9
0x180024600  jz      short loc_180024614
0x180024602  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180024609  mov     rdx, rsi; unsigned __int16 *
0x18002460c  mov     rcx, rax; this
0x18002460f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024614  mov     rcx, [rbx+28h]
0x180024618  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002461c  mov     rdx, rsi; unsigned __int16 *
0x18002461f  test    rcx, rcx
0x180024622  jz      short loc_18002463A
0x180024624  mov     [rsp+288h+lpBuffer], rcx
0x180024629  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180024630  mov     rcx, rax; this
0x180024633  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024638  jmp     short loc_18002465C
0x18002463a  mov     rcx, rax; this
0x18002463d  test    r9, r9
0x180024640  jz      short loc_180024650
0x180024642  lea     r8, aHs; "[%hs]\n"
0x180024649  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002464e  jmp     short loc_18002465C
0x180024650  lea     r8, asc_180038D38; "\n"
0x180024657  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002465c  xor     eax, eax
0x18002465e  mov     rcx, [rsp+288h+var_38]
0x180024666  xor     rcx, rsp; StackCookie
0x180024669  call    __security_check_cookie
0x18002466e  mov     rbx, [rsp+288h+arg_18]
0x180024676  add     rsp, 260h
0x18002467d  pop     r15
0x18002467f  pop     r14
0x180024681  pop     rdi
0x180024682  pop     rsi
0x180024683  pop     rbp
0x180024684  retn
```
