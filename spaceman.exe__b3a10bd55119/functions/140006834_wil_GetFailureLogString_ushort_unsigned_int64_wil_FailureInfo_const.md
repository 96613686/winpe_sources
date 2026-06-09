# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140006834`
- end: `0x140006aea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400046f0`
- `0x140004958`
- `0x140007190`

## callees

- `0x140006834`
- `0x140007490`
- `0x14000d1be`
- `0x14000d1f0`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400069e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400069e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006966`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006966`

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
          v8 = (const char *)&word_14000F816;
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
0x140006834  mov     [rsp+arg_18], rbx
0x140006839  push    rbp
0x14000683a  push    rsi
0x14000683b  push    rdi
0x14000683c  push    r14
0x14000683e  push    r15
0x140006840  sub     rsp, 250h
0x140006847  mov     rax, cs:__security_cookie
0x14000684e  xor     rax, rsp
0x140006851  mov     [rsp+278h+var_38], rax
0x140006859  xor     r15d, r15d
0x14000685c  mov     rbx, r8
0x14000685f  mov     rsi, rdx
0x140006862  mov     r14, rcx
0x140006865  test    rdx, rdx
0x140006868  jz      loc_140006AC1
0x14000686e  test    rcx, rcx
0x140006871  jz      loc_140006AC1
0x140006877  mov     rax, cs:g_pfnResultLoggingCallback
0x14000687e  mov     [rcx], r15w
0x140006882  test    rax, rax
0x140006885  jz      short loc_1400068A8
0x140006887  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000688e  jz      short loc_1400068A8
0x140006890  mov     r8, rdx
0x140006893  mov     rdx, rcx
0x140006896  mov     rcx, rbx
0x140006899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000689e  cmp     [r14], r15w
0x1400068a2  jnz     loc_140006AC1
0x1400068a8  mov     ecx, [rbx]
0x1400068aa  mov     bpl, 8
0x1400068ad  test    ecx, ecx
0x1400068af  jz      short loc_1400068FA
0x1400068b1  sub     ecx, 1
0x1400068b4  jz      short loc_1400068E2
0x1400068b6  sub     ecx, 1
0x1400068b9  jz      short loc_1400068D2
0x1400068bb  cmp     ecx, 1
0x1400068be  jz      short loc_1400068C9
0x1400068c0  lea     rdi, word_14000F816
0x1400068c7  jmp     short loc_140006901
0x1400068c9  lea     rdi, aFailfast; "FailFast"
0x1400068d0  jmp     short loc_140006901
0x1400068d2  lea     rax, aLoghr; "LogHr"
0x1400068d9  lea     rdi, aLognt; "LogNt"
0x1400068e0  jmp     short loc_1400068F0
0x1400068e2  lea     rax, aReturnhr; "ReturnHr"
0x1400068e9  lea     rdi, aReturnnt; "ReturnNt"
0x1400068f0  test    [rbx+4], bpl
0x1400068f4  cmovz   rdi, rax
0x1400068f8  jmp     short loc_140006901
0x1400068fa  lea     rdi, aException; "Exception"
0x140006901  xor     edx, edx; Val
0x140006903  lea     rcx, [rsp+278h+Buffer]; void *
0x140006908  mov     r8d, 200h; Size
0x14000690e  call    memset_0
0x140006913  test    [rbx+4], bpl
0x140006917  jz      short loc_14000693C
0x140006919  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140006920  mov     ebp, [rbx+0Ch]
0x140006923  test    rax, rax
0x140006926  jz      short loc_14000696C
0x140006928  mov     r8d, 100h
0x14000692e  lea     rdx, [rsp+278h+Buffer]
0x140006933  mov     ecx, ebp
0x140006935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000693a  jmp     short loc_14000696C
0x14000693c  mov     ebp, [rbx+8]
0x14000693f  lea     rax, [rsp+278h+Buffer]
0x140006944  mov     [rsp+278h+Arguments], r15; Arguments
0x140006949  mov     r8d, ebp; dwMessageId
0x14000694c  mov     [rsp+278h+nSize], 100h; nSize
0x140006954  mov     r9d, 400h; dwLanguageId
0x14000695a  xor     edx, edx; lpSource
0x14000695c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140006961  mov     ecx, 1200h; dwFlags
0x140006966  call    cs:__imp_FormatMessageW
0x14000696c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140006970  lea     rsi, [r14+rsi*2]
0x140006974  mov     rax, [rbx+88h]
0x14000697b  mov     rdx, rsi; unsigned __int16 *
0x14000697e  mov     rcx, [rbx+80h]
0x140006985  test    r9, r9
0x140006988  jz      short loc_1400069AC
0x14000698a  mov     [rsp+278h+Arguments], rax
0x14000698f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140006996  mov     eax, [rbx+40h]
0x140006999  mov     qword ptr [rsp+278h+nSize], rcx
0x14000699e  mov     rcx, r14; this
0x1400069a1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400069a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400069aa  jmp     short loc_1400069C3
0x1400069ac  mov     r9, rcx; unsigned __int16 *
0x1400069af  mov     [rsp+278h+lpBuffer], rax
0x1400069b4  mov     rcx, r14; this
0x1400069b7  lea     r8, aHsP; "%hs!%p: "
0x1400069be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400069c3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400069ca  mov     r14, rax
0x1400069cd  test    r9, r9
0x1400069d0  jz      short loc_1400069E7
0x1400069d2  lea     r8, aCallerP; "(caller: %p) "
0x1400069d9  mov     rdx, rsi; unsigned __int16 *
0x1400069dc  mov     rcx, rax; this
0x1400069df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400069e4  mov     r14, rax
0x1400069e7  call    cs:__imp_GetCurrentThreadId
0x1400069ed  lea     rcx, [rsp+278h+Buffer]
0x1400069f2  mov     r9, rdi; unsigned __int16 *
0x1400069f5  mov     [rsp+278h+var_240], rcx
0x1400069fa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140006a01  mov     dword ptr [rsp+278h+Arguments], ebp
0x140006a05  mov     rdx, rsi; unsigned __int16 *
0x140006a08  mov     [rsp+278h+nSize], eax
0x140006a0c  mov     rcx, r14; this
0x140006a0f  mov     eax, [rbx+44h]
0x140006a12  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006a16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006a1b  cmp     [rbx+18h], r15
0x140006a1f  jnz     short loc_140006A31
0x140006a21  cmp     [rbx+48h], r15
0x140006a25  jnz     short loc_140006A31
0x140006a27  cmp     [rbx+30h], r15
0x140006a2b  jz      loc_140006AC1
0x140006a31  lea     r8, asc_14000FBE8; "    "
0x140006a38  mov     rdx, rsi; unsigned __int16 *
0x140006a3b  mov     rcx, rax; this
0x140006a3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006a43  mov     r9, [rbx+18h]; unsigned __int16 *
0x140006a47  test    r9, r9
0x140006a4a  jz      short loc_140006A5E
0x140006a4c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140006a53  mov     rdx, rsi; unsigned __int16 *
0x140006a56  mov     rcx, rax; this
0x140006a59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006a5e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140006a62  test    r9, r9
0x140006a65  jz      short loc_140006A79
0x140006a67  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140006a6e  mov     rdx, rsi; unsigned __int16 *
0x140006a71  mov     rcx, rax; this
0x140006a74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006a79  mov     rcx, [rbx+28h]
0x140006a7d  mov     rdx, rsi; unsigned __int16 *
0x140006a80  mov     r9, [rbx+30h]; unsigned __int16 *
0x140006a84  test    rcx, rcx
0x140006a87  jz      short loc_140006A9F
0x140006a89  mov     [rsp+278h+lpBuffer], rcx
0x140006a8e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140006a95  mov     rcx, rax; this
0x140006a98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006a9d  jmp     short loc_140006AC1
0x140006a9f  mov     rcx, rax; this
0x140006aa2  test    r9, r9
0x140006aa5  jz      short loc_140006AB5
0x140006aa7  lea     r8, aHs; "[%hs]\n"
0x140006aae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006ab3  jmp     short loc_140006AC1
0x140006ab5  lea     r8, asc_14000FC60; "\n"
0x140006abc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006ac1  xor     eax, eax
0x140006ac3  mov     rcx, [rsp+278h+var_38]
0x140006acb  xor     rcx, rsp; StackCookie
0x140006ace  call    __security_check_cookie
0x140006ad3  mov     rbx, [rsp+278h+arg_18]
0x140006adb  add     rsp, 250h
0x140006ae2  pop     r15
0x140006ae4  pop     r14
0x140006ae6  pop     rdi
0x140006ae7  pop     rsi
0x140006ae8  pop     rbp
0x140006ae9  retn
```
