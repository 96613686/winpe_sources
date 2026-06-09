# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140001efc`
- end: `0x1400021b0`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1400021b8`
- `0x1400025a0`
- `0x140003860`
- `0x1400052cc`
- `0x14000b7c0`
- `0x14002121c`
- `0x140021355`

## callees

- `0x140001e90`
- `0x140001efc`
- `0x14001aa60`
- `0x1400206e0`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400020ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400020ad`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000202c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000202c`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v7 = (const char *)&qword_140023E40;
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
0x140001efc  mov     [rsp+arg_18], rbx
0x140001f01  push    rbp
0x140001f02  push    rsi
0x140001f03  push    rdi
0x140001f04  push    r14
0x140001f06  push    r15
0x140001f08  sub     rsp, 250h
0x140001f0f  mov     rax, cs:__security_cookie
0x140001f16  xor     rax, rsp
0x140001f19  mov     [rsp+278h+var_38], rax
0x140001f21  mov     rbx, r8
0x140001f24  mov     rdi, rdx
0x140001f27  mov     r14, rcx
0x140001f2a  xor     r15d, r15d
0x140001f2d  test    rdx, rdx
0x140001f30  jz      loc_140002187
0x140001f36  test    rcx, rcx
0x140001f39  jz      loc_140002187
0x140001f3f  mov     [rcx], r15w
0x140001f43  mov     rax, cs:g_pfnResultLoggingCallback
0x140001f4a  test    rax, rax
0x140001f4d  jz      short loc_140001F70
0x140001f4f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140001f56  jz      short loc_140001F70
0x140001f58  mov     r8, rdx
0x140001f5b  mov     rdx, rcx
0x140001f5e  mov     rcx, rbx
0x140001f61  call    _guard_dispatch_icall
0x140001f66  cmp     [r14], r15w
0x140001f6a  jnz     loc_140002187
0x140001f70  lea     rsi, qword_140023E40
0x140001f77  mov     ecx, [rbx]
0x140001f79  mov     bpl, 8
0x140001f7c  test    ecx, ecx
0x140001f7e  jz      short loc_140001FC0
0x140001f80  sub     ecx, 1
0x140001f83  jz      short loc_140001FA8
0x140001f85  sub     ecx, 1
0x140001f88  jz      short loc_140001F98
0x140001f8a  cmp     ecx, 1
0x140001f8d  jnz     short loc_140001FC7
0x140001f8f  lea     rsi, aFailfast; "FailFast"
0x140001f96  jmp     short loc_140001FC7
0x140001f98  lea     rax, aLoghr; "LogHr"
0x140001f9f  lea     rsi, aLognt; "LogNt"
0x140001fa6  jmp     short loc_140001FB6
0x140001fa8  lea     rax, aReturnhr; "ReturnHr"
0x140001faf  lea     rsi, aReturnnt; "ReturnNt"
0x140001fb6  test    [rbx+4], bpl
0x140001fba  cmovz   rsi, rax
0x140001fbe  jmp     short loc_140001FC7
0x140001fc0  lea     rsi, aException; "Exception"
0x140001fc7  xor     edx, edx; Val
0x140001fc9  mov     r8d, 200h; Size
0x140001fcf  lea     rcx, [rsp+278h+Buffer]; void *
0x140001fd4  call    memset
0x140001fd9  test    [rbx+4], bpl
0x140001fdd  jz      short loc_140002002
0x140001fdf  mov     ebp, [rbx+0Ch]
0x140001fe2  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140001fe9  test    rax, rax
0x140001fec  jz      short loc_140002032
0x140001fee  mov     r8d, 100h
0x140001ff4  lea     rdx, [rsp+278h+Buffer]
0x140001ff9  mov     ecx, ebp
0x140001ffb  call    _guard_dispatch_icall
0x140002000  jmp     short loc_140002032
0x140002002  mov     ebp, [rbx+8]
0x140002005  mov     [rsp+278h+Arguments], r15; Arguments
0x14000200a  mov     [rsp+278h+nSize], 100h; nSize
0x140002012  lea     rax, [rsp+278h+Buffer]
0x140002017  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000201c  mov     r9d, 400h; dwLanguageId
0x140002022  mov     r8d, ebp; dwMessageId
0x140002025  xor     edx, edx; lpSource
0x140002027  mov     ecx, 1200h; dwFlags
0x14000202c  call    cs:__imp_FormatMessageW
0x140002032  lea     rdi, [r14+rdi*2]
0x140002036  mov     r9, [rbx+38h]; wchar_t *
0x14000203a  mov     rax, [rbx+88h]
0x140002041  mov     rcx, [rbx+80h]
0x140002048  mov     rdx, rdi; wchar_t *
0x14000204b  test    r9, r9
0x14000204e  jz      short loc_140002072
0x140002050  mov     [rsp+278h+Arguments], rax
0x140002055  mov     qword ptr [rsp+278h+nSize], rcx
0x14000205a  mov     eax, [rbx+40h]
0x14000205d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140002061  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140002068  mov     rcx, r14; this
0x14000206b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140002070  jmp     short loc_140002089
0x140002072  mov     [rsp+278h+lpBuffer], rax
0x140002077  mov     r9, rcx; wchar_t *
0x14000207a  lea     r8, aHsP; "%hs!%p: "
0x140002081  mov     rcx, r14; this
0x140002084  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140002089  mov     r14, rax
0x14000208c  mov     r9, [rbx+90h]; wchar_t *
0x140002093  test    r9, r9
0x140002096  jz      short loc_1400020AD
0x140002098  lea     r8, aCallerP; "(caller: %p) "
0x14000209f  mov     rdx, rdi; wchar_t *
0x1400020a2  mov     rcx, rax; this
0x1400020a5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400020aa  mov     r14, rax
0x1400020ad  call    cs:__imp_GetCurrentThreadId
0x1400020b3  lea     rcx, [rsp+278h+Buffer]
0x1400020b8  mov     [rsp+278h+var_240], rcx
0x1400020bd  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400020c1  mov     [rsp+278h+nSize], eax
0x1400020c5  mov     eax, [rbx+44h]
0x1400020c8  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400020cc  mov     r9, rsi; wchar_t *
0x1400020cf  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400020d6  mov     rdx, rdi; wchar_t *
0x1400020d9  mov     rcx, r14; this
0x1400020dc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400020e1  cmp     [rbx+18h], r15
0x1400020e5  jnz     short loc_1400020F7
0x1400020e7  cmp     [rbx+48h], r15
0x1400020eb  jnz     short loc_1400020F7
0x1400020ed  cmp     [rbx+30h], r15
0x1400020f1  jz      loc_140002187
0x1400020f7  lea     r8, asc_140023F30; "    "
0x1400020fe  mov     rdx, rdi; wchar_t *
0x140002101  mov     rcx, rax; this
0x140002104  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140002109  mov     r9, [rbx+18h]; wchar_t *
0x14000210d  test    r9, r9
0x140002110  jz      short loc_140002124
0x140002112  lea     r8, aMsgWs; "Msg:[%ws] "
0x140002119  mov     rdx, rdi; wchar_t *
0x14000211c  mov     rcx, rax; this
0x14000211f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140002124  mov     r9, [rbx+48h]; wchar_t *
0x140002128  test    r9, r9
0x14000212b  jz      short loc_14000213F
0x14000212d  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140002134  mov     rdx, rdi; wchar_t *
0x140002137  mov     rcx, rax; this
0x14000213a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000213f  mov     rcx, [rbx+28h]
0x140002143  mov     r9, [rbx+30h]; wchar_t *
0x140002147  mov     rdx, rdi; wchar_t *
0x14000214a  test    rcx, rcx
0x14000214d  jz      short loc_140002165
0x14000214f  mov     [rsp+278h+lpBuffer], rcx
0x140002154  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000215b  mov     rcx, rax; this
0x14000215e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140002163  jmp     short loc_140002187
0x140002165  mov     rcx, rax; this
0x140002168  test    r9, r9
0x14000216b  jz      short loc_14000217B
0x14000216d  lea     r8, aHs; "[%hs]\n"
0x140002174  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140002179  jmp     short loc_140002187
0x14000217b  lea     r8, asc_140023FA8; "\n"
0x140002182  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140002187  xor     eax, eax
0x140002189  mov     rcx, [rsp+278h+var_38]
0x140002191  xor     rcx, rsp; StackCookie
0x140002194  call    __security_check_cookie
0x140002199  mov     rbx, [rsp+278h+arg_18]
0x1400021a1  add     rsp, 250h
0x1400021a8  pop     r15
0x1400021aa  pop     r14
0x1400021ac  pop     rdi
0x1400021ad  pop     rsi
0x1400021ae  pop     rbp
0x1400021af  retn
```
