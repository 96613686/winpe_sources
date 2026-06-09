# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180035704`
- end: `0x1800359c7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180035cf8`

## callees

- `0x180035704`
- `0x180036008`
- `0x18004022e`
- `0x180040260`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800358bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800358bd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180035836`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180035836`

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
          v8 = (const char *)&qword_180044758;
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
0x180035704  mov     [rsp+arg_18], rbx
0x180035709  push    rbp
0x18003570a  push    rsi
0x18003570b  push    rdi
0x18003570c  push    r14
0x18003570e  push    r15
0x180035710  sub     rsp, 250h
0x180035717  mov     rax, cs:__security_cookie
0x18003571e  xor     rax, rsp
0x180035721  mov     [rsp+278h+var_38], rax
0x180035729  xor     r15d, r15d
0x18003572c  mov     rbx, r8
0x18003572f  mov     rsi, rdx
0x180035732  mov     r14, rcx
0x180035735  test    rdx, rdx
0x180035738  jz      loc_18003599D
0x18003573e  test    rcx, rcx
0x180035741  jz      loc_18003599D
0x180035747  mov     rax, cs:g_pfnResultLoggingCallback
0x18003574e  mov     [rcx], r15w
0x180035752  test    rax, rax
0x180035755  jz      short loc_180035778
0x180035757  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003575e  jz      short loc_180035778
0x180035760  mov     r8, rdx
0x180035763  mov     rdx, rcx
0x180035766  mov     rcx, rbx
0x180035769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003576e  cmp     [r14], r15w
0x180035772  jnz     loc_18003599D
0x180035778  mov     ecx, [rbx]
0x18003577a  mov     bpl, 8
0x18003577d  test    ecx, ecx
0x18003577f  jz      short loc_1800357CA
0x180035781  sub     ecx, 1
0x180035784  jz      short loc_1800357B2
0x180035786  sub     ecx, 1
0x180035789  jz      short loc_1800357A2
0x18003578b  cmp     ecx, 1
0x18003578e  jz      short loc_180035799
0x180035790  lea     rdi, qword_180044758
0x180035797  jmp     short loc_1800357D1
0x180035799  lea     rdi, aFailfast; "FailFast"
0x1800357a0  jmp     short loc_1800357D1
0x1800357a2  lea     rax, aLoghr; "LogHr"
0x1800357a9  lea     rdi, aLognt; "LogNt"
0x1800357b0  jmp     short loc_1800357C0
0x1800357b2  lea     rax, aReturnhr; "ReturnHr"
0x1800357b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800357c0  test    [rbx+4], bpl
0x1800357c4  cmovz   rdi, rax
0x1800357c8  jmp     short loc_1800357D1
0x1800357ca  lea     rdi, aException; "Exception"
0x1800357d1  xor     edx, edx; Val
0x1800357d3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800357d8  mov     r8d, 200h; Size
0x1800357de  call    memset_0
0x1800357e3  test    [rbx+4], bpl
0x1800357e7  jz      short loc_18003580C
0x1800357e9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800357f0  mov     ebp, [rbx+0Ch]
0x1800357f3  test    rax, rax
0x1800357f6  jz      short loc_180035842
0x1800357f8  mov     r8d, 100h
0x1800357fe  lea     rdx, [rsp+278h+Buffer]
0x180035803  mov     ecx, ebp
0x180035805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003580a  jmp     short loc_180035842
0x18003580c  mov     ebp, [rbx+8]
0x18003580f  lea     rax, [rsp+278h+Buffer]
0x180035814  mov     [rsp+278h+Arguments], r15; Arguments
0x180035819  mov     r8d, ebp; dwMessageId
0x18003581c  mov     [rsp+278h+nSize], 100h; nSize
0x180035824  mov     r9d, 400h; dwLanguageId
0x18003582a  xor     edx, edx; lpSource
0x18003582c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180035831  mov     ecx, 1200h; dwFlags
0x180035836  call    cs:__imp_FormatMessageW
0x18003583d  nop     dword ptr [rax+rax+00h]
0x180035842  mov     r9, [rbx+38h]; unsigned __int16 *
0x180035846  lea     rsi, [r14+rsi*2]
0x18003584a  mov     rax, [rbx+88h]
0x180035851  mov     rdx, rsi; unsigned __int16 *
0x180035854  mov     rcx, [rbx+80h]
0x18003585b  test    r9, r9
0x18003585e  jz      short loc_180035882
0x180035860  mov     [rsp+278h+Arguments], rax
0x180035865  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003586c  mov     eax, [rbx+40h]
0x18003586f  mov     qword ptr [rsp+278h+nSize], rcx
0x180035874  mov     rcx, r14; this
0x180035877  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003587b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035880  jmp     short loc_180035899
0x180035882  mov     r9, rcx; unsigned __int16 *
0x180035885  mov     [rsp+278h+lpBuffer], rax
0x18003588a  mov     rcx, r14; this
0x18003588d  lea     r8, aHsP; "%hs!%p: "
0x180035894  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035899  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800358a0  mov     r14, rax
0x1800358a3  test    r9, r9
0x1800358a6  jz      short loc_1800358BD
0x1800358a8  lea     r8, aCallerP; "(caller: %p) "
0x1800358af  mov     rdx, rsi; unsigned __int16 *
0x1800358b2  mov     rcx, rax; this
0x1800358b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800358ba  mov     r14, rax
0x1800358bd  call    cs:__imp_GetCurrentThreadId
0x1800358c4  nop     dword ptr [rax+rax+00h]
0x1800358c9  lea     rcx, [rsp+278h+Buffer]
0x1800358ce  mov     r9, rdi; unsigned __int16 *
0x1800358d1  mov     [rsp+278h+var_240], rcx
0x1800358d6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800358dd  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800358e1  mov     rdx, rsi; unsigned __int16 *
0x1800358e4  mov     [rsp+278h+nSize], eax
0x1800358e8  mov     rcx, r14; this
0x1800358eb  mov     eax, [rbx+44h]
0x1800358ee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800358f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800358f7  cmp     [rbx+18h], r15
0x1800358fb  jnz     short loc_18003590D
0x1800358fd  cmp     [rbx+48h], r15
0x180035901  jnz     short loc_18003590D
0x180035903  cmp     [rbx+30h], r15
0x180035907  jz      loc_18003599D
0x18003590d  lea     r8, asc_180044848; "    "
0x180035914  mov     rdx, rsi; unsigned __int16 *
0x180035917  mov     rcx, rax; this
0x18003591a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003591f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180035923  test    r9, r9
0x180035926  jz      short loc_18003593A
0x180035928  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003592f  mov     rdx, rsi; unsigned __int16 *
0x180035932  mov     rcx, rax; this
0x180035935  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003593a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003593e  test    r9, r9
0x180035941  jz      short loc_180035955
0x180035943  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003594a  mov     rdx, rsi; unsigned __int16 *
0x18003594d  mov     rcx, rax; this
0x180035950  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035955  mov     rcx, [rbx+28h]
0x180035959  mov     rdx, rsi; unsigned __int16 *
0x18003595c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180035960  test    rcx, rcx
0x180035963  jz      short loc_18003597B
0x180035965  mov     [rsp+278h+lpBuffer], rcx
0x18003596a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180035971  mov     rcx, rax; this
0x180035974  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035979  jmp     short loc_18003599D
0x18003597b  mov     rcx, rax; this
0x18003597e  test    r9, r9
0x180035981  jz      short loc_180035991
0x180035983  lea     r8, aHs; "[%hs]\n"
0x18003598a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003598f  jmp     short loc_18003599D
0x180035991  lea     r8, asc_1800448C0; "\n"
0x180035998  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003599d  xor     eax, eax
0x18003599f  mov     rcx, [rsp+278h+var_38]
0x1800359a7  xor     rcx, rsp; StackCookie
0x1800359aa  call    __security_check_cookie
0x1800359af  mov     rbx, [rsp+278h+arg_18]
0x1800359b7  add     rsp, 250h
0x1800359be  pop     r15
0x1800359c0  pop     r14
0x1800359c2  pop     rdi
0x1800359c3  pop     rsi
0x1800359c4  pop     rbp
0x1800359c5  retn
```
