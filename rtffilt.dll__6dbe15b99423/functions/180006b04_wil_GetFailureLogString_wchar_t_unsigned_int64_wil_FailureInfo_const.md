# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006b04`
- end: `0x180006dba`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003114`
- `0x180003394`
- `0x180003648`
- `0x18000776c`
- `0x18000ca70`
- `0x180019aea`
- `0x180019c1e`
- `0x180019d87`
- `0x18001a1cd`

## callees

- `0x180001e40`
- `0x1800028b4`
- `0x180006b04`
- `0x180007a6c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cb7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006c36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006c36`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
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
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&byte_18001CFD0;
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180006b04  mov     [rsp+arg_18], rbx
0x180006b09  push    rbp
0x180006b0a  push    rsi
0x180006b0b  push    rdi
0x180006b0c  push    r14
0x180006b0e  push    r15
0x180006b10  sub     rsp, 250h
0x180006b17  mov     rax, cs:__security_cookie
0x180006b1e  xor     rax, rsp
0x180006b21  mov     [rsp+278h+var_38], rax
0x180006b29  mov     rbx, r8
0x180006b2c  mov     rsi, rdx
0x180006b2f  mov     r14, rcx
0x180006b32  xor     r15d, r15d
0x180006b35  test    rdx, rdx
0x180006b38  jz      loc_180006D91
0x180006b3e  test    rcx, rcx
0x180006b41  jz      loc_180006D91
0x180006b47  mov     [rcx], r15w
0x180006b4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b52  test    rax, rax
0x180006b55  jz      short loc_180006B78
0x180006b57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006b5e  jz      short loc_180006B78
0x180006b60  mov     r8, rdx
0x180006b63  mov     rdx, rcx
0x180006b66  mov     rcx, rbx
0x180006b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b6e  cmp     [r14], r15w
0x180006b72  jnz     loc_180006D91
0x180006b78  mov     ecx, [rbx]
0x180006b7a  mov     bpl, 8
0x180006b7d  test    ecx, ecx
0x180006b7f  jz      short loc_180006BCA
0x180006b81  sub     ecx, 1
0x180006b84  jz      short loc_180006BB2
0x180006b86  sub     ecx, 1
0x180006b89  jz      short loc_180006BA2
0x180006b8b  cmp     ecx, 1
0x180006b8e  jz      short loc_180006B99
0x180006b90  lea     rdi, byte_18001CFD0
0x180006b97  jmp     short loc_180006BD1
0x180006b99  lea     rdi, aFailfast; "FailFast"
0x180006ba0  jmp     short loc_180006BD1
0x180006ba2  lea     rax, aLoghr; "LogHr"
0x180006ba9  lea     rdi, aLognt; "LogNt"
0x180006bb0  jmp     short loc_180006BC0
0x180006bb2  lea     rax, aReturnhr; "ReturnHr"
0x180006bb9  lea     rdi, aReturnnt; "ReturnNt"
0x180006bc0  test    [rbx+4], bpl
0x180006bc4  cmovz   rdi, rax
0x180006bc8  jmp     short loc_180006BD1
0x180006bca  lea     rdi, aException; "Exception"
0x180006bd1  xor     edx, edx; Val
0x180006bd3  mov     r8d, 200h; Size
0x180006bd9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006bde  call    memset_0
0x180006be3  test    [rbx+4], bpl
0x180006be7  jz      short loc_180006C0C
0x180006be9  mov     ebp, [rbx+0Ch]
0x180006bec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180006bf3  test    rax, rax
0x180006bf6  jz      short loc_180006C3C
0x180006bf8  mov     r8d, 100h
0x180006bfe  lea     rdx, [rsp+278h+Buffer]
0x180006c03  mov     ecx, ebp
0x180006c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c0a  jmp     short loc_180006C3C
0x180006c0c  mov     ebp, [rbx+8]
0x180006c0f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006c14  mov     [rsp+278h+nSize], 100h; nSize
0x180006c1c  lea     rax, [rsp+278h+Buffer]
0x180006c21  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006c26  mov     r9d, 400h; dwLanguageId
0x180006c2c  mov     r8d, ebp; dwMessageId
0x180006c2f  xor     edx, edx; lpSource
0x180006c31  mov     ecx, 1200h; dwFlags
0x180006c36  call    cs:__imp_FormatMessageW
0x180006c3c  lea     rsi, [r14+rsi*2]
0x180006c40  mov     r9, [rbx+38h]; wchar_t *
0x180006c44  mov     rax, [rbx+88h]
0x180006c4b  mov     rcx, [rbx+80h]
0x180006c52  mov     rdx, rsi; wchar_t *
0x180006c55  test    r9, r9
0x180006c58  jz      short loc_180006C7C
0x180006c5a  mov     [rsp+278h+Arguments], rax
0x180006c5f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006c64  mov     eax, [rbx+40h]
0x180006c67  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006c6b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006c72  mov     rcx, r14; this
0x180006c75  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006c7a  jmp     short loc_180006C93
0x180006c7c  mov     [rsp+278h+lpBuffer], rax
0x180006c81  mov     r9, rcx; wchar_t *
0x180006c84  lea     r8, aHsP; "%hs!%p: "
0x180006c8b  mov     rcx, r14; this
0x180006c8e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006c93  mov     r14, rax
0x180006c96  mov     r9, [rbx+90h]; wchar_t *
0x180006c9d  test    r9, r9
0x180006ca0  jz      short loc_180006CB7
0x180006ca2  lea     r8, aCallerP; "(caller: %p) "
0x180006ca9  mov     rdx, rsi; wchar_t *
0x180006cac  mov     rcx, rax; this
0x180006caf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006cb4  mov     r14, rax
0x180006cb7  call    cs:__imp_GetCurrentThreadId
0x180006cbd  lea     rcx, [rsp+278h+Buffer]
0x180006cc2  mov     [rsp+278h+var_240], rcx
0x180006cc7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006ccb  mov     [rsp+278h+nSize], eax
0x180006ccf  mov     eax, [rbx+44h]
0x180006cd2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006cd6  mov     r9, rdi; wchar_t *
0x180006cd9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006ce0  mov     rdx, rsi; wchar_t *
0x180006ce3  mov     rcx, r14; this
0x180006ce6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006ceb  cmp     [rbx+18h], r15
0x180006cef  jnz     short loc_180006D01
0x180006cf1  cmp     [rbx+48h], r15
0x180006cf5  jnz     short loc_180006D01
0x180006cf7  cmp     [rbx+30h], r15
0x180006cfb  jz      loc_180006D91
0x180006d01  lea     r8, asc_18001D0C0; "    "
0x180006d08  mov     rdx, rsi; wchar_t *
0x180006d0b  mov     rcx, rax; this
0x180006d0e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d13  mov     r9, [rbx+18h]; wchar_t *
0x180006d17  test    r9, r9
0x180006d1a  jz      short loc_180006D2E
0x180006d1c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006d23  mov     rdx, rsi; wchar_t *
0x180006d26  mov     rcx, rax; this
0x180006d29  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d2e  mov     r9, [rbx+48h]; wchar_t *
0x180006d32  test    r9, r9
0x180006d35  jz      short loc_180006D49
0x180006d37  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006d3e  mov     rdx, rsi; wchar_t *
0x180006d41  mov     rcx, rax; this
0x180006d44  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d49  mov     rcx, [rbx+28h]
0x180006d4d  mov     r9, [rbx+30h]; wchar_t *
0x180006d51  mov     rdx, rsi; wchar_t *
0x180006d54  test    rcx, rcx
0x180006d57  jz      short loc_180006D6F
0x180006d59  mov     [rsp+278h+lpBuffer], rcx
0x180006d5e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006d65  mov     rcx, rax; this
0x180006d68  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d6d  jmp     short loc_180006D91
0x180006d6f  mov     rcx, rax; this
0x180006d72  test    r9, r9
0x180006d75  jz      short loc_180006D85
0x180006d77  lea     r8, aHs; "[%hs]\n"
0x180006d7e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d83  jmp     short loc_180006D91
0x180006d85  lea     r8, asc_18001D138; "\n"
0x180006d8c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d91  xor     eax, eax
0x180006d93  mov     rcx, [rsp+278h+var_38]
0x180006d9b  xor     rcx, rsp; StackCookie
0x180006d9e  call    __security_check_cookie
0x180006da3  mov     rbx, [rsp+278h+arg_18]
0x180006dab  add     rsp, 250h
0x180006db2  pop     r15
0x180006db4  pop     r14
0x180006db6  pop     rdi
0x180006db7  pop     rsi
0x180006db8  pop     rbp
0x180006db9  retn
```
