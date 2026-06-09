# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180041bc4`
- end: `0x180041e87`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003e564`
- `0x1800427d0`

## callees

- `0x18003cb60`
- `0x18003d4b0`
- `0x180041bc4`
- `0x180042ae4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041d7d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180041cf6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180041cf6`

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
          v8 = (const char *)&qword_1800683F0;
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
0x180041bc4  mov     [rsp+arg_18], rbx
0x180041bc9  push    rbp
0x180041bca  push    rsi
0x180041bcb  push    rdi
0x180041bcc  push    r14
0x180041bce  push    r15
0x180041bd0  sub     rsp, 250h
0x180041bd7  mov     rax, cs:__security_cookie
0x180041bde  xor     rax, rsp
0x180041be1  mov     [rsp+278h+var_38], rax
0x180041be9  xor     r15d, r15d
0x180041bec  mov     rbx, r8
0x180041bef  mov     rsi, rdx
0x180041bf2  mov     r14, rcx
0x180041bf5  test    rdx, rdx
0x180041bf8  jz      loc_180041E5D
0x180041bfe  test    rcx, rcx
0x180041c01  jz      loc_180041E5D
0x180041c07  mov     rax, cs:g_pfnResultLoggingCallback
0x180041c0e  mov     [rcx], r15w
0x180041c12  test    rax, rax
0x180041c15  jz      short loc_180041C38
0x180041c17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180041c1e  jz      short loc_180041C38
0x180041c20  mov     r8, rdx
0x180041c23  mov     rdx, rcx
0x180041c26  mov     rcx, rbx
0x180041c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c2e  cmp     [r14], r15w
0x180041c32  jnz     loc_180041E5D
0x180041c38  mov     ecx, [rbx]
0x180041c3a  mov     bpl, 8
0x180041c3d  test    ecx, ecx
0x180041c3f  jz      short loc_180041C8A
0x180041c41  sub     ecx, 1
0x180041c44  jz      short loc_180041C72
0x180041c46  sub     ecx, 1
0x180041c49  jz      short loc_180041C62
0x180041c4b  cmp     ecx, 1
0x180041c4e  jz      short loc_180041C59
0x180041c50  lea     rdi, qword_1800683F0
0x180041c57  jmp     short loc_180041C91
0x180041c59  lea     rdi, aFailfast; "FailFast"
0x180041c60  jmp     short loc_180041C91
0x180041c62  lea     rax, aLoghr; "LogHr"
0x180041c69  lea     rdi, aLognt; "LogNt"
0x180041c70  jmp     short loc_180041C80
0x180041c72  lea     rax, aReturnhr; "ReturnHr"
0x180041c79  lea     rdi, aReturnnt; "ReturnNt"
0x180041c80  test    [rbx+4], bpl
0x180041c84  cmovz   rdi, rax
0x180041c88  jmp     short loc_180041C91
0x180041c8a  lea     rdi, aException; "Exception"
0x180041c91  xor     edx, edx; Val
0x180041c93  lea     rcx, [rsp+278h+Buffer]; void *
0x180041c98  mov     r8d, 200h; Size
0x180041c9e  call    memset_0
0x180041ca3  test    [rbx+4], bpl
0x180041ca7  jz      short loc_180041CCC
0x180041ca9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180041cb0  mov     ebp, [rbx+0Ch]
0x180041cb3  test    rax, rax
0x180041cb6  jz      short loc_180041D02
0x180041cb8  mov     r8d, 100h
0x180041cbe  lea     rdx, [rsp+278h+Buffer]
0x180041cc3  mov     ecx, ebp
0x180041cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cca  jmp     short loc_180041D02
0x180041ccc  mov     ebp, [rbx+8]
0x180041ccf  lea     rax, [rsp+278h+Buffer]
0x180041cd4  mov     [rsp+278h+Arguments], r15; Arguments
0x180041cd9  mov     r8d, ebp; dwMessageId
0x180041cdc  mov     [rsp+278h+nSize], 100h; nSize
0x180041ce4  mov     r9d, 400h; dwLanguageId
0x180041cea  xor     edx, edx; lpSource
0x180041cec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180041cf1  mov     ecx, 1200h; dwFlags
0x180041cf6  call    cs:__imp_FormatMessageW
0x180041cfd  nop     dword ptr [rax+rax+00h]
0x180041d02  mov     r9, [rbx+38h]; unsigned __int16 *
0x180041d06  lea     rsi, [r14+rsi*2]
0x180041d0a  mov     rax, [rbx+88h]
0x180041d11  mov     rdx, rsi; unsigned __int16 *
0x180041d14  mov     rcx, [rbx+80h]
0x180041d1b  test    r9, r9
0x180041d1e  jz      short loc_180041D42
0x180041d20  mov     [rsp+278h+Arguments], rax
0x180041d25  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180041d2c  mov     eax, [rbx+40h]
0x180041d2f  mov     qword ptr [rsp+278h+nSize], rcx
0x180041d34  mov     rcx, r14; this
0x180041d37  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180041d3b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041d40  jmp     short loc_180041D59
0x180041d42  mov     r9, rcx; unsigned __int16 *
0x180041d45  mov     [rsp+278h+lpBuffer], rax
0x180041d4a  mov     rcx, r14; this
0x180041d4d  lea     r8, aHsP; "%hs!%p: "
0x180041d54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041d59  mov     r9, [rbx+90h]; unsigned __int16 *
0x180041d60  mov     r14, rax
0x180041d63  test    r9, r9
0x180041d66  jz      short loc_180041D7D
0x180041d68  lea     r8, aCallerP; "(caller: %p) "
0x180041d6f  mov     rdx, rsi; unsigned __int16 *
0x180041d72  mov     rcx, rax; this
0x180041d75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041d7a  mov     r14, rax
0x180041d7d  call    cs:__imp_GetCurrentThreadId
0x180041d84  nop     dword ptr [rax+rax+00h]
0x180041d89  lea     rcx, [rsp+278h+Buffer]
0x180041d8e  mov     r9, rdi; unsigned __int16 *
0x180041d91  mov     [rsp+278h+var_240], rcx
0x180041d96  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180041d9d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180041da1  mov     rdx, rsi; unsigned __int16 *
0x180041da4  mov     [rsp+278h+nSize], eax
0x180041da8  mov     rcx, r14; this
0x180041dab  mov     eax, [rbx+44h]
0x180041dae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180041db2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041db7  cmp     [rbx+18h], r15
0x180041dbb  jnz     short loc_180041DCD
0x180041dbd  cmp     [rbx+48h], r15
0x180041dc1  jnz     short loc_180041DCD
0x180041dc3  cmp     [rbx+30h], r15
0x180041dc7  jz      loc_180041E5D
0x180041dcd  lea     r8, asc_180068840; "    "
0x180041dd4  mov     rdx, rsi; unsigned __int16 *
0x180041dd7  mov     rcx, rax; this
0x180041dda  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041ddf  mov     r9, [rbx+18h]; unsigned __int16 *
0x180041de3  test    r9, r9
0x180041de6  jz      short loc_180041DFA
0x180041de8  lea     r8, aMsgWs; "Msg:[%ws] "
0x180041def  mov     rdx, rsi; unsigned __int16 *
0x180041df2  mov     rcx, rax; this
0x180041df5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041dfa  mov     r9, [rbx+48h]; unsigned __int16 *
0x180041dfe  test    r9, r9
0x180041e01  jz      short loc_180041E15
0x180041e03  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180041e0a  mov     rdx, rsi; unsigned __int16 *
0x180041e0d  mov     rcx, rax; this
0x180041e10  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041e15  mov     rcx, [rbx+28h]
0x180041e19  mov     rdx, rsi; unsigned __int16 *
0x180041e1c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180041e20  test    rcx, rcx
0x180041e23  jz      short loc_180041E3B
0x180041e25  mov     [rsp+278h+lpBuffer], rcx
0x180041e2a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180041e31  mov     rcx, rax; this
0x180041e34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041e39  jmp     short loc_180041E5D
0x180041e3b  mov     rcx, rax; this
0x180041e3e  test    r9, r9
0x180041e41  jz      short loc_180041E51
0x180041e43  lea     r8, aHs; "[%hs]\n"
0x180041e4a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041e4f  jmp     short loc_180041E5D
0x180041e51  lea     r8, asc_1800688B8; "\n"
0x180041e58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041e5d  xor     eax, eax
0x180041e5f  mov     rcx, [rsp+278h+var_38]
0x180041e67  xor     rcx, rsp; StackCookie
0x180041e6a  call    __security_check_cookie
0x180041e6f  mov     rbx, [rsp+278h+arg_18]
0x180041e77  add     rsp, 250h
0x180041e7e  pop     r15
0x180041e80  pop     r14
0x180041e82  pop     rdi
0x180041e83  pop     rsi
0x180041e84  pop     rbp
0x180041e85  retn
```
