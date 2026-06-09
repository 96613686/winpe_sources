# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180019614`
- end: `0x1800198d7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180017be4`
- `0x180017e5c`
- `0x18001a1f8`

## callees

- `0x180019614`
- `0x18001a50c`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800197cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800197cd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180019746`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180019746`

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
          v8 = (const char *)&word_18002881E;
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
0x180019614  mov     [rsp+arg_18], rbx
0x180019619  push    rbp
0x18001961a  push    rsi
0x18001961b  push    rdi
0x18001961c  push    r14
0x18001961e  push    r15
0x180019620  sub     rsp, 250h
0x180019627  mov     rax, cs:__security_cookie
0x18001962e  xor     rax, rsp
0x180019631  mov     [rsp+278h+var_38], rax
0x180019639  xor     r15d, r15d
0x18001963c  mov     rbx, r8
0x18001963f  mov     rsi, rdx
0x180019642  mov     r14, rcx
0x180019645  test    rdx, rdx
0x180019648  jz      loc_1800198AD
0x18001964e  test    rcx, rcx
0x180019651  jz      loc_1800198AD
0x180019657  mov     rax, cs:g_pfnResultLoggingCallback
0x18001965e  mov     [rcx], r15w
0x180019662  test    rax, rax
0x180019665  jz      short loc_180019688
0x180019667  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001966e  jz      short loc_180019688
0x180019670  mov     r8, rdx
0x180019673  mov     rdx, rcx
0x180019676  mov     rcx, rbx
0x180019679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001967e  cmp     [r14], r15w
0x180019682  jnz     loc_1800198AD
0x180019688  mov     ecx, [rbx]
0x18001968a  mov     bpl, 8
0x18001968d  test    ecx, ecx
0x18001968f  jz      short loc_1800196DA
0x180019691  sub     ecx, 1
0x180019694  jz      short loc_1800196C2
0x180019696  sub     ecx, 1
0x180019699  jz      short loc_1800196B2
0x18001969b  cmp     ecx, 1
0x18001969e  jz      short loc_1800196A9
0x1800196a0  lea     rdi, word_18002881E
0x1800196a7  jmp     short loc_1800196E1
0x1800196a9  lea     rdi, aFailfast; "FailFast"
0x1800196b0  jmp     short loc_1800196E1
0x1800196b2  lea     rax, aLoghr; "LogHr"
0x1800196b9  lea     rdi, aLognt; "LogNt"
0x1800196c0  jmp     short loc_1800196D0
0x1800196c2  lea     rax, aReturnhr; "ReturnHr"
0x1800196c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800196d0  test    [rbx+4], bpl
0x1800196d4  cmovz   rdi, rax
0x1800196d8  jmp     short loc_1800196E1
0x1800196da  lea     rdi, aException; "Exception"
0x1800196e1  xor     edx, edx; Val
0x1800196e3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800196e8  mov     r8d, 200h; Size
0x1800196ee  call    memset_0
0x1800196f3  test    [rbx+4], bpl
0x1800196f7  jz      short loc_18001971C
0x1800196f9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180019700  mov     ebp, [rbx+0Ch]
0x180019703  test    rax, rax
0x180019706  jz      short loc_180019752
0x180019708  mov     r8d, 100h
0x18001970e  lea     rdx, [rsp+278h+Buffer]
0x180019713  mov     ecx, ebp
0x180019715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001971a  jmp     short loc_180019752
0x18001971c  mov     ebp, [rbx+8]
0x18001971f  lea     rax, [rsp+278h+Buffer]
0x180019724  mov     [rsp+278h+Arguments], r15; Arguments
0x180019729  mov     r8d, ebp; dwMessageId
0x18001972c  mov     [rsp+278h+nSize], 100h; nSize
0x180019734  mov     r9d, 400h; dwLanguageId
0x18001973a  xor     edx, edx; lpSource
0x18001973c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180019741  mov     ecx, 1200h; dwFlags
0x180019746  call    cs:__imp_FormatMessageW
0x18001974d  nop     dword ptr [rax+rax+00h]
0x180019752  mov     r9, [rbx+38h]; unsigned __int16 *
0x180019756  lea     rsi, [r14+rsi*2]
0x18001975a  mov     rax, [rbx+88h]
0x180019761  mov     rdx, rsi; unsigned __int16 *
0x180019764  mov     rcx, [rbx+80h]
0x18001976b  test    r9, r9
0x18001976e  jz      short loc_180019792
0x180019770  mov     [rsp+278h+Arguments], rax
0x180019775  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001977c  mov     eax, [rbx+40h]
0x18001977f  mov     qword ptr [rsp+278h+nSize], rcx
0x180019784  mov     rcx, r14; this
0x180019787  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001978b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019790  jmp     short loc_1800197A9
0x180019792  mov     r9, rcx; unsigned __int16 *
0x180019795  mov     [rsp+278h+lpBuffer], rax
0x18001979a  mov     rcx, r14; this
0x18001979d  lea     r8, aHsP; "%hs!%p: "
0x1800197a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800197a9  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800197b0  mov     r14, rax
0x1800197b3  test    r9, r9
0x1800197b6  jz      short loc_1800197CD
0x1800197b8  lea     r8, aCallerP; "(caller: %p) "
0x1800197bf  mov     rdx, rsi; unsigned __int16 *
0x1800197c2  mov     rcx, rax; this
0x1800197c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800197ca  mov     r14, rax
0x1800197cd  call    cs:__imp_GetCurrentThreadId
0x1800197d4  nop     dword ptr [rax+rax+00h]
0x1800197d9  lea     rcx, [rsp+278h+Buffer]
0x1800197de  mov     r9, rdi; unsigned __int16 *
0x1800197e1  mov     [rsp+278h+var_240], rcx
0x1800197e6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800197ed  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800197f1  mov     rdx, rsi; unsigned __int16 *
0x1800197f4  mov     [rsp+278h+nSize], eax
0x1800197f8  mov     rcx, r14; this
0x1800197fb  mov     eax, [rbx+44h]
0x1800197fe  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180019802  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019807  cmp     [rbx+18h], r15
0x18001980b  jnz     short loc_18001981D
0x18001980d  cmp     [rbx+48h], r15
0x180019811  jnz     short loc_18001981D
0x180019813  cmp     [rbx+30h], r15
0x180019817  jz      loc_1800198AD
0x18001981d  lea     r8, asc_180028908; "    "
0x180019824  mov     rdx, rsi; unsigned __int16 *
0x180019827  mov     rcx, rax; this
0x18001982a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001982f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180019833  test    r9, r9
0x180019836  jz      short loc_18001984A
0x180019838  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001983f  mov     rdx, rsi; unsigned __int16 *
0x180019842  mov     rcx, rax; this
0x180019845  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001984a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001984e  test    r9, r9
0x180019851  jz      short loc_180019865
0x180019853  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001985a  mov     rdx, rsi; unsigned __int16 *
0x18001985d  mov     rcx, rax; this
0x180019860  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019865  mov     rcx, [rbx+28h]
0x180019869  mov     rdx, rsi; unsigned __int16 *
0x18001986c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180019870  test    rcx, rcx
0x180019873  jz      short loc_18001988B
0x180019875  mov     [rsp+278h+lpBuffer], rcx
0x18001987a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180019881  mov     rcx, rax; this
0x180019884  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019889  jmp     short loc_1800198AD
0x18001988b  mov     rcx, rax; this
0x18001988e  test    r9, r9
0x180019891  jz      short loc_1800198A1
0x180019893  lea     r8, aHs; "[%hs]\n"
0x18001989a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001989f  jmp     short loc_1800198AD
0x1800198a1  lea     r8, asc_180028980; "\n"
0x1800198a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800198ad  xor     eax, eax
0x1800198af  mov     rcx, [rsp+278h+var_38]
0x1800198b7  xor     rcx, rsp; StackCookie
0x1800198ba  call    __security_check_cookie
0x1800198bf  mov     rbx, [rsp+278h+arg_18]
0x1800198c7  add     rsp, 250h
0x1800198ce  pop     r15
0x1800198d0  pop     r14
0x1800198d2  pop     rdi
0x1800198d3  pop     rsi
0x1800198d4  pop     rbp
0x1800198d5  retn
```
