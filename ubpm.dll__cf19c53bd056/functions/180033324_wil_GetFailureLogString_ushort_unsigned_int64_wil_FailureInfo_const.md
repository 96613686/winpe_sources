# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180033324`
- end: `0x1800335da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800338e0`

## callees

- `0x180033324`
- `0x180033bdc`
- `0x18003d7de`
- `0x18003d810`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800334d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800334d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180033456`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180033456`

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
          v8 = (const char *)&qword_180041748;
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
0x180033324  mov     [rsp+arg_18], rbx
0x180033329  push    rbp
0x18003332a  push    rsi
0x18003332b  push    rdi
0x18003332c  push    r14
0x18003332e  push    r15
0x180033330  sub     rsp, 250h
0x180033337  mov     rax, cs:__security_cookie
0x18003333e  xor     rax, rsp
0x180033341  mov     [rsp+278h+var_38], rax
0x180033349  xor     r15d, r15d
0x18003334c  mov     rbx, r8
0x18003334f  mov     rsi, rdx
0x180033352  mov     r14, rcx
0x180033355  test    rdx, rdx
0x180033358  jz      loc_1800335B1
0x18003335e  test    rcx, rcx
0x180033361  jz      loc_1800335B1
0x180033367  mov     rax, cs:g_pfnResultLoggingCallback
0x18003336e  mov     [rcx], r15w
0x180033372  test    rax, rax
0x180033375  jz      short loc_180033398
0x180033377  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003337e  jz      short loc_180033398
0x180033380  mov     r8, rdx
0x180033383  mov     rdx, rcx
0x180033386  mov     rcx, rbx
0x180033389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003338e  cmp     [r14], r15w
0x180033392  jnz     loc_1800335B1
0x180033398  mov     ecx, [rbx]
0x18003339a  mov     bpl, 8
0x18003339d  test    ecx, ecx
0x18003339f  jz      short loc_1800333EA
0x1800333a1  sub     ecx, 1
0x1800333a4  jz      short loc_1800333D2
0x1800333a6  sub     ecx, 1
0x1800333a9  jz      short loc_1800333C2
0x1800333ab  cmp     ecx, 1
0x1800333ae  jz      short loc_1800333B9
0x1800333b0  lea     rdi, qword_180041748
0x1800333b7  jmp     short loc_1800333F1
0x1800333b9  lea     rdi, aFailfast; "FailFast"
0x1800333c0  jmp     short loc_1800333F1
0x1800333c2  lea     rax, aLoghr; "LogHr"
0x1800333c9  lea     rdi, aLognt; "LogNt"
0x1800333d0  jmp     short loc_1800333E0
0x1800333d2  lea     rax, aReturnhr; "ReturnHr"
0x1800333d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800333e0  test    [rbx+4], bpl
0x1800333e4  cmovz   rdi, rax
0x1800333e8  jmp     short loc_1800333F1
0x1800333ea  lea     rdi, aException; "Exception"
0x1800333f1  xor     edx, edx; Val
0x1800333f3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800333f8  mov     r8d, 200h; Size
0x1800333fe  call    memset_0
0x180033403  test    [rbx+4], bpl
0x180033407  jz      short loc_18003342C
0x180033409  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180033410  mov     ebp, [rbx+0Ch]
0x180033413  test    rax, rax
0x180033416  jz      short loc_18003345C
0x180033418  mov     r8d, 100h
0x18003341e  lea     rdx, [rsp+278h+Buffer]
0x180033423  mov     ecx, ebp
0x180033425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003342a  jmp     short loc_18003345C
0x18003342c  mov     ebp, [rbx+8]
0x18003342f  lea     rax, [rsp+278h+Buffer]
0x180033434  mov     [rsp+278h+Arguments], r15; Arguments
0x180033439  mov     r8d, ebp; dwMessageId
0x18003343c  mov     [rsp+278h+nSize], 100h; nSize
0x180033444  mov     r9d, 400h; dwLanguageId
0x18003344a  xor     edx, edx; lpSource
0x18003344c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180033451  mov     ecx, 1200h; dwFlags
0x180033456  call    cs:__imp_FormatMessageW
0x18003345c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180033460  lea     rsi, [r14+rsi*2]
0x180033464  mov     rax, [rbx+88h]
0x18003346b  mov     rdx, rsi; unsigned __int16 *
0x18003346e  mov     rcx, [rbx+80h]
0x180033475  test    r9, r9
0x180033478  jz      short loc_18003349C
0x18003347a  mov     [rsp+278h+Arguments], rax
0x18003347f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180033486  mov     eax, [rbx+40h]
0x180033489  mov     qword ptr [rsp+278h+nSize], rcx
0x18003348e  mov     rcx, r14; this
0x180033491  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180033495  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003349a  jmp     short loc_1800334B3
0x18003349c  mov     r9, rcx; unsigned __int16 *
0x18003349f  mov     [rsp+278h+lpBuffer], rax
0x1800334a4  mov     rcx, r14; this
0x1800334a7  lea     r8, aHsP; "%hs!%p: "
0x1800334ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800334b3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800334ba  mov     r14, rax
0x1800334bd  test    r9, r9
0x1800334c0  jz      short loc_1800334D7
0x1800334c2  lea     r8, aCallerP; "(caller: %p) "
0x1800334c9  mov     rdx, rsi; unsigned __int16 *
0x1800334cc  mov     rcx, rax; this
0x1800334cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800334d4  mov     r14, rax
0x1800334d7  call    cs:__imp_GetCurrentThreadId
0x1800334dd  lea     rcx, [rsp+278h+Buffer]
0x1800334e2  mov     r9, rdi; unsigned __int16 *
0x1800334e5  mov     [rsp+278h+var_240], rcx
0x1800334ea  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800334f1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800334f5  mov     rdx, rsi; unsigned __int16 *
0x1800334f8  mov     [rsp+278h+nSize], eax
0x1800334fc  mov     rcx, r14; this
0x1800334ff  mov     eax, [rbx+44h]
0x180033502  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180033506  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003350b  cmp     [rbx+18h], r15
0x18003350f  jnz     short loc_180033521
0x180033511  cmp     [rbx+48h], r15
0x180033515  jnz     short loc_180033521
0x180033517  cmp     [rbx+30h], r15
0x18003351b  jz      loc_1800335B1
0x180033521  lea     r8, asc_180041838; "    "
0x180033528  mov     rdx, rsi; unsigned __int16 *
0x18003352b  mov     rcx, rax; this
0x18003352e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180033533  mov     r9, [rbx+18h]; unsigned __int16 *
0x180033537  test    r9, r9
0x18003353a  jz      short loc_18003354E
0x18003353c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180033543  mov     rdx, rsi; unsigned __int16 *
0x180033546  mov     rcx, rax; this
0x180033549  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003354e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180033552  test    r9, r9
0x180033555  jz      short loc_180033569
0x180033557  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003355e  mov     rdx, rsi; unsigned __int16 *
0x180033561  mov     rcx, rax; this
0x180033564  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180033569  mov     rcx, [rbx+28h]
0x18003356d  mov     rdx, rsi; unsigned __int16 *
0x180033570  mov     r9, [rbx+30h]; unsigned __int16 *
0x180033574  test    rcx, rcx
0x180033577  jz      short loc_18003358F
0x180033579  mov     [rsp+278h+lpBuffer], rcx
0x18003357e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180033585  mov     rcx, rax; this
0x180033588  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003358d  jmp     short loc_1800335B1
0x18003358f  mov     rcx, rax; this
0x180033592  test    r9, r9
0x180033595  jz      short loc_1800335A5
0x180033597  lea     r8, aHs; "[%hs]\n"
0x18003359e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800335a3  jmp     short loc_1800335B1
0x1800335a5  lea     r8, asc_1800418B0; "\n"
0x1800335ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800335b1  xor     eax, eax
0x1800335b3  mov     rcx, [rsp+278h+var_38]
0x1800335bb  xor     rcx, rsp; StackCookie
0x1800335be  call    __security_check_cookie
0x1800335c3  mov     rbx, [rsp+278h+arg_18]
0x1800335cb  add     rsp, 250h
0x1800335d2  pop     r15
0x1800335d4  pop     r14
0x1800335d6  pop     rdi
0x1800335d7  pop     rsi
0x1800335d8  pop     rbp
0x1800335d9  retn
```
