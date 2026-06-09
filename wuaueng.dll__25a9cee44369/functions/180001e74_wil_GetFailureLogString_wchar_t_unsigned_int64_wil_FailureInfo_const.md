# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180001e74`
- end: `0x180002128`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002d90`
- `0x180003280`
- `0x180004580`
- `0x180004b60`
- `0x180009af8`
- `0x1800164ec`
- `0x180016625`

## callees

- `0x180001e08`
- `0x180001e74`
- `0x18000fc90`
- `0x1800159b0`
- `0x180015a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002025`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002025`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180001fa4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180001fa4`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rdi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
  v7 = (const char *)&word_1800189A6;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180001e74  mov     [rsp+arg_18], rbx
0x180001e79  push    rbp
0x180001e7a  push    rsi
0x180001e7b  push    rdi
0x180001e7c  push    r14
0x180001e7e  push    r15
0x180001e80  sub     rsp, 250h
0x180001e87  mov     rax, cs:__security_cookie
0x180001e8e  xor     rax, rsp
0x180001e91  mov     [rsp+278h+var_38], rax
0x180001e99  mov     rbx, r8
0x180001e9c  mov     rdi, rdx
0x180001e9f  mov     r14, rcx
0x180001ea2  xor     r15d, r15d
0x180001ea5  test    rdx, rdx
0x180001ea8  jz      loc_1800020FF
0x180001eae  test    rcx, rcx
0x180001eb1  jz      loc_1800020FF
0x180001eb7  mov     [rcx], r15w
0x180001ebb  mov     rax, cs:g_pfnResultLoggingCallback
0x180001ec2  test    rax, rax
0x180001ec5  jz      short loc_180001EE8
0x180001ec7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180001ece  jz      short loc_180001EE8
0x180001ed0  mov     r8, rdx
0x180001ed3  mov     rdx, rcx
0x180001ed6  mov     rcx, rbx
0x180001ed9  call    _guard_dispatch_icall
0x180001ede  cmp     [r14], r15w
0x180001ee2  jnz     loc_1800020FF
0x180001ee8  lea     rsi, word_1800189A6
0x180001eef  mov     ecx, [rbx]
0x180001ef1  mov     bpl, 8
0x180001ef4  test    ecx, ecx
0x180001ef6  jz      short loc_180001F38
0x180001ef8  sub     ecx, 1
0x180001efb  jz      short loc_180001F20
0x180001efd  sub     ecx, 1
0x180001f00  jz      short loc_180001F10
0x180001f02  cmp     ecx, 1
0x180001f05  jnz     short loc_180001F3F
0x180001f07  lea     rsi, aFailfast; "FailFast"
0x180001f0e  jmp     short loc_180001F3F
0x180001f10  lea     rax, aLoghr; "LogHr"
0x180001f17  lea     rsi, aLognt; "LogNt"
0x180001f1e  jmp     short loc_180001F2E
0x180001f20  lea     rax, aReturnhr; "ReturnHr"
0x180001f27  lea     rsi, aReturnnt; "ReturnNt"
0x180001f2e  test    [rbx+4], bpl
0x180001f32  cmovz   rsi, rax
0x180001f36  jmp     short loc_180001F3F
0x180001f38  lea     rsi, aException; "Exception"
0x180001f3f  xor     edx, edx; Val
0x180001f41  mov     r8d, 200h; Size
0x180001f47  lea     rcx, [rsp+278h+Buffer]; void *
0x180001f4c  call    memset
0x180001f51  test    [rbx+4], bpl
0x180001f55  jz      short loc_180001F7A
0x180001f57  mov     ebp, [rbx+0Ch]
0x180001f5a  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180001f61  test    rax, rax
0x180001f64  jz      short loc_180001FAA
0x180001f66  mov     r8d, 100h
0x180001f6c  lea     rdx, [rsp+278h+Buffer]
0x180001f71  mov     ecx, ebp
0x180001f73  call    _guard_dispatch_icall
0x180001f78  jmp     short loc_180001FAA
0x180001f7a  mov     ebp, [rbx+8]
0x180001f7d  mov     [rsp+278h+Arguments], r15; Arguments
0x180001f82  mov     [rsp+278h+nSize], 100h; nSize
0x180001f8a  lea     rax, [rsp+278h+Buffer]
0x180001f8f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180001f94  mov     r9d, 400h; dwLanguageId
0x180001f9a  mov     r8d, ebp; dwMessageId
0x180001f9d  xor     edx, edx; lpSource
0x180001f9f  mov     ecx, 1200h; dwFlags
0x180001fa4  call    cs:__imp_FormatMessageW
0x180001faa  lea     rdi, [r14+rdi*2]
0x180001fae  mov     r9, [rbx+38h]; wchar_t *
0x180001fb2  mov     rax, [rbx+88h]
0x180001fb9  mov     rcx, [rbx+80h]
0x180001fc0  mov     rdx, rdi; wchar_t *
0x180001fc3  test    r9, r9
0x180001fc6  jz      short loc_180001FEA
0x180001fc8  mov     [rsp+278h+Arguments], rax
0x180001fcd  mov     qword ptr [rsp+278h+nSize], rcx
0x180001fd2  mov     eax, [rbx+40h]
0x180001fd5  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180001fd9  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180001fe0  mov     rcx, r14; this
0x180001fe3  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180001fe8  jmp     short loc_180002001
0x180001fea  mov     [rsp+278h+lpBuffer], rax
0x180001fef  mov     r9, rcx; wchar_t *
0x180001ff2  lea     r8, aHsP; "%hs!%p: "
0x180001ff9  mov     rcx, r14; this
0x180001ffc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002001  mov     r14, rax
0x180002004  mov     r9, [rbx+90h]; wchar_t *
0x18000200b  test    r9, r9
0x18000200e  jz      short loc_180002025
0x180002010  lea     r8, aCallerP; "(caller: %p) "
0x180002017  mov     rdx, rdi; wchar_t *
0x18000201a  mov     rcx, rax; this
0x18000201d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002022  mov     r14, rax
0x180002025  call    cs:__imp_GetCurrentThreadId
0x18000202b  lea     rcx, [rsp+278h+Buffer]
0x180002030  mov     [rsp+278h+var_240], rcx
0x180002035  mov     dword ptr [rsp+278h+Arguments], ebp
0x180002039  mov     [rsp+278h+nSize], eax
0x18000203d  mov     eax, [rbx+44h]
0x180002040  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002044  mov     r9, rsi; wchar_t *
0x180002047  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000204e  mov     rdx, rdi; wchar_t *
0x180002051  mov     rcx, r14; this
0x180002054  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002059  cmp     [rbx+18h], r15
0x18000205d  jnz     short loc_18000206F
0x18000205f  cmp     [rbx+48h], r15
0x180002063  jnz     short loc_18000206F
0x180002065  cmp     [rbx+30h], r15
0x180002069  jz      loc_1800020FF
0x18000206f  lea     r8, asc_180018AA8; "    "
0x180002076  mov     rdx, rdi; wchar_t *
0x180002079  mov     rcx, rax; this
0x18000207c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002081  mov     r9, [rbx+18h]; wchar_t *
0x180002085  test    r9, r9
0x180002088  jz      short loc_18000209C
0x18000208a  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002091  mov     rdx, rdi; wchar_t *
0x180002094  mov     rcx, rax; this
0x180002097  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000209c  mov     r9, [rbx+48h]; wchar_t *
0x1800020a0  test    r9, r9
0x1800020a3  jz      short loc_1800020B7
0x1800020a5  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800020ac  mov     rdx, rdi; wchar_t *
0x1800020af  mov     rcx, rax; this
0x1800020b2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800020b7  mov     rcx, [rbx+28h]
0x1800020bb  mov     r9, [rbx+30h]; wchar_t *
0x1800020bf  mov     rdx, rdi; wchar_t *
0x1800020c2  test    rcx, rcx
0x1800020c5  jz      short loc_1800020DD
0x1800020c7  mov     [rsp+278h+lpBuffer], rcx
0x1800020cc  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800020d3  mov     rcx, rax; this
0x1800020d6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800020db  jmp     short loc_1800020FF
0x1800020dd  mov     rcx, rax; this
0x1800020e0  test    r9, r9
0x1800020e3  jz      short loc_1800020F3
0x1800020e5  lea     r8, aHs; "[%hs]\n"
0x1800020ec  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800020f1  jmp     short loc_1800020FF
0x1800020f3  lea     r8, asc_180018B20; "\n"
0x1800020fa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800020ff  xor     eax, eax
0x180002101  mov     rcx, [rsp+278h+var_38]
0x180002109  xor     rcx, rsp; StackCookie
0x18000210c  call    __security_check_cookie
0x180002111  mov     rbx, [rsp+278h+arg_18]
0x180002119  add     rsp, 250h
0x180002120  pop     r15
0x180002122  pop     r14
0x180002124  pop     rdi
0x180002125  pop     rsi
0x180002126  pop     rbp
0x180002127  retn
```
