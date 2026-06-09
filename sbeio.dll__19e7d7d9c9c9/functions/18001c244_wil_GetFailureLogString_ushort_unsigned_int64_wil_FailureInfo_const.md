# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001c244`
- end: `0x18001c4fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800146cc`
- `0x18001493c`
- `0x18001d4e4`

## callees

- `0x1800015f0`
- `0x180001f1c`
- `0x18001c244`
- `0x18001d7e4`
- `0x18002b010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18001c376`
- `KERNEL32!FormatMessageW` at `0x18001c376`
- `KERNEL32!GetCurrentThreadId` at `0x18001c3f7`
- `KERNEL32!GetCurrentThreadId` at `0x18001c3f7`

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
          v8 = (const char *)&byte_18002EF5F;
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
0x18001c244  mov     [rsp+arg_18], rbx
0x18001c249  push    rbp
0x18001c24a  push    rsi
0x18001c24b  push    rdi
0x18001c24c  push    r14
0x18001c24e  push    r15
0x18001c250  sub     rsp, 250h
0x18001c257  mov     rax, cs:__security_cookie
0x18001c25e  xor     rax, rsp
0x18001c261  mov     [rsp+278h+var_38], rax
0x18001c269  xor     r15d, r15d
0x18001c26c  mov     rbx, r8
0x18001c26f  mov     rsi, rdx
0x18001c272  mov     r14, rcx
0x18001c275  test    rdx, rdx
0x18001c278  jz      loc_18001C4D1
0x18001c27e  test    rcx, rcx
0x18001c281  jz      loc_18001C4D1
0x18001c287  mov     rax, cs:g_pfnResultLoggingCallback
0x18001c28e  mov     [rcx], r15w
0x18001c292  test    rax, rax
0x18001c295  jz      short loc_18001C2B8
0x18001c297  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001c29e  jz      short loc_18001C2B8
0x18001c2a0  mov     r8, rdx
0x18001c2a3  mov     rdx, rcx
0x18001c2a6  mov     rcx, rbx
0x18001c2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2ae  cmp     [r14], r15w
0x18001c2b2  jnz     loc_18001C4D1
0x18001c2b8  mov     ecx, [rbx]
0x18001c2ba  mov     bpl, 8
0x18001c2bd  test    ecx, ecx
0x18001c2bf  jz      short loc_18001C30A
0x18001c2c1  sub     ecx, 1
0x18001c2c4  jz      short loc_18001C2F2
0x18001c2c6  sub     ecx, 1
0x18001c2c9  jz      short loc_18001C2E2
0x18001c2cb  cmp     ecx, 1
0x18001c2ce  jz      short loc_18001C2D9
0x18001c2d0  lea     rdi, byte_18002EF5F
0x18001c2d7  jmp     short loc_18001C311
0x18001c2d9  lea     rdi, aFailfast; "FailFast"
0x18001c2e0  jmp     short loc_18001C311
0x18001c2e2  lea     rax, aLoghr; "LogHr"
0x18001c2e9  lea     rdi, aLognt; "LogNt"
0x18001c2f0  jmp     short loc_18001C300
0x18001c2f2  lea     rax, aReturnhr; "ReturnHr"
0x18001c2f9  lea     rdi, aReturnnt; "ReturnNt"
0x18001c300  test    [rbx+4], bpl
0x18001c304  cmovz   rdi, rax
0x18001c308  jmp     short loc_18001C311
0x18001c30a  lea     rdi, aException; "Exception"
0x18001c311  xor     edx, edx; Val
0x18001c313  lea     rcx, [rsp+278h+Buffer]; void *
0x18001c318  mov     r8d, 200h; Size
0x18001c31e  call    memset_0
0x18001c323  test    [rbx+4], bpl
0x18001c327  jz      short loc_18001C34C
0x18001c329  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001c330  mov     ebp, [rbx+0Ch]
0x18001c333  test    rax, rax
0x18001c336  jz      short loc_18001C37C
0x18001c338  mov     r8d, 100h
0x18001c33e  lea     rdx, [rsp+278h+Buffer]
0x18001c343  mov     ecx, ebp
0x18001c345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c34a  jmp     short loc_18001C37C
0x18001c34c  mov     ebp, [rbx+8]
0x18001c34f  lea     rax, [rsp+278h+Buffer]
0x18001c354  mov     [rsp+278h+Arguments], r15; Arguments
0x18001c359  mov     r8d, ebp; dwMessageId
0x18001c35c  mov     [rsp+278h+nSize], 100h; nSize
0x18001c364  mov     r9d, 400h; dwLanguageId
0x18001c36a  xor     edx, edx; lpSource
0x18001c36c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001c371  mov     ecx, 1200h; dwFlags
0x18001c376  call    cs:__imp_FormatMessageW
0x18001c37c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001c380  lea     rsi, [r14+rsi*2]
0x18001c384  mov     rax, [rbx+88h]
0x18001c38b  mov     rdx, rsi; unsigned __int16 *
0x18001c38e  mov     rcx, [rbx+80h]
0x18001c395  test    r9, r9
0x18001c398  jz      short loc_18001C3BC
0x18001c39a  mov     [rsp+278h+Arguments], rax
0x18001c39f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001c3a6  mov     eax, [rbx+40h]
0x18001c3a9  mov     qword ptr [rsp+278h+nSize], rcx
0x18001c3ae  mov     rcx, r14; this
0x18001c3b1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001c3b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c3ba  jmp     short loc_18001C3D3
0x18001c3bc  mov     r9, rcx; unsigned __int16 *
0x18001c3bf  mov     [rsp+278h+lpBuffer], rax
0x18001c3c4  mov     rcx, r14; this
0x18001c3c7  lea     r8, aHsP; "%hs!%p: "
0x18001c3ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c3d3  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001c3da  mov     r14, rax
0x18001c3dd  test    r9, r9
0x18001c3e0  jz      short loc_18001C3F7
0x18001c3e2  lea     r8, aCallerP; "(caller: %p) "
0x18001c3e9  mov     rdx, rsi; unsigned __int16 *
0x18001c3ec  mov     rcx, rax; this
0x18001c3ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c3f4  mov     r14, rax
0x18001c3f7  call    cs:__imp_GetCurrentThreadId
0x18001c3fd  lea     rcx, [rsp+278h+Buffer]
0x18001c402  mov     r9, rdi; unsigned __int16 *
0x18001c405  mov     [rsp+278h+var_240], rcx
0x18001c40a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001c411  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001c415  mov     rdx, rsi; unsigned __int16 *
0x18001c418  mov     [rsp+278h+nSize], eax
0x18001c41c  mov     rcx, r14; this
0x18001c41f  mov     eax, [rbx+44h]
0x18001c422  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001c426  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c42b  cmp     [rbx+18h], r15
0x18001c42f  jnz     short loc_18001C441
0x18001c431  cmp     [rbx+48h], r15
0x18001c435  jnz     short loc_18001C441
0x18001c437  cmp     [rbx+30h], r15
0x18001c43b  jz      loc_18001C4D1
0x18001c441  lea     r8, asc_18002F048; "    "
0x18001c448  mov     rdx, rsi; unsigned __int16 *
0x18001c44b  mov     rcx, rax; this
0x18001c44e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c453  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001c457  test    r9, r9
0x18001c45a  jz      short loc_18001C46E
0x18001c45c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001c463  mov     rdx, rsi; unsigned __int16 *
0x18001c466  mov     rcx, rax; this
0x18001c469  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c46e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001c472  test    r9, r9
0x18001c475  jz      short loc_18001C489
0x18001c477  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001c47e  mov     rdx, rsi; unsigned __int16 *
0x18001c481  mov     rcx, rax; this
0x18001c484  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c489  mov     rcx, [rbx+28h]
0x18001c48d  mov     rdx, rsi; unsigned __int16 *
0x18001c490  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001c494  test    rcx, rcx
0x18001c497  jz      short loc_18001C4AF
0x18001c499  mov     [rsp+278h+lpBuffer], rcx
0x18001c49e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001c4a5  mov     rcx, rax; this
0x18001c4a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c4ad  jmp     short loc_18001C4D1
0x18001c4af  mov     rcx, rax; this
0x18001c4b2  test    r9, r9
0x18001c4b5  jz      short loc_18001C4C5
0x18001c4b7  lea     r8, aHs; "[%hs]\n"
0x18001c4be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c4c3  jmp     short loc_18001C4D1
0x18001c4c5  lea     r8, asc_18002F0C0; "\n"
0x18001c4cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001c4d1  xor     eax, eax
0x18001c4d3  mov     rcx, [rsp+278h+var_38]
0x18001c4db  xor     rcx, rsp; StackCookie
0x18001c4de  call    __security_check_cookie
0x18001c4e3  mov     rbx, [rsp+278h+arg_18]
0x18001c4eb  add     rsp, 250h
0x18001c4f2  pop     r15
0x18001c4f4  pop     r14
0x18001c4f6  pop     rdi
0x18001c4f7  pop     rsi
0x18001c4f8  pop     rbp
0x18001c4f9  retn
```
