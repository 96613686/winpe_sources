# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004944`
- end: `0x140004bfa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400031dc`
- `0x140003444`
- `0x140005408`

## callees

- `0x1400015a0`
- `0x140002254`
- `0x140004944`
- `0x140005708`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004af7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004af7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004a76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004a76`

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
          v8 = (const char *)&qword_14000DF90;
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
0x140004944  mov     [rsp+arg_18], rbx
0x140004949  push    rbp
0x14000494a  push    rsi
0x14000494b  push    rdi
0x14000494c  push    r14
0x14000494e  push    r15
0x140004950  sub     rsp, 250h
0x140004957  mov     rax, cs:__security_cookie
0x14000495e  xor     rax, rsp
0x140004961  mov     [rsp+278h+var_38], rax
0x140004969  xor     r15d, r15d
0x14000496c  mov     rbx, r8
0x14000496f  mov     rsi, rdx
0x140004972  mov     r14, rcx
0x140004975  test    rdx, rdx
0x140004978  jz      loc_140004BD1
0x14000497e  test    rcx, rcx
0x140004981  jz      loc_140004BD1
0x140004987  mov     rax, cs:g_pfnResultLoggingCallback
0x14000498e  mov     [rcx], r15w
0x140004992  test    rax, rax
0x140004995  jz      short loc_1400049B8
0x140004997  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000499e  jz      short loc_1400049B8
0x1400049a0  mov     r8, rdx
0x1400049a3  mov     rdx, rcx
0x1400049a6  mov     rcx, rbx
0x1400049a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049ae  cmp     [r14], r15w
0x1400049b2  jnz     loc_140004BD1
0x1400049b8  mov     ecx, [rbx]
0x1400049ba  mov     bpl, 8
0x1400049bd  test    ecx, ecx
0x1400049bf  jz      short loc_140004A0A
0x1400049c1  sub     ecx, 1
0x1400049c4  jz      short loc_1400049F2
0x1400049c6  sub     ecx, 1
0x1400049c9  jz      short loc_1400049E2
0x1400049cb  cmp     ecx, 1
0x1400049ce  jz      short loc_1400049D9
0x1400049d0  lea     rdi, qword_14000DF90
0x1400049d7  jmp     short loc_140004A11
0x1400049d9  lea     rdi, aFailfast; "FailFast"
0x1400049e0  jmp     short loc_140004A11
0x1400049e2  lea     rax, aLoghr; "LogHr"
0x1400049e9  lea     rdi, aLognt; "LogNt"
0x1400049f0  jmp     short loc_140004A00
0x1400049f2  lea     rax, aReturnhr; "ReturnHr"
0x1400049f9  lea     rdi, aReturnnt; "ReturnNt"
0x140004a00  test    [rbx+4], bpl
0x140004a04  cmovz   rdi, rax
0x140004a08  jmp     short loc_140004A11
0x140004a0a  lea     rdi, aException; "Exception"
0x140004a11  xor     edx, edx; Val
0x140004a13  lea     rcx, [rsp+278h+Buffer]; void *
0x140004a18  mov     r8d, 200h; Size
0x140004a1e  call    memset_0
0x140004a23  test    [rbx+4], bpl
0x140004a27  jz      short loc_140004A4C
0x140004a29  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004a30  mov     ebp, [rbx+0Ch]
0x140004a33  test    rax, rax
0x140004a36  jz      short loc_140004A7C
0x140004a38  mov     r8d, 100h
0x140004a3e  lea     rdx, [rsp+278h+Buffer]
0x140004a43  mov     ecx, ebp
0x140004a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a4a  jmp     short loc_140004A7C
0x140004a4c  mov     ebp, [rbx+8]
0x140004a4f  lea     rax, [rsp+278h+Buffer]
0x140004a54  mov     [rsp+278h+Arguments], r15; Arguments
0x140004a59  mov     r8d, ebp; dwMessageId
0x140004a5c  mov     [rsp+278h+nSize], 100h; nSize
0x140004a64  mov     r9d, 400h; dwLanguageId
0x140004a6a  xor     edx, edx; lpSource
0x140004a6c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004a71  mov     ecx, 1200h; dwFlags
0x140004a76  call    cs:__imp_FormatMessageW
0x140004a7c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140004a80  lea     rsi, [r14+rsi*2]
0x140004a84  mov     rax, [rbx+88h]
0x140004a8b  mov     rdx, rsi; unsigned __int16 *
0x140004a8e  mov     rcx, [rbx+80h]
0x140004a95  test    r9, r9
0x140004a98  jz      short loc_140004ABC
0x140004a9a  mov     [rsp+278h+Arguments], rax
0x140004a9f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004aa6  mov     eax, [rbx+40h]
0x140004aa9  mov     qword ptr [rsp+278h+nSize], rcx
0x140004aae  mov     rcx, r14; this
0x140004ab1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004ab5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004aba  jmp     short loc_140004AD3
0x140004abc  mov     r9, rcx; unsigned __int16 *
0x140004abf  mov     [rsp+278h+lpBuffer], rax
0x140004ac4  mov     rcx, r14; this
0x140004ac7  lea     r8, aHsP; "%hs!%p: "
0x140004ace  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004ad3  mov     r9, [rbx+90h]; unsigned __int16 *
0x140004ada  mov     r14, rax
0x140004add  test    r9, r9
0x140004ae0  jz      short loc_140004AF7
0x140004ae2  lea     r8, aCallerP; "(caller: %p) "
0x140004ae9  mov     rdx, rsi; unsigned __int16 *
0x140004aec  mov     rcx, rax; this
0x140004aef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004af4  mov     r14, rax
0x140004af7  call    cs:__imp_GetCurrentThreadId
0x140004afd  lea     rcx, [rsp+278h+Buffer]
0x140004b02  mov     r9, rdi; unsigned __int16 *
0x140004b05  mov     [rsp+278h+var_240], rcx
0x140004b0a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004b11  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004b15  mov     rdx, rsi; unsigned __int16 *
0x140004b18  mov     [rsp+278h+nSize], eax
0x140004b1c  mov     rcx, r14; this
0x140004b1f  mov     eax, [rbx+44h]
0x140004b22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004b26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b2b  cmp     [rbx+18h], r15
0x140004b2f  jnz     short loc_140004B41
0x140004b31  cmp     [rbx+48h], r15
0x140004b35  jnz     short loc_140004B41
0x140004b37  cmp     [rbx+30h], r15
0x140004b3b  jz      loc_140004BD1
0x140004b41  lea     r8, asc_14000E080; "    "
0x140004b48  mov     rdx, rsi; unsigned __int16 *
0x140004b4b  mov     rcx, rax; this
0x140004b4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b53  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004b57  test    r9, r9
0x140004b5a  jz      short loc_140004B6E
0x140004b5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004b63  mov     rdx, rsi; unsigned __int16 *
0x140004b66  mov     rcx, rax; this
0x140004b69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140004b72  test    r9, r9
0x140004b75  jz      short loc_140004B89
0x140004b77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140004b7e  mov     rdx, rsi; unsigned __int16 *
0x140004b81  mov     rcx, rax; this
0x140004b84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b89  mov     rcx, [rbx+28h]
0x140004b8d  mov     rdx, rsi; unsigned __int16 *
0x140004b90  mov     r9, [rbx+30h]; unsigned __int16 *
0x140004b94  test    rcx, rcx
0x140004b97  jz      short loc_140004BAF
0x140004b99  mov     [rsp+278h+lpBuffer], rcx
0x140004b9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004ba5  mov     rcx, rax; this
0x140004ba8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004bad  jmp     short loc_140004BD1
0x140004baf  mov     rcx, rax; this
0x140004bb2  test    r9, r9
0x140004bb5  jz      short loc_140004BC5
0x140004bb7  lea     r8, aHs; "[%hs]\n"
0x140004bbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004bc3  jmp     short loc_140004BD1
0x140004bc5  lea     r8, asc_14000E0F8; "\n"
0x140004bcc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004bd1  xor     eax, eax
0x140004bd3  mov     rcx, [rsp+278h+var_38]
0x140004bdb  xor     rcx, rsp; StackCookie
0x140004bde  call    __security_check_cookie
0x140004be3  mov     rbx, [rsp+278h+arg_18]
0x140004beb  add     rsp, 250h
0x140004bf2  pop     r15
0x140004bf4  pop     r14
0x140004bf6  pop     rdi
0x140004bf7  pop     rsi
0x140004bf8  pop     rbp
0x140004bf9  retn
```
