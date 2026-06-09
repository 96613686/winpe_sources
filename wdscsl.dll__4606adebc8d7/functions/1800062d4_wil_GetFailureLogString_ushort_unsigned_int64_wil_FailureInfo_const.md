# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800062d4`
- end: `0x180006595`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b48`
- `0x180002dc0`
- `0x18000796c`

## callees

- `0x1800062d4`
- `0x180007c7c`
- `0x18000d6d2`
- `0x18000d700`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000648b`
- `KERNEL32!GetCurrentThreadId` at `0x18000648b`
- `KERNEL32!FormatMessageW` at `0x180006404`
- `KERNEL32!FormatMessageW` at `0x180006404`

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
  v8 = (const char *)&dword_180011084;
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
0x1800062d4  mov     [rsp+arg_18], rbx
0x1800062d9  push    rbp
0x1800062da  push    rsi
0x1800062db  push    rdi
0x1800062dc  push    r14
0x1800062de  push    r15
0x1800062e0  sub     rsp, 250h
0x1800062e7  mov     rax, cs:__security_cookie
0x1800062ee  xor     rax, rsp
0x1800062f1  mov     [rsp+278h+var_38], rax
0x1800062f9  xor     r15d, r15d
0x1800062fc  mov     rbx, r8
0x1800062ff  mov     rdi, rdx
0x180006302  mov     r14, rcx
0x180006305  test    rdx, rdx
0x180006308  jz      loc_18000656B
0x18000630e  test    rcx, rcx
0x180006311  jz      loc_18000656B
0x180006317  mov     rax, cs:g_pfnResultLoggingCallback
0x18000631e  mov     [rcx], r15w
0x180006322  test    rax, rax
0x180006325  jz      short loc_180006348
0x180006327  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000632e  jz      short loc_180006348
0x180006330  mov     r8, rdx
0x180006333  mov     rdx, rcx
0x180006336  mov     rcx, rbx
0x180006339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000633e  cmp     [r14], r15w
0x180006342  jnz     loc_18000656B
0x180006348  mov     ecx, [rbx]
0x18000634a  lea     rsi, dword_180011084
0x180006351  mov     bpl, 8
0x180006354  test    ecx, ecx
0x180006356  jz      short loc_180006398
0x180006358  sub     ecx, 1
0x18000635b  jz      short loc_180006380
0x18000635d  sub     ecx, 1
0x180006360  jz      short loc_180006370
0x180006362  cmp     ecx, 1
0x180006365  jnz     short loc_18000639F
0x180006367  lea     rsi, aFailfast; "FailFast"
0x18000636e  jmp     short loc_18000639F
0x180006370  lea     rax, aLoghr; "LogHr"
0x180006377  lea     rsi, aLognt; "LogNt"
0x18000637e  jmp     short loc_18000638E
0x180006380  lea     rax, aReturnhr; "ReturnHr"
0x180006387  lea     rsi, aReturnnt; "ReturnNt"
0x18000638e  test    [rbx+4], bpl
0x180006392  cmovz   rsi, rax
0x180006396  jmp     short loc_18000639F
0x180006398  lea     rsi, aException; "Exception"
0x18000639f  xor     edx, edx; Val
0x1800063a1  lea     rcx, [rsp+278h+Buffer]; void *
0x1800063a6  mov     r8d, 200h; Size
0x1800063ac  call    memset_0
0x1800063b1  test    [rbx+4], bpl
0x1800063b5  jz      short loc_1800063DA
0x1800063b7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800063be  mov     ebp, [rbx+0Ch]
0x1800063c1  test    rax, rax
0x1800063c4  jz      short loc_180006410
0x1800063c6  mov     r8d, 100h
0x1800063cc  lea     rdx, [rsp+278h+Buffer]
0x1800063d1  mov     ecx, ebp
0x1800063d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d8  jmp     short loc_180006410
0x1800063da  mov     ebp, [rbx+8]
0x1800063dd  lea     rax, [rsp+278h+Buffer]
0x1800063e2  mov     [rsp+278h+Arguments], r15; Arguments
0x1800063e7  mov     r8d, ebp; dwMessageId
0x1800063ea  mov     [rsp+278h+nSize], 100h; nSize
0x1800063f2  mov     r9d, 400h; dwLanguageId
0x1800063f8  xor     edx, edx; lpSource
0x1800063fa  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800063ff  mov     ecx, 1200h; dwFlags
0x180006404  call    cs:__imp_FormatMessageW
0x18000640b  nop     dword ptr [rax+rax+00h]
0x180006410  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006414  lea     rdi, [r14+rdi*2]
0x180006418  mov     rax, [rbx+88h]
0x18000641f  mov     rdx, rdi; unsigned __int16 *
0x180006422  mov     rcx, [rbx+80h]
0x180006429  test    r9, r9
0x18000642c  jz      short loc_180006450
0x18000642e  mov     [rsp+278h+Arguments], rax
0x180006433  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000643a  mov     eax, [rbx+40h]
0x18000643d  mov     qword ptr [rsp+278h+nSize], rcx
0x180006442  mov     rcx, r14; this
0x180006445  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006449  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000644e  jmp     short loc_180006467
0x180006450  mov     r9, rcx; unsigned __int16 *
0x180006453  mov     [rsp+278h+lpBuffer], rax
0x180006458  mov     rcx, r14; this
0x18000645b  lea     r8, aHsP; "%hs!%p: "
0x180006462  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006467  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000646e  mov     r14, rax
0x180006471  test    r9, r9
0x180006474  jz      short loc_18000648B
0x180006476  lea     r8, aCallerP; "(caller: %p) "
0x18000647d  mov     rdx, rdi; unsigned __int16 *
0x180006480  mov     rcx, rax; this
0x180006483  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006488  mov     r14, rax
0x18000648b  call    cs:__imp_GetCurrentThreadId
0x180006492  nop     dword ptr [rax+rax+00h]
0x180006497  mov     ecx, [rbx+44h]
0x18000649a  lea     rdx, [rsp+278h+Buffer]
0x18000649f  mov     [rsp+278h+var_240], rdx
0x1800064a4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800064ab  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800064af  mov     r9, rsi; unsigned __int16 *
0x1800064b2  mov     [rsp+278h+nSize], eax
0x1800064b6  mov     rdx, rdi; unsigned __int16 *
0x1800064b9  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x1800064bd  mov     rcx, r14; this
0x1800064c0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800064c5  cmp     [rbx+18h], r15
0x1800064c9  jnz     short loc_1800064DB
0x1800064cb  cmp     [rbx+48h], r15
0x1800064cf  jnz     short loc_1800064DB
0x1800064d1  cmp     [rbx+30h], r15
0x1800064d5  jz      loc_18000656B
0x1800064db  lea     r8, asc_1800111D0; "    "
0x1800064e2  mov     rdx, rdi; unsigned __int16 *
0x1800064e5  mov     rcx, rax; this
0x1800064e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800064ed  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800064f1  test    r9, r9
0x1800064f4  jz      short loc_180006508
0x1800064f6  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800064fd  mov     rdx, rdi; unsigned __int16 *
0x180006500  mov     rcx, rax; this
0x180006503  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006508  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000650c  test    r9, r9
0x18000650f  jz      short loc_180006523
0x180006511  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006518  mov     rdx, rdi; unsigned __int16 *
0x18000651b  mov     rcx, rax; this
0x18000651e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006523  mov     rcx, [rbx+28h]
0x180006527  mov     rdx, rdi; unsigned __int16 *
0x18000652a  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000652e  test    rcx, rcx
0x180006531  jz      short loc_180006549
0x180006533  mov     [rsp+278h+lpBuffer], rcx
0x180006538  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000653f  mov     rcx, rax; this
0x180006542  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006547  jmp     short loc_18000656B
0x180006549  mov     rcx, rax; this
0x18000654c  test    r9, r9
0x18000654f  jz      short loc_18000655F
0x180006551  lea     r8, aHs; "[%hs]\n"
0x180006558  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000655d  jmp     short loc_18000656B
0x18000655f  lea     r8, asc_180011248; "\n"
0x180006566  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000656b  xor     eax, eax
0x18000656d  mov     rcx, [rsp+278h+var_38]
0x180006575  xor     rcx, rsp; StackCookie
0x180006578  call    __security_check_cookie
0x18000657d  mov     rbx, [rsp+278h+arg_18]
0x180006585  add     rsp, 250h
0x18000658c  pop     r15
0x18000658e  pop     r14
0x180006590  pop     rdi
0x180006591  pop     rsi
0x180006592  pop     rbp
0x180006593  retn
```
