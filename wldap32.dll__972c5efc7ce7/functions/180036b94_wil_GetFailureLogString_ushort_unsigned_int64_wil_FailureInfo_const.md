# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180036b94`
- end: `0x180036e57`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180037490`

## callees

- `0x180033400`
- `0x180034510`
- `0x180034e6c`
- `0x180036b94`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036d4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036d4d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180036cc6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180036cc6`

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
          v8 = MultiByteStr;
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
0x180036b94  mov     [rsp+arg_18], rbx
0x180036b99  push    rbp
0x180036b9a  push    rsi
0x180036b9b  push    rdi
0x180036b9c  push    r14
0x180036b9e  push    r15
0x180036ba0  sub     rsp, 250h
0x180036ba7  mov     rax, cs:__security_cookie
0x180036bae  xor     rax, rsp
0x180036bb1  mov     [rsp+278h+var_38], rax
0x180036bb9  xor     r15d, r15d
0x180036bbc  mov     rbx, r8
0x180036bbf  mov     rsi, rdx
0x180036bc2  mov     r14, rcx
0x180036bc5  test    rdx, rdx
0x180036bc8  jz      loc_180036E2D
0x180036bce  test    rcx, rcx
0x180036bd1  jz      loc_180036E2D
0x180036bd7  mov     rax, cs:g_pfnResultLoggingCallback
0x180036bde  mov     [rcx], r15w
0x180036be2  test    rax, rax
0x180036be5  jz      short loc_180036C08
0x180036be7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180036bee  jz      short loc_180036C08
0x180036bf0  mov     r8, rdx
0x180036bf3  mov     rdx, rcx
0x180036bf6  mov     rcx, rbx
0x180036bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036bfe  cmp     [r14], r15w
0x180036c02  jnz     loc_180036E2D
0x180036c08  mov     ecx, [rbx]
0x180036c0a  mov     bpl, 8
0x180036c0d  test    ecx, ecx
0x180036c0f  jz      short loc_180036C5A
0x180036c11  sub     ecx, 1
0x180036c14  jz      short loc_180036C42
0x180036c16  sub     ecx, 1
0x180036c19  jz      short loc_180036C32
0x180036c1b  cmp     ecx, 1
0x180036c1e  jz      short loc_180036C29
0x180036c20  lea     rdi, MultiByteStr
0x180036c27  jmp     short loc_180036C61
0x180036c29  lea     rdi, aFailfast; "FailFast"
0x180036c30  jmp     short loc_180036C61
0x180036c32  lea     rax, aLoghr; "LogHr"
0x180036c39  lea     rdi, aLognt; "LogNt"
0x180036c40  jmp     short loc_180036C50
0x180036c42  lea     rax, aReturnhr; "ReturnHr"
0x180036c49  lea     rdi, aReturnnt; "ReturnNt"
0x180036c50  test    [rbx+4], bpl
0x180036c54  cmovz   rdi, rax
0x180036c58  jmp     short loc_180036C61
0x180036c5a  lea     rdi, aException; "Exception"
0x180036c61  xor     edx, edx; Val
0x180036c63  lea     rcx, [rsp+278h+Buffer]; void *
0x180036c68  mov     r8d, 200h; Size
0x180036c6e  call    memset_0
0x180036c73  test    [rbx+4], bpl
0x180036c77  jz      short loc_180036C9C
0x180036c79  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180036c80  mov     ebp, [rbx+0Ch]
0x180036c83  test    rax, rax
0x180036c86  jz      short loc_180036CD2
0x180036c88  mov     r8d, 100h
0x180036c8e  lea     rdx, [rsp+278h+Buffer]
0x180036c93  mov     ecx, ebp
0x180036c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c9a  jmp     short loc_180036CD2
0x180036c9c  mov     ebp, [rbx+8]
0x180036c9f  lea     rax, [rsp+278h+Buffer]
0x180036ca4  mov     [rsp+278h+Arguments], r15; Arguments
0x180036ca9  mov     r8d, ebp; dwMessageId
0x180036cac  mov     [rsp+278h+nSize], 100h; nSize
0x180036cb4  mov     r9d, 400h; dwLanguageId
0x180036cba  xor     edx, edx; lpSource
0x180036cbc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180036cc1  mov     ecx, 1200h; dwFlags
0x180036cc6  call    cs:__imp_FormatMessageW
0x180036ccd  nop     dword ptr [rax+rax+00h]
0x180036cd2  mov     r9, [rbx+38h]; unsigned __int16 *
0x180036cd6  lea     rsi, [r14+rsi*2]
0x180036cda  mov     rax, [rbx+88h]
0x180036ce1  mov     rdx, rsi; unsigned __int16 *
0x180036ce4  mov     rcx, [rbx+80h]
0x180036ceb  test    r9, r9
0x180036cee  jz      short loc_180036D12
0x180036cf0  mov     [rsp+278h+Arguments], rax
0x180036cf5  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180036cfc  mov     eax, [rbx+40h]
0x180036cff  mov     qword ptr [rsp+278h+nSize], rcx
0x180036d04  mov     rcx, r14; this
0x180036d07  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180036d0b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036d10  jmp     short loc_180036D29
0x180036d12  mov     r9, rcx; unsigned __int16 *
0x180036d15  mov     [rsp+278h+lpBuffer], rax
0x180036d1a  mov     rcx, r14; this
0x180036d1d  lea     r8, aHsP; "%hs!%p: "
0x180036d24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036d29  mov     r9, [rbx+90h]; unsigned __int16 *
0x180036d30  mov     r14, rax
0x180036d33  test    r9, r9
0x180036d36  jz      short loc_180036D4D
0x180036d38  lea     r8, aCallerP; "(caller: %p) "
0x180036d3f  mov     rdx, rsi; unsigned __int16 *
0x180036d42  mov     rcx, rax; this
0x180036d45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036d4a  mov     r14, rax
0x180036d4d  call    cs:__imp_GetCurrentThreadId
0x180036d54  nop     dword ptr [rax+rax+00h]
0x180036d59  lea     rcx, [rsp+278h+Buffer]
0x180036d5e  mov     r9, rdi; unsigned __int16 *
0x180036d61  mov     [rsp+278h+var_240], rcx
0x180036d66  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180036d6d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180036d71  mov     rdx, rsi; unsigned __int16 *
0x180036d74  mov     [rsp+278h+nSize], eax
0x180036d78  mov     rcx, r14; this
0x180036d7b  mov     eax, [rbx+44h]
0x180036d7e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180036d82  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036d87  cmp     [rbx+18h], r15
0x180036d8b  jnz     short loc_180036D9D
0x180036d8d  cmp     [rbx+48h], r15
0x180036d91  jnz     short loc_180036D9D
0x180036d93  cmp     [rbx+30h], r15
0x180036d97  jz      loc_180036E2D
0x180036d9d  lea     r8, asc_18004F628; "    "
0x180036da4  mov     rdx, rsi; unsigned __int16 *
0x180036da7  mov     rcx, rax; this
0x180036daa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036daf  mov     r9, [rbx+18h]; unsigned __int16 *
0x180036db3  test    r9, r9
0x180036db6  jz      short loc_180036DCA
0x180036db8  lea     r8, aMsgWs; "Msg:[%ws] "
0x180036dbf  mov     rdx, rsi; unsigned __int16 *
0x180036dc2  mov     rcx, rax; this
0x180036dc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036dca  mov     r9, [rbx+48h]; unsigned __int16 *
0x180036dce  test    r9, r9
0x180036dd1  jz      short loc_180036DE5
0x180036dd3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180036dda  mov     rdx, rsi; unsigned __int16 *
0x180036ddd  mov     rcx, rax; this
0x180036de0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036de5  mov     rcx, [rbx+28h]
0x180036de9  mov     rdx, rsi; unsigned __int16 *
0x180036dec  mov     r9, [rbx+30h]; unsigned __int16 *
0x180036df0  test    rcx, rcx
0x180036df3  jz      short loc_180036E0B
0x180036df5  mov     [rsp+278h+lpBuffer], rcx
0x180036dfa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180036e01  mov     rcx, rax; this
0x180036e04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036e09  jmp     short loc_180036E2D
0x180036e0b  mov     rcx, rax; this
0x180036e0e  test    r9, r9
0x180036e11  jz      short loc_180036E21
0x180036e13  lea     r8, aHs; "[%hs]\n"
0x180036e1a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036e1f  jmp     short loc_180036E2D
0x180036e21  lea     r8, asc_18004F6A0; "\n"
0x180036e28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036e2d  xor     eax, eax
0x180036e2f  mov     rcx, [rsp+278h+var_38]
0x180036e37  xor     rcx, rsp; StackCookie
0x180036e3a  call    __security_check_cookie
0x180036e3f  mov     rbx, [rsp+278h+arg_18]
0x180036e47  add     rsp, 250h
0x180036e4e  pop     r15
0x180036e50  pop     r14
0x180036e52  pop     rdi
0x180036e53  pop     rsi
0x180036e54  pop     rbp
0x180036e55  retn
```
