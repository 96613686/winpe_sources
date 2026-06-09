# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180042be4`
- end: `0x180042ea7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180043e14`
- `0x180044578`
- `0x180048dd0`

## callees

- `0x18003d270`
- `0x18003dd2c`
- `0x180042be4`
- `0x180044124`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180042d16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180042d16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042d9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_18007DF78;
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
0x180042be4  mov     [rsp+arg_18], rbx
0x180042be9  push    rbp
0x180042bea  push    rsi
0x180042beb  push    rdi
0x180042bec  push    r14
0x180042bee  push    r15
0x180042bf0  sub     rsp, 250h
0x180042bf7  mov     rax, cs:__security_cookie
0x180042bfe  xor     rax, rsp
0x180042c01  mov     [rsp+278h+var_38], rax
0x180042c09  mov     rbx, r8
0x180042c0c  mov     rsi, rdx
0x180042c0f  mov     r14, rcx
0x180042c12  xor     r15d, r15d
0x180042c15  test    rdx, rdx
0x180042c18  jz      loc_180042E7D
0x180042c1e  test    rcx, rcx
0x180042c21  jz      loc_180042E7D
0x180042c27  mov     [rcx], r15w
0x180042c2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180042c32  test    rax, rax
0x180042c35  jz      short loc_180042C58
0x180042c37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180042c3e  jz      short loc_180042C58
0x180042c40  mov     r8, rdx
0x180042c43  mov     rdx, rcx
0x180042c46  mov     rcx, rbx
0x180042c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c4e  cmp     [r14], r15w
0x180042c52  jnz     loc_180042E7D
0x180042c58  mov     ecx, [rbx]
0x180042c5a  mov     bpl, 8
0x180042c5d  test    ecx, ecx
0x180042c5f  jz      short loc_180042CAA
0x180042c61  sub     ecx, 1
0x180042c64  jz      short loc_180042C92
0x180042c66  sub     ecx, 1
0x180042c69  jz      short loc_180042C82
0x180042c6b  cmp     ecx, 1
0x180042c6e  jz      short loc_180042C79
0x180042c70  lea     rdi, qword_18007DF78
0x180042c77  jmp     short loc_180042CB1
0x180042c79  lea     rdi, aFailfast; "FailFast"
0x180042c80  jmp     short loc_180042CB1
0x180042c82  lea     rax, aLoghr; "LogHr"
0x180042c89  lea     rdi, aLognt; "LogNt"
0x180042c90  jmp     short loc_180042CA0
0x180042c92  lea     rax, aReturnhr; "ReturnHr"
0x180042c99  lea     rdi, aReturnnt; "ReturnNt"
0x180042ca0  test    [rbx+4], bpl
0x180042ca4  cmovz   rdi, rax
0x180042ca8  jmp     short loc_180042CB1
0x180042caa  lea     rdi, aException; "Exception"
0x180042cb1  xor     edx, edx; Val
0x180042cb3  mov     r8d, 200h; Size
0x180042cb9  lea     rcx, [rsp+278h+Buffer]; void *
0x180042cbe  call    memset_0
0x180042cc3  test    [rbx+4], bpl
0x180042cc7  jz      short loc_180042CEC
0x180042cc9  mov     ebp, [rbx+0Ch]
0x180042ccc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180042cd3  test    rax, rax
0x180042cd6  jz      short loc_180042D22
0x180042cd8  mov     r8d, 100h
0x180042cde  lea     rdx, [rsp+278h+Buffer]
0x180042ce3  mov     ecx, ebp
0x180042ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cea  jmp     short loc_180042D22
0x180042cec  mov     ebp, [rbx+8]
0x180042cef  mov     [rsp+278h+Arguments], r15; Arguments
0x180042cf4  mov     [rsp+278h+nSize], 100h; nSize
0x180042cfc  lea     rax, [rsp+278h+Buffer]
0x180042d01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180042d06  mov     r9d, 400h; dwLanguageId
0x180042d0c  mov     r8d, ebp; dwMessageId
0x180042d0f  xor     edx, edx; lpSource
0x180042d11  mov     ecx, 1200h; dwFlags
0x180042d16  call    cs:__imp_FormatMessageW
0x180042d1d  nop     dword ptr [rax+rax+00h]
0x180042d22  lea     rsi, [r14+rsi*2]
0x180042d26  mov     r9, [rbx+38h]; unsigned __int16 *
0x180042d2a  mov     rax, [rbx+88h]
0x180042d31  mov     rcx, [rbx+80h]
0x180042d38  mov     rdx, rsi; unsigned __int16 *
0x180042d3b  test    r9, r9
0x180042d3e  jz      short loc_180042D62
0x180042d40  mov     [rsp+278h+Arguments], rax
0x180042d45  mov     qword ptr [rsp+278h+nSize], rcx
0x180042d4a  mov     eax, [rbx+40h]
0x180042d4d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180042d51  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180042d58  mov     rcx, r14; this
0x180042d5b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042d60  jmp     short loc_180042D79
0x180042d62  mov     [rsp+278h+lpBuffer], rax
0x180042d67  mov     r9, rcx; unsigned __int16 *
0x180042d6a  lea     r8, aHsP; "%hs!%p: "
0x180042d71  mov     rcx, r14; this
0x180042d74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042d79  mov     r14, rax
0x180042d7c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180042d83  test    r9, r9
0x180042d86  jz      short loc_180042D9D
0x180042d88  lea     r8, aCallerP; "(caller: %p) "
0x180042d8f  mov     rdx, rsi; unsigned __int16 *
0x180042d92  mov     rcx, rax; this
0x180042d95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042d9a  mov     r14, rax
0x180042d9d  call    cs:__imp_GetCurrentThreadId
0x180042da4  nop     dword ptr [rax+rax+00h]
0x180042da9  lea     rcx, [rsp+278h+Buffer]
0x180042dae  mov     [rsp+278h+var_240], rcx
0x180042db3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180042db7  mov     [rsp+278h+nSize], eax
0x180042dbb  mov     eax, [rbx+44h]
0x180042dbe  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180042dc2  mov     r9, rdi; unsigned __int16 *
0x180042dc5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180042dcc  mov     rdx, rsi; unsigned __int16 *
0x180042dcf  mov     rcx, r14; this
0x180042dd2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042dd7  cmp     [rbx+18h], r15
0x180042ddb  jnz     short loc_180042DED
0x180042ddd  cmp     [rbx+48h], r15
0x180042de1  jnz     short loc_180042DED
0x180042de3  cmp     [rbx+30h], r15
0x180042de7  jz      loc_180042E7D
0x180042ded  lea     r8, asc_1800739F0; "    "
0x180042df4  mov     rdx, rsi; unsigned __int16 *
0x180042df7  mov     rcx, rax; this
0x180042dfa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042dff  mov     r9, [rbx+18h]; unsigned __int16 *
0x180042e03  test    r9, r9
0x180042e06  jz      short loc_180042E1A
0x180042e08  lea     r8, aMsgWs; "Msg:[%ws] "
0x180042e0f  mov     rdx, rsi; unsigned __int16 *
0x180042e12  mov     rcx, rax; this
0x180042e15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042e1a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180042e1e  test    r9, r9
0x180042e21  jz      short loc_180042E35
0x180042e23  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180042e2a  mov     rdx, rsi; unsigned __int16 *
0x180042e2d  mov     rcx, rax; this
0x180042e30  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042e35  mov     rcx, [rbx+28h]
0x180042e39  mov     r9, [rbx+30h]; unsigned __int16 *
0x180042e3d  mov     rdx, rsi; unsigned __int16 *
0x180042e40  test    rcx, rcx
0x180042e43  jz      short loc_180042E5B
0x180042e45  mov     [rsp+278h+lpBuffer], rcx
0x180042e4a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180042e51  mov     rcx, rax; this
0x180042e54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042e59  jmp     short loc_180042E7D
0x180042e5b  mov     rcx, rax; this
0x180042e5e  test    r9, r9
0x180042e61  jz      short loc_180042E71
0x180042e63  lea     r8, aHs; "[%hs]\n"
0x180042e6a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042e6f  jmp     short loc_180042E7D
0x180042e71  lea     r8, asc_18007145C; "\n"
0x180042e78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042e7d  xor     eax, eax
0x180042e7f  mov     rcx, [rsp+278h+var_38]
0x180042e87  xor     rcx, rsp; StackCookie
0x180042e8a  call    __security_check_cookie
0x180042e8f  mov     rbx, [rsp+278h+arg_18]
0x180042e97  add     rsp, 250h
0x180042e9e  pop     r15
0x180042ea0  pop     r14
0x180042ea2  pop     rdi
0x180042ea3  pop     rsi
0x180042ea4  pop     rbp
0x180042ea5  retn
```
