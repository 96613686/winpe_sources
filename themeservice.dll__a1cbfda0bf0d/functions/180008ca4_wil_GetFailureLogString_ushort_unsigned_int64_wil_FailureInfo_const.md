# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008ca4`
- end: `0x180008f5a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009398`

## callees

- `0x180008ca4`
- `0x180009694`
- `0x18000f9da`
- `0x18000fa00`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e57`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008dd6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008dd6`

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
          v8 = (const char *)&byte_180011FBB;
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
0x180008ca4  mov     [rsp+arg_18], rbx
0x180008ca9  push    rbp
0x180008caa  push    rsi
0x180008cab  push    rdi
0x180008cac  push    r14
0x180008cae  push    r15
0x180008cb0  sub     rsp, 250h
0x180008cb7  mov     rax, cs:__security_cookie
0x180008cbe  xor     rax, rsp
0x180008cc1  mov     [rsp+278h+var_38], rax
0x180008cc9  xor     r15d, r15d
0x180008ccc  mov     rbx, r8
0x180008ccf  mov     rsi, rdx
0x180008cd2  mov     r14, rcx
0x180008cd5  test    rdx, rdx
0x180008cd8  jz      loc_180008F31
0x180008cde  test    rcx, rcx
0x180008ce1  jz      loc_180008F31
0x180008ce7  mov     rax, cs:g_pfnResultLoggingCallback
0x180008cee  mov     [rcx], r15w
0x180008cf2  test    rax, rax
0x180008cf5  jz      short loc_180008D18
0x180008cf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008cfe  jz      short loc_180008D18
0x180008d00  mov     r8, rdx
0x180008d03  mov     rdx, rcx
0x180008d06  mov     rcx, rbx
0x180008d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d0e  cmp     [r14], r15w
0x180008d12  jnz     loc_180008F31
0x180008d18  mov     ecx, [rbx]
0x180008d1a  mov     bpl, 8
0x180008d1d  test    ecx, ecx
0x180008d1f  jz      short loc_180008D6A
0x180008d21  sub     ecx, 1
0x180008d24  jz      short loc_180008D52
0x180008d26  sub     ecx, 1
0x180008d29  jz      short loc_180008D42
0x180008d2b  cmp     ecx, 1
0x180008d2e  jz      short loc_180008D39
0x180008d30  lea     rdi, byte_180011FBB
0x180008d37  jmp     short loc_180008D71
0x180008d39  lea     rdi, aFailfast; "FailFast"
0x180008d40  jmp     short loc_180008D71
0x180008d42  lea     rax, aLoghr; "LogHr"
0x180008d49  lea     rdi, aLognt; "LogNt"
0x180008d50  jmp     short loc_180008D60
0x180008d52  lea     rax, aReturnhr; "ReturnHr"
0x180008d59  lea     rdi, aReturnnt; "ReturnNt"
0x180008d60  test    [rbx+4], bpl
0x180008d64  cmovz   rdi, rax
0x180008d68  jmp     short loc_180008D71
0x180008d6a  lea     rdi, aException; "Exception"
0x180008d71  xor     edx, edx; Val
0x180008d73  lea     rcx, [rsp+278h+Buffer]; void *
0x180008d78  mov     r8d, 200h; Size
0x180008d7e  call    memset_0
0x180008d83  test    [rbx+4], bpl
0x180008d87  jz      short loc_180008DAC
0x180008d89  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008d90  mov     ebp, [rbx+0Ch]
0x180008d93  test    rax, rax
0x180008d96  jz      short loc_180008DDC
0x180008d98  mov     r8d, 100h
0x180008d9e  lea     rdx, [rsp+278h+Buffer]
0x180008da3  mov     ecx, ebp
0x180008da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008daa  jmp     short loc_180008DDC
0x180008dac  mov     ebp, [rbx+8]
0x180008daf  lea     rax, [rsp+278h+Buffer]
0x180008db4  mov     [rsp+278h+Arguments], r15; Arguments
0x180008db9  mov     r8d, ebp; dwMessageId
0x180008dbc  mov     [rsp+278h+nSize], 100h; nSize
0x180008dc4  mov     r9d, 400h; dwLanguageId
0x180008dca  xor     edx, edx; lpSource
0x180008dcc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008dd1  mov     ecx, 1200h; dwFlags
0x180008dd6  call    cs:__imp_FormatMessageW
0x180008ddc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008de0  lea     rsi, [r14+rsi*2]
0x180008de4  mov     rax, [rbx+88h]
0x180008deb  mov     rdx, rsi; unsigned __int16 *
0x180008dee  mov     rcx, [rbx+80h]
0x180008df5  test    r9, r9
0x180008df8  jz      short loc_180008E1C
0x180008dfa  mov     [rsp+278h+Arguments], rax
0x180008dff  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008e06  mov     eax, [rbx+40h]
0x180008e09  mov     qword ptr [rsp+278h+nSize], rcx
0x180008e0e  mov     rcx, r14; this
0x180008e11  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008e15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e1a  jmp     short loc_180008E33
0x180008e1c  mov     r9, rcx; unsigned __int16 *
0x180008e1f  mov     [rsp+278h+lpBuffer], rax
0x180008e24  mov     rcx, r14; this
0x180008e27  lea     r8, aHsP; "%hs!%p: "
0x180008e2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e33  mov     r9, [rbx+90h]; unsigned __int16 *
0x180008e3a  mov     r14, rax
0x180008e3d  test    r9, r9
0x180008e40  jz      short loc_180008E57
0x180008e42  lea     r8, aCallerP; "(caller: %p) "
0x180008e49  mov     rdx, rsi; unsigned __int16 *
0x180008e4c  mov     rcx, rax; this
0x180008e4f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e54  mov     r14, rax
0x180008e57  call    cs:__imp_GetCurrentThreadId
0x180008e5d  lea     rcx, [rsp+278h+Buffer]
0x180008e62  mov     r9, rdi; unsigned __int16 *
0x180008e65  mov     [rsp+278h+var_240], rcx
0x180008e6a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008e71  mov     dword ptr [rsp+278h+Arguments], ebp
0x180008e75  mov     rdx, rsi; unsigned __int16 *
0x180008e78  mov     [rsp+278h+nSize], eax
0x180008e7c  mov     rcx, r14; this
0x180008e7f  mov     eax, [rbx+44h]
0x180008e82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008e86  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e8b  cmp     [rbx+18h], r15
0x180008e8f  jnz     short loc_180008EA1
0x180008e91  cmp     [rbx+48h], r15
0x180008e95  jnz     short loc_180008EA1
0x180008e97  cmp     [rbx+30h], r15
0x180008e9b  jz      loc_180008F31
0x180008ea1  lea     r8, asc_1800120A8; "    "
0x180008ea8  mov     rdx, rsi; unsigned __int16 *
0x180008eab  mov     rcx, rax; this
0x180008eae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008eb3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008eb7  test    r9, r9
0x180008eba  jz      short loc_180008ECE
0x180008ebc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008ec3  mov     rdx, rsi; unsigned __int16 *
0x180008ec6  mov     rcx, rax; this
0x180008ec9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008ece  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008ed2  test    r9, r9
0x180008ed5  jz      short loc_180008EE9
0x180008ed7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180008ede  mov     rdx, rsi; unsigned __int16 *
0x180008ee1  mov     rcx, rax; this
0x180008ee4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008ee9  mov     rcx, [rbx+28h]
0x180008eed  mov     rdx, rsi; unsigned __int16 *
0x180008ef0  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008ef4  test    rcx, rcx
0x180008ef7  jz      short loc_180008F0F
0x180008ef9  mov     [rsp+278h+lpBuffer], rcx
0x180008efe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008f05  mov     rcx, rax; this
0x180008f08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008f0d  jmp     short loc_180008F31
0x180008f0f  mov     rcx, rax; this
0x180008f12  test    r9, r9
0x180008f15  jz      short loc_180008F25
0x180008f17  lea     r8, aHs; "[%hs]\n"
0x180008f1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008f23  jmp     short loc_180008F31
0x180008f25  lea     r8, asc_180012120; "\n"
0x180008f2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008f31  xor     eax, eax
0x180008f33  mov     rcx, [rsp+278h+var_38]
0x180008f3b  xor     rcx, rsp; StackCookie
0x180008f3e  call    __security_check_cookie
0x180008f43  mov     rbx, [rsp+278h+arg_18]
0x180008f4b  add     rsp, 250h
0x180008f52  pop     r15
0x180008f54  pop     r14
0x180008f56  pop     rdi
0x180008f57  pop     rsi
0x180008f58  pop     rbp
0x180008f59  retn
```
