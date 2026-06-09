# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004fe4`
- end: `0x18000529a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180006520`
- `0x180007210`
- `0x180007478`
- `0x18000770c`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180004fe4`
- `0x180005590`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005197`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005116`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005116`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
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
          v7 = (const char *)&word_180039412;
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
0x180004fe4  mov     [rsp+arg_18], rbx
0x180004fe9  push    rbp
0x180004fea  push    rsi
0x180004feb  push    rdi
0x180004fec  push    r14
0x180004fee  push    r15
0x180004ff0  sub     rsp, 250h
0x180004ff7  mov     rax, cs:__security_cookie
0x180004ffe  xor     rax, rsp
0x180005001  mov     [rsp+278h+var_38], rax
0x180005009  mov     rbx, r8
0x18000500c  mov     rsi, rdx
0x18000500f  mov     r14, rcx
0x180005012  xor     r15d, r15d
0x180005015  test    rdx, rdx
0x180005018  jz      loc_180005271
0x18000501e  test    rcx, rcx
0x180005021  jz      loc_180005271
0x180005027  mov     [rcx], r15w
0x18000502b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005032  test    rax, rax
0x180005035  jz      short loc_180005058
0x180005037  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000503e  jz      short loc_180005058
0x180005040  mov     r8, rdx
0x180005043  mov     rdx, rcx
0x180005046  mov     rcx, rbx
0x180005049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504e  cmp     [r14], r15w
0x180005052  jnz     loc_180005271
0x180005058  mov     ecx, [rbx]
0x18000505a  mov     bpl, 8
0x18000505d  test    ecx, ecx
0x18000505f  jz      short loc_1800050AA
0x180005061  sub     ecx, 1
0x180005064  jz      short loc_180005092
0x180005066  sub     ecx, 1
0x180005069  jz      short loc_180005082
0x18000506b  cmp     ecx, 1
0x18000506e  jz      short loc_180005079
0x180005070  lea     rdi, word_180039412
0x180005077  jmp     short loc_1800050B1
0x180005079  lea     rdi, aFailfast; "FailFast"
0x180005080  jmp     short loc_1800050B1
0x180005082  lea     rax, aLoghr; "LogHr"
0x180005089  lea     rdi, aLognt; "LogNt"
0x180005090  jmp     short loc_1800050A0
0x180005092  lea     rax, aReturnhr; "ReturnHr"
0x180005099  lea     rdi, aReturnnt; "ReturnNt"
0x1800050a0  test    [rbx+4], bpl
0x1800050a4  cmovz   rdi, rax
0x1800050a8  jmp     short loc_1800050B1
0x1800050aa  lea     rdi, aException; "Exception"
0x1800050b1  xor     edx, edx; Val
0x1800050b3  mov     r8d, 200h; Size
0x1800050b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800050be  call    memset_0
0x1800050c3  test    [rbx+4], bpl
0x1800050c7  jz      short loc_1800050EC
0x1800050c9  mov     ebp, [rbx+0Ch]
0x1800050cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800050d3  test    rax, rax
0x1800050d6  jz      short loc_18000511C
0x1800050d8  mov     r8d, 100h
0x1800050de  lea     rdx, [rsp+278h+Buffer]
0x1800050e3  mov     ecx, ebp
0x1800050e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ea  jmp     short loc_18000511C
0x1800050ec  mov     ebp, [rbx+8]
0x1800050ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800050f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800050fc  lea     rax, [rsp+278h+Buffer]
0x180005101  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005106  mov     r9d, 400h; dwLanguageId
0x18000510c  mov     r8d, ebp; dwMessageId
0x18000510f  xor     edx, edx; lpSource
0x180005111  mov     ecx, 1200h; dwFlags
0x180005116  call    cs:__imp_FormatMessageW
0x18000511c  lea     rsi, [r14+rsi*2]
0x180005120  mov     r9, [rbx+38h]; wchar_t *
0x180005124  mov     rax, [rbx+88h]
0x18000512b  mov     rcx, [rbx+80h]
0x180005132  mov     rdx, rsi; wchar_t *
0x180005135  test    r9, r9
0x180005138  jz      short loc_18000515C
0x18000513a  mov     [rsp+278h+Arguments], rax
0x18000513f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005144  mov     eax, [rbx+40h]
0x180005147  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000514b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005152  mov     rcx, r14; this
0x180005155  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000515a  jmp     short loc_180005173
0x18000515c  mov     [rsp+278h+lpBuffer], rax
0x180005161  mov     r9, rcx; wchar_t *
0x180005164  lea     r8, aHsP; "%hs!%p: "
0x18000516b  mov     rcx, r14; this
0x18000516e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005173  mov     r14, rax
0x180005176  mov     r9, [rbx+90h]; wchar_t *
0x18000517d  test    r9, r9
0x180005180  jz      short loc_180005197
0x180005182  lea     r8, aCallerP; "(caller: %p) "
0x180005189  mov     rdx, rsi; wchar_t *
0x18000518c  mov     rcx, rax; this
0x18000518f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005194  mov     r14, rax
0x180005197  call    cs:__imp_GetCurrentThreadId
0x18000519d  lea     rcx, [rsp+278h+Buffer]
0x1800051a2  mov     [rsp+278h+var_240], rcx
0x1800051a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800051ab  mov     [rsp+278h+nSize], eax
0x1800051af  mov     eax, [rbx+44h]
0x1800051b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800051b6  mov     r9, rdi; wchar_t *
0x1800051b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800051c0  mov     rdx, rsi; wchar_t *
0x1800051c3  mov     rcx, r14; this
0x1800051c6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800051cb  cmp     [rbx+18h], r15
0x1800051cf  jnz     short loc_1800051E1
0x1800051d1  cmp     [rbx+48h], r15
0x1800051d5  jnz     short loc_1800051E1
0x1800051d7  cmp     [rbx+30h], r15
0x1800051db  jz      loc_180005271
0x1800051e1  lea     r8, asc_180039518; "    "
0x1800051e8  mov     rdx, rsi; wchar_t *
0x1800051eb  mov     rcx, rax; this
0x1800051ee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800051f3  mov     r9, [rbx+18h]; wchar_t *
0x1800051f7  test    r9, r9
0x1800051fa  jz      short loc_18000520E
0x1800051fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005203  mov     rdx, rsi; wchar_t *
0x180005206  mov     rcx, rax; this
0x180005209  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000520e  mov     r9, [rbx+48h]; wchar_t *
0x180005212  test    r9, r9
0x180005215  jz      short loc_180005229
0x180005217  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000521e  mov     rdx, rsi; wchar_t *
0x180005221  mov     rcx, rax; this
0x180005224  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005229  mov     rcx, [rbx+28h]
0x18000522d  mov     r9, [rbx+30h]; wchar_t *
0x180005231  mov     rdx, rsi; wchar_t *
0x180005234  test    rcx, rcx
0x180005237  jz      short loc_18000524F
0x180005239  mov     [rsp+278h+lpBuffer], rcx
0x18000523e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005245  mov     rcx, rax; this
0x180005248  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000524d  jmp     short loc_180005271
0x18000524f  mov     rcx, rax; this
0x180005252  test    r9, r9
0x180005255  jz      short loc_180005265
0x180005257  lea     r8, aHs; "[%hs]\n"
0x18000525e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005263  jmp     short loc_180005271
0x180005265  lea     r8, asc_180039590; "\n"
0x18000526c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005271  xor     eax, eax
0x180005273  mov     rcx, [rsp+278h+var_38]
0x18000527b  xor     rcx, rsp; StackCookie
0x18000527e  call    __security_check_cookie
0x180005283  mov     rbx, [rsp+278h+arg_18]
0x18000528b  add     rsp, 250h
0x180005292  pop     r15
0x180005294  pop     r14
0x180005296  pop     rdi
0x180005297  pop     rsi
0x180005298  pop     rbp
0x180005299  retn
```
