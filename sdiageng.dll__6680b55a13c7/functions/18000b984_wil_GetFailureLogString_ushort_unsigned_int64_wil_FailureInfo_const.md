# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b984`
- end: `0x18000bc3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180008750`
- `0x1800089b8`
- `0x18000dee8`
- `0x180012d80`

## callees

- `0x18000b984`
- `0x18000e1e8`
- `0x180029882`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000bab6`
- `KERNEL32!FormatMessageW` at `0x18000bab6`
- `KERNEL32!GetCurrentThreadId` at `0x18000bb37`
- `KERNEL32!GetCurrentThreadId` at `0x18000bb37`

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
          v7 = (const char *)&qword_18002F518;
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
0x18000b984  mov     [rsp+arg_18], rbx
0x18000b989  push    rbp
0x18000b98a  push    rsi
0x18000b98b  push    rdi
0x18000b98c  push    r14
0x18000b98e  push    r15
0x18000b990  sub     rsp, 250h
0x18000b997  mov     rax, cs:__security_cookie
0x18000b99e  xor     rax, rsp
0x18000b9a1  mov     [rsp+278h+var_38], rax
0x18000b9a9  mov     rbx, r8
0x18000b9ac  mov     rsi, rdx
0x18000b9af  mov     r14, rcx
0x18000b9b2  xor     r15d, r15d
0x18000b9b5  test    rdx, rdx
0x18000b9b8  jz      loc_18000BC11
0x18000b9be  test    rcx, rcx
0x18000b9c1  jz      loc_18000BC11
0x18000b9c7  mov     [rcx], r15w
0x18000b9cb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b9d2  test    rax, rax
0x18000b9d5  jz      short loc_18000B9F8
0x18000b9d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b9de  jz      short loc_18000B9F8
0x18000b9e0  mov     r8, rdx
0x18000b9e3  mov     rdx, rcx
0x18000b9e6  mov     rcx, rbx
0x18000b9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9ee  cmp     [r14], r15w
0x18000b9f2  jnz     loc_18000BC11
0x18000b9f8  mov     ecx, [rbx]
0x18000b9fa  mov     bpl, 8
0x18000b9fd  test    ecx, ecx
0x18000b9ff  jz      short loc_18000BA4A
0x18000ba01  sub     ecx, 1
0x18000ba04  jz      short loc_18000BA32
0x18000ba06  sub     ecx, 1
0x18000ba09  jz      short loc_18000BA22
0x18000ba0b  cmp     ecx, 1
0x18000ba0e  jz      short loc_18000BA19
0x18000ba10  lea     rdi, qword_18002F518
0x18000ba17  jmp     short loc_18000BA51
0x18000ba19  lea     rdi, aFailfast; "FailFast"
0x18000ba20  jmp     short loc_18000BA51
0x18000ba22  lea     rax, aLoghr; "LogHr"
0x18000ba29  lea     rdi, aLognt; "LogNt"
0x18000ba30  jmp     short loc_18000BA40
0x18000ba32  lea     rax, aReturnhr; "ReturnHr"
0x18000ba39  lea     rdi, aReturnnt; "ReturnNt"
0x18000ba40  test    [rbx+4], bpl
0x18000ba44  cmovz   rdi, rax
0x18000ba48  jmp     short loc_18000BA51
0x18000ba4a  lea     rdi, aException; "Exception"
0x18000ba51  xor     edx, edx; Val
0x18000ba53  mov     r8d, 200h; Size
0x18000ba59  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ba5e  call    memset_0
0x18000ba63  test    [rbx+4], bpl
0x18000ba67  jz      short loc_18000BA8C
0x18000ba69  mov     ebp, [rbx+0Ch]
0x18000ba6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ba73  test    rax, rax
0x18000ba76  jz      short loc_18000BABC
0x18000ba78  mov     r8d, 100h
0x18000ba7e  lea     rdx, [rsp+278h+Buffer]
0x18000ba83  mov     ecx, ebp
0x18000ba85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba8a  jmp     short loc_18000BABC
0x18000ba8c  mov     ebp, [rbx+8]
0x18000ba8f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000ba94  mov     [rsp+278h+nSize], 100h; nSize
0x18000ba9c  lea     rax, [rsp+278h+Buffer]
0x18000baa1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000baa6  mov     r9d, 400h; dwLanguageId
0x18000baac  mov     r8d, ebp; dwMessageId
0x18000baaf  xor     edx, edx; lpSource
0x18000bab1  mov     ecx, 1200h; dwFlags
0x18000bab6  call    cs:__imp_FormatMessageW
0x18000babc  lea     rsi, [r14+rsi*2]
0x18000bac0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000bac4  mov     rax, [rbx+88h]
0x18000bacb  mov     rcx, [rbx+80h]
0x18000bad2  mov     rdx, rsi; unsigned __int16 *
0x18000bad5  test    r9, r9
0x18000bad8  jz      short loc_18000BAFC
0x18000bada  mov     [rsp+278h+Arguments], rax
0x18000badf  mov     qword ptr [rsp+278h+nSize], rcx
0x18000bae4  mov     eax, [rbx+40h]
0x18000bae7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000baeb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000baf2  mov     rcx, r14; this
0x18000baf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bafa  jmp     short loc_18000BB13
0x18000bafc  mov     [rsp+278h+lpBuffer], rax
0x18000bb01  mov     r9, rcx; unsigned __int16 *
0x18000bb04  lea     r8, aHsP; "%hs!%p: "
0x18000bb0b  mov     rcx, r14; this
0x18000bb0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb13  mov     r14, rax
0x18000bb16  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000bb1d  test    r9, r9
0x18000bb20  jz      short loc_18000BB37
0x18000bb22  lea     r8, aCallerP; "(caller: %p) "
0x18000bb29  mov     rdx, rsi; unsigned __int16 *
0x18000bb2c  mov     rcx, rax; this
0x18000bb2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb34  mov     r14, rax
0x18000bb37  call    cs:__imp_GetCurrentThreadId
0x18000bb3d  lea     rcx, [rsp+278h+Buffer]
0x18000bb42  mov     [rsp+278h+var_240], rcx
0x18000bb47  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000bb4b  mov     [rsp+278h+nSize], eax
0x18000bb4f  mov     eax, [rbx+44h]
0x18000bb52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bb56  mov     r9, rdi; unsigned __int16 *
0x18000bb59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000bb60  mov     rdx, rsi; unsigned __int16 *
0x18000bb63  mov     rcx, r14; this
0x18000bb66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb6b  cmp     [rbx+18h], r15
0x18000bb6f  jnz     short loc_18000BB81
0x18000bb71  cmp     [rbx+48h], r15
0x18000bb75  jnz     short loc_18000BB81
0x18000bb77  cmp     [rbx+30h], r15
0x18000bb7b  jz      loc_18000BC11
0x18000bb81  lea     r8, asc_18002E5F8; "    "
0x18000bb88  mov     rdx, rsi; unsigned __int16 *
0x18000bb8b  mov     rcx, rax; this
0x18000bb8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb93  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000bb97  test    r9, r9
0x18000bb9a  jz      short loc_18000BBAE
0x18000bb9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000bba3  mov     rdx, rsi; unsigned __int16 *
0x18000bba6  mov     rcx, rax; this
0x18000bba9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000bbb2  test    r9, r9
0x18000bbb5  jz      short loc_18000BBC9
0x18000bbb7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000bbbe  mov     rdx, rsi; unsigned __int16 *
0x18000bbc1  mov     rcx, rax; this
0x18000bbc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbc9  mov     rcx, [rbx+28h]
0x18000bbcd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000bbd1  mov     rdx, rsi; unsigned __int16 *
0x18000bbd4  test    rcx, rcx
0x18000bbd7  jz      short loc_18000BBEF
0x18000bbd9  mov     [rsp+278h+lpBuffer], rcx
0x18000bbde  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000bbe5  mov     rcx, rax; this
0x18000bbe8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbed  jmp     short loc_18000BC11
0x18000bbef  mov     rcx, rax; this
0x18000bbf2  test    r9, r9
0x18000bbf5  jz      short loc_18000BC05
0x18000bbf7  lea     r8, aHs; "[%hs]\n"
0x18000bbfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc03  jmp     short loc_18000BC11
0x18000bc05  lea     r8, asc_18002E670; "\n"
0x18000bc0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc11  xor     eax, eax
0x18000bc13  mov     rcx, [rsp+278h+var_38]
0x18000bc1b  xor     rcx, rsp; StackCookie
0x18000bc1e  call    __security_check_cookie
0x18000bc23  mov     rbx, [rsp+278h+arg_18]
0x18000bc2b  add     rsp, 250h
0x18000bc32  pop     r15
0x18000bc34  pop     r14
0x18000bc36  pop     rdi
0x18000bc37  pop     rsi
0x18000bc38  pop     rbp
0x18000bc39  retn
```
