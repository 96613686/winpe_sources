# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b2ac`
- end: `0x18000b562`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800088fc`
- `0x180008b5c`
- `0x18000bdfc`

## callees

- `0x18000b2ac`
- `0x18000c0fc`
- `0x18001218a`
- `0x1800121b0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b3de`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b3de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b45f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b45f`

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
          v8 = (const char *)&qword_180016B48;
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
0x18000b2ac  mov     [rsp+arg_18], rbx
0x18000b2b1  push    rbp
0x18000b2b2  push    rsi
0x18000b2b3  push    rdi
0x18000b2b4  push    r14
0x18000b2b6  push    r15
0x18000b2b8  sub     rsp, 250h
0x18000b2bf  mov     rax, cs:__security_cookie
0x18000b2c6  xor     rax, rsp
0x18000b2c9  mov     [rsp+278h+var_38], rax
0x18000b2d1  xor     r15d, r15d
0x18000b2d4  mov     rbx, r8
0x18000b2d7  mov     rsi, rdx
0x18000b2da  mov     r14, rcx
0x18000b2dd  test    rdx, rdx
0x18000b2e0  jz      loc_18000B539
0x18000b2e6  test    rcx, rcx
0x18000b2e9  jz      loc_18000B539
0x18000b2ef  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b2f6  mov     [rcx], r15w
0x18000b2fa  test    rax, rax
0x18000b2fd  jz      short loc_18000B320
0x18000b2ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b306  jz      short loc_18000B320
0x18000b308  mov     r8, rdx
0x18000b30b  mov     rdx, rcx
0x18000b30e  mov     rcx, rbx
0x18000b311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b316  cmp     [r14], r15w
0x18000b31a  jnz     loc_18000B539
0x18000b320  mov     ecx, [rbx]
0x18000b322  mov     bpl, 8
0x18000b325  test    ecx, ecx
0x18000b327  jz      short loc_18000B372
0x18000b329  sub     ecx, 1
0x18000b32c  jz      short loc_18000B35A
0x18000b32e  sub     ecx, 1
0x18000b331  jz      short loc_18000B34A
0x18000b333  cmp     ecx, 1
0x18000b336  jz      short loc_18000B341
0x18000b338  lea     rdi, qword_180016B48
0x18000b33f  jmp     short loc_18000B379
0x18000b341  lea     rdi, aFailfast; "FailFast"
0x18000b348  jmp     short loc_18000B379
0x18000b34a  lea     rax, aLoghr; "LogHr"
0x18000b351  lea     rdi, aLognt; "LogNt"
0x18000b358  jmp     short loc_18000B368
0x18000b35a  lea     rax, aReturnhr; "ReturnHr"
0x18000b361  lea     rdi, aReturnnt; "ReturnNt"
0x18000b368  test    [rbx+4], bpl
0x18000b36c  cmovz   rdi, rax
0x18000b370  jmp     short loc_18000B379
0x18000b372  lea     rdi, aException; "Exception"
0x18000b379  xor     edx, edx; Val
0x18000b37b  lea     rcx, [rsp+278h+Buffer]; void *
0x18000b380  mov     r8d, 200h; Size
0x18000b386  call    memset_0
0x18000b38b  test    [rbx+4], bpl
0x18000b38f  jz      short loc_18000B3B4
0x18000b391  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000b398  mov     ebp, [rbx+0Ch]
0x18000b39b  test    rax, rax
0x18000b39e  jz      short loc_18000B3E4
0x18000b3a0  mov     r8d, 100h
0x18000b3a6  lea     rdx, [rsp+278h+Buffer]
0x18000b3ab  mov     ecx, ebp
0x18000b3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3b2  jmp     short loc_18000B3E4
0x18000b3b4  mov     ebp, [rbx+8]
0x18000b3b7  lea     rax, [rsp+278h+Buffer]
0x18000b3bc  mov     [rsp+278h+Arguments], r15; Arguments
0x18000b3c1  mov     r8d, ebp; dwMessageId
0x18000b3c4  mov     [rsp+278h+nSize], 100h; nSize
0x18000b3cc  mov     r9d, 400h; dwLanguageId
0x18000b3d2  xor     edx, edx; lpSource
0x18000b3d4  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000b3d9  mov     ecx, 1200h; dwFlags
0x18000b3de  call    cs:__imp_FormatMessageW
0x18000b3e4  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000b3e8  lea     rsi, [r14+rsi*2]
0x18000b3ec  mov     rax, [rbx+88h]
0x18000b3f3  mov     rdx, rsi; unsigned __int16 *
0x18000b3f6  mov     rcx, [rbx+80h]
0x18000b3fd  test    r9, r9
0x18000b400  jz      short loc_18000B424
0x18000b402  mov     [rsp+278h+Arguments], rax
0x18000b407  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b40e  mov     eax, [rbx+40h]
0x18000b411  mov     qword ptr [rsp+278h+nSize], rcx
0x18000b416  mov     rcx, r14; this
0x18000b419  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b41d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b422  jmp     short loc_18000B43B
0x18000b424  mov     r9, rcx; unsigned __int16 *
0x18000b427  mov     [rsp+278h+lpBuffer], rax
0x18000b42c  mov     rcx, r14; this
0x18000b42f  lea     r8, aHsP; "%hs!%p: "
0x18000b436  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b43b  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000b442  mov     r14, rax
0x18000b445  test    r9, r9
0x18000b448  jz      short loc_18000B45F
0x18000b44a  lea     r8, aCallerP; "(caller: %p) "
0x18000b451  mov     rdx, rsi; unsigned __int16 *
0x18000b454  mov     rcx, rax; this
0x18000b457  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b45c  mov     r14, rax
0x18000b45f  call    cs:__imp_GetCurrentThreadId
0x18000b465  lea     rcx, [rsp+278h+Buffer]
0x18000b46a  mov     r9, rdi; unsigned __int16 *
0x18000b46d  mov     [rsp+278h+var_240], rcx
0x18000b472  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b479  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b47d  mov     rdx, rsi; unsigned __int16 *
0x18000b480  mov     [rsp+278h+nSize], eax
0x18000b484  mov     rcx, r14; this
0x18000b487  mov     eax, [rbx+44h]
0x18000b48a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b48e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b493  cmp     [rbx+18h], r15
0x18000b497  jnz     short loc_18000B4A9
0x18000b499  cmp     [rbx+48h], r15
0x18000b49d  jnz     short loc_18000B4A9
0x18000b49f  cmp     [rbx+30h], r15
0x18000b4a3  jz      loc_18000B539
0x18000b4a9  lea     r8, asc_180016C38; "    "
0x18000b4b0  mov     rdx, rsi; unsigned __int16 *
0x18000b4b3  mov     rcx, rax; this
0x18000b4b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b4bb  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000b4bf  test    r9, r9
0x18000b4c2  jz      short loc_18000B4D6
0x18000b4c4  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b4cb  mov     rdx, rsi; unsigned __int16 *
0x18000b4ce  mov     rcx, rax; this
0x18000b4d1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b4d6  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000b4da  test    r9, r9
0x18000b4dd  jz      short loc_18000B4F1
0x18000b4df  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b4e6  mov     rdx, rsi; unsigned __int16 *
0x18000b4e9  mov     rcx, rax; this
0x18000b4ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b4f1  mov     rcx, [rbx+28h]
0x18000b4f5  mov     rdx, rsi; unsigned __int16 *
0x18000b4f8  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000b4fc  test    rcx, rcx
0x18000b4ff  jz      short loc_18000B517
0x18000b501  mov     [rsp+278h+lpBuffer], rcx
0x18000b506  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b50d  mov     rcx, rax; this
0x18000b510  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b515  jmp     short loc_18000B539
0x18000b517  mov     rcx, rax; this
0x18000b51a  test    r9, r9
0x18000b51d  jz      short loc_18000B52D
0x18000b51f  lea     r8, aHs; "[%hs]\n"
0x18000b526  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b52b  jmp     short loc_18000B539
0x18000b52d  lea     r8, asc_180016CB0; "\n"
0x18000b534  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b539  xor     eax, eax
0x18000b53b  mov     rcx, [rsp+278h+var_38]
0x18000b543  xor     rcx, rsp; StackCookie
0x18000b546  call    __security_check_cookie
0x18000b54b  mov     rbx, [rsp+278h+arg_18]
0x18000b553  add     rsp, 250h
0x18000b55a  pop     r15
0x18000b55c  pop     r14
0x18000b55e  pop     rdi
0x18000b55f  pop     rsi
0x18000b560  pop     rbp
0x18000b561  retn
```
