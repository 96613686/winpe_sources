# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001e7a4`
- end: `0x18001ea5a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001caf4`
- `0x18001cd5c`
- `0x18001f370`

## callees

- `0x18001a57c`
- `0x18001e7a4`
- `0x180032c6a`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e957`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e8d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e8d6`

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
          v8 = (const char *)&qword_180037540;
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
0x18001e7a4  mov     [rsp+arg_18], rbx
0x18001e7a9  push    rbp
0x18001e7aa  push    rsi
0x18001e7ab  push    rdi
0x18001e7ac  push    r14
0x18001e7ae  push    r15
0x18001e7b0  sub     rsp, 250h
0x18001e7b7  mov     rax, cs:__security_cookie
0x18001e7be  xor     rax, rsp
0x18001e7c1  mov     [rsp+278h+var_38], rax
0x18001e7c9  xor     r15d, r15d
0x18001e7cc  mov     rbx, r8
0x18001e7cf  mov     rsi, rdx
0x18001e7d2  mov     r14, rcx
0x18001e7d5  test    rdx, rdx
0x18001e7d8  jz      loc_18001EA31
0x18001e7de  test    rcx, rcx
0x18001e7e1  jz      loc_18001EA31
0x18001e7e7  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e7ee  mov     [rcx], r15w
0x18001e7f2  test    rax, rax
0x18001e7f5  jz      short loc_18001E818
0x18001e7f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001e7fe  jz      short loc_18001E818
0x18001e800  mov     r8, rdx
0x18001e803  mov     rdx, rcx
0x18001e806  mov     rcx, rbx
0x18001e809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e80e  cmp     [r14], r15w
0x18001e812  jnz     loc_18001EA31
0x18001e818  mov     ecx, [rbx]
0x18001e81a  mov     bpl, 8
0x18001e81d  test    ecx, ecx
0x18001e81f  jz      short loc_18001E86A
0x18001e821  sub     ecx, 1
0x18001e824  jz      short loc_18001E852
0x18001e826  sub     ecx, 1
0x18001e829  jz      short loc_18001E842
0x18001e82b  cmp     ecx, 1
0x18001e82e  jz      short loc_18001E839
0x18001e830  lea     rdi, qword_180037540
0x18001e837  jmp     short loc_18001E871
0x18001e839  lea     rdi, aFailfast; "FailFast"
0x18001e840  jmp     short loc_18001E871
0x18001e842  lea     rax, aLoghr; "LogHr"
0x18001e849  lea     rdi, aLognt; "LogNt"
0x18001e850  jmp     short loc_18001E860
0x18001e852  lea     rax, aReturnhr; "ReturnHr"
0x18001e859  lea     rdi, aReturnnt; "ReturnNt"
0x18001e860  test    [rbx+4], bpl
0x18001e864  cmovz   rdi, rax
0x18001e868  jmp     short loc_18001E871
0x18001e86a  lea     rdi, aException; "Exception"
0x18001e871  xor     edx, edx; Val
0x18001e873  lea     rcx, [rsp+278h+Buffer]; void *
0x18001e878  mov     r8d, 200h; Size
0x18001e87e  call    memset_0
0x18001e883  test    [rbx+4], bpl
0x18001e887  jz      short loc_18001E8AC
0x18001e889  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001e890  mov     ebp, [rbx+0Ch]
0x18001e893  test    rax, rax
0x18001e896  jz      short loc_18001E8DC
0x18001e898  mov     r8d, 100h
0x18001e89e  lea     rdx, [rsp+278h+Buffer]
0x18001e8a3  mov     ecx, ebp
0x18001e8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8aa  jmp     short loc_18001E8DC
0x18001e8ac  mov     ebp, [rbx+8]
0x18001e8af  lea     rax, [rsp+278h+Buffer]
0x18001e8b4  mov     [rsp+278h+Arguments], r15; Arguments
0x18001e8b9  mov     r8d, ebp; dwMessageId
0x18001e8bc  mov     [rsp+278h+nSize], 100h; nSize
0x18001e8c4  mov     r9d, 400h; dwLanguageId
0x18001e8ca  xor     edx, edx; lpSource
0x18001e8cc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001e8d1  mov     ecx, 1200h; dwFlags
0x18001e8d6  call    cs:__imp_FormatMessageW
0x18001e8dc  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001e8e0  lea     rsi, [r14+rsi*2]
0x18001e8e4  mov     rax, [rbx+88h]
0x18001e8eb  mov     rdx, rsi; unsigned __int16 *
0x18001e8ee  mov     rcx, [rbx+80h]
0x18001e8f5  test    r9, r9
0x18001e8f8  jz      short loc_18001E91C
0x18001e8fa  mov     [rsp+278h+Arguments], rax
0x18001e8ff  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001e906  mov     eax, [rbx+40h]
0x18001e909  mov     qword ptr [rsp+278h+nSize], rcx
0x18001e90e  mov     rcx, r14; this
0x18001e911  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e915  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e91a  jmp     short loc_18001E933
0x18001e91c  mov     r9, rcx; unsigned __int16 *
0x18001e91f  mov     [rsp+278h+lpBuffer], rax
0x18001e924  mov     rcx, r14; this
0x18001e927  lea     r8, aHsP; "%hs!%p: "
0x18001e92e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e933  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001e93a  mov     r14, rax
0x18001e93d  test    r9, r9
0x18001e940  jz      short loc_18001E957
0x18001e942  lea     r8, aCallerP; "(caller: %p) "
0x18001e949  mov     rdx, rsi; unsigned __int16 *
0x18001e94c  mov     rcx, rax; this
0x18001e94f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e954  mov     r14, rax
0x18001e957  call    cs:__imp_GetCurrentThreadId
0x18001e95d  lea     rcx, [rsp+278h+Buffer]
0x18001e962  mov     r9, rdi; unsigned __int16 *
0x18001e965  mov     [rsp+278h+var_240], rcx
0x18001e96a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001e971  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001e975  mov     rdx, rsi; unsigned __int16 *
0x18001e978  mov     [rsp+278h+nSize], eax
0x18001e97c  mov     rcx, r14; this
0x18001e97f  mov     eax, [rbx+44h]
0x18001e982  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e986  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e98b  cmp     [rbx+18h], r15
0x18001e98f  jnz     short loc_18001E9A1
0x18001e991  cmp     [rbx+48h], r15
0x18001e995  jnz     short loc_18001E9A1
0x18001e997  cmp     [rbx+30h], r15
0x18001e99b  jz      loc_18001EA31
0x18001e9a1  lea     r8, asc_180037630; "    "
0x18001e9a8  mov     rdx, rsi; unsigned __int16 *
0x18001e9ab  mov     rcx, rax; this
0x18001e9ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e9b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001e9b7  test    r9, r9
0x18001e9ba  jz      short loc_18001E9CE
0x18001e9bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001e9c3  mov     rdx, rsi; unsigned __int16 *
0x18001e9c6  mov     rcx, rax; this
0x18001e9c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e9ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001e9d2  test    r9, r9
0x18001e9d5  jz      short loc_18001E9E9
0x18001e9d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001e9de  mov     rdx, rsi; unsigned __int16 *
0x18001e9e1  mov     rcx, rax; this
0x18001e9e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e9e9  mov     rcx, [rbx+28h]
0x18001e9ed  mov     rdx, rsi; unsigned __int16 *
0x18001e9f0  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001e9f4  test    rcx, rcx
0x18001e9f7  jz      short loc_18001EA0F
0x18001e9f9  mov     [rsp+278h+lpBuffer], rcx
0x18001e9fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001ea05  mov     rcx, rax; this
0x18001ea08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ea0d  jmp     short loc_18001EA31
0x18001ea0f  mov     rcx, rax; this
0x18001ea12  test    r9, r9
0x18001ea15  jz      short loc_18001EA25
0x18001ea17  lea     r8, aHs; "[%hs]\n"
0x18001ea1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ea23  jmp     short loc_18001EA31
0x18001ea25  lea     r8, asc_1800376A8; "\n"
0x18001ea2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ea31  xor     eax, eax
0x18001ea33  mov     rcx, [rsp+278h+var_38]
0x18001ea3b  xor     rcx, rsp; StackCookie
0x18001ea3e  call    __security_check_cookie
0x18001ea43  mov     rbx, [rsp+278h+arg_18]
0x18001ea4b  add     rsp, 250h
0x18001ea52  pop     r15
0x18001ea54  pop     r14
0x18001ea56  pop     rdi
0x18001ea57  pop     rsi
0x18001ea58  pop     rbp
0x18001ea59  retn
```
