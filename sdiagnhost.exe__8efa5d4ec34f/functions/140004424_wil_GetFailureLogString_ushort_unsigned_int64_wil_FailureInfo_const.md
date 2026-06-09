# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004424`
- end: `0x1400046e5`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1400030e8`
- `0x140003368`
- `0x140004da4`
- `0x1400074e0`

## callees

- `0x140001c8f`
- `0x140004424`
- `0x1400050ac`
- `0x140007770`
- `0x140008010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140004561`
- `KERNEL32!FormatMessageW` at `0x140004561`
- `KERNEL32!GetCurrentThreadId` at `0x1400045e2`
- `KERNEL32!GetCurrentThreadId` at `0x1400045e2`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&qword_14000AE88;
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
                          Buffer,
                          -2);
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
0x140004424  mov     rax, rsp
0x140004427  push    rbp
0x140004428  push    rsi
0x140004429  push    rdi
0x14000442a  push    r14
0x14000442c  push    r15
0x14000442e  sub     rsp, 260h
0x140004435  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x14000443e  mov     [rax+20h], rbx
0x140004442  mov     rax, cs:__security_cookie
0x140004449  xor     rax, rsp
0x14000444c  mov     [rsp+288h+var_38], rax
0x140004454  mov     rbx, r8
0x140004457  mov     rsi, rdx
0x14000445a  mov     r14, rcx
0x14000445d  xor     r15d, r15d
0x140004460  test    rdx, rdx
0x140004463  jz      loc_1400046BC
0x140004469  test    rcx, rcx
0x14000446c  jz      loc_1400046BC
0x140004472  mov     [rcx], r15w
0x140004476  mov     rax, cs:g_pfnResultLoggingCallback
0x14000447d  test    rax, rax
0x140004480  jz      short loc_1400044A3
0x140004482  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004489  jz      short loc_1400044A3
0x14000448b  mov     r8, rdx
0x14000448e  mov     rdx, rcx
0x140004491  mov     rcx, rbx
0x140004494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004499  cmp     [r14], r15w
0x14000449d  jnz     loc_1400046BC
0x1400044a3  mov     ecx, [rbx]
0x1400044a5  mov     bpl, 8
0x1400044a8  test    ecx, ecx
0x1400044aa  jz      short loc_1400044F5
0x1400044ac  sub     ecx, 1
0x1400044af  jz      short loc_1400044DD
0x1400044b1  sub     ecx, 1
0x1400044b4  jz      short loc_1400044CD
0x1400044b6  cmp     ecx, 1
0x1400044b9  jz      short loc_1400044C4
0x1400044bb  lea     rdi, qword_14000AE88
0x1400044c2  jmp     short loc_1400044FC
0x1400044c4  lea     rdi, aFailfast; "FailFast"
0x1400044cb  jmp     short loc_1400044FC
0x1400044cd  lea     rax, aLoghr; "LogHr"
0x1400044d4  lea     rdi, aLognt; "LogNt"
0x1400044db  jmp     short loc_1400044EB
0x1400044dd  lea     rax, aReturnhr; "ReturnHr"
0x1400044e4  lea     rdi, aReturnnt; "ReturnNt"
0x1400044eb  test    [rbx+4], bpl
0x1400044ef  cmovz   rdi, rax
0x1400044f3  jmp     short loc_1400044FC
0x1400044f5  lea     rdi, aException; "Exception"
0x1400044fc  xor     edx, edx; Val
0x1400044fe  mov     r8d, 200h; Size
0x140004504  lea     rcx, [rsp+288h+Buffer]; void *
0x140004509  call    memset_0
0x14000450e  test    [rbx+4], bpl
0x140004512  jz      short loc_140004537
0x140004514  mov     ebp, [rbx+0Ch]
0x140004517  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000451e  test    rax, rax
0x140004521  jz      short loc_140004567
0x140004523  mov     r8d, 100h
0x140004529  lea     rdx, [rsp+288h+Buffer]
0x14000452e  mov     ecx, ebp
0x140004530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004535  jmp     short loc_140004567
0x140004537  mov     ebp, [rbx+8]
0x14000453a  mov     [rsp+288h+Arguments], r15; Arguments
0x14000453f  mov     [rsp+288h+nSize], 100h; nSize
0x140004547  lea     rax, [rsp+288h+Buffer]
0x14000454c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x140004551  mov     r9d, 400h; dwLanguageId
0x140004557  mov     r8d, ebp; dwMessageId
0x14000455a  xor     edx, edx; lpSource
0x14000455c  mov     ecx, 1200h; dwFlags
0x140004561  call    cs:__imp_FormatMessageW
0x140004567  lea     rsi, [r14+rsi*2]
0x14000456b  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000456f  mov     rax, [rbx+88h]
0x140004576  mov     rcx, [rbx+80h]
0x14000457d  mov     rdx, rsi; unsigned __int16 *
0x140004580  test    r9, r9
0x140004583  jz      short loc_1400045A7
0x140004585  mov     [rsp+288h+Arguments], rax
0x14000458a  mov     qword ptr [rsp+288h+nSize], rcx
0x14000458f  mov     eax, [rbx+40h]
0x140004592  mov     dword ptr [rsp+288h+lpBuffer], eax
0x140004596  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000459d  mov     rcx, r14; this
0x1400045a0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045a5  jmp     short loc_1400045BE
0x1400045a7  mov     [rsp+288h+lpBuffer], rax
0x1400045ac  mov     r9, rcx; unsigned __int16 *
0x1400045af  lea     r8, aHsP; "%hs!%p: "
0x1400045b6  mov     rcx, r14; this
0x1400045b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045be  mov     r14, rax
0x1400045c1  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400045c8  test    r9, r9
0x1400045cb  jz      short loc_1400045E2
0x1400045cd  lea     r8, aCallerP; "(caller: %p) "
0x1400045d4  mov     rdx, rsi; unsigned __int16 *
0x1400045d7  mov     rcx, rax; this
0x1400045da  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045df  mov     r14, rax
0x1400045e2  call    cs:__imp_GetCurrentThreadId
0x1400045e8  lea     rcx, [rsp+288h+Buffer]
0x1400045ed  mov     [rsp+288h+var_250], rcx
0x1400045f2  mov     dword ptr [rsp+288h+Arguments], ebp
0x1400045f6  mov     [rsp+288h+nSize], eax
0x1400045fa  mov     eax, [rbx+44h]
0x1400045fd  mov     dword ptr [rsp+288h+lpBuffer], eax
0x140004601  mov     r9, rdi; unsigned __int16 *
0x140004604  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000460b  mov     rdx, rsi; unsigned __int16 *
0x14000460e  mov     rcx, r14; this
0x140004611  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004616  cmp     [rbx+18h], r15
0x14000461a  jnz     short loc_14000462C
0x14000461c  cmp     [rbx+48h], r15
0x140004620  jnz     short loc_14000462C
0x140004622  cmp     [rbx+30h], r15
0x140004626  jz      loc_1400046BC
0x14000462c  lea     r8, asc_14000AF88; "    "
0x140004633  mov     rdx, rsi; unsigned __int16 *
0x140004636  mov     rcx, rax; this
0x140004639  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000463e  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004642  test    r9, r9
0x140004645  jz      short loc_140004659
0x140004647  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000464e  mov     rdx, rsi; unsigned __int16 *
0x140004651  mov     rcx, rax; this
0x140004654  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004659  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000465d  test    r9, r9
0x140004660  jz      short loc_140004674
0x140004662  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140004669  mov     rdx, rsi; unsigned __int16 *
0x14000466c  mov     rcx, rax; this
0x14000466f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004674  mov     rcx, [rbx+28h]
0x140004678  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000467c  mov     rdx, rsi; unsigned __int16 *
0x14000467f  test    rcx, rcx
0x140004682  jz      short loc_14000469A
0x140004684  mov     [rsp+288h+lpBuffer], rcx
0x140004689  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004690  mov     rcx, rax; this
0x140004693  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004698  jmp     short loc_1400046BC
0x14000469a  mov     rcx, rax; this
0x14000469d  test    r9, r9
0x1400046a0  jz      short loc_1400046B0
0x1400046a2  lea     r8, aHs; "[%hs]\n"
0x1400046a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400046ae  jmp     short loc_1400046BC
0x1400046b0  lea     r8, asc_14000B000; "\n"
0x1400046b7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400046bc  xor     eax, eax
0x1400046be  mov     rcx, [rsp+288h+var_38]
0x1400046c6  xor     rcx, rsp; StackCookie
0x1400046c9  call    __security_check_cookie
0x1400046ce  mov     rbx, [rsp+288h+arg_18]
0x1400046d6  add     rsp, 260h
0x1400046dd  pop     r15
0x1400046df  pop     r14
0x1400046e1  pop     rdi
0x1400046e2  pop     rsi
0x1400046e3  pop     rbp
0x1400046e4  retn
```
