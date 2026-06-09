# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180038a48`
- end: `0x180038cfe`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180037ff8`
- `0x180038f68`
- `0x1800392b8`
- `0x180039a90`

## callees

- `0x180035830`
- `0x1800364ac`
- `0x180038a48`
- `0x180039268`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180038b7a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180038b7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038bfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038bfb`

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
          v7 = (const char *)&qword_180050CF0;
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
0x180038a48  mov     [rsp+arg_18], rbx
0x180038a4d  push    rbp
0x180038a4e  push    rsi
0x180038a4f  push    rdi
0x180038a50  push    r14
0x180038a52  push    r15
0x180038a54  sub     rsp, 250h
0x180038a5b  mov     rax, cs:__security_cookie
0x180038a62  xor     rax, rsp
0x180038a65  mov     [rsp+278h+var_38], rax
0x180038a6d  mov     rbx, r8
0x180038a70  mov     rsi, rdx
0x180038a73  mov     r14, rcx
0x180038a76  xor     r15d, r15d
0x180038a79  test    rdx, rdx
0x180038a7c  jz      loc_180038CD5
0x180038a82  test    rcx, rcx
0x180038a85  jz      loc_180038CD5
0x180038a8b  mov     [rcx], r15w
0x180038a8f  mov     rax, cs:g_pfnResultLoggingCallback
0x180038a96  test    rax, rax
0x180038a99  jz      short loc_180038ABC
0x180038a9b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180038aa2  jz      short loc_180038ABC
0x180038aa4  mov     r8, rdx
0x180038aa7  mov     rdx, rcx
0x180038aaa  mov     rcx, rbx
0x180038aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ab2  cmp     [r14], r15w
0x180038ab6  jnz     loc_180038CD5
0x180038abc  mov     ecx, [rbx]
0x180038abe  mov     bpl, 8
0x180038ac1  test    ecx, ecx
0x180038ac3  jz      short loc_180038B0E
0x180038ac5  sub     ecx, 1
0x180038ac8  jz      short loc_180038AF6
0x180038aca  sub     ecx, 1
0x180038acd  jz      short loc_180038AE6
0x180038acf  cmp     ecx, 1
0x180038ad2  jz      short loc_180038ADD
0x180038ad4  lea     rdi, qword_180050CF0
0x180038adb  jmp     short loc_180038B15
0x180038add  lea     rdi, aFailfast; "FailFast"
0x180038ae4  jmp     short loc_180038B15
0x180038ae6  lea     rax, aLoghr; "LogHr"
0x180038aed  lea     rdi, aLognt; "LogNt"
0x180038af4  jmp     short loc_180038B04
0x180038af6  lea     rax, aReturnhr; "ReturnHr"
0x180038afd  lea     rdi, aReturnnt; "ReturnNt"
0x180038b04  test    [rbx+4], bpl
0x180038b08  cmovz   rdi, rax
0x180038b0c  jmp     short loc_180038B15
0x180038b0e  lea     rdi, aException; "Exception"
0x180038b15  xor     edx, edx; Val
0x180038b17  mov     r8d, 200h; Size
0x180038b1d  lea     rcx, [rsp+278h+Buffer]; void *
0x180038b22  call    memset_0
0x180038b27  test    [rbx+4], bpl
0x180038b2b  jz      short loc_180038B50
0x180038b2d  mov     ebp, [rbx+0Ch]
0x180038b30  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180038b37  test    rax, rax
0x180038b3a  jz      short loc_180038B80
0x180038b3c  mov     r8d, 100h
0x180038b42  lea     rdx, [rsp+278h+Buffer]
0x180038b47  mov     ecx, ebp
0x180038b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b4e  jmp     short loc_180038B80
0x180038b50  mov     ebp, [rbx+8]
0x180038b53  mov     [rsp+278h+Arguments], r15; Arguments
0x180038b58  mov     [rsp+278h+nSize], 100h; nSize
0x180038b60  lea     rax, [rsp+278h+Buffer]
0x180038b65  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180038b6a  mov     r9d, 400h; dwLanguageId
0x180038b70  mov     r8d, ebp; dwMessageId
0x180038b73  xor     edx, edx; lpSource
0x180038b75  mov     ecx, 1200h; dwFlags
0x180038b7a  call    cs:__imp_FormatMessageW
0x180038b80  lea     rsi, [r14+rsi*2]
0x180038b84  mov     r9, [rbx+38h]; unsigned __int16 *
0x180038b88  mov     rax, [rbx+88h]
0x180038b8f  mov     rcx, [rbx+80h]
0x180038b96  mov     rdx, rsi; unsigned __int16 *
0x180038b99  test    r9, r9
0x180038b9c  jz      short loc_180038BC0
0x180038b9e  mov     [rsp+278h+Arguments], rax
0x180038ba3  mov     qword ptr [rsp+278h+nSize], rcx
0x180038ba8  mov     eax, [rbx+40h]
0x180038bab  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180038baf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180038bb6  mov     rcx, r14; this
0x180038bb9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038bbe  jmp     short loc_180038BD7
0x180038bc0  mov     [rsp+278h+lpBuffer], rax
0x180038bc5  mov     r9, rcx; unsigned __int16 *
0x180038bc8  lea     r8, aHsP; "%hs!%p: "
0x180038bcf  mov     rcx, r14; this
0x180038bd2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038bd7  mov     r14, rax
0x180038bda  mov     r9, [rbx+90h]; unsigned __int16 *
0x180038be1  test    r9, r9
0x180038be4  jz      short loc_180038BFB
0x180038be6  lea     r8, aCallerP; "(caller: %p) "
0x180038bed  mov     rdx, rsi; unsigned __int16 *
0x180038bf0  mov     rcx, rax; this
0x180038bf3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038bf8  mov     r14, rax
0x180038bfb  call    cs:__imp_GetCurrentThreadId
0x180038c01  lea     rcx, [rsp+278h+Buffer]
0x180038c06  mov     [rsp+278h+var_240], rcx
0x180038c0b  mov     dword ptr [rsp+278h+Arguments], ebp
0x180038c0f  mov     [rsp+278h+nSize], eax
0x180038c13  mov     eax, [rbx+44h]
0x180038c16  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180038c1a  mov     r9, rdi; unsigned __int16 *
0x180038c1d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180038c24  mov     rdx, rsi; unsigned __int16 *
0x180038c27  mov     rcx, r14; this
0x180038c2a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038c2f  cmp     [rbx+18h], r15
0x180038c33  jnz     short loc_180038C45
0x180038c35  cmp     [rbx+48h], r15
0x180038c39  jnz     short loc_180038C45
0x180038c3b  cmp     [rbx+30h], r15
0x180038c3f  jz      loc_180038CD5
0x180038c45  lea     r8, asc_180051890; "    "
0x180038c4c  mov     rdx, rsi; unsigned __int16 *
0x180038c4f  mov     rcx, rax; this
0x180038c52  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038c57  mov     r9, [rbx+18h]; unsigned __int16 *
0x180038c5b  test    r9, r9
0x180038c5e  jz      short loc_180038C72
0x180038c60  lea     r8, aMsgWs; "Msg:[%ws] "
0x180038c67  mov     rdx, rsi; unsigned __int16 *
0x180038c6a  mov     rcx, rax; this
0x180038c6d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038c72  mov     r9, [rbx+48h]; unsigned __int16 *
0x180038c76  test    r9, r9
0x180038c79  jz      short loc_180038C8D
0x180038c7b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180038c82  mov     rdx, rsi; unsigned __int16 *
0x180038c85  mov     rcx, rax; this
0x180038c88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038c8d  mov     rcx, [rbx+28h]
0x180038c91  mov     r9, [rbx+30h]; unsigned __int16 *
0x180038c95  mov     rdx, rsi; unsigned __int16 *
0x180038c98  test    rcx, rcx
0x180038c9b  jz      short loc_180038CB3
0x180038c9d  mov     [rsp+278h+lpBuffer], rcx
0x180038ca2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180038ca9  mov     rcx, rax; this
0x180038cac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038cb1  jmp     short loc_180038CD5
0x180038cb3  mov     rcx, rax; this
0x180038cb6  test    r9, r9
0x180038cb9  jz      short loc_180038CC9
0x180038cbb  lea     r8, aHs; "[%hs]\n"
0x180038cc2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038cc7  jmp     short loc_180038CD5
0x180038cc9  lea     r8, asc_180051908; "\n"
0x180038cd0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038cd5  xor     eax, eax
0x180038cd7  mov     rcx, [rsp+278h+var_38]
0x180038cdf  xor     rcx, rsp; StackCookie
0x180038ce2  call    __security_check_cookie
0x180038ce7  mov     rbx, [rsp+278h+arg_18]
0x180038cef  add     rsp, 250h
0x180038cf6  pop     r15
0x180038cf8  pop     r14
0x180038cfa  pop     rdi
0x180038cfb  pop     rsi
0x180038cfc  pop     rbp
0x180038cfd  retn
```
