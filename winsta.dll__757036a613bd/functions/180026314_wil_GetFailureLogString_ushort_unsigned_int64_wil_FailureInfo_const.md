# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180026314`
- end: `0x1800265ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800249ec`
- `0x1800268d0`

## callees

- `0x180026314`
- `0x180026bdc`
- `0x18002fe06`
- `0x18002fe40`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800264c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800264c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180026446`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180026446`

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
          v8 = (const char *)&byte_18003E6E1;
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
0x180026314  mov     [rsp+arg_18], rbx
0x180026319  push    rbp
0x18002631a  push    rsi
0x18002631b  push    rdi
0x18002631c  push    r14
0x18002631e  push    r15
0x180026320  sub     rsp, 250h
0x180026327  mov     rax, cs:__security_cookie
0x18002632e  xor     rax, rsp
0x180026331  mov     [rsp+278h+var_38], rax
0x180026339  xor     r15d, r15d
0x18002633c  mov     rbx, r8
0x18002633f  mov     rsi, rdx
0x180026342  mov     r14, rcx
0x180026345  test    rdx, rdx
0x180026348  jz      loc_1800265A1
0x18002634e  test    rcx, rcx
0x180026351  jz      loc_1800265A1
0x180026357  mov     rax, cs:g_pfnResultLoggingCallback
0x18002635e  mov     [rcx], r15w
0x180026362  test    rax, rax
0x180026365  jz      short loc_180026388
0x180026367  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002636e  jz      short loc_180026388
0x180026370  mov     r8, rdx
0x180026373  mov     rdx, rcx
0x180026376  mov     rcx, rbx
0x180026379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002637e  cmp     [r14], r15w
0x180026382  jnz     loc_1800265A1
0x180026388  mov     ecx, [rbx]
0x18002638a  mov     bpl, 8
0x18002638d  test    ecx, ecx
0x18002638f  jz      short loc_1800263DA
0x180026391  sub     ecx, 1
0x180026394  jz      short loc_1800263C2
0x180026396  sub     ecx, 1
0x180026399  jz      short loc_1800263B2
0x18002639b  cmp     ecx, 1
0x18002639e  jz      short loc_1800263A9
0x1800263a0  lea     rdi, byte_18003E6E1
0x1800263a7  jmp     short loc_1800263E1
0x1800263a9  lea     rdi, aFailfast; "FailFast"
0x1800263b0  jmp     short loc_1800263E1
0x1800263b2  lea     rax, aLoghr; "LogHr"
0x1800263b9  lea     rdi, aLognt; "LogNt"
0x1800263c0  jmp     short loc_1800263D0
0x1800263c2  lea     rax, aReturnhr; "ReturnHr"
0x1800263c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800263d0  test    [rbx+4], bpl
0x1800263d4  cmovz   rdi, rax
0x1800263d8  jmp     short loc_1800263E1
0x1800263da  lea     rdi, aException; "Exception"
0x1800263e1  xor     edx, edx; Val
0x1800263e3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800263e8  mov     r8d, 200h; Size
0x1800263ee  call    memset_0
0x1800263f3  test    [rbx+4], bpl
0x1800263f7  jz      short loc_18002641C
0x1800263f9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180026400  mov     ebp, [rbx+0Ch]
0x180026403  test    rax, rax
0x180026406  jz      short loc_18002644C
0x180026408  mov     r8d, 100h
0x18002640e  lea     rdx, [rsp+278h+Buffer]
0x180026413  mov     ecx, ebp
0x180026415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002641a  jmp     short loc_18002644C
0x18002641c  mov     ebp, [rbx+8]
0x18002641f  lea     rax, [rsp+278h+Buffer]
0x180026424  mov     [rsp+278h+Arguments], r15; Arguments
0x180026429  mov     r8d, ebp; dwMessageId
0x18002642c  mov     [rsp+278h+nSize], 100h; nSize
0x180026434  mov     r9d, 400h; dwLanguageId
0x18002643a  xor     edx, edx; lpSource
0x18002643c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180026441  mov     ecx, 1200h; dwFlags
0x180026446  call    cs:__imp_FormatMessageW
0x18002644c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180026450  lea     rsi, [r14+rsi*2]
0x180026454  mov     rax, [rbx+88h]
0x18002645b  mov     rdx, rsi; unsigned __int16 *
0x18002645e  mov     rcx, [rbx+80h]
0x180026465  test    r9, r9
0x180026468  jz      short loc_18002648C
0x18002646a  mov     [rsp+278h+Arguments], rax
0x18002646f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180026476  mov     eax, [rbx+40h]
0x180026479  mov     qword ptr [rsp+278h+nSize], rcx
0x18002647e  mov     rcx, r14; this
0x180026481  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180026485  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002648a  jmp     short loc_1800264A3
0x18002648c  mov     r9, rcx; unsigned __int16 *
0x18002648f  mov     [rsp+278h+lpBuffer], rax
0x180026494  mov     rcx, r14; this
0x180026497  lea     r8, aHsP; "%hs!%p: "
0x18002649e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800264a3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800264aa  mov     r14, rax
0x1800264ad  test    r9, r9
0x1800264b0  jz      short loc_1800264C7
0x1800264b2  lea     r8, aCallerP; "(caller: %p) "
0x1800264b9  mov     rdx, rsi; unsigned __int16 *
0x1800264bc  mov     rcx, rax; this
0x1800264bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800264c4  mov     r14, rax
0x1800264c7  call    cs:__imp_GetCurrentThreadId
0x1800264cd  lea     rcx, [rsp+278h+Buffer]
0x1800264d2  mov     r9, rdi; unsigned __int16 *
0x1800264d5  mov     [rsp+278h+var_240], rcx
0x1800264da  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800264e1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800264e5  mov     rdx, rsi; unsigned __int16 *
0x1800264e8  mov     [rsp+278h+nSize], eax
0x1800264ec  mov     rcx, r14; this
0x1800264ef  mov     eax, [rbx+44h]
0x1800264f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800264f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800264fb  cmp     [rbx+18h], r15
0x1800264ff  jnz     short loc_180026511
0x180026501  cmp     [rbx+48h], r15
0x180026505  jnz     short loc_180026511
0x180026507  cmp     [rbx+30h], r15
0x18002650b  jz      loc_1800265A1
0x180026511  lea     r8, asc_180047598; "    "
0x180026518  mov     rdx, rsi; unsigned __int16 *
0x18002651b  mov     rcx, rax; this
0x18002651e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026523  mov     r9, [rbx+18h]; unsigned __int16 *
0x180026527  test    r9, r9
0x18002652a  jz      short loc_18002653E
0x18002652c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180026533  mov     rdx, rsi; unsigned __int16 *
0x180026536  mov     rcx, rax; this
0x180026539  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002653e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180026542  test    r9, r9
0x180026545  jz      short loc_180026559
0x180026547  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002654e  mov     rdx, rsi; unsigned __int16 *
0x180026551  mov     rcx, rax; this
0x180026554  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026559  mov     rcx, [rbx+28h]
0x18002655d  mov     rdx, rsi; unsigned __int16 *
0x180026560  mov     r9, [rbx+30h]; unsigned __int16 *
0x180026564  test    rcx, rcx
0x180026567  jz      short loc_18002657F
0x180026569  mov     [rsp+278h+lpBuffer], rcx
0x18002656e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180026575  mov     rcx, rax; this
0x180026578  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002657d  jmp     short loc_1800265A1
0x18002657f  mov     rcx, rax; this
0x180026582  test    r9, r9
0x180026585  jz      short loc_180026595
0x180026587  lea     r8, aHs; "[%hs]\n"
0x18002658e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026593  jmp     short loc_1800265A1
0x180026595  lea     r8, asc_180047610; "\n"
0x18002659c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800265a1  xor     eax, eax
0x1800265a3  mov     rcx, [rsp+278h+var_38]
0x1800265ab  xor     rcx, rsp; StackCookie
0x1800265ae  call    __security_check_cookie
0x1800265b3  mov     rbx, [rsp+278h+arg_18]
0x1800265bb  add     rsp, 250h
0x1800265c2  pop     r15
0x1800265c4  pop     r14
0x1800265c6  pop     rdi
0x1800265c7  pop     rsi
0x1800265c8  pop     rbp
0x1800265c9  retn
```
