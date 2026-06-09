# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800091d4`
- end: `0x180009495`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800068d0`
- `0x180006b48`
- `0x18000a414`

## callees

- `0x1800091d4`
- `0x18000a724`
- `0x18001c12a`
- `0x18001c150`
- `0x18001d010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180009304`
- `KERNEL32!FormatMessageW` at `0x180009304`
- `KERNEL32!GetCurrentThreadId` at `0x18000938b`
- `KERNEL32!GetCurrentThreadId` at `0x18000938b`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rsi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdi
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
  v8 = (const char *)&dword_18001F974;
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
        goto LABEL_17;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_17;
  }
  v8 = "Exception";
LABEL_17:
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
0x1800091d4  mov     [rsp+arg_18], rbx
0x1800091d9  push    rbp
0x1800091da  push    rsi
0x1800091db  push    rdi
0x1800091dc  push    r14
0x1800091de  push    r15
0x1800091e0  sub     rsp, 250h
0x1800091e7  mov     rax, cs:__security_cookie
0x1800091ee  xor     rax, rsp
0x1800091f1  mov     [rsp+278h+var_38], rax
0x1800091f9  xor     r15d, r15d
0x1800091fc  mov     rbx, r8
0x1800091ff  mov     rdi, rdx
0x180009202  mov     r14, rcx
0x180009205  test    rdx, rdx
0x180009208  jz      loc_18000946B
0x18000920e  test    rcx, rcx
0x180009211  jz      loc_18000946B
0x180009217  mov     rax, cs:g_pfnResultLoggingCallback
0x18000921e  mov     [rcx], r15w
0x180009222  test    rax, rax
0x180009225  jz      short loc_180009248
0x180009227  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000922e  jz      short loc_180009248
0x180009230  mov     r8, rdx
0x180009233  mov     rdx, rcx
0x180009236  mov     rcx, rbx
0x180009239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000923e  cmp     [r14], r15w
0x180009242  jnz     loc_18000946B
0x180009248  mov     ecx, [rbx]
0x18000924a  lea     rsi, dword_18001F974
0x180009251  mov     bpl, 8
0x180009254  test    ecx, ecx
0x180009256  jz      short loc_180009298
0x180009258  sub     ecx, 1
0x18000925b  jz      short loc_180009280
0x18000925d  sub     ecx, 1
0x180009260  jz      short loc_180009270
0x180009262  cmp     ecx, 1
0x180009265  jnz     short loc_18000929F
0x180009267  lea     rsi, aFailfast; "FailFast"
0x18000926e  jmp     short loc_18000929F
0x180009270  lea     rax, aLoghr; "LogHr"
0x180009277  lea     rsi, aLognt; "LogNt"
0x18000927e  jmp     short loc_18000928E
0x180009280  lea     rax, aReturnhr; "ReturnHr"
0x180009287  lea     rsi, aReturnnt; "ReturnNt"
0x18000928e  test    [rbx+4], bpl
0x180009292  cmovz   rsi, rax
0x180009296  jmp     short loc_18000929F
0x180009298  lea     rsi, aException; "Exception"
0x18000929f  xor     edx, edx; Val
0x1800092a1  lea     rcx, [rsp+278h+Buffer]; void *
0x1800092a6  mov     r8d, 200h; Size
0x1800092ac  call    memset_0
0x1800092b1  test    [rbx+4], bpl
0x1800092b5  jz      short loc_1800092DA
0x1800092b7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800092be  mov     ebp, [rbx+0Ch]
0x1800092c1  test    rax, rax
0x1800092c4  jz      short loc_180009310
0x1800092c6  mov     r8d, 100h
0x1800092cc  lea     rdx, [rsp+278h+Buffer]
0x1800092d1  mov     ecx, ebp
0x1800092d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092d8  jmp     short loc_180009310
0x1800092da  mov     ebp, [rbx+8]
0x1800092dd  lea     rax, [rsp+278h+Buffer]
0x1800092e2  mov     [rsp+278h+Arguments], r15; Arguments
0x1800092e7  mov     r8d, ebp; dwMessageId
0x1800092ea  mov     [rsp+278h+nSize], 100h; nSize
0x1800092f2  mov     r9d, 400h; dwLanguageId
0x1800092f8  xor     edx, edx; lpSource
0x1800092fa  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800092ff  mov     ecx, 1200h; dwFlags
0x180009304  call    cs:__imp_FormatMessageW
0x18000930b  nop     dword ptr [rax+rax+00h]
0x180009310  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009314  lea     rdi, [r14+rdi*2]
0x180009318  mov     rax, [rbx+88h]
0x18000931f  mov     rdx, rdi; unsigned __int16 *
0x180009322  mov     rcx, [rbx+80h]
0x180009329  test    r9, r9
0x18000932c  jz      short loc_180009350
0x18000932e  mov     [rsp+278h+Arguments], rax
0x180009333  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000933a  mov     eax, [rbx+40h]
0x18000933d  mov     qword ptr [rsp+278h+nSize], rcx
0x180009342  mov     rcx, r14; this
0x180009345  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009349  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000934e  jmp     short loc_180009367
0x180009350  mov     r9, rcx; unsigned __int16 *
0x180009353  mov     [rsp+278h+lpBuffer], rax
0x180009358  mov     rcx, r14; this
0x18000935b  lea     r8, aHsP; "%hs!%p: "
0x180009362  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009367  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000936e  mov     r14, rax
0x180009371  test    r9, r9
0x180009374  jz      short loc_18000938B
0x180009376  lea     r8, aCallerP; "(caller: %p) "
0x18000937d  mov     rdx, rdi; unsigned __int16 *
0x180009380  mov     rcx, rax; this
0x180009383  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009388  mov     r14, rax
0x18000938b  call    cs:__imp_GetCurrentThreadId
0x180009392  nop     dword ptr [rax+rax+00h]
0x180009397  mov     ecx, [rbx+44h]
0x18000939a  lea     rdx, [rsp+278h+Buffer]
0x18000939f  mov     [rsp+278h+var_240], rdx
0x1800093a4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800093ab  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800093af  mov     r9, rsi; unsigned __int16 *
0x1800093b2  mov     [rsp+278h+nSize], eax
0x1800093b6  mov     rdx, rdi; unsigned __int16 *
0x1800093b9  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x1800093bd  mov     rcx, r14; this
0x1800093c0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800093c5  cmp     [rbx+18h], r15
0x1800093c9  jnz     short loc_1800093DB
0x1800093cb  cmp     [rbx+48h], r15
0x1800093cf  jnz     short loc_1800093DB
0x1800093d1  cmp     [rbx+30h], r15
0x1800093d5  jz      loc_18000946B
0x1800093db  lea     r8, asc_180020830; "    "
0x1800093e2  mov     rdx, rdi; unsigned __int16 *
0x1800093e5  mov     rcx, rax; this
0x1800093e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800093ed  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800093f1  test    r9, r9
0x1800093f4  jz      short loc_180009408
0x1800093f6  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800093fd  mov     rdx, rdi; unsigned __int16 *
0x180009400  mov     rcx, rax; this
0x180009403  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009408  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000940c  test    r9, r9
0x18000940f  jz      short loc_180009423
0x180009411  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009418  mov     rdx, rdi; unsigned __int16 *
0x18000941b  mov     rcx, rax; this
0x18000941e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009423  mov     rcx, [rbx+28h]
0x180009427  mov     rdx, rdi; unsigned __int16 *
0x18000942a  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000942e  test    rcx, rcx
0x180009431  jz      short loc_180009449
0x180009433  mov     [rsp+278h+lpBuffer], rcx
0x180009438  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000943f  mov     rcx, rax; this
0x180009442  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009447  jmp     short loc_18000946B
0x180009449  mov     rcx, rax; this
0x18000944c  test    r9, r9
0x18000944f  jz      short loc_18000945F
0x180009451  lea     r8, aHs; "[%hs]\n"
0x180009458  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000945d  jmp     short loc_18000946B
0x18000945f  lea     r8, asc_1800208A8; "\n"
0x180009466  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000946b  xor     eax, eax
0x18000946d  mov     rcx, [rsp+278h+var_38]
0x180009475  xor     rcx, rsp; StackCookie
0x180009478  call    __security_check_cookie
0x18000947d  mov     rbx, [rsp+278h+arg_18]
0x180009485  add     rsp, 250h
0x18000948c  pop     r15
0x18000948e  pop     r14
0x180009490  pop     rdi
0x180009491  pop     rsi
0x180009492  pop     rbp
0x180009493  retn
```
