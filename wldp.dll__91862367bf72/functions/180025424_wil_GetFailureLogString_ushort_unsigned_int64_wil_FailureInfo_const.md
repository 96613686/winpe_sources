# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180025424`
- end: `0x1800256da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f578`
- `0x180025c8c`
- `0x1800269a0`

## callees

- `0x180021ec0`
- `0x180022a10`
- `0x180025424`
- `0x1800258f0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800255d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800255d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180025556`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180025556`

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
          v7 = (const char *)&byte_180048E15;
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
0x180025424  mov     [rsp+arg_18], rbx
0x180025429  push    rbp
0x18002542a  push    rsi
0x18002542b  push    rdi
0x18002542c  push    r14
0x18002542e  push    r15
0x180025430  sub     rsp, 250h
0x180025437  mov     rax, cs:__security_cookie
0x18002543e  xor     rax, rsp
0x180025441  mov     [rsp+278h+var_38], rax
0x180025449  mov     rbx, r8
0x18002544c  mov     rsi, rdx
0x18002544f  mov     r14, rcx
0x180025452  xor     r15d, r15d
0x180025455  test    rdx, rdx
0x180025458  jz      loc_1800256B1
0x18002545e  test    rcx, rcx
0x180025461  jz      loc_1800256B1
0x180025467  mov     [rcx], r15w
0x18002546b  mov     rax, cs:g_pfnResultLoggingCallback
0x180025472  test    rax, rax
0x180025475  jz      short loc_180025498
0x180025477  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002547e  jz      short loc_180025498
0x180025480  mov     r8, rdx
0x180025483  mov     rdx, rcx
0x180025486  mov     rcx, rbx
0x180025489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002548e  cmp     [r14], r15w
0x180025492  jnz     loc_1800256B1
0x180025498  mov     ecx, [rbx]
0x18002549a  mov     bpl, 8
0x18002549d  test    ecx, ecx
0x18002549f  jz      short loc_1800254EA
0x1800254a1  sub     ecx, 1
0x1800254a4  jz      short loc_1800254D2
0x1800254a6  sub     ecx, 1
0x1800254a9  jz      short loc_1800254C2
0x1800254ab  cmp     ecx, 1
0x1800254ae  jz      short loc_1800254B9
0x1800254b0  lea     rdi, byte_180048E15
0x1800254b7  jmp     short loc_1800254F1
0x1800254b9  lea     rdi, aFailfast; "FailFast"
0x1800254c0  jmp     short loc_1800254F1
0x1800254c2  lea     rax, aLoghr; "LogHr"
0x1800254c9  lea     rdi, aLognt; "LogNt"
0x1800254d0  jmp     short loc_1800254E0
0x1800254d2  lea     rax, aReturnhr; "ReturnHr"
0x1800254d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800254e0  test    [rbx+4], bpl
0x1800254e4  cmovz   rdi, rax
0x1800254e8  jmp     short loc_1800254F1
0x1800254ea  lea     rdi, aException; "Exception"
0x1800254f1  xor     edx, edx; Val
0x1800254f3  mov     r8d, 200h; Size
0x1800254f9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800254fe  call    memset_0
0x180025503  test    [rbx+4], bpl
0x180025507  jz      short loc_18002552C
0x180025509  mov     ebp, [rbx+0Ch]
0x18002550c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180025513  test    rax, rax
0x180025516  jz      short loc_18002555C
0x180025518  mov     r8d, 100h
0x18002551e  lea     rdx, [rsp+278h+Buffer]
0x180025523  mov     ecx, ebp
0x180025525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002552a  jmp     short loc_18002555C
0x18002552c  mov     ebp, [rbx+8]
0x18002552f  mov     [rsp+278h+Arguments], r15; Arguments
0x180025534  mov     [rsp+278h+nSize], 100h; nSize
0x18002553c  lea     rax, [rsp+278h+Buffer]
0x180025541  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180025546  mov     r9d, 400h; dwLanguageId
0x18002554c  mov     r8d, ebp; dwMessageId
0x18002554f  xor     edx, edx; lpSource
0x180025551  mov     ecx, 1200h; dwFlags
0x180025556  call    cs:__imp_FormatMessageW
0x18002555c  lea     rsi, [r14+rsi*2]
0x180025560  mov     r9, [rbx+38h]; unsigned __int16 *
0x180025564  mov     rax, [rbx+88h]
0x18002556b  mov     rcx, [rbx+80h]
0x180025572  mov     rdx, rsi; unsigned __int16 *
0x180025575  test    r9, r9
0x180025578  jz      short loc_18002559C
0x18002557a  mov     [rsp+278h+Arguments], rax
0x18002557f  mov     qword ptr [rsp+278h+nSize], rcx
0x180025584  mov     eax, [rbx+40h]
0x180025587  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002558b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180025592  mov     rcx, r14; this
0x180025595  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002559a  jmp     short loc_1800255B3
0x18002559c  mov     [rsp+278h+lpBuffer], rax
0x1800255a1  mov     r9, rcx; unsigned __int16 *
0x1800255a4  lea     r8, aHsP; "%hs!%p: "
0x1800255ab  mov     rcx, r14; this
0x1800255ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800255b3  mov     r14, rax
0x1800255b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800255bd  test    r9, r9
0x1800255c0  jz      short loc_1800255D7
0x1800255c2  lea     r8, aCallerP; "(caller: %p) "
0x1800255c9  mov     rdx, rsi; unsigned __int16 *
0x1800255cc  mov     rcx, rax; this
0x1800255cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800255d4  mov     r14, rax
0x1800255d7  call    cs:__imp_GetCurrentThreadId
0x1800255dd  lea     rcx, [rsp+278h+Buffer]
0x1800255e2  mov     [rsp+278h+var_240], rcx
0x1800255e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800255eb  mov     [rsp+278h+nSize], eax
0x1800255ef  mov     eax, [rbx+44h]
0x1800255f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800255f6  mov     r9, rdi; unsigned __int16 *
0x1800255f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180025600  mov     rdx, rsi; unsigned __int16 *
0x180025603  mov     rcx, r14; this
0x180025606  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002560b  cmp     [rbx+18h], r15
0x18002560f  jnz     short loc_180025621
0x180025611  cmp     [rbx+48h], r15
0x180025615  jnz     short loc_180025621
0x180025617  cmp     [rbx+30h], r15
0x18002561b  jz      loc_1800256B1
0x180025621  lea     r8, asc_180048F18; "    "
0x180025628  mov     rdx, rsi; unsigned __int16 *
0x18002562b  mov     rcx, rax; this
0x18002562e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025633  mov     r9, [rbx+18h]; unsigned __int16 *
0x180025637  test    r9, r9
0x18002563a  jz      short loc_18002564E
0x18002563c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180025643  mov     rdx, rsi; unsigned __int16 *
0x180025646  mov     rcx, rax; this
0x180025649  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002564e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180025652  test    r9, r9
0x180025655  jz      short loc_180025669
0x180025657  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002565e  mov     rdx, rsi; unsigned __int16 *
0x180025661  mov     rcx, rax; this
0x180025664  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025669  mov     rcx, [rbx+28h]
0x18002566d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180025671  mov     rdx, rsi; unsigned __int16 *
0x180025674  test    rcx, rcx
0x180025677  jz      short loc_18002568F
0x180025679  mov     [rsp+278h+lpBuffer], rcx
0x18002567e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180025685  mov     rcx, rax; this
0x180025688  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002568d  jmp     short loc_1800256B1
0x18002568f  mov     rcx, rax; this
0x180025692  test    r9, r9
0x180025695  jz      short loc_1800256A5
0x180025697  lea     r8, aHs; "[%hs]\n"
0x18002569e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800256a3  jmp     short loc_1800256B1
0x1800256a5  lea     r8, asc_180048F90; "\n"
0x1800256ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800256b1  xor     eax, eax
0x1800256b3  mov     rcx, [rsp+278h+var_38]
0x1800256bb  xor     rcx, rsp; StackCookie
0x1800256be  call    __security_check_cookie
0x1800256c3  mov     rbx, [rsp+278h+arg_18]
0x1800256cb  add     rsp, 250h
0x1800256d2  pop     r15
0x1800256d4  pop     r14
0x1800256d6  pop     rdi
0x1800256d7  pop     rsi
0x1800256d8  pop     rbp
0x1800256d9  retn
```
