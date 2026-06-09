# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800185f4`
- end: `0x1800188aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001516c`
- `0x1800153d4`
- `0x180019ee8`
- `0x180020760`

## callees

- `0x1800185f4`
- `0x18001a1e8`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800187a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800187a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018726`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018726`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
          v7 = (const char *)&byte_18007E0BD;
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
0x1800185f4  mov     [rsp+arg_18], rbx
0x1800185f9  push    rbp
0x1800185fa  push    rsi
0x1800185fb  push    rdi
0x1800185fc  push    r14
0x1800185fe  push    r15
0x180018600  sub     rsp, 250h
0x180018607  mov     rax, cs:__security_cookie
0x18001860e  xor     rax, rsp
0x180018611  mov     [rsp+278h+var_38], rax
0x180018619  mov     rbx, r8
0x18001861c  mov     rsi, rdx
0x18001861f  mov     r14, rcx
0x180018622  xor     r15d, r15d
0x180018625  test    rdx, rdx
0x180018628  jz      loc_180018881
0x18001862e  test    rcx, rcx
0x180018631  jz      loc_180018881
0x180018637  mov     [rcx], r15w
0x18001863b  mov     rax, cs:g_pfnResultLoggingCallback
0x180018642  test    rax, rax
0x180018645  jz      short loc_180018668
0x180018647  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001864e  jz      short loc_180018668
0x180018650  mov     r8, rdx
0x180018653  mov     rdx, rcx
0x180018656  mov     rcx, rbx
0x180018659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001865e  cmp     [r14], r15w
0x180018662  jnz     loc_180018881
0x180018668  mov     ecx, [rbx]
0x18001866a  mov     bpl, 8
0x18001866d  test    ecx, ecx
0x18001866f  jz      short loc_1800186BA
0x180018671  sub     ecx, 1
0x180018674  jz      short loc_1800186A2
0x180018676  sub     ecx, 1
0x180018679  jz      short loc_180018692
0x18001867b  cmp     ecx, 1
0x18001867e  jz      short loc_180018689
0x180018680  lea     rdi, byte_18007E0BD
0x180018687  jmp     short loc_1800186C1
0x180018689  lea     rdi, aFailfast; "FailFast"
0x180018690  jmp     short loc_1800186C1
0x180018692  lea     rax, aLoghr; "LogHr"
0x180018699  lea     rdi, aLognt; "LogNt"
0x1800186a0  jmp     short loc_1800186B0
0x1800186a2  lea     rax, aReturnhr; "ReturnHr"
0x1800186a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800186b0  test    [rbx+4], bpl
0x1800186b4  cmovz   rdi, rax
0x1800186b8  jmp     short loc_1800186C1
0x1800186ba  lea     rdi, aException; "Exception"
0x1800186c1  xor     edx, edx; Val
0x1800186c3  mov     r8d, 200h; Size
0x1800186c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800186ce  call    memset_0
0x1800186d3  test    [rbx+4], bpl
0x1800186d7  jz      short loc_1800186FC
0x1800186d9  mov     ebp, [rbx+0Ch]
0x1800186dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800186e3  test    rax, rax
0x1800186e6  jz      short loc_18001872C
0x1800186e8  mov     r8d, 100h
0x1800186ee  lea     rdx, [rsp+278h+Buffer]
0x1800186f3  mov     ecx, ebp
0x1800186f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186fa  jmp     short loc_18001872C
0x1800186fc  mov     ebp, [rbx+8]
0x1800186ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180018704  mov     [rsp+278h+nSize], 100h; nSize
0x18001870c  lea     rax, [rsp+278h+Buffer]
0x180018711  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180018716  mov     r9d, 400h; dwLanguageId
0x18001871c  mov     r8d, ebp; dwMessageId
0x18001871f  xor     edx, edx; lpSource
0x180018721  mov     ecx, 1200h; dwFlags
0x180018726  call    cs:__imp_FormatMessageW
0x18001872c  lea     rsi, [r14+rsi*2]
0x180018730  mov     r9, [rbx+38h]; unsigned __int16 *
0x180018734  mov     rax, [rbx+88h]
0x18001873b  mov     rcx, [rbx+80h]
0x180018742  mov     rdx, rsi; unsigned __int16 *
0x180018745  test    r9, r9
0x180018748  jz      short loc_18001876C
0x18001874a  mov     [rsp+278h+Arguments], rax
0x18001874f  mov     qword ptr [rsp+278h+nSize], rcx
0x180018754  mov     eax, [rbx+40h]
0x180018757  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001875b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180018762  mov     rcx, r14; this
0x180018765  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001876a  jmp     short loc_180018783
0x18001876c  mov     [rsp+278h+lpBuffer], rax
0x180018771  mov     r9, rcx; unsigned __int16 *
0x180018774  lea     r8, aHsP; "%hs!%p: "
0x18001877b  mov     rcx, r14; this
0x18001877e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018783  mov     r14, rax
0x180018786  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001878d  test    r9, r9
0x180018790  jz      short loc_1800187A7
0x180018792  lea     r8, aCallerP; "(caller: %p) "
0x180018799  mov     rdx, rsi; unsigned __int16 *
0x18001879c  mov     rcx, rax; this
0x18001879f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800187a4  mov     r14, rax
0x1800187a7  call    cs:__imp_GetCurrentThreadId
0x1800187ad  lea     rcx, [rsp+278h+Buffer]
0x1800187b2  mov     [rsp+278h+var_240], rcx
0x1800187b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800187bb  mov     [rsp+278h+nSize], eax
0x1800187bf  mov     eax, [rbx+44h]
0x1800187c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800187c6  mov     r9, rdi; unsigned __int16 *
0x1800187c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800187d0  mov     rdx, rsi; unsigned __int16 *
0x1800187d3  mov     rcx, r14; this
0x1800187d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800187db  cmp     [rbx+18h], r15
0x1800187df  jnz     short loc_1800187F1
0x1800187e1  cmp     [rbx+48h], r15
0x1800187e5  jnz     short loc_1800187F1
0x1800187e7  cmp     [rbx+30h], r15
0x1800187eb  jz      loc_180018881
0x1800187f1  lea     r8, asc_180084260; "    "
0x1800187f8  mov     rdx, rsi; unsigned __int16 *
0x1800187fb  mov     rcx, rax; this
0x1800187fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018803  mov     r9, [rbx+18h]; unsigned __int16 *
0x180018807  test    r9, r9
0x18001880a  jz      short loc_18001881E
0x18001880c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180018813  mov     rdx, rsi; unsigned __int16 *
0x180018816  mov     rcx, rax; this
0x180018819  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001881e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180018822  test    r9, r9
0x180018825  jz      short loc_180018839
0x180018827  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001882e  mov     rdx, rsi; unsigned __int16 *
0x180018831  mov     rcx, rax; this
0x180018834  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018839  mov     rcx, [rbx+28h]
0x18001883d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180018841  mov     rdx, rsi; unsigned __int16 *
0x180018844  test    rcx, rcx
0x180018847  jz      short loc_18001885F
0x180018849  mov     [rsp+278h+lpBuffer], rcx
0x18001884e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180018855  mov     rcx, rax; this
0x180018858  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001885d  jmp     short loc_180018881
0x18001885f  mov     rcx, rax; this
0x180018862  test    r9, r9
0x180018865  jz      short loc_180018875
0x180018867  lea     r8, aHs; "[%hs]\n"
0x18001886e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018873  jmp     short loc_180018881
0x180018875  lea     r8, asc_1800842D8; "\n"
0x18001887c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018881  xor     eax, eax
0x180018883  mov     rcx, [rsp+278h+var_38]
0x18001888b  xor     rcx, rsp; StackCookie
0x18001888e  call    __security_check_cookie
0x180018893  mov     rbx, [rsp+278h+arg_18]
0x18001889b  add     rsp, 250h
0x1800188a2  pop     r15
0x1800188a4  pop     r14
0x1800188a6  pop     rdi
0x1800188a7  pop     rsi
0x1800188a8  pop     rbp
0x1800188a9  retn
```
