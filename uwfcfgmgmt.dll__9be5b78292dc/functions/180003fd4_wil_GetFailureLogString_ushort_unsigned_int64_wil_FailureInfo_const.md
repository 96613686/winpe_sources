# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003fd4`
- end: `0x18000428a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002e54`
- `0x1800030c4`
- `0x18000493c`

## callees

- `0x180003fd4`
- `0x180004c3c`
- `0x18001afe2`
- `0x18001b020`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004187`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004187`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004106`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004106`

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
          v8 = (const char *)&qword_18001F610;
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
0x180003fd4  mov     [rsp+arg_18], rbx
0x180003fd9  push    rbp
0x180003fda  push    rsi
0x180003fdb  push    rdi
0x180003fdc  push    r14
0x180003fde  push    r15
0x180003fe0  sub     rsp, 250h
0x180003fe7  mov     rax, cs:__security_cookie
0x180003fee  xor     rax, rsp
0x180003ff1  mov     [rsp+278h+var_38], rax
0x180003ff9  xor     r15d, r15d
0x180003ffc  mov     rbx, r8
0x180003fff  mov     rsi, rdx
0x180004002  mov     r14, rcx
0x180004005  test    rdx, rdx
0x180004008  jz      loc_180004261
0x18000400e  test    rcx, rcx
0x180004011  jz      loc_180004261
0x180004017  mov     rax, cs:g_pfnResultLoggingCallback
0x18000401e  mov     [rcx], r15w
0x180004022  test    rax, rax
0x180004025  jz      short loc_180004048
0x180004027  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000402e  jz      short loc_180004048
0x180004030  mov     r8, rdx
0x180004033  mov     rdx, rcx
0x180004036  mov     rcx, rbx
0x180004039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000403e  cmp     [r14], r15w
0x180004042  jnz     loc_180004261
0x180004048  mov     ecx, [rbx]
0x18000404a  mov     bpl, 8
0x18000404d  test    ecx, ecx
0x18000404f  jz      short loc_18000409A
0x180004051  sub     ecx, 1
0x180004054  jz      short loc_180004082
0x180004056  sub     ecx, 1
0x180004059  jz      short loc_180004072
0x18000405b  cmp     ecx, 1
0x18000405e  jz      short loc_180004069
0x180004060  lea     rdi, qword_18001F610
0x180004067  jmp     short loc_1800040A1
0x180004069  lea     rdi, aFailfast; "FailFast"
0x180004070  jmp     short loc_1800040A1
0x180004072  lea     rax, aLoghr; "LogHr"
0x180004079  lea     rdi, aLognt; "LogNt"
0x180004080  jmp     short loc_180004090
0x180004082  lea     rax, aReturnhr; "ReturnHr"
0x180004089  lea     rdi, aReturnnt; "ReturnNt"
0x180004090  test    [rbx+4], bpl
0x180004094  cmovz   rdi, rax
0x180004098  jmp     short loc_1800040A1
0x18000409a  lea     rdi, aException; "Exception"
0x1800040a1  xor     edx, edx; Val
0x1800040a3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800040a8  mov     r8d, 200h; Size
0x1800040ae  call    memset_0
0x1800040b3  test    [rbx+4], bpl
0x1800040b7  jz      short loc_1800040DC
0x1800040b9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800040c0  mov     ebp, [rbx+0Ch]
0x1800040c3  test    rax, rax
0x1800040c6  jz      short loc_18000410C
0x1800040c8  mov     r8d, 100h
0x1800040ce  lea     rdx, [rsp+278h+Buffer]
0x1800040d3  mov     ecx, ebp
0x1800040d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040da  jmp     short loc_18000410C
0x1800040dc  mov     ebp, [rbx+8]
0x1800040df  lea     rax, [rsp+278h+Buffer]
0x1800040e4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800040e9  mov     r8d, ebp; dwMessageId
0x1800040ec  mov     [rsp+278h+nSize], 100h; nSize
0x1800040f4  mov     r9d, 400h; dwLanguageId
0x1800040fa  xor     edx, edx; lpSource
0x1800040fc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004101  mov     ecx, 1200h; dwFlags
0x180004106  call    cs:__imp_FormatMessageW
0x18000410c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004110  lea     rsi, [r14+rsi*2]
0x180004114  mov     rax, [rbx+88h]
0x18000411b  mov     rdx, rsi; unsigned __int16 *
0x18000411e  mov     rcx, [rbx+80h]
0x180004125  test    r9, r9
0x180004128  jz      short loc_18000414C
0x18000412a  mov     [rsp+278h+Arguments], rax
0x18000412f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004136  mov     eax, [rbx+40h]
0x180004139  mov     qword ptr [rsp+278h+nSize], rcx
0x18000413e  mov     rcx, r14; this
0x180004141  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004145  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000414a  jmp     short loc_180004163
0x18000414c  mov     r9, rcx; unsigned __int16 *
0x18000414f  mov     [rsp+278h+lpBuffer], rax
0x180004154  mov     rcx, r14; this
0x180004157  lea     r8, aHsP; "%hs!%p: "
0x18000415e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004163  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000416a  mov     r14, rax
0x18000416d  test    r9, r9
0x180004170  jz      short loc_180004187
0x180004172  lea     r8, aCallerP; "(caller: %p) "
0x180004179  mov     rdx, rsi; unsigned __int16 *
0x18000417c  mov     rcx, rax; this
0x18000417f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004184  mov     r14, rax
0x180004187  call    cs:__imp_GetCurrentThreadId
0x18000418d  lea     rcx, [rsp+278h+Buffer]
0x180004192  mov     r9, rdi; unsigned __int16 *
0x180004195  mov     [rsp+278h+var_240], rcx
0x18000419a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800041a1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800041a5  mov     rdx, rsi; unsigned __int16 *
0x1800041a8  mov     [rsp+278h+nSize], eax
0x1800041ac  mov     rcx, r14; this
0x1800041af  mov     eax, [rbx+44h]
0x1800041b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800041b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041bb  cmp     [rbx+18h], r15
0x1800041bf  jnz     short loc_1800041D1
0x1800041c1  cmp     [rbx+48h], r15
0x1800041c5  jnz     short loc_1800041D1
0x1800041c7  cmp     [rbx+30h], r15
0x1800041cb  jz      loc_180004261
0x1800041d1  lea     r8, asc_18001F700; "    "
0x1800041d8  mov     rdx, rsi; unsigned __int16 *
0x1800041db  mov     rcx, rax; this
0x1800041de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800041e7  test    r9, r9
0x1800041ea  jz      short loc_1800041FE
0x1800041ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800041f3  mov     rdx, rsi; unsigned __int16 *
0x1800041f6  mov     rcx, rax; this
0x1800041f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004202  test    r9, r9
0x180004205  jz      short loc_180004219
0x180004207  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000420e  mov     rdx, rsi; unsigned __int16 *
0x180004211  mov     rcx, rax; this
0x180004214  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004219  mov     rcx, [rbx+28h]
0x18000421d  mov     rdx, rsi; unsigned __int16 *
0x180004220  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004224  test    rcx, rcx
0x180004227  jz      short loc_18000423F
0x180004229  mov     [rsp+278h+lpBuffer], rcx
0x18000422e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004235  mov     rcx, rax; this
0x180004238  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000423d  jmp     short loc_180004261
0x18000423f  mov     rcx, rax; this
0x180004242  test    r9, r9
0x180004245  jz      short loc_180004255
0x180004247  lea     r8, aHs; "[%hs]\n"
0x18000424e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004253  jmp     short loc_180004261
0x180004255  lea     r8, asc_18001F778; "\n"
0x18000425c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004261  xor     eax, eax
0x180004263  mov     rcx, [rsp+278h+var_38]
0x18000426b  xor     rcx, rsp; StackCookie
0x18000426e  call    __security_check_cookie
0x180004273  mov     rbx, [rsp+278h+arg_18]
0x18000427b  add     rsp, 250h
0x180004282  pop     r15
0x180004284  pop     r14
0x180004286  pop     rdi
0x180004287  pop     rsi
0x180004288  pop     rbp
0x180004289  retn
```
