# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000bf54`
- end: `0x18000c20a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c6a0`
- `0x18000daa0`

## callees

- `0x180008e18`
- `0x1800097d0`
- `0x18000a192`
- `0x18000bf54`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c107`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c086`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c086`

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
          v7 = (const char *)&byte_1800183AD;
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
0x18000bf54  mov     [rsp+arg_18], rbx
0x18000bf59  push    rbp
0x18000bf5a  push    rsi
0x18000bf5b  push    rdi
0x18000bf5c  push    r14
0x18000bf5e  push    r15
0x18000bf60  sub     rsp, 250h
0x18000bf67  mov     rax, cs:__security_cookie
0x18000bf6e  xor     rax, rsp
0x18000bf71  mov     [rsp+278h+var_38], rax
0x18000bf79  mov     rbx, r8
0x18000bf7c  mov     rsi, rdx
0x18000bf7f  mov     r14, rcx
0x18000bf82  xor     r15d, r15d
0x18000bf85  test    rdx, rdx
0x18000bf88  jz      loc_18000C1E1
0x18000bf8e  test    rcx, rcx
0x18000bf91  jz      loc_18000C1E1
0x18000bf97  mov     [rcx], r15w
0x18000bf9b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bfa2  test    rax, rax
0x18000bfa5  jz      short loc_18000BFC8
0x18000bfa7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000bfae  jz      short loc_18000BFC8
0x18000bfb0  mov     r8, rdx
0x18000bfb3  mov     rdx, rcx
0x18000bfb6  mov     rcx, rbx
0x18000bfb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfbe  cmp     [r14], r15w
0x18000bfc2  jnz     loc_18000C1E1
0x18000bfc8  mov     ecx, [rbx]
0x18000bfca  mov     bpl, 8
0x18000bfcd  test    ecx, ecx
0x18000bfcf  jz      short loc_18000C01A
0x18000bfd1  sub     ecx, 1
0x18000bfd4  jz      short loc_18000C002
0x18000bfd6  sub     ecx, 1
0x18000bfd9  jz      short loc_18000BFF2
0x18000bfdb  cmp     ecx, 1
0x18000bfde  jz      short loc_18000BFE9
0x18000bfe0  lea     rdi, byte_1800183AD
0x18000bfe7  jmp     short loc_18000C021
0x18000bfe9  lea     rdi, aFailfast; "FailFast"
0x18000bff0  jmp     short loc_18000C021
0x18000bff2  lea     rax, aLoghr; "LogHr"
0x18000bff9  lea     rdi, aLognt; "LogNt"
0x18000c000  jmp     short loc_18000C010
0x18000c002  lea     rax, aReturnhr; "ReturnHr"
0x18000c009  lea     rdi, aReturnnt; "ReturnNt"
0x18000c010  test    [rbx+4], bpl
0x18000c014  cmovz   rdi, rax
0x18000c018  jmp     short loc_18000C021
0x18000c01a  lea     rdi, aException; "Exception"
0x18000c021  xor     edx, edx; Val
0x18000c023  mov     r8d, 200h; Size
0x18000c029  lea     rcx, [rsp+278h+Buffer]; void *
0x18000c02e  call    memset_0
0x18000c033  test    [rbx+4], bpl
0x18000c037  jz      short loc_18000C05C
0x18000c039  mov     ebp, [rbx+0Ch]
0x18000c03c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000c043  test    rax, rax
0x18000c046  jz      short loc_18000C08C
0x18000c048  mov     r8d, 100h
0x18000c04e  lea     rdx, [rsp+278h+Buffer]
0x18000c053  mov     ecx, ebp
0x18000c055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c05a  jmp     short loc_18000C08C
0x18000c05c  mov     ebp, [rbx+8]
0x18000c05f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000c064  mov     [rsp+278h+nSize], 100h; nSize
0x18000c06c  lea     rax, [rsp+278h+Buffer]
0x18000c071  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000c076  mov     r9d, 400h; dwLanguageId
0x18000c07c  mov     r8d, ebp; dwMessageId
0x18000c07f  xor     edx, edx; lpSource
0x18000c081  mov     ecx, 1200h; dwFlags
0x18000c086  call    cs:__imp_FormatMessageW
0x18000c08c  lea     rsi, [r14+rsi*2]
0x18000c090  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000c094  mov     rax, [rbx+88h]
0x18000c09b  mov     rcx, [rbx+80h]
0x18000c0a2  mov     rdx, rsi; unsigned __int16 *
0x18000c0a5  test    r9, r9
0x18000c0a8  jz      short loc_18000C0CC
0x18000c0aa  mov     [rsp+278h+Arguments], rax
0x18000c0af  mov     qword ptr [rsp+278h+nSize], rcx
0x18000c0b4  mov     eax, [rbx+40h]
0x18000c0b7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000c0bb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000c0c2  mov     rcx, r14; this
0x18000c0c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c0ca  jmp     short loc_18000C0E3
0x18000c0cc  mov     [rsp+278h+lpBuffer], rax
0x18000c0d1  mov     r9, rcx; unsigned __int16 *
0x18000c0d4  lea     r8, aHsP; "%hs!%p: "
0x18000c0db  mov     rcx, r14; this
0x18000c0de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c0e3  mov     r14, rax
0x18000c0e6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000c0ed  test    r9, r9
0x18000c0f0  jz      short loc_18000C107
0x18000c0f2  lea     r8, aCallerP; "(caller: %p) "
0x18000c0f9  mov     rdx, rsi; unsigned __int16 *
0x18000c0fc  mov     rcx, rax; this
0x18000c0ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c104  mov     r14, rax
0x18000c107  call    cs:__imp_GetCurrentThreadId
0x18000c10d  lea     rcx, [rsp+278h+Buffer]
0x18000c112  mov     [rsp+278h+var_240], rcx
0x18000c117  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000c11b  mov     [rsp+278h+nSize], eax
0x18000c11f  mov     eax, [rbx+44h]
0x18000c122  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000c126  mov     r9, rdi; unsigned __int16 *
0x18000c129  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000c130  mov     rdx, rsi; unsigned __int16 *
0x18000c133  mov     rcx, r14; this
0x18000c136  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c13b  cmp     [rbx+18h], r15
0x18000c13f  jnz     short loc_18000C151
0x18000c141  cmp     [rbx+48h], r15
0x18000c145  jnz     short loc_18000C151
0x18000c147  cmp     [rbx+30h], r15
0x18000c14b  jz      loc_18000C1E1
0x18000c151  lea     r8, asc_1800184B0; "    "
0x18000c158  mov     rdx, rsi; unsigned __int16 *
0x18000c15b  mov     rcx, rax; this
0x18000c15e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c163  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000c167  test    r9, r9
0x18000c16a  jz      short loc_18000C17E
0x18000c16c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000c173  mov     rdx, rsi; unsigned __int16 *
0x18000c176  mov     rcx, rax; this
0x18000c179  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c17e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000c182  test    r9, r9
0x18000c185  jz      short loc_18000C199
0x18000c187  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000c18e  mov     rdx, rsi; unsigned __int16 *
0x18000c191  mov     rcx, rax; this
0x18000c194  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c199  mov     rcx, [rbx+28h]
0x18000c19d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000c1a1  mov     rdx, rsi; unsigned __int16 *
0x18000c1a4  test    rcx, rcx
0x18000c1a7  jz      short loc_18000C1BF
0x18000c1a9  mov     [rsp+278h+lpBuffer], rcx
0x18000c1ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000c1b5  mov     rcx, rax; this
0x18000c1b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c1bd  jmp     short loc_18000C1E1
0x18000c1bf  mov     rcx, rax; this
0x18000c1c2  test    r9, r9
0x18000c1c5  jz      short loc_18000C1D5
0x18000c1c7  lea     r8, aHs; "[%hs]\n"
0x18000c1ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c1d3  jmp     short loc_18000C1E1
0x18000c1d5  lea     r8, asc_180018528; "\n"
0x18000c1dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c1e1  xor     eax, eax
0x18000c1e3  mov     rcx, [rsp+278h+var_38]
0x18000c1eb  xor     rcx, rsp; StackCookie
0x18000c1ee  call    __security_check_cookie
0x18000c1f3  mov     rbx, [rsp+278h+arg_18]
0x18000c1fb  add     rsp, 250h
0x18000c202  pop     r15
0x18000c204  pop     r14
0x18000c206  pop     rdi
0x18000c207  pop     rsi
0x18000c208  pop     rbp
0x18000c209  retn
```
