# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140011cc8`
- end: `0x140011f7e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1400090d4`
- `0x140009354`
- `0x140012c74`
- `0x14001edc0`
- `0x14002c75c`
- `0x14009deb3`
- `0x14009dfe7`
- `0x1400a1a1b`
- `0x1400a1e61`

## callees

- `0x140005530`
- `0x140006314`
- `0x140011cc8`
- `0x140013094`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140011dfa`
- `KERNEL32!FormatMessageW` at `0x140011dfa`
- `KERNEL32!GetCurrentThreadId` at `0x140011e7b`
- `KERNEL32!GetCurrentThreadId` at `0x140011e7b`

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
          v7 = (const char *)&byte_1400B3CE9;
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
0x140011cc8  mov     [rsp+arg_18], rbx
0x140011ccd  push    rbp
0x140011cce  push    rsi
0x140011ccf  push    rdi
0x140011cd0  push    r14
0x140011cd2  push    r15
0x140011cd4  sub     rsp, 250h
0x140011cdb  mov     rax, cs:__security_cookie
0x140011ce2  xor     rax, rsp
0x140011ce5  mov     [rsp+278h+var_38], rax
0x140011ced  mov     rbx, r8
0x140011cf0  mov     rsi, rdx
0x140011cf3  mov     r14, rcx
0x140011cf6  xor     r15d, r15d
0x140011cf9  test    rdx, rdx
0x140011cfc  jz      loc_140011F55
0x140011d02  test    rcx, rcx
0x140011d05  jz      loc_140011F55
0x140011d0b  mov     [rcx], r15w
0x140011d0f  mov     rax, cs:g_pfnResultLoggingCallback
0x140011d16  test    rax, rax
0x140011d19  jz      short loc_140011D3C
0x140011d1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140011d22  jz      short loc_140011D3C
0x140011d24  mov     r8, rdx
0x140011d27  mov     rdx, rcx
0x140011d2a  mov     rcx, rbx
0x140011d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d32  cmp     [r14], r15w
0x140011d36  jnz     loc_140011F55
0x140011d3c  mov     ecx, [rbx]
0x140011d3e  mov     bpl, 8
0x140011d41  test    ecx, ecx
0x140011d43  jz      short loc_140011D8E
0x140011d45  sub     ecx, 1
0x140011d48  jz      short loc_140011D76
0x140011d4a  sub     ecx, 1
0x140011d4d  jz      short loc_140011D66
0x140011d4f  cmp     ecx, 1
0x140011d52  jz      short loc_140011D5D
0x140011d54  lea     rdi, byte_1400B3CE9
0x140011d5b  jmp     short loc_140011D95
0x140011d5d  lea     rdi, aFailfast; "FailFast"
0x140011d64  jmp     short loc_140011D95
0x140011d66  lea     rax, aLoghr; "LogHr"
0x140011d6d  lea     rdi, aLognt; "LogNt"
0x140011d74  jmp     short loc_140011D84
0x140011d76  lea     rax, aReturnhr; "ReturnHr"
0x140011d7d  lea     rdi, aReturnnt; "ReturnNt"
0x140011d84  test    [rbx+4], bpl
0x140011d88  cmovz   rdi, rax
0x140011d8c  jmp     short loc_140011D95
0x140011d8e  lea     rdi, aException; "Exception"
0x140011d95  xor     edx, edx; Val
0x140011d97  mov     r8d, 200h; Size
0x140011d9d  lea     rcx, [rsp+278h+Buffer]; void *
0x140011da2  call    memset_0
0x140011da7  test    [rbx+4], bpl
0x140011dab  jz      short loc_140011DD0
0x140011dad  mov     ebp, [rbx+0Ch]
0x140011db0  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140011db7  test    rax, rax
0x140011dba  jz      short loc_140011E00
0x140011dbc  mov     r8d, 100h
0x140011dc2  lea     rdx, [rsp+278h+Buffer]
0x140011dc7  mov     ecx, ebp
0x140011dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011dce  jmp     short loc_140011E00
0x140011dd0  mov     ebp, [rbx+8]
0x140011dd3  mov     [rsp+278h+Arguments], r15; Arguments
0x140011dd8  mov     [rsp+278h+nSize], 100h; nSize
0x140011de0  lea     rax, [rsp+278h+Buffer]
0x140011de5  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140011dea  mov     r9d, 400h; dwLanguageId
0x140011df0  mov     r8d, ebp; dwMessageId
0x140011df3  xor     edx, edx; lpSource
0x140011df5  mov     ecx, 1200h; dwFlags
0x140011dfa  call    cs:__imp_FormatMessageW
0x140011e00  lea     rsi, [r14+rsi*2]
0x140011e04  mov     r9, [rbx+38h]; unsigned __int16 *
0x140011e08  mov     rax, [rbx+88h]
0x140011e0f  mov     rcx, [rbx+80h]
0x140011e16  mov     rdx, rsi; unsigned __int16 *
0x140011e19  test    r9, r9
0x140011e1c  jz      short loc_140011E40
0x140011e1e  mov     [rsp+278h+Arguments], rax
0x140011e23  mov     qword ptr [rsp+278h+nSize], rcx
0x140011e28  mov     eax, [rbx+40h]
0x140011e2b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140011e2f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140011e36  mov     rcx, r14; this
0x140011e39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011e3e  jmp     short loc_140011E57
0x140011e40  mov     [rsp+278h+lpBuffer], rax
0x140011e45  mov     r9, rcx; unsigned __int16 *
0x140011e48  lea     r8, aHsP; "%hs!%p: "
0x140011e4f  mov     rcx, r14; this
0x140011e52  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011e57  mov     r14, rax
0x140011e5a  mov     r9, [rbx+90h]; unsigned __int16 *
0x140011e61  test    r9, r9
0x140011e64  jz      short loc_140011E7B
0x140011e66  lea     r8, aCallerP; "(caller: %p) "
0x140011e6d  mov     rdx, rsi; unsigned __int16 *
0x140011e70  mov     rcx, rax; this
0x140011e73  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011e78  mov     r14, rax
0x140011e7b  call    cs:__imp_GetCurrentThreadId
0x140011e81  lea     rcx, [rsp+278h+Buffer]
0x140011e86  mov     [rsp+278h+var_240], rcx
0x140011e8b  mov     dword ptr [rsp+278h+Arguments], ebp
0x140011e8f  mov     [rsp+278h+nSize], eax
0x140011e93  mov     eax, [rbx+44h]
0x140011e96  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140011e9a  mov     r9, rdi; unsigned __int16 *
0x140011e9d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140011ea4  mov     rdx, rsi; unsigned __int16 *
0x140011ea7  mov     rcx, r14; this
0x140011eaa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011eaf  cmp     [rbx+18h], r15
0x140011eb3  jnz     short loc_140011EC5
0x140011eb5  cmp     [rbx+48h], r15
0x140011eb9  jnz     short loc_140011EC5
0x140011ebb  cmp     [rbx+30h], r15
0x140011ebf  jz      loc_140011F55
0x140011ec5  lea     r8, asc_1400B3DD8; "    "
0x140011ecc  mov     rdx, rsi; unsigned __int16 *
0x140011ecf  mov     rcx, rax; this
0x140011ed2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011ed7  mov     r9, [rbx+18h]; unsigned __int16 *
0x140011edb  test    r9, r9
0x140011ede  jz      short loc_140011EF2
0x140011ee0  lea     r8, aMsgWs; "Msg:[%ws] "
0x140011ee7  mov     rdx, rsi; unsigned __int16 *
0x140011eea  mov     rcx, rax; this
0x140011eed  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011ef2  mov     r9, [rbx+48h]; unsigned __int16 *
0x140011ef6  test    r9, r9
0x140011ef9  jz      short loc_140011F0D
0x140011efb  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140011f02  mov     rdx, rsi; unsigned __int16 *
0x140011f05  mov     rcx, rax; this
0x140011f08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f0d  mov     rcx, [rbx+28h]
0x140011f11  mov     r9, [rbx+30h]; unsigned __int16 *
0x140011f15  mov     rdx, rsi; unsigned __int16 *
0x140011f18  test    rcx, rcx
0x140011f1b  jz      short loc_140011F33
0x140011f1d  mov     [rsp+278h+lpBuffer], rcx
0x140011f22  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140011f29  mov     rcx, rax; this
0x140011f2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f31  jmp     short loc_140011F55
0x140011f33  mov     rcx, rax; this
0x140011f36  test    r9, r9
0x140011f39  jz      short loc_140011F49
0x140011f3b  lea     r8, aHs; "[%hs]\n"
0x140011f42  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f47  jmp     short loc_140011F55
0x140011f49  lea     r8, asc_1400B3E50; "\n"
0x140011f50  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f55  xor     eax, eax
0x140011f57  mov     rcx, [rsp+278h+var_38]
0x140011f5f  xor     rcx, rsp; StackCookie
0x140011f62  call    __security_check_cookie
0x140011f67  mov     rbx, [rsp+278h+arg_18]
0x140011f6f  add     rsp, 250h
0x140011f76  pop     r15
0x140011f78  pop     r14
0x140011f7a  pop     rdi
0x140011f7b  pop     rsi
0x140011f7c  pop     rbp
0x140011f7d  retn
```
