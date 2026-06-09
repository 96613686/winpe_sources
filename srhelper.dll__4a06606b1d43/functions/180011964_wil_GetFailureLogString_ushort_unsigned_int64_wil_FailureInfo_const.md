# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180011964`
- end: `0x180011c1a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fa50`
- `0x18000fcb8`
- `0x1800122c0`

## callees

- `0x180011964`
- `0x1800125c0`
- `0x1800157be`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011b17`
- `KERNEL32!GetCurrentThreadId` at `0x180011b17`
- `KERNEL32!FormatMessageW` at `0x180011a96`
- `KERNEL32!FormatMessageW` at `0x180011a96`

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
          v8 = (const char *)&byte_18001A1DD;
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
0x180011964  mov     [rsp+arg_18], rbx
0x180011969  push    rbp
0x18001196a  push    rsi
0x18001196b  push    rdi
0x18001196c  push    r14
0x18001196e  push    r15
0x180011970  sub     rsp, 250h
0x180011977  mov     rax, cs:__security_cookie
0x18001197e  xor     rax, rsp
0x180011981  mov     [rsp+278h+var_38], rax
0x180011989  xor     r15d, r15d
0x18001198c  mov     rbx, r8
0x18001198f  mov     rsi, rdx
0x180011992  mov     r14, rcx
0x180011995  test    rdx, rdx
0x180011998  jz      loc_180011BF1
0x18001199e  test    rcx, rcx
0x1800119a1  jz      loc_180011BF1
0x1800119a7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800119ae  mov     [rcx], r15w
0x1800119b2  test    rax, rax
0x1800119b5  jz      short loc_1800119D8
0x1800119b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800119be  jz      short loc_1800119D8
0x1800119c0  mov     r8, rdx
0x1800119c3  mov     rdx, rcx
0x1800119c6  mov     rcx, rbx
0x1800119c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119ce  cmp     [r14], r15w
0x1800119d2  jnz     loc_180011BF1
0x1800119d8  mov     ecx, [rbx]
0x1800119da  mov     bpl, 8
0x1800119dd  test    ecx, ecx
0x1800119df  jz      short loc_180011A2A
0x1800119e1  sub     ecx, 1
0x1800119e4  jz      short loc_180011A12
0x1800119e6  sub     ecx, 1
0x1800119e9  jz      short loc_180011A02
0x1800119eb  cmp     ecx, 1
0x1800119ee  jz      short loc_1800119F9
0x1800119f0  lea     rdi, byte_18001A1DD
0x1800119f7  jmp     short loc_180011A31
0x1800119f9  lea     rdi, aFailfast; "FailFast"
0x180011a00  jmp     short loc_180011A31
0x180011a02  lea     rax, aLoghr; "LogHr"
0x180011a09  lea     rdi, aLognt; "LogNt"
0x180011a10  jmp     short loc_180011A20
0x180011a12  lea     rax, aReturnhr; "ReturnHr"
0x180011a19  lea     rdi, aReturnnt; "ReturnNt"
0x180011a20  test    [rbx+4], bpl
0x180011a24  cmovz   rdi, rax
0x180011a28  jmp     short loc_180011A31
0x180011a2a  lea     rdi, aException; "Exception"
0x180011a31  xor     edx, edx; Val
0x180011a33  lea     rcx, [rsp+278h+Buffer]; void *
0x180011a38  mov     r8d, 200h; Size
0x180011a3e  call    memset_0
0x180011a43  test    [rbx+4], bpl
0x180011a47  jz      short loc_180011A6C
0x180011a49  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180011a50  mov     ebp, [rbx+0Ch]
0x180011a53  test    rax, rax
0x180011a56  jz      short loc_180011A9C
0x180011a58  mov     r8d, 100h
0x180011a5e  lea     rdx, [rsp+278h+Buffer]
0x180011a63  mov     ecx, ebp
0x180011a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6a  jmp     short loc_180011A9C
0x180011a6c  mov     ebp, [rbx+8]
0x180011a6f  lea     rax, [rsp+278h+Buffer]
0x180011a74  mov     [rsp+278h+Arguments], r15; Arguments
0x180011a79  mov     r8d, ebp; dwMessageId
0x180011a7c  mov     [rsp+278h+nSize], 100h; nSize
0x180011a84  mov     r9d, 400h; dwLanguageId
0x180011a8a  xor     edx, edx; lpSource
0x180011a8c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180011a91  mov     ecx, 1200h; dwFlags
0x180011a96  call    cs:__imp_FormatMessageW
0x180011a9c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180011aa0  lea     rsi, [r14+rsi*2]
0x180011aa4  mov     rax, [rbx+88h]
0x180011aab  mov     rdx, rsi; unsigned __int16 *
0x180011aae  mov     rcx, [rbx+80h]
0x180011ab5  test    r9, r9
0x180011ab8  jz      short loc_180011ADC
0x180011aba  mov     [rsp+278h+Arguments], rax
0x180011abf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180011ac6  mov     eax, [rbx+40h]
0x180011ac9  mov     qword ptr [rsp+278h+nSize], rcx
0x180011ace  mov     rcx, r14; this
0x180011ad1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011ad5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011ada  jmp     short loc_180011AF3
0x180011adc  mov     r9, rcx; unsigned __int16 *
0x180011adf  mov     [rsp+278h+lpBuffer], rax
0x180011ae4  mov     rcx, r14; this
0x180011ae7  lea     r8, aHsP; "%hs!%p: "
0x180011aee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011af3  mov     r9, [rbx+90h]; unsigned __int16 *
0x180011afa  mov     r14, rax
0x180011afd  test    r9, r9
0x180011b00  jz      short loc_180011B17
0x180011b02  lea     r8, aCallerP; "(caller: %p) "
0x180011b09  mov     rdx, rsi; unsigned __int16 *
0x180011b0c  mov     rcx, rax; this
0x180011b0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011b14  mov     r14, rax
0x180011b17  call    cs:__imp_GetCurrentThreadId
0x180011b1d  lea     rcx, [rsp+278h+Buffer]
0x180011b22  mov     r9, rdi; unsigned __int16 *
0x180011b25  mov     [rsp+278h+var_240], rcx
0x180011b2a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180011b31  mov     dword ptr [rsp+278h+Arguments], ebp
0x180011b35  mov     rdx, rsi; unsigned __int16 *
0x180011b38  mov     [rsp+278h+nSize], eax
0x180011b3c  mov     rcx, r14; this
0x180011b3f  mov     eax, [rbx+44h]
0x180011b42  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011b46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011b4b  cmp     [rbx+18h], r15
0x180011b4f  jnz     short loc_180011B61
0x180011b51  cmp     [rbx+48h], r15
0x180011b55  jnz     short loc_180011B61
0x180011b57  cmp     [rbx+30h], r15
0x180011b5b  jz      loc_180011BF1
0x180011b61  lea     r8, asc_18001A2C8; "    "
0x180011b68  mov     rdx, rsi; unsigned __int16 *
0x180011b6b  mov     rcx, rax; this
0x180011b6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011b73  mov     r9, [rbx+18h]; unsigned __int16 *
0x180011b77  test    r9, r9
0x180011b7a  jz      short loc_180011B8E
0x180011b7c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180011b83  mov     rdx, rsi; unsigned __int16 *
0x180011b86  mov     rcx, rax; this
0x180011b89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011b8e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180011b92  test    r9, r9
0x180011b95  jz      short loc_180011BA9
0x180011b97  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180011b9e  mov     rdx, rsi; unsigned __int16 *
0x180011ba1  mov     rcx, rax; this
0x180011ba4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011ba9  mov     rcx, [rbx+28h]
0x180011bad  mov     rdx, rsi; unsigned __int16 *
0x180011bb0  mov     r9, [rbx+30h]; unsigned __int16 *
0x180011bb4  test    rcx, rcx
0x180011bb7  jz      short loc_180011BCF
0x180011bb9  mov     [rsp+278h+lpBuffer], rcx
0x180011bbe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180011bc5  mov     rcx, rax; this
0x180011bc8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011bcd  jmp     short loc_180011BF1
0x180011bcf  mov     rcx, rax; this
0x180011bd2  test    r9, r9
0x180011bd5  jz      short loc_180011BE5
0x180011bd7  lea     r8, aHs; "[%hs]\n"
0x180011bde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011be3  jmp     short loc_180011BF1
0x180011be5  lea     r8, asc_18001A340; "\n"
0x180011bec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011bf1  xor     eax, eax
0x180011bf3  mov     rcx, [rsp+278h+var_38]
0x180011bfb  xor     rcx, rsp; StackCookie
0x180011bfe  call    __security_check_cookie
0x180011c03  mov     rbx, [rsp+278h+arg_18]
0x180011c0b  add     rsp, 250h
0x180011c12  pop     r15
0x180011c14  pop     r14
0x180011c16  pop     rdi
0x180011c17  pop     rsi
0x180011c18  pop     rbp
0x180011c19  retn
```
