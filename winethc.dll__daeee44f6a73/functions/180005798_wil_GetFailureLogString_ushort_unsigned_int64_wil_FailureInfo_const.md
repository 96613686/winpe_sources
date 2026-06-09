# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005798`
- end: `0x180005a5b`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800022e8`
- `0x180002568`
- `0x180008b20`

## callees

- `0x180005798`
- `0x180008e34`
- `0x180012d6e`
- `0x180012db0`
- `0x180014010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800058ca`
- `KERNEL32!FormatMessageW` at `0x1800058ca`
- `KERNEL32!GetCurrentThreadId` at `0x180005951`
- `KERNEL32!GetCurrentThreadId` at `0x180005951`

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
          v8 = (const char *)&word_180017BD2;
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
0x180005798  mov     [rsp+arg_18], rbx
0x18000579d  push    rbp
0x18000579e  push    rsi
0x18000579f  push    rdi
0x1800057a0  push    r14
0x1800057a2  push    r15
0x1800057a4  sub     rsp, 250h
0x1800057ab  mov     rax, cs:__security_cookie
0x1800057b2  xor     rax, rsp
0x1800057b5  mov     [rsp+278h+var_38], rax
0x1800057bd  xor     r15d, r15d
0x1800057c0  mov     rbx, r8
0x1800057c3  mov     rsi, rdx
0x1800057c6  mov     r14, rcx
0x1800057c9  test    rdx, rdx
0x1800057cc  jz      loc_180005A31
0x1800057d2  test    rcx, rcx
0x1800057d5  jz      loc_180005A31
0x1800057db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800057e2  mov     [rcx], r15w
0x1800057e6  test    rax, rax
0x1800057e9  jz      short loc_18000580C
0x1800057eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800057f2  jz      short loc_18000580C
0x1800057f4  mov     r8, rdx
0x1800057f7  mov     rdx, rcx
0x1800057fa  mov     rcx, rbx
0x1800057fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005802  cmp     [r14], r15w
0x180005806  jnz     loc_180005A31
0x18000580c  mov     ecx, [rbx]
0x18000580e  mov     bpl, 8
0x180005811  test    ecx, ecx
0x180005813  jz      short loc_18000585E
0x180005815  sub     ecx, 1
0x180005818  jz      short loc_180005846
0x18000581a  sub     ecx, 1
0x18000581d  jz      short loc_180005836
0x18000581f  cmp     ecx, 1
0x180005822  jz      short loc_18000582D
0x180005824  lea     rdi, word_180017BD2
0x18000582b  jmp     short loc_180005865
0x18000582d  lea     rdi, aFailfast; "FailFast"
0x180005834  jmp     short loc_180005865
0x180005836  lea     rax, aLoghr; "LogHr"
0x18000583d  lea     rdi, aLognt; "LogNt"
0x180005844  jmp     short loc_180005854
0x180005846  lea     rax, aReturnhr; "ReturnHr"
0x18000584d  lea     rdi, aReturnnt; "ReturnNt"
0x180005854  test    [rbx+4], bpl
0x180005858  cmovz   rdi, rax
0x18000585c  jmp     short loc_180005865
0x18000585e  lea     rdi, aException; "Exception"
0x180005865  xor     edx, edx; Val
0x180005867  lea     rcx, [rsp+278h+Buffer]; void *
0x18000586c  mov     r8d, 200h; Size
0x180005872  call    memset_0
0x180005877  test    [rbx+4], bpl
0x18000587b  jz      short loc_1800058A0
0x18000587d  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005884  mov     ebp, [rbx+0Ch]
0x180005887  test    rax, rax
0x18000588a  jz      short loc_1800058D6
0x18000588c  mov     r8d, 100h
0x180005892  lea     rdx, [rsp+278h+Buffer]
0x180005897  mov     ecx, ebp
0x180005899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000589e  jmp     short loc_1800058D6
0x1800058a0  mov     ebp, [rbx+8]
0x1800058a3  lea     rax, [rsp+278h+Buffer]
0x1800058a8  mov     [rsp+278h+Arguments], r15; Arguments
0x1800058ad  mov     r8d, ebp; dwMessageId
0x1800058b0  mov     [rsp+278h+nSize], 100h; nSize
0x1800058b8  mov     r9d, 400h; dwLanguageId
0x1800058be  xor     edx, edx; lpSource
0x1800058c0  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800058c5  mov     ecx, 1200h; dwFlags
0x1800058ca  call    cs:__imp_FormatMessageW
0x1800058d1  nop     dword ptr [rax+rax+00h]
0x1800058d6  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800058da  lea     rsi, [r14+rsi*2]
0x1800058de  mov     rax, [rbx+88h]
0x1800058e5  mov     rdx, rsi; unsigned __int16 *
0x1800058e8  mov     rcx, [rbx+80h]
0x1800058ef  test    r9, r9
0x1800058f2  jz      short loc_180005916
0x1800058f4  mov     [rsp+278h+Arguments], rax
0x1800058f9  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005900  mov     eax, [rbx+40h]
0x180005903  mov     qword ptr [rsp+278h+nSize], rcx
0x180005908  mov     rcx, r14; this
0x18000590b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000590f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005914  jmp     short loc_18000592D
0x180005916  mov     r9, rcx; unsigned __int16 *
0x180005919  mov     [rsp+278h+lpBuffer], rax
0x18000591e  mov     rcx, r14; this
0x180005921  lea     r8, aHsP; "%hs!%p: "
0x180005928  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000592d  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005934  mov     r14, rax
0x180005937  test    r9, r9
0x18000593a  jz      short loc_180005951
0x18000593c  lea     r8, aCallerP; "(caller: %p) "
0x180005943  mov     rdx, rsi; unsigned __int16 *
0x180005946  mov     rcx, rax; this
0x180005949  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000594e  mov     r14, rax
0x180005951  call    cs:__imp_GetCurrentThreadId
0x180005958  nop     dword ptr [rax+rax+00h]
0x18000595d  lea     rcx, [rsp+278h+Buffer]
0x180005962  mov     r9, rdi; unsigned __int16 *
0x180005965  mov     [rsp+278h+var_240], rcx
0x18000596a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005971  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005975  mov     rdx, rsi; unsigned __int16 *
0x180005978  mov     [rsp+278h+nSize], eax
0x18000597c  mov     rcx, r14; this
0x18000597f  mov     eax, [rbx+44h]
0x180005982  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005986  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000598b  cmp     [rbx+18h], r15
0x18000598f  jnz     short loc_1800059A1
0x180005991  cmp     [rbx+48h], r15
0x180005995  jnz     short loc_1800059A1
0x180005997  cmp     [rbx+30h], r15
0x18000599b  jz      loc_180005A31
0x1800059a1  lea     r8, asc_180016140; "    "
0x1800059a8  mov     rdx, rsi; unsigned __int16 *
0x1800059ab  mov     rcx, rax; this
0x1800059ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800059b7  test    r9, r9
0x1800059ba  jz      short loc_1800059CE
0x1800059bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800059c3  mov     rdx, rsi; unsigned __int16 *
0x1800059c6  mov     rcx, rax; this
0x1800059c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800059d2  test    r9, r9
0x1800059d5  jz      short loc_1800059E9
0x1800059d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800059de  mov     rdx, rsi; unsigned __int16 *
0x1800059e1  mov     rcx, rax; this
0x1800059e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059e9  mov     rcx, [rbx+28h]
0x1800059ed  mov     rdx, rsi; unsigned __int16 *
0x1800059f0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800059f4  test    rcx, rcx
0x1800059f7  jz      short loc_180005A0F
0x1800059f9  mov     [rsp+278h+lpBuffer], rcx
0x1800059fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005a05  mov     rcx, rax; this
0x180005a08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a0d  jmp     short loc_180005A31
0x180005a0f  mov     rcx, rax; this
0x180005a12  test    r9, r9
0x180005a15  jz      short loc_180005A25
0x180005a17  lea     r8, aHs; "[%hs]\n"
0x180005a1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a23  jmp     short loc_180005A31
0x180005a25  lea     r8, asc_1800161B8; "\n"
0x180005a2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a31  xor     eax, eax
0x180005a33  mov     rcx, [rsp+278h+var_38]
0x180005a3b  xor     rcx, rsp; StackCookie
0x180005a3e  call    __security_check_cookie
0x180005a43  mov     rbx, [rsp+278h+arg_18]
0x180005a4b  add     rsp, 250h
0x180005a52  pop     r15
0x180005a54  pop     r14
0x180005a56  pop     rdi
0x180005a57  pop     rsi
0x180005a58  pop     rbp
0x180005a59  retn
```
