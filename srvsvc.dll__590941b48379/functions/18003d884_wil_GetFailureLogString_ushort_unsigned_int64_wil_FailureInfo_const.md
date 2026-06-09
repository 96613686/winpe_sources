# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003d884`
- end: `0x18003db3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18003bfdc`
- `0x18003c244`
- `0x18003e4d4`

## callees

- `0x18001deb0`
- `0x18001e80c`
- `0x18003d884`
- `0x18003e7d4`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003da37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003da37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003d9b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003d9b6`

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
          v8 = (const char *)&word_180054B46;
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
0x18003d884  mov     [rsp+arg_18], rbx
0x18003d889  push    rbp
0x18003d88a  push    rsi
0x18003d88b  push    rdi
0x18003d88c  push    r14
0x18003d88e  push    r15
0x18003d890  sub     rsp, 250h
0x18003d897  mov     rax, cs:__security_cookie
0x18003d89e  xor     rax, rsp
0x18003d8a1  mov     [rsp+278h+var_38], rax
0x18003d8a9  xor     r15d, r15d
0x18003d8ac  mov     rbx, r8
0x18003d8af  mov     rsi, rdx
0x18003d8b2  mov     r14, rcx
0x18003d8b5  test    rdx, rdx
0x18003d8b8  jz      loc_18003DB11
0x18003d8be  test    rcx, rcx
0x18003d8c1  jz      loc_18003DB11
0x18003d8c7  mov     rax, cs:g_pfnResultLoggingCallback
0x18003d8ce  mov     [rcx], r15w
0x18003d8d2  test    rax, rax
0x18003d8d5  jz      short loc_18003D8F8
0x18003d8d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003d8de  jz      short loc_18003D8F8
0x18003d8e0  mov     r8, rdx
0x18003d8e3  mov     rdx, rcx
0x18003d8e6  mov     rcx, rbx
0x18003d8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8ee  cmp     [r14], r15w
0x18003d8f2  jnz     loc_18003DB11
0x18003d8f8  mov     ecx, [rbx]
0x18003d8fa  mov     bpl, 8
0x18003d8fd  test    ecx, ecx
0x18003d8ff  jz      short loc_18003D94A
0x18003d901  sub     ecx, 1
0x18003d904  jz      short loc_18003D932
0x18003d906  sub     ecx, 1
0x18003d909  jz      short loc_18003D922
0x18003d90b  cmp     ecx, 1
0x18003d90e  jz      short loc_18003D919
0x18003d910  lea     rdi, word_180054B46
0x18003d917  jmp     short loc_18003D951
0x18003d919  lea     rdi, aFailfast; "FailFast"
0x18003d920  jmp     short loc_18003D951
0x18003d922  lea     rax, aLoghr; "LogHr"
0x18003d929  lea     rdi, aLognt; "LogNt"
0x18003d930  jmp     short loc_18003D940
0x18003d932  lea     rax, aReturnhr; "ReturnHr"
0x18003d939  lea     rdi, aReturnnt; "ReturnNt"
0x18003d940  test    [rbx+4], bpl
0x18003d944  cmovz   rdi, rax
0x18003d948  jmp     short loc_18003D951
0x18003d94a  lea     rdi, aException; "Exception"
0x18003d951  xor     edx, edx; Val
0x18003d953  lea     rcx, [rsp+278h+Buffer]; void *
0x18003d958  mov     r8d, 200h; Size
0x18003d95e  call    memset_0
0x18003d963  test    [rbx+4], bpl
0x18003d967  jz      short loc_18003D98C
0x18003d969  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003d970  mov     ebp, [rbx+0Ch]
0x18003d973  test    rax, rax
0x18003d976  jz      short loc_18003D9BC
0x18003d978  mov     r8d, 100h
0x18003d97e  lea     rdx, [rsp+278h+Buffer]
0x18003d983  mov     ecx, ebp
0x18003d985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d98a  jmp     short loc_18003D9BC
0x18003d98c  mov     ebp, [rbx+8]
0x18003d98f  lea     rax, [rsp+278h+Buffer]
0x18003d994  mov     [rsp+278h+Arguments], r15; Arguments
0x18003d999  mov     r8d, ebp; dwMessageId
0x18003d99c  mov     [rsp+278h+nSize], 100h; nSize
0x18003d9a4  mov     r9d, 400h; dwLanguageId
0x18003d9aa  xor     edx, edx; lpSource
0x18003d9ac  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003d9b1  mov     ecx, 1200h; dwFlags
0x18003d9b6  call    cs:__imp_FormatMessageW
0x18003d9bc  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003d9c0  lea     rsi, [r14+rsi*2]
0x18003d9c4  mov     rax, [rbx+88h]
0x18003d9cb  mov     rdx, rsi; unsigned __int16 *
0x18003d9ce  mov     rcx, [rbx+80h]
0x18003d9d5  test    r9, r9
0x18003d9d8  jz      short loc_18003D9FC
0x18003d9da  mov     [rsp+278h+Arguments], rax
0x18003d9df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003d9e6  mov     eax, [rbx+40h]
0x18003d9e9  mov     qword ptr [rsp+278h+nSize], rcx
0x18003d9ee  mov     rcx, r14; this
0x18003d9f1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003d9f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003d9fa  jmp     short loc_18003DA13
0x18003d9fc  mov     r9, rcx; unsigned __int16 *
0x18003d9ff  mov     [rsp+278h+lpBuffer], rax
0x18003da04  mov     rcx, r14; this
0x18003da07  lea     r8, aHsP; "%hs!%p: "
0x18003da0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003da13  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003da1a  mov     r14, rax
0x18003da1d  test    r9, r9
0x18003da20  jz      short loc_18003DA37
0x18003da22  lea     r8, aCallerP; "(caller: %p) "
0x18003da29  mov     rdx, rsi; unsigned __int16 *
0x18003da2c  mov     rcx, rax; this
0x18003da2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003da34  mov     r14, rax
0x18003da37  call    cs:__imp_GetCurrentThreadId
0x18003da3d  lea     rcx, [rsp+278h+Buffer]
0x18003da42  mov     r9, rdi; unsigned __int16 *
0x18003da45  mov     [rsp+278h+var_240], rcx
0x18003da4a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003da51  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003da55  mov     rdx, rsi; unsigned __int16 *
0x18003da58  mov     [rsp+278h+nSize], eax
0x18003da5c  mov     rcx, r14; this
0x18003da5f  mov     eax, [rbx+44h]
0x18003da62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003da66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003da6b  cmp     [rbx+18h], r15
0x18003da6f  jnz     short loc_18003DA81
0x18003da71  cmp     [rbx+48h], r15
0x18003da75  jnz     short loc_18003DA81
0x18003da77  cmp     [rbx+30h], r15
0x18003da7b  jz      loc_18003DB11
0x18003da81  lea     r8, asc_180054C90; "    "
0x18003da88  mov     rdx, rsi; unsigned __int16 *
0x18003da8b  mov     rcx, rax; this
0x18003da8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003da93  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003da97  test    r9, r9
0x18003da9a  jz      short loc_18003DAAE
0x18003da9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003daa3  mov     rdx, rsi; unsigned __int16 *
0x18003daa6  mov     rcx, rax; this
0x18003daa9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003daae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003dab2  test    r9, r9
0x18003dab5  jz      short loc_18003DAC9
0x18003dab7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003dabe  mov     rdx, rsi; unsigned __int16 *
0x18003dac1  mov     rcx, rax; this
0x18003dac4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003dac9  mov     rcx, [rbx+28h]
0x18003dacd  mov     rdx, rsi; unsigned __int16 *
0x18003dad0  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003dad4  test    rcx, rcx
0x18003dad7  jz      short loc_18003DAEF
0x18003dad9  mov     [rsp+278h+lpBuffer], rcx
0x18003dade  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003dae5  mov     rcx, rax; this
0x18003dae8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003daed  jmp     short loc_18003DB11
0x18003daef  mov     rcx, rax; this
0x18003daf2  test    r9, r9
0x18003daf5  jz      short loc_18003DB05
0x18003daf7  lea     r8, aHs; "[%hs]\n"
0x18003dafe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003db03  jmp     short loc_18003DB11
0x18003db05  lea     r8, asc_1800547EC; "\n"
0x18003db0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003db11  xor     eax, eax
0x18003db13  mov     rcx, [rsp+278h+var_38]
0x18003db1b  xor     rcx, rsp; StackCookie
0x18003db1e  call    __security_check_cookie
0x18003db23  mov     rbx, [rsp+278h+arg_18]
0x18003db2b  add     rsp, 250h
0x18003db32  pop     r15
0x18003db34  pop     r14
0x18003db36  pop     rdi
0x18003db37  pop     rsi
0x18003db38  pop     rbp
0x18003db39  retn
```
