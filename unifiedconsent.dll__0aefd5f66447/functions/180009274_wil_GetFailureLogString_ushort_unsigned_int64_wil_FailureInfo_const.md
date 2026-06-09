# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009274`
- end: `0x18000952a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800044e4`
- `0x180004764`
- `0x180004a50`
- `0x180004cfc`
- `0x18000ed50`
- `0x180070a1a`
- `0x180070b4e`
- `0x180070cb7`
- `0x180070f34`

## callees

- `0x180002810`
- `0x180003384`
- `0x180009274`
- `0x180009fb0`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009427`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009427`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800093a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800093a6`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&byte_180082848;
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
0x180009274  mov     [rsp+arg_18], rbx
0x180009279  push    rbp
0x18000927a  push    rsi
0x18000927b  push    rdi
0x18000927c  push    r14
0x18000927e  push    r15
0x180009280  sub     rsp, 250h
0x180009287  mov     rax, cs:__security_cookie
0x18000928e  xor     rax, rsp
0x180009291  mov     [rsp+278h+var_38], rax
0x180009299  mov     rbx, r8
0x18000929c  mov     rsi, rdx
0x18000929f  mov     r14, rcx
0x1800092a2  xor     r15d, r15d
0x1800092a5  test    rdx, rdx
0x1800092a8  jz      loc_180009501
0x1800092ae  test    rcx, rcx
0x1800092b1  jz      loc_180009501
0x1800092b7  mov     [rcx], r15w
0x1800092bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800092c2  test    rax, rax
0x1800092c5  jz      short loc_1800092E8
0x1800092c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800092ce  jz      short loc_1800092E8
0x1800092d0  mov     r8, rdx
0x1800092d3  mov     rdx, rcx
0x1800092d6  mov     rcx, rbx
0x1800092d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092de  cmp     [r14], r15w
0x1800092e2  jnz     loc_180009501
0x1800092e8  mov     ecx, [rbx]
0x1800092ea  mov     bpl, 8
0x1800092ed  test    ecx, ecx
0x1800092ef  jz      short loc_18000933A
0x1800092f1  sub     ecx, 1
0x1800092f4  jz      short loc_180009322
0x1800092f6  sub     ecx, 1
0x1800092f9  jz      short loc_180009312
0x1800092fb  cmp     ecx, 1
0x1800092fe  jz      short loc_180009309
0x180009300  lea     rdi, byte_180082848
0x180009307  jmp     short loc_180009341
0x180009309  lea     rdi, aFailfast; "FailFast"
0x180009310  jmp     short loc_180009341
0x180009312  lea     rax, aLoghr; "LogHr"
0x180009319  lea     rdi, aLognt; "LogNt"
0x180009320  jmp     short loc_180009330
0x180009322  lea     rax, aReturnhr; "ReturnHr"
0x180009329  lea     rdi, aReturnnt; "ReturnNt"
0x180009330  test    [rbx+4], bpl
0x180009334  cmovz   rdi, rax
0x180009338  jmp     short loc_180009341
0x18000933a  lea     rdi, aException; "Exception"
0x180009341  xor     edx, edx; Val
0x180009343  mov     r8d, 200h; Size
0x180009349  lea     rcx, [rsp+278h+Buffer]; void *
0x18000934e  call    memset_0
0x180009353  test    [rbx+4], bpl
0x180009357  jz      short loc_18000937C
0x180009359  mov     ebp, [rbx+0Ch]
0x18000935c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009363  test    rax, rax
0x180009366  jz      short loc_1800093AC
0x180009368  mov     r8d, 100h
0x18000936e  lea     rdx, [rsp+278h+Buffer]
0x180009373  mov     ecx, ebp
0x180009375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000937a  jmp     short loc_1800093AC
0x18000937c  mov     ebp, [rbx+8]
0x18000937f  mov     [rsp+278h+Arguments], r15; Arguments
0x180009384  mov     [rsp+278h+nSize], 100h; nSize
0x18000938c  lea     rax, [rsp+278h+Buffer]
0x180009391  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009396  mov     r9d, 400h; dwLanguageId
0x18000939c  mov     r8d, ebp; dwMessageId
0x18000939f  xor     edx, edx; lpSource
0x1800093a1  mov     ecx, 1200h; dwFlags
0x1800093a6  call    cs:__imp_FormatMessageW
0x1800093ac  lea     rsi, [r14+rsi*2]
0x1800093b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800093b4  mov     rax, [rbx+88h]
0x1800093bb  mov     rcx, [rbx+80h]
0x1800093c2  mov     rdx, rsi; unsigned __int16 *
0x1800093c5  test    r9, r9
0x1800093c8  jz      short loc_1800093EC
0x1800093ca  mov     [rsp+278h+Arguments], rax
0x1800093cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800093d4  mov     eax, [rbx+40h]
0x1800093d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800093db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800093e2  mov     rcx, r14; this
0x1800093e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800093ea  jmp     short loc_180009403
0x1800093ec  mov     [rsp+278h+lpBuffer], rax
0x1800093f1  mov     r9, rcx; unsigned __int16 *
0x1800093f4  lea     r8, aHsP; "%hs!%p: "
0x1800093fb  mov     rcx, r14; this
0x1800093fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009403  mov     r14, rax
0x180009406  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000940d  test    r9, r9
0x180009410  jz      short loc_180009427
0x180009412  lea     r8, aCallerP; "(caller: %p) "
0x180009419  mov     rdx, rsi; unsigned __int16 *
0x18000941c  mov     rcx, rax; this
0x18000941f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009424  mov     r14, rax
0x180009427  call    cs:__imp_GetCurrentThreadId
0x18000942d  lea     rcx, [rsp+278h+Buffer]
0x180009432  mov     [rsp+278h+var_240], rcx
0x180009437  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000943b  mov     [rsp+278h+nSize], eax
0x18000943f  mov     eax, [rbx+44h]
0x180009442  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009446  mov     r9, rdi; unsigned __int16 *
0x180009449  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009450  mov     rdx, rsi; unsigned __int16 *
0x180009453  mov     rcx, r14; this
0x180009456  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000945b  cmp     [rbx+18h], r15
0x18000945f  jnz     short loc_180009471
0x180009461  cmp     [rbx+48h], r15
0x180009465  jnz     short loc_180009471
0x180009467  cmp     [rbx+30h], r15
0x18000946b  jz      loc_180009501
0x180009471  lea     r8, asc_180082960; "    "
0x180009478  mov     rdx, rsi; unsigned __int16 *
0x18000947b  mov     rcx, rax; this
0x18000947e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009483  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009487  test    r9, r9
0x18000948a  jz      short loc_18000949E
0x18000948c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009493  mov     rdx, rsi; unsigned __int16 *
0x180009496  mov     rcx, rax; this
0x180009499  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000949e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800094a2  test    r9, r9
0x1800094a5  jz      short loc_1800094B9
0x1800094a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800094ae  mov     rdx, rsi; unsigned __int16 *
0x1800094b1  mov     rcx, rax; this
0x1800094b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800094b9  mov     rcx, [rbx+28h]
0x1800094bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800094c1  mov     rdx, rsi; unsigned __int16 *
0x1800094c4  test    rcx, rcx
0x1800094c7  jz      short loc_1800094DF
0x1800094c9  mov     [rsp+278h+lpBuffer], rcx
0x1800094ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800094d5  mov     rcx, rax; this
0x1800094d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800094dd  jmp     short loc_180009501
0x1800094df  mov     rcx, rax; this
0x1800094e2  test    r9, r9
0x1800094e5  jz      short loc_1800094F5
0x1800094e7  lea     r8, aHs; "[%hs]\n"
0x1800094ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800094f3  jmp     short loc_180009501
0x1800094f5  lea     r8, asc_1800829D8; "\n"
0x1800094fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009501  xor     eax, eax
0x180009503  mov     rcx, [rsp+278h+var_38]
0x18000950b  xor     rcx, rsp; StackCookie
0x18000950e  call    __security_check_cookie
0x180009513  mov     rbx, [rsp+278h+arg_18]
0x18000951b  add     rsp, 250h
0x180009522  pop     r15
0x180009524  pop     r14
0x180009526  pop     rdi
0x180009527  pop     rsi
0x180009528  pop     rbp
0x180009529  retn
```
