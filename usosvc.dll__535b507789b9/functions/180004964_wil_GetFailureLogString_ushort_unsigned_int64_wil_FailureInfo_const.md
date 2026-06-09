# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004964`
- end: `0x180004c1a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800034dc`
- `0x180003744`
- `0x1800052d0`
- `0x180006970`
- `0x180007078`

## callees

- `0x1800026d0`
- `0x180003198`
- `0x180004964`
- `0x1800055d0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b17`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004a96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004a96`

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
          v7 = (const char *)&word_180010AD2;
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
0x180004964  mov     [rsp+arg_18], rbx
0x180004969  push    rbp
0x18000496a  push    rsi
0x18000496b  push    rdi
0x18000496c  push    r14
0x18000496e  push    r15
0x180004970  sub     rsp, 250h
0x180004977  mov     rax, cs:__security_cookie
0x18000497e  xor     rax, rsp
0x180004981  mov     [rsp+278h+var_38], rax
0x180004989  mov     rbx, r8
0x18000498c  mov     rsi, rdx
0x18000498f  mov     r14, rcx
0x180004992  xor     r15d, r15d
0x180004995  test    rdx, rdx
0x180004998  jz      loc_180004BF1
0x18000499e  test    rcx, rcx
0x1800049a1  jz      loc_180004BF1
0x1800049a7  mov     [rcx], r15w
0x1800049ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800049b2  test    rax, rax
0x1800049b5  jz      short loc_1800049D8
0x1800049b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800049be  jz      short loc_1800049D8
0x1800049c0  mov     r8, rdx
0x1800049c3  mov     rdx, rcx
0x1800049c6  mov     rcx, rbx
0x1800049c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ce  cmp     [r14], r15w
0x1800049d2  jnz     loc_180004BF1
0x1800049d8  mov     ecx, [rbx]
0x1800049da  mov     bpl, 8
0x1800049dd  test    ecx, ecx
0x1800049df  jz      short loc_180004A2A
0x1800049e1  sub     ecx, 1
0x1800049e4  jz      short loc_180004A12
0x1800049e6  sub     ecx, 1
0x1800049e9  jz      short loc_180004A02
0x1800049eb  cmp     ecx, 1
0x1800049ee  jz      short loc_1800049F9
0x1800049f0  lea     rdi, word_180010AD2
0x1800049f7  jmp     short loc_180004A31
0x1800049f9  lea     rdi, aFailfast; "FailFast"
0x180004a00  jmp     short loc_180004A31
0x180004a02  lea     rax, aLoghr; "LogHr"
0x180004a09  lea     rdi, aLognt; "LogNt"
0x180004a10  jmp     short loc_180004A20
0x180004a12  lea     rax, aReturnhr; "ReturnHr"
0x180004a19  lea     rdi, aReturnnt; "ReturnNt"
0x180004a20  test    [rbx+4], bpl
0x180004a24  cmovz   rdi, rax
0x180004a28  jmp     short loc_180004A31
0x180004a2a  lea     rdi, aException; "Exception"
0x180004a31  xor     edx, edx; Val
0x180004a33  mov     r8d, 200h; Size
0x180004a39  lea     rcx, [rsp+278h+Buffer]; void *
0x180004a3e  call    memset_0
0x180004a43  test    [rbx+4], bpl
0x180004a47  jz      short loc_180004A6C
0x180004a49  mov     ebp, [rbx+0Ch]
0x180004a4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004a53  test    rax, rax
0x180004a56  jz      short loc_180004A9C
0x180004a58  mov     r8d, 100h
0x180004a5e  lea     rdx, [rsp+278h+Buffer]
0x180004a63  mov     ecx, ebp
0x180004a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a6a  jmp     short loc_180004A9C
0x180004a6c  mov     ebp, [rbx+8]
0x180004a6f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004a74  mov     [rsp+278h+nSize], 100h; nSize
0x180004a7c  lea     rax, [rsp+278h+Buffer]
0x180004a81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004a86  mov     r9d, 400h; dwLanguageId
0x180004a8c  mov     r8d, ebp; dwMessageId
0x180004a8f  xor     edx, edx; lpSource
0x180004a91  mov     ecx, 1200h; dwFlags
0x180004a96  call    cs:__imp_FormatMessageW
0x180004a9c  lea     rsi, [r14+rsi*2]
0x180004aa0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004aa4  mov     rax, [rbx+88h]
0x180004aab  mov     rcx, [rbx+80h]
0x180004ab2  mov     rdx, rsi; unsigned __int16 *
0x180004ab5  test    r9, r9
0x180004ab8  jz      short loc_180004ADC
0x180004aba  mov     [rsp+278h+Arguments], rax
0x180004abf  mov     qword ptr [rsp+278h+nSize], rcx
0x180004ac4  mov     eax, [rbx+40h]
0x180004ac7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004acb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004ad2  mov     rcx, r14; this
0x180004ad5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ada  jmp     short loc_180004AF3
0x180004adc  mov     [rsp+278h+lpBuffer], rax
0x180004ae1  mov     r9, rcx; unsigned __int16 *
0x180004ae4  lea     r8, aHsP; "%hs!%p: "
0x180004aeb  mov     rcx, r14; this
0x180004aee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004af3  mov     r14, rax
0x180004af6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004afd  test    r9, r9
0x180004b00  jz      short loc_180004B17
0x180004b02  lea     r8, aCallerP; "(caller: %p) "
0x180004b09  mov     rdx, rsi; unsigned __int16 *
0x180004b0c  mov     rcx, rax; this
0x180004b0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b14  mov     r14, rax
0x180004b17  call    cs:__imp_GetCurrentThreadId
0x180004b1d  lea     rcx, [rsp+278h+Buffer]
0x180004b22  mov     [rsp+278h+var_240], rcx
0x180004b27  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004b2b  mov     [rsp+278h+nSize], eax
0x180004b2f  mov     eax, [rbx+44h]
0x180004b32  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004b36  mov     r9, rdi; unsigned __int16 *
0x180004b39  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004b40  mov     rdx, rsi; unsigned __int16 *
0x180004b43  mov     rcx, r14; this
0x180004b46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b4b  cmp     [rbx+18h], r15
0x180004b4f  jnz     short loc_180004B61
0x180004b51  cmp     [rbx+48h], r15
0x180004b55  jnz     short loc_180004B61
0x180004b57  cmp     [rbx+30h], r15
0x180004b5b  jz      loc_180004BF1
0x180004b61  lea     r8, asc_180010BC0; "    "
0x180004b68  mov     rdx, rsi; unsigned __int16 *
0x180004b6b  mov     rcx, rax; this
0x180004b6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b73  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004b77  test    r9, r9
0x180004b7a  jz      short loc_180004B8E
0x180004b7c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004b83  mov     rdx, rsi; unsigned __int16 *
0x180004b86  mov     rcx, rax; this
0x180004b89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b8e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004b92  test    r9, r9
0x180004b95  jz      short loc_180004BA9
0x180004b97  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004b9e  mov     rdx, rsi; unsigned __int16 *
0x180004ba1  mov     rcx, rax; this
0x180004ba4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ba9  mov     rcx, [rbx+28h]
0x180004bad  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004bb1  mov     rdx, rsi; unsigned __int16 *
0x180004bb4  test    rcx, rcx
0x180004bb7  jz      short loc_180004BCF
0x180004bb9  mov     [rsp+278h+lpBuffer], rcx
0x180004bbe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004bc5  mov     rcx, rax; this
0x180004bc8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bcd  jmp     short loc_180004BF1
0x180004bcf  mov     rcx, rax; this
0x180004bd2  test    r9, r9
0x180004bd5  jz      short loc_180004BE5
0x180004bd7  lea     r8, aHs; "[%hs]\n"
0x180004bde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004be3  jmp     short loc_180004BF1
0x180004be5  lea     r8, asc_180010C38; "\n"
0x180004bec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bf1  xor     eax, eax
0x180004bf3  mov     rcx, [rsp+278h+var_38]
0x180004bfb  xor     rcx, rsp; StackCookie
0x180004bfe  call    __security_check_cookie
0x180004c03  mov     rbx, [rsp+278h+arg_18]
0x180004c0b  add     rsp, 250h
0x180004c12  pop     r15
0x180004c14  pop     r14
0x180004c16  pop     rdi
0x180004c17  pop     rsi
0x180004c18  pop     rbp
0x180004c19  retn
```
