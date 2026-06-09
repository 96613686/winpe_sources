# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800045f4`
- end: `0x1800048aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800035d4`
- `0x1800052f0`
- `0x180006f60`

## callees

- `0x1800024e0`
- `0x1800030ae`
- `0x1800045f4`
- `0x1800055f0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004726`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004726`

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
          v7 = (const char *)&byte_1800097ED;
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
0x1800045f4  mov     [rsp+arg_18], rbx
0x1800045f9  push    rbp
0x1800045fa  push    rsi
0x1800045fb  push    rdi
0x1800045fc  push    r14
0x1800045fe  push    r15
0x180004600  sub     rsp, 250h
0x180004607  mov     rax, cs:__security_cookie
0x18000460e  xor     rax, rsp
0x180004611  mov     [rsp+278h+var_38], rax
0x180004619  mov     rbx, r8
0x18000461c  mov     rsi, rdx
0x18000461f  mov     r14, rcx
0x180004622  xor     r15d, r15d
0x180004625  test    rdx, rdx
0x180004628  jz      loc_180004881
0x18000462e  test    rcx, rcx
0x180004631  jz      loc_180004881
0x180004637  mov     [rcx], r15w
0x18000463b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004642  test    rax, rax
0x180004645  jz      short loc_180004668
0x180004647  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000464e  jz      short loc_180004668
0x180004650  mov     r8, rdx
0x180004653  mov     rdx, rcx
0x180004656  mov     rcx, rbx
0x180004659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000465e  cmp     [r14], r15w
0x180004662  jnz     loc_180004881
0x180004668  mov     ecx, [rbx]
0x18000466a  mov     bpl, 8
0x18000466d  test    ecx, ecx
0x18000466f  jz      short loc_1800046BA
0x180004671  sub     ecx, 1
0x180004674  jz      short loc_1800046A2
0x180004676  sub     ecx, 1
0x180004679  jz      short loc_180004692
0x18000467b  cmp     ecx, 1
0x18000467e  jz      short loc_180004689
0x180004680  lea     rdi, byte_1800097ED
0x180004687  jmp     short loc_1800046C1
0x180004689  lea     rdi, aFailfast; "FailFast"
0x180004690  jmp     short loc_1800046C1
0x180004692  lea     rax, aLoghr; "LogHr"
0x180004699  lea     rdi, aLognt; "LogNt"
0x1800046a0  jmp     short loc_1800046B0
0x1800046a2  lea     rax, aReturnhr; "ReturnHr"
0x1800046a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800046b0  test    [rbx+4], bpl
0x1800046b4  cmovz   rdi, rax
0x1800046b8  jmp     short loc_1800046C1
0x1800046ba  lea     rdi, aException; "Exception"
0x1800046c1  xor     edx, edx; Val
0x1800046c3  mov     r8d, 200h; Size
0x1800046c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800046ce  call    memset_0
0x1800046d3  test    [rbx+4], bpl
0x1800046d7  jz      short loc_1800046FC
0x1800046d9  mov     ebp, [rbx+0Ch]
0x1800046dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800046e3  test    rax, rax
0x1800046e6  jz      short loc_18000472C
0x1800046e8  mov     r8d, 100h
0x1800046ee  lea     rdx, [rsp+278h+Buffer]
0x1800046f3  mov     ecx, ebp
0x1800046f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fa  jmp     short loc_18000472C
0x1800046fc  mov     ebp, [rbx+8]
0x1800046ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180004704  mov     [rsp+278h+nSize], 100h; nSize
0x18000470c  lea     rax, [rsp+278h+Buffer]
0x180004711  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004716  mov     r9d, 400h; dwLanguageId
0x18000471c  mov     r8d, ebp; dwMessageId
0x18000471f  xor     edx, edx; lpSource
0x180004721  mov     ecx, 1200h; dwFlags
0x180004726  call    cs:__imp_FormatMessageW
0x18000472c  lea     rsi, [r14+rsi*2]
0x180004730  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004734  mov     rax, [rbx+88h]
0x18000473b  mov     rcx, [rbx+80h]
0x180004742  mov     rdx, rsi; unsigned __int16 *
0x180004745  test    r9, r9
0x180004748  jz      short loc_18000476C
0x18000474a  mov     [rsp+278h+Arguments], rax
0x18000474f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004754  mov     eax, [rbx+40h]
0x180004757  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000475b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004762  mov     rcx, r14; this
0x180004765  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000476a  jmp     short loc_180004783
0x18000476c  mov     [rsp+278h+lpBuffer], rax
0x180004771  mov     r9, rcx; unsigned __int16 *
0x180004774  lea     r8, aHsP; "%hs!%p: "
0x18000477b  mov     rcx, r14; this
0x18000477e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004783  mov     r14, rax
0x180004786  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000478d  test    r9, r9
0x180004790  jz      short loc_1800047A7
0x180004792  lea     r8, aCallerP; "(caller: %p) "
0x180004799  mov     rdx, rsi; unsigned __int16 *
0x18000479c  mov     rcx, rax; this
0x18000479f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047a4  mov     r14, rax
0x1800047a7  call    cs:__imp_GetCurrentThreadId
0x1800047ad  lea     rcx, [rsp+278h+Buffer]
0x1800047b2  mov     [rsp+278h+var_240], rcx
0x1800047b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800047bb  mov     [rsp+278h+nSize], eax
0x1800047bf  mov     eax, [rbx+44h]
0x1800047c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800047c6  mov     r9, rdi; unsigned __int16 *
0x1800047c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800047d0  mov     rdx, rsi; unsigned __int16 *
0x1800047d3  mov     rcx, r14; this
0x1800047d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047db  cmp     [rbx+18h], r15
0x1800047df  jnz     short loc_1800047F1
0x1800047e1  cmp     [rbx+48h], r15
0x1800047e5  jnz     short loc_1800047F1
0x1800047e7  cmp     [rbx+30h], r15
0x1800047eb  jz      loc_180004881
0x1800047f1  lea     r8, asc_1800098F0; "    "
0x1800047f8  mov     rdx, rsi; unsigned __int16 *
0x1800047fb  mov     rcx, rax; this
0x1800047fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004803  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004807  test    r9, r9
0x18000480a  jz      short loc_18000481E
0x18000480c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004813  mov     rdx, rsi; unsigned __int16 *
0x180004816  mov     rcx, rax; this
0x180004819  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000481e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004822  test    r9, r9
0x180004825  jz      short loc_180004839
0x180004827  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000482e  mov     rdx, rsi; unsigned __int16 *
0x180004831  mov     rcx, rax; this
0x180004834  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004839  mov     rcx, [rbx+28h]
0x18000483d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004841  mov     rdx, rsi; unsigned __int16 *
0x180004844  test    rcx, rcx
0x180004847  jz      short loc_18000485F
0x180004849  mov     [rsp+278h+lpBuffer], rcx
0x18000484e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004855  mov     rcx, rax; this
0x180004858  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000485d  jmp     short loc_180004881
0x18000485f  mov     rcx, rax; this
0x180004862  test    r9, r9
0x180004865  jz      short loc_180004875
0x180004867  lea     r8, aHs; "[%hs]\n"
0x18000486e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004873  jmp     short loc_180004881
0x180004875  lea     r8, asc_180009968; "\n"
0x18000487c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004881  xor     eax, eax
0x180004883  mov     rcx, [rsp+278h+var_38]
0x18000488b  xor     rcx, rsp; StackCookie
0x18000488e  call    __security_check_cookie
0x180004893  mov     rbx, [rsp+278h+arg_18]
0x18000489b  add     rsp, 250h
0x1800048a2  pop     r15
0x1800048a4  pop     r14
0x1800048a6  pop     rdi
0x1800048a7  pop     rsi
0x1800048a8  pop     rbp
0x1800048a9  retn
```
