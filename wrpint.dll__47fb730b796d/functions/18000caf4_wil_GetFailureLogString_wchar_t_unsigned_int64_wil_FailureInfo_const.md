# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000caf4`
- end: `0x18000cdaa`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000aa34`
- `0x18000ac9c`
- `0x18000d470`

## callees

- `0x18000caf4`
- `0x18000d770`
- `0x18001b77a`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cca7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cc26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cc26`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, wchar_t *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const wchar_t *v11; // r9
  wchar_t *v12; // rsi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const wchar_t *v15; // r9
  wil::details *v16; // r14
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !this )
    return 0;
  v7 = (void (__fastcall *)(__int64, wil *, wchar_t *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
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
          v8 = (const char *)&qword_180023000;
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
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const wchar_t **)(a3 + 128), v13);
  }
  v15 = *(const wchar_t **)(a3 + 144);
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
                          (const wchar_t *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x18000caf4  mov     [rsp+arg_18], rbx
0x18000caf9  push    rbp
0x18000cafa  push    rsi
0x18000cafb  push    rdi
0x18000cafc  push    r14
0x18000cafe  push    r15
0x18000cb00  sub     rsp, 250h
0x18000cb07  mov     rax, cs:__security_cookie
0x18000cb0e  xor     rax, rsp
0x18000cb11  mov     [rsp+278h+var_38], rax
0x18000cb19  xor     r15d, r15d
0x18000cb1c  mov     rbx, r8
0x18000cb1f  mov     rsi, rdx
0x18000cb22  mov     r14, rcx
0x18000cb25  test    rdx, rdx
0x18000cb28  jz      loc_18000CD81
0x18000cb2e  test    rcx, rcx
0x18000cb31  jz      loc_18000CD81
0x18000cb37  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cb3e  mov     [rcx], r15w
0x18000cb42  test    rax, rax
0x18000cb45  jz      short loc_18000CB68
0x18000cb47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cb4e  jz      short loc_18000CB68
0x18000cb50  mov     r8, rdx
0x18000cb53  mov     rdx, rcx
0x18000cb56  mov     rcx, rbx
0x18000cb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb5e  cmp     [r14], r15w
0x18000cb62  jnz     loc_18000CD81
0x18000cb68  mov     ecx, [rbx]
0x18000cb6a  mov     bpl, 8
0x18000cb6d  test    ecx, ecx
0x18000cb6f  jz      short loc_18000CBBA
0x18000cb71  sub     ecx, 1
0x18000cb74  jz      short loc_18000CBA2
0x18000cb76  sub     ecx, 1
0x18000cb79  jz      short loc_18000CB92
0x18000cb7b  cmp     ecx, 1
0x18000cb7e  jz      short loc_18000CB89
0x18000cb80  lea     rdi, qword_180023000
0x18000cb87  jmp     short loc_18000CBC1
0x18000cb89  lea     rdi, aFailfast; "FailFast"
0x18000cb90  jmp     short loc_18000CBC1
0x18000cb92  lea     rax, aLoghr; "LogHr"
0x18000cb99  lea     rdi, aLognt; "LogNt"
0x18000cba0  jmp     short loc_18000CBB0
0x18000cba2  lea     rax, aReturnhr; "ReturnHr"
0x18000cba9  lea     rdi, aReturnnt; "ReturnNt"
0x18000cbb0  test    [rbx+4], bpl
0x18000cbb4  cmovz   rdi, rax
0x18000cbb8  jmp     short loc_18000CBC1
0x18000cbba  lea     rdi, aException; "Exception"
0x18000cbc1  xor     edx, edx; Val
0x18000cbc3  lea     rcx, [rsp+278h+Buffer]; void *
0x18000cbc8  mov     r8d, 200h; Size
0x18000cbce  call    memset_0
0x18000cbd3  test    [rbx+4], bpl
0x18000cbd7  jz      short loc_18000CBFC
0x18000cbd9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18000cbe0  mov     ebp, [rbx+0Ch]
0x18000cbe3  test    rax, rax
0x18000cbe6  jz      short loc_18000CC2C
0x18000cbe8  mov     r8d, 100h
0x18000cbee  lea     rdx, [rsp+278h+Buffer]
0x18000cbf3  mov     ecx, ebp
0x18000cbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbfa  jmp     short loc_18000CC2C
0x18000cbfc  mov     ebp, [rbx+8]
0x18000cbff  lea     rax, [rsp+278h+Buffer]
0x18000cc04  mov     [rsp+278h+Arguments], r15; Arguments
0x18000cc09  mov     r8d, ebp; dwMessageId
0x18000cc0c  mov     [rsp+278h+nSize], 100h; nSize
0x18000cc14  mov     r9d, 400h; dwLanguageId
0x18000cc1a  xor     edx, edx; lpSource
0x18000cc1c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000cc21  mov     ecx, 1200h; dwFlags
0x18000cc26  call    cs:__imp_FormatMessageW
0x18000cc2c  mov     r9, [rbx+38h]; wchar_t *
0x18000cc30  lea     rsi, [r14+rsi*2]
0x18000cc34  mov     rax, [rbx+88h]
0x18000cc3b  mov     rdx, rsi; wchar_t *
0x18000cc3e  mov     rcx, [rbx+80h]
0x18000cc45  test    r9, r9
0x18000cc48  jz      short loc_18000CC6C
0x18000cc4a  mov     [rsp+278h+Arguments], rax
0x18000cc4f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000cc56  mov     eax, [rbx+40h]
0x18000cc59  mov     qword ptr [rsp+278h+nSize], rcx
0x18000cc5e  mov     rcx, r14; this
0x18000cc61  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000cc65  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cc6a  jmp     short loc_18000CC83
0x18000cc6c  mov     r9, rcx; wchar_t *
0x18000cc6f  mov     [rsp+278h+lpBuffer], rax
0x18000cc74  mov     rcx, r14; this
0x18000cc77  lea     r8, aHsP; "%hs!%p: "
0x18000cc7e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cc83  mov     r9, [rbx+90h]; wchar_t *
0x18000cc8a  mov     r14, rax
0x18000cc8d  test    r9, r9
0x18000cc90  jz      short loc_18000CCA7
0x18000cc92  lea     r8, aCallerP; "(caller: %p) "
0x18000cc99  mov     rdx, rsi; wchar_t *
0x18000cc9c  mov     rcx, rax; this
0x18000cc9f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cca4  mov     r14, rax
0x18000cca7  call    cs:__imp_GetCurrentThreadId
0x18000ccad  lea     rcx, [rsp+278h+Buffer]
0x18000ccb2  mov     r9, rdi; wchar_t *
0x18000ccb5  mov     [rsp+278h+var_240], rcx
0x18000ccba  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000ccc1  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000ccc5  mov     rdx, rsi; wchar_t *
0x18000ccc8  mov     [rsp+278h+nSize], eax
0x18000cccc  mov     rcx, r14; this
0x18000cccf  mov     eax, [rbx+44h]
0x18000ccd2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ccd6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000ccdb  cmp     [rbx+18h], r15
0x18000ccdf  jnz     short loc_18000CCF1
0x18000cce1  cmp     [rbx+48h], r15
0x18000cce5  jnz     short loc_18000CCF1
0x18000cce7  cmp     [rbx+30h], r15
0x18000cceb  jz      loc_18000CD81
0x18000ccf1  lea     r8, asc_1800230F0; "    "
0x18000ccf8  mov     rdx, rsi; wchar_t *
0x18000ccfb  mov     rcx, rax; this
0x18000ccfe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cd03  mov     r9, [rbx+18h]; wchar_t *
0x18000cd07  test    r9, r9
0x18000cd0a  jz      short loc_18000CD1E
0x18000cd0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000cd13  mov     rdx, rsi; wchar_t *
0x18000cd16  mov     rcx, rax; this
0x18000cd19  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cd1e  mov     r9, [rbx+48h]; wchar_t *
0x18000cd22  test    r9, r9
0x18000cd25  jz      short loc_18000CD39
0x18000cd27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000cd2e  mov     rdx, rsi; wchar_t *
0x18000cd31  mov     rcx, rax; this
0x18000cd34  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cd39  mov     rcx, [rbx+28h]
0x18000cd3d  mov     rdx, rsi; wchar_t *
0x18000cd40  mov     r9, [rbx+30h]; wchar_t *
0x18000cd44  test    rcx, rcx
0x18000cd47  jz      short loc_18000CD5F
0x18000cd49  mov     [rsp+278h+lpBuffer], rcx
0x18000cd4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000cd55  mov     rcx, rax; this
0x18000cd58  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cd5d  jmp     short loc_18000CD81
0x18000cd5f  mov     rcx, rax; this
0x18000cd62  test    r9, r9
0x18000cd65  jz      short loc_18000CD75
0x18000cd67  lea     r8, aHs; "[%hs]\n"
0x18000cd6e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cd73  jmp     short loc_18000CD81
0x18000cd75  lea     r8, asc_180023168; "\n"
0x18000cd7c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000cd81  xor     eax, eax
0x18000cd83  mov     rcx, [rsp+278h+var_38]
0x18000cd8b  xor     rcx, rsp; StackCookie
0x18000cd8e  call    __security_check_cookie
0x18000cd93  mov     rbx, [rsp+278h+arg_18]
0x18000cd9b  add     rsp, 250h
0x18000cda2  pop     r15
0x18000cda4  pop     r14
0x18000cda6  pop     rdi
0x18000cda7  pop     rsi
0x18000cda8  pop     rbp
0x18000cda9  retn
```
