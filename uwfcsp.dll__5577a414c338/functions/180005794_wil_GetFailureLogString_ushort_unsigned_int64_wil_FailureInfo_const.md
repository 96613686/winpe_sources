# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005794`
- end: `0x180005a4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004724`
- `0x180004994`
- `0x180006198`

## callees

- `0x180005794`
- `0x180006498`
- `0x18001a1d6`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005947`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005947`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800058c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800058c6`

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
          v8 = (const char *)&qword_18001EF80;
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
0x180005794  mov     [rsp+arg_18], rbx
0x180005799  push    rbp
0x18000579a  push    rsi
0x18000579b  push    rdi
0x18000579c  push    r14
0x18000579e  push    r15
0x1800057a0  sub     rsp, 250h
0x1800057a7  mov     rax, cs:__security_cookie
0x1800057ae  xor     rax, rsp
0x1800057b1  mov     [rsp+278h+var_38], rax
0x1800057b9  xor     r15d, r15d
0x1800057bc  mov     rbx, r8
0x1800057bf  mov     rsi, rdx
0x1800057c2  mov     r14, rcx
0x1800057c5  test    rdx, rdx
0x1800057c8  jz      loc_180005A21
0x1800057ce  test    rcx, rcx
0x1800057d1  jz      loc_180005A21
0x1800057d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800057de  mov     [rcx], r15w
0x1800057e2  test    rax, rax
0x1800057e5  jz      short loc_180005808
0x1800057e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800057ee  jz      short loc_180005808
0x1800057f0  mov     r8, rdx
0x1800057f3  mov     rdx, rcx
0x1800057f6  mov     rcx, rbx
0x1800057f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057fe  cmp     [r14], r15w
0x180005802  jnz     loc_180005A21
0x180005808  mov     ecx, [rbx]
0x18000580a  mov     bpl, 8
0x18000580d  test    ecx, ecx
0x18000580f  jz      short loc_18000585A
0x180005811  sub     ecx, 1
0x180005814  jz      short loc_180005842
0x180005816  sub     ecx, 1
0x180005819  jz      short loc_180005832
0x18000581b  cmp     ecx, 1
0x18000581e  jz      short loc_180005829
0x180005820  lea     rdi, qword_18001EF80
0x180005827  jmp     short loc_180005861
0x180005829  lea     rdi, aFailfast; "FailFast"
0x180005830  jmp     short loc_180005861
0x180005832  lea     rax, aLoghr; "LogHr"
0x180005839  lea     rdi, aLognt; "LogNt"
0x180005840  jmp     short loc_180005850
0x180005842  lea     rax, aReturnhr; "ReturnHr"
0x180005849  lea     rdi, aReturnnt; "ReturnNt"
0x180005850  test    [rbx+4], bpl
0x180005854  cmovz   rdi, rax
0x180005858  jmp     short loc_180005861
0x18000585a  lea     rdi, aException; "Exception"
0x180005861  xor     edx, edx; Val
0x180005863  lea     rcx, [rsp+278h+Buffer]; void *
0x180005868  mov     r8d, 200h; Size
0x18000586e  call    memset_0
0x180005873  test    [rbx+4], bpl
0x180005877  jz      short loc_18000589C
0x180005879  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005880  mov     ebp, [rbx+0Ch]
0x180005883  test    rax, rax
0x180005886  jz      short loc_1800058CC
0x180005888  mov     r8d, 100h
0x18000588e  lea     rdx, [rsp+278h+Buffer]
0x180005893  mov     ecx, ebp
0x180005895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000589a  jmp     short loc_1800058CC
0x18000589c  mov     ebp, [rbx+8]
0x18000589f  lea     rax, [rsp+278h+Buffer]
0x1800058a4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800058a9  mov     r8d, ebp; dwMessageId
0x1800058ac  mov     [rsp+278h+nSize], 100h; nSize
0x1800058b4  mov     r9d, 400h; dwLanguageId
0x1800058ba  xor     edx, edx; lpSource
0x1800058bc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800058c1  mov     ecx, 1200h; dwFlags
0x1800058c6  call    cs:__imp_FormatMessageW
0x1800058cc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800058d0  lea     rsi, [r14+rsi*2]
0x1800058d4  mov     rax, [rbx+88h]
0x1800058db  mov     rdx, rsi; unsigned __int16 *
0x1800058de  mov     rcx, [rbx+80h]
0x1800058e5  test    r9, r9
0x1800058e8  jz      short loc_18000590C
0x1800058ea  mov     [rsp+278h+Arguments], rax
0x1800058ef  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800058f6  mov     eax, [rbx+40h]
0x1800058f9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800058fe  mov     rcx, r14; this
0x180005901  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005905  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000590a  jmp     short loc_180005923
0x18000590c  mov     r9, rcx; unsigned __int16 *
0x18000590f  mov     [rsp+278h+lpBuffer], rax
0x180005914  mov     rcx, r14; this
0x180005917  lea     r8, aHsP; "%hs!%p: "
0x18000591e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005923  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000592a  mov     r14, rax
0x18000592d  test    r9, r9
0x180005930  jz      short loc_180005947
0x180005932  lea     r8, aCallerP; "(caller: %p) "
0x180005939  mov     rdx, rsi; unsigned __int16 *
0x18000593c  mov     rcx, rax; this
0x18000593f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005944  mov     r14, rax
0x180005947  call    cs:__imp_GetCurrentThreadId
0x18000594d  lea     rcx, [rsp+278h+Buffer]
0x180005952  mov     r9, rdi; unsigned __int16 *
0x180005955  mov     [rsp+278h+var_240], rcx
0x18000595a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005961  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005965  mov     rdx, rsi; unsigned __int16 *
0x180005968  mov     [rsp+278h+nSize], eax
0x18000596c  mov     rcx, r14; this
0x18000596f  mov     eax, [rbx+44h]
0x180005972  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005976  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000597b  cmp     [rbx+18h], r15
0x18000597f  jnz     short loc_180005991
0x180005981  cmp     [rbx+48h], r15
0x180005985  jnz     short loc_180005991
0x180005987  cmp     [rbx+30h], r15
0x18000598b  jz      loc_180005A21
0x180005991  lea     r8, asc_18001F0B8; "    "
0x180005998  mov     rdx, rsi; unsigned __int16 *
0x18000599b  mov     rcx, rax; this
0x18000599e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800059a7  test    r9, r9
0x1800059aa  jz      short loc_1800059BE
0x1800059ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800059b3  mov     rdx, rsi; unsigned __int16 *
0x1800059b6  mov     rcx, rax; this
0x1800059b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800059c2  test    r9, r9
0x1800059c5  jz      short loc_1800059D9
0x1800059c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800059ce  mov     rdx, rsi; unsigned __int16 *
0x1800059d1  mov     rcx, rax; this
0x1800059d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059d9  mov     rcx, [rbx+28h]
0x1800059dd  mov     rdx, rsi; unsigned __int16 *
0x1800059e0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800059e4  test    rcx, rcx
0x1800059e7  jz      short loc_1800059FF
0x1800059e9  mov     [rsp+278h+lpBuffer], rcx
0x1800059ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800059f5  mov     rcx, rax; this
0x1800059f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059fd  jmp     short loc_180005A21
0x1800059ff  mov     rcx, rax; this
0x180005a02  test    r9, r9
0x180005a05  jz      short loc_180005A15
0x180005a07  lea     r8, aHs; "[%hs]\n"
0x180005a0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a13  jmp     short loc_180005A21
0x180005a15  lea     r8, asc_18001F130; "\n"
0x180005a1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a21  xor     eax, eax
0x180005a23  mov     rcx, [rsp+278h+var_38]
0x180005a2b  xor     rcx, rsp; StackCookie
0x180005a2e  call    __security_check_cookie
0x180005a33  mov     rbx, [rsp+278h+arg_18]
0x180005a3b  add     rsp, 250h
0x180005a42  pop     r15
0x180005a44  pop     r14
0x180005a46  pop     rdi
0x180005a47  pop     rsi
0x180005a48  pop     rbp
0x180005a49  retn
```
