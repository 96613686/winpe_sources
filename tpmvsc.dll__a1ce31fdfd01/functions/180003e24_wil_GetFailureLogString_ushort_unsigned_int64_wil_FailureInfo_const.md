# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003e24`
- end: `0x1800040da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002fac`
- `0x1800047bc`
- `0x180004c74`
- `0x180005dc0`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x180003e24`
- `0x180004abc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fd7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003f56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003f56`

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
          v7 = (const char *)&qword_180039CE8;
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
0x180003e24  mov     [rsp+arg_18], rbx
0x180003e29  push    rbp
0x180003e2a  push    rsi
0x180003e2b  push    rdi
0x180003e2c  push    r14
0x180003e2e  push    r15
0x180003e30  sub     rsp, 250h
0x180003e37  mov     rax, cs:__security_cookie
0x180003e3e  xor     rax, rsp
0x180003e41  mov     [rsp+278h+var_38], rax
0x180003e49  mov     rbx, r8
0x180003e4c  mov     rsi, rdx
0x180003e4f  mov     r14, rcx
0x180003e52  xor     r15d, r15d
0x180003e55  test    rdx, rdx
0x180003e58  jz      loc_1800040B1
0x180003e5e  test    rcx, rcx
0x180003e61  jz      loc_1800040B1
0x180003e67  mov     [rcx], r15w
0x180003e6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003e72  test    rax, rax
0x180003e75  jz      short loc_180003E98
0x180003e77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003e7e  jz      short loc_180003E98
0x180003e80  mov     r8, rdx
0x180003e83  mov     rdx, rcx
0x180003e86  mov     rcx, rbx
0x180003e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e8e  cmp     [r14], r15w
0x180003e92  jnz     loc_1800040B1
0x180003e98  mov     ecx, [rbx]
0x180003e9a  mov     bpl, 8
0x180003e9d  test    ecx, ecx
0x180003e9f  jz      short loc_180003EEA
0x180003ea1  sub     ecx, 1
0x180003ea4  jz      short loc_180003ED2
0x180003ea6  sub     ecx, 1
0x180003ea9  jz      short loc_180003EC2
0x180003eab  cmp     ecx, 1
0x180003eae  jz      short loc_180003EB9
0x180003eb0  lea     rdi, qword_180039CE8
0x180003eb7  jmp     short loc_180003EF1
0x180003eb9  lea     rdi, aFailfast; "FailFast"
0x180003ec0  jmp     short loc_180003EF1
0x180003ec2  lea     rax, aLoghr; "LogHr"
0x180003ec9  lea     rdi, aLognt; "LogNt"
0x180003ed0  jmp     short loc_180003EE0
0x180003ed2  lea     rax, aReturnhr; "ReturnHr"
0x180003ed9  lea     rdi, aReturnnt; "ReturnNt"
0x180003ee0  test    [rbx+4], bpl
0x180003ee4  cmovz   rdi, rax
0x180003ee8  jmp     short loc_180003EF1
0x180003eea  lea     rdi, aException; "Exception"
0x180003ef1  xor     edx, edx; Val
0x180003ef3  mov     r8d, 200h; Size
0x180003ef9  lea     rcx, [rsp+278h+Buffer]; void *
0x180003efe  call    memset_0
0x180003f03  test    [rbx+4], bpl
0x180003f07  jz      short loc_180003F2C
0x180003f09  mov     ebp, [rbx+0Ch]
0x180003f0c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003f13  test    rax, rax
0x180003f16  jz      short loc_180003F5C
0x180003f18  mov     r8d, 100h
0x180003f1e  lea     rdx, [rsp+278h+Buffer]
0x180003f23  mov     ecx, ebp
0x180003f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f2a  jmp     short loc_180003F5C
0x180003f2c  mov     ebp, [rbx+8]
0x180003f2f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003f34  mov     [rsp+278h+nSize], 100h; nSize
0x180003f3c  lea     rax, [rsp+278h+Buffer]
0x180003f41  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003f46  mov     r9d, 400h; dwLanguageId
0x180003f4c  mov     r8d, ebp; dwMessageId
0x180003f4f  xor     edx, edx; lpSource
0x180003f51  mov     ecx, 1200h; dwFlags
0x180003f56  call    cs:__imp_FormatMessageW
0x180003f5c  lea     rsi, [r14+rsi*2]
0x180003f60  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003f64  mov     rax, [rbx+88h]
0x180003f6b  mov     rcx, [rbx+80h]
0x180003f72  mov     rdx, rsi; unsigned __int16 *
0x180003f75  test    r9, r9
0x180003f78  jz      short loc_180003F9C
0x180003f7a  mov     [rsp+278h+Arguments], rax
0x180003f7f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003f84  mov     eax, [rbx+40h]
0x180003f87  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003f8b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003f92  mov     rcx, r14; this
0x180003f95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f9a  jmp     short loc_180003FB3
0x180003f9c  mov     [rsp+278h+lpBuffer], rax
0x180003fa1  mov     r9, rcx; unsigned __int16 *
0x180003fa4  lea     r8, aHsP; "%hs!%p: "
0x180003fab  mov     rcx, r14; this
0x180003fae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003fb3  mov     r14, rax
0x180003fb6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003fbd  test    r9, r9
0x180003fc0  jz      short loc_180003FD7
0x180003fc2  lea     r8, aCallerP; "(caller: %p) "
0x180003fc9  mov     rdx, rsi; unsigned __int16 *
0x180003fcc  mov     rcx, rax; this
0x180003fcf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003fd4  mov     r14, rax
0x180003fd7  call    cs:__imp_GetCurrentThreadId
0x180003fdd  lea     rcx, [rsp+278h+Buffer]
0x180003fe2  mov     [rsp+278h+var_240], rcx
0x180003fe7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003feb  mov     [rsp+278h+nSize], eax
0x180003fef  mov     eax, [rbx+44h]
0x180003ff2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003ff6  mov     r9, rdi; unsigned __int16 *
0x180003ff9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004000  mov     rdx, rsi; unsigned __int16 *
0x180004003  mov     rcx, r14; this
0x180004006  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000400b  cmp     [rbx+18h], r15
0x18000400f  jnz     short loc_180004021
0x180004011  cmp     [rbx+48h], r15
0x180004015  jnz     short loc_180004021
0x180004017  cmp     [rbx+30h], r15
0x18000401b  jz      loc_1800040B1
0x180004021  lea     r8, asc_180039DF0; "    "
0x180004028  mov     rdx, rsi; unsigned __int16 *
0x18000402b  mov     rcx, rax; this
0x18000402e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004033  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004037  test    r9, r9
0x18000403a  jz      short loc_18000404E
0x18000403c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004043  mov     rdx, rsi; unsigned __int16 *
0x180004046  mov     rcx, rax; this
0x180004049  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000404e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004052  test    r9, r9
0x180004055  jz      short loc_180004069
0x180004057  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000405e  mov     rdx, rsi; unsigned __int16 *
0x180004061  mov     rcx, rax; this
0x180004064  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004069  mov     rcx, [rbx+28h]
0x18000406d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004071  mov     rdx, rsi; unsigned __int16 *
0x180004074  test    rcx, rcx
0x180004077  jz      short loc_18000408F
0x180004079  mov     [rsp+278h+lpBuffer], rcx
0x18000407e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004085  mov     rcx, rax; this
0x180004088  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000408d  jmp     short loc_1800040B1
0x18000408f  mov     rcx, rax; this
0x180004092  test    r9, r9
0x180004095  jz      short loc_1800040A5
0x180004097  lea     r8, aHs; "[%hs]\n"
0x18000409e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800040a3  jmp     short loc_1800040B1
0x1800040a5  lea     r8, asc_180039E68; "\n"
0x1800040ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800040b1  xor     eax, eax
0x1800040b3  mov     rcx, [rsp+278h+var_38]
0x1800040bb  xor     rcx, rsp; StackCookie
0x1800040be  call    __security_check_cookie
0x1800040c3  mov     rbx, [rsp+278h+arg_18]
0x1800040cb  add     rsp, 250h
0x1800040d2  pop     r15
0x1800040d4  pop     r14
0x1800040d6  pop     rdi
0x1800040d7  pop     rsi
0x1800040d8  pop     rbp
0x1800040d9  retn
```
