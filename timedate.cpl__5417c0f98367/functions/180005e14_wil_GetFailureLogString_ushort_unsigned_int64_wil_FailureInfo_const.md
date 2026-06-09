# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005e14`
- end: `0x1800060ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800048ac`
- `0x180006a84`

## callees

- `0x180005e14`
- `0x180006d88`
- `0x180028f2e`
- `0x180028f60`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005f46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005f46`

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
          v8 = (const char *)&word_18002E916;
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
0x180005e14  mov     [rsp+arg_18], rbx
0x180005e19  push    rbp
0x180005e1a  push    rsi
0x180005e1b  push    rdi
0x180005e1c  push    r14
0x180005e1e  push    r15
0x180005e20  sub     rsp, 250h
0x180005e27  mov     rax, cs:__security_cookie
0x180005e2e  xor     rax, rsp
0x180005e31  mov     [rsp+278h+var_38], rax
0x180005e39  xor     r15d, r15d
0x180005e3c  mov     rbx, r8
0x180005e3f  mov     rsi, rdx
0x180005e42  mov     r14, rcx
0x180005e45  test    rdx, rdx
0x180005e48  jz      loc_1800060A1
0x180005e4e  test    rcx, rcx
0x180005e51  jz      loc_1800060A1
0x180005e57  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e5e  mov     [rcx], r15w
0x180005e62  test    rax, rax
0x180005e65  jz      short loc_180005E88
0x180005e67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005e6e  jz      short loc_180005E88
0x180005e70  mov     r8, rdx
0x180005e73  mov     rdx, rcx
0x180005e76  mov     rcx, rbx
0x180005e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7e  cmp     [r14], r15w
0x180005e82  jnz     loc_1800060A1
0x180005e88  mov     ecx, [rbx]
0x180005e8a  mov     bpl, 8
0x180005e8d  test    ecx, ecx
0x180005e8f  jz      short loc_180005EDA
0x180005e91  sub     ecx, 1
0x180005e94  jz      short loc_180005EC2
0x180005e96  sub     ecx, 1
0x180005e99  jz      short loc_180005EB2
0x180005e9b  cmp     ecx, 1
0x180005e9e  jz      short loc_180005EA9
0x180005ea0  lea     rdi, word_18002E916
0x180005ea7  jmp     short loc_180005EE1
0x180005ea9  lea     rdi, aFailfast; "FailFast"
0x180005eb0  jmp     short loc_180005EE1
0x180005eb2  lea     rax, aLoghr; "LogHr"
0x180005eb9  lea     rdi, aLognt; "LogNt"
0x180005ec0  jmp     short loc_180005ED0
0x180005ec2  lea     rax, aReturnhr; "ReturnHr"
0x180005ec9  lea     rdi, aReturnnt; "ReturnNt"
0x180005ed0  test    [rbx+4], bpl
0x180005ed4  cmovz   rdi, rax
0x180005ed8  jmp     short loc_180005EE1
0x180005eda  lea     rdi, aException; "Exception"
0x180005ee1  xor     edx, edx; Val
0x180005ee3  lea     rcx, [rsp+278h+Buffer]; void *
0x180005ee8  mov     r8d, 200h; Size
0x180005eee  call    memset_0
0x180005ef3  test    [rbx+4], bpl
0x180005ef7  jz      short loc_180005F1C
0x180005ef9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005f00  mov     ebp, [rbx+0Ch]
0x180005f03  test    rax, rax
0x180005f06  jz      short loc_180005F4C
0x180005f08  mov     r8d, 100h
0x180005f0e  lea     rdx, [rsp+278h+Buffer]
0x180005f13  mov     ecx, ebp
0x180005f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1a  jmp     short loc_180005F4C
0x180005f1c  mov     ebp, [rbx+8]
0x180005f1f  lea     rax, [rsp+278h+Buffer]
0x180005f24  mov     [rsp+278h+Arguments], r15; Arguments
0x180005f29  mov     r8d, ebp; dwMessageId
0x180005f2c  mov     [rsp+278h+nSize], 100h; nSize
0x180005f34  mov     r9d, 400h; dwLanguageId
0x180005f3a  xor     edx, edx; lpSource
0x180005f3c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005f41  mov     ecx, 1200h; dwFlags
0x180005f46  call    cs:__imp_FormatMessageW
0x180005f4c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005f50  lea     rsi, [r14+rsi*2]
0x180005f54  mov     rax, [rbx+88h]
0x180005f5b  mov     rdx, rsi; unsigned __int16 *
0x180005f5e  mov     rcx, [rbx+80h]
0x180005f65  test    r9, r9
0x180005f68  jz      short loc_180005F8C
0x180005f6a  mov     [rsp+278h+Arguments], rax
0x180005f6f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005f76  mov     eax, [rbx+40h]
0x180005f79  mov     qword ptr [rsp+278h+nSize], rcx
0x180005f7e  mov     rcx, r14; this
0x180005f81  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005f85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f8a  jmp     short loc_180005FA3
0x180005f8c  mov     r9, rcx; unsigned __int16 *
0x180005f8f  mov     [rsp+278h+lpBuffer], rax
0x180005f94  mov     rcx, r14; this
0x180005f97  lea     r8, aHsP; "%hs!%p: "
0x180005f9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fa3  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005faa  mov     r14, rax
0x180005fad  test    r9, r9
0x180005fb0  jz      short loc_180005FC7
0x180005fb2  lea     r8, aCallerP; "(caller: %p) "
0x180005fb9  mov     rdx, rsi; unsigned __int16 *
0x180005fbc  mov     rcx, rax; this
0x180005fbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fc4  mov     r14, rax
0x180005fc7  call    cs:__imp_GetCurrentThreadId
0x180005fcd  lea     rcx, [rsp+278h+Buffer]
0x180005fd2  mov     r9, rdi; unsigned __int16 *
0x180005fd5  mov     [rsp+278h+var_240], rcx
0x180005fda  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005fe1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005fe5  mov     rdx, rsi; unsigned __int16 *
0x180005fe8  mov     [rsp+278h+nSize], eax
0x180005fec  mov     rcx, r14; this
0x180005fef  mov     eax, [rbx+44h]
0x180005ff2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005ff6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ffb  cmp     [rbx+18h], r15
0x180005fff  jnz     short loc_180006011
0x180006001  cmp     [rbx+48h], r15
0x180006005  jnz     short loc_180006011
0x180006007  cmp     [rbx+30h], r15
0x18000600b  jz      loc_1800060A1
0x180006011  lea     r8, asc_18002E5D0; "    "
0x180006018  mov     rdx, rsi; unsigned __int16 *
0x18000601b  mov     rcx, rax; this
0x18000601e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006023  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006027  test    r9, r9
0x18000602a  jz      short loc_18000603E
0x18000602c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006033  mov     rdx, rsi; unsigned __int16 *
0x180006036  mov     rcx, rax; this
0x180006039  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000603e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006042  test    r9, r9
0x180006045  jz      short loc_180006059
0x180006047  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000604e  mov     rdx, rsi; unsigned __int16 *
0x180006051  mov     rcx, rax; this
0x180006054  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006059  mov     rcx, [rbx+28h]
0x18000605d  mov     rdx, rsi; unsigned __int16 *
0x180006060  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006064  test    rcx, rcx
0x180006067  jz      short loc_18000607F
0x180006069  mov     [rsp+278h+lpBuffer], rcx
0x18000606e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006075  mov     rcx, rax; this
0x180006078  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000607d  jmp     short loc_1800060A1
0x18000607f  mov     rcx, rax; this
0x180006082  test    r9, r9
0x180006085  jz      short loc_180006095
0x180006087  lea     r8, aHs; "[%hs]\n"
0x18000608e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006093  jmp     short loc_1800060A1
0x180006095  lea     r8, asc_18002E648; "\n"
0x18000609c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060a1  xor     eax, eax
0x1800060a3  mov     rcx, [rsp+278h+var_38]
0x1800060ab  xor     rcx, rsp; StackCookie
0x1800060ae  call    __security_check_cookie
0x1800060b3  mov     rbx, [rsp+278h+arg_18]
0x1800060bb  add     rsp, 250h
0x1800060c2  pop     r15
0x1800060c4  pop     r14
0x1800060c6  pop     rdi
0x1800060c7  pop     rsi
0x1800060c8  pop     rbp
0x1800060c9  retn
```
