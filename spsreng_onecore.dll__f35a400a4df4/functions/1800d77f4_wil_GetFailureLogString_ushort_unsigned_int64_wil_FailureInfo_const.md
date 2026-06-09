# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800d77f4`
- end: `0x1800d7aaa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800d69ec`
- `0x1800d8148`
- `0x1800d93b0`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x1800d77f4`
- `0x1800d8448`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d79a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d79a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d7926`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d7926`

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
          v7 = MultiByteStr;
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
0x1800d77f4  mov     [rsp+arg_18], rbx
0x1800d77f9  push    rbp
0x1800d77fa  push    rsi
0x1800d77fb  push    rdi
0x1800d77fc  push    r14
0x1800d77fe  push    r15
0x1800d7800  sub     rsp, 250h
0x1800d7807  mov     rax, cs:__security_cookie
0x1800d780e  xor     rax, rsp
0x1800d7811  mov     [rsp+278h+var_38], rax
0x1800d7819  mov     rbx, r8
0x1800d781c  mov     rsi, rdx
0x1800d781f  mov     r14, rcx
0x1800d7822  xor     r15d, r15d
0x1800d7825  test    rdx, rdx
0x1800d7828  jz      loc_1800D7A81
0x1800d782e  test    rcx, rcx
0x1800d7831  jz      loc_1800D7A81
0x1800d7837  mov     [rcx], r15w
0x1800d783b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800d7842  test    rax, rax
0x1800d7845  jz      short loc_1800D7868
0x1800d7847  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800d784e  jz      short loc_1800D7868
0x1800d7850  mov     r8, rdx
0x1800d7853  mov     rdx, rcx
0x1800d7856  mov     rcx, rbx
0x1800d7859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d785e  cmp     [r14], r15w
0x1800d7862  jnz     loc_1800D7A81
0x1800d7868  mov     ecx, [rbx]
0x1800d786a  mov     bpl, 8
0x1800d786d  test    ecx, ecx
0x1800d786f  jz      short loc_1800D78BA
0x1800d7871  sub     ecx, 1
0x1800d7874  jz      short loc_1800D78A2
0x1800d7876  sub     ecx, 1
0x1800d7879  jz      short loc_1800D7892
0x1800d787b  cmp     ecx, 1
0x1800d787e  jz      short loc_1800D7889
0x1800d7880  lea     rdi, MultiByteStr
0x1800d7887  jmp     short loc_1800D78C1
0x1800d7889  lea     rdi, aFailfast; "FailFast"
0x1800d7890  jmp     short loc_1800D78C1
0x1800d7892  lea     rax, aLoghr; "LogHr"
0x1800d7899  lea     rdi, aLognt; "LogNt"
0x1800d78a0  jmp     short loc_1800D78B0
0x1800d78a2  lea     rax, aReturnhr; "ReturnHr"
0x1800d78a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800d78b0  test    [rbx+4], bpl
0x1800d78b4  cmovz   rdi, rax
0x1800d78b8  jmp     short loc_1800D78C1
0x1800d78ba  lea     rdi, aException; "Exception"
0x1800d78c1  xor     edx, edx; Val
0x1800d78c3  mov     r8d, 200h; Size
0x1800d78c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800d78ce  call    memset_0
0x1800d78d3  test    [rbx+4], bpl
0x1800d78d7  jz      short loc_1800D78FC
0x1800d78d9  mov     ebp, [rbx+0Ch]
0x1800d78dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800d78e3  test    rax, rax
0x1800d78e6  jz      short loc_1800D792C
0x1800d78e8  mov     r8d, 100h
0x1800d78ee  lea     rdx, [rsp+278h+Buffer]
0x1800d78f3  mov     ecx, ebp
0x1800d78f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d78fa  jmp     short loc_1800D792C
0x1800d78fc  mov     ebp, [rbx+8]
0x1800d78ff  mov     [rsp+278h+Arguments], r15; Arguments
0x1800d7904  mov     [rsp+278h+nSize], 100h; nSize
0x1800d790c  lea     rax, [rsp+278h+Buffer]
0x1800d7911  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800d7916  mov     r9d, 400h; dwLanguageId
0x1800d791c  mov     r8d, ebp; dwMessageId
0x1800d791f  xor     edx, edx; lpSource
0x1800d7921  mov     ecx, 1200h; dwFlags
0x1800d7926  call    cs:__imp_FormatMessageW
0x1800d792c  lea     rsi, [r14+rsi*2]
0x1800d7930  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800d7934  mov     rax, [rbx+88h]
0x1800d793b  mov     rcx, [rbx+80h]
0x1800d7942  mov     rdx, rsi; unsigned __int16 *
0x1800d7945  test    r9, r9
0x1800d7948  jz      short loc_1800D796C
0x1800d794a  mov     [rsp+278h+Arguments], rax
0x1800d794f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800d7954  mov     eax, [rbx+40h]
0x1800d7957  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800d795b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800d7962  mov     rcx, r14; this
0x1800d7965  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d796a  jmp     short loc_1800D7983
0x1800d796c  mov     [rsp+278h+lpBuffer], rax
0x1800d7971  mov     r9, rcx; unsigned __int16 *
0x1800d7974  lea     r8, aHsP; "%hs!%p: "
0x1800d797b  mov     rcx, r14; this
0x1800d797e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d7983  mov     r14, rax
0x1800d7986  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800d798d  test    r9, r9
0x1800d7990  jz      short loc_1800D79A7
0x1800d7992  lea     r8, aCallerP; "(caller: %p) "
0x1800d7999  mov     rdx, rsi; unsigned __int16 *
0x1800d799c  mov     rcx, rax; this
0x1800d799f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d79a4  mov     r14, rax
0x1800d79a7  call    cs:__imp_GetCurrentThreadId
0x1800d79ad  lea     rcx, [rsp+278h+Buffer]
0x1800d79b2  mov     [rsp+278h+var_240], rcx
0x1800d79b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800d79bb  mov     [rsp+278h+nSize], eax
0x1800d79bf  mov     eax, [rbx+44h]
0x1800d79c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800d79c6  mov     r9, rdi; unsigned __int16 *
0x1800d79c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800d79d0  mov     rdx, rsi; unsigned __int16 *
0x1800d79d3  mov     rcx, r14; this
0x1800d79d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d79db  cmp     [rbx+18h], r15
0x1800d79df  jnz     short loc_1800D79F1
0x1800d79e1  cmp     [rbx+48h], r15
0x1800d79e5  jnz     short loc_1800D79F1
0x1800d79e7  cmp     [rbx+30h], r15
0x1800d79eb  jz      loc_1800D7A81
0x1800d79f1  lea     r8, asc_180113640; "    "
0x1800d79f8  mov     rdx, rsi; unsigned __int16 *
0x1800d79fb  mov     rcx, rax; this
0x1800d79fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d7a03  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800d7a07  test    r9, r9
0x1800d7a0a  jz      short loc_1800D7A1E
0x1800d7a0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800d7a13  mov     rdx, rsi; unsigned __int16 *
0x1800d7a16  mov     rcx, rax; this
0x1800d7a19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d7a1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800d7a22  test    r9, r9
0x1800d7a25  jz      short loc_1800D7A39
0x1800d7a27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800d7a2e  mov     rdx, rsi; unsigned __int16 *
0x1800d7a31  mov     rcx, rax; this
0x1800d7a34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d7a39  mov     rcx, [rbx+28h]
0x1800d7a3d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800d7a41  mov     rdx, rsi; unsigned __int16 *
0x1800d7a44  test    rcx, rcx
0x1800d7a47  jz      short loc_1800D7A5F
0x1800d7a49  mov     [rsp+278h+lpBuffer], rcx
0x1800d7a4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800d7a55  mov     rcx, rax; this
0x1800d7a58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d7a5d  jmp     short loc_1800D7A81
0x1800d7a5f  mov     rcx, rax; this
0x1800d7a62  test    r9, r9
0x1800d7a65  jz      short loc_1800D7A75
0x1800d7a67  lea     r8, aHs; "[%hs]\n"
0x1800d7a6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d7a73  jmp     short loc_1800D7A81
0x1800d7a75  lea     r8, asc_180112C7C; "\n"
0x1800d7a7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d7a81  xor     eax, eax
0x1800d7a83  mov     rcx, [rsp+278h+var_38]
0x1800d7a8b  xor     rcx, rsp; StackCookie
0x1800d7a8e  call    __security_check_cookie
0x1800d7a93  mov     rbx, [rsp+278h+arg_18]
0x1800d7a9b  add     rsp, 250h
0x1800d7aa2  pop     r15
0x1800d7aa4  pop     r14
0x1800d7aa6  pop     rdi
0x1800d7aa7  pop     rsi
0x1800d7aa8  pop     rbp
0x1800d7aa9  retn
```
