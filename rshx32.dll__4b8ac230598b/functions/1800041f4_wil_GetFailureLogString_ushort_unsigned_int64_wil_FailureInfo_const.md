# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800041f4`
- end: `0x1800044aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800030b0`
- `0x180003318`
- `0x180004b50`

## callees

- `0x1800041f4`
- `0x180004e50`
- `0x18001d33a`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004326`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004326`

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
          v8 = (const char *)&dword_1800209A4;
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
0x1800041f4  mov     [rsp+arg_18], rbx
0x1800041f9  push    rbp
0x1800041fa  push    rsi
0x1800041fb  push    rdi
0x1800041fc  push    r14
0x1800041fe  push    r15
0x180004200  sub     rsp, 250h
0x180004207  mov     rax, cs:__security_cookie
0x18000420e  xor     rax, rsp
0x180004211  mov     [rsp+278h+var_38], rax
0x180004219  xor     r15d, r15d
0x18000421c  mov     rbx, r8
0x18000421f  mov     rsi, rdx
0x180004222  mov     r14, rcx
0x180004225  test    rdx, rdx
0x180004228  jz      loc_180004481
0x18000422e  test    rcx, rcx
0x180004231  jz      loc_180004481
0x180004237  mov     rax, cs:g_pfnResultLoggingCallback
0x18000423e  mov     [rcx], r15w
0x180004242  test    rax, rax
0x180004245  jz      short loc_180004268
0x180004247  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000424e  jz      short loc_180004268
0x180004250  mov     r8, rdx
0x180004253  mov     rdx, rcx
0x180004256  mov     rcx, rbx
0x180004259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000425e  cmp     [r14], r15w
0x180004262  jnz     loc_180004481
0x180004268  mov     ecx, [rbx]
0x18000426a  mov     bpl, 8
0x18000426d  test    ecx, ecx
0x18000426f  jz      short loc_1800042BA
0x180004271  sub     ecx, 1
0x180004274  jz      short loc_1800042A2
0x180004276  sub     ecx, 1
0x180004279  jz      short loc_180004292
0x18000427b  cmp     ecx, 1
0x18000427e  jz      short loc_180004289
0x180004280  lea     rdi, dword_1800209A4
0x180004287  jmp     short loc_1800042C1
0x180004289  lea     rdi, aFailfast; "FailFast"
0x180004290  jmp     short loc_1800042C1
0x180004292  lea     rax, aLoghr; "LogHr"
0x180004299  lea     rdi, aLognt; "LogNt"
0x1800042a0  jmp     short loc_1800042B0
0x1800042a2  lea     rax, aReturnhr; "ReturnHr"
0x1800042a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800042b0  test    [rbx+4], bpl
0x1800042b4  cmovz   rdi, rax
0x1800042b8  jmp     short loc_1800042C1
0x1800042ba  lea     rdi, aException; "Exception"
0x1800042c1  xor     edx, edx; Val
0x1800042c3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800042c8  mov     r8d, 200h; Size
0x1800042ce  call    memset_0
0x1800042d3  test    [rbx+4], bpl
0x1800042d7  jz      short loc_1800042FC
0x1800042d9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800042e0  mov     ebp, [rbx+0Ch]
0x1800042e3  test    rax, rax
0x1800042e6  jz      short loc_18000432C
0x1800042e8  mov     r8d, 100h
0x1800042ee  lea     rdx, [rsp+278h+Buffer]
0x1800042f3  mov     ecx, ebp
0x1800042f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042fa  jmp     short loc_18000432C
0x1800042fc  mov     ebp, [rbx+8]
0x1800042ff  lea     rax, [rsp+278h+Buffer]
0x180004304  mov     [rsp+278h+Arguments], r15; Arguments
0x180004309  mov     r8d, ebp; dwMessageId
0x18000430c  mov     [rsp+278h+nSize], 100h; nSize
0x180004314  mov     r9d, 400h; dwLanguageId
0x18000431a  xor     edx, edx; lpSource
0x18000431c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004321  mov     ecx, 1200h; dwFlags
0x180004326  call    cs:__imp_FormatMessageW
0x18000432c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004330  lea     rsi, [r14+rsi*2]
0x180004334  mov     rax, [rbx+88h]
0x18000433b  mov     rdx, rsi; unsigned __int16 *
0x18000433e  mov     rcx, [rbx+80h]
0x180004345  test    r9, r9
0x180004348  jz      short loc_18000436C
0x18000434a  mov     [rsp+278h+Arguments], rax
0x18000434f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004356  mov     eax, [rbx+40h]
0x180004359  mov     qword ptr [rsp+278h+nSize], rcx
0x18000435e  mov     rcx, r14; this
0x180004361  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004365  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000436a  jmp     short loc_180004383
0x18000436c  mov     r9, rcx; unsigned __int16 *
0x18000436f  mov     [rsp+278h+lpBuffer], rax
0x180004374  mov     rcx, r14; this
0x180004377  lea     r8, aHsP; "%hs!%p: "
0x18000437e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004383  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000438a  mov     r14, rax
0x18000438d  test    r9, r9
0x180004390  jz      short loc_1800043A7
0x180004392  lea     r8, aCallerP; "(caller: %p) "
0x180004399  mov     rdx, rsi; unsigned __int16 *
0x18000439c  mov     rcx, rax; this
0x18000439f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043a4  mov     r14, rax
0x1800043a7  call    cs:__imp_GetCurrentThreadId
0x1800043ad  lea     rcx, [rsp+278h+Buffer]
0x1800043b2  mov     r9, rdi; unsigned __int16 *
0x1800043b5  mov     [rsp+278h+var_240], rcx
0x1800043ba  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800043c1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800043c5  mov     rdx, rsi; unsigned __int16 *
0x1800043c8  mov     [rsp+278h+nSize], eax
0x1800043cc  mov     rcx, r14; this
0x1800043cf  mov     eax, [rbx+44h]
0x1800043d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800043d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043db  cmp     [rbx+18h], r15
0x1800043df  jnz     short loc_1800043F1
0x1800043e1  cmp     [rbx+48h], r15
0x1800043e5  jnz     short loc_1800043F1
0x1800043e7  cmp     [rbx+30h], r15
0x1800043eb  jz      loc_180004481
0x1800043f1  lea     r8, asc_180020A90; "    "
0x1800043f8  mov     rdx, rsi; unsigned __int16 *
0x1800043fb  mov     rcx, rax; this
0x1800043fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004403  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004407  test    r9, r9
0x18000440a  jz      short loc_18000441E
0x18000440c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004413  mov     rdx, rsi; unsigned __int16 *
0x180004416  mov     rcx, rax; this
0x180004419  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000441e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004422  test    r9, r9
0x180004425  jz      short loc_180004439
0x180004427  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000442e  mov     rdx, rsi; unsigned __int16 *
0x180004431  mov     rcx, rax; this
0x180004434  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004439  mov     rcx, [rbx+28h]
0x18000443d  mov     rdx, rsi; unsigned __int16 *
0x180004440  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004444  test    rcx, rcx
0x180004447  jz      short loc_18000445F
0x180004449  mov     [rsp+278h+lpBuffer], rcx
0x18000444e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004455  mov     rcx, rax; this
0x180004458  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000445d  jmp     short loc_180004481
0x18000445f  mov     rcx, rax; this
0x180004462  test    r9, r9
0x180004465  jz      short loc_180004475
0x180004467  lea     r8, aHs; "[%hs]\n"
0x18000446e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004473  jmp     short loc_180004481
0x180004475  lea     r8, asc_180020B08; "\n"
0x18000447c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004481  xor     eax, eax
0x180004483  mov     rcx, [rsp+278h+var_38]
0x18000448b  xor     rcx, rsp; StackCookie
0x18000448e  call    __security_check_cookie
0x180004493  mov     rbx, [rsp+278h+arg_18]
0x18000449b  add     rsp, 250h
0x1800044a2  pop     r15
0x1800044a4  pop     r14
0x1800044a6  pop     rdi
0x1800044a7  pop     rsi
0x1800044a8  pop     rbp
0x1800044a9  retn
```
