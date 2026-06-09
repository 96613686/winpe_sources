# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14001ede8`
- end: `0x14001f09e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140016fac`
- `0x14001ecb0`
- `0x14002e030`

## callees

- `0x14001ede8`
- `0x140025aa0`
- `0x14002dfc4`
- `0x140062c80`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001ef9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001ef9b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14001ef1a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14001ef1a`

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
          v7 = word_14007089A;
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
  memset(Buffer, 0, sizeof(Buffer));
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
0x14001ede8  mov     [rsp+arg_18], rbx
0x14001eded  push    rbp
0x14001edee  push    rsi
0x14001edef  push    rdi
0x14001edf0  push    r14
0x14001edf2  push    r15
0x14001edf4  sub     rsp, 250h
0x14001edfb  mov     rax, cs:__security_cookie
0x14001ee02  xor     rax, rsp
0x14001ee05  mov     [rsp+278h+var_38], rax
0x14001ee0d  mov     rbx, r8
0x14001ee10  mov     rsi, rdx
0x14001ee13  mov     r14, rcx
0x14001ee16  xor     r15d, r15d
0x14001ee19  test    rdx, rdx
0x14001ee1c  jz      loc_14001F075
0x14001ee22  test    rcx, rcx
0x14001ee25  jz      loc_14001F075
0x14001ee2b  mov     [rcx], r15w
0x14001ee2f  mov     rax, cs:g_pfnResultLoggingCallback
0x14001ee36  test    rax, rax
0x14001ee39  jz      short loc_14001EE5C
0x14001ee3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14001ee42  jz      short loc_14001EE5C
0x14001ee44  mov     r8, rdx
0x14001ee47  mov     rdx, rcx
0x14001ee4a  mov     rcx, rbx
0x14001ee4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ee52  cmp     [r14], r15w
0x14001ee56  jnz     loc_14001F075
0x14001ee5c  mov     ecx, [rbx]
0x14001ee5e  mov     bpl, 8
0x14001ee61  test    ecx, ecx
0x14001ee63  jz      short loc_14001EEAE
0x14001ee65  sub     ecx, 1
0x14001ee68  jz      short loc_14001EE96
0x14001ee6a  sub     ecx, 1
0x14001ee6d  jz      short loc_14001EE86
0x14001ee6f  cmp     ecx, 1
0x14001ee72  jz      short loc_14001EE7D
0x14001ee74  lea     rdi, word_14007089A
0x14001ee7b  jmp     short loc_14001EEB5
0x14001ee7d  lea     rdi, aFailfast; "FailFast"
0x14001ee84  jmp     short loc_14001EEB5
0x14001ee86  lea     rax, aLoghr; "LogHr"
0x14001ee8d  lea     rdi, aLognt; "LogNt"
0x14001ee94  jmp     short loc_14001EEA4
0x14001ee96  lea     rax, aReturnhr; "ReturnHr"
0x14001ee9d  lea     rdi, aReturnnt; "ReturnNt"
0x14001eea4  test    [rbx+4], bpl
0x14001eea8  cmovz   rdi, rax
0x14001eeac  jmp     short loc_14001EEB5
0x14001eeae  lea     rdi, aException; "Exception"
0x14001eeb5  xor     edx, edx; Val
0x14001eeb7  mov     r8d, 200h; Size
0x14001eebd  lea     rcx, [rsp+278h+Buffer]; void *
0x14001eec2  call    memset
0x14001eec7  test    [rbx+4], bpl
0x14001eecb  jz      short loc_14001EEF0
0x14001eecd  mov     ebp, [rbx+0Ch]
0x14001eed0  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14001eed7  test    rax, rax
0x14001eeda  jz      short loc_14001EF20
0x14001eedc  mov     r8d, 100h
0x14001eee2  lea     rdx, [rsp+278h+Buffer]
0x14001eee7  mov     ecx, ebp
0x14001eee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eeee  jmp     short loc_14001EF20
0x14001eef0  mov     ebp, [rbx+8]
0x14001eef3  mov     [rsp+278h+Arguments], r15; Arguments
0x14001eef8  mov     [rsp+278h+nSize], 100h; nSize
0x14001ef00  lea     rax, [rsp+278h+Buffer]
0x14001ef05  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14001ef0a  mov     r9d, 400h; dwLanguageId
0x14001ef10  mov     r8d, ebp; dwMessageId
0x14001ef13  xor     edx, edx; lpSource
0x14001ef15  mov     ecx, 1200h; dwFlags
0x14001ef1a  call    cs:__imp_FormatMessageW
0x14001ef20  lea     rsi, [r14+rsi*2]
0x14001ef24  mov     r9, [rbx+38h]; unsigned __int16 *
0x14001ef28  mov     rax, [rbx+88h]
0x14001ef2f  mov     rcx, [rbx+80h]
0x14001ef36  mov     rdx, rsi; unsigned __int16 *
0x14001ef39  test    r9, r9
0x14001ef3c  jz      short loc_14001EF60
0x14001ef3e  mov     [rsp+278h+Arguments], rax
0x14001ef43  mov     qword ptr [rsp+278h+nSize], rcx
0x14001ef48  mov     eax, [rbx+40h]
0x14001ef4b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14001ef4f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14001ef56  mov     rcx, r14; this
0x14001ef59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001ef5e  jmp     short loc_14001EF77
0x14001ef60  mov     [rsp+278h+lpBuffer], rax
0x14001ef65  mov     r9, rcx; unsigned __int16 *
0x14001ef68  lea     r8, aHsP; "%hs!%p: "
0x14001ef6f  mov     rcx, r14; this
0x14001ef72  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001ef77  mov     r14, rax
0x14001ef7a  mov     r9, [rbx+90h]; unsigned __int16 *
0x14001ef81  test    r9, r9
0x14001ef84  jz      short loc_14001EF9B
0x14001ef86  lea     r8, aCallerP; "(caller: %p) "
0x14001ef8d  mov     rdx, rsi; unsigned __int16 *
0x14001ef90  mov     rcx, rax; this
0x14001ef93  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001ef98  mov     r14, rax
0x14001ef9b  call    cs:__imp_GetCurrentThreadId
0x14001efa1  lea     rcx, [rsp+278h+Buffer]
0x14001efa6  mov     [rsp+278h+var_240], rcx
0x14001efab  mov     dword ptr [rsp+278h+Arguments], ebp
0x14001efaf  mov     [rsp+278h+nSize], eax
0x14001efb3  mov     eax, [rbx+44h]
0x14001efb6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14001efba  mov     r9, rdi; unsigned __int16 *
0x14001efbd  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14001efc4  mov     rdx, rsi; unsigned __int16 *
0x14001efc7  mov     rcx, r14; this
0x14001efca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001efcf  cmp     [rbx+18h], r15
0x14001efd3  jnz     short loc_14001EFE5
0x14001efd5  cmp     [rbx+48h], r15
0x14001efd9  jnz     short loc_14001EFE5
0x14001efdb  cmp     [rbx+30h], r15
0x14001efdf  jz      loc_14001F075
0x14001efe5  lea     r8, asc_1400714A0; "    "
0x14001efec  mov     rdx, rsi; unsigned __int16 *
0x14001efef  mov     rcx, rax; this
0x14001eff2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001eff7  mov     r9, [rbx+18h]; unsigned __int16 *
0x14001effb  test    r9, r9
0x14001effe  jz      short loc_14001F012
0x14001f000  lea     r8, aMsgWs; "Msg:[%ws] "
0x14001f007  mov     rdx, rsi; unsigned __int16 *
0x14001f00a  mov     rcx, rax; this
0x14001f00d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001f012  mov     r9, [rbx+48h]; unsigned __int16 *
0x14001f016  test    r9, r9
0x14001f019  jz      short loc_14001F02D
0x14001f01b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14001f022  mov     rdx, rsi; unsigned __int16 *
0x14001f025  mov     rcx, rax; this
0x14001f028  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001f02d  mov     rcx, [rbx+28h]
0x14001f031  mov     r9, [rbx+30h]; unsigned __int16 *
0x14001f035  mov     rdx, rsi; unsigned __int16 *
0x14001f038  test    rcx, rcx
0x14001f03b  jz      short loc_14001F053
0x14001f03d  mov     [rsp+278h+lpBuffer], rcx
0x14001f042  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14001f049  mov     rcx, rax; this
0x14001f04c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001f051  jmp     short loc_14001F075
0x14001f053  mov     rcx, rax; this
0x14001f056  test    r9, r9
0x14001f059  jz      short loc_14001F069
0x14001f05b  lea     r8, aHs; "[%hs]\n"
0x14001f062  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001f067  jmp     short loc_14001F075
0x14001f069  lea     r8, asc_140071518; "\n"
0x14001f070  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001f075  xor     eax, eax
0x14001f077  mov     rcx, [rsp+278h+var_38]
0x14001f07f  xor     rcx, rsp; StackCookie
0x14001f082  call    __security_check_cookie
0x14001f087  mov     rbx, [rsp+278h+arg_18]
0x14001f08f  add     rsp, 250h
0x14001f096  pop     r15
0x14001f098  pop     r14
0x14001f09a  pop     rdi
0x14001f09b  pop     rsi
0x14001f09c  pop     rbp
0x14001f09d  retn
```
