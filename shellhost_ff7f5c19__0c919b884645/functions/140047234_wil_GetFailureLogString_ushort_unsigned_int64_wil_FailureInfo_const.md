# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140047234`
- end: `0x1400474ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140047cd8`
- `0x14004b500`

## callees

- `0x14000f7e0`
- `0x14001062c`
- `0x140047234`
- `0x140047fb4`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400473e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400473e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140047366`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140047366`

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
          v7 = (const char *)&qword_14006D7D8;
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
0x140047234  mov     [rsp+arg_18], rbx
0x140047239  push    rbp
0x14004723a  push    rsi
0x14004723b  push    rdi
0x14004723c  push    r14
0x14004723e  push    r15
0x140047240  sub     rsp, 250h
0x140047247  mov     rax, cs:__security_cookie
0x14004724e  xor     rax, rsp
0x140047251  mov     [rsp+278h+var_38], rax
0x140047259  mov     rbx, r8
0x14004725c  mov     rsi, rdx
0x14004725f  mov     r14, rcx
0x140047262  xor     r15d, r15d
0x140047265  test    rdx, rdx
0x140047268  jz      loc_1400474C1
0x14004726e  test    rcx, rcx
0x140047271  jz      loc_1400474C1
0x140047277  mov     [rcx], r15w
0x14004727b  mov     rax, cs:g_pfnResultLoggingCallback
0x140047282  test    rax, rax
0x140047285  jz      short loc_1400472A8
0x140047287  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14004728e  jz      short loc_1400472A8
0x140047290  mov     r8, rdx
0x140047293  mov     rdx, rcx
0x140047296  mov     rcx, rbx
0x140047299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004729e  cmp     [r14], r15w
0x1400472a2  jnz     loc_1400474C1
0x1400472a8  mov     ecx, [rbx]
0x1400472aa  mov     bpl, 8
0x1400472ad  test    ecx, ecx
0x1400472af  jz      short loc_1400472FA
0x1400472b1  sub     ecx, 1
0x1400472b4  jz      short loc_1400472E2
0x1400472b6  sub     ecx, 1
0x1400472b9  jz      short loc_1400472D2
0x1400472bb  cmp     ecx, 1
0x1400472be  jz      short loc_1400472C9
0x1400472c0  lea     rdi, qword_14006D7D8
0x1400472c7  jmp     short loc_140047301
0x1400472c9  lea     rdi, aFailfast; "FailFast"
0x1400472d0  jmp     short loc_140047301
0x1400472d2  lea     rax, aLoghr; "LogHr"
0x1400472d9  lea     rdi, aLognt; "LogNt"
0x1400472e0  jmp     short loc_1400472F0
0x1400472e2  lea     rax, aReturnhr; "ReturnHr"
0x1400472e9  lea     rdi, aReturnnt; "ReturnNt"
0x1400472f0  test    [rbx+4], bpl
0x1400472f4  cmovz   rdi, rax
0x1400472f8  jmp     short loc_140047301
0x1400472fa  lea     rdi, aException; "Exception"
0x140047301  xor     edx, edx; Val
0x140047303  mov     r8d, 200h; Size
0x140047309  lea     rcx, [rsp+278h+Buffer]; void *
0x14004730e  call    memset_0
0x140047313  test    [rbx+4], bpl
0x140047317  jz      short loc_14004733C
0x140047319  mov     ebp, [rbx+0Ch]
0x14004731c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140047323  test    rax, rax
0x140047326  jz      short loc_14004736C
0x140047328  mov     r8d, 100h
0x14004732e  lea     rdx, [rsp+278h+Buffer]
0x140047333  mov     ecx, ebp
0x140047335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004733a  jmp     short loc_14004736C
0x14004733c  mov     ebp, [rbx+8]
0x14004733f  mov     [rsp+278h+Arguments], r15; Arguments
0x140047344  mov     [rsp+278h+nSize], 100h; nSize
0x14004734c  lea     rax, [rsp+278h+Buffer]
0x140047351  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140047356  mov     r9d, 400h; dwLanguageId
0x14004735c  mov     r8d, ebp; dwMessageId
0x14004735f  xor     edx, edx; lpSource
0x140047361  mov     ecx, 1200h; dwFlags
0x140047366  call    cs:__imp_FormatMessageW
0x14004736c  lea     rsi, [r14+rsi*2]
0x140047370  mov     r9, [rbx+38h]; unsigned __int16 *
0x140047374  mov     rax, [rbx+88h]
0x14004737b  mov     rcx, [rbx+80h]
0x140047382  mov     rdx, rsi; unsigned __int16 *
0x140047385  test    r9, r9
0x140047388  jz      short loc_1400473AC
0x14004738a  mov     [rsp+278h+Arguments], rax
0x14004738f  mov     qword ptr [rsp+278h+nSize], rcx
0x140047394  mov     eax, [rbx+40h]
0x140047397  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14004739b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400473a2  mov     rcx, r14; this
0x1400473a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400473aa  jmp     short loc_1400473C3
0x1400473ac  mov     [rsp+278h+lpBuffer], rax
0x1400473b1  mov     r9, rcx; unsigned __int16 *
0x1400473b4  lea     r8, aHsP; "%hs!%p: "
0x1400473bb  mov     rcx, r14; this
0x1400473be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400473c3  mov     r14, rax
0x1400473c6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400473cd  test    r9, r9
0x1400473d0  jz      short loc_1400473E7
0x1400473d2  lea     r8, aCallerP; "(caller: %p) "
0x1400473d9  mov     rdx, rsi; unsigned __int16 *
0x1400473dc  mov     rcx, rax; this
0x1400473df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400473e4  mov     r14, rax
0x1400473e7  call    cs:__imp_GetCurrentThreadId
0x1400473ed  lea     rcx, [rsp+278h+Buffer]
0x1400473f2  mov     [rsp+278h+var_240], rcx
0x1400473f7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400473fb  mov     [rsp+278h+nSize], eax
0x1400473ff  mov     eax, [rbx+44h]
0x140047402  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140047406  mov     r9, rdi; unsigned __int16 *
0x140047409  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140047410  mov     rdx, rsi; unsigned __int16 *
0x140047413  mov     rcx, r14; this
0x140047416  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14004741b  cmp     [rbx+18h], r15
0x14004741f  jnz     short loc_140047431
0x140047421  cmp     [rbx+48h], r15
0x140047425  jnz     short loc_140047431
0x140047427  cmp     [rbx+30h], r15
0x14004742b  jz      loc_1400474C1
0x140047431  lea     r8, asc_14006D8E8; "    "
0x140047438  mov     rdx, rsi; unsigned __int16 *
0x14004743b  mov     rcx, rax; this
0x14004743e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140047443  mov     r9, [rbx+18h]; unsigned __int16 *
0x140047447  test    r9, r9
0x14004744a  jz      short loc_14004745E
0x14004744c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140047453  mov     rdx, rsi; unsigned __int16 *
0x140047456  mov     rcx, rax; this
0x140047459  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14004745e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140047462  test    r9, r9
0x140047465  jz      short loc_140047479
0x140047467  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14004746e  mov     rdx, rsi; unsigned __int16 *
0x140047471  mov     rcx, rax; this
0x140047474  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140047479  mov     rcx, [rbx+28h]
0x14004747d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140047481  mov     rdx, rsi; unsigned __int16 *
0x140047484  test    rcx, rcx
0x140047487  jz      short loc_14004749F
0x140047489  mov     [rsp+278h+lpBuffer], rcx
0x14004748e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140047495  mov     rcx, rax; this
0x140047498  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14004749d  jmp     short loc_1400474C1
0x14004749f  mov     rcx, rax; this
0x1400474a2  test    r9, r9
0x1400474a5  jz      short loc_1400474B5
0x1400474a7  lea     r8, aHs; "[%hs]\n"
0x1400474ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400474b3  jmp     short loc_1400474C1
0x1400474b5  lea     r8, asc_14006D960; "\n"
0x1400474bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400474c1  xor     eax, eax
0x1400474c3  mov     rcx, [rsp+278h+var_38]
0x1400474cb  xor     rcx, rsp; StackCookie
0x1400474ce  call    __security_check_cookie
0x1400474d3  mov     rbx, [rsp+278h+arg_18]
0x1400474db  add     rsp, 250h
0x1400474e2  pop     r15
0x1400474e4  pop     r14
0x1400474e6  pop     rdi
0x1400474e7  pop     rsi
0x1400474e8  pop     rbp
0x1400474e9  retn
```
