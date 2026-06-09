# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b0f4`
- end: `0x18000b3aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a020`
- `0x18000ba80`
- `0x18000bf38`
- `0x18000d2a0`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000b0f4`
- `0x18000bd84`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b226`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b226`

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
          v7 = (const char *)&byte_18009A357;
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
0x18000b0f4  mov     [rsp+arg_18], rbx
0x18000b0f9  push    rbp
0x18000b0fa  push    rsi
0x18000b0fb  push    rdi
0x18000b0fc  push    r14
0x18000b0fe  push    r15
0x18000b100  sub     rsp, 250h
0x18000b107  mov     rax, cs:__security_cookie
0x18000b10e  xor     rax, rsp
0x18000b111  mov     [rsp+278h+var_38], rax
0x18000b119  mov     rbx, r8
0x18000b11c  mov     rsi, rdx
0x18000b11f  mov     r14, rcx
0x18000b122  xor     r15d, r15d
0x18000b125  test    rdx, rdx
0x18000b128  jz      loc_18000B381
0x18000b12e  test    rcx, rcx
0x18000b131  jz      loc_18000B381
0x18000b137  mov     [rcx], r15w
0x18000b13b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b142  test    rax, rax
0x18000b145  jz      short loc_18000B168
0x18000b147  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b14e  jz      short loc_18000B168
0x18000b150  mov     r8, rdx
0x18000b153  mov     rdx, rcx
0x18000b156  mov     rcx, rbx
0x18000b159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b15e  cmp     [r14], r15w
0x18000b162  jnz     loc_18000B381
0x18000b168  mov     ecx, [rbx]
0x18000b16a  mov     bpl, 8
0x18000b16d  test    ecx, ecx
0x18000b16f  jz      short loc_18000B1BA
0x18000b171  sub     ecx, 1
0x18000b174  jz      short loc_18000B1A2
0x18000b176  sub     ecx, 1
0x18000b179  jz      short loc_18000B192
0x18000b17b  cmp     ecx, 1
0x18000b17e  jz      short loc_18000B189
0x18000b180  lea     rdi, byte_18009A357
0x18000b187  jmp     short loc_18000B1C1
0x18000b189  lea     rdi, aFailfast; "FailFast"
0x18000b190  jmp     short loc_18000B1C1
0x18000b192  lea     rax, aLoghr; "LogHr"
0x18000b199  lea     rdi, aLognt; "LogNt"
0x18000b1a0  jmp     short loc_18000B1B0
0x18000b1a2  lea     rax, aReturnhr; "ReturnHr"
0x18000b1a9  lea     rdi, aReturnnt; "ReturnNt"
0x18000b1b0  test    [rbx+4], bpl
0x18000b1b4  cmovz   rdi, rax
0x18000b1b8  jmp     short loc_18000B1C1
0x18000b1ba  lea     rdi, aException; "Exception"
0x18000b1c1  xor     edx, edx; Val
0x18000b1c3  mov     r8d, 200h; Size
0x18000b1c9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000b1ce  call    memset_0
0x18000b1d3  test    [rbx+4], bpl
0x18000b1d7  jz      short loc_18000B1FC
0x18000b1d9  mov     ebp, [rbx+0Ch]
0x18000b1dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000b1e3  test    rax, rax
0x18000b1e6  jz      short loc_18000B22C
0x18000b1e8  mov     r8d, 100h
0x18000b1ee  lea     rdx, [rsp+278h+Buffer]
0x18000b1f3  mov     ecx, ebp
0x18000b1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1fa  jmp     short loc_18000B22C
0x18000b1fc  mov     ebp, [rbx+8]
0x18000b1ff  mov     [rsp+278h+Arguments], r15; Arguments
0x18000b204  mov     [rsp+278h+nSize], 100h; nSize
0x18000b20c  lea     rax, [rsp+278h+Buffer]
0x18000b211  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000b216  mov     r9d, 400h; dwLanguageId
0x18000b21c  mov     r8d, ebp; dwMessageId
0x18000b21f  xor     edx, edx; lpSource
0x18000b221  mov     ecx, 1200h; dwFlags
0x18000b226  call    cs:__imp_FormatMessageW
0x18000b22c  lea     rsi, [r14+rsi*2]
0x18000b230  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000b234  mov     rax, [rbx+88h]
0x18000b23b  mov     rcx, [rbx+80h]
0x18000b242  mov     rdx, rsi; unsigned __int16 *
0x18000b245  test    r9, r9
0x18000b248  jz      short loc_18000B26C
0x18000b24a  mov     [rsp+278h+Arguments], rax
0x18000b24f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000b254  mov     eax, [rbx+40h]
0x18000b257  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b25b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b262  mov     rcx, r14; this
0x18000b265  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b26a  jmp     short loc_18000B283
0x18000b26c  mov     [rsp+278h+lpBuffer], rax
0x18000b271  mov     r9, rcx; unsigned __int16 *
0x18000b274  lea     r8, aHsP; "%hs!%p: "
0x18000b27b  mov     rcx, r14; this
0x18000b27e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b283  mov     r14, rax
0x18000b286  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000b28d  test    r9, r9
0x18000b290  jz      short loc_18000B2A7
0x18000b292  lea     r8, aCallerP; "(caller: %p) "
0x18000b299  mov     rdx, rsi; unsigned __int16 *
0x18000b29c  mov     rcx, rax; this
0x18000b29f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2a4  mov     r14, rax
0x18000b2a7  call    cs:__imp_GetCurrentThreadId
0x18000b2ad  lea     rcx, [rsp+278h+Buffer]
0x18000b2b2  mov     [rsp+278h+var_240], rcx
0x18000b2b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b2bb  mov     [rsp+278h+nSize], eax
0x18000b2bf  mov     eax, [rbx+44h]
0x18000b2c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b2c6  mov     r9, rdi; unsigned __int16 *
0x18000b2c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b2d0  mov     rdx, rsi; unsigned __int16 *
0x18000b2d3  mov     rcx, r14; this
0x18000b2d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2db  cmp     [rbx+18h], r15
0x18000b2df  jnz     short loc_18000B2F1
0x18000b2e1  cmp     [rbx+48h], r15
0x18000b2e5  jnz     short loc_18000B2F1
0x18000b2e7  cmp     [rbx+30h], r15
0x18000b2eb  jz      loc_18000B381
0x18000b2f1  lea     r8, asc_18009A480; "    "
0x18000b2f8  mov     rdx, rsi; unsigned __int16 *
0x18000b2fb  mov     rcx, rax; this
0x18000b2fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b303  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000b307  test    r9, r9
0x18000b30a  jz      short loc_18000B31E
0x18000b30c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b313  mov     rdx, rsi; unsigned __int16 *
0x18000b316  mov     rcx, rax; this
0x18000b319  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b31e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000b322  test    r9, r9
0x18000b325  jz      short loc_18000B339
0x18000b327  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b32e  mov     rdx, rsi; unsigned __int16 *
0x18000b331  mov     rcx, rax; this
0x18000b334  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b339  mov     rcx, [rbx+28h]
0x18000b33d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000b341  mov     rdx, rsi; unsigned __int16 *
0x18000b344  test    rcx, rcx
0x18000b347  jz      short loc_18000B35F
0x18000b349  mov     [rsp+278h+lpBuffer], rcx
0x18000b34e  lea     r8, aHsHs_2; "[%hs(%hs)]\n"
0x18000b355  mov     rcx, rax; this
0x18000b358  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b35d  jmp     short loc_18000B381
0x18000b35f  mov     rcx, rax; this
0x18000b362  test    r9, r9
0x18000b365  jz      short loc_18000B375
0x18000b367  lea     r8, aHs; "[%hs]\n"
0x18000b36e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b373  jmp     short loc_18000B381
0x18000b375  lea     r8, asc_18009A4F8; "\n"
0x18000b37c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b381  xor     eax, eax
0x18000b383  mov     rcx, [rsp+278h+var_38]
0x18000b38b  xor     rcx, rsp; StackCookie
0x18000b38e  call    __security_check_cookie
0x18000b393  mov     rbx, [rsp+278h+arg_18]
0x18000b39b  add     rsp, 250h
0x18000b3a2  pop     r15
0x18000b3a4  pop     r14
0x18000b3a6  pop     rdi
0x18000b3a7  pop     rsi
0x18000b3a8  pop     rbp
0x18000b3a9  retn
```
