# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000ae94`
- end: `0x18000b155`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008e88`
- `0x180009100`
- `0x18000b920`

## callees

- `0x18000ae94`
- `0x18000bc30`
- `0x180030362`
- `0x180030390`
- `0x180031010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000afc4`
- `KERNEL32!FormatMessageW` at `0x18000afc4`
- `KERNEL32!GetCurrentThreadId` at `0x18000b04b`
- `KERNEL32!GetCurrentThreadId` at `0x18000b04b`

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
  v8 = (const char *)&dword_18003572C;
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
0x18000ae94  mov     [rsp+arg_18], rbx
0x18000ae99  push    rbp
0x18000ae9a  push    rsi
0x18000ae9b  push    rdi
0x18000ae9c  push    r14
0x18000ae9e  push    r15
0x18000aea0  sub     rsp, 250h
0x18000aea7  mov     rax, cs:__security_cookie
0x18000aeae  xor     rax, rsp
0x18000aeb1  mov     [rsp+278h+var_38], rax
0x18000aeb9  xor     r15d, r15d
0x18000aebc  mov     rbx, r8
0x18000aebf  mov     rdi, rdx
0x18000aec2  mov     r14, rcx
0x18000aec5  test    rdx, rdx
0x18000aec8  jz      loc_18000B12B
0x18000aece  test    rcx, rcx
0x18000aed1  jz      loc_18000B12B
0x18000aed7  mov     rax, cs:g_pfnResultLoggingCallback
0x18000aede  mov     [rcx], r15w
0x18000aee2  test    rax, rax
0x18000aee5  jz      short loc_18000AF08
0x18000aee7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000aeee  jz      short loc_18000AF08
0x18000aef0  mov     r8, rdx
0x18000aef3  mov     rdx, rcx
0x18000aef6  mov     rcx, rbx
0x18000aef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aefe  cmp     [r14], r15w
0x18000af02  jnz     loc_18000B12B
0x18000af08  mov     ecx, [rbx]
0x18000af0a  lea     rsi, dword_18003572C
0x18000af11  mov     bpl, 8
0x18000af14  test    ecx, ecx
0x18000af16  jz      short loc_18000AF58
0x18000af18  sub     ecx, 1
0x18000af1b  jz      short loc_18000AF40
0x18000af1d  sub     ecx, 1
0x18000af20  jz      short loc_18000AF30
0x18000af22  cmp     ecx, 1
0x18000af25  jnz     short loc_18000AF5F
0x18000af27  lea     rsi, aFailfast; "FailFast"
0x18000af2e  jmp     short loc_18000AF5F
0x18000af30  lea     rax, aLoghr; "LogHr"
0x18000af37  lea     rsi, aLognt; "LogNt"
0x18000af3e  jmp     short loc_18000AF4E
0x18000af40  lea     rax, aReturnhr; "ReturnHr"
0x18000af47  lea     rsi, aReturnnt; "ReturnNt"
0x18000af4e  test    [rbx+4], bpl
0x18000af52  cmovz   rsi, rax
0x18000af56  jmp     short loc_18000AF5F
0x18000af58  lea     rsi, aException; "Exception"
0x18000af5f  xor     edx, edx; Val
0x18000af61  lea     rcx, [rsp+278h+Buffer]; void *
0x18000af66  mov     r8d, 200h; Size
0x18000af6c  call    memset_0
0x18000af71  test    [rbx+4], bpl
0x18000af75  jz      short loc_18000AF9A
0x18000af77  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000af7e  mov     ebp, [rbx+0Ch]
0x18000af81  test    rax, rax
0x18000af84  jz      short loc_18000AFD0
0x18000af86  mov     r8d, 100h
0x18000af8c  lea     rdx, [rsp+278h+Buffer]
0x18000af91  mov     ecx, ebp
0x18000af93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af98  jmp     short loc_18000AFD0
0x18000af9a  mov     ebp, [rbx+8]
0x18000af9d  lea     rax, [rsp+278h+Buffer]
0x18000afa2  mov     [rsp+278h+Arguments], r15; Arguments
0x18000afa7  mov     r8d, ebp; dwMessageId
0x18000afaa  mov     [rsp+278h+nSize], 100h; nSize
0x18000afb2  mov     r9d, 400h; dwLanguageId
0x18000afb8  xor     edx, edx; lpSource
0x18000afba  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000afbf  mov     ecx, 1200h; dwFlags
0x18000afc4  call    cs:__imp_FormatMessageW
0x18000afcb  nop     dword ptr [rax+rax+00h]
0x18000afd0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000afd4  lea     rdi, [r14+rdi*2]
0x18000afd8  mov     rax, [rbx+88h]
0x18000afdf  mov     rdx, rdi; unsigned __int16 *
0x18000afe2  mov     rcx, [rbx+80h]
0x18000afe9  test    r9, r9
0x18000afec  jz      short loc_18000B010
0x18000afee  mov     [rsp+278h+Arguments], rax
0x18000aff3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000affa  mov     eax, [rbx+40h]
0x18000affd  mov     qword ptr [rsp+278h+nSize], rcx
0x18000b002  mov     rcx, r14; this
0x18000b005  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b009  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b00e  jmp     short loc_18000B027
0x18000b010  mov     r9, rcx; unsigned __int16 *
0x18000b013  mov     [rsp+278h+lpBuffer], rax
0x18000b018  mov     rcx, r14; this
0x18000b01b  lea     r8, aHsP; "%hs!%p: "
0x18000b022  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b027  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000b02e  mov     r14, rax
0x18000b031  test    r9, r9
0x18000b034  jz      short loc_18000B04B
0x18000b036  lea     r8, aCallerP; "(caller: %p) "
0x18000b03d  mov     rdx, rdi; unsigned __int16 *
0x18000b040  mov     rcx, rax; this
0x18000b043  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b048  mov     r14, rax
0x18000b04b  call    cs:__imp_GetCurrentThreadId
0x18000b052  nop     dword ptr [rax+rax+00h]
0x18000b057  mov     ecx, [rbx+44h]
0x18000b05a  lea     rdx, [rsp+278h+Buffer]
0x18000b05f  mov     [rsp+278h+var_240], rdx
0x18000b064  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b06b  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b06f  mov     r9, rsi; unsigned __int16 *
0x18000b072  mov     [rsp+278h+nSize], eax
0x18000b076  mov     rdx, rdi; unsigned __int16 *
0x18000b079  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x18000b07d  mov     rcx, r14; this
0x18000b080  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b085  cmp     [rbx+18h], r15
0x18000b089  jnz     short loc_18000B09B
0x18000b08b  cmp     [rbx+48h], r15
0x18000b08f  jnz     short loc_18000B09B
0x18000b091  cmp     [rbx+30h], r15
0x18000b095  jz      loc_18000B12B
0x18000b09b  lea     r8, asc_180035B78; "    "
0x18000b0a2  mov     rdx, rdi; unsigned __int16 *
0x18000b0a5  mov     rcx, rax; this
0x18000b0a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b0ad  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000b0b1  test    r9, r9
0x18000b0b4  jz      short loc_18000B0C8
0x18000b0b6  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b0bd  mov     rdx, rdi; unsigned __int16 *
0x18000b0c0  mov     rcx, rax; this
0x18000b0c3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b0c8  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000b0cc  test    r9, r9
0x18000b0cf  jz      short loc_18000B0E3
0x18000b0d1  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b0d8  mov     rdx, rdi; unsigned __int16 *
0x18000b0db  mov     rcx, rax; this
0x18000b0de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b0e3  mov     rcx, [rbx+28h]
0x18000b0e7  mov     rdx, rdi; unsigned __int16 *
0x18000b0ea  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000b0ee  test    rcx, rcx
0x18000b0f1  jz      short loc_18000B109
0x18000b0f3  mov     [rsp+278h+lpBuffer], rcx
0x18000b0f8  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b0ff  mov     rcx, rax; this
0x18000b102  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b107  jmp     short loc_18000B12B
0x18000b109  mov     rcx, rax; this
0x18000b10c  test    r9, r9
0x18000b10f  jz      short loc_18000B11F
0x18000b111  lea     r8, aHs; "[%hs]\n"
0x18000b118  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b11d  jmp     short loc_18000B12B
0x18000b11f  lea     r8, OutputString; "\n"
0x18000b126  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b12b  xor     eax, eax
0x18000b12d  mov     rcx, [rsp+278h+var_38]
0x18000b135  xor     rcx, rsp; StackCookie
0x18000b138  call    __security_check_cookie
0x18000b13d  mov     rbx, [rsp+278h+arg_18]
0x18000b145  add     rsp, 250h
0x18000b14c  pop     r15
0x18000b14e  pop     r14
0x18000b150  pop     rdi
0x18000b151  pop     rsi
0x18000b152  pop     rbp
0x18000b153  retn
```
