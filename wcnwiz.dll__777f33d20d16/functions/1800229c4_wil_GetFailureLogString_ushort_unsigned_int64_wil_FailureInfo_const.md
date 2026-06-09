# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800229c4`
- end: `0x180022c7a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180021b28`
- `0x180023570`
- `0x180024cb0`

## callees

- `0x180001820`
- `0x180002294`
- `0x1800229c4`
- `0x180023870`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022b77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022b77`
- `KERNEL32!FormatMessageW` at `0x180022af6`
- `KERNEL32!FormatMessageW` at `0x180022af6`

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
          v7 = (const char *)&word_18003746E;
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
0x1800229c4  mov     [rsp+arg_18], rbx
0x1800229c9  push    rbp
0x1800229ca  push    rsi
0x1800229cb  push    rdi
0x1800229cc  push    r14
0x1800229ce  push    r15
0x1800229d0  sub     rsp, 250h
0x1800229d7  mov     rax, cs:__security_cookie
0x1800229de  xor     rax, rsp
0x1800229e1  mov     [rsp+278h+var_38], rax
0x1800229e9  mov     rbx, r8
0x1800229ec  mov     rsi, rdx
0x1800229ef  mov     r14, rcx
0x1800229f2  xor     r15d, r15d
0x1800229f5  test    rdx, rdx
0x1800229f8  jz      loc_180022C51
0x1800229fe  test    rcx, rcx
0x180022a01  jz      loc_180022C51
0x180022a07  mov     [rcx], r15w
0x180022a0b  mov     rax, cs:g_pfnResultLoggingCallback
0x180022a12  test    rax, rax
0x180022a15  jz      short loc_180022A38
0x180022a17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180022a1e  jz      short loc_180022A38
0x180022a20  mov     r8, rdx
0x180022a23  mov     rdx, rcx
0x180022a26  mov     rcx, rbx
0x180022a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a2e  cmp     [r14], r15w
0x180022a32  jnz     loc_180022C51
0x180022a38  mov     ecx, [rbx]
0x180022a3a  mov     bpl, 8
0x180022a3d  test    ecx, ecx
0x180022a3f  jz      short loc_180022A8A
0x180022a41  sub     ecx, 1
0x180022a44  jz      short loc_180022A72
0x180022a46  sub     ecx, 1
0x180022a49  jz      short loc_180022A62
0x180022a4b  cmp     ecx, 1
0x180022a4e  jz      short loc_180022A59
0x180022a50  lea     rdi, word_18003746E
0x180022a57  jmp     short loc_180022A91
0x180022a59  lea     rdi, aFailfast; "FailFast"
0x180022a60  jmp     short loc_180022A91
0x180022a62  lea     rax, aLoghr; "LogHr"
0x180022a69  lea     rdi, aLognt; "LogNt"
0x180022a70  jmp     short loc_180022A80
0x180022a72  lea     rax, aReturnhr; "ReturnHr"
0x180022a79  lea     rdi, aReturnnt; "ReturnNt"
0x180022a80  test    [rbx+4], bpl
0x180022a84  cmovz   rdi, rax
0x180022a88  jmp     short loc_180022A91
0x180022a8a  lea     rdi, aException; "Exception"
0x180022a91  xor     edx, edx; Val
0x180022a93  mov     r8d, 200h; Size
0x180022a99  lea     rcx, [rsp+278h+Buffer]; void *
0x180022a9e  call    memset_0
0x180022aa3  test    [rbx+4], bpl
0x180022aa7  jz      short loc_180022ACC
0x180022aa9  mov     ebp, [rbx+0Ch]
0x180022aac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180022ab3  test    rax, rax
0x180022ab6  jz      short loc_180022AFC
0x180022ab8  mov     r8d, 100h
0x180022abe  lea     rdx, [rsp+278h+Buffer]
0x180022ac3  mov     ecx, ebp
0x180022ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aca  jmp     short loc_180022AFC
0x180022acc  mov     ebp, [rbx+8]
0x180022acf  mov     [rsp+278h+Arguments], r15; Arguments
0x180022ad4  mov     [rsp+278h+nSize], 100h; nSize
0x180022adc  lea     rax, [rsp+278h+Buffer]
0x180022ae1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180022ae6  mov     r9d, 400h; dwLanguageId
0x180022aec  mov     r8d, ebp; dwMessageId
0x180022aef  xor     edx, edx; lpSource
0x180022af1  mov     ecx, 1200h; dwFlags
0x180022af6  call    cs:__imp_FormatMessageW
0x180022afc  lea     rsi, [r14+rsi*2]
0x180022b00  mov     r9, [rbx+38h]; unsigned __int16 *
0x180022b04  mov     rax, [rbx+88h]
0x180022b0b  mov     rcx, [rbx+80h]
0x180022b12  mov     rdx, rsi; unsigned __int16 *
0x180022b15  test    r9, r9
0x180022b18  jz      short loc_180022B3C
0x180022b1a  mov     [rsp+278h+Arguments], rax
0x180022b1f  mov     qword ptr [rsp+278h+nSize], rcx
0x180022b24  mov     eax, [rbx+40h]
0x180022b27  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180022b2b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180022b32  mov     rcx, r14; this
0x180022b35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022b3a  jmp     short loc_180022B53
0x180022b3c  mov     [rsp+278h+lpBuffer], rax
0x180022b41  mov     r9, rcx; unsigned __int16 *
0x180022b44  lea     r8, aHsP; "%hs!%p: "
0x180022b4b  mov     rcx, r14; this
0x180022b4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022b53  mov     r14, rax
0x180022b56  mov     r9, [rbx+90h]; unsigned __int16 *
0x180022b5d  test    r9, r9
0x180022b60  jz      short loc_180022B77
0x180022b62  lea     r8, aCallerP; "(caller: %p) "
0x180022b69  mov     rdx, rsi; unsigned __int16 *
0x180022b6c  mov     rcx, rax; this
0x180022b6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022b74  mov     r14, rax
0x180022b77  call    cs:__imp_GetCurrentThreadId
0x180022b7d  lea     rcx, [rsp+278h+Buffer]
0x180022b82  mov     [rsp+278h+var_240], rcx
0x180022b87  mov     dword ptr [rsp+278h+Arguments], ebp
0x180022b8b  mov     [rsp+278h+nSize], eax
0x180022b8f  mov     eax, [rbx+44h]
0x180022b92  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180022b96  mov     r9, rdi; unsigned __int16 *
0x180022b99  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180022ba0  mov     rdx, rsi; unsigned __int16 *
0x180022ba3  mov     rcx, r14; this
0x180022ba6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022bab  cmp     [rbx+18h], r15
0x180022baf  jnz     short loc_180022BC1
0x180022bb1  cmp     [rbx+48h], r15
0x180022bb5  jnz     short loc_180022BC1
0x180022bb7  cmp     [rbx+30h], r15
0x180022bbb  jz      loc_180022C51
0x180022bc1  lea     r8, asc_1800375A0; "    "
0x180022bc8  mov     rdx, rsi; unsigned __int16 *
0x180022bcb  mov     rcx, rax; this
0x180022bce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022bd3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180022bd7  test    r9, r9
0x180022bda  jz      short loc_180022BEE
0x180022bdc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180022be3  mov     rdx, rsi; unsigned __int16 *
0x180022be6  mov     rcx, rax; this
0x180022be9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022bee  mov     r9, [rbx+48h]; unsigned __int16 *
0x180022bf2  test    r9, r9
0x180022bf5  jz      short loc_180022C09
0x180022bf7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180022bfe  mov     rdx, rsi; unsigned __int16 *
0x180022c01  mov     rcx, rax; this
0x180022c04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c09  mov     rcx, [rbx+28h]
0x180022c0d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180022c11  mov     rdx, rsi; unsigned __int16 *
0x180022c14  test    rcx, rcx
0x180022c17  jz      short loc_180022C2F
0x180022c19  mov     [rsp+278h+lpBuffer], rcx
0x180022c1e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180022c25  mov     rcx, rax; this
0x180022c28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c2d  jmp     short loc_180022C51
0x180022c2f  mov     rcx, rax; this
0x180022c32  test    r9, r9
0x180022c35  jz      short loc_180022C45
0x180022c37  lea     r8, aHs; "[%hs]\n"
0x180022c3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c43  jmp     short loc_180022C51
0x180022c45  lea     r8, asc_1800375F0; "\n"
0x180022c4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c51  xor     eax, eax
0x180022c53  mov     rcx, [rsp+278h+var_38]
0x180022c5b  xor     rcx, rsp; StackCookie
0x180022c5e  call    __security_check_cookie
0x180022c63  mov     rbx, [rsp+278h+arg_18]
0x180022c6b  add     rsp, 250h
0x180022c72  pop     r15
0x180022c74  pop     r14
0x180022c76  pop     rdi
0x180022c77  pop     rsi
0x180022c78  pop     rbp
0x180022c79  retn
```
