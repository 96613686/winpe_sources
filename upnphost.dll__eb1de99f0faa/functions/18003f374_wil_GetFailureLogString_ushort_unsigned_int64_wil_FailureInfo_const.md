# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003f374`
- end: `0x18003f62a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003bef0`
- `0x18003fef0`

## callees

- `0x18003a560`
- `0x18003ae80`
- `0x18003f374`
- `0x1800401f0`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f527`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003f4a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003f4a6`

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
          v8 = (const char *)&qword_180064410;
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
0x18003f374  mov     [rsp+arg_18], rbx
0x18003f379  push    rbp
0x18003f37a  push    rsi
0x18003f37b  push    rdi
0x18003f37c  push    r14
0x18003f37e  push    r15
0x18003f380  sub     rsp, 250h
0x18003f387  mov     rax, cs:__security_cookie
0x18003f38e  xor     rax, rsp
0x18003f391  mov     [rsp+278h+var_38], rax
0x18003f399  xor     r15d, r15d
0x18003f39c  mov     rbx, r8
0x18003f39f  mov     rsi, rdx
0x18003f3a2  mov     r14, rcx
0x18003f3a5  test    rdx, rdx
0x18003f3a8  jz      loc_18003F601
0x18003f3ae  test    rcx, rcx
0x18003f3b1  jz      loc_18003F601
0x18003f3b7  mov     rax, cs:g_pfnResultLoggingCallback
0x18003f3be  mov     [rcx], r15w
0x18003f3c2  test    rax, rax
0x18003f3c5  jz      short loc_18003F3E8
0x18003f3c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003f3ce  jz      short loc_18003F3E8
0x18003f3d0  mov     r8, rdx
0x18003f3d3  mov     rdx, rcx
0x18003f3d6  mov     rcx, rbx
0x18003f3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3de  cmp     [r14], r15w
0x18003f3e2  jnz     loc_18003F601
0x18003f3e8  mov     ecx, [rbx]
0x18003f3ea  mov     bpl, 8
0x18003f3ed  test    ecx, ecx
0x18003f3ef  jz      short loc_18003F43A
0x18003f3f1  sub     ecx, 1
0x18003f3f4  jz      short loc_18003F422
0x18003f3f6  sub     ecx, 1
0x18003f3f9  jz      short loc_18003F412
0x18003f3fb  cmp     ecx, 1
0x18003f3fe  jz      short loc_18003F409
0x18003f400  lea     rdi, qword_180064410
0x18003f407  jmp     short loc_18003F441
0x18003f409  lea     rdi, aFailfast; "FailFast"
0x18003f410  jmp     short loc_18003F441
0x18003f412  lea     rax, aLoghr; "LogHr"
0x18003f419  lea     rdi, aLognt; "LogNt"
0x18003f420  jmp     short loc_18003F430
0x18003f422  lea     rax, aReturnhr; "ReturnHr"
0x18003f429  lea     rdi, aReturnnt; "ReturnNt"
0x18003f430  test    [rbx+4], bpl
0x18003f434  cmovz   rdi, rax
0x18003f438  jmp     short loc_18003F441
0x18003f43a  lea     rdi, aException; "Exception"
0x18003f441  xor     edx, edx; Val
0x18003f443  lea     rcx, [rsp+278h+Buffer]; void *
0x18003f448  mov     r8d, 200h; Size
0x18003f44e  call    memset_0
0x18003f453  test    [rbx+4], bpl
0x18003f457  jz      short loc_18003F47C
0x18003f459  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003f460  mov     ebp, [rbx+0Ch]
0x18003f463  test    rax, rax
0x18003f466  jz      short loc_18003F4AC
0x18003f468  mov     r8d, 100h
0x18003f46e  lea     rdx, [rsp+278h+Buffer]
0x18003f473  mov     ecx, ebp
0x18003f475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f47a  jmp     short loc_18003F4AC
0x18003f47c  mov     ebp, [rbx+8]
0x18003f47f  lea     rax, [rsp+278h+Buffer]
0x18003f484  mov     [rsp+278h+Arguments], r15; Arguments
0x18003f489  mov     r8d, ebp; dwMessageId
0x18003f48c  mov     [rsp+278h+nSize], 100h; nSize
0x18003f494  mov     r9d, 400h; dwLanguageId
0x18003f49a  xor     edx, edx; lpSource
0x18003f49c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003f4a1  mov     ecx, 1200h; dwFlags
0x18003f4a6  call    cs:__imp_FormatMessageW
0x18003f4ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003f4b0  lea     rsi, [r14+rsi*2]
0x18003f4b4  mov     rax, [rbx+88h]
0x18003f4bb  mov     rdx, rsi; unsigned __int16 *
0x18003f4be  mov     rcx, [rbx+80h]
0x18003f4c5  test    r9, r9
0x18003f4c8  jz      short loc_18003F4EC
0x18003f4ca  mov     [rsp+278h+Arguments], rax
0x18003f4cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003f4d6  mov     eax, [rbx+40h]
0x18003f4d9  mov     qword ptr [rsp+278h+nSize], rcx
0x18003f4de  mov     rcx, r14; this
0x18003f4e1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003f4e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f4ea  jmp     short loc_18003F503
0x18003f4ec  mov     r9, rcx; unsigned __int16 *
0x18003f4ef  mov     [rsp+278h+lpBuffer], rax
0x18003f4f4  mov     rcx, r14; this
0x18003f4f7  lea     r8, aHsP; "%hs!%p: "
0x18003f4fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f503  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003f50a  mov     r14, rax
0x18003f50d  test    r9, r9
0x18003f510  jz      short loc_18003F527
0x18003f512  lea     r8, aCallerP; "(caller: %p) "
0x18003f519  mov     rdx, rsi; unsigned __int16 *
0x18003f51c  mov     rcx, rax; this
0x18003f51f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f524  mov     r14, rax
0x18003f527  call    cs:__imp_GetCurrentThreadId
0x18003f52d  lea     rcx, [rsp+278h+Buffer]
0x18003f532  mov     r9, rdi; unsigned __int16 *
0x18003f535  mov     [rsp+278h+var_240], rcx
0x18003f53a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003f541  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003f545  mov     rdx, rsi; unsigned __int16 *
0x18003f548  mov     [rsp+278h+nSize], eax
0x18003f54c  mov     rcx, r14; this
0x18003f54f  mov     eax, [rbx+44h]
0x18003f552  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003f556  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f55b  cmp     [rbx+18h], r15
0x18003f55f  jnz     short loc_18003F571
0x18003f561  cmp     [rbx+48h], r15
0x18003f565  jnz     short loc_18003F571
0x18003f567  cmp     [rbx+30h], r15
0x18003f56b  jz      loc_18003F601
0x18003f571  lea     r8, asc_180064860; "    "
0x18003f578  mov     rdx, rsi; unsigned __int16 *
0x18003f57b  mov     rcx, rax; this
0x18003f57e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f583  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003f587  test    r9, r9
0x18003f58a  jz      short loc_18003F59E
0x18003f58c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003f593  mov     rdx, rsi; unsigned __int16 *
0x18003f596  mov     rcx, rax; this
0x18003f599  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f59e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003f5a2  test    r9, r9
0x18003f5a5  jz      short loc_18003F5B9
0x18003f5a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003f5ae  mov     rdx, rsi; unsigned __int16 *
0x18003f5b1  mov     rcx, rax; this
0x18003f5b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f5b9  mov     rcx, [rbx+28h]
0x18003f5bd  mov     rdx, rsi; unsigned __int16 *
0x18003f5c0  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003f5c4  test    rcx, rcx
0x18003f5c7  jz      short loc_18003F5DF
0x18003f5c9  mov     [rsp+278h+lpBuffer], rcx
0x18003f5ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003f5d5  mov     rcx, rax; this
0x18003f5d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f5dd  jmp     short loc_18003F601
0x18003f5df  mov     rcx, rax; this
0x18003f5e2  test    r9, r9
0x18003f5e5  jz      short loc_18003F5F5
0x18003f5e7  lea     r8, aHs; "[%hs]\n"
0x18003f5ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f5f3  jmp     short loc_18003F601
0x18003f5f5  lea     r8, asc_1800648D8; "\n"
0x18003f5fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f601  xor     eax, eax
0x18003f603  mov     rcx, [rsp+278h+var_38]
0x18003f60b  xor     rcx, rsp; StackCookie
0x18003f60e  call    __security_check_cookie
0x18003f613  mov     rbx, [rsp+278h+arg_18]
0x18003f61b  add     rsp, 250h
0x18003f622  pop     r15
0x18003f624  pop     r14
0x18003f626  pop     rdi
0x18003f627  pop     rsi
0x18003f628  pop     rbp
0x18003f629  retn
```
