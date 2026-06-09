# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005354`
- end: `0x18000560a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002f14`
- `0x18000317c`
- `0x1800060c4`

## callees

- `0x180001670`
- `0x180001fa4`
- `0x180005354`
- `0x1800063c4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005486`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005486`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005507`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005507`

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
          v8 = (const char *)&word_18000FA56;
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
0x180005354  mov     [rsp+arg_18], rbx
0x180005359  push    rbp
0x18000535a  push    rsi
0x18000535b  push    rdi
0x18000535c  push    r14
0x18000535e  push    r15
0x180005360  sub     rsp, 250h
0x180005367  mov     rax, cs:__security_cookie
0x18000536e  xor     rax, rsp
0x180005371  mov     [rsp+278h+var_38], rax
0x180005379  xor     r15d, r15d
0x18000537c  mov     rbx, r8
0x18000537f  mov     rsi, rdx
0x180005382  mov     r14, rcx
0x180005385  test    rdx, rdx
0x180005388  jz      loc_1800055E1
0x18000538e  test    rcx, rcx
0x180005391  jz      loc_1800055E1
0x180005397  mov     rax, cs:g_pfnResultLoggingCallback
0x18000539e  mov     [rcx], r15w
0x1800053a2  test    rax, rax
0x1800053a5  jz      short loc_1800053C8
0x1800053a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800053ae  jz      short loc_1800053C8
0x1800053b0  mov     r8, rdx
0x1800053b3  mov     rdx, rcx
0x1800053b6  mov     rcx, rbx
0x1800053b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053be  cmp     [r14], r15w
0x1800053c2  jnz     loc_1800055E1
0x1800053c8  mov     ecx, [rbx]
0x1800053ca  mov     bpl, 8
0x1800053cd  test    ecx, ecx
0x1800053cf  jz      short loc_18000541A
0x1800053d1  sub     ecx, 1
0x1800053d4  jz      short loc_180005402
0x1800053d6  sub     ecx, 1
0x1800053d9  jz      short loc_1800053F2
0x1800053db  cmp     ecx, 1
0x1800053de  jz      short loc_1800053E9
0x1800053e0  lea     rdi, word_18000FA56
0x1800053e7  jmp     short loc_180005421
0x1800053e9  lea     rdi, aFailfast; "FailFast"
0x1800053f0  jmp     short loc_180005421
0x1800053f2  lea     rax, aLoghr; "LogHr"
0x1800053f9  lea     rdi, aLognt; "LogNt"
0x180005400  jmp     short loc_180005410
0x180005402  lea     rax, aReturnhr; "ReturnHr"
0x180005409  lea     rdi, aReturnnt; "ReturnNt"
0x180005410  test    [rbx+4], bpl
0x180005414  cmovz   rdi, rax
0x180005418  jmp     short loc_180005421
0x18000541a  lea     rdi, aException; "Exception"
0x180005421  xor     edx, edx; Val
0x180005423  lea     rcx, [rsp+278h+Buffer]; void *
0x180005428  mov     r8d, 200h; Size
0x18000542e  call    memset_0
0x180005433  test    [rbx+4], bpl
0x180005437  jz      short loc_18000545C
0x180005439  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005440  mov     ebp, [rbx+0Ch]
0x180005443  test    rax, rax
0x180005446  jz      short loc_18000548C
0x180005448  mov     r8d, 100h
0x18000544e  lea     rdx, [rsp+278h+Buffer]
0x180005453  mov     ecx, ebp
0x180005455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000545a  jmp     short loc_18000548C
0x18000545c  mov     ebp, [rbx+8]
0x18000545f  lea     rax, [rsp+278h+Buffer]
0x180005464  mov     [rsp+278h+Arguments], r15; Arguments
0x180005469  mov     r8d, ebp; dwMessageId
0x18000546c  mov     [rsp+278h+nSize], 100h; nSize
0x180005474  mov     r9d, 400h; dwLanguageId
0x18000547a  xor     edx, edx; lpSource
0x18000547c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005481  mov     ecx, 1200h; dwFlags
0x180005486  call    cs:__imp_FormatMessageW
0x18000548c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005490  lea     rsi, [r14+rsi*2]
0x180005494  mov     rax, [rbx+88h]
0x18000549b  mov     rdx, rsi; unsigned __int16 *
0x18000549e  mov     rcx, [rbx+80h]
0x1800054a5  test    r9, r9
0x1800054a8  jz      short loc_1800054CC
0x1800054aa  mov     [rsp+278h+Arguments], rax
0x1800054af  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800054b6  mov     eax, [rbx+40h]
0x1800054b9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800054be  mov     rcx, r14; this
0x1800054c1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800054c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054ca  jmp     short loc_1800054E3
0x1800054cc  mov     r9, rcx; unsigned __int16 *
0x1800054cf  mov     [rsp+278h+lpBuffer], rax
0x1800054d4  mov     rcx, r14; this
0x1800054d7  lea     r8, aHsP; "%hs!%p: "
0x1800054de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054e3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800054ea  mov     r14, rax
0x1800054ed  test    r9, r9
0x1800054f0  jz      short loc_180005507
0x1800054f2  lea     r8, aCallerP; "(caller: %p) "
0x1800054f9  mov     rdx, rsi; unsigned __int16 *
0x1800054fc  mov     rcx, rax; this
0x1800054ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005504  mov     r14, rax
0x180005507  call    cs:__imp_GetCurrentThreadId
0x18000550d  lea     rcx, [rsp+278h+Buffer]
0x180005512  mov     r9, rdi; unsigned __int16 *
0x180005515  mov     [rsp+278h+var_240], rcx
0x18000551a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005521  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005525  mov     rdx, rsi; unsigned __int16 *
0x180005528  mov     [rsp+278h+nSize], eax
0x18000552c  mov     rcx, r14; this
0x18000552f  mov     eax, [rbx+44h]
0x180005532  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005536  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000553b  cmp     [rbx+18h], r15
0x18000553f  jnz     short loc_180005551
0x180005541  cmp     [rbx+48h], r15
0x180005545  jnz     short loc_180005551
0x180005547  cmp     [rbx+30h], r15
0x18000554b  jz      loc_1800055E1
0x180005551  lea     r8, asc_18000FB40; "    "
0x180005558  mov     rdx, rsi; unsigned __int16 *
0x18000555b  mov     rcx, rax; this
0x18000555e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005563  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005567  test    r9, r9
0x18000556a  jz      short loc_18000557E
0x18000556c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005573  mov     rdx, rsi; unsigned __int16 *
0x180005576  mov     rcx, rax; this
0x180005579  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000557e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005582  test    r9, r9
0x180005585  jz      short loc_180005599
0x180005587  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000558e  mov     rdx, rsi; unsigned __int16 *
0x180005591  mov     rcx, rax; this
0x180005594  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005599  mov     rcx, [rbx+28h]
0x18000559d  mov     rdx, rsi; unsigned __int16 *
0x1800055a0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800055a4  test    rcx, rcx
0x1800055a7  jz      short loc_1800055BF
0x1800055a9  mov     [rsp+278h+lpBuffer], rcx
0x1800055ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800055b5  mov     rcx, rax; this
0x1800055b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055bd  jmp     short loc_1800055E1
0x1800055bf  mov     rcx, rax; this
0x1800055c2  test    r9, r9
0x1800055c5  jz      short loc_1800055D5
0x1800055c7  lea     r8, aHs; "[%hs]\n"
0x1800055ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055d3  jmp     short loc_1800055E1
0x1800055d5  lea     r8, asc_18000FBB8; "\n"
0x1800055dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055e1  xor     eax, eax
0x1800055e3  mov     rcx, [rsp+278h+var_38]
0x1800055eb  xor     rcx, rsp; StackCookie
0x1800055ee  call    __security_check_cookie
0x1800055f3  mov     rbx, [rsp+278h+arg_18]
0x1800055fb  add     rsp, 250h
0x180005602  pop     r15
0x180005604  pop     r14
0x180005606  pop     rdi
0x180005607  pop     rsi
0x180005608  pop     rbp
0x180005609  retn
```
