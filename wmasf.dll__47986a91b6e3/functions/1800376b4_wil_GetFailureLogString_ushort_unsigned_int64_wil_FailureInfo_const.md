# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800376b4`
- end: `0x18003796a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180038ee4`

## callees

- `0x1800015d0`
- `0x180001ee8`
- `0x1800376b4`
- `0x1800391ec`
- `0x180040010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180037867`
- `KERNEL32!GetCurrentThreadId` at `0x180037867`
- `KERNEL32!FormatMessageW` at `0x1800377e6`
- `KERNEL32!FormatMessageW` at `0x1800377e6`

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
          v8 = (const char *)&qword_180046D98;
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
0x1800376b4  mov     [rsp+arg_18], rbx
0x1800376b9  push    rbp
0x1800376ba  push    rsi
0x1800376bb  push    rdi
0x1800376bc  push    r14
0x1800376be  push    r15
0x1800376c0  sub     rsp, 250h
0x1800376c7  mov     rax, cs:__security_cookie
0x1800376ce  xor     rax, rsp
0x1800376d1  mov     [rsp+278h+var_38], rax
0x1800376d9  xor     r15d, r15d
0x1800376dc  mov     rbx, r8
0x1800376df  mov     rsi, rdx
0x1800376e2  mov     r14, rcx
0x1800376e5  test    rdx, rdx
0x1800376e8  jz      loc_180037941
0x1800376ee  test    rcx, rcx
0x1800376f1  jz      loc_180037941
0x1800376f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800376fe  mov     [rcx], r15w
0x180037702  test    rax, rax
0x180037705  jz      short loc_180037728
0x180037707  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003770e  jz      short loc_180037728
0x180037710  mov     r8, rdx
0x180037713  mov     rdx, rcx
0x180037716  mov     rcx, rbx
0x180037719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003771e  cmp     [r14], r15w
0x180037722  jnz     loc_180037941
0x180037728  mov     ecx, [rbx]
0x18003772a  mov     bpl, 8
0x18003772d  test    ecx, ecx
0x18003772f  jz      short loc_18003777A
0x180037731  sub     ecx, 1
0x180037734  jz      short loc_180037762
0x180037736  sub     ecx, 1
0x180037739  jz      short loc_180037752
0x18003773b  cmp     ecx, 1
0x18003773e  jz      short loc_180037749
0x180037740  lea     rdi, qword_180046D98
0x180037747  jmp     short loc_180037781
0x180037749  lea     rdi, aFailfast; "FailFast"
0x180037750  jmp     short loc_180037781
0x180037752  lea     rax, aLoghr; "LogHr"
0x180037759  lea     rdi, aLognt; "LogNt"
0x180037760  jmp     short loc_180037770
0x180037762  lea     rax, aReturnhr; "ReturnHr"
0x180037769  lea     rdi, aReturnnt; "ReturnNt"
0x180037770  test    [rbx+4], bpl
0x180037774  cmovz   rdi, rax
0x180037778  jmp     short loc_180037781
0x18003777a  lea     rdi, aException; "Exception"
0x180037781  xor     edx, edx; Val
0x180037783  lea     rcx, [rsp+278h+Buffer]; void *
0x180037788  mov     r8d, 200h; Size
0x18003778e  call    memset_0
0x180037793  test    [rbx+4], bpl
0x180037797  jz      short loc_1800377BC
0x180037799  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800377a0  mov     ebp, [rbx+0Ch]
0x1800377a3  test    rax, rax
0x1800377a6  jz      short loc_1800377EC
0x1800377a8  mov     r8d, 100h
0x1800377ae  lea     rdx, [rsp+278h+Buffer]
0x1800377b3  mov     ecx, ebp
0x1800377b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377ba  jmp     short loc_1800377EC
0x1800377bc  mov     ebp, [rbx+8]
0x1800377bf  lea     rax, [rsp+278h+Buffer]
0x1800377c4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800377c9  mov     r8d, ebp; dwMessageId
0x1800377cc  mov     [rsp+278h+nSize], 100h; nSize
0x1800377d4  mov     r9d, 400h; dwLanguageId
0x1800377da  xor     edx, edx; lpSource
0x1800377dc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800377e1  mov     ecx, 1200h; dwFlags
0x1800377e6  call    cs:__imp_FormatMessageW
0x1800377ec  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800377f0  lea     rsi, [r14+rsi*2]
0x1800377f4  mov     rax, [rbx+88h]
0x1800377fb  mov     rdx, rsi; unsigned __int16 *
0x1800377fe  mov     rcx, [rbx+80h]
0x180037805  test    r9, r9
0x180037808  jz      short loc_18003782C
0x18003780a  mov     [rsp+278h+Arguments], rax
0x18003780f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180037816  mov     eax, [rbx+40h]
0x180037819  mov     qword ptr [rsp+278h+nSize], rcx
0x18003781e  mov     rcx, r14; this
0x180037821  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180037825  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003782a  jmp     short loc_180037843
0x18003782c  mov     r9, rcx; unsigned __int16 *
0x18003782f  mov     [rsp+278h+lpBuffer], rax
0x180037834  mov     rcx, r14; this
0x180037837  lea     r8, aHsP; "%hs!%p: "
0x18003783e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180037843  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003784a  mov     r14, rax
0x18003784d  test    r9, r9
0x180037850  jz      short loc_180037867
0x180037852  lea     r8, aCallerP; "(caller: %p) "
0x180037859  mov     rdx, rsi; unsigned __int16 *
0x18003785c  mov     rcx, rax; this
0x18003785f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180037864  mov     r14, rax
0x180037867  call    cs:__imp_GetCurrentThreadId
0x18003786d  lea     rcx, [rsp+278h+Buffer]
0x180037872  mov     r9, rdi; unsigned __int16 *
0x180037875  mov     [rsp+278h+var_240], rcx
0x18003787a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180037881  mov     dword ptr [rsp+278h+Arguments], ebp
0x180037885  mov     rdx, rsi; unsigned __int16 *
0x180037888  mov     [rsp+278h+nSize], eax
0x18003788c  mov     rcx, r14; this
0x18003788f  mov     eax, [rbx+44h]
0x180037892  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180037896  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003789b  cmp     [rbx+18h], r15
0x18003789f  jnz     short loc_1800378B1
0x1800378a1  cmp     [rbx+48h], r15
0x1800378a5  jnz     short loc_1800378B1
0x1800378a7  cmp     [rbx+30h], r15
0x1800378ab  jz      loc_180037941
0x1800378b1  lea     r8, asc_180046E88; "    "
0x1800378b8  mov     rdx, rsi; unsigned __int16 *
0x1800378bb  mov     rcx, rax; this
0x1800378be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800378c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800378c7  test    r9, r9
0x1800378ca  jz      short loc_1800378DE
0x1800378cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800378d3  mov     rdx, rsi; unsigned __int16 *
0x1800378d6  mov     rcx, rax; this
0x1800378d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800378de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800378e2  test    r9, r9
0x1800378e5  jz      short loc_1800378F9
0x1800378e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800378ee  mov     rdx, rsi; unsigned __int16 *
0x1800378f1  mov     rcx, rax; this
0x1800378f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800378f9  mov     rcx, [rbx+28h]
0x1800378fd  mov     rdx, rsi; unsigned __int16 *
0x180037900  mov     r9, [rbx+30h]; unsigned __int16 *
0x180037904  test    rcx, rcx
0x180037907  jz      short loc_18003791F
0x180037909  mov     [rsp+278h+lpBuffer], rcx
0x18003790e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180037915  mov     rcx, rax; this
0x180037918  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003791d  jmp     short loc_180037941
0x18003791f  mov     rcx, rax; this
0x180037922  test    r9, r9
0x180037925  jz      short loc_180037935
0x180037927  lea     r8, aHs; "[%hs]\n"
0x18003792e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180037933  jmp     short loc_180037941
0x180037935  lea     r8, asc_180046F00; "\n"
0x18003793c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180037941  xor     eax, eax
0x180037943  mov     rcx, [rsp+278h+var_38]
0x18003794b  xor     rcx, rsp; StackCookie
0x18003794e  call    __security_check_cookie
0x180037953  mov     rbx, [rsp+278h+arg_18]
0x18003795b  add     rsp, 250h
0x180037962  pop     r15
0x180037964  pop     r14
0x180037966  pop     rdi
0x180037967  pop     rsi
0x180037968  pop     rbp
0x180037969  retn
```
