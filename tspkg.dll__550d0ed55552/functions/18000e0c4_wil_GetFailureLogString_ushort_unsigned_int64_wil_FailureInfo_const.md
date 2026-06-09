# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000e0c4`
- end: `0x18000e37a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cdd4`
- `0x18000e9b8`

## callees

- `0x18000b550`
- `0x18000c1a4`
- `0x18000e0c4`
- `0x18000ecb8`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e277`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e1f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e1f6`

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
          v8 = (const char *)&byte_18001F7EB;
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
0x18000e0c4  mov     [rsp+arg_18], rbx
0x18000e0c9  push    rbp
0x18000e0ca  push    rsi
0x18000e0cb  push    rdi
0x18000e0cc  push    r14
0x18000e0ce  push    r15
0x18000e0d0  sub     rsp, 250h
0x18000e0d7  mov     rax, cs:__security_cookie
0x18000e0de  xor     rax, rsp
0x18000e0e1  mov     [rsp+278h+var_38], rax
0x18000e0e9  xor     r15d, r15d
0x18000e0ec  mov     rbx, r8
0x18000e0ef  mov     rsi, rdx
0x18000e0f2  mov     r14, rcx
0x18000e0f5  test    rdx, rdx
0x18000e0f8  jz      loc_18000E351
0x18000e0fe  test    rcx, rcx
0x18000e101  jz      loc_18000E351
0x18000e107  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e10e  mov     [rcx], r15w
0x18000e112  test    rax, rax
0x18000e115  jz      short loc_18000E138
0x18000e117  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000e11e  jz      short loc_18000E138
0x18000e120  mov     r8, rdx
0x18000e123  mov     rdx, rcx
0x18000e126  mov     rcx, rbx
0x18000e129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e12e  cmp     [r14], r15w
0x18000e132  jnz     loc_18000E351
0x18000e138  mov     ecx, [rbx]
0x18000e13a  mov     bpl, 8
0x18000e13d  test    ecx, ecx
0x18000e13f  jz      short loc_18000E18A
0x18000e141  sub     ecx, 1
0x18000e144  jz      short loc_18000E172
0x18000e146  sub     ecx, 1
0x18000e149  jz      short loc_18000E162
0x18000e14b  cmp     ecx, 1
0x18000e14e  jz      short loc_18000E159
0x18000e150  lea     rdi, byte_18001F7EB
0x18000e157  jmp     short loc_18000E191
0x18000e159  lea     rdi, aFailfast; "FailFast"
0x18000e160  jmp     short loc_18000E191
0x18000e162  lea     rax, aLoghr; "LogHr"
0x18000e169  lea     rdi, aLognt; "LogNt"
0x18000e170  jmp     short loc_18000E180
0x18000e172  lea     rax, aReturnhr; "ReturnHr"
0x18000e179  lea     rdi, aReturnnt; "ReturnNt"
0x18000e180  test    [rbx+4], bpl
0x18000e184  cmovz   rdi, rax
0x18000e188  jmp     short loc_18000E191
0x18000e18a  lea     rdi, aException; "Exception"
0x18000e191  xor     edx, edx; Val
0x18000e193  lea     rcx, [rsp+278h+Buffer]; void *
0x18000e198  mov     r8d, 200h; Size
0x18000e19e  call    memset_0
0x18000e1a3  test    [rbx+4], bpl
0x18000e1a7  jz      short loc_18000E1CC
0x18000e1a9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000e1b0  mov     ebp, [rbx+0Ch]
0x18000e1b3  test    rax, rax
0x18000e1b6  jz      short loc_18000E1FC
0x18000e1b8  mov     r8d, 100h
0x18000e1be  lea     rdx, [rsp+278h+Buffer]
0x18000e1c3  mov     ecx, ebp
0x18000e1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ca  jmp     short loc_18000E1FC
0x18000e1cc  mov     ebp, [rbx+8]
0x18000e1cf  lea     rax, [rsp+278h+Buffer]
0x18000e1d4  mov     [rsp+278h+Arguments], r15; Arguments
0x18000e1d9  mov     r8d, ebp; dwMessageId
0x18000e1dc  mov     [rsp+278h+nSize], 100h; nSize
0x18000e1e4  mov     r9d, 400h; dwLanguageId
0x18000e1ea  xor     edx, edx; lpSource
0x18000e1ec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000e1f1  mov     ecx, 1200h; dwFlags
0x18000e1f6  call    cs:__imp_FormatMessageW
0x18000e1fc  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000e200  lea     rsi, [r14+rsi*2]
0x18000e204  mov     rax, [rbx+88h]
0x18000e20b  mov     rdx, rsi; unsigned __int16 *
0x18000e20e  mov     rcx, [rbx+80h]
0x18000e215  test    r9, r9
0x18000e218  jz      short loc_18000E23C
0x18000e21a  mov     [rsp+278h+Arguments], rax
0x18000e21f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000e226  mov     eax, [rbx+40h]
0x18000e229  mov     qword ptr [rsp+278h+nSize], rcx
0x18000e22e  mov     rcx, r14; this
0x18000e231  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000e235  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e23a  jmp     short loc_18000E253
0x18000e23c  mov     r9, rcx; unsigned __int16 *
0x18000e23f  mov     [rsp+278h+lpBuffer], rax
0x18000e244  mov     rcx, r14; this
0x18000e247  lea     r8, aHsP; "%hs!%p: "
0x18000e24e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e253  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000e25a  mov     r14, rax
0x18000e25d  test    r9, r9
0x18000e260  jz      short loc_18000E277
0x18000e262  lea     r8, aCallerP; "(caller: %p) "
0x18000e269  mov     rdx, rsi; unsigned __int16 *
0x18000e26c  mov     rcx, rax; this
0x18000e26f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e274  mov     r14, rax
0x18000e277  call    cs:__imp_GetCurrentThreadId
0x18000e27d  lea     rcx, [rsp+278h+Buffer]
0x18000e282  mov     r9, rdi; unsigned __int16 *
0x18000e285  mov     [rsp+278h+var_240], rcx
0x18000e28a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000e291  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000e295  mov     rdx, rsi; unsigned __int16 *
0x18000e298  mov     [rsp+278h+nSize], eax
0x18000e29c  mov     rcx, r14; this
0x18000e29f  mov     eax, [rbx+44h]
0x18000e2a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000e2a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e2ab  cmp     [rbx+18h], r15
0x18000e2af  jnz     short loc_18000E2C1
0x18000e2b1  cmp     [rbx+48h], r15
0x18000e2b5  jnz     short loc_18000E2C1
0x18000e2b7  cmp     [rbx+30h], r15
0x18000e2bb  jz      loc_18000E351
0x18000e2c1  lea     r8, asc_18001F8D8; "    "
0x18000e2c8  mov     rdx, rsi; unsigned __int16 *
0x18000e2cb  mov     rcx, rax; this
0x18000e2ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e2d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000e2d7  test    r9, r9
0x18000e2da  jz      short loc_18000E2EE
0x18000e2dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000e2e3  mov     rdx, rsi; unsigned __int16 *
0x18000e2e6  mov     rcx, rax; this
0x18000e2e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e2ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000e2f2  test    r9, r9
0x18000e2f5  jz      short loc_18000E309
0x18000e2f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000e2fe  mov     rdx, rsi; unsigned __int16 *
0x18000e301  mov     rcx, rax; this
0x18000e304  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e309  mov     rcx, [rbx+28h]
0x18000e30d  mov     rdx, rsi; unsigned __int16 *
0x18000e310  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000e314  test    rcx, rcx
0x18000e317  jz      short loc_18000E32F
0x18000e319  mov     [rsp+278h+lpBuffer], rcx
0x18000e31e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000e325  mov     rcx, rax; this
0x18000e328  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e32d  jmp     short loc_18000E351
0x18000e32f  mov     rcx, rax; this
0x18000e332  test    r9, r9
0x18000e335  jz      short loc_18000E345
0x18000e337  lea     r8, aHs; "[%hs]\n"
0x18000e33e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e343  jmp     short loc_18000E351
0x18000e345  lea     r8, asc_18001F950; "\n"
0x18000e34c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000e351  xor     eax, eax
0x18000e353  mov     rcx, [rsp+278h+var_38]
0x18000e35b  xor     rcx, rsp; StackCookie
0x18000e35e  call    __security_check_cookie
0x18000e363  mov     rbx, [rsp+278h+arg_18]
0x18000e36b  add     rsp, 250h
0x18000e372  pop     r15
0x18000e374  pop     r14
0x18000e376  pop     rdi
0x18000e377  pop     rsi
0x18000e378  pop     rbp
0x18000e379  retn
```
