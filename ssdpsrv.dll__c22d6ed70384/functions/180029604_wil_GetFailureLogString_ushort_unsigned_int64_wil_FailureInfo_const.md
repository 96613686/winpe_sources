# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180029604`
- end: `0x1800298ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180029ee8`

## callees

- `0x180026a30`
- `0x18002735c`
- `0x180029604`
- `0x18002a1e4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800297b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800297b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180029736`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180029736`

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
0x180029604  mov     [rsp+arg_18], rbx
0x180029609  push    rbp
0x18002960a  push    rsi
0x18002960b  push    rdi
0x18002960c  push    r14
0x18002960e  push    r15
0x180029610  sub     rsp, 250h
0x180029617  mov     rax, cs:__security_cookie
0x18002961e  xor     rax, rsp
0x180029621  mov     [rsp+278h+var_38], rax
0x180029629  xor     r15d, r15d
0x18002962c  mov     rbx, r8
0x18002962f  mov     rsi, rdx
0x180029632  mov     r14, rcx
0x180029635  test    rdx, rdx
0x180029638  jz      loc_180029891
0x18002963e  test    rcx, rcx
0x180029641  jz      loc_180029891
0x180029647  mov     rax, cs:g_pfnResultLoggingCallback
0x18002964e  mov     [rcx], r15w
0x180029652  test    rax, rax
0x180029655  jz      short loc_180029678
0x180029657  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002965e  jz      short loc_180029678
0x180029660  mov     r8, rdx
0x180029663  mov     rdx, rcx
0x180029666  mov     rcx, rbx
0x180029669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002966e  cmp     [r14], r15w
0x180029672  jnz     loc_180029891
0x180029678  mov     ecx, [rbx]
0x18002967a  mov     bpl, 8
0x18002967d  test    ecx, ecx
0x18002967f  jz      short loc_1800296CA
0x180029681  sub     ecx, 1
0x180029684  jz      short loc_1800296B2
0x180029686  sub     ecx, 1
0x180029689  jz      short loc_1800296A2
0x18002968b  cmp     ecx, 1
0x18002968e  jz      short loc_180029699
0x180029690  lea     rdi, Format
0x180029697  jmp     short loc_1800296D1
0x180029699  lea     rdi, aFailfast; "FailFast"
0x1800296a0  jmp     short loc_1800296D1
0x1800296a2  lea     rax, aLoghr; "LogHr"
0x1800296a9  lea     rdi, aLognt; "LogNt"
0x1800296b0  jmp     short loc_1800296C0
0x1800296b2  lea     rax, aReturnhr; "ReturnHr"
0x1800296b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800296c0  test    [rbx+4], bpl
0x1800296c4  cmovz   rdi, rax
0x1800296c8  jmp     short loc_1800296D1
0x1800296ca  lea     rdi, aException; "Exception"
0x1800296d1  xor     edx, edx; Val
0x1800296d3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800296d8  mov     r8d, 200h; Size
0x1800296de  call    memset_0
0x1800296e3  test    [rbx+4], bpl
0x1800296e7  jz      short loc_18002970C
0x1800296e9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800296f0  mov     ebp, [rbx+0Ch]
0x1800296f3  test    rax, rax
0x1800296f6  jz      short loc_18002973C
0x1800296f8  mov     r8d, 100h
0x1800296fe  lea     rdx, [rsp+278h+Buffer]
0x180029703  mov     ecx, ebp
0x180029705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002970a  jmp     short loc_18002973C
0x18002970c  mov     ebp, [rbx+8]
0x18002970f  lea     rax, [rsp+278h+Buffer]
0x180029714  mov     [rsp+278h+Arguments], r15; Arguments
0x180029719  mov     r8d, ebp; dwMessageId
0x18002971c  mov     [rsp+278h+nSize], 100h; nSize
0x180029724  mov     r9d, 400h; dwLanguageId
0x18002972a  xor     edx, edx; lpSource
0x18002972c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180029731  mov     ecx, 1200h; dwFlags
0x180029736  call    cs:__imp_FormatMessageW
0x18002973c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180029740  lea     rsi, [r14+rsi*2]
0x180029744  mov     rax, [rbx+88h]
0x18002974b  mov     rdx, rsi; unsigned __int16 *
0x18002974e  mov     rcx, [rbx+80h]
0x180029755  test    r9, r9
0x180029758  jz      short loc_18002977C
0x18002975a  mov     [rsp+278h+Arguments], rax
0x18002975f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180029766  mov     eax, [rbx+40h]
0x180029769  mov     qword ptr [rsp+278h+nSize], rcx
0x18002976e  mov     rcx, r14; this
0x180029771  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180029775  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002977a  jmp     short loc_180029793
0x18002977c  mov     r9, rcx; unsigned __int16 *
0x18002977f  mov     [rsp+278h+lpBuffer], rax
0x180029784  mov     rcx, r14; this
0x180029787  lea     r8, aHsP; "%hs!%p: "
0x18002978e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180029793  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002979a  mov     r14, rax
0x18002979d  test    r9, r9
0x1800297a0  jz      short loc_1800297B7
0x1800297a2  lea     r8, aCallerP; "(caller: %p) "
0x1800297a9  mov     rdx, rsi; unsigned __int16 *
0x1800297ac  mov     rcx, rax; this
0x1800297af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800297b4  mov     r14, rax
0x1800297b7  call    cs:__imp_GetCurrentThreadId
0x1800297bd  lea     rcx, [rsp+278h+Buffer]
0x1800297c2  mov     r9, rdi; unsigned __int16 *
0x1800297c5  mov     [rsp+278h+var_240], rcx
0x1800297ca  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800297d1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800297d5  mov     rdx, rsi; unsigned __int16 *
0x1800297d8  mov     [rsp+278h+nSize], eax
0x1800297dc  mov     rcx, r14; this
0x1800297df  mov     eax, [rbx+44h]
0x1800297e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800297e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800297eb  cmp     [rbx+18h], r15
0x1800297ef  jnz     short loc_180029801
0x1800297f1  cmp     [rbx+48h], r15
0x1800297f5  jnz     short loc_180029801
0x1800297f7  cmp     [rbx+30h], r15
0x1800297fb  jz      loc_180029891
0x180029801  lea     r8, asc_18003A288; "    "
0x180029808  mov     rdx, rsi; unsigned __int16 *
0x18002980b  mov     rcx, rax; this
0x18002980e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180029813  mov     r9, [rbx+18h]; unsigned __int16 *
0x180029817  test    r9, r9
0x18002981a  jz      short loc_18002982E
0x18002981c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180029823  mov     rdx, rsi; unsigned __int16 *
0x180029826  mov     rcx, rax; this
0x180029829  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002982e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180029832  test    r9, r9
0x180029835  jz      short loc_180029849
0x180029837  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002983e  mov     rdx, rsi; unsigned __int16 *
0x180029841  mov     rcx, rax; this
0x180029844  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180029849  mov     rcx, [rbx+28h]
0x18002984d  mov     rdx, rsi; unsigned __int16 *
0x180029850  mov     r9, [rbx+30h]; unsigned __int16 *
0x180029854  test    rcx, rcx
0x180029857  jz      short loc_18002986F
0x180029859  mov     [rsp+278h+lpBuffer], rcx
0x18002985e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180029865  mov     rcx, rax; this
0x180029868  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002986d  jmp     short loc_180029891
0x18002986f  mov     rcx, rax; this
0x180029872  test    r9, r9
0x180029875  jz      short loc_180029885
0x180029877  lea     r8, aHs; "[%hs]\n"
0x18002987e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180029883  jmp     short loc_180029891
0x180029885  lea     r8, asc_18003A300; "\n"
0x18002988c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180029891  xor     eax, eax
0x180029893  mov     rcx, [rsp+278h+var_38]
0x18002989b  xor     rcx, rsp; StackCookie
0x18002989e  call    __security_check_cookie
0x1800298a3  mov     rbx, [rsp+278h+arg_18]
0x1800298ab  add     rsp, 250h
0x1800298b2  pop     r15
0x1800298b4  pop     r14
0x1800298b6  pop     rdi
0x1800298b7  pop     rsi
0x1800298b8  pop     rbp
0x1800298b9  retn
```
