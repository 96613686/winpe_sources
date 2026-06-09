# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800067d4`
- end: `0x180006a8a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004bb8`
- `0x180007480`
- `0x1800097a0`

## callees

- `0x1800027f0`
- `0x1800033b4`
- `0x1800067d4`
- `0x180007780`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006906`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006987`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006987`

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
          v7 = (const char *)&word_180017D52;
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
0x1800067d4  mov     [rsp+arg_18], rbx
0x1800067d9  push    rbp
0x1800067da  push    rsi
0x1800067db  push    rdi
0x1800067dc  push    r14
0x1800067de  push    r15
0x1800067e0  sub     rsp, 250h
0x1800067e7  mov     rax, cs:__security_cookie
0x1800067ee  xor     rax, rsp
0x1800067f1  mov     [rsp+278h+var_38], rax
0x1800067f9  mov     rbx, r8
0x1800067fc  mov     rsi, rdx
0x1800067ff  mov     r14, rcx
0x180006802  xor     r15d, r15d
0x180006805  test    rdx, rdx
0x180006808  jz      loc_180006A61
0x18000680e  test    rcx, rcx
0x180006811  jz      loc_180006A61
0x180006817  mov     [rcx], r15w
0x18000681b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006822  test    rax, rax
0x180006825  jz      short loc_180006848
0x180006827  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000682e  jz      short loc_180006848
0x180006830  mov     r8, rdx
0x180006833  mov     rdx, rcx
0x180006836  mov     rcx, rbx
0x180006839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000683e  cmp     [r14], r15w
0x180006842  jnz     loc_180006A61
0x180006848  mov     ecx, [rbx]
0x18000684a  mov     bpl, 8
0x18000684d  test    ecx, ecx
0x18000684f  jz      short loc_18000689A
0x180006851  sub     ecx, 1
0x180006854  jz      short loc_180006882
0x180006856  sub     ecx, 1
0x180006859  jz      short loc_180006872
0x18000685b  cmp     ecx, 1
0x18000685e  jz      short loc_180006869
0x180006860  lea     rdi, word_180017D52
0x180006867  jmp     short loc_1800068A1
0x180006869  lea     rdi, aFailfast; "FailFast"
0x180006870  jmp     short loc_1800068A1
0x180006872  lea     rax, aLoghr; "LogHr"
0x180006879  lea     rdi, aLognt; "LogNt"
0x180006880  jmp     short loc_180006890
0x180006882  lea     rax, aReturnhr; "ReturnHr"
0x180006889  lea     rdi, aReturnnt; "ReturnNt"
0x180006890  test    [rbx+4], bpl
0x180006894  cmovz   rdi, rax
0x180006898  jmp     short loc_1800068A1
0x18000689a  lea     rdi, aException; "Exception"
0x1800068a1  xor     edx, edx; Val
0x1800068a3  mov     r8d, 200h; Size
0x1800068a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800068ae  call    memset_0
0x1800068b3  test    [rbx+4], bpl
0x1800068b7  jz      short loc_1800068DC
0x1800068b9  mov     ebp, [rbx+0Ch]
0x1800068bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800068c3  test    rax, rax
0x1800068c6  jz      short loc_18000690C
0x1800068c8  mov     r8d, 100h
0x1800068ce  lea     rdx, [rsp+278h+Buffer]
0x1800068d3  mov     ecx, ebp
0x1800068d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068da  jmp     short loc_18000690C
0x1800068dc  mov     ebp, [rbx+8]
0x1800068df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800068e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800068ec  lea     rax, [rsp+278h+Buffer]
0x1800068f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800068f6  mov     r9d, 400h; dwLanguageId
0x1800068fc  mov     r8d, ebp; dwMessageId
0x1800068ff  xor     edx, edx; lpSource
0x180006901  mov     ecx, 1200h; dwFlags
0x180006906  call    cs:__imp_FormatMessageW
0x18000690c  lea     rsi, [r14+rsi*2]
0x180006910  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006914  mov     rax, [rbx+88h]
0x18000691b  mov     rcx, [rbx+80h]
0x180006922  mov     rdx, rsi; unsigned __int16 *
0x180006925  test    r9, r9
0x180006928  jz      short loc_18000694C
0x18000692a  mov     [rsp+278h+Arguments], rax
0x18000692f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006934  mov     eax, [rbx+40h]
0x180006937  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000693b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006942  mov     rcx, r14; this
0x180006945  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000694a  jmp     short loc_180006963
0x18000694c  mov     [rsp+278h+lpBuffer], rax
0x180006951  mov     r9, rcx; unsigned __int16 *
0x180006954  lea     r8, aHsP; "%hs!%p: "
0x18000695b  mov     rcx, r14; this
0x18000695e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006963  mov     r14, rax
0x180006966  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000696d  test    r9, r9
0x180006970  jz      short loc_180006987
0x180006972  lea     r8, aCallerP; "(caller: %p) "
0x180006979  mov     rdx, rsi; unsigned __int16 *
0x18000697c  mov     rcx, rax; this
0x18000697f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006984  mov     r14, rax
0x180006987  call    cs:__imp_GetCurrentThreadId
0x18000698d  lea     rcx, [rsp+278h+Buffer]
0x180006992  mov     [rsp+278h+var_240], rcx
0x180006997  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000699b  mov     [rsp+278h+nSize], eax
0x18000699f  mov     eax, [rbx+44h]
0x1800069a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800069a6  mov     r9, rdi; unsigned __int16 *
0x1800069a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800069b0  mov     rdx, rsi; unsigned __int16 *
0x1800069b3  mov     rcx, r14; this
0x1800069b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800069bb  cmp     [rbx+18h], r15
0x1800069bf  jnz     short loc_1800069D1
0x1800069c1  cmp     [rbx+48h], r15
0x1800069c5  jnz     short loc_1800069D1
0x1800069c7  cmp     [rbx+30h], r15
0x1800069cb  jz      loc_180006A61
0x1800069d1  lea     r8, asc_180017E40; "    "
0x1800069d8  mov     rdx, rsi; unsigned __int16 *
0x1800069db  mov     rcx, rax; this
0x1800069de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800069e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800069e7  test    r9, r9
0x1800069ea  jz      short loc_1800069FE
0x1800069ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800069f3  mov     rdx, rsi; unsigned __int16 *
0x1800069f6  mov     rcx, rax; this
0x1800069f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800069fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006a02  test    r9, r9
0x180006a05  jz      short loc_180006A19
0x180006a07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006a0e  mov     rdx, rsi; unsigned __int16 *
0x180006a11  mov     rcx, rax; this
0x180006a14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a19  mov     rcx, [rbx+28h]
0x180006a1d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006a21  mov     rdx, rsi; unsigned __int16 *
0x180006a24  test    rcx, rcx
0x180006a27  jz      short loc_180006A3F
0x180006a29  mov     [rsp+278h+lpBuffer], rcx
0x180006a2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006a35  mov     rcx, rax; this
0x180006a38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a3d  jmp     short loc_180006A61
0x180006a3f  mov     rcx, rax; this
0x180006a42  test    r9, r9
0x180006a45  jz      short loc_180006A55
0x180006a47  lea     r8, aHs; "[%hs]\n"
0x180006a4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a53  jmp     short loc_180006A61
0x180006a55  lea     r8, asc_180017EB8; "\n"
0x180006a5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a61  xor     eax, eax
0x180006a63  mov     rcx, [rsp+278h+var_38]
0x180006a6b  xor     rcx, rsp; StackCookie
0x180006a6e  call    __security_check_cookie
0x180006a73  mov     rbx, [rsp+278h+arg_18]
0x180006a7b  add     rsp, 250h
0x180006a82  pop     r15
0x180006a84  pop     r14
0x180006a86  pop     rdi
0x180006a87  pop     rsi
0x180006a88  pop     rbp
0x180006a89  retn
```
