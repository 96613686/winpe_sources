# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000e894`
- end: `0x18000eb4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cc2c`
- `0x18000ce94`
- `0x18000f650`
- `0x180012820`

## callees

- `0x18000e894`
- `0x18000f950`
- `0x1800131a2`
- `0x1800131e0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea47`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e9c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e9c6`

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
          v7 = (const char *)&dword_1800191A4;
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
0x18000e894  mov     [rsp+arg_18], rbx
0x18000e899  push    rbp
0x18000e89a  push    rsi
0x18000e89b  push    rdi
0x18000e89c  push    r14
0x18000e89e  push    r15
0x18000e8a0  sub     rsp, 250h
0x18000e8a7  mov     rax, cs:__security_cookie
0x18000e8ae  xor     rax, rsp
0x18000e8b1  mov     [rsp+278h+var_38], rax
0x18000e8b9  mov     rbx, r8
0x18000e8bc  mov     rsi, rdx
0x18000e8bf  mov     r14, rcx
0x18000e8c2  xor     r15d, r15d
0x18000e8c5  test    rdx, rdx
0x18000e8c8  jz      loc_18000EB21
0x18000e8ce  test    rcx, rcx
0x18000e8d1  jz      loc_18000EB21
0x18000e8d7  mov     [rcx], r15w
0x18000e8db  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e8e2  test    rax, rax
0x18000e8e5  jz      short loc_18000E908
0x18000e8e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000e8ee  jz      short loc_18000E908
0x18000e8f0  mov     r8, rdx
0x18000e8f3  mov     rdx, rcx
0x18000e8f6  mov     rcx, rbx
0x18000e8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8fe  cmp     [r14], r15w
0x18000e902  jnz     loc_18000EB21
0x18000e908  mov     ecx, [rbx]
0x18000e90a  mov     bpl, 8
0x18000e90d  test    ecx, ecx
0x18000e90f  jz      short loc_18000E95A
0x18000e911  sub     ecx, 1
0x18000e914  jz      short loc_18000E942
0x18000e916  sub     ecx, 1
0x18000e919  jz      short loc_18000E932
0x18000e91b  cmp     ecx, 1
0x18000e91e  jz      short loc_18000E929
0x18000e920  lea     rdi, dword_1800191A4
0x18000e927  jmp     short loc_18000E961
0x18000e929  lea     rdi, aFailfast; "FailFast"
0x18000e930  jmp     short loc_18000E961
0x18000e932  lea     rax, aLoghr; "LogHr"
0x18000e939  lea     rdi, aLognt; "LogNt"
0x18000e940  jmp     short loc_18000E950
0x18000e942  lea     rax, aReturnhr; "ReturnHr"
0x18000e949  lea     rdi, aReturnnt; "ReturnNt"
0x18000e950  test    [rbx+4], bpl
0x18000e954  cmovz   rdi, rax
0x18000e958  jmp     short loc_18000E961
0x18000e95a  lea     rdi, aException; "Exception"
0x18000e961  xor     edx, edx; Val
0x18000e963  mov     r8d, 200h; Size
0x18000e969  lea     rcx, [rsp+278h+Buffer]; void *
0x18000e96e  call    memset_0
0x18000e973  test    [rbx+4], bpl
0x18000e977  jz      short loc_18000E99C
0x18000e979  mov     ebp, [rbx+0Ch]
0x18000e97c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000e983  test    rax, rax
0x18000e986  jz      short loc_18000E9CC
0x18000e988  mov     r8d, 100h
0x18000e98e  lea     rdx, [rsp+278h+Buffer]
0x18000e993  mov     ecx, ebp
0x18000e995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e99a  jmp     short loc_18000E9CC
0x18000e99c  mov     ebp, [rbx+8]
0x18000e99f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000e9a4  mov     [rsp+278h+nSize], 100h; nSize
0x18000e9ac  lea     rax, [rsp+278h+Buffer]
0x18000e9b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000e9b6  mov     r9d, 400h; dwLanguageId
0x18000e9bc  mov     r8d, ebp; dwMessageId
0x18000e9bf  xor     edx, edx; lpSource
0x18000e9c1  mov     ecx, 1200h; dwFlags
0x18000e9c6  call    cs:__imp_FormatMessageW
0x18000e9cc  lea     rsi, [r14+rsi*2]
0x18000e9d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000e9d4  mov     rax, [rbx+88h]
0x18000e9db  mov     rcx, [rbx+80h]
0x18000e9e2  mov     rdx, rsi; unsigned __int16 *
0x18000e9e5  test    r9, r9
0x18000e9e8  jz      short loc_18000EA0C
0x18000e9ea  mov     [rsp+278h+Arguments], rax
0x18000e9ef  mov     qword ptr [rsp+278h+nSize], rcx
0x18000e9f4  mov     eax, [rbx+40h]
0x18000e9f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000e9fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000ea02  mov     rcx, r14; this
0x18000ea05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ea0a  jmp     short loc_18000EA23
0x18000ea0c  mov     [rsp+278h+lpBuffer], rax
0x18000ea11  mov     r9, rcx; unsigned __int16 *
0x18000ea14  lea     r8, aHsP; "%hs!%p: "
0x18000ea1b  mov     rcx, r14; this
0x18000ea1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ea23  mov     r14, rax
0x18000ea26  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000ea2d  test    r9, r9
0x18000ea30  jz      short loc_18000EA47
0x18000ea32  lea     r8, aCallerP; "(caller: %p) "
0x18000ea39  mov     rdx, rsi; unsigned __int16 *
0x18000ea3c  mov     rcx, rax; this
0x18000ea3f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ea44  mov     r14, rax
0x18000ea47  call    cs:__imp_GetCurrentThreadId
0x18000ea4d  lea     rcx, [rsp+278h+Buffer]
0x18000ea52  mov     [rsp+278h+var_240], rcx
0x18000ea57  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000ea5b  mov     [rsp+278h+nSize], eax
0x18000ea5f  mov     eax, [rbx+44h]
0x18000ea62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ea66  mov     r9, rdi; unsigned __int16 *
0x18000ea69  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000ea70  mov     rdx, rsi; unsigned __int16 *
0x18000ea73  mov     rcx, r14; this
0x18000ea76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ea7b  cmp     [rbx+18h], r15
0x18000ea7f  jnz     short loc_18000EA91
0x18000ea81  cmp     [rbx+48h], r15
0x18000ea85  jnz     short loc_18000EA91
0x18000ea87  cmp     [rbx+30h], r15
0x18000ea8b  jz      loc_18000EB21
0x18000ea91  lea     r8, asc_18001A7D0; "    "
0x18000ea98  mov     rdx, rsi; unsigned __int16 *
0x18000ea9b  mov     rcx, rax; this
0x18000ea9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eaa3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000eaa7  test    r9, r9
0x18000eaaa  jz      short loc_18000EABE
0x18000eaac  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000eab3  mov     rdx, rsi; unsigned __int16 *
0x18000eab6  mov     rcx, rax; this
0x18000eab9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eabe  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000eac2  test    r9, r9
0x18000eac5  jz      short loc_18000EAD9
0x18000eac7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000eace  mov     rdx, rsi; unsigned __int16 *
0x18000ead1  mov     rcx, rax; this
0x18000ead4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ead9  mov     rcx, [rbx+28h]
0x18000eadd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000eae1  mov     rdx, rsi; unsigned __int16 *
0x18000eae4  test    rcx, rcx
0x18000eae7  jz      short loc_18000EAFF
0x18000eae9  mov     [rsp+278h+lpBuffer], rcx
0x18000eaee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000eaf5  mov     rcx, rax; this
0x18000eaf8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eafd  jmp     short loc_18000EB21
0x18000eaff  mov     rcx, rax; this
0x18000eb02  test    r9, r9
0x18000eb05  jz      short loc_18000EB15
0x18000eb07  lea     r8, aHs; "[%hs]\n"
0x18000eb0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eb13  jmp     short loc_18000EB21
0x18000eb15  lea     r8, asc_18001A848; "\n"
0x18000eb1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eb21  xor     eax, eax
0x18000eb23  mov     rcx, [rsp+278h+var_38]
0x18000eb2b  xor     rcx, rsp; StackCookie
0x18000eb2e  call    __security_check_cookie
0x18000eb33  mov     rbx, [rsp+278h+arg_18]
0x18000eb3b  add     rsp, 250h
0x18000eb42  pop     r15
0x18000eb44  pop     r14
0x18000eb46  pop     rdi
0x18000eb47  pop     rsi
0x18000eb48  pop     rbp
0x18000eb49  retn
```
