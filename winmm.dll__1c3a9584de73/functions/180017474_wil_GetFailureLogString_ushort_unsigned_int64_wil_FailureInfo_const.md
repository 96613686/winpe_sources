# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180017474`
- end: `0x18001772a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a524`
- `0x180019a60`

## callees

- `0x18000c990`
- `0x18000d470`
- `0x180017474`
- `0x180018210`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017627`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800175a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800175a6`

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
          v7 = (const char *)&byte_18001DA80;
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
0x180017474  mov     [rsp+arg_18], rbx
0x180017479  push    rbp
0x18001747a  push    rsi
0x18001747b  push    rdi
0x18001747c  push    r14
0x18001747e  push    r15
0x180017480  sub     rsp, 250h
0x180017487  mov     rax, cs:__security_cookie
0x18001748e  xor     rax, rsp
0x180017491  mov     [rsp+278h+var_38], rax
0x180017499  mov     rbx, r8
0x18001749c  mov     rsi, rdx
0x18001749f  mov     r14, rcx
0x1800174a2  xor     r15d, r15d
0x1800174a5  test    rdx, rdx
0x1800174a8  jz      loc_180017701
0x1800174ae  test    rcx, rcx
0x1800174b1  jz      loc_180017701
0x1800174b7  mov     [rcx], r15w
0x1800174bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800174c2  test    rax, rax
0x1800174c5  jz      short loc_1800174E8
0x1800174c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800174ce  jz      short loc_1800174E8
0x1800174d0  mov     r8, rdx
0x1800174d3  mov     rdx, rcx
0x1800174d6  mov     rcx, rbx
0x1800174d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174de  cmp     [r14], r15w
0x1800174e2  jnz     loc_180017701
0x1800174e8  mov     ecx, [rbx]
0x1800174ea  mov     bpl, 8
0x1800174ed  test    ecx, ecx
0x1800174ef  jz      short loc_18001753A
0x1800174f1  sub     ecx, 1
0x1800174f4  jz      short loc_180017522
0x1800174f6  sub     ecx, 1
0x1800174f9  jz      short loc_180017512
0x1800174fb  cmp     ecx, 1
0x1800174fe  jz      short loc_180017509
0x180017500  lea     rdi, byte_18001DA80
0x180017507  jmp     short loc_180017541
0x180017509  lea     rdi, aFailfast; "FailFast"
0x180017510  jmp     short loc_180017541
0x180017512  lea     rax, aLoghr; "LogHr"
0x180017519  lea     rdi, aLognt; "LogNt"
0x180017520  jmp     short loc_180017530
0x180017522  lea     rax, aReturnhr; "ReturnHr"
0x180017529  lea     rdi, aReturnnt; "ReturnNt"
0x180017530  test    [rbx+4], bpl
0x180017534  cmovz   rdi, rax
0x180017538  jmp     short loc_180017541
0x18001753a  lea     rdi, aException; "Exception"
0x180017541  xor     edx, edx; Val
0x180017543  mov     r8d, 200h; Size
0x180017549  lea     rcx, [rsp+278h+Buffer]; void *
0x18001754e  call    memset_0
0x180017553  test    [rbx+4], bpl
0x180017557  jz      short loc_18001757C
0x180017559  mov     ebp, [rbx+0Ch]
0x18001755c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180017563  test    rax, rax
0x180017566  jz      short loc_1800175AC
0x180017568  mov     r8d, 100h
0x18001756e  lea     rdx, [rsp+278h+Buffer]
0x180017573  mov     ecx, ebp
0x180017575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001757a  jmp     short loc_1800175AC
0x18001757c  mov     ebp, [rbx+8]
0x18001757f  mov     [rsp+278h+Arguments], r15; Arguments
0x180017584  mov     [rsp+278h+nSize], 100h; nSize
0x18001758c  lea     rax, [rsp+278h+Buffer]
0x180017591  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180017596  mov     r9d, 400h; dwLanguageId
0x18001759c  mov     r8d, ebp; dwMessageId
0x18001759f  xor     edx, edx; lpSource
0x1800175a1  mov     ecx, 1200h; dwFlags
0x1800175a6  call    cs:__imp_FormatMessageW
0x1800175ac  lea     rsi, [r14+rsi*2]
0x1800175b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800175b4  mov     rax, [rbx+88h]
0x1800175bb  mov     rcx, [rbx+80h]
0x1800175c2  mov     rdx, rsi; unsigned __int16 *
0x1800175c5  test    r9, r9
0x1800175c8  jz      short loc_1800175EC
0x1800175ca  mov     [rsp+278h+Arguments], rax
0x1800175cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800175d4  mov     eax, [rbx+40h]
0x1800175d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800175db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800175e2  mov     rcx, r14; this
0x1800175e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800175ea  jmp     short loc_180017603
0x1800175ec  mov     [rsp+278h+lpBuffer], rax
0x1800175f1  mov     r9, rcx; unsigned __int16 *
0x1800175f4  lea     r8, aHsP; "%hs!%p: "
0x1800175fb  mov     rcx, r14; this
0x1800175fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180017603  mov     r14, rax
0x180017606  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001760d  test    r9, r9
0x180017610  jz      short loc_180017627
0x180017612  lea     r8, aCallerP; "(caller: %p) "
0x180017619  mov     rdx, rsi; unsigned __int16 *
0x18001761c  mov     rcx, rax; this
0x18001761f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180017624  mov     r14, rax
0x180017627  call    cs:__imp_GetCurrentThreadId
0x18001762d  lea     rcx, [rsp+278h+Buffer]
0x180017632  mov     [rsp+278h+var_240], rcx
0x180017637  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001763b  mov     [rsp+278h+nSize], eax
0x18001763f  mov     eax, [rbx+44h]
0x180017642  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180017646  mov     r9, rdi; unsigned __int16 *
0x180017649  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180017650  mov     rdx, rsi; unsigned __int16 *
0x180017653  mov     rcx, r14; this
0x180017656  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001765b  cmp     [rbx+18h], r15
0x18001765f  jnz     short loc_180017671
0x180017661  cmp     [rbx+48h], r15
0x180017665  jnz     short loc_180017671
0x180017667  cmp     [rbx+30h], r15
0x18001766b  jz      loc_180017701
0x180017671  lea     r8, asc_18001DB88; "    "
0x180017678  mov     rdx, rsi; unsigned __int16 *
0x18001767b  mov     rcx, rax; this
0x18001767e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180017683  mov     r9, [rbx+18h]; unsigned __int16 *
0x180017687  test    r9, r9
0x18001768a  jz      short loc_18001769E
0x18001768c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180017693  mov     rdx, rsi; unsigned __int16 *
0x180017696  mov     rcx, rax; this
0x180017699  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001769e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800176a2  test    r9, r9
0x1800176a5  jz      short loc_1800176B9
0x1800176a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800176ae  mov     rdx, rsi; unsigned __int16 *
0x1800176b1  mov     rcx, rax; this
0x1800176b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800176b9  mov     rcx, [rbx+28h]
0x1800176bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800176c1  mov     rdx, rsi; unsigned __int16 *
0x1800176c4  test    rcx, rcx
0x1800176c7  jz      short loc_1800176DF
0x1800176c9  mov     [rsp+278h+lpBuffer], rcx
0x1800176ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800176d5  mov     rcx, rax; this
0x1800176d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800176dd  jmp     short loc_180017701
0x1800176df  mov     rcx, rax; this
0x1800176e2  test    r9, r9
0x1800176e5  jz      short loc_1800176F5
0x1800176e7  lea     r8, aHs; "[%hs]\n"
0x1800176ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800176f3  jmp     short loc_180017701
0x1800176f5  lea     r8, asc_18001DC00; "\n"
0x1800176fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180017701  xor     eax, eax
0x180017703  mov     rcx, [rsp+278h+var_38]
0x18001770b  xor     rcx, rsp; StackCookie
0x18001770e  call    __security_check_cookie
0x180017713  mov     rbx, [rsp+278h+arg_18]
0x18001771b  add     rsp, 250h
0x180017722  pop     r15
0x180017724  pop     r14
0x180017726  pop     rdi
0x180017727  pop     rsi
0x180017728  pop     rbp
0x180017729  retn
```
