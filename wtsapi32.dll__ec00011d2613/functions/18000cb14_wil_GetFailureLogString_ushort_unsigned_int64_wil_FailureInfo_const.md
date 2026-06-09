# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000cb14`
- end: `0x18000cdca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d590`

## callees

- `0x18000cb14`
- `0x18000d88c`
- `0x18001558e`
- `0x1800155c0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cc46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cc46`

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
          v8 = (const char *)&qword_180018198;
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
0x18000cb14  mov     [rsp+arg_18], rbx
0x18000cb19  push    rbp
0x18000cb1a  push    rsi
0x18000cb1b  push    rdi
0x18000cb1c  push    r14
0x18000cb1e  push    r15
0x18000cb20  sub     rsp, 250h
0x18000cb27  mov     rax, cs:__security_cookie
0x18000cb2e  xor     rax, rsp
0x18000cb31  mov     [rsp+278h+var_38], rax
0x18000cb39  xor     r15d, r15d
0x18000cb3c  mov     rbx, r8
0x18000cb3f  mov     rsi, rdx
0x18000cb42  mov     r14, rcx
0x18000cb45  test    rdx, rdx
0x18000cb48  jz      loc_18000CDA1
0x18000cb4e  test    rcx, rcx
0x18000cb51  jz      loc_18000CDA1
0x18000cb57  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cb5e  mov     [rcx], r15w
0x18000cb62  test    rax, rax
0x18000cb65  jz      short loc_18000CB88
0x18000cb67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cb6e  jz      short loc_18000CB88
0x18000cb70  mov     r8, rdx
0x18000cb73  mov     rdx, rcx
0x18000cb76  mov     rcx, rbx
0x18000cb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7e  cmp     [r14], r15w
0x18000cb82  jnz     loc_18000CDA1
0x18000cb88  mov     ecx, [rbx]
0x18000cb8a  mov     bpl, 8
0x18000cb8d  test    ecx, ecx
0x18000cb8f  jz      short loc_18000CBDA
0x18000cb91  sub     ecx, 1
0x18000cb94  jz      short loc_18000CBC2
0x18000cb96  sub     ecx, 1
0x18000cb99  jz      short loc_18000CBB2
0x18000cb9b  cmp     ecx, 1
0x18000cb9e  jz      short loc_18000CBA9
0x18000cba0  lea     rdi, qword_180018198
0x18000cba7  jmp     short loc_18000CBE1
0x18000cba9  lea     rdi, aFailfast; "FailFast"
0x18000cbb0  jmp     short loc_18000CBE1
0x18000cbb2  lea     rax, aLoghr; "LogHr"
0x18000cbb9  lea     rdi, aLognt; "LogNt"
0x18000cbc0  jmp     short loc_18000CBD0
0x18000cbc2  lea     rax, aReturnhr; "ReturnHr"
0x18000cbc9  lea     rdi, aReturnnt; "ReturnNt"
0x18000cbd0  test    [rbx+4], bpl
0x18000cbd4  cmovz   rdi, rax
0x18000cbd8  jmp     short loc_18000CBE1
0x18000cbda  lea     rdi, aException; "Exception"
0x18000cbe1  xor     edx, edx; Val
0x18000cbe3  lea     rcx, [rsp+278h+Buffer]; void *
0x18000cbe8  mov     r8d, 200h; Size
0x18000cbee  call    memset_0
0x18000cbf3  test    [rbx+4], bpl
0x18000cbf7  jz      short loc_18000CC1C
0x18000cbf9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000cc00  mov     ebp, [rbx+0Ch]
0x18000cc03  test    rax, rax
0x18000cc06  jz      short loc_18000CC4C
0x18000cc08  mov     r8d, 100h
0x18000cc0e  lea     rdx, [rsp+278h+Buffer]
0x18000cc13  mov     ecx, ebp
0x18000cc15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc1a  jmp     short loc_18000CC4C
0x18000cc1c  mov     ebp, [rbx+8]
0x18000cc1f  lea     rax, [rsp+278h+Buffer]
0x18000cc24  mov     [rsp+278h+Arguments], r15; Arguments
0x18000cc29  mov     r8d, ebp; dwMessageId
0x18000cc2c  mov     [rsp+278h+nSize], 100h; nSize
0x18000cc34  mov     r9d, 400h; dwLanguageId
0x18000cc3a  xor     edx, edx; lpSource
0x18000cc3c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000cc41  mov     ecx, 1200h; dwFlags
0x18000cc46  call    cs:__imp_FormatMessageW
0x18000cc4c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000cc50  lea     rsi, [r14+rsi*2]
0x18000cc54  mov     rax, [rbx+88h]
0x18000cc5b  mov     rdx, rsi; unsigned __int16 *
0x18000cc5e  mov     rcx, [rbx+80h]
0x18000cc65  test    r9, r9
0x18000cc68  jz      short loc_18000CC8C
0x18000cc6a  mov     [rsp+278h+Arguments], rax
0x18000cc6f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000cc76  mov     eax, [rbx+40h]
0x18000cc79  mov     qword ptr [rsp+278h+nSize], rcx
0x18000cc7e  mov     rcx, r14; this
0x18000cc81  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000cc85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cc8a  jmp     short loc_18000CCA3
0x18000cc8c  mov     r9, rcx; unsigned __int16 *
0x18000cc8f  mov     [rsp+278h+lpBuffer], rax
0x18000cc94  mov     rcx, r14; this
0x18000cc97  lea     r8, aHsP; "%hs!%p: "
0x18000cc9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cca3  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000ccaa  mov     r14, rax
0x18000ccad  test    r9, r9
0x18000ccb0  jz      short loc_18000CCC7
0x18000ccb2  lea     r8, aCallerP; "(caller: %p) "
0x18000ccb9  mov     rdx, rsi; unsigned __int16 *
0x18000ccbc  mov     rcx, rax; this
0x18000ccbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ccc4  mov     r14, rax
0x18000ccc7  call    cs:__imp_GetCurrentThreadId
0x18000cccd  lea     rcx, [rsp+278h+Buffer]
0x18000ccd2  mov     r9, rdi; unsigned __int16 *
0x18000ccd5  mov     [rsp+278h+var_240], rcx
0x18000ccda  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000cce1  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000cce5  mov     rdx, rsi; unsigned __int16 *
0x18000cce8  mov     [rsp+278h+nSize], eax
0x18000ccec  mov     rcx, r14; this
0x18000ccef  mov     eax, [rbx+44h]
0x18000ccf2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ccf6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ccfb  cmp     [rbx+18h], r15
0x18000ccff  jnz     short loc_18000CD11
0x18000cd01  cmp     [rbx+48h], r15
0x18000cd05  jnz     short loc_18000CD11
0x18000cd07  cmp     [rbx+30h], r15
0x18000cd0b  jz      loc_18000CDA1
0x18000cd11  lea     r8, asc_180018288; "    "
0x18000cd18  mov     rdx, rsi; unsigned __int16 *
0x18000cd1b  mov     rcx, rax; this
0x18000cd1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cd23  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000cd27  test    r9, r9
0x18000cd2a  jz      short loc_18000CD3E
0x18000cd2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000cd33  mov     rdx, rsi; unsigned __int16 *
0x18000cd36  mov     rcx, rax; this
0x18000cd39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cd3e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000cd42  test    r9, r9
0x18000cd45  jz      short loc_18000CD59
0x18000cd47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000cd4e  mov     rdx, rsi; unsigned __int16 *
0x18000cd51  mov     rcx, rax; this
0x18000cd54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cd59  mov     rcx, [rbx+28h]
0x18000cd5d  mov     rdx, rsi; unsigned __int16 *
0x18000cd60  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000cd64  test    rcx, rcx
0x18000cd67  jz      short loc_18000CD7F
0x18000cd69  mov     [rsp+278h+lpBuffer], rcx
0x18000cd6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000cd75  mov     rcx, rax; this
0x18000cd78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cd7d  jmp     short loc_18000CDA1
0x18000cd7f  mov     rcx, rax; this
0x18000cd82  test    r9, r9
0x18000cd85  jz      short loc_18000CD95
0x18000cd87  lea     r8, aHs; "[%hs]\n"
0x18000cd8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cd93  jmp     short loc_18000CDA1
0x18000cd95  lea     r8, asc_180018300; "\n"
0x18000cd9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cda1  xor     eax, eax
0x18000cda3  mov     rcx, [rsp+278h+var_38]
0x18000cdab  xor     rcx, rsp; StackCookie
0x18000cdae  call    __security_check_cookie
0x18000cdb3  mov     rbx, [rsp+278h+arg_18]
0x18000cdbb  add     rsp, 250h
0x18000cdc2  pop     r15
0x18000cdc4  pop     r14
0x18000cdc6  pop     rdi
0x18000cdc7  pop     rsi
0x18000cdc8  pop     rbp
0x18000cdc9  retn
```
