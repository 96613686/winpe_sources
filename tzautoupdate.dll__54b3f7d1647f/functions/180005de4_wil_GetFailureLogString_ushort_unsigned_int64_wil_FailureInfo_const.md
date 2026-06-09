# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005de4`
- end: `0x18000609a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003868`
- `0x180006ad8`
- `0x18000b840`

## callees

- `0x180005de4`
- `0x180006dd8`
- `0x18001b0f6`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005f16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005f16`

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
          v7 = (const char *)&word_180021DC6;
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
0x180005de4  mov     [rsp+arg_18], rbx
0x180005de9  push    rbp
0x180005dea  push    rsi
0x180005deb  push    rdi
0x180005dec  push    r14
0x180005dee  push    r15
0x180005df0  sub     rsp, 250h
0x180005df7  mov     rax, cs:__security_cookie
0x180005dfe  xor     rax, rsp
0x180005e01  mov     [rsp+278h+var_38], rax
0x180005e09  mov     rbx, r8
0x180005e0c  mov     rsi, rdx
0x180005e0f  mov     r14, rcx
0x180005e12  xor     r15d, r15d
0x180005e15  test    rdx, rdx
0x180005e18  jz      loc_180006071
0x180005e1e  test    rcx, rcx
0x180005e21  jz      loc_180006071
0x180005e27  mov     [rcx], r15w
0x180005e2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e32  test    rax, rax
0x180005e35  jz      short loc_180005E58
0x180005e37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005e3e  jz      short loc_180005E58
0x180005e40  mov     r8, rdx
0x180005e43  mov     rdx, rcx
0x180005e46  mov     rcx, rbx
0x180005e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e4e  cmp     [r14], r15w
0x180005e52  jnz     loc_180006071
0x180005e58  mov     ecx, [rbx]
0x180005e5a  mov     bpl, 8
0x180005e5d  test    ecx, ecx
0x180005e5f  jz      short loc_180005EAA
0x180005e61  sub     ecx, 1
0x180005e64  jz      short loc_180005E92
0x180005e66  sub     ecx, 1
0x180005e69  jz      short loc_180005E82
0x180005e6b  cmp     ecx, 1
0x180005e6e  jz      short loc_180005E79
0x180005e70  lea     rdi, word_180021DC6
0x180005e77  jmp     short loc_180005EB1
0x180005e79  lea     rdi, aFailfast; "FailFast"
0x180005e80  jmp     short loc_180005EB1
0x180005e82  lea     rax, aLoghr; "LogHr"
0x180005e89  lea     rdi, aLognt; "LogNt"
0x180005e90  jmp     short loc_180005EA0
0x180005e92  lea     rax, aReturnhr; "ReturnHr"
0x180005e99  lea     rdi, aReturnnt; "ReturnNt"
0x180005ea0  test    [rbx+4], bpl
0x180005ea4  cmovz   rdi, rax
0x180005ea8  jmp     short loc_180005EB1
0x180005eaa  lea     rdi, aException; "Exception"
0x180005eb1  xor     edx, edx; Val
0x180005eb3  mov     r8d, 200h; Size
0x180005eb9  lea     rcx, [rsp+278h+Buffer]; void *
0x180005ebe  call    memset_0
0x180005ec3  test    [rbx+4], bpl
0x180005ec7  jz      short loc_180005EEC
0x180005ec9  mov     ebp, [rbx+0Ch]
0x180005ecc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005ed3  test    rax, rax
0x180005ed6  jz      short loc_180005F1C
0x180005ed8  mov     r8d, 100h
0x180005ede  lea     rdx, [rsp+278h+Buffer]
0x180005ee3  mov     ecx, ebp
0x180005ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eea  jmp     short loc_180005F1C
0x180005eec  mov     ebp, [rbx+8]
0x180005eef  mov     [rsp+278h+Arguments], r15; Arguments
0x180005ef4  mov     [rsp+278h+nSize], 100h; nSize
0x180005efc  lea     rax, [rsp+278h+Buffer]
0x180005f01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005f06  mov     r9d, 400h; dwLanguageId
0x180005f0c  mov     r8d, ebp; dwMessageId
0x180005f0f  xor     edx, edx; lpSource
0x180005f11  mov     ecx, 1200h; dwFlags
0x180005f16  call    cs:__imp_FormatMessageW
0x180005f1c  lea     rsi, [r14+rsi*2]
0x180005f20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005f24  mov     rax, [rbx+88h]
0x180005f2b  mov     rcx, [rbx+80h]
0x180005f32  mov     rdx, rsi; unsigned __int16 *
0x180005f35  test    r9, r9
0x180005f38  jz      short loc_180005F5C
0x180005f3a  mov     [rsp+278h+Arguments], rax
0x180005f3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005f44  mov     eax, [rbx+40h]
0x180005f47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005f4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005f52  mov     rcx, r14; this
0x180005f55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f5a  jmp     short loc_180005F73
0x180005f5c  mov     [rsp+278h+lpBuffer], rax
0x180005f61  mov     r9, rcx; unsigned __int16 *
0x180005f64  lea     r8, aHsP; "%hs!%p: "
0x180005f6b  mov     rcx, r14; this
0x180005f6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f73  mov     r14, rax
0x180005f76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005f7d  test    r9, r9
0x180005f80  jz      short loc_180005F97
0x180005f82  lea     r8, aCallerP; "(caller: %p) "
0x180005f89  mov     rdx, rsi; unsigned __int16 *
0x180005f8c  mov     rcx, rax; this
0x180005f8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f94  mov     r14, rax
0x180005f97  call    cs:__imp_GetCurrentThreadId
0x180005f9d  lea     rcx, [rsp+278h+Buffer]
0x180005fa2  mov     [rsp+278h+var_240], rcx
0x180005fa7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005fab  mov     [rsp+278h+nSize], eax
0x180005faf  mov     eax, [rbx+44h]
0x180005fb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005fb6  mov     r9, rdi; unsigned __int16 *
0x180005fb9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005fc0  mov     rdx, rsi; unsigned __int16 *
0x180005fc3  mov     rcx, r14; this
0x180005fc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fcb  cmp     [rbx+18h], r15
0x180005fcf  jnz     short loc_180005FE1
0x180005fd1  cmp     [rbx+48h], r15
0x180005fd5  jnz     short loc_180005FE1
0x180005fd7  cmp     [rbx+30h], r15
0x180005fdb  jz      loc_180006071
0x180005fe1  lea     r8, asc_180021F00; "    "
0x180005fe8  mov     rdx, rsi; unsigned __int16 *
0x180005feb  mov     rcx, rax; this
0x180005fee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ff3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005ff7  test    r9, r9
0x180005ffa  jz      short loc_18000600E
0x180005ffc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006003  mov     rdx, rsi; unsigned __int16 *
0x180006006  mov     rcx, rax; this
0x180006009  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000600e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006012  test    r9, r9
0x180006015  jz      short loc_180006029
0x180006017  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000601e  mov     rdx, rsi; unsigned __int16 *
0x180006021  mov     rcx, rax; this
0x180006024  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006029  mov     rcx, [rbx+28h]
0x18000602d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006031  mov     rdx, rsi; unsigned __int16 *
0x180006034  test    rcx, rcx
0x180006037  jz      short loc_18000604F
0x180006039  mov     [rsp+278h+lpBuffer], rcx
0x18000603e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006045  mov     rcx, rax; this
0x180006048  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000604d  jmp     short loc_180006071
0x18000604f  mov     rcx, rax; this
0x180006052  test    r9, r9
0x180006055  jz      short loc_180006065
0x180006057  lea     r8, aHs; "[%hs]\n"
0x18000605e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006063  jmp     short loc_180006071
0x180006065  lea     r8, asc_180021F78; "\n"
0x18000606c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006071  xor     eax, eax
0x180006073  mov     rcx, [rsp+278h+var_38]
0x18000607b  xor     rcx, rsp; StackCookie
0x18000607e  call    __security_check_cookie
0x180006083  mov     rbx, [rsp+278h+arg_18]
0x18000608b  add     rsp, 250h
0x180006092  pop     r15
0x180006094  pop     r14
0x180006096  pop     rdi
0x180006097  pop     rsi
0x180006098  pop     rbp
0x180006099  retn
```
