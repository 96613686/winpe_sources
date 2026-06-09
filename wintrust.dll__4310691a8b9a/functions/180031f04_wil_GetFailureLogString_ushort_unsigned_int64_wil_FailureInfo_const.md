# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180031f04`
- end: `0x1800321ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800328e0`
- `0x180032dbc`
- `0x180033fb8`

## callees

- `0x180031f04`
- `0x1800322a8`
- `0x18004de6a`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800320b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800320b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180032036`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180032036`

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
          v7 = (const char *)&byte_180057695;
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
0x180031f04  mov     [rsp+arg_18], rbx
0x180031f09  push    rbp
0x180031f0a  push    rsi
0x180031f0b  push    rdi
0x180031f0c  push    r14
0x180031f0e  push    r15
0x180031f10  sub     rsp, 250h
0x180031f17  mov     rax, cs:__security_cookie
0x180031f1e  xor     rax, rsp
0x180031f21  mov     [rsp+278h+var_38], rax
0x180031f29  mov     rbx, r8
0x180031f2c  mov     rsi, rdx
0x180031f2f  mov     r14, rcx
0x180031f32  xor     r15d, r15d
0x180031f35  test    rdx, rdx
0x180031f38  jz      loc_180032191
0x180031f3e  test    rcx, rcx
0x180031f41  jz      loc_180032191
0x180031f47  mov     [rcx], r15w
0x180031f4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180031f52  test    rax, rax
0x180031f55  jz      short loc_180031F78
0x180031f57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180031f5e  jz      short loc_180031F78
0x180031f60  mov     r8, rdx
0x180031f63  mov     rdx, rcx
0x180031f66  mov     rcx, rbx
0x180031f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f6e  cmp     [r14], r15w
0x180031f72  jnz     loc_180032191
0x180031f78  mov     ecx, [rbx]
0x180031f7a  mov     bpl, 8
0x180031f7d  test    ecx, ecx
0x180031f7f  jz      short loc_180031FCA
0x180031f81  sub     ecx, 1
0x180031f84  jz      short loc_180031FB2
0x180031f86  sub     ecx, 1
0x180031f89  jz      short loc_180031FA2
0x180031f8b  cmp     ecx, 1
0x180031f8e  jz      short loc_180031F99
0x180031f90  lea     rdi, byte_180057695
0x180031f97  jmp     short loc_180031FD1
0x180031f99  lea     rdi, aFailfast; "FailFast"
0x180031fa0  jmp     short loc_180031FD1
0x180031fa2  lea     rax, aLoghr; "LogHr"
0x180031fa9  lea     rdi, aLognt; "LogNt"
0x180031fb0  jmp     short loc_180031FC0
0x180031fb2  lea     rax, aReturnhr; "ReturnHr"
0x180031fb9  lea     rdi, aReturnnt; "ReturnNt"
0x180031fc0  test    [rbx+4], bpl
0x180031fc4  cmovz   rdi, rax
0x180031fc8  jmp     short loc_180031FD1
0x180031fca  lea     rdi, aException; "Exception"
0x180031fd1  xor     edx, edx; Val
0x180031fd3  mov     r8d, 200h; Size
0x180031fd9  lea     rcx, [rsp+278h+Buffer]; void *
0x180031fde  call    memset_0
0x180031fe3  test    [rbx+4], bpl
0x180031fe7  jz      short loc_18003200C
0x180031fe9  mov     ebp, [rbx+0Ch]
0x180031fec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180031ff3  test    rax, rax
0x180031ff6  jz      short loc_18003203C
0x180031ff8  mov     r8d, 100h
0x180031ffe  lea     rdx, [rsp+278h+Buffer]
0x180032003  mov     ecx, ebp
0x180032005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003200a  jmp     short loc_18003203C
0x18003200c  mov     ebp, [rbx+8]
0x18003200f  mov     [rsp+278h+Arguments], r15; Arguments
0x180032014  mov     [rsp+278h+nSize], 100h; nSize
0x18003201c  lea     rax, [rsp+278h+Buffer]
0x180032021  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180032026  mov     r9d, 400h; dwLanguageId
0x18003202c  mov     r8d, ebp; dwMessageId
0x18003202f  xor     edx, edx; lpSource
0x180032031  mov     ecx, 1200h; dwFlags
0x180032036  call    cs:__imp_FormatMessageW
0x18003203c  lea     rsi, [r14+rsi*2]
0x180032040  mov     r9, [rbx+38h]; unsigned __int16 *
0x180032044  mov     rax, [rbx+88h]
0x18003204b  mov     rcx, [rbx+80h]
0x180032052  mov     rdx, rsi; unsigned __int16 *
0x180032055  test    r9, r9
0x180032058  jz      short loc_18003207C
0x18003205a  mov     [rsp+278h+Arguments], rax
0x18003205f  mov     qword ptr [rsp+278h+nSize], rcx
0x180032064  mov     eax, [rbx+40h]
0x180032067  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003206b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180032072  mov     rcx, r14; this
0x180032075  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003207a  jmp     short loc_180032093
0x18003207c  mov     [rsp+278h+lpBuffer], rax
0x180032081  mov     r9, rcx; unsigned __int16 *
0x180032084  lea     r8, aHsP; "%hs!%p: "
0x18003208b  mov     rcx, r14; this
0x18003208e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180032093  mov     r14, rax
0x180032096  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003209d  test    r9, r9
0x1800320a0  jz      short loc_1800320B7
0x1800320a2  lea     r8, aCallerP; "(caller: %p) "
0x1800320a9  mov     rdx, rsi; unsigned __int16 *
0x1800320ac  mov     rcx, rax; this
0x1800320af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800320b4  mov     r14, rax
0x1800320b7  call    cs:__imp_GetCurrentThreadId
0x1800320bd  lea     rcx, [rsp+278h+Buffer]
0x1800320c2  mov     [rsp+278h+var_240], rcx
0x1800320c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800320cb  mov     [rsp+278h+nSize], eax
0x1800320cf  mov     eax, [rbx+44h]
0x1800320d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800320d6  mov     r9, rdi; unsigned __int16 *
0x1800320d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800320e0  mov     rdx, rsi; unsigned __int16 *
0x1800320e3  mov     rcx, r14; this
0x1800320e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800320eb  cmp     [rbx+18h], r15
0x1800320ef  jnz     short loc_180032101
0x1800320f1  cmp     [rbx+48h], r15
0x1800320f5  jnz     short loc_180032101
0x1800320f7  cmp     [rbx+30h], r15
0x1800320fb  jz      loc_180032191
0x180032101  lea     r8, asc_180057780; "    "
0x180032108  mov     rdx, rsi; unsigned __int16 *
0x18003210b  mov     rcx, rax; this
0x18003210e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180032113  mov     r9, [rbx+18h]; unsigned __int16 *
0x180032117  test    r9, r9
0x18003211a  jz      short loc_18003212E
0x18003211c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180032123  mov     rdx, rsi; unsigned __int16 *
0x180032126  mov     rcx, rax; this
0x180032129  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003212e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180032132  test    r9, r9
0x180032135  jz      short loc_180032149
0x180032137  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003213e  mov     rdx, rsi; unsigned __int16 *
0x180032141  mov     rcx, rax; this
0x180032144  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180032149  mov     rcx, [rbx+28h]
0x18003214d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180032151  mov     rdx, rsi; unsigned __int16 *
0x180032154  test    rcx, rcx
0x180032157  jz      short loc_18003216F
0x180032159  mov     [rsp+278h+lpBuffer], rcx
0x18003215e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180032165  mov     rcx, rax; this
0x180032168  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003216d  jmp     short loc_180032191
0x18003216f  mov     rcx, rax; this
0x180032172  test    r9, r9
0x180032175  jz      short loc_180032185
0x180032177  lea     r8, aHs; "[%hs]\n"
0x18003217e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180032183  jmp     short loc_180032191
0x180032185  lea     r8, asc_1800577F8; "\n"
0x18003218c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180032191  xor     eax, eax
0x180032193  mov     rcx, [rsp+278h+var_38]
0x18003219b  xor     rcx, rsp; StackCookie
0x18003219e  call    __security_check_cookie
0x1800321a3  mov     rbx, [rsp+278h+arg_18]
0x1800321ab  add     rsp, 250h
0x1800321b2  pop     r15
0x1800321b4  pop     r14
0x1800321b6  pop     rdi
0x1800321b7  pop     rsi
0x1800321b8  pop     rbp
0x1800321b9  retn
```
