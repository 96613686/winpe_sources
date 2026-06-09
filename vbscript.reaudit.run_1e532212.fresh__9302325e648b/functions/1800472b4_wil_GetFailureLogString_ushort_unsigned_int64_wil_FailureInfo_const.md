# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800472b4`
- end: `0x18004756a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180046854`
- `0x1800478a0`

## callees

- `0x1800472b4`
- `0x180047ba0`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800473e6`
- `KERNEL32!FormatMessageW` at `0x1800473e6`
- `KERNEL32!GetCurrentThreadId` at `0x180047467`
- `KERNEL32!GetCurrentThreadId` at `0x180047467`

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
          v8 = (const char *)&dword_18007E62C;
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
0x1800472b4  mov     [rsp+arg_18], rbx
0x1800472b9  push    rbp
0x1800472ba  push    rsi
0x1800472bb  push    rdi
0x1800472bc  push    r14
0x1800472be  push    r15
0x1800472c0  sub     rsp, 250h
0x1800472c7  mov     rax, cs:__security_cookie
0x1800472ce  xor     rax, rsp
0x1800472d1  mov     [rsp+278h+var_38], rax
0x1800472d9  xor     r15d, r15d
0x1800472dc  mov     rbx, r8
0x1800472df  mov     rsi, rdx
0x1800472e2  mov     r14, rcx
0x1800472e5  test    rdx, rdx
0x1800472e8  jz      loc_180047541
0x1800472ee  test    rcx, rcx
0x1800472f1  jz      loc_180047541
0x1800472f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800472fe  mov     [rcx], r15w
0x180047302  test    rax, rax
0x180047305  jz      short loc_180047328
0x180047307  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18004730e  jz      short loc_180047328
0x180047310  mov     r8, rdx
0x180047313  mov     rdx, rcx
0x180047316  mov     rcx, rbx
0x180047319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004731e  cmp     [r14], r15w
0x180047322  jnz     loc_180047541
0x180047328  mov     ecx, [rbx]
0x18004732a  mov     bpl, 8
0x18004732d  test    ecx, ecx
0x18004732f  jz      short loc_18004737A
0x180047331  sub     ecx, 1
0x180047334  jz      short loc_180047362
0x180047336  sub     ecx, 1
0x180047339  jz      short loc_180047352
0x18004733b  cmp     ecx, 1
0x18004733e  jz      short loc_180047349
0x180047340  lea     rdi, dword_18007E62C
0x180047347  jmp     short loc_180047381
0x180047349  lea     rdi, aFailfast; "FailFast"
0x180047350  jmp     short loc_180047381
0x180047352  lea     rax, aLoghr; "LogHr"
0x180047359  lea     rdi, aLognt; "LogNt"
0x180047360  jmp     short loc_180047370
0x180047362  lea     rax, aReturnhr; "ReturnHr"
0x180047369  lea     rdi, aReturnnt; "ReturnNt"
0x180047370  test    [rbx+4], bpl
0x180047374  cmovz   rdi, rax
0x180047378  jmp     short loc_180047381
0x18004737a  lea     rdi, aException; "Exception"
0x180047381  xor     edx, edx; Val
0x180047383  lea     rcx, [rsp+278h+Buffer]; void *
0x180047388  mov     r8d, 200h; Size
0x18004738e  call    memset_0
0x180047393  test    [rbx+4], bpl
0x180047397  jz      short loc_1800473BC
0x180047399  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800473a0  mov     ebp, [rbx+0Ch]
0x1800473a3  test    rax, rax
0x1800473a6  jz      short loc_1800473EC
0x1800473a8  mov     r8d, 100h
0x1800473ae  lea     rdx, [rsp+278h+Buffer]
0x1800473b3  mov     ecx, ebp
0x1800473b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473ba  jmp     short loc_1800473EC
0x1800473bc  mov     ebp, [rbx+8]
0x1800473bf  lea     rax, [rsp+278h+Buffer]
0x1800473c4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800473c9  mov     r8d, ebp; dwMessageId
0x1800473cc  mov     [rsp+278h+nSize], 100h; nSize
0x1800473d4  mov     r9d, 400h; dwLanguageId
0x1800473da  xor     edx, edx; lpSource
0x1800473dc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800473e1  mov     ecx, 1200h; dwFlags
0x1800473e6  call    cs:__imp_FormatMessageW
0x1800473ec  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800473f0  lea     rsi, [r14+rsi*2]
0x1800473f4  mov     rax, [rbx+88h]
0x1800473fb  mov     rdx, rsi; unsigned __int16 *
0x1800473fe  mov     rcx, [rbx+80h]
0x180047405  test    r9, r9
0x180047408  jz      short loc_18004742C
0x18004740a  mov     [rsp+278h+Arguments], rax
0x18004740f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180047416  mov     eax, [rbx+40h]
0x180047419  mov     qword ptr [rsp+278h+nSize], rcx
0x18004741e  mov     rcx, r14; this
0x180047421  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180047425  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004742a  jmp     short loc_180047443
0x18004742c  mov     r9, rcx; unsigned __int16 *
0x18004742f  mov     [rsp+278h+lpBuffer], rax
0x180047434  mov     rcx, r14; this
0x180047437  lea     r8, aHsP; "%hs!%p: "
0x18004743e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180047443  mov     r9, [rbx+90h]; unsigned __int16 *
0x18004744a  mov     r14, rax
0x18004744d  test    r9, r9
0x180047450  jz      short loc_180047467
0x180047452  lea     r8, aCallerP; "(caller: %p) "
0x180047459  mov     rdx, rsi; unsigned __int16 *
0x18004745c  mov     rcx, rax; this
0x18004745f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180047464  mov     r14, rax
0x180047467  call    cs:__imp_GetCurrentThreadId
0x18004746d  lea     rcx, [rsp+278h+Buffer]
0x180047472  mov     r9, rdi; unsigned __int16 *
0x180047475  mov     [rsp+278h+var_240], rcx
0x18004747a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180047481  mov     dword ptr [rsp+278h+Arguments], ebp
0x180047485  mov     rdx, rsi; unsigned __int16 *
0x180047488  mov     [rsp+278h+nSize], eax
0x18004748c  mov     rcx, r14; this
0x18004748f  mov     eax, [rbx+44h]
0x180047492  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180047496  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004749b  cmp     [rbx+18h], r15
0x18004749f  jnz     short loc_1800474B1
0x1800474a1  cmp     [rbx+48h], r15
0x1800474a5  jnz     short loc_1800474B1
0x1800474a7  cmp     [rbx+30h], r15
0x1800474ab  jz      loc_180047541
0x1800474b1  lea     r8, asc_18007ED18; "    "
0x1800474b8  mov     rdx, rsi; unsigned __int16 *
0x1800474bb  mov     rcx, rax; this
0x1800474be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800474c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800474c7  test    r9, r9
0x1800474ca  jz      short loc_1800474DE
0x1800474cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800474d3  mov     rdx, rsi; unsigned __int16 *
0x1800474d6  mov     rcx, rax; this
0x1800474d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800474de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800474e2  test    r9, r9
0x1800474e5  jz      short loc_1800474F9
0x1800474e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800474ee  mov     rdx, rsi; unsigned __int16 *
0x1800474f1  mov     rcx, rax; this
0x1800474f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800474f9  mov     rcx, [rbx+28h]
0x1800474fd  mov     rdx, rsi; unsigned __int16 *
0x180047500  mov     r9, [rbx+30h]; unsigned __int16 *
0x180047504  test    rcx, rcx
0x180047507  jz      short loc_18004751F
0x180047509  mov     [rsp+278h+lpBuffer], rcx
0x18004750e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180047515  mov     rcx, rax; this
0x180047518  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004751d  jmp     short loc_180047541
0x18004751f  mov     rcx, rax; this
0x180047522  test    r9, r9
0x180047525  jz      short loc_180047535
0x180047527  lea     r8, aHs; "[%hs]\n"
0x18004752e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180047533  jmp     short loc_180047541
0x180047535  lea     r8, strIn; "\n"
0x18004753c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180047541  xor     eax, eax
0x180047543  mov     rcx, [rsp+278h+var_38]
0x18004754b  xor     rcx, rsp; StackCookie
0x18004754e  call    __security_check_cookie
0x180047553  mov     rbx, [rsp+278h+arg_18]
0x18004755b  add     rsp, 250h
0x180047562  pop     r15
0x180047564  pop     r14
0x180047566  pop     rdi
0x180047567  pop     rsi
0x180047568  pop     rbp
0x180047569  retn
```
