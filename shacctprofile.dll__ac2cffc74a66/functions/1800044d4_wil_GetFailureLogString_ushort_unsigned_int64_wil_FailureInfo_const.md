# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800044d4`
- end: `0x18000478a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000344c`
- `0x1800036bc`
- `0x180004e30`

## callees

- `0x180002230`
- `0x180002b8e`
- `0x1800044d4`
- `0x180005130`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004687`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004687`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004606`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004606`

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
          v8 = (const char *)&word_18000BE00;
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
0x1800044d4  mov     [rsp+arg_18], rbx
0x1800044d9  push    rbp
0x1800044da  push    rsi
0x1800044db  push    rdi
0x1800044dc  push    r14
0x1800044de  push    r15
0x1800044e0  sub     rsp, 250h
0x1800044e7  mov     rax, cs:__security_cookie
0x1800044ee  xor     rax, rsp
0x1800044f1  mov     [rsp+278h+var_38], rax
0x1800044f9  xor     r15d, r15d
0x1800044fc  mov     rbx, r8
0x1800044ff  mov     rsi, rdx
0x180004502  mov     r14, rcx
0x180004505  test    rdx, rdx
0x180004508  jz      loc_180004761
0x18000450e  test    rcx, rcx
0x180004511  jz      loc_180004761
0x180004517  mov     rax, cs:g_pfnResultLoggingCallback
0x18000451e  mov     [rcx], r15w
0x180004522  test    rax, rax
0x180004525  jz      short loc_180004548
0x180004527  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000452e  jz      short loc_180004548
0x180004530  mov     r8, rdx
0x180004533  mov     rdx, rcx
0x180004536  mov     rcx, rbx
0x180004539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000453e  cmp     [r14], r15w
0x180004542  jnz     loc_180004761
0x180004548  mov     ecx, [rbx]
0x18000454a  mov     bpl, 8
0x18000454d  test    ecx, ecx
0x18000454f  jz      short loc_18000459A
0x180004551  sub     ecx, 1
0x180004554  jz      short loc_180004582
0x180004556  sub     ecx, 1
0x180004559  jz      short loc_180004572
0x18000455b  cmp     ecx, 1
0x18000455e  jz      short loc_180004569
0x180004560  lea     rdi, word_18000BE00
0x180004567  jmp     short loc_1800045A1
0x180004569  lea     rdi, aFailfast; "FailFast"
0x180004570  jmp     short loc_1800045A1
0x180004572  lea     rax, aLoghr; "LogHr"
0x180004579  lea     rdi, aLognt; "LogNt"
0x180004580  jmp     short loc_180004590
0x180004582  lea     rax, aReturnhr; "ReturnHr"
0x180004589  lea     rdi, aReturnnt; "ReturnNt"
0x180004590  test    [rbx+4], bpl
0x180004594  cmovz   rdi, rax
0x180004598  jmp     short loc_1800045A1
0x18000459a  lea     rdi, aException; "Exception"
0x1800045a1  xor     edx, edx; Val
0x1800045a3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800045a8  mov     r8d, 200h; Size
0x1800045ae  call    memset_0
0x1800045b3  test    [rbx+4], bpl
0x1800045b7  jz      short loc_1800045DC
0x1800045b9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800045c0  mov     ebp, [rbx+0Ch]
0x1800045c3  test    rax, rax
0x1800045c6  jz      short loc_18000460C
0x1800045c8  mov     r8d, 100h
0x1800045ce  lea     rdx, [rsp+278h+Buffer]
0x1800045d3  mov     ecx, ebp
0x1800045d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045da  jmp     short loc_18000460C
0x1800045dc  mov     ebp, [rbx+8]
0x1800045df  lea     rax, [rsp+278h+Buffer]
0x1800045e4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800045e9  mov     r8d, ebp; dwMessageId
0x1800045ec  mov     [rsp+278h+nSize], 100h; nSize
0x1800045f4  mov     r9d, 400h; dwLanguageId
0x1800045fa  xor     edx, edx; lpSource
0x1800045fc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004601  mov     ecx, 1200h; dwFlags
0x180004606  call    cs:__imp_FormatMessageW
0x18000460c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004610  lea     rsi, [r14+rsi*2]
0x180004614  mov     rax, [rbx+88h]
0x18000461b  mov     rdx, rsi; unsigned __int16 *
0x18000461e  mov     rcx, [rbx+80h]
0x180004625  test    r9, r9
0x180004628  jz      short loc_18000464C
0x18000462a  mov     [rsp+278h+Arguments], rax
0x18000462f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004636  mov     eax, [rbx+40h]
0x180004639  mov     qword ptr [rsp+278h+nSize], rcx
0x18000463e  mov     rcx, r14; this
0x180004641  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004645  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000464a  jmp     short loc_180004663
0x18000464c  mov     r9, rcx; unsigned __int16 *
0x18000464f  mov     [rsp+278h+lpBuffer], rax
0x180004654  mov     rcx, r14; this
0x180004657  lea     r8, aHsP; "%hs!%p: "
0x18000465e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004663  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000466a  mov     r14, rax
0x18000466d  test    r9, r9
0x180004670  jz      short loc_180004687
0x180004672  lea     r8, aCallerP; "(caller: %p) "
0x180004679  mov     rdx, rsi; unsigned __int16 *
0x18000467c  mov     rcx, rax; this
0x18000467f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004684  mov     r14, rax
0x180004687  call    cs:__imp_GetCurrentThreadId
0x18000468d  lea     rcx, [rsp+278h+Buffer]
0x180004692  mov     r9, rdi; unsigned __int16 *
0x180004695  mov     [rsp+278h+var_240], rcx
0x18000469a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800046a1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800046a5  mov     rdx, rsi; unsigned __int16 *
0x1800046a8  mov     [rsp+278h+nSize], eax
0x1800046ac  mov     rcx, r14; this
0x1800046af  mov     eax, [rbx+44h]
0x1800046b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800046b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046bb  cmp     [rbx+18h], r15
0x1800046bf  jnz     short loc_1800046D1
0x1800046c1  cmp     [rbx+48h], r15
0x1800046c5  jnz     short loc_1800046D1
0x1800046c7  cmp     [rbx+30h], r15
0x1800046cb  jz      loc_180004761
0x1800046d1  lea     r8, asc_18000BEF0; "    "
0x1800046d8  mov     rdx, rsi; unsigned __int16 *
0x1800046db  mov     rcx, rax; this
0x1800046de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800046e7  test    r9, r9
0x1800046ea  jz      short loc_1800046FE
0x1800046ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800046f3  mov     rdx, rsi; unsigned __int16 *
0x1800046f6  mov     rcx, rax; this
0x1800046f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004702  test    r9, r9
0x180004705  jz      short loc_180004719
0x180004707  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000470e  mov     rdx, rsi; unsigned __int16 *
0x180004711  mov     rcx, rax; this
0x180004714  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004719  mov     rcx, [rbx+28h]
0x18000471d  mov     rdx, rsi; unsigned __int16 *
0x180004720  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004724  test    rcx, rcx
0x180004727  jz      short loc_18000473F
0x180004729  mov     [rsp+278h+lpBuffer], rcx
0x18000472e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004735  mov     rcx, rax; this
0x180004738  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000473d  jmp     short loc_180004761
0x18000473f  mov     rcx, rax; this
0x180004742  test    r9, r9
0x180004745  jz      short loc_180004755
0x180004747  lea     r8, aHs; "[%hs]\n"
0x18000474e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004753  jmp     short loc_180004761
0x180004755  lea     r8, asc_18000BF68; "\n"
0x18000475c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004761  xor     eax, eax
0x180004763  mov     rcx, [rsp+278h+var_38]
0x18000476b  xor     rcx, rsp; StackCookie
0x18000476e  call    __security_check_cookie
0x180004773  mov     rbx, [rsp+278h+arg_18]
0x18000477b  add     rsp, 250h
0x180004782  pop     r15
0x180004784  pop     r14
0x180004786  pop     rdi
0x180004787  pop     rsi
0x180004788  pop     rbp
0x180004789  retn
```
