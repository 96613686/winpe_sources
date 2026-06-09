# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008c64`
- end: `0x180008f27`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006d64`
- `0x18000967c`
- `0x18000c860`

## callees

- `0x180005680`
- `0x18000601c`
- `0x180008c64`
- `0x180009990`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e1d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008d96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008d96`

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
          v7 = (const char *)&dword_18001929C;
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
0x180008c64  mov     [rsp+arg_18], rbx
0x180008c69  push    rbp
0x180008c6a  push    rsi
0x180008c6b  push    rdi
0x180008c6c  push    r14
0x180008c6e  push    r15
0x180008c70  sub     rsp, 250h
0x180008c77  mov     rax, cs:__security_cookie
0x180008c7e  xor     rax, rsp
0x180008c81  mov     [rsp+278h+var_38], rax
0x180008c89  mov     rbx, r8
0x180008c8c  mov     rsi, rdx
0x180008c8f  mov     r14, rcx
0x180008c92  xor     r15d, r15d
0x180008c95  test    rdx, rdx
0x180008c98  jz      loc_180008EFD
0x180008c9e  test    rcx, rcx
0x180008ca1  jz      loc_180008EFD
0x180008ca7  mov     [rcx], r15w
0x180008cab  mov     rax, cs:g_pfnResultLoggingCallback
0x180008cb2  test    rax, rax
0x180008cb5  jz      short loc_180008CD8
0x180008cb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008cbe  jz      short loc_180008CD8
0x180008cc0  mov     r8, rdx
0x180008cc3  mov     rdx, rcx
0x180008cc6  mov     rcx, rbx
0x180008cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cce  cmp     [r14], r15w
0x180008cd2  jnz     loc_180008EFD
0x180008cd8  mov     ecx, [rbx]
0x180008cda  mov     bpl, 8
0x180008cdd  test    ecx, ecx
0x180008cdf  jz      short loc_180008D2A
0x180008ce1  sub     ecx, 1
0x180008ce4  jz      short loc_180008D12
0x180008ce6  sub     ecx, 1
0x180008ce9  jz      short loc_180008D02
0x180008ceb  cmp     ecx, 1
0x180008cee  jz      short loc_180008CF9
0x180008cf0  lea     rdi, dword_18001929C
0x180008cf7  jmp     short loc_180008D31
0x180008cf9  lea     rdi, aFailfast; "FailFast"
0x180008d00  jmp     short loc_180008D31
0x180008d02  lea     rax, aLoghr; "LogHr"
0x180008d09  lea     rdi, aLognt; "LogNt"
0x180008d10  jmp     short loc_180008D20
0x180008d12  lea     rax, aReturnhr; "ReturnHr"
0x180008d19  lea     rdi, aReturnnt; "ReturnNt"
0x180008d20  test    [rbx+4], bpl
0x180008d24  cmovz   rdi, rax
0x180008d28  jmp     short loc_180008D31
0x180008d2a  lea     rdi, aException; "Exception"
0x180008d31  xor     edx, edx; Val
0x180008d33  mov     r8d, 200h; Size
0x180008d39  lea     rcx, [rsp+278h+Buffer]; void *
0x180008d3e  call    memset_0
0x180008d43  test    [rbx+4], bpl
0x180008d47  jz      short loc_180008D6C
0x180008d49  mov     ebp, [rbx+0Ch]
0x180008d4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008d53  test    rax, rax
0x180008d56  jz      short loc_180008DA2
0x180008d58  mov     r8d, 100h
0x180008d5e  lea     rdx, [rsp+278h+Buffer]
0x180008d63  mov     ecx, ebp
0x180008d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d6a  jmp     short loc_180008DA2
0x180008d6c  mov     ebp, [rbx+8]
0x180008d6f  mov     [rsp+278h+Arguments], r15; Arguments
0x180008d74  mov     [rsp+278h+nSize], 100h; nSize
0x180008d7c  lea     rax, [rsp+278h+Buffer]
0x180008d81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008d86  mov     r9d, 400h; dwLanguageId
0x180008d8c  mov     r8d, ebp; dwMessageId
0x180008d8f  xor     edx, edx; lpSource
0x180008d91  mov     ecx, 1200h; dwFlags
0x180008d96  call    cs:__imp_FormatMessageW
0x180008d9d  nop     dword ptr [rax+rax+00h]
0x180008da2  lea     rsi, [r14+rsi*2]
0x180008da6  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008daa  mov     rax, [rbx+88h]
0x180008db1  mov     rcx, [rbx+80h]
0x180008db8  mov     rdx, rsi; unsigned __int16 *
0x180008dbb  test    r9, r9
0x180008dbe  jz      short loc_180008DE2
0x180008dc0  mov     [rsp+278h+Arguments], rax
0x180008dc5  mov     qword ptr [rsp+278h+nSize], rcx
0x180008dca  mov     eax, [rbx+40h]
0x180008dcd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008dd1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008dd8  mov     rcx, r14; this
0x180008ddb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008de0  jmp     short loc_180008DF9
0x180008de2  mov     [rsp+278h+lpBuffer], rax
0x180008de7  mov     r9, rcx; unsigned __int16 *
0x180008dea  lea     r8, aHsP; "%hs!%p: "
0x180008df1  mov     rcx, r14; this
0x180008df4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008df9  mov     r14, rax
0x180008dfc  mov     r9, [rbx+90h]; unsigned __int16 *
0x180008e03  test    r9, r9
0x180008e06  jz      short loc_180008E1D
0x180008e08  lea     r8, aCallerP; "(caller: %p) "
0x180008e0f  mov     rdx, rsi; unsigned __int16 *
0x180008e12  mov     rcx, rax; this
0x180008e15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e1a  mov     r14, rax
0x180008e1d  call    cs:__imp_GetCurrentThreadId
0x180008e24  nop     dword ptr [rax+rax+00h]
0x180008e29  lea     rcx, [rsp+278h+Buffer]
0x180008e2e  mov     [rsp+278h+var_240], rcx
0x180008e33  mov     dword ptr [rsp+278h+Arguments], ebp
0x180008e37  mov     [rsp+278h+nSize], eax
0x180008e3b  mov     eax, [rbx+44h]
0x180008e3e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008e42  mov     r9, rdi; unsigned __int16 *
0x180008e45  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008e4c  mov     rdx, rsi; unsigned __int16 *
0x180008e4f  mov     rcx, r14; this
0x180008e52  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e57  cmp     [rbx+18h], r15
0x180008e5b  jnz     short loc_180008E6D
0x180008e5d  cmp     [rbx+48h], r15
0x180008e61  jnz     short loc_180008E6D
0x180008e63  cmp     [rbx+30h], r15
0x180008e67  jz      loc_180008EFD
0x180008e6d  lea     r8, asc_1800193A0; "    "
0x180008e74  mov     rdx, rsi; unsigned __int16 *
0x180008e77  mov     rcx, rax; this
0x180008e7a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e7f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008e83  test    r9, r9
0x180008e86  jz      short loc_180008E9A
0x180008e88  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008e8f  mov     rdx, rsi; unsigned __int16 *
0x180008e92  mov     rcx, rax; this
0x180008e95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e9a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008e9e  test    r9, r9
0x180008ea1  jz      short loc_180008EB5
0x180008ea3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180008eaa  mov     rdx, rsi; unsigned __int16 *
0x180008ead  mov     rcx, rax; this
0x180008eb0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008eb5  mov     rcx, [rbx+28h]
0x180008eb9  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008ebd  mov     rdx, rsi; unsigned __int16 *
0x180008ec0  test    rcx, rcx
0x180008ec3  jz      short loc_180008EDB
0x180008ec5  mov     [rsp+278h+lpBuffer], rcx
0x180008eca  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008ed1  mov     rcx, rax; this
0x180008ed4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008ed9  jmp     short loc_180008EFD
0x180008edb  mov     rcx, rax; this
0x180008ede  test    r9, r9
0x180008ee1  jz      short loc_180008EF1
0x180008ee3  lea     r8, aHs; "[%hs]\n"
0x180008eea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008eef  jmp     short loc_180008EFD
0x180008ef1  lea     r8, asc_180019418; "\n"
0x180008ef8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008efd  xor     eax, eax
0x180008eff  mov     rcx, [rsp+278h+var_38]
0x180008f07  xor     rcx, rsp; StackCookie
0x180008f0a  call    __security_check_cookie
0x180008f0f  mov     rbx, [rsp+278h+arg_18]
0x180008f17  add     rsp, 250h
0x180008f1e  pop     r15
0x180008f20  pop     r14
0x180008f22  pop     rdi
0x180008f23  pop     rsi
0x180008f24  pop     rbp
0x180008f25  retn
```
