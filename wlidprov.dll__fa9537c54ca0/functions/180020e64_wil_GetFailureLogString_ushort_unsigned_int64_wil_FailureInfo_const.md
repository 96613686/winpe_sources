# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180020e64`
- end: `0x18002111a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ffdc`
- `0x18002166c`
- `0x1800219bc`
- `0x180022ab0`

## callees

- `0x18001a0d0`
- `0x18001ac3c`
- `0x180020e64`
- `0x18002196c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180020f96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180020f96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021017`

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
          v7 = (const char *)&qword_1800630C8;
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
0x180020e64  mov     [rsp+arg_18], rbx
0x180020e69  push    rbp
0x180020e6a  push    rsi
0x180020e6b  push    rdi
0x180020e6c  push    r14
0x180020e6e  push    r15
0x180020e70  sub     rsp, 250h
0x180020e77  mov     rax, cs:__security_cookie
0x180020e7e  xor     rax, rsp
0x180020e81  mov     [rsp+278h+var_38], rax
0x180020e89  mov     rbx, r8
0x180020e8c  mov     rsi, rdx
0x180020e8f  mov     r14, rcx
0x180020e92  xor     r15d, r15d
0x180020e95  test    rdx, rdx
0x180020e98  jz      loc_1800210F1
0x180020e9e  test    rcx, rcx
0x180020ea1  jz      loc_1800210F1
0x180020ea7  mov     [rcx], r15w
0x180020eab  mov     rax, cs:g_pfnResultLoggingCallback
0x180020eb2  test    rax, rax
0x180020eb5  jz      short loc_180020ED8
0x180020eb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180020ebe  jz      short loc_180020ED8
0x180020ec0  mov     r8, rdx
0x180020ec3  mov     rdx, rcx
0x180020ec6  mov     rcx, rbx
0x180020ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ece  cmp     [r14], r15w
0x180020ed2  jnz     loc_1800210F1
0x180020ed8  mov     ecx, [rbx]
0x180020eda  mov     bpl, 8
0x180020edd  test    ecx, ecx
0x180020edf  jz      short loc_180020F2A
0x180020ee1  sub     ecx, 1
0x180020ee4  jz      short loc_180020F12
0x180020ee6  sub     ecx, 1
0x180020ee9  jz      short loc_180020F02
0x180020eeb  cmp     ecx, 1
0x180020eee  jz      short loc_180020EF9
0x180020ef0  lea     rdi, qword_1800630C8
0x180020ef7  jmp     short loc_180020F31
0x180020ef9  lea     rdi, aFailfast; "FailFast"
0x180020f00  jmp     short loc_180020F31
0x180020f02  lea     rax, aLoghr; "LogHr"
0x180020f09  lea     rdi, aLognt; "LogNt"
0x180020f10  jmp     short loc_180020F20
0x180020f12  lea     rax, aReturnhr; "ReturnHr"
0x180020f19  lea     rdi, aReturnnt; "ReturnNt"
0x180020f20  test    [rbx+4], bpl
0x180020f24  cmovz   rdi, rax
0x180020f28  jmp     short loc_180020F31
0x180020f2a  lea     rdi, aException; "Exception"
0x180020f31  xor     edx, edx; Val
0x180020f33  mov     r8d, 200h; Size
0x180020f39  lea     rcx, [rsp+278h+Buffer]; void *
0x180020f3e  call    memset_0
0x180020f43  test    [rbx+4], bpl
0x180020f47  jz      short loc_180020F6C
0x180020f49  mov     ebp, [rbx+0Ch]
0x180020f4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180020f53  test    rax, rax
0x180020f56  jz      short loc_180020F9C
0x180020f58  mov     r8d, 100h
0x180020f5e  lea     rdx, [rsp+278h+Buffer]
0x180020f63  mov     ecx, ebp
0x180020f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f6a  jmp     short loc_180020F9C
0x180020f6c  mov     ebp, [rbx+8]
0x180020f6f  mov     [rsp+278h+Arguments], r15; Arguments
0x180020f74  mov     [rsp+278h+nSize], 100h; nSize
0x180020f7c  lea     rax, [rsp+278h+Buffer]
0x180020f81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180020f86  mov     r9d, 400h; dwLanguageId
0x180020f8c  mov     r8d, ebp; dwMessageId
0x180020f8f  xor     edx, edx; lpSource
0x180020f91  mov     ecx, 1200h; dwFlags
0x180020f96  call    cs:__imp_FormatMessageW
0x180020f9c  lea     rsi, [r14+rsi*2]
0x180020fa0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180020fa4  mov     rax, [rbx+88h]
0x180020fab  mov     rcx, [rbx+80h]
0x180020fb2  mov     rdx, rsi; unsigned __int16 *
0x180020fb5  test    r9, r9
0x180020fb8  jz      short loc_180020FDC
0x180020fba  mov     [rsp+278h+Arguments], rax
0x180020fbf  mov     qword ptr [rsp+278h+nSize], rcx
0x180020fc4  mov     eax, [rbx+40h]
0x180020fc7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180020fcb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180020fd2  mov     rcx, r14; this
0x180020fd5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020fda  jmp     short loc_180020FF3
0x180020fdc  mov     [rsp+278h+lpBuffer], rax
0x180020fe1  mov     r9, rcx; unsigned __int16 *
0x180020fe4  lea     r8, aHsP; "%hs!%p: "
0x180020feb  mov     rcx, r14; this
0x180020fee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020ff3  mov     r14, rax
0x180020ff6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180020ffd  test    r9, r9
0x180021000  jz      short loc_180021017
0x180021002  lea     r8, aCallerP; "(caller: %p) "
0x180021009  mov     rdx, rsi; unsigned __int16 *
0x18002100c  mov     rcx, rax; this
0x18002100f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021014  mov     r14, rax
0x180021017  call    cs:__imp_GetCurrentThreadId
0x18002101d  lea     rcx, [rsp+278h+Buffer]
0x180021022  mov     [rsp+278h+var_240], rcx
0x180021027  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002102b  mov     [rsp+278h+nSize], eax
0x18002102f  mov     eax, [rbx+44h]
0x180021032  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180021036  mov     r9, rdi; unsigned __int16 *
0x180021039  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180021040  mov     rdx, rsi; unsigned __int16 *
0x180021043  mov     rcx, r14; this
0x180021046  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002104b  cmp     [rbx+18h], r15
0x18002104f  jnz     short loc_180021061
0x180021051  cmp     [rbx+48h], r15
0x180021055  jnz     short loc_180021061
0x180021057  cmp     [rbx+30h], r15
0x18002105b  jz      loc_1800210F1
0x180021061  lea     r8, asc_180066870; "    "
0x180021068  mov     rdx, rsi; unsigned __int16 *
0x18002106b  mov     rcx, rax; this
0x18002106e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021073  mov     r9, [rbx+18h]; unsigned __int16 *
0x180021077  test    r9, r9
0x18002107a  jz      short loc_18002108E
0x18002107c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180021083  mov     rdx, rsi; unsigned __int16 *
0x180021086  mov     rcx, rax; this
0x180021089  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002108e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180021092  test    r9, r9
0x180021095  jz      short loc_1800210A9
0x180021097  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002109e  mov     rdx, rsi; unsigned __int16 *
0x1800210a1  mov     rcx, rax; this
0x1800210a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800210a9  mov     rcx, [rbx+28h]
0x1800210ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800210b1  mov     rdx, rsi; unsigned __int16 *
0x1800210b4  test    rcx, rcx
0x1800210b7  jz      short loc_1800210CF
0x1800210b9  mov     [rsp+278h+lpBuffer], rcx
0x1800210be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800210c5  mov     rcx, rax; this
0x1800210c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800210cd  jmp     short loc_1800210F1
0x1800210cf  mov     rcx, rax; this
0x1800210d2  test    r9, r9
0x1800210d5  jz      short loc_1800210E5
0x1800210d7  lea     r8, aHs; "[%hs]\n"
0x1800210de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800210e3  jmp     short loc_1800210F1
0x1800210e5  lea     r8, asc_1800668E8; "\n"
0x1800210ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800210f1  xor     eax, eax
0x1800210f3  mov     rcx, [rsp+278h+var_38]
0x1800210fb  xor     rcx, rsp; StackCookie
0x1800210fe  call    __security_check_cookie
0x180021103  mov     rbx, [rsp+278h+arg_18]
0x18002110b  add     rsp, 250h
0x180021112  pop     r15
0x180021114  pop     r14
0x180021116  pop     rdi
0x180021117  pop     rsi
0x180021118  pop     rbp
0x180021119  retn
```
