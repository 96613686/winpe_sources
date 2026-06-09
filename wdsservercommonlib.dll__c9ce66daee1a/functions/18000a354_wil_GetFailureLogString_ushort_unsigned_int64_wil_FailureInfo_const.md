# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a354`
- end: `0x18000a615`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008338`
- `0x1800085b0`
- `0x18000ade0`

## callees

- `0x18000a354`
- `0x18000b0f0`
- `0x18002f3ba`
- `0x18002f3e0`
- `0x180030010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000a484`
- `KERNEL32!FormatMessageW` at `0x18000a484`
- `KERNEL32!GetCurrentThreadId` at `0x18000a50b`
- `KERNEL32!GetCurrentThreadId` at `0x18000a50b`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rsi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdi
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
  v8 = (const char *)&dword_1800331C4;
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
        goto LABEL_17;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_17;
  }
  v8 = "Exception";
LABEL_17:
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
0x18000a354  mov     [rsp+arg_18], rbx
0x18000a359  push    rbp
0x18000a35a  push    rsi
0x18000a35b  push    rdi
0x18000a35c  push    r14
0x18000a35e  push    r15
0x18000a360  sub     rsp, 250h
0x18000a367  mov     rax, cs:__security_cookie
0x18000a36e  xor     rax, rsp
0x18000a371  mov     [rsp+278h+var_38], rax
0x18000a379  xor     r15d, r15d
0x18000a37c  mov     rbx, r8
0x18000a37f  mov     rdi, rdx
0x18000a382  mov     r14, rcx
0x18000a385  test    rdx, rdx
0x18000a388  jz      loc_18000A5EB
0x18000a38e  test    rcx, rcx
0x18000a391  jz      loc_18000A5EB
0x18000a397  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a39e  mov     [rcx], r15w
0x18000a3a2  test    rax, rax
0x18000a3a5  jz      short loc_18000A3C8
0x18000a3a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a3ae  jz      short loc_18000A3C8
0x18000a3b0  mov     r8, rdx
0x18000a3b3  mov     rdx, rcx
0x18000a3b6  mov     rcx, rbx
0x18000a3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3be  cmp     [r14], r15w
0x18000a3c2  jnz     loc_18000A5EB
0x18000a3c8  mov     ecx, [rbx]
0x18000a3ca  lea     rsi, dword_1800331C4
0x18000a3d1  mov     bpl, 8
0x18000a3d4  test    ecx, ecx
0x18000a3d6  jz      short loc_18000A418
0x18000a3d8  sub     ecx, 1
0x18000a3db  jz      short loc_18000A400
0x18000a3dd  sub     ecx, 1
0x18000a3e0  jz      short loc_18000A3F0
0x18000a3e2  cmp     ecx, 1
0x18000a3e5  jnz     short loc_18000A41F
0x18000a3e7  lea     rsi, aFailfast; "FailFast"
0x18000a3ee  jmp     short loc_18000A41F
0x18000a3f0  lea     rax, aLoghr; "LogHr"
0x18000a3f7  lea     rsi, aLognt; "LogNt"
0x18000a3fe  jmp     short loc_18000A40E
0x18000a400  lea     rax, aReturnhr; "ReturnHr"
0x18000a407  lea     rsi, aReturnnt; "ReturnNt"
0x18000a40e  test    [rbx+4], bpl
0x18000a412  cmovz   rsi, rax
0x18000a416  jmp     short loc_18000A41F
0x18000a418  lea     rsi, aException; "Exception"
0x18000a41f  xor     edx, edx; Val
0x18000a421  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a426  mov     r8d, 200h; Size
0x18000a42c  call    memset_0
0x18000a431  test    [rbx+4], bpl
0x18000a435  jz      short loc_18000A45A
0x18000a437  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000a43e  mov     ebp, [rbx+0Ch]
0x18000a441  test    rax, rax
0x18000a444  jz      short loc_18000A490
0x18000a446  mov     r8d, 100h
0x18000a44c  lea     rdx, [rsp+278h+Buffer]
0x18000a451  mov     ecx, ebp
0x18000a453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a458  jmp     short loc_18000A490
0x18000a45a  mov     ebp, [rbx+8]
0x18000a45d  lea     rax, [rsp+278h+Buffer]
0x18000a462  mov     [rsp+278h+Arguments], r15; Arguments
0x18000a467  mov     r8d, ebp; dwMessageId
0x18000a46a  mov     [rsp+278h+nSize], 100h; nSize
0x18000a472  mov     r9d, 400h; dwLanguageId
0x18000a478  xor     edx, edx; lpSource
0x18000a47a  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000a47f  mov     ecx, 1200h; dwFlags
0x18000a484  call    cs:__imp_FormatMessageW
0x18000a48b  nop     dword ptr [rax+rax+00h]
0x18000a490  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000a494  lea     rdi, [r14+rdi*2]
0x18000a498  mov     rax, [rbx+88h]
0x18000a49f  mov     rdx, rdi; unsigned __int16 *
0x18000a4a2  mov     rcx, [rbx+80h]
0x18000a4a9  test    r9, r9
0x18000a4ac  jz      short loc_18000A4D0
0x18000a4ae  mov     [rsp+278h+Arguments], rax
0x18000a4b3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000a4ba  mov     eax, [rbx+40h]
0x18000a4bd  mov     qword ptr [rsp+278h+nSize], rcx
0x18000a4c2  mov     rcx, r14; this
0x18000a4c5  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a4c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a4ce  jmp     short loc_18000A4E7
0x18000a4d0  mov     r9, rcx; unsigned __int16 *
0x18000a4d3  mov     [rsp+278h+lpBuffer], rax
0x18000a4d8  mov     rcx, r14; this
0x18000a4db  lea     r8, aHsP; "%hs!%p: "
0x18000a4e2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a4e7  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000a4ee  mov     r14, rax
0x18000a4f1  test    r9, r9
0x18000a4f4  jz      short loc_18000A50B
0x18000a4f6  lea     r8, aCallerP; "(caller: %p) "
0x18000a4fd  mov     rdx, rdi; unsigned __int16 *
0x18000a500  mov     rcx, rax; this
0x18000a503  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a508  mov     r14, rax
0x18000a50b  call    cs:__imp_GetCurrentThreadId
0x18000a512  nop     dword ptr [rax+rax+00h]
0x18000a517  mov     ecx, [rbx+44h]
0x18000a51a  lea     rdx, [rsp+278h+Buffer]
0x18000a51f  mov     [rsp+278h+var_240], rdx
0x18000a524  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000a52b  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000a52f  mov     r9, rsi; unsigned __int16 *
0x18000a532  mov     [rsp+278h+nSize], eax
0x18000a536  mov     rdx, rdi; unsigned __int16 *
0x18000a539  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x18000a53d  mov     rcx, r14; this
0x18000a540  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a545  cmp     [rbx+18h], r15
0x18000a549  jnz     short loc_18000A55B
0x18000a54b  cmp     [rbx+48h], r15
0x18000a54f  jnz     short loc_18000A55B
0x18000a551  cmp     [rbx+30h], r15
0x18000a555  jz      loc_18000A5EB
0x18000a55b  lea     r8, asc_180033608; "    "
0x18000a562  mov     rdx, rdi; unsigned __int16 *
0x18000a565  mov     rcx, rax; this
0x18000a568  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a56d  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000a571  test    r9, r9
0x18000a574  jz      short loc_18000A588
0x18000a576  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000a57d  mov     rdx, rdi; unsigned __int16 *
0x18000a580  mov     rcx, rax; this
0x18000a583  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a588  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000a58c  test    r9, r9
0x18000a58f  jz      short loc_18000A5A3
0x18000a591  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000a598  mov     rdx, rdi; unsigned __int16 *
0x18000a59b  mov     rcx, rax; this
0x18000a59e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5a3  mov     rcx, [rbx+28h]
0x18000a5a7  mov     rdx, rdi; unsigned __int16 *
0x18000a5aa  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000a5ae  test    rcx, rcx
0x18000a5b1  jz      short loc_18000A5C9
0x18000a5b3  mov     [rsp+278h+lpBuffer], rcx
0x18000a5b8  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000a5bf  mov     rcx, rax; this
0x18000a5c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5c7  jmp     short loc_18000A5EB
0x18000a5c9  mov     rcx, rax; this
0x18000a5cc  test    r9, r9
0x18000a5cf  jz      short loc_18000A5DF
0x18000a5d1  lea     r8, aHs; "[%hs]\n"
0x18000a5d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5dd  jmp     short loc_18000A5EB
0x18000a5df  lea     r8, OutputString; "\n"
0x18000a5e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5eb  xor     eax, eax
0x18000a5ed  mov     rcx, [rsp+278h+var_38]
0x18000a5f5  xor     rcx, rsp; StackCookie
0x18000a5f8  call    __security_check_cookie
0x18000a5fd  mov     rbx, [rsp+278h+arg_18]
0x18000a605  add     rsp, 250h
0x18000a60c  pop     r15
0x18000a60e  pop     r14
0x18000a610  pop     rdi
0x18000a611  pop     rsi
0x18000a612  pop     rbp
0x18000a613  retn
```
