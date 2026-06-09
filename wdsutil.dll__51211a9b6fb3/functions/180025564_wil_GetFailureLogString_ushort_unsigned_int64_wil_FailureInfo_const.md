# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180025564`
- end: `0x180025832`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `718`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180021c6c`
- `0x180021efc`
- `0x180026050`
- `0x180029670`

## callees

- `0x180025564`
- `0x18002636c`
- `0x1800319ae`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800256a1`
- `KERNEL32!FormatMessageW` at `0x1800256a1`
- `KERNEL32!GetCurrentThreadId` at `0x180025728`
- `KERNEL32!GetCurrentThreadId` at `0x180025728`

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
          v7 = (const char *)&word_18003B8F6;
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
0x180025564  mov     rax, rsp
0x180025567  push    rbp
0x180025568  push    rsi
0x180025569  push    rdi
0x18002556a  push    r14
0x18002556c  push    r15
0x18002556e  sub     rsp, 260h
0x180025575  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18002557e  mov     [rax+20h], rbx
0x180025582  mov     rax, cs:__security_cookie
0x180025589  xor     rax, rsp
0x18002558c  mov     [rsp+288h+var_38], rax
0x180025594  mov     rbx, r8
0x180025597  mov     rsi, rdx
0x18002559a  mov     r14, rcx
0x18002559d  xor     r15d, r15d
0x1800255a0  test    rdx, rdx
0x1800255a3  jz      loc_180025808
0x1800255a9  test    rcx, rcx
0x1800255ac  jz      loc_180025808
0x1800255b2  mov     [rcx], r15w
0x1800255b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800255bd  test    rax, rax
0x1800255c0  jz      short loc_1800255E3
0x1800255c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800255c9  jz      short loc_1800255E3
0x1800255cb  mov     r8, rdx
0x1800255ce  mov     rdx, rcx
0x1800255d1  mov     rcx, rbx
0x1800255d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255d9  cmp     [r14], r15w
0x1800255dd  jnz     loc_180025808
0x1800255e3  mov     ecx, [rbx]
0x1800255e5  mov     bpl, 8
0x1800255e8  test    ecx, ecx
0x1800255ea  jz      short loc_180025635
0x1800255ec  sub     ecx, 1
0x1800255ef  jz      short loc_18002561D
0x1800255f1  sub     ecx, 1
0x1800255f4  jz      short loc_18002560D
0x1800255f6  cmp     ecx, 1
0x1800255f9  jz      short loc_180025604
0x1800255fb  lea     rdi, word_18003B8F6
0x180025602  jmp     short loc_18002563C
0x180025604  lea     rdi, aFailfast; "FailFast"
0x18002560b  jmp     short loc_18002563C
0x18002560d  lea     rax, aLoghr; "LogHr"
0x180025614  lea     rdi, aLognt; "LogNt"
0x18002561b  jmp     short loc_18002562B
0x18002561d  lea     rax, aReturnhr; "ReturnHr"
0x180025624  lea     rdi, aReturnnt; "ReturnNt"
0x18002562b  test    [rbx+4], bpl
0x18002562f  cmovz   rdi, rax
0x180025633  jmp     short loc_18002563C
0x180025635  lea     rdi, aException; "Exception"
0x18002563c  xor     edx, edx; Val
0x18002563e  mov     r8d, 200h; Size
0x180025644  lea     rcx, [rsp+288h+Buffer]; void *
0x180025649  call    memset_0
0x18002564e  test    [rbx+4], bpl
0x180025652  jz      short loc_180025677
0x180025654  mov     ebp, [rbx+0Ch]
0x180025657  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002565e  test    rax, rax
0x180025661  jz      short loc_1800256AD
0x180025663  mov     r8d, 100h
0x180025669  lea     rdx, [rsp+288h+Buffer]
0x18002566e  mov     ecx, ebp
0x180025670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025675  jmp     short loc_1800256AD
0x180025677  mov     ebp, [rbx+8]
0x18002567a  mov     [rsp+288h+Arguments], r15; Arguments
0x18002567f  mov     [rsp+288h+nSize], 100h; nSize
0x180025687  lea     rax, [rsp+288h+Buffer]
0x18002568c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180025691  mov     r9d, 400h; dwLanguageId
0x180025697  mov     r8d, ebp; dwMessageId
0x18002569a  xor     edx, edx; lpSource
0x18002569c  mov     ecx, 1200h; dwFlags
0x1800256a1  call    cs:__imp_FormatMessageW
0x1800256a8  nop     dword ptr [rax+rax+00h]
0x1800256ad  lea     rsi, [r14+rsi*2]
0x1800256b1  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800256b5  mov     rax, [rbx+88h]
0x1800256bc  mov     rcx, [rbx+80h]
0x1800256c3  mov     rdx, rsi; unsigned __int16 *
0x1800256c6  test    r9, r9
0x1800256c9  jz      short loc_1800256ED
0x1800256cb  mov     [rsp+288h+Arguments], rax
0x1800256d0  mov     qword ptr [rsp+288h+nSize], rcx
0x1800256d5  mov     eax, [rbx+40h]
0x1800256d8  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800256dc  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800256e3  mov     rcx, r14; this
0x1800256e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800256eb  jmp     short loc_180025704
0x1800256ed  mov     [rsp+288h+lpBuffer], rax
0x1800256f2  mov     r9, rcx; unsigned __int16 *
0x1800256f5  lea     r8, aHsP; "%hs!%p: "
0x1800256fc  mov     rcx, r14; this
0x1800256ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025704  mov     r14, rax
0x180025707  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002570e  test    r9, r9
0x180025711  jz      short loc_180025728
0x180025713  lea     r8, aCallerP; "(caller: %p) "
0x18002571a  mov     rdx, rsi; unsigned __int16 *
0x18002571d  mov     rcx, rax; this
0x180025720  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025725  mov     r14, rax
0x180025728  call    cs:__imp_GetCurrentThreadId
0x18002572f  nop     dword ptr [rax+rax+00h]
0x180025734  lea     rcx, [rsp+288h+Buffer]
0x180025739  mov     [rsp+288h+var_250], rcx
0x18002573e  mov     dword ptr [rsp+288h+Arguments], ebp
0x180025742  mov     [rsp+288h+nSize], eax
0x180025746  mov     eax, [rbx+44h]
0x180025749  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18002574d  mov     r9, rdi; unsigned __int16 *
0x180025750  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180025757  mov     rdx, rsi; unsigned __int16 *
0x18002575a  mov     rcx, r14; this
0x18002575d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025762  cmp     [rbx+18h], r15
0x180025766  jnz     short loc_180025778
0x180025768  cmp     [rbx+48h], r15
0x18002576c  jnz     short loc_180025778
0x18002576e  cmp     [rbx+30h], r15
0x180025772  jz      loc_180025808
0x180025778  lea     r8, asc_18003B628; "    "
0x18002577f  mov     rdx, rsi; unsigned __int16 *
0x180025782  mov     rcx, rax; this
0x180025785  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002578a  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002578e  test    r9, r9
0x180025791  jz      short loc_1800257A5
0x180025793  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002579a  mov     rdx, rsi; unsigned __int16 *
0x18002579d  mov     rcx, rax; this
0x1800257a0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800257a5  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800257a9  test    r9, r9
0x1800257ac  jz      short loc_1800257C0
0x1800257ae  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800257b5  mov     rdx, rsi; unsigned __int16 *
0x1800257b8  mov     rcx, rax; this
0x1800257bb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800257c0  mov     rcx, [rbx+28h]
0x1800257c4  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800257c8  mov     rdx, rsi; unsigned __int16 *
0x1800257cb  test    rcx, rcx
0x1800257ce  jz      short loc_1800257E6
0x1800257d0  mov     [rsp+288h+lpBuffer], rcx
0x1800257d5  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800257dc  mov     rcx, rax; this
0x1800257df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800257e4  jmp     short loc_180025808
0x1800257e6  mov     rcx, rax; this
0x1800257e9  test    r9, r9
0x1800257ec  jz      short loc_1800257FC
0x1800257ee  lea     r8, aHs; "[%hs]\n"
0x1800257f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800257fa  jmp     short loc_180025808
0x1800257fc  lea     r8, asc_18003B6A0; "\n"
0x180025803  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025808  xor     eax, eax
0x18002580a  mov     rcx, [rsp+288h+var_38]
0x180025812  xor     rcx, rsp; StackCookie
0x180025815  call    __security_check_cookie
0x18002581a  mov     rbx, [rsp+288h+arg_18]
0x180025822  add     rsp, 260h
0x180025829  pop     r15
0x18002582b  pop     r14
0x18002582d  pop     rdi
0x18002582e  pop     rsi
0x18002582f  pop     rbp
0x180025830  retn
```
