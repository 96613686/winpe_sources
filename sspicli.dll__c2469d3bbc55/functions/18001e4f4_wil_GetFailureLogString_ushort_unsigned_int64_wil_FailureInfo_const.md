# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001e4f4`
- end: `0x18001e7aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016380`

## callees

- `0x180016df0`
- `0x18001e4f4`
- `0x18002205f`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e6a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e6a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e626`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e626`

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
          v8 = (const char *)&dword_180033314;
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
0x18001e4f4  mov     [rsp+arg_18], rbx
0x18001e4f9  push    rbp
0x18001e4fa  push    rsi
0x18001e4fb  push    rdi
0x18001e4fc  push    r14
0x18001e4fe  push    r15
0x18001e500  sub     rsp, 250h
0x18001e507  mov     rax, cs:__security_cookie
0x18001e50e  xor     rax, rsp
0x18001e511  mov     [rsp+278h+var_38], rax
0x18001e519  xor     r15d, r15d
0x18001e51c  mov     rbx, r8
0x18001e51f  mov     rsi, rdx
0x18001e522  mov     r14, rcx
0x18001e525  test    rdx, rdx
0x18001e528  jz      loc_18001E781
0x18001e52e  test    rcx, rcx
0x18001e531  jz      loc_18001E781
0x18001e537  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e53e  mov     [rcx], r15w
0x18001e542  test    rax, rax
0x18001e545  jz      short loc_18001E568
0x18001e547  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001e54e  jz      short loc_18001E568
0x18001e550  mov     r8, rdx
0x18001e553  mov     rdx, rcx
0x18001e556  mov     rcx, rbx
0x18001e559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e55e  cmp     [r14], r15w
0x18001e562  jnz     loc_18001E781
0x18001e568  mov     ecx, [rbx]
0x18001e56a  mov     bpl, 8
0x18001e56d  test    ecx, ecx
0x18001e56f  jz      short loc_18001E5BA
0x18001e571  sub     ecx, 1
0x18001e574  jz      short loc_18001E5A2
0x18001e576  sub     ecx, 1
0x18001e579  jz      short loc_18001E592
0x18001e57b  cmp     ecx, 1
0x18001e57e  jz      short loc_18001E589
0x18001e580  lea     rdi, dword_180033314
0x18001e587  jmp     short loc_18001E5C1
0x18001e589  lea     rdi, aFailfast; "FailFast"
0x18001e590  jmp     short loc_18001E5C1
0x18001e592  lea     rax, aLoghr; "LogHr"
0x18001e599  lea     rdi, aLognt; "LogNt"
0x18001e5a0  jmp     short loc_18001E5B0
0x18001e5a2  lea     rax, aReturnhr; "ReturnHr"
0x18001e5a9  lea     rdi, aReturnnt; "ReturnNt"
0x18001e5b0  test    [rbx+4], bpl
0x18001e5b4  cmovz   rdi, rax
0x18001e5b8  jmp     short loc_18001E5C1
0x18001e5ba  lea     rdi, aException; "Exception"
0x18001e5c1  xor     edx, edx; Val
0x18001e5c3  lea     rcx, [rsp+278h+Buffer]; void *
0x18001e5c8  mov     r8d, 200h; Size
0x18001e5ce  call    memset_0
0x18001e5d3  test    [rbx+4], bpl
0x18001e5d7  jz      short loc_18001E5FC
0x18001e5d9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001e5e0  mov     ebp, [rbx+0Ch]
0x18001e5e3  test    rax, rax
0x18001e5e6  jz      short loc_18001E62C
0x18001e5e8  mov     r8d, 100h
0x18001e5ee  lea     rdx, [rsp+278h+Buffer]
0x18001e5f3  mov     ecx, ebp
0x18001e5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5fa  jmp     short loc_18001E62C
0x18001e5fc  mov     ebp, [rbx+8]
0x18001e5ff  lea     rax, [rsp+278h+Buffer]
0x18001e604  mov     [rsp+278h+Arguments], r15; Arguments
0x18001e609  mov     r8d, ebp; dwMessageId
0x18001e60c  mov     [rsp+278h+nSize], 100h; nSize
0x18001e614  mov     r9d, 400h; dwLanguageId
0x18001e61a  xor     edx, edx; lpSource
0x18001e61c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001e621  mov     ecx, 1200h; dwFlags
0x18001e626  call    cs:__imp_FormatMessageW
0x18001e62c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001e630  lea     rsi, [r14+rsi*2]
0x18001e634  mov     rax, [rbx+88h]
0x18001e63b  mov     rdx, rsi; unsigned __int16 *
0x18001e63e  mov     rcx, [rbx+80h]
0x18001e645  test    r9, r9
0x18001e648  jz      short loc_18001E66C
0x18001e64a  mov     [rsp+278h+Arguments], rax
0x18001e64f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001e656  mov     eax, [rbx+40h]
0x18001e659  mov     qword ptr [rsp+278h+nSize], rcx
0x18001e65e  mov     rcx, r14; this
0x18001e661  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e665  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e66a  jmp     short loc_18001E683
0x18001e66c  mov     r9, rcx; unsigned __int16 *
0x18001e66f  mov     [rsp+278h+lpBuffer], rax
0x18001e674  mov     rcx, r14; this
0x18001e677  lea     r8, aHsP; "%hs!%p: "
0x18001e67e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e683  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001e68a  mov     r14, rax
0x18001e68d  test    r9, r9
0x18001e690  jz      short loc_18001E6A7
0x18001e692  lea     r8, aCallerP; "(caller: %p) "
0x18001e699  mov     rdx, rsi; unsigned __int16 *
0x18001e69c  mov     rcx, rax; this
0x18001e69f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e6a4  mov     r14, rax
0x18001e6a7  call    cs:__imp_GetCurrentThreadId
0x18001e6ad  lea     rcx, [rsp+278h+Buffer]
0x18001e6b2  mov     r9, rdi; unsigned __int16 *
0x18001e6b5  mov     [rsp+278h+var_240], rcx
0x18001e6ba  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001e6c1  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001e6c5  mov     rdx, rsi; unsigned __int16 *
0x18001e6c8  mov     [rsp+278h+nSize], eax
0x18001e6cc  mov     rcx, r14; this
0x18001e6cf  mov     eax, [rbx+44h]
0x18001e6d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e6d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e6db  cmp     [rbx+18h], r15
0x18001e6df  jnz     short loc_18001E6F1
0x18001e6e1  cmp     [rbx+48h], r15
0x18001e6e5  jnz     short loc_18001E6F1
0x18001e6e7  cmp     [rbx+30h], r15
0x18001e6eb  jz      loc_18001E781
0x18001e6f1  lea     r8, asc_180033400; "    "
0x18001e6f8  mov     rdx, rsi; unsigned __int16 *
0x18001e6fb  mov     rcx, rax; this
0x18001e6fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e703  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001e707  test    r9, r9
0x18001e70a  jz      short loc_18001E71E
0x18001e70c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001e713  mov     rdx, rsi; unsigned __int16 *
0x18001e716  mov     rcx, rax; this
0x18001e719  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e71e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001e722  test    r9, r9
0x18001e725  jz      short loc_18001E739
0x18001e727  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001e72e  mov     rdx, rsi; unsigned __int16 *
0x18001e731  mov     rcx, rax; this
0x18001e734  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e739  mov     rcx, [rbx+28h]
0x18001e73d  mov     rdx, rsi; unsigned __int16 *
0x18001e740  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001e744  test    rcx, rcx
0x18001e747  jz      short loc_18001E75F
0x18001e749  mov     [rsp+278h+lpBuffer], rcx
0x18001e74e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001e755  mov     rcx, rax; this
0x18001e758  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e75d  jmp     short loc_18001E781
0x18001e75f  mov     rcx, rax; this
0x18001e762  test    r9, r9
0x18001e765  jz      short loc_18001E775
0x18001e767  lea     r8, aHs; "[%hs]\n"
0x18001e76e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e773  jmp     short loc_18001E781
0x18001e775  lea     r8, asc_180033478; "\n"
0x18001e77c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e781  xor     eax, eax
0x18001e783  mov     rcx, [rsp+278h+var_38]
0x18001e78b  xor     rcx, rsp; StackCookie
0x18001e78e  call    __security_check_cookie
0x18001e793  mov     rbx, [rsp+278h+arg_18]
0x18001e79b  add     rsp, 250h
0x18001e7a2  pop     r15
0x18001e7a4  pop     r14
0x18001e7a6  pop     rdi
0x18001e7a7  pop     rsi
0x18001e7a8  pop     rbp
0x18001e7a9  retn
```
