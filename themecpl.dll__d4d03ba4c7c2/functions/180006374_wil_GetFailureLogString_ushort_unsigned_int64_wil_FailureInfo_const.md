# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006374`
- end: `0x180006637`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180004d78`
- `0x18000500c`
- `0x180006df0`
- `0x180008ac0`
- `0x18002e76c`
- `0x180055930`
- `0x180055a64`
- `0x180055bcd`
- `0x180055e33`

## callees

- `0x180002280`
- `0x180002f34`
- `0x180006374`
- `0x180007104`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000652d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000652d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800064a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800064a6`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&word_18005D14E;
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
0x180006374  mov     [rsp+arg_18], rbx
0x180006379  push    rbp
0x18000637a  push    rsi
0x18000637b  push    rdi
0x18000637c  push    r14
0x18000637e  push    r15
0x180006380  sub     rsp, 250h
0x180006387  mov     rax, cs:__security_cookie
0x18000638e  xor     rax, rsp
0x180006391  mov     [rsp+278h+var_38], rax
0x180006399  mov     rbx, r8
0x18000639c  mov     rsi, rdx
0x18000639f  mov     r14, rcx
0x1800063a2  xor     r15d, r15d
0x1800063a5  test    rdx, rdx
0x1800063a8  jz      loc_18000660D
0x1800063ae  test    rcx, rcx
0x1800063b1  jz      loc_18000660D
0x1800063b7  mov     [rcx], r15w
0x1800063bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800063c2  test    rax, rax
0x1800063c5  jz      short loc_1800063E8
0x1800063c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800063ce  jz      short loc_1800063E8
0x1800063d0  mov     r8, rdx
0x1800063d3  mov     rdx, rcx
0x1800063d6  mov     rcx, rbx
0x1800063d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063de  cmp     [r14], r15w
0x1800063e2  jnz     loc_18000660D
0x1800063e8  mov     ecx, [rbx]
0x1800063ea  mov     bpl, 8
0x1800063ed  test    ecx, ecx
0x1800063ef  jz      short loc_18000643A
0x1800063f1  sub     ecx, 1
0x1800063f4  jz      short loc_180006422
0x1800063f6  sub     ecx, 1
0x1800063f9  jz      short loc_180006412
0x1800063fb  cmp     ecx, 1
0x1800063fe  jz      short loc_180006409
0x180006400  lea     rdi, word_18005D14E
0x180006407  jmp     short loc_180006441
0x180006409  lea     rdi, aFailfast; "FailFast"
0x180006410  jmp     short loc_180006441
0x180006412  lea     rax, aLoghr; "LogHr"
0x180006419  lea     rdi, aLognt; "LogNt"
0x180006420  jmp     short loc_180006430
0x180006422  lea     rax, aReturnhr; "ReturnHr"
0x180006429  lea     rdi, aReturnnt; "ReturnNt"
0x180006430  test    [rbx+4], bpl
0x180006434  cmovz   rdi, rax
0x180006438  jmp     short loc_180006441
0x18000643a  lea     rdi, aException; "Exception"
0x180006441  xor     edx, edx; Val
0x180006443  mov     r8d, 200h; Size
0x180006449  lea     rcx, [rsp+278h+Buffer]; void *
0x18000644e  call    memset_0
0x180006453  test    [rbx+4], bpl
0x180006457  jz      short loc_18000647C
0x180006459  mov     ebp, [rbx+0Ch]
0x18000645c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006463  test    rax, rax
0x180006466  jz      short loc_1800064B2
0x180006468  mov     r8d, 100h
0x18000646e  lea     rdx, [rsp+278h+Buffer]
0x180006473  mov     ecx, ebp
0x180006475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000647a  jmp     short loc_1800064B2
0x18000647c  mov     ebp, [rbx+8]
0x18000647f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006484  mov     [rsp+278h+nSize], 100h; nSize
0x18000648c  lea     rax, [rsp+278h+Buffer]
0x180006491  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006496  mov     r9d, 400h; dwLanguageId
0x18000649c  mov     r8d, ebp; dwMessageId
0x18000649f  xor     edx, edx; lpSource
0x1800064a1  mov     ecx, 1200h; dwFlags
0x1800064a6  call    cs:__imp_FormatMessageW
0x1800064ad  nop     dword ptr [rax+rax+00h]
0x1800064b2  lea     rsi, [r14+rsi*2]
0x1800064b6  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800064ba  mov     rax, [rbx+88h]
0x1800064c1  mov     rcx, [rbx+80h]
0x1800064c8  mov     rdx, rsi; unsigned __int16 *
0x1800064cb  test    r9, r9
0x1800064ce  jz      short loc_1800064F2
0x1800064d0  mov     [rsp+278h+Arguments], rax
0x1800064d5  mov     qword ptr [rsp+278h+nSize], rcx
0x1800064da  mov     eax, [rbx+40h]
0x1800064dd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800064e1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800064e8  mov     rcx, r14; this
0x1800064eb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800064f0  jmp     short loc_180006509
0x1800064f2  mov     [rsp+278h+lpBuffer], rax
0x1800064f7  mov     r9, rcx; unsigned __int16 *
0x1800064fa  lea     r8, aHsP; "%hs!%p: "
0x180006501  mov     rcx, r14; this
0x180006504  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006509  mov     r14, rax
0x18000650c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006513  test    r9, r9
0x180006516  jz      short loc_18000652D
0x180006518  lea     r8, aCallerP; "(caller: %p) "
0x18000651f  mov     rdx, rsi; unsigned __int16 *
0x180006522  mov     rcx, rax; this
0x180006525  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000652a  mov     r14, rax
0x18000652d  call    cs:__imp_GetCurrentThreadId
0x180006534  nop     dword ptr [rax+rax+00h]
0x180006539  lea     rcx, [rsp+278h+Buffer]
0x18000653e  mov     [rsp+278h+var_240], rcx
0x180006543  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006547  mov     [rsp+278h+nSize], eax
0x18000654b  mov     eax, [rbx+44h]
0x18000654e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006552  mov     r9, rdi; unsigned __int16 *
0x180006555  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000655c  mov     rdx, rsi; unsigned __int16 *
0x18000655f  mov     rcx, r14; this
0x180006562  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006567  cmp     [rbx+18h], r15
0x18000656b  jnz     short loc_18000657D
0x18000656d  cmp     [rbx+48h], r15
0x180006571  jnz     short loc_18000657D
0x180006573  cmp     [rbx+30h], r15
0x180006577  jz      loc_18000660D
0x18000657d  lea     r8, asc_18005D260; "    "
0x180006584  mov     rdx, rsi; unsigned __int16 *
0x180006587  mov     rcx, rax; this
0x18000658a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000658f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006593  test    r9, r9
0x180006596  jz      short loc_1800065AA
0x180006598  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000659f  mov     rdx, rsi; unsigned __int16 *
0x1800065a2  mov     rcx, rax; this
0x1800065a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800065aa  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800065ae  test    r9, r9
0x1800065b1  jz      short loc_1800065C5
0x1800065b3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800065ba  mov     rdx, rsi; unsigned __int16 *
0x1800065bd  mov     rcx, rax; this
0x1800065c0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800065c5  mov     rcx, [rbx+28h]
0x1800065c9  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800065cd  mov     rdx, rsi; unsigned __int16 *
0x1800065d0  test    rcx, rcx
0x1800065d3  jz      short loc_1800065EB
0x1800065d5  mov     [rsp+278h+lpBuffer], rcx
0x1800065da  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800065e1  mov     rcx, rax; this
0x1800065e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800065e9  jmp     short loc_18000660D
0x1800065eb  mov     rcx, rax; this
0x1800065ee  test    r9, r9
0x1800065f1  jz      short loc_180006601
0x1800065f3  lea     r8, aHs; "[%hs]\n"
0x1800065fa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800065ff  jmp     short loc_18000660D
0x180006601  lea     r8, asc_18005D2D8; "\n"
0x180006608  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000660d  xor     eax, eax
0x18000660f  mov     rcx, [rsp+278h+var_38]
0x180006617  xor     rcx, rsp; StackCookie
0x18000661a  call    __security_check_cookie
0x18000661f  mov     rbx, [rsp+278h+arg_18]
0x180006627  add     rsp, 250h
0x18000662e  pop     r15
0x180006630  pop     r14
0x180006632  pop     rdi
0x180006633  pop     rsi
0x180006634  pop     rbp
0x180006635  retn
```
