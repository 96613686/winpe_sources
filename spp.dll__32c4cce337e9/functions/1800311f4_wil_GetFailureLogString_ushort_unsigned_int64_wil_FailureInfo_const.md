# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800311f4`
- end: `0x1800314aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002fa9c`
- `0x18002fd04`
- `0x180031d64`

## callees

- `0x1800311f4`
- `0x180032064`
- `0x180035b9a`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800313a7`
- `KERNEL32!GetCurrentThreadId` at `0x1800313a7`
- `KERNEL32!FormatMessageW` at `0x180031326`
- `KERNEL32!FormatMessageW` at `0x180031326`

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
          v8 = (const char *)&word_18003D7BD;
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
0x1800311f4  mov     [rsp+arg_18], rbx
0x1800311f9  push    rbp
0x1800311fa  push    rsi
0x1800311fb  push    rdi
0x1800311fc  push    r14
0x1800311fe  push    r15
0x180031200  sub     rsp, 250h
0x180031207  mov     rax, cs:__security_cookie
0x18003120e  xor     rax, rsp
0x180031211  mov     [rsp+278h+var_38], rax
0x180031219  xor     r15d, r15d
0x18003121c  mov     rbx, r8
0x18003121f  mov     rsi, rdx
0x180031222  mov     r14, rcx
0x180031225  test    rdx, rdx
0x180031228  jz      loc_180031481
0x18003122e  test    rcx, rcx
0x180031231  jz      loc_180031481
0x180031237  mov     rax, cs:g_pfnResultLoggingCallback
0x18003123e  mov     [rcx], r15w
0x180031242  test    rax, rax
0x180031245  jz      short loc_180031268
0x180031247  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003124e  jz      short loc_180031268
0x180031250  mov     r8, rdx
0x180031253  mov     rdx, rcx
0x180031256  mov     rcx, rbx
0x180031259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003125e  cmp     [r14], r15w
0x180031262  jnz     loc_180031481
0x180031268  mov     ecx, [rbx]
0x18003126a  mov     bpl, 8
0x18003126d  test    ecx, ecx
0x18003126f  jz      short loc_1800312BA
0x180031271  sub     ecx, 1
0x180031274  jz      short loc_1800312A2
0x180031276  sub     ecx, 1
0x180031279  jz      short loc_180031292
0x18003127b  cmp     ecx, 1
0x18003127e  jz      short loc_180031289
0x180031280  lea     rdi, word_18003D7BD
0x180031287  jmp     short loc_1800312C1
0x180031289  lea     rdi, aFailfast; "FailFast"
0x180031290  jmp     short loc_1800312C1
0x180031292  lea     rax, aLoghr; "LogHr"
0x180031299  lea     rdi, aLognt; "LogNt"
0x1800312a0  jmp     short loc_1800312B0
0x1800312a2  lea     rax, aReturnhr; "ReturnHr"
0x1800312a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800312b0  test    [rbx+4], bpl
0x1800312b4  cmovz   rdi, rax
0x1800312b8  jmp     short loc_1800312C1
0x1800312ba  lea     rdi, aException; "Exception"
0x1800312c1  xor     edx, edx; Val
0x1800312c3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800312c8  mov     r8d, 200h; Size
0x1800312ce  call    memset_0
0x1800312d3  test    [rbx+4], bpl
0x1800312d7  jz      short loc_1800312FC
0x1800312d9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800312e0  mov     ebp, [rbx+0Ch]
0x1800312e3  test    rax, rax
0x1800312e6  jz      short loc_18003132C
0x1800312e8  mov     r8d, 100h
0x1800312ee  lea     rdx, [rsp+278h+Buffer]
0x1800312f3  mov     ecx, ebp
0x1800312f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312fa  jmp     short loc_18003132C
0x1800312fc  mov     ebp, [rbx+8]
0x1800312ff  lea     rax, [rsp+278h+Buffer]
0x180031304  mov     [rsp+278h+Arguments], r15; Arguments
0x180031309  mov     r8d, ebp; dwMessageId
0x18003130c  mov     [rsp+278h+nSize], 100h; nSize
0x180031314  mov     r9d, 400h; dwLanguageId
0x18003131a  xor     edx, edx; lpSource
0x18003131c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180031321  mov     ecx, 1200h; dwFlags
0x180031326  call    cs:__imp_FormatMessageW
0x18003132c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180031330  lea     rsi, [r14+rsi*2]
0x180031334  mov     rax, [rbx+88h]
0x18003133b  mov     rdx, rsi; unsigned __int16 *
0x18003133e  mov     rcx, [rbx+80h]
0x180031345  test    r9, r9
0x180031348  jz      short loc_18003136C
0x18003134a  mov     [rsp+278h+Arguments], rax
0x18003134f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180031356  mov     eax, [rbx+40h]
0x180031359  mov     qword ptr [rsp+278h+nSize], rcx
0x18003135e  mov     rcx, r14; this
0x180031361  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180031365  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003136a  jmp     short loc_180031383
0x18003136c  mov     r9, rcx; unsigned __int16 *
0x18003136f  mov     [rsp+278h+lpBuffer], rax
0x180031374  mov     rcx, r14; this
0x180031377  lea     r8, aHsP; "%hs!%p: "
0x18003137e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180031383  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003138a  mov     r14, rax
0x18003138d  test    r9, r9
0x180031390  jz      short loc_1800313A7
0x180031392  lea     r8, aCallerP; "(caller: %p) "
0x180031399  mov     rdx, rsi; unsigned __int16 *
0x18003139c  mov     rcx, rax; this
0x18003139f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800313a4  mov     r14, rax
0x1800313a7  call    cs:__imp_GetCurrentThreadId
0x1800313ad  lea     rcx, [rsp+278h+Buffer]
0x1800313b2  mov     r9, rdi; unsigned __int16 *
0x1800313b5  mov     [rsp+278h+var_240], rcx
0x1800313ba  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800313c1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800313c5  mov     rdx, rsi; unsigned __int16 *
0x1800313c8  mov     [rsp+278h+nSize], eax
0x1800313cc  mov     rcx, r14; this
0x1800313cf  mov     eax, [rbx+44h]
0x1800313d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800313d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800313db  cmp     [rbx+18h], r15
0x1800313df  jnz     short loc_1800313F1
0x1800313e1  cmp     [rbx+48h], r15
0x1800313e5  jnz     short loc_1800313F1
0x1800313e7  cmp     [rbx+30h], r15
0x1800313eb  jz      loc_180031481
0x1800313f1  lea     r8, asc_18003D8A8; "    "
0x1800313f8  mov     rdx, rsi; unsigned __int16 *
0x1800313fb  mov     rcx, rax; this
0x1800313fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180031403  mov     r9, [rbx+18h]; unsigned __int16 *
0x180031407  test    r9, r9
0x18003140a  jz      short loc_18003141E
0x18003140c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180031413  mov     rdx, rsi; unsigned __int16 *
0x180031416  mov     rcx, rax; this
0x180031419  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003141e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180031422  test    r9, r9
0x180031425  jz      short loc_180031439
0x180031427  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003142e  mov     rdx, rsi; unsigned __int16 *
0x180031431  mov     rcx, rax; this
0x180031434  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180031439  mov     rcx, [rbx+28h]
0x18003143d  mov     rdx, rsi; unsigned __int16 *
0x180031440  mov     r9, [rbx+30h]; unsigned __int16 *
0x180031444  test    rcx, rcx
0x180031447  jz      short loc_18003145F
0x180031449  mov     [rsp+278h+lpBuffer], rcx
0x18003144e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180031455  mov     rcx, rax; this
0x180031458  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003145d  jmp     short loc_180031481
0x18003145f  mov     rcx, rax; this
0x180031462  test    r9, r9
0x180031465  jz      short loc_180031475
0x180031467  lea     r8, aHs; "[%hs]\n"
0x18003146e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180031473  jmp     short loc_180031481
0x180031475  lea     r8, asc_18003D920; "\n"
0x18003147c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180031481  xor     eax, eax
0x180031483  mov     rcx, [rsp+278h+var_38]
0x18003148b  xor     rcx, rsp; StackCookie
0x18003148e  call    __security_check_cookie
0x180031493  mov     rbx, [rsp+278h+arg_18]
0x18003149b  add     rsp, 250h
0x1800314a2  pop     r15
0x1800314a4  pop     r14
0x1800314a6  pop     rdi
0x1800314a7  pop     rsi
0x1800314a8  pop     rbp
0x1800314a9  retn
```
