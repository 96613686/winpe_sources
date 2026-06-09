# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800250c4`
- end: `0x18002537a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180024464`
- `0x180025a70`

## callees

- `0x1800250c4`
- `0x180025d70`
- `0x18002924e`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800251f6`
- `KERNEL32!FormatMessageW` at `0x1800251f6`
- `KERNEL32!GetCurrentThreadId` at `0x180025277`
- `KERNEL32!GetCurrentThreadId` at `0x180025277`

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
          v8 = (const char *)&word_18002E892;
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
0x1800250c4  mov     [rsp+arg_18], rbx
0x1800250c9  push    rbp
0x1800250ca  push    rsi
0x1800250cb  push    rdi
0x1800250cc  push    r14
0x1800250ce  push    r15
0x1800250d0  sub     rsp, 250h
0x1800250d7  mov     rax, cs:__security_cookie
0x1800250de  xor     rax, rsp
0x1800250e1  mov     [rsp+278h+var_38], rax
0x1800250e9  xor     r15d, r15d
0x1800250ec  mov     rbx, r8
0x1800250ef  mov     rsi, rdx
0x1800250f2  mov     r14, rcx
0x1800250f5  test    rdx, rdx
0x1800250f8  jz      loc_180025351
0x1800250fe  test    rcx, rcx
0x180025101  jz      loc_180025351
0x180025107  mov     rax, cs:g_pfnResultLoggingCallback
0x18002510e  mov     [rcx], r15w
0x180025112  test    rax, rax
0x180025115  jz      short loc_180025138
0x180025117  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002511e  jz      short loc_180025138
0x180025120  mov     r8, rdx
0x180025123  mov     rdx, rcx
0x180025126  mov     rcx, rbx
0x180025129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002512e  cmp     [r14], r15w
0x180025132  jnz     loc_180025351
0x180025138  mov     ecx, [rbx]
0x18002513a  mov     bpl, 8
0x18002513d  test    ecx, ecx
0x18002513f  jz      short loc_18002518A
0x180025141  sub     ecx, 1
0x180025144  jz      short loc_180025172
0x180025146  sub     ecx, 1
0x180025149  jz      short loc_180025162
0x18002514b  cmp     ecx, 1
0x18002514e  jz      short loc_180025159
0x180025150  lea     rdi, word_18002E892
0x180025157  jmp     short loc_180025191
0x180025159  lea     rdi, aFailfast; "FailFast"
0x180025160  jmp     short loc_180025191
0x180025162  lea     rax, aLoghr; "LogHr"
0x180025169  lea     rdi, aLognt; "LogNt"
0x180025170  jmp     short loc_180025180
0x180025172  lea     rax, aReturnhr; "ReturnHr"
0x180025179  lea     rdi, aReturnnt; "ReturnNt"
0x180025180  test    [rbx+4], bpl
0x180025184  cmovz   rdi, rax
0x180025188  jmp     short loc_180025191
0x18002518a  lea     rdi, aException; "Exception"
0x180025191  xor     edx, edx; Val
0x180025193  lea     rcx, [rsp+278h+Buffer]; void *
0x180025198  mov     r8d, 200h; Size
0x18002519e  call    memset_0
0x1800251a3  test    [rbx+4], bpl
0x1800251a7  jz      short loc_1800251CC
0x1800251a9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800251b0  mov     ebp, [rbx+0Ch]
0x1800251b3  test    rax, rax
0x1800251b6  jz      short loc_1800251FC
0x1800251b8  mov     r8d, 100h
0x1800251be  lea     rdx, [rsp+278h+Buffer]
0x1800251c3  mov     ecx, ebp
0x1800251c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251ca  jmp     short loc_1800251FC
0x1800251cc  mov     ebp, [rbx+8]
0x1800251cf  lea     rax, [rsp+278h+Buffer]
0x1800251d4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800251d9  mov     r8d, ebp; dwMessageId
0x1800251dc  mov     [rsp+278h+nSize], 100h; nSize
0x1800251e4  mov     r9d, 400h; dwLanguageId
0x1800251ea  xor     edx, edx; lpSource
0x1800251ec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800251f1  mov     ecx, 1200h; dwFlags
0x1800251f6  call    cs:__imp_FormatMessageW
0x1800251fc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180025200  lea     rsi, [r14+rsi*2]
0x180025204  mov     rax, [rbx+88h]
0x18002520b  mov     rdx, rsi; unsigned __int16 *
0x18002520e  mov     rcx, [rbx+80h]
0x180025215  test    r9, r9
0x180025218  jz      short loc_18002523C
0x18002521a  mov     [rsp+278h+Arguments], rax
0x18002521f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180025226  mov     eax, [rbx+40h]
0x180025229  mov     qword ptr [rsp+278h+nSize], rcx
0x18002522e  mov     rcx, r14; this
0x180025231  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180025235  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002523a  jmp     short loc_180025253
0x18002523c  mov     r9, rcx; unsigned __int16 *
0x18002523f  mov     [rsp+278h+lpBuffer], rax
0x180025244  mov     rcx, r14; this
0x180025247  lea     r8, aHsP; "%hs!%p: "
0x18002524e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025253  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002525a  mov     r14, rax
0x18002525d  test    r9, r9
0x180025260  jz      short loc_180025277
0x180025262  lea     r8, aCallerP; "(caller: %p) "
0x180025269  mov     rdx, rsi; unsigned __int16 *
0x18002526c  mov     rcx, rax; this
0x18002526f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025274  mov     r14, rax
0x180025277  call    cs:__imp_GetCurrentThreadId
0x18002527d  lea     rcx, [rsp+278h+Buffer]
0x180025282  mov     r9, rdi; unsigned __int16 *
0x180025285  mov     [rsp+278h+var_240], rcx
0x18002528a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180025291  mov     dword ptr [rsp+278h+Arguments], ebp
0x180025295  mov     rdx, rsi; unsigned __int16 *
0x180025298  mov     [rsp+278h+nSize], eax
0x18002529c  mov     rcx, r14; this
0x18002529f  mov     eax, [rbx+44h]
0x1800252a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800252a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800252ab  cmp     [rbx+18h], r15
0x1800252af  jnz     short loc_1800252C1
0x1800252b1  cmp     [rbx+48h], r15
0x1800252b5  jnz     short loc_1800252C1
0x1800252b7  cmp     [rbx+30h], r15
0x1800252bb  jz      loc_180025351
0x1800252c1  lea     r8, asc_18002E980; "    "
0x1800252c8  mov     rdx, rsi; unsigned __int16 *
0x1800252cb  mov     rcx, rax; this
0x1800252ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800252d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800252d7  test    r9, r9
0x1800252da  jz      short loc_1800252EE
0x1800252dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800252e3  mov     rdx, rsi; unsigned __int16 *
0x1800252e6  mov     rcx, rax; this
0x1800252e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800252ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800252f2  test    r9, r9
0x1800252f5  jz      short loc_180025309
0x1800252f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800252fe  mov     rdx, rsi; unsigned __int16 *
0x180025301  mov     rcx, rax; this
0x180025304  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025309  mov     rcx, [rbx+28h]
0x18002530d  mov     rdx, rsi; unsigned __int16 *
0x180025310  mov     r9, [rbx+30h]; unsigned __int16 *
0x180025314  test    rcx, rcx
0x180025317  jz      short loc_18002532F
0x180025319  mov     [rsp+278h+lpBuffer], rcx
0x18002531e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180025325  mov     rcx, rax; this
0x180025328  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002532d  jmp     short loc_180025351
0x18002532f  mov     rcx, rax; this
0x180025332  test    r9, r9
0x180025335  jz      short loc_180025345
0x180025337  lea     r8, aHs; "[%hs]\n"
0x18002533e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025343  jmp     short loc_180025351
0x180025345  lea     r8, asc_18002E750; "\n"
0x18002534c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025351  xor     eax, eax
0x180025353  mov     rcx, [rsp+278h+var_38]
0x18002535b  xor     rcx, rsp; StackCookie
0x18002535e  call    __security_check_cookie
0x180025363  mov     rbx, [rsp+278h+arg_18]
0x18002536b  add     rsp, 250h
0x180025372  pop     r15
0x180025374  pop     r14
0x180025376  pop     rdi
0x180025377  pop     rsi
0x180025378  pop     rbp
0x180025379  retn
```
