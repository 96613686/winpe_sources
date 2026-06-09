# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009b44`
- end: `0x180009e07`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009fcc`
- `0x18000a8b0`
- `0x18000b720`
- `0x18000de3c`

## callees

- `0x180008a90`
- `0x18000953c`
- `0x180009b44`
- `0x180009f48`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009cfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009cfd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009c76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009c76`

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
          v7 = (const char *)&dword_18002202C;
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
0x180009b44  mov     [rsp+arg_18], rbx
0x180009b49  push    rbp
0x180009b4a  push    rsi
0x180009b4b  push    rdi
0x180009b4c  push    r14
0x180009b4e  push    r15
0x180009b50  sub     rsp, 250h
0x180009b57  mov     rax, cs:__security_cookie
0x180009b5e  xor     rax, rsp
0x180009b61  mov     [rsp+278h+var_38], rax
0x180009b69  mov     rbx, r8
0x180009b6c  mov     rsi, rdx
0x180009b6f  mov     r14, rcx
0x180009b72  xor     r15d, r15d
0x180009b75  test    rdx, rdx
0x180009b78  jz      loc_180009DDD
0x180009b7e  test    rcx, rcx
0x180009b81  jz      loc_180009DDD
0x180009b87  mov     [rcx], r15w
0x180009b8b  mov     rax, cs:g_pfnResultLoggingCallback
0x180009b92  test    rax, rax
0x180009b95  jz      short loc_180009BB8
0x180009b97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009b9e  jz      short loc_180009BB8
0x180009ba0  mov     r8, rdx
0x180009ba3  mov     rdx, rcx
0x180009ba6  mov     rcx, rbx
0x180009ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bae  cmp     [r14], r15w
0x180009bb2  jnz     loc_180009DDD
0x180009bb8  mov     ecx, [rbx]
0x180009bba  mov     bpl, 8
0x180009bbd  test    ecx, ecx
0x180009bbf  jz      short loc_180009C0A
0x180009bc1  sub     ecx, 1
0x180009bc4  jz      short loc_180009BF2
0x180009bc6  sub     ecx, 1
0x180009bc9  jz      short loc_180009BE2
0x180009bcb  cmp     ecx, 1
0x180009bce  jz      short loc_180009BD9
0x180009bd0  lea     rdi, dword_18002202C
0x180009bd7  jmp     short loc_180009C11
0x180009bd9  lea     rdi, aFailfast; "FailFast"
0x180009be0  jmp     short loc_180009C11
0x180009be2  lea     rax, aLoghr; "LogHr"
0x180009be9  lea     rdi, aLognt; "LogNt"
0x180009bf0  jmp     short loc_180009C00
0x180009bf2  lea     rax, aReturnhr; "ReturnHr"
0x180009bf9  lea     rdi, aReturnnt; "ReturnNt"
0x180009c00  test    [rbx+4], bpl
0x180009c04  cmovz   rdi, rax
0x180009c08  jmp     short loc_180009C11
0x180009c0a  lea     rdi, aException; "Exception"
0x180009c11  xor     edx, edx; Val
0x180009c13  mov     r8d, 200h; Size
0x180009c19  lea     rcx, [rsp+278h+Buffer]; void *
0x180009c1e  call    memset_0
0x180009c23  test    [rbx+4], bpl
0x180009c27  jz      short loc_180009C4C
0x180009c29  mov     ebp, [rbx+0Ch]
0x180009c2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009c33  test    rax, rax
0x180009c36  jz      short loc_180009C82
0x180009c38  mov     r8d, 100h
0x180009c3e  lea     rdx, [rsp+278h+Buffer]
0x180009c43  mov     ecx, ebp
0x180009c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c4a  jmp     short loc_180009C82
0x180009c4c  mov     ebp, [rbx+8]
0x180009c4f  mov     [rsp+278h+Arguments], r15; Arguments
0x180009c54  mov     [rsp+278h+nSize], 100h; nSize
0x180009c5c  lea     rax, [rsp+278h+Buffer]
0x180009c61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009c66  mov     r9d, 400h; dwLanguageId
0x180009c6c  mov     r8d, ebp; dwMessageId
0x180009c6f  xor     edx, edx; lpSource
0x180009c71  mov     ecx, 1200h; dwFlags
0x180009c76  call    cs:__imp_FormatMessageW
0x180009c7d  nop     dword ptr [rax+rax+00h]
0x180009c82  lea     rsi, [r14+rsi*2]
0x180009c86  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009c8a  mov     rax, [rbx+88h]
0x180009c91  mov     rcx, [rbx+80h]
0x180009c98  mov     rdx, rsi; unsigned __int16 *
0x180009c9b  test    r9, r9
0x180009c9e  jz      short loc_180009CC2
0x180009ca0  mov     [rsp+278h+Arguments], rax
0x180009ca5  mov     qword ptr [rsp+278h+nSize], rcx
0x180009caa  mov     eax, [rbx+40h]
0x180009cad  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009cb1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009cb8  mov     rcx, r14; this
0x180009cbb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cc0  jmp     short loc_180009CD9
0x180009cc2  mov     [rsp+278h+lpBuffer], rax
0x180009cc7  mov     r9, rcx; unsigned __int16 *
0x180009cca  lea     r8, aHsP; "%hs!%p: "
0x180009cd1  mov     rcx, r14; this
0x180009cd4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cd9  mov     r14, rax
0x180009cdc  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009ce3  test    r9, r9
0x180009ce6  jz      short loc_180009CFD
0x180009ce8  lea     r8, aCallerP; "(caller: %p) "
0x180009cef  mov     rdx, rsi; unsigned __int16 *
0x180009cf2  mov     rcx, rax; this
0x180009cf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cfa  mov     r14, rax
0x180009cfd  call    cs:__imp_GetCurrentThreadId
0x180009d04  nop     dword ptr [rax+rax+00h]
0x180009d09  lea     rcx, [rsp+278h+Buffer]
0x180009d0e  mov     [rsp+278h+var_240], rcx
0x180009d13  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009d17  mov     [rsp+278h+nSize], eax
0x180009d1b  mov     eax, [rbx+44h]
0x180009d1e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009d22  mov     r9, rdi; unsigned __int16 *
0x180009d25  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009d2c  mov     rdx, rsi; unsigned __int16 *
0x180009d2f  mov     rcx, r14; this
0x180009d32  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d37  cmp     [rbx+18h], r15
0x180009d3b  jnz     short loc_180009D4D
0x180009d3d  cmp     [rbx+48h], r15
0x180009d41  jnz     short loc_180009D4D
0x180009d43  cmp     [rbx+30h], r15
0x180009d47  jz      loc_180009DDD
0x180009d4d  lea     r8, asc_180022210; "    "
0x180009d54  mov     rdx, rsi; unsigned __int16 *
0x180009d57  mov     rcx, rax; this
0x180009d5a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d5f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009d63  test    r9, r9
0x180009d66  jz      short loc_180009D7A
0x180009d68  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009d6f  mov     rdx, rsi; unsigned __int16 *
0x180009d72  mov     rcx, rax; this
0x180009d75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d7a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009d7e  test    r9, r9
0x180009d81  jz      short loc_180009D95
0x180009d83  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009d8a  mov     rdx, rsi; unsigned __int16 *
0x180009d8d  mov     rcx, rax; this
0x180009d90  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d95  mov     rcx, [rbx+28h]
0x180009d99  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009d9d  mov     rdx, rsi; unsigned __int16 *
0x180009da0  test    rcx, rcx
0x180009da3  jz      short loc_180009DBB
0x180009da5  mov     [rsp+278h+lpBuffer], rcx
0x180009daa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009db1  mov     rcx, rax; this
0x180009db4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009db9  jmp     short loc_180009DDD
0x180009dbb  mov     rcx, rax; this
0x180009dbe  test    r9, r9
0x180009dc1  jz      short loc_180009DD1
0x180009dc3  lea     r8, aHs; "[%hs]\n"
0x180009dca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009dcf  jmp     short loc_180009DDD
0x180009dd1  lea     r8, asc_180022288; "\n"
0x180009dd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009ddd  xor     eax, eax
0x180009ddf  mov     rcx, [rsp+278h+var_38]
0x180009de7  xor     rcx, rsp; StackCookie
0x180009dea  call    __security_check_cookie
0x180009def  mov     rbx, [rsp+278h+arg_18]
0x180009df7  add     rsp, 250h
0x180009dfe  pop     r15
0x180009e00  pop     r14
0x180009e02  pop     rdi
0x180009e03  pop     rsi
0x180009e04  pop     rbp
0x180009e05  retn
```
