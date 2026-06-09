# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180062104`
- end: `0x1800623ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180062838`

## callees

- `0x1800597b0`
- `0x18005a160`
- `0x180062104`
- `0x180062b34`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180062236`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180062236`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800622b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800622b7`

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
          v8 = (const char *)&qword_180099B30;
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
0x180062104  mov     [rsp+arg_18], rbx
0x180062109  push    rbp
0x18006210a  push    rsi
0x18006210b  push    rdi
0x18006210c  push    r14
0x18006210e  push    r15
0x180062110  sub     rsp, 250h
0x180062117  mov     rax, cs:__security_cookie
0x18006211e  xor     rax, rsp
0x180062121  mov     [rsp+278h+var_38], rax
0x180062129  xor     r15d, r15d
0x18006212c  mov     rbx, r8
0x18006212f  mov     rsi, rdx
0x180062132  mov     r14, rcx
0x180062135  test    rdx, rdx
0x180062138  jz      loc_180062391
0x18006213e  test    rcx, rcx
0x180062141  jz      loc_180062391
0x180062147  mov     rax, cs:g_pfnResultLoggingCallback
0x18006214e  mov     [rcx], r15w
0x180062152  test    rax, rax
0x180062155  jz      short loc_180062178
0x180062157  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18006215e  jz      short loc_180062178
0x180062160  mov     r8, rdx
0x180062163  mov     rdx, rcx
0x180062166  mov     rcx, rbx
0x180062169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006216e  cmp     [r14], r15w
0x180062172  jnz     loc_180062391
0x180062178  mov     ecx, [rbx]
0x18006217a  mov     bpl, 8
0x18006217d  test    ecx, ecx
0x18006217f  jz      short loc_1800621CA
0x180062181  sub     ecx, 1
0x180062184  jz      short loc_1800621B2
0x180062186  sub     ecx, 1
0x180062189  jz      short loc_1800621A2
0x18006218b  cmp     ecx, 1
0x18006218e  jz      short loc_180062199
0x180062190  lea     rdi, qword_180099B30
0x180062197  jmp     short loc_1800621D1
0x180062199  lea     rdi, aFailfast; "FailFast"
0x1800621a0  jmp     short loc_1800621D1
0x1800621a2  lea     rax, aLoghr; "LogHr"
0x1800621a9  lea     rdi, aLognt; "LogNt"
0x1800621b0  jmp     short loc_1800621C0
0x1800621b2  lea     rax, aReturnhr; "ReturnHr"
0x1800621b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800621c0  test    [rbx+4], bpl
0x1800621c4  cmovz   rdi, rax
0x1800621c8  jmp     short loc_1800621D1
0x1800621ca  lea     rdi, aException; "Exception"
0x1800621d1  xor     edx, edx; Val
0x1800621d3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800621d8  mov     r8d, 200h; Size
0x1800621de  call    memset_0
0x1800621e3  test    [rbx+4], bpl
0x1800621e7  jz      short loc_18006220C
0x1800621e9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800621f0  mov     ebp, [rbx+0Ch]
0x1800621f3  test    rax, rax
0x1800621f6  jz      short loc_18006223C
0x1800621f8  mov     r8d, 100h
0x1800621fe  lea     rdx, [rsp+278h+Buffer]
0x180062203  mov     ecx, ebp
0x180062205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006220a  jmp     short loc_18006223C
0x18006220c  mov     ebp, [rbx+8]
0x18006220f  lea     rax, [rsp+278h+Buffer]
0x180062214  mov     [rsp+278h+Arguments], r15; Arguments
0x180062219  mov     r8d, ebp; dwMessageId
0x18006221c  mov     [rsp+278h+nSize], 100h; nSize
0x180062224  mov     r9d, 400h; dwLanguageId
0x18006222a  xor     edx, edx; lpSource
0x18006222c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180062231  mov     ecx, 1200h; dwFlags
0x180062236  call    cs:__imp_FormatMessageW
0x18006223c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180062240  lea     rsi, [r14+rsi*2]
0x180062244  mov     rax, [rbx+88h]
0x18006224b  mov     rdx, rsi; unsigned __int16 *
0x18006224e  mov     rcx, [rbx+80h]
0x180062255  test    r9, r9
0x180062258  jz      short loc_18006227C
0x18006225a  mov     [rsp+278h+Arguments], rax
0x18006225f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180062266  mov     eax, [rbx+40h]
0x180062269  mov     qword ptr [rsp+278h+nSize], rcx
0x18006226e  mov     rcx, r14; this
0x180062271  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180062275  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006227a  jmp     short loc_180062293
0x18006227c  mov     r9, rcx; unsigned __int16 *
0x18006227f  mov     [rsp+278h+lpBuffer], rax
0x180062284  mov     rcx, r14; this
0x180062287  lea     r8, aHsP; "%hs!%p: "
0x18006228e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180062293  mov     r9, [rbx+90h]; unsigned __int16 *
0x18006229a  mov     r14, rax
0x18006229d  test    r9, r9
0x1800622a0  jz      short loc_1800622B7
0x1800622a2  lea     r8, aCallerP; "(caller: %p) "
0x1800622a9  mov     rdx, rsi; unsigned __int16 *
0x1800622ac  mov     rcx, rax; this
0x1800622af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800622b4  mov     r14, rax
0x1800622b7  call    cs:__imp_GetCurrentThreadId
0x1800622bd  lea     rcx, [rsp+278h+Buffer]
0x1800622c2  mov     r9, rdi; unsigned __int16 *
0x1800622c5  mov     [rsp+278h+var_240], rcx
0x1800622ca  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800622d1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800622d5  mov     rdx, rsi; unsigned __int16 *
0x1800622d8  mov     [rsp+278h+nSize], eax
0x1800622dc  mov     rcx, r14; this
0x1800622df  mov     eax, [rbx+44h]
0x1800622e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800622e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800622eb  cmp     [rbx+18h], r15
0x1800622ef  jnz     short loc_180062301
0x1800622f1  cmp     [rbx+48h], r15
0x1800622f5  jnz     short loc_180062301
0x1800622f7  cmp     [rbx+30h], r15
0x1800622fb  jz      loc_180062391
0x180062301  lea     r8, asc_180099808; "    "
0x180062308  mov     rdx, rsi; unsigned __int16 *
0x18006230b  mov     rcx, rax; this
0x18006230e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180062313  mov     r9, [rbx+18h]; unsigned __int16 *
0x180062317  test    r9, r9
0x18006231a  jz      short loc_18006232E
0x18006231c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180062323  mov     rdx, rsi; unsigned __int16 *
0x180062326  mov     rcx, rax; this
0x180062329  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006232e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180062332  test    r9, r9
0x180062335  jz      short loc_180062349
0x180062337  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18006233e  mov     rdx, rsi; unsigned __int16 *
0x180062341  mov     rcx, rax; this
0x180062344  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180062349  mov     rcx, [rbx+28h]
0x18006234d  mov     rdx, rsi; unsigned __int16 *
0x180062350  mov     r9, [rbx+30h]; unsigned __int16 *
0x180062354  test    rcx, rcx
0x180062357  jz      short loc_18006236F
0x180062359  mov     [rsp+278h+lpBuffer], rcx
0x18006235e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180062365  mov     rcx, rax; this
0x180062368  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006236d  jmp     short loc_180062391
0x18006236f  mov     rcx, rax; this
0x180062372  test    r9, r9
0x180062375  jz      short loc_180062385
0x180062377  lea     r8, aHs; "[%hs]\n"
0x18006237e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180062383  jmp     short loc_180062391
0x180062385  lea     r8, asc_180099880; "\n"
0x18006238c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180062391  xor     eax, eax
0x180062393  mov     rcx, [rsp+278h+var_38]
0x18006239b  xor     rcx, rsp; StackCookie
0x18006239e  call    __security_check_cookie
0x1800623a3  mov     rbx, [rsp+278h+arg_18]
0x1800623ab  add     rsp, 250h
0x1800623b2  pop     r15
0x1800623b4  pop     r14
0x1800623b6  pop     rdi
0x1800623b7  pop     rsi
0x1800623b8  pop     rbp
0x1800623b9  retn
```
