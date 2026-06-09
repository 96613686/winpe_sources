# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004d34`
- end: `0x180004fea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800059b0`
- `0x180014e78`
- `0x180015cd8`

## callees

- `0x180004d34`
- `0x1800052e0`
- `0x180016c1e`
- `0x180016c50`
- `0x180018010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180004e66`
- `KERNEL32!FormatMessageW` at `0x180004e66`
- `KERNEL32!GetCurrentThreadId` at `0x180004ee7`
- `KERNEL32!GetCurrentThreadId` at `0x180004ee7`

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
          v7 = UserSearchPath;
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
0x180004d34  mov     [rsp+arg_18], rbx
0x180004d39  push    rbp
0x180004d3a  push    rsi
0x180004d3b  push    rdi
0x180004d3c  push    r14
0x180004d3e  push    r15
0x180004d40  sub     rsp, 250h
0x180004d47  mov     rax, cs:__security_cookie
0x180004d4e  xor     rax, rsp
0x180004d51  mov     [rsp+278h+var_38], rax
0x180004d59  mov     rbx, r8
0x180004d5c  mov     rsi, rdx
0x180004d5f  mov     r14, rcx
0x180004d62  xor     r15d, r15d
0x180004d65  test    rdx, rdx
0x180004d68  jz      loc_180004FC1
0x180004d6e  test    rcx, rcx
0x180004d71  jz      loc_180004FC1
0x180004d77  mov     [rcx], r15w
0x180004d7b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d82  test    rax, rax
0x180004d85  jz      short loc_180004DA8
0x180004d87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004d8e  jz      short loc_180004DA8
0x180004d90  mov     r8, rdx
0x180004d93  mov     rdx, rcx
0x180004d96  mov     rcx, rbx
0x180004d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9e  cmp     [r14], r15w
0x180004da2  jnz     loc_180004FC1
0x180004da8  mov     ecx, [rbx]
0x180004daa  mov     bpl, 8
0x180004dad  test    ecx, ecx
0x180004daf  jz      short loc_180004DFA
0x180004db1  sub     ecx, 1
0x180004db4  jz      short loc_180004DE2
0x180004db6  sub     ecx, 1
0x180004db9  jz      short loc_180004DD2
0x180004dbb  cmp     ecx, 1
0x180004dbe  jz      short loc_180004DC9
0x180004dc0  lea     rdi, UserSearchPath
0x180004dc7  jmp     short loc_180004E01
0x180004dc9  lea     rdi, aFailfast; "FailFast"
0x180004dd0  jmp     short loc_180004E01
0x180004dd2  lea     rax, aLoghr; "LogHr"
0x180004dd9  lea     rdi, aLognt; "LogNt"
0x180004de0  jmp     short loc_180004DF0
0x180004de2  lea     rax, aReturnhr; "ReturnHr"
0x180004de9  lea     rdi, aReturnnt; "ReturnNt"
0x180004df0  test    [rbx+4], bpl
0x180004df4  cmovz   rdi, rax
0x180004df8  jmp     short loc_180004E01
0x180004dfa  lea     rdi, aException; "Exception"
0x180004e01  xor     edx, edx; Val
0x180004e03  mov     r8d, 200h; Size
0x180004e09  lea     rcx, [rsp+278h+Buffer]; void *
0x180004e0e  call    memset_0
0x180004e13  test    [rbx+4], bpl
0x180004e17  jz      short loc_180004E3C
0x180004e19  mov     ebp, [rbx+0Ch]
0x180004e1c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004e23  test    rax, rax
0x180004e26  jz      short loc_180004E6C
0x180004e28  mov     r8d, 100h
0x180004e2e  lea     rdx, [rsp+278h+Buffer]
0x180004e33  mov     ecx, ebp
0x180004e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e3a  jmp     short loc_180004E6C
0x180004e3c  mov     ebp, [rbx+8]
0x180004e3f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004e44  mov     [rsp+278h+nSize], 100h; nSize
0x180004e4c  lea     rax, [rsp+278h+Buffer]
0x180004e51  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004e56  mov     r9d, 400h; dwLanguageId
0x180004e5c  mov     r8d, ebp; dwMessageId
0x180004e5f  xor     edx, edx; lpSource
0x180004e61  mov     ecx, 1200h; dwFlags
0x180004e66  call    cs:__imp_FormatMessageW
0x180004e6c  lea     rsi, [r14+rsi*2]
0x180004e70  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004e74  mov     rax, [rbx+88h]
0x180004e7b  mov     rcx, [rbx+80h]
0x180004e82  mov     rdx, rsi; unsigned __int16 *
0x180004e85  test    r9, r9
0x180004e88  jz      short loc_180004EAC
0x180004e8a  mov     [rsp+278h+Arguments], rax
0x180004e8f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004e94  mov     eax, [rbx+40h]
0x180004e97  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004e9b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004ea2  mov     rcx, r14; this
0x180004ea5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004eaa  jmp     short loc_180004EC3
0x180004eac  mov     [rsp+278h+lpBuffer], rax
0x180004eb1  mov     r9, rcx; unsigned __int16 *
0x180004eb4  lea     r8, aHsP; "%hs!%p: "
0x180004ebb  mov     rcx, r14; this
0x180004ebe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ec3  mov     r14, rax
0x180004ec6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004ecd  test    r9, r9
0x180004ed0  jz      short loc_180004EE7
0x180004ed2  lea     r8, aCallerP; "(caller: %p) "
0x180004ed9  mov     rdx, rsi; unsigned __int16 *
0x180004edc  mov     rcx, rax; this
0x180004edf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ee4  mov     r14, rax
0x180004ee7  call    cs:__imp_GetCurrentThreadId
0x180004eed  lea     rcx, [rsp+278h+Buffer]
0x180004ef2  mov     [rsp+278h+var_240], rcx
0x180004ef7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004efb  mov     [rsp+278h+nSize], eax
0x180004eff  mov     eax, [rbx+44h]
0x180004f02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004f06  mov     r9, rdi; unsigned __int16 *
0x180004f09  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004f10  mov     rdx, rsi; unsigned __int16 *
0x180004f13  mov     rcx, r14; this
0x180004f16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f1b  cmp     [rbx+18h], r15
0x180004f1f  jnz     short loc_180004F31
0x180004f21  cmp     [rbx+48h], r15
0x180004f25  jnz     short loc_180004F31
0x180004f27  cmp     [rbx+30h], r15
0x180004f2b  jz      loc_180004FC1
0x180004f31  lea     r8, asc_18001AE90; "    "
0x180004f38  mov     rdx, rsi; unsigned __int16 *
0x180004f3b  mov     rcx, rax; this
0x180004f3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f43  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004f47  test    r9, r9
0x180004f4a  jz      short loc_180004F5E
0x180004f4c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004f53  mov     rdx, rsi; unsigned __int16 *
0x180004f56  mov     rcx, rax; this
0x180004f59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f5e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004f62  test    r9, r9
0x180004f65  jz      short loc_180004F79
0x180004f67  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004f6e  mov     rdx, rsi; unsigned __int16 *
0x180004f71  mov     rcx, rax; this
0x180004f74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f79  mov     rcx, [rbx+28h]
0x180004f7d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004f81  mov     rdx, rsi; unsigned __int16 *
0x180004f84  test    rcx, rcx
0x180004f87  jz      short loc_180004F9F
0x180004f89  mov     [rsp+278h+lpBuffer], rcx
0x180004f8e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004f95  mov     rcx, rax; this
0x180004f98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f9d  jmp     short loc_180004FC1
0x180004f9f  mov     rcx, rax; this
0x180004fa2  test    r9, r9
0x180004fa5  jz      short loc_180004FB5
0x180004fa7  lea     r8, aHs; "[%hs]\n"
0x180004fae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fb3  jmp     short loc_180004FC1
0x180004fb5  lea     r8, asc_18001AF08; "\n"
0x180004fbc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fc1  xor     eax, eax
0x180004fc3  mov     rcx, [rsp+278h+var_38]
0x180004fcb  xor     rcx, rsp; StackCookie
0x180004fce  call    __security_check_cookie
0x180004fd3  mov     rbx, [rsp+278h+arg_18]
0x180004fdb  add     rsp, 250h
0x180004fe2  pop     r15
0x180004fe4  pop     r14
0x180004fe6  pop     rdi
0x180004fe7  pop     rsi
0x180004fe8  pop     rbp
0x180004fe9  retn
```
