# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008a04`
- end: `0x180008cba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000701c`
- `0x180007284`
- `0x180009654`

## callees

- `0x180008a04`
- `0x180009954`
- `0x18000cfbe`
- `0x18000cff0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008bb7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008b36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008b36`

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
          v8 = (const char *)&dword_180012904;
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
0x180008a04  mov     [rsp+arg_18], rbx
0x180008a09  push    rbp
0x180008a0a  push    rsi
0x180008a0b  push    rdi
0x180008a0c  push    r14
0x180008a0e  push    r15
0x180008a10  sub     rsp, 250h
0x180008a17  mov     rax, cs:__security_cookie
0x180008a1e  xor     rax, rsp
0x180008a21  mov     [rsp+278h+var_38], rax
0x180008a29  xor     r15d, r15d
0x180008a2c  mov     rbx, r8
0x180008a2f  mov     rsi, rdx
0x180008a32  mov     r14, rcx
0x180008a35  test    rdx, rdx
0x180008a38  jz      loc_180008C91
0x180008a3e  test    rcx, rcx
0x180008a41  jz      loc_180008C91
0x180008a47  mov     rax, cs:g_pfnResultLoggingCallback
0x180008a4e  mov     [rcx], r15w
0x180008a52  test    rax, rax
0x180008a55  jz      short loc_180008A78
0x180008a57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008a5e  jz      short loc_180008A78
0x180008a60  mov     r8, rdx
0x180008a63  mov     rdx, rcx
0x180008a66  mov     rcx, rbx
0x180008a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a6e  cmp     [r14], r15w
0x180008a72  jnz     loc_180008C91
0x180008a78  mov     ecx, [rbx]
0x180008a7a  mov     bpl, 8
0x180008a7d  test    ecx, ecx
0x180008a7f  jz      short loc_180008ACA
0x180008a81  sub     ecx, 1
0x180008a84  jz      short loc_180008AB2
0x180008a86  sub     ecx, 1
0x180008a89  jz      short loc_180008AA2
0x180008a8b  cmp     ecx, 1
0x180008a8e  jz      short loc_180008A99
0x180008a90  lea     rdi, dword_180012904
0x180008a97  jmp     short loc_180008AD1
0x180008a99  lea     rdi, aFailfast; "FailFast"
0x180008aa0  jmp     short loc_180008AD1
0x180008aa2  lea     rax, aLoghr; "LogHr"
0x180008aa9  lea     rdi, aLognt; "LogNt"
0x180008ab0  jmp     short loc_180008AC0
0x180008ab2  lea     rax, aReturnhr; "ReturnHr"
0x180008ab9  lea     rdi, aReturnnt; "ReturnNt"
0x180008ac0  test    [rbx+4], bpl
0x180008ac4  cmovz   rdi, rax
0x180008ac8  jmp     short loc_180008AD1
0x180008aca  lea     rdi, aException; "Exception"
0x180008ad1  xor     edx, edx; Val
0x180008ad3  lea     rcx, [rsp+278h+Buffer]; void *
0x180008ad8  mov     r8d, 200h; Size
0x180008ade  call    memset_0
0x180008ae3  test    [rbx+4], bpl
0x180008ae7  jz      short loc_180008B0C
0x180008ae9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008af0  mov     ebp, [rbx+0Ch]
0x180008af3  test    rax, rax
0x180008af6  jz      short loc_180008B3C
0x180008af8  mov     r8d, 100h
0x180008afe  lea     rdx, [rsp+278h+Buffer]
0x180008b03  mov     ecx, ebp
0x180008b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0a  jmp     short loc_180008B3C
0x180008b0c  mov     ebp, [rbx+8]
0x180008b0f  lea     rax, [rsp+278h+Buffer]
0x180008b14  mov     [rsp+278h+Arguments], r15; Arguments
0x180008b19  mov     r8d, ebp; dwMessageId
0x180008b1c  mov     [rsp+278h+nSize], 100h; nSize
0x180008b24  mov     r9d, 400h; dwLanguageId
0x180008b2a  xor     edx, edx; lpSource
0x180008b2c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008b31  mov     ecx, 1200h; dwFlags
0x180008b36  call    cs:__imp_FormatMessageW
0x180008b3c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008b40  lea     rsi, [r14+rsi*2]
0x180008b44  mov     rax, [rbx+88h]
0x180008b4b  mov     rdx, rsi; unsigned __int16 *
0x180008b4e  mov     rcx, [rbx+80h]
0x180008b55  test    r9, r9
0x180008b58  jz      short loc_180008B7C
0x180008b5a  mov     [rsp+278h+Arguments], rax
0x180008b5f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008b66  mov     eax, [rbx+40h]
0x180008b69  mov     qword ptr [rsp+278h+nSize], rcx
0x180008b6e  mov     rcx, r14; this
0x180008b71  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008b75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008b7a  jmp     short loc_180008B93
0x180008b7c  mov     r9, rcx; unsigned __int16 *
0x180008b7f  mov     [rsp+278h+lpBuffer], rax
0x180008b84  mov     rcx, r14; this
0x180008b87  lea     r8, aHsP; "%hs!%p: "
0x180008b8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008b93  mov     r9, [rbx+90h]; unsigned __int16 *
0x180008b9a  mov     r14, rax
0x180008b9d  test    r9, r9
0x180008ba0  jz      short loc_180008BB7
0x180008ba2  lea     r8, aCallerP; "(caller: %p) "
0x180008ba9  mov     rdx, rsi; unsigned __int16 *
0x180008bac  mov     rcx, rax; this
0x180008baf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008bb4  mov     r14, rax
0x180008bb7  call    cs:__imp_GetCurrentThreadId
0x180008bbd  lea     rcx, [rsp+278h+Buffer]
0x180008bc2  mov     r9, rdi; unsigned __int16 *
0x180008bc5  mov     [rsp+278h+var_240], rcx
0x180008bca  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008bd1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180008bd5  mov     rdx, rsi; unsigned __int16 *
0x180008bd8  mov     [rsp+278h+nSize], eax
0x180008bdc  mov     rcx, r14; this
0x180008bdf  mov     eax, [rbx+44h]
0x180008be2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008be6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008beb  cmp     [rbx+18h], r15
0x180008bef  jnz     short loc_180008C01
0x180008bf1  cmp     [rbx+48h], r15
0x180008bf5  jnz     short loc_180008C01
0x180008bf7  cmp     [rbx+30h], r15
0x180008bfb  jz      loc_180008C91
0x180008c01  lea     r8, asc_1800129F0; "    "
0x180008c08  mov     rdx, rsi; unsigned __int16 *
0x180008c0b  mov     rcx, rax; this
0x180008c0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008c13  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008c17  test    r9, r9
0x180008c1a  jz      short loc_180008C2E
0x180008c1c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008c23  mov     rdx, rsi; unsigned __int16 *
0x180008c26  mov     rcx, rax; this
0x180008c29  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008c2e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008c32  test    r9, r9
0x180008c35  jz      short loc_180008C49
0x180008c37  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180008c3e  mov     rdx, rsi; unsigned __int16 *
0x180008c41  mov     rcx, rax; this
0x180008c44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008c49  mov     rcx, [rbx+28h]
0x180008c4d  mov     rdx, rsi; unsigned __int16 *
0x180008c50  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008c54  test    rcx, rcx
0x180008c57  jz      short loc_180008C6F
0x180008c59  mov     [rsp+278h+lpBuffer], rcx
0x180008c5e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008c65  mov     rcx, rax; this
0x180008c68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008c6d  jmp     short loc_180008C91
0x180008c6f  mov     rcx, rax; this
0x180008c72  test    r9, r9
0x180008c75  jz      short loc_180008C85
0x180008c77  lea     r8, aHs; "[%hs]\n"
0x180008c7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008c83  jmp     short loc_180008C91
0x180008c85  lea     r8, asc_180012A68; "\n"
0x180008c8c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008c91  xor     eax, eax
0x180008c93  mov     rcx, [rsp+278h+var_38]
0x180008c9b  xor     rcx, rsp; StackCookie
0x180008c9e  call    __security_check_cookie
0x180008ca3  mov     rbx, [rsp+278h+arg_18]
0x180008cab  add     rsp, 250h
0x180008cb2  pop     r15
0x180008cb4  pop     r14
0x180008cb6  pop     rdi
0x180008cb7  pop     rsi
0x180008cb8  pop     rbp
0x180008cb9  retn
```
