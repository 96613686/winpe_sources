# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002c960`
- end: `0x18002cc21`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180025a04`
- `0x180025c74`
- `0x18002e444`
- `0x1800321f0`

## callees

- `0x18002c960`
- `0x18002e74c`
- `0x180068fe6`
- `0x180069020`
- `0x18006f010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18002ca9d`
- `KERNEL32!FormatMessageW` at `0x18002ca9d`
- `KERNEL32!GetCurrentThreadId` at `0x18002cb1e`
- `KERNEL32!GetCurrentThreadId` at `0x18002cb1e`

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
          v7 = (const char *)&qword_180080A30;
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
0x18002c960  mov     rax, rsp
0x18002c963  push    rbp
0x18002c964  push    rsi
0x18002c965  push    rdi
0x18002c966  push    r14
0x18002c968  push    r15
0x18002c96a  sub     rsp, 260h
0x18002c971  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18002c97a  mov     [rax+20h], rbx
0x18002c97e  mov     rax, cs:__security_cookie
0x18002c985  xor     rax, rsp
0x18002c988  mov     [rsp+288h+var_38], rax
0x18002c990  mov     rbx, r8
0x18002c993  mov     rsi, rdx
0x18002c996  mov     r14, rcx
0x18002c999  xor     r15d, r15d
0x18002c99c  test    rdx, rdx
0x18002c99f  jz      loc_18002CBF8
0x18002c9a5  test    rcx, rcx
0x18002c9a8  jz      loc_18002CBF8
0x18002c9ae  mov     [rcx], r15w
0x18002c9b2  mov     rax, cs:g_pfnResultLoggingCallback
0x18002c9b9  test    rax, rax
0x18002c9bc  jz      short loc_18002C9DF
0x18002c9be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002c9c5  jz      short loc_18002C9DF
0x18002c9c7  mov     r8, rdx
0x18002c9ca  mov     rdx, rcx
0x18002c9cd  mov     rcx, rbx
0x18002c9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9d5  cmp     [r14], r15w
0x18002c9d9  jnz     loc_18002CBF8
0x18002c9df  mov     ecx, [rbx]
0x18002c9e1  mov     bpl, 8
0x18002c9e4  test    ecx, ecx
0x18002c9e6  jz      short loc_18002CA31
0x18002c9e8  sub     ecx, 1
0x18002c9eb  jz      short loc_18002CA19
0x18002c9ed  sub     ecx, 1
0x18002c9f0  jz      short loc_18002CA09
0x18002c9f2  cmp     ecx, 1
0x18002c9f5  jz      short loc_18002CA00
0x18002c9f7  lea     rdi, qword_180080A30
0x18002c9fe  jmp     short loc_18002CA38
0x18002ca00  lea     rdi, aFailfast; "FailFast"
0x18002ca07  jmp     short loc_18002CA38
0x18002ca09  lea     rax, aLoghr; "LogHr"
0x18002ca10  lea     rdi, aLognt; "LogNt"
0x18002ca17  jmp     short loc_18002CA27
0x18002ca19  lea     rax, aReturnhr; "ReturnHr"
0x18002ca20  lea     rdi, aReturnnt; "ReturnNt"
0x18002ca27  test    [rbx+4], bpl
0x18002ca2b  cmovz   rdi, rax
0x18002ca2f  jmp     short loc_18002CA38
0x18002ca31  lea     rdi, aException; "Exception"
0x18002ca38  xor     edx, edx; Val
0x18002ca3a  mov     r8d, 200h; Size
0x18002ca40  lea     rcx, [rsp+288h+Buffer]; void *
0x18002ca45  call    memset_0
0x18002ca4a  test    [rbx+4], bpl
0x18002ca4e  jz      short loc_18002CA73
0x18002ca50  mov     ebp, [rbx+0Ch]
0x18002ca53  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002ca5a  test    rax, rax
0x18002ca5d  jz      short loc_18002CAA3
0x18002ca5f  mov     r8d, 100h
0x18002ca65  lea     rdx, [rsp+288h+Buffer]
0x18002ca6a  mov     ecx, ebp
0x18002ca6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca71  jmp     short loc_18002CAA3
0x18002ca73  mov     ebp, [rbx+8]
0x18002ca76  mov     [rsp+288h+Arguments], r15; Arguments
0x18002ca7b  mov     [rsp+288h+nSize], 100h; nSize
0x18002ca83  lea     rax, [rsp+288h+Buffer]
0x18002ca88  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18002ca8d  mov     r9d, 400h; dwLanguageId
0x18002ca93  mov     r8d, ebp; dwMessageId
0x18002ca96  xor     edx, edx; lpSource
0x18002ca98  mov     ecx, 1200h; dwFlags
0x18002ca9d  call    cs:__imp_FormatMessageW
0x18002caa3  lea     rsi, [r14+rsi*2]
0x18002caa7  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002caab  mov     rax, [rbx+88h]
0x18002cab2  mov     rcx, [rbx+80h]
0x18002cab9  mov     rdx, rsi; unsigned __int16 *
0x18002cabc  test    r9, r9
0x18002cabf  jz      short loc_18002CAE3
0x18002cac1  mov     [rsp+288h+Arguments], rax
0x18002cac6  mov     qword ptr [rsp+288h+nSize], rcx
0x18002cacb  mov     eax, [rbx+40h]
0x18002cace  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18002cad2  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002cad9  mov     rcx, r14; this
0x18002cadc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cae1  jmp     short loc_18002CAFA
0x18002cae3  mov     [rsp+288h+lpBuffer], rax
0x18002cae8  mov     r9, rcx; unsigned __int16 *
0x18002caeb  lea     r8, aHsP; "%hs!%p: "
0x18002caf2  mov     rcx, r14; this
0x18002caf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cafa  mov     r14, rax
0x18002cafd  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002cb04  test    r9, r9
0x18002cb07  jz      short loc_18002CB1E
0x18002cb09  lea     r8, aCallerP; "(caller: %p) "
0x18002cb10  mov     rdx, rsi; unsigned __int16 *
0x18002cb13  mov     rcx, rax; this
0x18002cb16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cb1b  mov     r14, rax
0x18002cb1e  call    cs:__imp_GetCurrentThreadId
0x18002cb24  lea     rcx, [rsp+288h+Buffer]
0x18002cb29  mov     [rsp+288h+var_250], rcx
0x18002cb2e  mov     dword ptr [rsp+288h+Arguments], ebp
0x18002cb32  mov     [rsp+288h+nSize], eax
0x18002cb36  mov     eax, [rbx+44h]
0x18002cb39  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18002cb3d  mov     r9, rdi; unsigned __int16 *
0x18002cb40  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002cb47  mov     rdx, rsi; unsigned __int16 *
0x18002cb4a  mov     rcx, r14; this
0x18002cb4d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cb52  cmp     [rbx+18h], r15
0x18002cb56  jnz     short loc_18002CB68
0x18002cb58  cmp     [rbx+48h], r15
0x18002cb5c  jnz     short loc_18002CB68
0x18002cb5e  cmp     [rbx+30h], r15
0x18002cb62  jz      loc_18002CBF8
0x18002cb68  lea     r8, asc_180080B20; "    "
0x18002cb6f  mov     rdx, rsi; unsigned __int16 *
0x18002cb72  mov     rcx, rax; this
0x18002cb75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cb7a  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002cb7e  test    r9, r9
0x18002cb81  jz      short loc_18002CB95
0x18002cb83  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002cb8a  mov     rdx, rsi; unsigned __int16 *
0x18002cb8d  mov     rcx, rax; this
0x18002cb90  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cb95  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002cb99  test    r9, r9
0x18002cb9c  jz      short loc_18002CBB0
0x18002cb9e  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002cba5  mov     rdx, rsi; unsigned __int16 *
0x18002cba8  mov     rcx, rax; this
0x18002cbab  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cbb0  mov     rcx, [rbx+28h]
0x18002cbb4  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002cbb8  mov     rdx, rsi; unsigned __int16 *
0x18002cbbb  test    rcx, rcx
0x18002cbbe  jz      short loc_18002CBD6
0x18002cbc0  mov     [rsp+288h+lpBuffer], rcx
0x18002cbc5  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002cbcc  mov     rcx, rax; this
0x18002cbcf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cbd4  jmp     short loc_18002CBF8
0x18002cbd6  mov     rcx, rax; this
0x18002cbd9  test    r9, r9
0x18002cbdc  jz      short loc_18002CBEC
0x18002cbde  lea     r8, aHs; "[%hs]\n"
0x18002cbe5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cbea  jmp     short loc_18002CBF8
0x18002cbec  lea     r8, asc_180080B98; "\n"
0x18002cbf3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cbf8  xor     eax, eax
0x18002cbfa  mov     rcx, [rsp+288h+var_38]
0x18002cc02  xor     rcx, rsp; StackCookie
0x18002cc05  call    __security_check_cookie
0x18002cc0a  mov     rbx, [rsp+288h+arg_18]
0x18002cc12  add     rsp, 260h
0x18002cc19  pop     r15
0x18002cc1b  pop     r14
0x18002cc1d  pop     rdi
0x18002cc1e  pop     rsi
0x18002cc1f  pop     rbp
0x18002cc20  retn
```
