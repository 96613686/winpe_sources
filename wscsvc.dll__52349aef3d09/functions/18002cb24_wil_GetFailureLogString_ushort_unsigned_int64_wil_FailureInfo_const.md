# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002cb24`
- end: `0x18002cdda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18002bb6c`
- `0x18002d200`
- `0x18002d550`
- `0x18002f2e0`

## callees

- `0x18002cb24`
- `0x18002d500`
- `0x18003fbf2`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ccd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ccd7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002cc56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002cc56`

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
          v7 = (const char *)&qword_180047890;
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
0x18002cb24  mov     [rsp+arg_18], rbx
0x18002cb29  push    rbp
0x18002cb2a  push    rsi
0x18002cb2b  push    rdi
0x18002cb2c  push    r14
0x18002cb2e  push    r15
0x18002cb30  sub     rsp, 250h
0x18002cb37  mov     rax, cs:__security_cookie
0x18002cb3e  xor     rax, rsp
0x18002cb41  mov     [rsp+278h+var_38], rax
0x18002cb49  mov     rbx, r8
0x18002cb4c  mov     rsi, rdx
0x18002cb4f  mov     r14, rcx
0x18002cb52  xor     r15d, r15d
0x18002cb55  test    rdx, rdx
0x18002cb58  jz      loc_18002CDB1
0x18002cb5e  test    rcx, rcx
0x18002cb61  jz      loc_18002CDB1
0x18002cb67  mov     [rcx], r15w
0x18002cb6b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002cb72  test    rax, rax
0x18002cb75  jz      short loc_18002CB98
0x18002cb77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002cb7e  jz      short loc_18002CB98
0x18002cb80  mov     r8, rdx
0x18002cb83  mov     rdx, rcx
0x18002cb86  mov     rcx, rbx
0x18002cb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb8e  cmp     [r14], r15w
0x18002cb92  jnz     loc_18002CDB1
0x18002cb98  mov     ecx, [rbx]
0x18002cb9a  mov     bpl, 8
0x18002cb9d  test    ecx, ecx
0x18002cb9f  jz      short loc_18002CBEA
0x18002cba1  sub     ecx, 1
0x18002cba4  jz      short loc_18002CBD2
0x18002cba6  sub     ecx, 1
0x18002cba9  jz      short loc_18002CBC2
0x18002cbab  cmp     ecx, 1
0x18002cbae  jz      short loc_18002CBB9
0x18002cbb0  lea     rdi, qword_180047890
0x18002cbb7  jmp     short loc_18002CBF1
0x18002cbb9  lea     rdi, aFailfast; "FailFast"
0x18002cbc0  jmp     short loc_18002CBF1
0x18002cbc2  lea     rax, aLoghr; "LogHr"
0x18002cbc9  lea     rdi, aLognt; "LogNt"
0x18002cbd0  jmp     short loc_18002CBE0
0x18002cbd2  lea     rax, aReturnhr; "ReturnHr"
0x18002cbd9  lea     rdi, aReturnnt; "ReturnNt"
0x18002cbe0  test    [rbx+4], bpl
0x18002cbe4  cmovz   rdi, rax
0x18002cbe8  jmp     short loc_18002CBF1
0x18002cbea  lea     rdi, aException; "Exception"
0x18002cbf1  xor     edx, edx; Val
0x18002cbf3  mov     r8d, 200h; Size
0x18002cbf9  lea     rcx, [rsp+278h+Buffer]; void *
0x18002cbfe  call    memset_0
0x18002cc03  test    [rbx+4], bpl
0x18002cc07  jz      short loc_18002CC2C
0x18002cc09  mov     ebp, [rbx+0Ch]
0x18002cc0c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002cc13  test    rax, rax
0x18002cc16  jz      short loc_18002CC5C
0x18002cc18  mov     r8d, 100h
0x18002cc1e  lea     rdx, [rsp+278h+Buffer]
0x18002cc23  mov     ecx, ebp
0x18002cc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc2a  jmp     short loc_18002CC5C
0x18002cc2c  mov     ebp, [rbx+8]
0x18002cc2f  mov     [rsp+278h+Arguments], r15; Arguments
0x18002cc34  mov     [rsp+278h+nSize], 100h; nSize
0x18002cc3c  lea     rax, [rsp+278h+Buffer]
0x18002cc41  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002cc46  mov     r9d, 400h; dwLanguageId
0x18002cc4c  mov     r8d, ebp; dwMessageId
0x18002cc4f  xor     edx, edx; lpSource
0x18002cc51  mov     ecx, 1200h; dwFlags
0x18002cc56  call    cs:__imp_FormatMessageW
0x18002cc5c  lea     rsi, [r14+rsi*2]
0x18002cc60  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002cc64  mov     rax, [rbx+88h]
0x18002cc6b  mov     rcx, [rbx+80h]
0x18002cc72  mov     rdx, rsi; unsigned __int16 *
0x18002cc75  test    r9, r9
0x18002cc78  jz      short loc_18002CC9C
0x18002cc7a  mov     [rsp+278h+Arguments], rax
0x18002cc7f  mov     qword ptr [rsp+278h+nSize], rcx
0x18002cc84  mov     eax, [rbx+40h]
0x18002cc87  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002cc8b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002cc92  mov     rcx, r14; this
0x18002cc95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cc9a  jmp     short loc_18002CCB3
0x18002cc9c  mov     [rsp+278h+lpBuffer], rax
0x18002cca1  mov     r9, rcx; unsigned __int16 *
0x18002cca4  lea     r8, aHsP; "%hs!%p: "
0x18002ccab  mov     rcx, r14; this
0x18002ccae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002ccb3  mov     r14, rax
0x18002ccb6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002ccbd  test    r9, r9
0x18002ccc0  jz      short loc_18002CCD7
0x18002ccc2  lea     r8, aCallerP; "(caller: %p) "
0x18002ccc9  mov     rdx, rsi; unsigned __int16 *
0x18002cccc  mov     rcx, rax; this
0x18002cccf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002ccd4  mov     r14, rax
0x18002ccd7  call    cs:__imp_GetCurrentThreadId
0x18002ccdd  lea     rcx, [rsp+278h+Buffer]
0x18002cce2  mov     [rsp+278h+var_240], rcx
0x18002cce7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002cceb  mov     [rsp+278h+nSize], eax
0x18002ccef  mov     eax, [rbx+44h]
0x18002ccf2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002ccf6  mov     r9, rdi; unsigned __int16 *
0x18002ccf9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002cd00  mov     rdx, rsi; unsigned __int16 *
0x18002cd03  mov     rcx, r14; this
0x18002cd06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cd0b  cmp     [rbx+18h], r15
0x18002cd0f  jnz     short loc_18002CD21
0x18002cd11  cmp     [rbx+48h], r15
0x18002cd15  jnz     short loc_18002CD21
0x18002cd17  cmp     [rbx+30h], r15
0x18002cd1b  jz      loc_18002CDB1
0x18002cd21  lea     r8, asc_180047980; "    "
0x18002cd28  mov     rdx, rsi; unsigned __int16 *
0x18002cd2b  mov     rcx, rax; this
0x18002cd2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cd33  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002cd37  test    r9, r9
0x18002cd3a  jz      short loc_18002CD4E
0x18002cd3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002cd43  mov     rdx, rsi; unsigned __int16 *
0x18002cd46  mov     rcx, rax; this
0x18002cd49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cd4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002cd52  test    r9, r9
0x18002cd55  jz      short loc_18002CD69
0x18002cd57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002cd5e  mov     rdx, rsi; unsigned __int16 *
0x18002cd61  mov     rcx, rax; this
0x18002cd64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cd69  mov     rcx, [rbx+28h]
0x18002cd6d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002cd71  mov     rdx, rsi; unsigned __int16 *
0x18002cd74  test    rcx, rcx
0x18002cd77  jz      short loc_18002CD8F
0x18002cd79  mov     [rsp+278h+lpBuffer], rcx
0x18002cd7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002cd85  mov     rcx, rax; this
0x18002cd88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cd8d  jmp     short loc_18002CDB1
0x18002cd8f  mov     rcx, rax; this
0x18002cd92  test    r9, r9
0x18002cd95  jz      short loc_18002CDA5
0x18002cd97  lea     r8, aHs; "[%hs]\n"
0x18002cd9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cda3  jmp     short loc_18002CDB1
0x18002cda5  lea     r8, asc_1800479F8; "\n"
0x18002cdac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002cdb1  xor     eax, eax
0x18002cdb3  mov     rcx, [rsp+278h+var_38]
0x18002cdbb  xor     rcx, rsp; StackCookie
0x18002cdbe  call    __security_check_cookie
0x18002cdc3  mov     rbx, [rsp+278h+arg_18]
0x18002cdcb  add     rsp, 250h
0x18002cdd2  pop     r15
0x18002cdd4  pop     r14
0x18002cdd6  pop     rdi
0x18002cdd7  pop     rsi
0x18002cdd8  pop     rbp
0x18002cdd9  retn
```
