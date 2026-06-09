# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180021c08`
- end: `0x180021ebe`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180016a98`
- `0x1800220d8`
- `0x180022c00`

## callees

- `0x180013c10`
- `0x18001ff00`
- `0x180020d34`
- `0x180021c08`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021dbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021dbb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180021d3a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180021d3a`

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
          v7 = (const char *)&byte_180039553;
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
0x180021c08  mov     [rsp+arg_18], rbx
0x180021c0d  push    rbp
0x180021c0e  push    rsi
0x180021c0f  push    rdi
0x180021c10  push    r14
0x180021c12  push    r15
0x180021c14  sub     rsp, 250h
0x180021c1b  mov     rax, cs:__security_cookie
0x180021c22  xor     rax, rsp
0x180021c25  mov     [rsp+278h+var_38], rax
0x180021c2d  mov     rbx, r8
0x180021c30  mov     rsi, rdx
0x180021c33  mov     r14, rcx
0x180021c36  xor     r15d, r15d
0x180021c39  test    rdx, rdx
0x180021c3c  jz      loc_180021E95
0x180021c42  test    rcx, rcx
0x180021c45  jz      loc_180021E95
0x180021c4b  mov     [rcx], r15w
0x180021c4f  mov     rax, cs:g_pfnResultLoggingCallback
0x180021c56  test    rax, rax
0x180021c59  jz      short loc_180021C7C
0x180021c5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180021c62  jz      short loc_180021C7C
0x180021c64  mov     r8, rdx
0x180021c67  mov     rdx, rcx
0x180021c6a  mov     rcx, rbx
0x180021c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c72  cmp     [r14], r15w
0x180021c76  jnz     loc_180021E95
0x180021c7c  mov     ecx, [rbx]
0x180021c7e  mov     bpl, 8
0x180021c81  test    ecx, ecx
0x180021c83  jz      short loc_180021CCE
0x180021c85  sub     ecx, 1
0x180021c88  jz      short loc_180021CB6
0x180021c8a  sub     ecx, 1
0x180021c8d  jz      short loc_180021CA6
0x180021c8f  cmp     ecx, 1
0x180021c92  jz      short loc_180021C9D
0x180021c94  lea     rdi, byte_180039553
0x180021c9b  jmp     short loc_180021CD5
0x180021c9d  lea     rdi, aFailfast; "FailFast"
0x180021ca4  jmp     short loc_180021CD5
0x180021ca6  lea     rax, aLoghr; "LogHr"
0x180021cad  lea     rdi, aLognt; "LogNt"
0x180021cb4  jmp     short loc_180021CC4
0x180021cb6  lea     rax, aReturnhr; "ReturnHr"
0x180021cbd  lea     rdi, aReturnnt; "ReturnNt"
0x180021cc4  test    [rbx+4], bpl
0x180021cc8  cmovz   rdi, rax
0x180021ccc  jmp     short loc_180021CD5
0x180021cce  lea     rdi, aException; "Exception"
0x180021cd5  xor     edx, edx; Val
0x180021cd7  mov     r8d, 200h; Size
0x180021cdd  lea     rcx, [rsp+278h+Buffer]; void *
0x180021ce2  call    memset_0
0x180021ce7  test    [rbx+4], bpl
0x180021ceb  jz      short loc_180021D10
0x180021ced  mov     ebp, [rbx+0Ch]
0x180021cf0  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180021cf7  test    rax, rax
0x180021cfa  jz      short loc_180021D40
0x180021cfc  mov     r8d, 100h
0x180021d02  lea     rdx, [rsp+278h+Buffer]
0x180021d07  mov     ecx, ebp
0x180021d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d0e  jmp     short loc_180021D40
0x180021d10  mov     ebp, [rbx+8]
0x180021d13  mov     [rsp+278h+Arguments], r15; Arguments
0x180021d18  mov     [rsp+278h+nSize], 100h; nSize
0x180021d20  lea     rax, [rsp+278h+Buffer]
0x180021d25  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180021d2a  mov     r9d, 400h; dwLanguageId
0x180021d30  mov     r8d, ebp; dwMessageId
0x180021d33  xor     edx, edx; lpSource
0x180021d35  mov     ecx, 1200h; dwFlags
0x180021d3a  call    cs:__imp_FormatMessageW
0x180021d40  lea     rsi, [r14+rsi*2]
0x180021d44  mov     r9, [rbx+38h]; unsigned __int16 *
0x180021d48  mov     rax, [rbx+88h]
0x180021d4f  mov     rcx, [rbx+80h]
0x180021d56  mov     rdx, rsi; unsigned __int16 *
0x180021d59  test    r9, r9
0x180021d5c  jz      short loc_180021D80
0x180021d5e  mov     [rsp+278h+Arguments], rax
0x180021d63  mov     qword ptr [rsp+278h+nSize], rcx
0x180021d68  mov     eax, [rbx+40h]
0x180021d6b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180021d6f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180021d76  mov     rcx, r14; this
0x180021d79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021d7e  jmp     short loc_180021D97
0x180021d80  mov     [rsp+278h+lpBuffer], rax
0x180021d85  mov     r9, rcx; unsigned __int16 *
0x180021d88  lea     r8, aHsP; "%hs!%p: "
0x180021d8f  mov     rcx, r14; this
0x180021d92  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021d97  mov     r14, rax
0x180021d9a  mov     r9, [rbx+90h]; unsigned __int16 *
0x180021da1  test    r9, r9
0x180021da4  jz      short loc_180021DBB
0x180021da6  lea     r8, aCallerP; "(caller: %p) "
0x180021dad  mov     rdx, rsi; unsigned __int16 *
0x180021db0  mov     rcx, rax; this
0x180021db3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021db8  mov     r14, rax
0x180021dbb  call    cs:__imp_GetCurrentThreadId
0x180021dc1  lea     rcx, [rsp+278h+Buffer]
0x180021dc6  mov     [rsp+278h+var_240], rcx
0x180021dcb  mov     dword ptr [rsp+278h+Arguments], ebp
0x180021dcf  mov     [rsp+278h+nSize], eax
0x180021dd3  mov     eax, [rbx+44h]
0x180021dd6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180021dda  mov     r9, rdi; unsigned __int16 *
0x180021ddd  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180021de4  mov     rdx, rsi; unsigned __int16 *
0x180021de7  mov     rcx, r14; this
0x180021dea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021def  cmp     [rbx+18h], r15
0x180021df3  jnz     short loc_180021E05
0x180021df5  cmp     [rbx+48h], r15
0x180021df9  jnz     short loc_180021E05
0x180021dfb  cmp     [rbx+30h], r15
0x180021dff  jz      loc_180021E95
0x180021e05  lea     r8, asc_180039658; "    "
0x180021e0c  mov     rdx, rsi; unsigned __int16 *
0x180021e0f  mov     rcx, rax; this
0x180021e12  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021e17  mov     r9, [rbx+18h]; unsigned __int16 *
0x180021e1b  test    r9, r9
0x180021e1e  jz      short loc_180021E32
0x180021e20  lea     r8, aMsgWs; "Msg:[%ws] "
0x180021e27  mov     rdx, rsi; unsigned __int16 *
0x180021e2a  mov     rcx, rax; this
0x180021e2d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021e32  mov     r9, [rbx+48h]; unsigned __int16 *
0x180021e36  test    r9, r9
0x180021e39  jz      short loc_180021E4D
0x180021e3b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180021e42  mov     rdx, rsi; unsigned __int16 *
0x180021e45  mov     rcx, rax; this
0x180021e48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021e4d  mov     rcx, [rbx+28h]
0x180021e51  mov     r9, [rbx+30h]; unsigned __int16 *
0x180021e55  mov     rdx, rsi; unsigned __int16 *
0x180021e58  test    rcx, rcx
0x180021e5b  jz      short loc_180021E73
0x180021e5d  mov     [rsp+278h+lpBuffer], rcx
0x180021e62  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180021e69  mov     rcx, rax; this
0x180021e6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021e71  jmp     short loc_180021E95
0x180021e73  mov     rcx, rax; this
0x180021e76  test    r9, r9
0x180021e79  jz      short loc_180021E89
0x180021e7b  lea     r8, aHs; "[%hs]\n"
0x180021e82  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021e87  jmp     short loc_180021E95
0x180021e89  lea     r8, asc_1800396D0; "\n"
0x180021e90  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021e95  xor     eax, eax
0x180021e97  mov     rcx, [rsp+278h+var_38]
0x180021e9f  xor     rcx, rsp; StackCookie
0x180021ea2  call    __security_check_cookie
0x180021ea7  mov     rbx, [rsp+278h+arg_18]
0x180021eaf  add     rsp, 250h
0x180021eb6  pop     r15
0x180021eb8  pop     r14
0x180021eba  pop     rdi
0x180021ebb  pop     rsi
0x180021ebc  pop     rbp
0x180021ebd  retn
```
