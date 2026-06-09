# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002fe84`
- end: `0x18003013a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18002cd04`
- `0x18002cf6c`
- `0x1800308cc`
- `0x180034680`

## callees

- `0x18002fe84`
- `0x180030bcc`
- `0x180056df2`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030037`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002ffb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002ffb6`

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
          v7 = (const char *)&qword_180066950;
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
0x18002fe84  mov     [rsp+arg_18], rbx
0x18002fe89  push    rbp
0x18002fe8a  push    rsi
0x18002fe8b  push    rdi
0x18002fe8c  push    r14
0x18002fe8e  push    r15
0x18002fe90  sub     rsp, 250h
0x18002fe97  mov     rax, cs:__security_cookie
0x18002fe9e  xor     rax, rsp
0x18002fea1  mov     [rsp+278h+var_38], rax
0x18002fea9  mov     rbx, r8
0x18002feac  mov     rsi, rdx
0x18002feaf  mov     r14, rcx
0x18002feb2  xor     r15d, r15d
0x18002feb5  test    rdx, rdx
0x18002feb8  jz      loc_180030111
0x18002febe  test    rcx, rcx
0x18002fec1  jz      loc_180030111
0x18002fec7  mov     [rcx], r15w
0x18002fecb  mov     rax, cs:g_pfnResultLoggingCallback
0x18002fed2  test    rax, rax
0x18002fed5  jz      short loc_18002FEF8
0x18002fed7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002fede  jz      short loc_18002FEF8
0x18002fee0  mov     r8, rdx
0x18002fee3  mov     rdx, rcx
0x18002fee6  mov     rcx, rbx
0x18002fee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002feee  cmp     [r14], r15w
0x18002fef2  jnz     loc_180030111
0x18002fef8  mov     ecx, [rbx]
0x18002fefa  mov     bpl, 8
0x18002fefd  test    ecx, ecx
0x18002feff  jz      short loc_18002FF4A
0x18002ff01  sub     ecx, 1
0x18002ff04  jz      short loc_18002FF32
0x18002ff06  sub     ecx, 1
0x18002ff09  jz      short loc_18002FF22
0x18002ff0b  cmp     ecx, 1
0x18002ff0e  jz      short loc_18002FF19
0x18002ff10  lea     rdi, qword_180066950
0x18002ff17  jmp     short loc_18002FF51
0x18002ff19  lea     rdi, aFailfast; "FailFast"
0x18002ff20  jmp     short loc_18002FF51
0x18002ff22  lea     rax, aLoghr; "LogHr"
0x18002ff29  lea     rdi, aLognt; "LogNt"
0x18002ff30  jmp     short loc_18002FF40
0x18002ff32  lea     rax, aReturnhr; "ReturnHr"
0x18002ff39  lea     rdi, aReturnnt; "ReturnNt"
0x18002ff40  test    [rbx+4], bpl
0x18002ff44  cmovz   rdi, rax
0x18002ff48  jmp     short loc_18002FF51
0x18002ff4a  lea     rdi, aException; "Exception"
0x18002ff51  xor     edx, edx; Val
0x18002ff53  mov     r8d, 200h; Size
0x18002ff59  lea     rcx, [rsp+278h+Buffer]; void *
0x18002ff5e  call    memset_0
0x18002ff63  test    [rbx+4], bpl
0x18002ff67  jz      short loc_18002FF8C
0x18002ff69  mov     ebp, [rbx+0Ch]
0x18002ff6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002ff73  test    rax, rax
0x18002ff76  jz      short loc_18002FFBC
0x18002ff78  mov     r8d, 100h
0x18002ff7e  lea     rdx, [rsp+278h+Buffer]
0x18002ff83  mov     ecx, ebp
0x18002ff85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff8a  jmp     short loc_18002FFBC
0x18002ff8c  mov     ebp, [rbx+8]
0x18002ff8f  mov     [rsp+278h+Arguments], r15; Arguments
0x18002ff94  mov     [rsp+278h+nSize], 100h; nSize
0x18002ff9c  lea     rax, [rsp+278h+Buffer]
0x18002ffa1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002ffa6  mov     r9d, 400h; dwLanguageId
0x18002ffac  mov     r8d, ebp; dwMessageId
0x18002ffaf  xor     edx, edx; lpSource
0x18002ffb1  mov     ecx, 1200h; dwFlags
0x18002ffb6  call    cs:__imp_FormatMessageW
0x18002ffbc  lea     rsi, [r14+rsi*2]
0x18002ffc0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002ffc4  mov     rax, [rbx+88h]
0x18002ffcb  mov     rcx, [rbx+80h]
0x18002ffd2  mov     rdx, rsi; unsigned __int16 *
0x18002ffd5  test    r9, r9
0x18002ffd8  jz      short loc_18002FFFC
0x18002ffda  mov     [rsp+278h+Arguments], rax
0x18002ffdf  mov     qword ptr [rsp+278h+nSize], rcx
0x18002ffe4  mov     eax, [rbx+40h]
0x18002ffe7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002ffeb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002fff2  mov     rcx, r14; this
0x18002fff5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002fffa  jmp     short loc_180030013
0x18002fffc  mov     [rsp+278h+lpBuffer], rax
0x180030001  mov     r9, rcx; unsigned __int16 *
0x180030004  lea     r8, aHsP; "%hs!%p: "
0x18003000b  mov     rcx, r14; this
0x18003000e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030013  mov     r14, rax
0x180030016  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003001d  test    r9, r9
0x180030020  jz      short loc_180030037
0x180030022  lea     r8, aCallerP; "(caller: %p) "
0x180030029  mov     rdx, rsi; unsigned __int16 *
0x18003002c  mov     rcx, rax; this
0x18003002f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030034  mov     r14, rax
0x180030037  call    cs:__imp_GetCurrentThreadId
0x18003003d  lea     rcx, [rsp+278h+Buffer]
0x180030042  mov     [rsp+278h+var_240], rcx
0x180030047  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003004b  mov     [rsp+278h+nSize], eax
0x18003004f  mov     eax, [rbx+44h]
0x180030052  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180030056  mov     r9, rdi; unsigned __int16 *
0x180030059  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180030060  mov     rdx, rsi; unsigned __int16 *
0x180030063  mov     rcx, r14; this
0x180030066  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003006b  cmp     [rbx+18h], r15
0x18003006f  jnz     short loc_180030081
0x180030071  cmp     [rbx+48h], r15
0x180030075  jnz     short loc_180030081
0x180030077  cmp     [rbx+30h], r15
0x18003007b  jz      loc_180030111
0x180030081  lea     r8, asc_180066A40; "    "
0x180030088  mov     rdx, rsi; unsigned __int16 *
0x18003008b  mov     rcx, rax; this
0x18003008e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030093  mov     r9, [rbx+18h]; unsigned __int16 *
0x180030097  test    r9, r9
0x18003009a  jz      short loc_1800300AE
0x18003009c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800300a3  mov     rdx, rsi; unsigned __int16 *
0x1800300a6  mov     rcx, rax; this
0x1800300a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800300ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800300b2  test    r9, r9
0x1800300b5  jz      short loc_1800300C9
0x1800300b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800300be  mov     rdx, rsi; unsigned __int16 *
0x1800300c1  mov     rcx, rax; this
0x1800300c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800300c9  mov     rcx, [rbx+28h]
0x1800300cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800300d1  mov     rdx, rsi; unsigned __int16 *
0x1800300d4  test    rcx, rcx
0x1800300d7  jz      short loc_1800300EF
0x1800300d9  mov     [rsp+278h+lpBuffer], rcx
0x1800300de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800300e5  mov     rcx, rax; this
0x1800300e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800300ed  jmp     short loc_180030111
0x1800300ef  mov     rcx, rax; this
0x1800300f2  test    r9, r9
0x1800300f5  jz      short loc_180030105
0x1800300f7  lea     r8, aHs; "[%hs]\n"
0x1800300fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030103  jmp     short loc_180030111
0x180030105  lea     r8, asc_180066AB8; "\n"
0x18003010c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030111  xor     eax, eax
0x180030113  mov     rcx, [rsp+278h+var_38]
0x18003011b  xor     rcx, rsp; StackCookie
0x18003011e  call    __security_check_cookie
0x180030123  mov     rbx, [rsp+278h+arg_18]
0x18003012b  add     rsp, 250h
0x180030132  pop     r15
0x180030134  pop     r14
0x180030136  pop     rdi
0x180030137  pop     rsi
0x180030138  pop     rbp
0x180030139  retn
```
