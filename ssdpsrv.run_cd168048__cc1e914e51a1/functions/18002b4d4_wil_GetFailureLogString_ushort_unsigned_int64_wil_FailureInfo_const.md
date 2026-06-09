# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002b4d4`
- end: `0x18002b797`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002be78`

## callees

- `0x1800287d0`
- `0x18002911c`
- `0x18002b4d4`
- `0x18002c188`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b68d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b68d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002b606`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002b606`

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
          v8 = (const char *)&Format;
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
0x18002b4d4  mov     [rsp+arg_18], rbx
0x18002b4d9  push    rbp
0x18002b4da  push    rsi
0x18002b4db  push    rdi
0x18002b4dc  push    r14
0x18002b4de  push    r15
0x18002b4e0  sub     rsp, 250h
0x18002b4e7  mov     rax, cs:__security_cookie
0x18002b4ee  xor     rax, rsp
0x18002b4f1  mov     [rsp+278h+var_38], rax
0x18002b4f9  xor     r15d, r15d
0x18002b4fc  mov     rbx, r8
0x18002b4ff  mov     rsi, rdx
0x18002b502  mov     r14, rcx
0x18002b505  test    rdx, rdx
0x18002b508  jz      loc_18002B76D
0x18002b50e  test    rcx, rcx
0x18002b511  jz      loc_18002B76D
0x18002b517  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b51e  mov     [rcx], r15w
0x18002b522  test    rax, rax
0x18002b525  jz      short loc_18002B548
0x18002b527  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002b52e  jz      short loc_18002B548
0x18002b530  mov     r8, rdx
0x18002b533  mov     rdx, rcx
0x18002b536  mov     rcx, rbx
0x18002b539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b53e  cmp     [r14], r15w
0x18002b542  jnz     loc_18002B76D
0x18002b548  mov     ecx, [rbx]
0x18002b54a  mov     bpl, 8
0x18002b54d  test    ecx, ecx
0x18002b54f  jz      short loc_18002B59A
0x18002b551  sub     ecx, 1
0x18002b554  jz      short loc_18002B582
0x18002b556  sub     ecx, 1
0x18002b559  jz      short loc_18002B572
0x18002b55b  cmp     ecx, 1
0x18002b55e  jz      short loc_18002B569
0x18002b560  lea     rdi, Format
0x18002b567  jmp     short loc_18002B5A1
0x18002b569  lea     rdi, aFailfast; "FailFast"
0x18002b570  jmp     short loc_18002B5A1
0x18002b572  lea     rax, aLoghr; "LogHr"
0x18002b579  lea     rdi, aLognt; "LogNt"
0x18002b580  jmp     short loc_18002B590
0x18002b582  lea     rax, aReturnhr; "ReturnHr"
0x18002b589  lea     rdi, aReturnnt; "ReturnNt"
0x18002b590  test    [rbx+4], bpl
0x18002b594  cmovz   rdi, rax
0x18002b598  jmp     short loc_18002B5A1
0x18002b59a  lea     rdi, aException; "Exception"
0x18002b5a1  xor     edx, edx; Val
0x18002b5a3  lea     rcx, [rsp+278h+Buffer]; void *
0x18002b5a8  mov     r8d, 200h; Size
0x18002b5ae  call    memset_0
0x18002b5b3  test    [rbx+4], bpl
0x18002b5b7  jz      short loc_18002B5DC
0x18002b5b9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002b5c0  mov     ebp, [rbx+0Ch]
0x18002b5c3  test    rax, rax
0x18002b5c6  jz      short loc_18002B612
0x18002b5c8  mov     r8d, 100h
0x18002b5ce  lea     rdx, [rsp+278h+Buffer]
0x18002b5d3  mov     ecx, ebp
0x18002b5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5da  jmp     short loc_18002B612
0x18002b5dc  mov     ebp, [rbx+8]
0x18002b5df  lea     rax, [rsp+278h+Buffer]
0x18002b5e4  mov     [rsp+278h+Arguments], r15; Arguments
0x18002b5e9  mov     r8d, ebp; dwMessageId
0x18002b5ec  mov     [rsp+278h+nSize], 100h; nSize
0x18002b5f4  mov     r9d, 400h; dwLanguageId
0x18002b5fa  xor     edx, edx; lpSource
0x18002b5fc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002b601  mov     ecx, 1200h; dwFlags
0x18002b606  call    cs:__imp_FormatMessageW
0x18002b60d  nop     dword ptr [rax+rax+00h]
0x18002b612  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002b616  lea     rsi, [r14+rsi*2]
0x18002b61a  mov     rax, [rbx+88h]
0x18002b621  mov     rdx, rsi; unsigned __int16 *
0x18002b624  mov     rcx, [rbx+80h]
0x18002b62b  test    r9, r9
0x18002b62e  jz      short loc_18002B652
0x18002b630  mov     [rsp+278h+Arguments], rax
0x18002b635  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002b63c  mov     eax, [rbx+40h]
0x18002b63f  mov     qword ptr [rsp+278h+nSize], rcx
0x18002b644  mov     rcx, r14; this
0x18002b647  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002b64b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b650  jmp     short loc_18002B669
0x18002b652  mov     r9, rcx; unsigned __int16 *
0x18002b655  mov     [rsp+278h+lpBuffer], rax
0x18002b65a  mov     rcx, r14; this
0x18002b65d  lea     r8, aHsP; "%hs!%p: "
0x18002b664  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b669  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002b670  mov     r14, rax
0x18002b673  test    r9, r9
0x18002b676  jz      short loc_18002B68D
0x18002b678  lea     r8, aCallerP; "(caller: %p) "
0x18002b67f  mov     rdx, rsi; unsigned __int16 *
0x18002b682  mov     rcx, rax; this
0x18002b685  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b68a  mov     r14, rax
0x18002b68d  call    cs:__imp_GetCurrentThreadId
0x18002b694  nop     dword ptr [rax+rax+00h]
0x18002b699  lea     rcx, [rsp+278h+Buffer]
0x18002b69e  mov     r9, rdi; unsigned __int16 *
0x18002b6a1  mov     [rsp+278h+var_240], rcx
0x18002b6a6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002b6ad  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002b6b1  mov     rdx, rsi; unsigned __int16 *
0x18002b6b4  mov     [rsp+278h+nSize], eax
0x18002b6b8  mov     rcx, r14; this
0x18002b6bb  mov     eax, [rbx+44h]
0x18002b6be  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002b6c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b6c7  cmp     [rbx+18h], r15
0x18002b6cb  jnz     short loc_18002B6DD
0x18002b6cd  cmp     [rbx+48h], r15
0x18002b6d1  jnz     short loc_18002B6DD
0x18002b6d3  cmp     [rbx+30h], r15
0x18002b6d7  jz      loc_18002B76D
0x18002b6dd  lea     r8, asc_18003D298; "    "
0x18002b6e4  mov     rdx, rsi; unsigned __int16 *
0x18002b6e7  mov     rcx, rax; this
0x18002b6ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b6ef  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002b6f3  test    r9, r9
0x18002b6f6  jz      short loc_18002B70A
0x18002b6f8  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002b6ff  mov     rdx, rsi; unsigned __int16 *
0x18002b702  mov     rcx, rax; this
0x18002b705  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b70a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002b70e  test    r9, r9
0x18002b711  jz      short loc_18002B725
0x18002b713  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002b71a  mov     rdx, rsi; unsigned __int16 *
0x18002b71d  mov     rcx, rax; this
0x18002b720  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b725  mov     rcx, [rbx+28h]
0x18002b729  mov     rdx, rsi; unsigned __int16 *
0x18002b72c  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002b730  test    rcx, rcx
0x18002b733  jz      short loc_18002B74B
0x18002b735  mov     [rsp+278h+lpBuffer], rcx
0x18002b73a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002b741  mov     rcx, rax; this
0x18002b744  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b749  jmp     short loc_18002B76D
0x18002b74b  mov     rcx, rax; this
0x18002b74e  test    r9, r9
0x18002b751  jz      short loc_18002B761
0x18002b753  lea     r8, aHs; "[%hs]\n"
0x18002b75a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b75f  jmp     short loc_18002B76D
0x18002b761  lea     r8, asc_18003D310; "\n"
0x18002b768  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002b76d  xor     eax, eax
0x18002b76f  mov     rcx, [rsp+278h+var_38]
0x18002b777  xor     rcx, rsp; StackCookie
0x18002b77a  call    __security_check_cookie
0x18002b77f  mov     rbx, [rsp+278h+arg_18]
0x18002b787  add     rsp, 250h
0x18002b78e  pop     r15
0x18002b790  pop     r14
0x18002b792  pop     rdi
0x18002b793  pop     rsi
0x18002b794  pop     rbp
0x18002b795  retn
```
