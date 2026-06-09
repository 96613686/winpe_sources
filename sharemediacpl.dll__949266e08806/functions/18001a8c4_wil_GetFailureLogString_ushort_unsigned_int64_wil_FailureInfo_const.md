# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001a8c4`
- end: `0x18001ab7a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800191f0`
- `0x180019460`
- `0x18001b220`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x18001a8c4`
- `0x18001b520`
- `0x18001e010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18001a9f6`
- `KERNEL32!FormatMessageW` at `0x18001a9f6`
- `KERNEL32!GetCurrentThreadId` at `0x18001aa77`
- `KERNEL32!GetCurrentThreadId` at `0x18001aa77`

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
          v8 = (const char *)&byte_180023D80;
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
0x18001a8c4  mov     [rsp+arg_18], rbx
0x18001a8c9  push    rbp
0x18001a8ca  push    rsi
0x18001a8cb  push    rdi
0x18001a8cc  push    r14
0x18001a8ce  push    r15
0x18001a8d0  sub     rsp, 250h
0x18001a8d7  mov     rax, cs:__security_cookie
0x18001a8de  xor     rax, rsp
0x18001a8e1  mov     [rsp+278h+var_38], rax
0x18001a8e9  xor     r15d, r15d
0x18001a8ec  mov     rbx, r8
0x18001a8ef  mov     rsi, rdx
0x18001a8f2  mov     r14, rcx
0x18001a8f5  test    rdx, rdx
0x18001a8f8  jz      loc_18001AB51
0x18001a8fe  test    rcx, rcx
0x18001a901  jz      loc_18001AB51
0x18001a907  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a90e  mov     [rcx], r15w
0x18001a912  test    rax, rax
0x18001a915  jz      short loc_18001A938
0x18001a917  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001a91e  jz      short loc_18001A938
0x18001a920  mov     r8, rdx
0x18001a923  mov     rdx, rcx
0x18001a926  mov     rcx, rbx
0x18001a929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a92e  cmp     [r14], r15w
0x18001a932  jnz     loc_18001AB51
0x18001a938  mov     ecx, [rbx]
0x18001a93a  mov     bpl, 8
0x18001a93d  test    ecx, ecx
0x18001a93f  jz      short loc_18001A98A
0x18001a941  sub     ecx, 1
0x18001a944  jz      short loc_18001A972
0x18001a946  sub     ecx, 1
0x18001a949  jz      short loc_18001A962
0x18001a94b  cmp     ecx, 1
0x18001a94e  jz      short loc_18001A959
0x18001a950  lea     rdi, byte_180023D80
0x18001a957  jmp     short loc_18001A991
0x18001a959  lea     rdi, aFailfast; "FailFast"
0x18001a960  jmp     short loc_18001A991
0x18001a962  lea     rax, aLoghr; "LogHr"
0x18001a969  lea     rdi, aLognt; "LogNt"
0x18001a970  jmp     short loc_18001A980
0x18001a972  lea     rax, aReturnhr; "ReturnHr"
0x18001a979  lea     rdi, aReturnnt; "ReturnNt"
0x18001a980  test    [rbx+4], bpl
0x18001a984  cmovz   rdi, rax
0x18001a988  jmp     short loc_18001A991
0x18001a98a  lea     rdi, aException; "Exception"
0x18001a991  xor     edx, edx; Val
0x18001a993  lea     rcx, [rsp+278h+Buffer]; void *
0x18001a998  mov     r8d, 200h; Size
0x18001a99e  call    memset_0
0x18001a9a3  test    [rbx+4], bpl
0x18001a9a7  jz      short loc_18001A9CC
0x18001a9a9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001a9b0  mov     ebp, [rbx+0Ch]
0x18001a9b3  test    rax, rax
0x18001a9b6  jz      short loc_18001A9FC
0x18001a9b8  mov     r8d, 100h
0x18001a9be  lea     rdx, [rsp+278h+Buffer]
0x18001a9c3  mov     ecx, ebp
0x18001a9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9ca  jmp     short loc_18001A9FC
0x18001a9cc  mov     ebp, [rbx+8]
0x18001a9cf  lea     rax, [rsp+278h+Buffer]
0x18001a9d4  mov     [rsp+278h+Arguments], r15; Arguments
0x18001a9d9  mov     r8d, ebp; dwMessageId
0x18001a9dc  mov     [rsp+278h+nSize], 100h; nSize
0x18001a9e4  mov     r9d, 400h; dwLanguageId
0x18001a9ea  xor     edx, edx; lpSource
0x18001a9ec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001a9f1  mov     ecx, 1200h; dwFlags
0x18001a9f6  call    cs:__imp_FormatMessageW
0x18001a9fc  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001aa00  lea     rsi, [r14+rsi*2]
0x18001aa04  mov     rax, [rbx+88h]
0x18001aa0b  mov     rdx, rsi; unsigned __int16 *
0x18001aa0e  mov     rcx, [rbx+80h]
0x18001aa15  test    r9, r9
0x18001aa18  jz      short loc_18001AA3C
0x18001aa1a  mov     [rsp+278h+Arguments], rax
0x18001aa1f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001aa26  mov     eax, [rbx+40h]
0x18001aa29  mov     qword ptr [rsp+278h+nSize], rcx
0x18001aa2e  mov     rcx, r14; this
0x18001aa31  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001aa35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001aa3a  jmp     short loc_18001AA53
0x18001aa3c  mov     r9, rcx; unsigned __int16 *
0x18001aa3f  mov     [rsp+278h+lpBuffer], rax
0x18001aa44  mov     rcx, r14; this
0x18001aa47  lea     r8, aHsP; "%hs!%p: "
0x18001aa4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001aa53  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001aa5a  mov     r14, rax
0x18001aa5d  test    r9, r9
0x18001aa60  jz      short loc_18001AA77
0x18001aa62  lea     r8, aCallerP; "(caller: %p) "
0x18001aa69  mov     rdx, rsi; unsigned __int16 *
0x18001aa6c  mov     rcx, rax; this
0x18001aa6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001aa74  mov     r14, rax
0x18001aa77  call    cs:__imp_GetCurrentThreadId
0x18001aa7d  lea     rcx, [rsp+278h+Buffer]
0x18001aa82  mov     r9, rdi; unsigned __int16 *
0x18001aa85  mov     [rsp+278h+var_240], rcx
0x18001aa8a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001aa91  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001aa95  mov     rdx, rsi; unsigned __int16 *
0x18001aa98  mov     [rsp+278h+nSize], eax
0x18001aa9c  mov     rcx, r14; this
0x18001aa9f  mov     eax, [rbx+44h]
0x18001aaa2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001aaa6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001aaab  cmp     [rbx+18h], r15
0x18001aaaf  jnz     short loc_18001AAC1
0x18001aab1  cmp     [rbx+48h], r15
0x18001aab5  jnz     short loc_18001AAC1
0x18001aab7  cmp     [rbx+30h], r15
0x18001aabb  jz      loc_18001AB51
0x18001aac1  lea     r8, asc_1800239F8; "    "
0x18001aac8  mov     rdx, rsi; unsigned __int16 *
0x18001aacb  mov     rcx, rax; this
0x18001aace  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001aad3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001aad7  test    r9, r9
0x18001aada  jz      short loc_18001AAEE
0x18001aadc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001aae3  mov     rdx, rsi; unsigned __int16 *
0x18001aae6  mov     rcx, rax; this
0x18001aae9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001aaee  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001aaf2  test    r9, r9
0x18001aaf5  jz      short loc_18001AB09
0x18001aaf7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001aafe  mov     rdx, rsi; unsigned __int16 *
0x18001ab01  mov     rcx, rax; this
0x18001ab04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ab09  mov     rcx, [rbx+28h]
0x18001ab0d  mov     rdx, rsi; unsigned __int16 *
0x18001ab10  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001ab14  test    rcx, rcx
0x18001ab17  jz      short loc_18001AB2F
0x18001ab19  mov     [rsp+278h+lpBuffer], rcx
0x18001ab1e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001ab25  mov     rcx, rax; this
0x18001ab28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ab2d  jmp     short loc_18001AB51
0x18001ab2f  mov     rcx, rax; this
0x18001ab32  test    r9, r9
0x18001ab35  jz      short loc_18001AB45
0x18001ab37  lea     r8, aHs; "[%hs]\n"
0x18001ab3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ab43  jmp     short loc_18001AB51
0x18001ab45  lea     r8, asc_180023A70; "\n"
0x18001ab4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ab51  xor     eax, eax
0x18001ab53  mov     rcx, [rsp+278h+var_38]
0x18001ab5b  xor     rcx, rsp; StackCookie
0x18001ab5e  call    __security_check_cookie
0x18001ab63  mov     rbx, [rsp+278h+arg_18]
0x18001ab6b  add     rsp, 250h
0x18001ab72  pop     r15
0x18001ab74  pop     r14
0x18001ab76  pop     rdi
0x18001ab77  pop     rsi
0x18001ab78  pop     rbp
0x18001ab79  retn
```
