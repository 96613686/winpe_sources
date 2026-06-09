# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180016394`
- end: `0x18001664a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180015880`
- `0x180016a94`

## callees

- `0x180012550`
- `0x180013066`
- `0x180016394`
- `0x180016d94`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016547`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016547`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800164c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800164c6`

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
          v8 = (const char *)&qword_18003D748;
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
0x180016394  mov     [rsp+arg_18], rbx
0x180016399  push    rbp
0x18001639a  push    rsi
0x18001639b  push    rdi
0x18001639c  push    r14
0x18001639e  push    r15
0x1800163a0  sub     rsp, 250h
0x1800163a7  mov     rax, cs:__security_cookie
0x1800163ae  xor     rax, rsp
0x1800163b1  mov     [rsp+278h+var_38], rax
0x1800163b9  xor     r15d, r15d
0x1800163bc  mov     rbx, r8
0x1800163bf  mov     rsi, rdx
0x1800163c2  mov     r14, rcx
0x1800163c5  test    rdx, rdx
0x1800163c8  jz      loc_180016621
0x1800163ce  test    rcx, rcx
0x1800163d1  jz      loc_180016621
0x1800163d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800163de  mov     [rcx], r15w
0x1800163e2  test    rax, rax
0x1800163e5  jz      short loc_180016408
0x1800163e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800163ee  jz      short loc_180016408
0x1800163f0  mov     r8, rdx
0x1800163f3  mov     rdx, rcx
0x1800163f6  mov     rcx, rbx
0x1800163f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163fe  cmp     [r14], r15w
0x180016402  jnz     loc_180016621
0x180016408  mov     ecx, [rbx]
0x18001640a  mov     bpl, 8
0x18001640d  test    ecx, ecx
0x18001640f  jz      short loc_18001645A
0x180016411  sub     ecx, 1
0x180016414  jz      short loc_180016442
0x180016416  sub     ecx, 1
0x180016419  jz      short loc_180016432
0x18001641b  cmp     ecx, 1
0x18001641e  jz      short loc_180016429
0x180016420  lea     rdi, qword_18003D748
0x180016427  jmp     short loc_180016461
0x180016429  lea     rdi, aFailfast; "FailFast"
0x180016430  jmp     short loc_180016461
0x180016432  lea     rax, aLoghr; "LogHr"
0x180016439  lea     rdi, aLognt; "LogNt"
0x180016440  jmp     short loc_180016450
0x180016442  lea     rax, aReturnhr; "ReturnHr"
0x180016449  lea     rdi, aReturnnt; "ReturnNt"
0x180016450  test    [rbx+4], bpl
0x180016454  cmovz   rdi, rax
0x180016458  jmp     short loc_180016461
0x18001645a  lea     rdi, aException; "Exception"
0x180016461  xor     edx, edx; Val
0x180016463  lea     rcx, [rsp+278h+Buffer]; void *
0x180016468  mov     r8d, 200h; Size
0x18001646e  call    memset_0
0x180016473  test    [rbx+4], bpl
0x180016477  jz      short loc_18001649C
0x180016479  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180016480  mov     ebp, [rbx+0Ch]
0x180016483  test    rax, rax
0x180016486  jz      short loc_1800164CC
0x180016488  mov     r8d, 100h
0x18001648e  lea     rdx, [rsp+278h+Buffer]
0x180016493  mov     ecx, ebp
0x180016495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001649a  jmp     short loc_1800164CC
0x18001649c  mov     ebp, [rbx+8]
0x18001649f  lea     rax, [rsp+278h+Buffer]
0x1800164a4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800164a9  mov     r8d, ebp; dwMessageId
0x1800164ac  mov     [rsp+278h+nSize], 100h; nSize
0x1800164b4  mov     r9d, 400h; dwLanguageId
0x1800164ba  xor     edx, edx; lpSource
0x1800164bc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800164c1  mov     ecx, 1200h; dwFlags
0x1800164c6  call    cs:__imp_FormatMessageW
0x1800164cc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800164d0  lea     rsi, [r14+rsi*2]
0x1800164d4  mov     rax, [rbx+88h]
0x1800164db  mov     rdx, rsi; unsigned __int16 *
0x1800164de  mov     rcx, [rbx+80h]
0x1800164e5  test    r9, r9
0x1800164e8  jz      short loc_18001650C
0x1800164ea  mov     [rsp+278h+Arguments], rax
0x1800164ef  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800164f6  mov     eax, [rbx+40h]
0x1800164f9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800164fe  mov     rcx, r14; this
0x180016501  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180016505  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001650a  jmp     short loc_180016523
0x18001650c  mov     r9, rcx; unsigned __int16 *
0x18001650f  mov     [rsp+278h+lpBuffer], rax
0x180016514  mov     rcx, r14; this
0x180016517  lea     r8, aHsP; "%hs!%p: "
0x18001651e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016523  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001652a  mov     r14, rax
0x18001652d  test    r9, r9
0x180016530  jz      short loc_180016547
0x180016532  lea     r8, aCallerP; "(caller: %p) "
0x180016539  mov     rdx, rsi; unsigned __int16 *
0x18001653c  mov     rcx, rax; this
0x18001653f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016544  mov     r14, rax
0x180016547  call    cs:__imp_GetCurrentThreadId
0x18001654d  lea     rcx, [rsp+278h+Buffer]
0x180016552  mov     r9, rdi; unsigned __int16 *
0x180016555  mov     [rsp+278h+var_240], rcx
0x18001655a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180016561  mov     dword ptr [rsp+278h+Arguments], ebp
0x180016565  mov     rdx, rsi; unsigned __int16 *
0x180016568  mov     [rsp+278h+nSize], eax
0x18001656c  mov     rcx, r14; this
0x18001656f  mov     eax, [rbx+44h]
0x180016572  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180016576  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001657b  cmp     [rbx+18h], r15
0x18001657f  jnz     short loc_180016591
0x180016581  cmp     [rbx+48h], r15
0x180016585  jnz     short loc_180016591
0x180016587  cmp     [rbx+30h], r15
0x18001658b  jz      loc_180016621
0x180016591  lea     r8, asc_18003D838; "    "
0x180016598  mov     rdx, rsi; unsigned __int16 *
0x18001659b  mov     rcx, rax; this
0x18001659e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800165a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800165a7  test    r9, r9
0x1800165aa  jz      short loc_1800165BE
0x1800165ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800165b3  mov     rdx, rsi; unsigned __int16 *
0x1800165b6  mov     rcx, rax; this
0x1800165b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800165be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800165c2  test    r9, r9
0x1800165c5  jz      short loc_1800165D9
0x1800165c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800165ce  mov     rdx, rsi; unsigned __int16 *
0x1800165d1  mov     rcx, rax; this
0x1800165d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800165d9  mov     rcx, [rbx+28h]
0x1800165dd  mov     rdx, rsi; unsigned __int16 *
0x1800165e0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800165e4  test    rcx, rcx
0x1800165e7  jz      short loc_1800165FF
0x1800165e9  mov     [rsp+278h+lpBuffer], rcx
0x1800165ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800165f5  mov     rcx, rax; this
0x1800165f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800165fd  jmp     short loc_180016621
0x1800165ff  mov     rcx, rax; this
0x180016602  test    r9, r9
0x180016605  jz      short loc_180016615
0x180016607  lea     r8, aHs; "[%hs]\n"
0x18001660e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016613  jmp     short loc_180016621
0x180016615  lea     r8, asc_18003D8B0; "\n"
0x18001661c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016621  xor     eax, eax
0x180016623  mov     rcx, [rsp+278h+var_38]
0x18001662b  xor     rcx, rsp; StackCookie
0x18001662e  call    __security_check_cookie
0x180016633  mov     rbx, [rsp+278h+arg_18]
0x18001663b  add     rsp, 250h
0x180016642  pop     r15
0x180016644  pop     r14
0x180016646  pop     rdi
0x180016647  pop     rsi
0x180016648  pop     rbp
0x180016649  retn
```
