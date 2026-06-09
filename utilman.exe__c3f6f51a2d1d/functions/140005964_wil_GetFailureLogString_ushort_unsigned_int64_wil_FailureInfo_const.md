# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005964`
- end: `0x140005c27`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140003cf8`
- `0x140006668`
- `0x140006dc8`
- `0x140009f00`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x140005964`
- `0x14000697c`
- `0x140029010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005b1d`
- `KERNEL32!GetCurrentThreadId` at `0x140005b1d`
- `KERNEL32!FormatMessageW` at `0x140005a96`
- `KERNEL32!FormatMessageW` at `0x140005a96`

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
          v7 = (const char *)&byte_14002C58F;
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
0x140005964  mov     [rsp+arg_18], rbx
0x140005969  push    rbp
0x14000596a  push    rsi
0x14000596b  push    rdi
0x14000596c  push    r14
0x14000596e  push    r15
0x140005970  sub     rsp, 250h
0x140005977  mov     rax, cs:__security_cookie
0x14000597e  xor     rax, rsp
0x140005981  mov     [rsp+278h+var_38], rax
0x140005989  mov     rbx, r8
0x14000598c  mov     rsi, rdx
0x14000598f  mov     r14, rcx
0x140005992  xor     r15d, r15d
0x140005995  test    rdx, rdx
0x140005998  jz      loc_140005BFD
0x14000599e  test    rcx, rcx
0x1400059a1  jz      loc_140005BFD
0x1400059a7  mov     [rcx], r15w
0x1400059ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1400059b2  test    rax, rax
0x1400059b5  jz      short loc_1400059D8
0x1400059b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400059be  jz      short loc_1400059D8
0x1400059c0  mov     r8, rdx
0x1400059c3  mov     rdx, rcx
0x1400059c6  mov     rcx, rbx
0x1400059c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059ce  cmp     [r14], r15w
0x1400059d2  jnz     loc_140005BFD
0x1400059d8  mov     ecx, [rbx]
0x1400059da  mov     bpl, 8
0x1400059dd  test    ecx, ecx
0x1400059df  jz      short loc_140005A2A
0x1400059e1  sub     ecx, 1
0x1400059e4  jz      short loc_140005A12
0x1400059e6  sub     ecx, 1
0x1400059e9  jz      short loc_140005A02
0x1400059eb  cmp     ecx, 1
0x1400059ee  jz      short loc_1400059F9
0x1400059f0  lea     rdi, byte_14002C58F
0x1400059f7  jmp     short loc_140005A31
0x1400059f9  lea     rdi, aFailfast; "FailFast"
0x140005a00  jmp     short loc_140005A31
0x140005a02  lea     rax, aLoghr; "LogHr"
0x140005a09  lea     rdi, aLognt; "LogNt"
0x140005a10  jmp     short loc_140005A20
0x140005a12  lea     rax, aReturnhr; "ReturnHr"
0x140005a19  lea     rdi, aReturnnt; "ReturnNt"
0x140005a20  test    [rbx+4], bpl
0x140005a24  cmovz   rdi, rax
0x140005a28  jmp     short loc_140005A31
0x140005a2a  lea     rdi, aException; "Exception"
0x140005a31  xor     edx, edx; Val
0x140005a33  mov     r8d, 200h; Size
0x140005a39  lea     rcx, [rsp+278h+Buffer]; void *
0x140005a3e  call    memset_0
0x140005a43  test    [rbx+4], bpl
0x140005a47  jz      short loc_140005A6C
0x140005a49  mov     ebp, [rbx+0Ch]
0x140005a4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005a53  test    rax, rax
0x140005a56  jz      short loc_140005AA2
0x140005a58  mov     r8d, 100h
0x140005a5e  lea     rdx, [rsp+278h+Buffer]
0x140005a63  mov     ecx, ebp
0x140005a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a6a  jmp     short loc_140005AA2
0x140005a6c  mov     ebp, [rbx+8]
0x140005a6f  mov     [rsp+278h+Arguments], r15; Arguments
0x140005a74  mov     [rsp+278h+nSize], 100h; nSize
0x140005a7c  lea     rax, [rsp+278h+Buffer]
0x140005a81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005a86  mov     r9d, 400h; dwLanguageId
0x140005a8c  mov     r8d, ebp; dwMessageId
0x140005a8f  xor     edx, edx; lpSource
0x140005a91  mov     ecx, 1200h; dwFlags
0x140005a96  call    cs:__imp_FormatMessageW
0x140005a9d  nop     dword ptr [rax+rax+00h]
0x140005aa2  lea     rsi, [r14+rsi*2]
0x140005aa6  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005aaa  mov     rax, [rbx+88h]
0x140005ab1  mov     rcx, [rbx+80h]
0x140005ab8  mov     rdx, rsi; unsigned __int16 *
0x140005abb  test    r9, r9
0x140005abe  jz      short loc_140005AE2
0x140005ac0  mov     [rsp+278h+Arguments], rax
0x140005ac5  mov     qword ptr [rsp+278h+nSize], rcx
0x140005aca  mov     eax, [rbx+40h]
0x140005acd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005ad1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005ad8  mov     rcx, r14; this
0x140005adb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005ae0  jmp     short loc_140005AF9
0x140005ae2  mov     [rsp+278h+lpBuffer], rax
0x140005ae7  mov     r9, rcx; unsigned __int16 *
0x140005aea  lea     r8, aHsP; "%hs!%p: "
0x140005af1  mov     rcx, r14; this
0x140005af4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005af9  mov     r14, rax
0x140005afc  mov     r9, [rbx+90h]; unsigned __int16 *
0x140005b03  test    r9, r9
0x140005b06  jz      short loc_140005B1D
0x140005b08  lea     r8, aCallerP; "(caller: %p) "
0x140005b0f  mov     rdx, rsi; unsigned __int16 *
0x140005b12  mov     rcx, rax; this
0x140005b15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005b1a  mov     r14, rax
0x140005b1d  call    cs:__imp_GetCurrentThreadId
0x140005b24  nop     dword ptr [rax+rax+00h]
0x140005b29  lea     rcx, [rsp+278h+Buffer]
0x140005b2e  mov     [rsp+278h+var_240], rcx
0x140005b33  mov     dword ptr [rsp+278h+Arguments], ebp
0x140005b37  mov     [rsp+278h+nSize], eax
0x140005b3b  mov     eax, [rbx+44h]
0x140005b3e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005b42  mov     r9, rdi; unsigned __int16 *
0x140005b45  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005b4c  mov     rdx, rsi; unsigned __int16 *
0x140005b4f  mov     rcx, r14; this
0x140005b52  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005b57  cmp     [rbx+18h], r15
0x140005b5b  jnz     short loc_140005B6D
0x140005b5d  cmp     [rbx+48h], r15
0x140005b61  jnz     short loc_140005B6D
0x140005b63  cmp     [rbx+30h], r15
0x140005b67  jz      loc_140005BFD
0x140005b6d  lea     r8, asc_14002C680; "    "
0x140005b74  mov     rdx, rsi; unsigned __int16 *
0x140005b77  mov     rcx, rax; this
0x140005b7a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005b7f  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005b83  test    r9, r9
0x140005b86  jz      short loc_140005B9A
0x140005b88  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005b8f  mov     rdx, rsi; unsigned __int16 *
0x140005b92  mov     rcx, rax; this
0x140005b95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005b9a  mov     r9, [rbx+48h]; unsigned __int16 *
0x140005b9e  test    r9, r9
0x140005ba1  jz      short loc_140005BB5
0x140005ba3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140005baa  mov     rdx, rsi; unsigned __int16 *
0x140005bad  mov     rcx, rax; this
0x140005bb0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005bb5  mov     rcx, [rbx+28h]
0x140005bb9  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005bbd  mov     rdx, rsi; unsigned __int16 *
0x140005bc0  test    rcx, rcx
0x140005bc3  jz      short loc_140005BDB
0x140005bc5  mov     [rsp+278h+lpBuffer], rcx
0x140005bca  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005bd1  mov     rcx, rax; this
0x140005bd4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005bd9  jmp     short loc_140005BFD
0x140005bdb  mov     rcx, rax; this
0x140005bde  test    r9, r9
0x140005be1  jz      short loc_140005BF1
0x140005be3  lea     r8, aHs; "[%hs]\n"
0x140005bea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005bef  jmp     short loc_140005BFD
0x140005bf1  lea     r8, asc_14002C6F8; "\n"
0x140005bf8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005bfd  xor     eax, eax
0x140005bff  mov     rcx, [rsp+278h+var_38]
0x140005c07  xor     rcx, rsp; StackCookie
0x140005c0a  call    __security_check_cookie
0x140005c0f  mov     rbx, [rsp+278h+arg_18]
0x140005c17  add     rsp, 250h
0x140005c1e  pop     r15
0x140005c20  pop     r14
0x140005c22  pop     rdi
0x140005c23  pop     rsi
0x140005c24  pop     rbp
0x140005c25  retn
```
