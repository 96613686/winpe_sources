# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009b84`
- end: `0x180009e45`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000892c`
- `0x180008bb0`
- `0x18000a570`
- `0x18000c610`

## callees

- `0x180009b84`
- `0x18000a880`
- `0x18000c836`
- `0x18000c860`
- `0x18000d010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180009cb4`
- `KERNEL32!FormatMessageW` at `0x180009cb4`
- `KERNEL32!GetCurrentThreadId` at `0x180009d3b`
- `KERNEL32!GetCurrentThreadId` at `0x180009d3b`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rdi
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
  v7 = (const char *)&word_180011258;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
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
0x180009b84  mov     [rsp+arg_18], rbx
0x180009b89  push    rbp
0x180009b8a  push    rsi
0x180009b8b  push    rdi
0x180009b8c  push    r14
0x180009b8e  push    r15
0x180009b90  sub     rsp, 250h
0x180009b97  mov     rax, cs:__security_cookie
0x180009b9e  xor     rax, rsp
0x180009ba1  mov     [rsp+278h+var_38], rax
0x180009ba9  mov     rbx, r8
0x180009bac  mov     rdi, rdx
0x180009baf  mov     r14, rcx
0x180009bb2  xor     r15d, r15d
0x180009bb5  test    rdx, rdx
0x180009bb8  jz      loc_180009E1B
0x180009bbe  test    rcx, rcx
0x180009bc1  jz      loc_180009E1B
0x180009bc7  mov     [rcx], r15w
0x180009bcb  mov     rax, cs:g_pfnResultLoggingCallback
0x180009bd2  test    rax, rax
0x180009bd5  jz      short loc_180009BF8
0x180009bd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009bde  jz      short loc_180009BF8
0x180009be0  mov     r8, rdx
0x180009be3  mov     rdx, rcx
0x180009be6  mov     rcx, rbx
0x180009be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bee  cmp     [r14], r15w
0x180009bf2  jnz     loc_180009E1B
0x180009bf8  lea     rsi, word_180011258
0x180009bff  mov     ecx, [rbx]
0x180009c01  mov     bpl, 8
0x180009c04  test    ecx, ecx
0x180009c06  jz      short loc_180009C48
0x180009c08  sub     ecx, 1
0x180009c0b  jz      short loc_180009C30
0x180009c0d  sub     ecx, 1
0x180009c10  jz      short loc_180009C20
0x180009c12  cmp     ecx, 1
0x180009c15  jnz     short loc_180009C4F
0x180009c17  lea     rsi, aFailfast; "FailFast"
0x180009c1e  jmp     short loc_180009C4F
0x180009c20  lea     rax, aLoghr; "LogHr"
0x180009c27  lea     rsi, aLognt; "LogNt"
0x180009c2e  jmp     short loc_180009C3E
0x180009c30  lea     rax, aReturnhr; "ReturnHr"
0x180009c37  lea     rsi, aReturnnt; "ReturnNt"
0x180009c3e  test    [rbx+4], bpl
0x180009c42  cmovz   rsi, rax
0x180009c46  jmp     short loc_180009C4F
0x180009c48  lea     rsi, aException; "Exception"
0x180009c4f  xor     edx, edx; Val
0x180009c51  mov     r8d, 200h; Size
0x180009c57  lea     rcx, [rsp+278h+Buffer]; void *
0x180009c5c  call    memset_0
0x180009c61  test    [rbx+4], bpl
0x180009c65  jz      short loc_180009C8A
0x180009c67  mov     ebp, [rbx+0Ch]
0x180009c6a  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009c71  test    rax, rax
0x180009c74  jz      short loc_180009CC0
0x180009c76  mov     r8d, 100h
0x180009c7c  lea     rdx, [rsp+278h+Buffer]
0x180009c81  mov     ecx, ebp
0x180009c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c88  jmp     short loc_180009CC0
0x180009c8a  mov     ebp, [rbx+8]
0x180009c8d  mov     [rsp+278h+Arguments], r15; Arguments
0x180009c92  mov     [rsp+278h+nSize], 100h; nSize
0x180009c9a  lea     rax, [rsp+278h+Buffer]
0x180009c9f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009ca4  mov     r9d, 400h; dwLanguageId
0x180009caa  mov     r8d, ebp; dwMessageId
0x180009cad  xor     edx, edx; lpSource
0x180009caf  mov     ecx, 1200h; dwFlags
0x180009cb4  call    cs:__imp_FormatMessageW
0x180009cbb  nop     dword ptr [rax+rax+00h]
0x180009cc0  lea     rdi, [r14+rdi*2]
0x180009cc4  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009cc8  mov     rax, [rbx+88h]
0x180009ccf  mov     rcx, [rbx+80h]
0x180009cd6  mov     rdx, rdi; unsigned __int16 *
0x180009cd9  test    r9, r9
0x180009cdc  jz      short loc_180009D00
0x180009cde  mov     [rsp+278h+Arguments], rax
0x180009ce3  mov     qword ptr [rsp+278h+nSize], rcx
0x180009ce8  mov     eax, [rbx+40h]
0x180009ceb  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009cef  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009cf6  mov     rcx, r14; this
0x180009cf9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cfe  jmp     short loc_180009D17
0x180009d00  mov     [rsp+278h+lpBuffer], rax
0x180009d05  mov     r9, rcx; unsigned __int16 *
0x180009d08  lea     r8, aHsP; "%hs!%p: "
0x180009d0f  mov     rcx, r14; this
0x180009d12  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d17  mov     r14, rax
0x180009d1a  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009d21  test    r9, r9
0x180009d24  jz      short loc_180009D3B
0x180009d26  lea     r8, aCallerP; "(caller: %p) "
0x180009d2d  mov     rdx, rdi; unsigned __int16 *
0x180009d30  mov     rcx, rax; this
0x180009d33  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d38  mov     r14, rax
0x180009d3b  call    cs:__imp_GetCurrentThreadId
0x180009d42  nop     dword ptr [rax+rax+00h]
0x180009d47  mov     ecx, [rbx+44h]
0x180009d4a  lea     rdx, [rsp+278h+Buffer]
0x180009d4f  mov     [rsp+278h+var_240], rdx
0x180009d54  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009d58  mov     [rsp+278h+nSize], eax
0x180009d5c  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x180009d60  mov     r9, rsi; unsigned __int16 *
0x180009d63  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009d6a  mov     rdx, rdi; unsigned __int16 *
0x180009d6d  mov     rcx, r14; this
0x180009d70  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d75  cmp     [rbx+18h], r15
0x180009d79  jnz     short loc_180009D8B
0x180009d7b  cmp     [rbx+48h], r15
0x180009d7f  jnz     short loc_180009D8B
0x180009d81  cmp     [rbx+30h], r15
0x180009d85  jz      loc_180009E1B
0x180009d8b  lea     r8, asc_180011348; "    "
0x180009d92  mov     rdx, rdi; unsigned __int16 *
0x180009d95  mov     rcx, rax; this
0x180009d98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d9d  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009da1  test    r9, r9
0x180009da4  jz      short loc_180009DB8
0x180009da6  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009dad  mov     rdx, rdi; unsigned __int16 *
0x180009db0  mov     rcx, rax; this
0x180009db3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009db8  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009dbc  test    r9, r9
0x180009dbf  jz      short loc_180009DD3
0x180009dc1  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009dc8  mov     rdx, rdi; unsigned __int16 *
0x180009dcb  mov     rcx, rax; this
0x180009dce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009dd3  mov     rcx, [rbx+28h]
0x180009dd7  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009ddb  mov     rdx, rdi; unsigned __int16 *
0x180009dde  test    rcx, rcx
0x180009de1  jz      short loc_180009DF9
0x180009de3  mov     [rsp+278h+lpBuffer], rcx
0x180009de8  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009def  mov     rcx, rax; this
0x180009df2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009df7  jmp     short loc_180009E1B
0x180009df9  mov     rcx, rax; this
0x180009dfc  test    r9, r9
0x180009dff  jz      short loc_180009E0F
0x180009e01  lea     r8, aHs; "[%hs]\n"
0x180009e08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009e0d  jmp     short loc_180009E1B
0x180009e0f  lea     r8, asc_1800113C0; "\n"
0x180009e16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009e1b  xor     eax, eax
0x180009e1d  mov     rcx, [rsp+278h+var_38]
0x180009e25  xor     rcx, rsp; StackCookie
0x180009e28  call    __security_check_cookie
0x180009e2d  mov     rbx, [rsp+278h+arg_18]
0x180009e35  add     rsp, 250h
0x180009e3c  pop     r15
0x180009e3e  pop     r14
0x180009e40  pop     rdi
0x180009e41  pop     rsi
0x180009e42  pop     rbp
0x180009e43  retn
```
