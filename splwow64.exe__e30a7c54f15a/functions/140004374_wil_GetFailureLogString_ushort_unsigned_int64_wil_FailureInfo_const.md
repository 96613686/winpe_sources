# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004374`
- end: `0x14000462a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002e54`
- `0x1400030bc`
- `0x140004f10`

## callees

- `0x140001ee0`
- `0x1400028b8`
- `0x140004374`
- `0x140005210`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004527`
- `KERNEL32!GetCurrentThreadId` at `0x140004527`
- `KERNEL32!FormatMessageW` at `0x1400044a6`
- `KERNEL32!FormatMessageW` at `0x1400044a6`

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
          v8 = (const char *)&word_140019302;
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
0x140004374  mov     [rsp+arg_18], rbx
0x140004379  push    rbp
0x14000437a  push    rsi
0x14000437b  push    rdi
0x14000437c  push    r14
0x14000437e  push    r15
0x140004380  sub     rsp, 250h
0x140004387  mov     rax, cs:__security_cookie
0x14000438e  xor     rax, rsp
0x140004391  mov     [rsp+278h+var_38], rax
0x140004399  xor     r15d, r15d
0x14000439c  mov     rbx, r8
0x14000439f  mov     rsi, rdx
0x1400043a2  mov     r14, rcx
0x1400043a5  test    rdx, rdx
0x1400043a8  jz      loc_140004601
0x1400043ae  test    rcx, rcx
0x1400043b1  jz      loc_140004601
0x1400043b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400043be  mov     [rcx], r15w
0x1400043c2  test    rax, rax
0x1400043c5  jz      short loc_1400043E8
0x1400043c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400043ce  jz      short loc_1400043E8
0x1400043d0  mov     r8, rdx
0x1400043d3  mov     rdx, rcx
0x1400043d6  mov     rcx, rbx
0x1400043d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043de  cmp     [r14], r15w
0x1400043e2  jnz     loc_140004601
0x1400043e8  mov     ecx, [rbx]
0x1400043ea  mov     bpl, 8
0x1400043ed  test    ecx, ecx
0x1400043ef  jz      short loc_14000443A
0x1400043f1  sub     ecx, 1
0x1400043f4  jz      short loc_140004422
0x1400043f6  sub     ecx, 1
0x1400043f9  jz      short loc_140004412
0x1400043fb  cmp     ecx, 1
0x1400043fe  jz      short loc_140004409
0x140004400  lea     rdi, word_140019302
0x140004407  jmp     short loc_140004441
0x140004409  lea     rdi, aFailfast; "FailFast"
0x140004410  jmp     short loc_140004441
0x140004412  lea     rax, aLoghr; "LogHr"
0x140004419  lea     rdi, aLognt; "LogNt"
0x140004420  jmp     short loc_140004430
0x140004422  lea     rax, aReturnhr; "ReturnHr"
0x140004429  lea     rdi, aReturnnt; "ReturnNt"
0x140004430  test    [rbx+4], bpl
0x140004434  cmovz   rdi, rax
0x140004438  jmp     short loc_140004441
0x14000443a  lea     rdi, aException; "Exception"
0x140004441  xor     edx, edx; Val
0x140004443  lea     rcx, [rsp+278h+Buffer]; void *
0x140004448  mov     r8d, 200h; Size
0x14000444e  call    memset_0
0x140004453  test    [rbx+4], bpl
0x140004457  jz      short loc_14000447C
0x140004459  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004460  mov     ebp, [rbx+0Ch]
0x140004463  test    rax, rax
0x140004466  jz      short loc_1400044AC
0x140004468  mov     r8d, 100h
0x14000446e  lea     rdx, [rsp+278h+Buffer]
0x140004473  mov     ecx, ebp
0x140004475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000447a  jmp     short loc_1400044AC
0x14000447c  mov     ebp, [rbx+8]
0x14000447f  lea     rax, [rsp+278h+Buffer]
0x140004484  mov     [rsp+278h+Arguments], r15; Arguments
0x140004489  mov     r8d, ebp; dwMessageId
0x14000448c  mov     [rsp+278h+nSize], 100h; nSize
0x140004494  mov     r9d, 400h; dwLanguageId
0x14000449a  xor     edx, edx; lpSource
0x14000449c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400044a1  mov     ecx, 1200h; dwFlags
0x1400044a6  call    cs:__imp_FormatMessageW
0x1400044ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400044b0  lea     rsi, [r14+rsi*2]
0x1400044b4  mov     rax, [rbx+88h]
0x1400044bb  mov     rdx, rsi; unsigned __int16 *
0x1400044be  mov     rcx, [rbx+80h]
0x1400044c5  test    r9, r9
0x1400044c8  jz      short loc_1400044EC
0x1400044ca  mov     [rsp+278h+Arguments], rax
0x1400044cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400044d6  mov     eax, [rbx+40h]
0x1400044d9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400044de  mov     rcx, r14; this
0x1400044e1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400044e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044ea  jmp     short loc_140004503
0x1400044ec  mov     r9, rcx; unsigned __int16 *
0x1400044ef  mov     [rsp+278h+lpBuffer], rax
0x1400044f4  mov     rcx, r14; this
0x1400044f7  lea     r8, aHsP; "%hs!%p: "
0x1400044fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004503  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000450a  mov     r14, rax
0x14000450d  test    r9, r9
0x140004510  jz      short loc_140004527
0x140004512  lea     r8, aCallerP; "(caller: %p) "
0x140004519  mov     rdx, rsi; unsigned __int16 *
0x14000451c  mov     rcx, rax; this
0x14000451f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004524  mov     r14, rax
0x140004527  call    cs:__imp_GetCurrentThreadId
0x14000452d  lea     rcx, [rsp+278h+Buffer]
0x140004532  mov     r9, rdi; unsigned __int16 *
0x140004535  mov     [rsp+278h+var_240], rcx
0x14000453a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004541  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004545  mov     rdx, rsi; unsigned __int16 *
0x140004548  mov     [rsp+278h+nSize], eax
0x14000454c  mov     rcx, r14; this
0x14000454f  mov     eax, [rbx+44h]
0x140004552  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004556  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000455b  cmp     [rbx+18h], r15
0x14000455f  jnz     short loc_140004571
0x140004561  cmp     [rbx+48h], r15
0x140004565  jnz     short loc_140004571
0x140004567  cmp     [rbx+30h], r15
0x14000456b  jz      loc_140004601
0x140004571  lea     r8, asc_1400193F0; "    "
0x140004578  mov     rdx, rsi; unsigned __int16 *
0x14000457b  mov     rcx, rax; this
0x14000457e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004583  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004587  test    r9, r9
0x14000458a  jz      short loc_14000459E
0x14000458c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004593  mov     rdx, rsi; unsigned __int16 *
0x140004596  mov     rcx, rax; this
0x140004599  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000459e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400045a2  test    r9, r9
0x1400045a5  jz      short loc_1400045B9
0x1400045a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400045ae  mov     rdx, rsi; unsigned __int16 *
0x1400045b1  mov     rcx, rax; this
0x1400045b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045b9  mov     rcx, [rbx+28h]
0x1400045bd  mov     rdx, rsi; unsigned __int16 *
0x1400045c0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400045c4  test    rcx, rcx
0x1400045c7  jz      short loc_1400045DF
0x1400045c9  mov     [rsp+278h+lpBuffer], rcx
0x1400045ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400045d5  mov     rcx, rax; this
0x1400045d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045dd  jmp     short loc_140004601
0x1400045df  mov     rcx, rax; this
0x1400045e2  test    r9, r9
0x1400045e5  jz      short loc_1400045F5
0x1400045e7  lea     r8, aHs; "[%hs]\n"
0x1400045ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045f3  jmp     short loc_140004601
0x1400045f5  lea     r8, asc_140019468; "\n"
0x1400045fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004601  xor     eax, eax
0x140004603  mov     rcx, [rsp+278h+var_38]
0x14000460b  xor     rcx, rsp; StackCookie
0x14000460e  call    __security_check_cookie
0x140004613  mov     rbx, [rsp+278h+arg_18]
0x14000461b  add     rsp, 250h
0x140004622  pop     r15
0x140004624  pop     r14
0x140004626  pop     rdi
0x140004627  pop     rsi
0x140004628  pop     rbp
0x140004629  retn
```
