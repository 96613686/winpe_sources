# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005414`
- end: `0x1800056ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180004704`
- `0x180004984`
- `0x180004c30`
- `0x180006700`
- `0x1800268a4`
- `0x1800269d8`
- `0x180026b41`
- `0x180026e11`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x180005414`
- `0x180005894`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005546`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005546`

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
          v7 = (const char *)&byte_18002B291;
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
0x180005414  mov     [rsp+arg_18], rbx
0x180005419  push    rbp
0x18000541a  push    rsi
0x18000541b  push    rdi
0x18000541c  push    r14
0x18000541e  push    r15
0x180005420  sub     rsp, 250h
0x180005427  mov     rax, cs:__security_cookie
0x18000542e  xor     rax, rsp
0x180005431  mov     [rsp+278h+var_38], rax
0x180005439  mov     rbx, r8
0x18000543c  mov     rsi, rdx
0x18000543f  mov     r14, rcx
0x180005442  xor     r15d, r15d
0x180005445  test    rdx, rdx
0x180005448  jz      loc_1800056A1
0x18000544e  test    rcx, rcx
0x180005451  jz      loc_1800056A1
0x180005457  mov     [rcx], r15w
0x18000545b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005462  test    rax, rax
0x180005465  jz      short loc_180005488
0x180005467  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000546e  jz      short loc_180005488
0x180005470  mov     r8, rdx
0x180005473  mov     rdx, rcx
0x180005476  mov     rcx, rbx
0x180005479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547e  cmp     [r14], r15w
0x180005482  jnz     loc_1800056A1
0x180005488  mov     ecx, [rbx]
0x18000548a  mov     bpl, 8
0x18000548d  test    ecx, ecx
0x18000548f  jz      short loc_1800054DA
0x180005491  sub     ecx, 1
0x180005494  jz      short loc_1800054C2
0x180005496  sub     ecx, 1
0x180005499  jz      short loc_1800054B2
0x18000549b  cmp     ecx, 1
0x18000549e  jz      short loc_1800054A9
0x1800054a0  lea     rdi, byte_18002B291
0x1800054a7  jmp     short loc_1800054E1
0x1800054a9  lea     rdi, aFailfast; "FailFast"
0x1800054b0  jmp     short loc_1800054E1
0x1800054b2  lea     rax, aLoghr; "LogHr"
0x1800054b9  lea     rdi, aLognt; "LogNt"
0x1800054c0  jmp     short loc_1800054D0
0x1800054c2  lea     rax, aReturnhr; "ReturnHr"
0x1800054c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800054d0  test    [rbx+4], bpl
0x1800054d4  cmovz   rdi, rax
0x1800054d8  jmp     short loc_1800054E1
0x1800054da  lea     rdi, aException; "Exception"
0x1800054e1  xor     edx, edx; Val
0x1800054e3  mov     r8d, 200h; Size
0x1800054e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800054ee  call    memset_0
0x1800054f3  test    [rbx+4], bpl
0x1800054f7  jz      short loc_18000551C
0x1800054f9  mov     ebp, [rbx+0Ch]
0x1800054fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005503  test    rax, rax
0x180005506  jz      short loc_18000554C
0x180005508  mov     r8d, 100h
0x18000550e  lea     rdx, [rsp+278h+Buffer]
0x180005513  mov     ecx, ebp
0x180005515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551a  jmp     short loc_18000554C
0x18000551c  mov     ebp, [rbx+8]
0x18000551f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005524  mov     [rsp+278h+nSize], 100h; nSize
0x18000552c  lea     rax, [rsp+278h+Buffer]
0x180005531  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005536  mov     r9d, 400h; dwLanguageId
0x18000553c  mov     r8d, ebp; dwMessageId
0x18000553f  xor     edx, edx; lpSource
0x180005541  mov     ecx, 1200h; dwFlags
0x180005546  call    cs:__imp_FormatMessageW
0x18000554c  lea     rsi, [r14+rsi*2]
0x180005550  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005554  mov     rax, [rbx+88h]
0x18000555b  mov     rcx, [rbx+80h]
0x180005562  mov     rdx, rsi; unsigned __int16 *
0x180005565  test    r9, r9
0x180005568  jz      short loc_18000558C
0x18000556a  mov     [rsp+278h+Arguments], rax
0x18000556f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005574  mov     eax, [rbx+40h]
0x180005577  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000557b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005582  mov     rcx, r14; this
0x180005585  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000558a  jmp     short loc_1800055A3
0x18000558c  mov     [rsp+278h+lpBuffer], rax
0x180005591  mov     r9, rcx; unsigned __int16 *
0x180005594  lea     r8, aHsP; "%hs!%p: "
0x18000559b  mov     rcx, r14; this
0x18000559e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055a3  mov     r14, rax
0x1800055a6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800055ad  test    r9, r9
0x1800055b0  jz      short loc_1800055C7
0x1800055b2  lea     r8, aCallerP; "(caller: %p) "
0x1800055b9  mov     rdx, rsi; unsigned __int16 *
0x1800055bc  mov     rcx, rax; this
0x1800055bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055c4  mov     r14, rax
0x1800055c7  call    cs:__imp_GetCurrentThreadId
0x1800055cd  lea     rcx, [rsp+278h+Buffer]
0x1800055d2  mov     [rsp+278h+var_240], rcx
0x1800055d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800055db  mov     [rsp+278h+nSize], eax
0x1800055df  mov     eax, [rbx+44h]
0x1800055e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800055e6  mov     r9, rdi; unsigned __int16 *
0x1800055e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800055f0  mov     rdx, rsi; unsigned __int16 *
0x1800055f3  mov     rcx, r14; this
0x1800055f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055fb  cmp     [rbx+18h], r15
0x1800055ff  jnz     short loc_180005611
0x180005601  cmp     [rbx+48h], r15
0x180005605  jnz     short loc_180005611
0x180005607  cmp     [rbx+30h], r15
0x18000560b  jz      loc_1800056A1
0x180005611  lea     r8, asc_18002B3A8; "    "
0x180005618  mov     rdx, rsi; unsigned __int16 *
0x18000561b  mov     rcx, rax; this
0x18000561e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005623  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005627  test    r9, r9
0x18000562a  jz      short loc_18000563E
0x18000562c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005633  mov     rdx, rsi; unsigned __int16 *
0x180005636  mov     rcx, rax; this
0x180005639  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000563e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005642  test    r9, r9
0x180005645  jz      short loc_180005659
0x180005647  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000564e  mov     rdx, rsi; unsigned __int16 *
0x180005651  mov     rcx, rax; this
0x180005654  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005659  mov     rcx, [rbx+28h]
0x18000565d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005661  mov     rdx, rsi; unsigned __int16 *
0x180005664  test    rcx, rcx
0x180005667  jz      short loc_18000567F
0x180005669  mov     [rsp+278h+lpBuffer], rcx
0x18000566e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005675  mov     rcx, rax; this
0x180005678  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000567d  jmp     short loc_1800056A1
0x18000567f  mov     rcx, rax; this
0x180005682  test    r9, r9
0x180005685  jz      short loc_180005695
0x180005687  lea     r8, aHs; "[%hs]\n"
0x18000568e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005693  jmp     short loc_1800056A1
0x180005695  lea     r8, asc_18002B420; "\n"
0x18000569c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056a1  xor     eax, eax
0x1800056a3  mov     rcx, [rsp+278h+var_38]
0x1800056ab  xor     rcx, rsp; StackCookie
0x1800056ae  call    __security_check_cookie
0x1800056b3  mov     rbx, [rsp+278h+arg_18]
0x1800056bb  add     rsp, 250h
0x1800056c2  pop     r15
0x1800056c4  pop     r14
0x1800056c6  pop     rdi
0x1800056c7  pop     rsi
0x1800056c8  pop     rbp
0x1800056c9  retn
```
