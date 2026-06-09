# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180027d34`
- end: `0x180027ff7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002636c`
- `0x18002832c`

## callees

- `0x180027d34`
- `0x18002864c`
- `0x180032be6`
- `0x180032c20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027eed`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180027e66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180027e66`

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
          v8 = (const char *)&byte_1800416E1;
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
0x180027d34  mov     [rsp+arg_18], rbx
0x180027d39  push    rbp
0x180027d3a  push    rsi
0x180027d3b  push    rdi
0x180027d3c  push    r14
0x180027d3e  push    r15
0x180027d40  sub     rsp, 250h
0x180027d47  mov     rax, cs:__security_cookie
0x180027d4e  xor     rax, rsp
0x180027d51  mov     [rsp+278h+var_38], rax
0x180027d59  xor     r15d, r15d
0x180027d5c  mov     rbx, r8
0x180027d5f  mov     rsi, rdx
0x180027d62  mov     r14, rcx
0x180027d65  test    rdx, rdx
0x180027d68  jz      loc_180027FCD
0x180027d6e  test    rcx, rcx
0x180027d71  jz      loc_180027FCD
0x180027d77  mov     rax, cs:g_pfnResultLoggingCallback
0x180027d7e  mov     [rcx], r15w
0x180027d82  test    rax, rax
0x180027d85  jz      short loc_180027DA8
0x180027d87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180027d8e  jz      short loc_180027DA8
0x180027d90  mov     r8, rdx
0x180027d93  mov     rdx, rcx
0x180027d96  mov     rcx, rbx
0x180027d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d9e  cmp     [r14], r15w
0x180027da2  jnz     loc_180027FCD
0x180027da8  mov     ecx, [rbx]
0x180027daa  mov     bpl, 8
0x180027dad  test    ecx, ecx
0x180027daf  jz      short loc_180027DFA
0x180027db1  sub     ecx, 1
0x180027db4  jz      short loc_180027DE2
0x180027db6  sub     ecx, 1
0x180027db9  jz      short loc_180027DD2
0x180027dbb  cmp     ecx, 1
0x180027dbe  jz      short loc_180027DC9
0x180027dc0  lea     rdi, byte_1800416E1
0x180027dc7  jmp     short loc_180027E01
0x180027dc9  lea     rdi, aFailfast; "FailFast"
0x180027dd0  jmp     short loc_180027E01
0x180027dd2  lea     rax, aLoghr; "LogHr"
0x180027dd9  lea     rdi, aLognt; "LogNt"
0x180027de0  jmp     short loc_180027DF0
0x180027de2  lea     rax, aReturnhr; "ReturnHr"
0x180027de9  lea     rdi, aReturnnt; "ReturnNt"
0x180027df0  test    [rbx+4], bpl
0x180027df4  cmovz   rdi, rax
0x180027df8  jmp     short loc_180027E01
0x180027dfa  lea     rdi, aException; "Exception"
0x180027e01  xor     edx, edx; Val
0x180027e03  lea     rcx, [rsp+278h+Buffer]; void *
0x180027e08  mov     r8d, 200h; Size
0x180027e0e  call    memset_0
0x180027e13  test    [rbx+4], bpl
0x180027e17  jz      short loc_180027E3C
0x180027e19  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180027e20  mov     ebp, [rbx+0Ch]
0x180027e23  test    rax, rax
0x180027e26  jz      short loc_180027E72
0x180027e28  mov     r8d, 100h
0x180027e2e  lea     rdx, [rsp+278h+Buffer]
0x180027e33  mov     ecx, ebp
0x180027e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e3a  jmp     short loc_180027E72
0x180027e3c  mov     ebp, [rbx+8]
0x180027e3f  lea     rax, [rsp+278h+Buffer]
0x180027e44  mov     [rsp+278h+Arguments], r15; Arguments
0x180027e49  mov     r8d, ebp; dwMessageId
0x180027e4c  mov     [rsp+278h+nSize], 100h; nSize
0x180027e54  mov     r9d, 400h; dwLanguageId
0x180027e5a  xor     edx, edx; lpSource
0x180027e5c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180027e61  mov     ecx, 1200h; dwFlags
0x180027e66  call    cs:__imp_FormatMessageW
0x180027e6d  nop     dword ptr [rax+rax+00h]
0x180027e72  mov     r9, [rbx+38h]; unsigned __int16 *
0x180027e76  lea     rsi, [r14+rsi*2]
0x180027e7a  mov     rax, [rbx+88h]
0x180027e81  mov     rdx, rsi; unsigned __int16 *
0x180027e84  mov     rcx, [rbx+80h]
0x180027e8b  test    r9, r9
0x180027e8e  jz      short loc_180027EB2
0x180027e90  mov     [rsp+278h+Arguments], rax
0x180027e95  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180027e9c  mov     eax, [rbx+40h]
0x180027e9f  mov     qword ptr [rsp+278h+nSize], rcx
0x180027ea4  mov     rcx, r14; this
0x180027ea7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180027eab  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027eb0  jmp     short loc_180027EC9
0x180027eb2  mov     r9, rcx; unsigned __int16 *
0x180027eb5  mov     [rsp+278h+lpBuffer], rax
0x180027eba  mov     rcx, r14; this
0x180027ebd  lea     r8, aHsP; "%hs!%p: "
0x180027ec4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027ec9  mov     r9, [rbx+90h]; unsigned __int16 *
0x180027ed0  mov     r14, rax
0x180027ed3  test    r9, r9
0x180027ed6  jz      short loc_180027EED
0x180027ed8  lea     r8, aCallerP; "(caller: %p) "
0x180027edf  mov     rdx, rsi; unsigned __int16 *
0x180027ee2  mov     rcx, rax; this
0x180027ee5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027eea  mov     r14, rax
0x180027eed  call    cs:__imp_GetCurrentThreadId
0x180027ef4  nop     dword ptr [rax+rax+00h]
0x180027ef9  lea     rcx, [rsp+278h+Buffer]
0x180027efe  mov     r9, rdi; unsigned __int16 *
0x180027f01  mov     [rsp+278h+var_240], rcx
0x180027f06  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180027f0d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180027f11  mov     rdx, rsi; unsigned __int16 *
0x180027f14  mov     [rsp+278h+nSize], eax
0x180027f18  mov     rcx, r14; this
0x180027f1b  mov     eax, [rbx+44h]
0x180027f1e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180027f22  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027f27  cmp     [rbx+18h], r15
0x180027f2b  jnz     short loc_180027F3D
0x180027f2d  cmp     [rbx+48h], r15
0x180027f31  jnz     short loc_180027F3D
0x180027f33  cmp     [rbx+30h], r15
0x180027f37  jz      loc_180027FCD
0x180027f3d  lea     r8, asc_18004A598; "    "
0x180027f44  mov     rdx, rsi; unsigned __int16 *
0x180027f47  mov     rcx, rax; this
0x180027f4a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027f4f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180027f53  test    r9, r9
0x180027f56  jz      short loc_180027F6A
0x180027f58  lea     r8, aMsgWs; "Msg:[%ws] "
0x180027f5f  mov     rdx, rsi; unsigned __int16 *
0x180027f62  mov     rcx, rax; this
0x180027f65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027f6a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180027f6e  test    r9, r9
0x180027f71  jz      short loc_180027F85
0x180027f73  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180027f7a  mov     rdx, rsi; unsigned __int16 *
0x180027f7d  mov     rcx, rax; this
0x180027f80  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027f85  mov     rcx, [rbx+28h]
0x180027f89  mov     rdx, rsi; unsigned __int16 *
0x180027f8c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180027f90  test    rcx, rcx
0x180027f93  jz      short loc_180027FAB
0x180027f95  mov     [rsp+278h+lpBuffer], rcx
0x180027f9a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180027fa1  mov     rcx, rax; this
0x180027fa4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027fa9  jmp     short loc_180027FCD
0x180027fab  mov     rcx, rax; this
0x180027fae  test    r9, r9
0x180027fb1  jz      short loc_180027FC1
0x180027fb3  lea     r8, aHs; "[%hs]\n"
0x180027fba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027fbf  jmp     short loc_180027FCD
0x180027fc1  lea     r8, asc_18004A610; "\n"
0x180027fc8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027fcd  xor     eax, eax
0x180027fcf  mov     rcx, [rsp+278h+var_38]
0x180027fd7  xor     rcx, rsp; StackCookie
0x180027fda  call    __security_check_cookie
0x180027fdf  mov     rbx, [rsp+278h+arg_18]
0x180027fe7  add     rsp, 250h
0x180027fee  pop     r15
0x180027ff0  pop     r14
0x180027ff2  pop     rdi
0x180027ff3  pop     rsi
0x180027ff4  pop     rbp
0x180027ff5  retn
```
