# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800380e4`
- end: `0x18003839a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18003576c`
- `0x1800359d4`
- `0x1800392b8`

## callees

- `0x180001600`
- `0x180001f50`
- `0x1800380e4`
- `0x1800395b8`
- `0x180040010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180038216`
- `KERNEL32!FormatMessageW` at `0x180038216`
- `KERNEL32!GetCurrentThreadId` at `0x180038297`
- `KERNEL32!GetCurrentThreadId` at `0x180038297`

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
          v8 = (const char *)&word_18004AF8E;
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
0x1800380e4  mov     [rsp+arg_18], rbx
0x1800380e9  push    rbp
0x1800380ea  push    rsi
0x1800380eb  push    rdi
0x1800380ec  push    r14
0x1800380ee  push    r15
0x1800380f0  sub     rsp, 250h
0x1800380f7  mov     rax, cs:__security_cookie
0x1800380fe  xor     rax, rsp
0x180038101  mov     [rsp+278h+var_38], rax
0x180038109  xor     r15d, r15d
0x18003810c  mov     rbx, r8
0x18003810f  mov     rsi, rdx
0x180038112  mov     r14, rcx
0x180038115  test    rdx, rdx
0x180038118  jz      loc_180038371
0x18003811e  test    rcx, rcx
0x180038121  jz      loc_180038371
0x180038127  mov     rax, cs:g_pfnResultLoggingCallback
0x18003812e  mov     [rcx], r15w
0x180038132  test    rax, rax
0x180038135  jz      short loc_180038158
0x180038137  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003813e  jz      short loc_180038158
0x180038140  mov     r8, rdx
0x180038143  mov     rdx, rcx
0x180038146  mov     rcx, rbx
0x180038149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003814e  cmp     [r14], r15w
0x180038152  jnz     loc_180038371
0x180038158  mov     ecx, [rbx]
0x18003815a  mov     bpl, 8
0x18003815d  test    ecx, ecx
0x18003815f  jz      short loc_1800381AA
0x180038161  sub     ecx, 1
0x180038164  jz      short loc_180038192
0x180038166  sub     ecx, 1
0x180038169  jz      short loc_180038182
0x18003816b  cmp     ecx, 1
0x18003816e  jz      short loc_180038179
0x180038170  lea     rdi, word_18004AF8E
0x180038177  jmp     short loc_1800381B1
0x180038179  lea     rdi, aFailfast; "FailFast"
0x180038180  jmp     short loc_1800381B1
0x180038182  lea     rax, aLoghr; "LogHr"
0x180038189  lea     rdi, aLognt; "LogNt"
0x180038190  jmp     short loc_1800381A0
0x180038192  lea     rax, aReturnhr; "ReturnHr"
0x180038199  lea     rdi, aReturnnt; "ReturnNt"
0x1800381a0  test    [rbx+4], bpl
0x1800381a4  cmovz   rdi, rax
0x1800381a8  jmp     short loc_1800381B1
0x1800381aa  lea     rdi, aException; "Exception"
0x1800381b1  xor     edx, edx; Val
0x1800381b3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800381b8  mov     r8d, 200h; Size
0x1800381be  call    memset_0
0x1800381c3  test    [rbx+4], bpl
0x1800381c7  jz      short loc_1800381EC
0x1800381c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800381d0  mov     ebp, [rbx+0Ch]
0x1800381d3  test    rax, rax
0x1800381d6  jz      short loc_18003821C
0x1800381d8  mov     r8d, 100h
0x1800381de  lea     rdx, [rsp+278h+Buffer]
0x1800381e3  mov     ecx, ebp
0x1800381e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381ea  jmp     short loc_18003821C
0x1800381ec  mov     ebp, [rbx+8]
0x1800381ef  lea     rax, [rsp+278h+Buffer]
0x1800381f4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800381f9  mov     r8d, ebp; dwMessageId
0x1800381fc  mov     [rsp+278h+nSize], 100h; nSize
0x180038204  mov     r9d, 400h; dwLanguageId
0x18003820a  xor     edx, edx; lpSource
0x18003820c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180038211  mov     ecx, 1200h; dwFlags
0x180038216  call    cs:__imp_FormatMessageW
0x18003821c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180038220  lea     rsi, [r14+rsi*2]
0x180038224  mov     rax, [rbx+88h]
0x18003822b  mov     rdx, rsi; unsigned __int16 *
0x18003822e  mov     rcx, [rbx+80h]
0x180038235  test    r9, r9
0x180038238  jz      short loc_18003825C
0x18003823a  mov     [rsp+278h+Arguments], rax
0x18003823f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180038246  mov     eax, [rbx+40h]
0x180038249  mov     qword ptr [rsp+278h+nSize], rcx
0x18003824e  mov     rcx, r14; this
0x180038251  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180038255  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003825a  jmp     short loc_180038273
0x18003825c  mov     r9, rcx; unsigned __int16 *
0x18003825f  mov     [rsp+278h+lpBuffer], rax
0x180038264  mov     rcx, r14; this
0x180038267  lea     r8, aHsP; "%hs!%p: "
0x18003826e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038273  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003827a  mov     r14, rax
0x18003827d  test    r9, r9
0x180038280  jz      short loc_180038297
0x180038282  lea     r8, aCallerP; "(caller: %p) "
0x180038289  mov     rdx, rsi; unsigned __int16 *
0x18003828c  mov     rcx, rax; this
0x18003828f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038294  mov     r14, rax
0x180038297  call    cs:__imp_GetCurrentThreadId
0x18003829d  lea     rcx, [rsp+278h+Buffer]
0x1800382a2  mov     r9, rdi; unsigned __int16 *
0x1800382a5  mov     [rsp+278h+var_240], rcx
0x1800382aa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800382b1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800382b5  mov     rdx, rsi; unsigned __int16 *
0x1800382b8  mov     [rsp+278h+nSize], eax
0x1800382bc  mov     rcx, r14; this
0x1800382bf  mov     eax, [rbx+44h]
0x1800382c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800382c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800382cb  cmp     [rbx+18h], r15
0x1800382cf  jnz     short loc_1800382E1
0x1800382d1  cmp     [rbx+48h], r15
0x1800382d5  jnz     short loc_1800382E1
0x1800382d7  cmp     [rbx+30h], r15
0x1800382db  jz      loc_180038371
0x1800382e1  lea     r8, asc_18004B020; "    "
0x1800382e8  mov     rdx, rsi; unsigned __int16 *
0x1800382eb  mov     rcx, rax; this
0x1800382ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800382f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800382f7  test    r9, r9
0x1800382fa  jz      short loc_18003830E
0x1800382fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180038303  mov     rdx, rsi; unsigned __int16 *
0x180038306  mov     rcx, rax; this
0x180038309  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003830e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180038312  test    r9, r9
0x180038315  jz      short loc_180038329
0x180038317  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003831e  mov     rdx, rsi; unsigned __int16 *
0x180038321  mov     rcx, rax; this
0x180038324  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038329  mov     rcx, [rbx+28h]
0x18003832d  mov     rdx, rsi; unsigned __int16 *
0x180038330  mov     r9, [rbx+30h]; unsigned __int16 *
0x180038334  test    rcx, rcx
0x180038337  jz      short loc_18003834F
0x180038339  mov     [rsp+278h+lpBuffer], rcx
0x18003833e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180038345  mov     rcx, rax; this
0x180038348  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003834d  jmp     short loc_180038371
0x18003834f  mov     rcx, rax; this
0x180038352  test    r9, r9
0x180038355  jz      short loc_180038365
0x180038357  lea     r8, aHs; "[%hs]\n"
0x18003835e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038363  jmp     short loc_180038371
0x180038365  lea     r8, asc_18004B0B0; "\n"
0x18003836c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038371  xor     eax, eax
0x180038373  mov     rcx, [rsp+278h+var_38]
0x18003837b  xor     rcx, rsp; StackCookie
0x18003837e  call    __security_check_cookie
0x180038383  mov     rbx, [rsp+278h+arg_18]
0x18003838b  add     rsp, 250h
0x180038392  pop     r15
0x180038394  pop     r14
0x180038396  pop     rdi
0x180038397  pop     rsi
0x180038398  pop     rbp
0x180038399  retn
```
