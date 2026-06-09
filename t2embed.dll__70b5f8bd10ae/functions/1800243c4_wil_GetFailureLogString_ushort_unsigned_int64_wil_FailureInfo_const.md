# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800243c4`
- end: `0x18002467a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180024d0c`

## callees

- `0x1800243c4`
- `0x180025008`
- `0x18002a566`
- `0x18002a590`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180024577`
- `KERNEL32!GetCurrentThreadId` at `0x180024577`
- `KERNEL32!FormatMessageW` at `0x1800244f6`
- `KERNEL32!FormatMessageW` at `0x1800244f6`

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
          v8 = &Class;
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
0x1800243c4  mov     [rsp+arg_18], rbx
0x1800243c9  push    rbp
0x1800243ca  push    rsi
0x1800243cb  push    rdi
0x1800243cc  push    r14
0x1800243ce  push    r15
0x1800243d0  sub     rsp, 250h
0x1800243d7  mov     rax, cs:__security_cookie
0x1800243de  xor     rax, rsp
0x1800243e1  mov     [rsp+278h+var_38], rax
0x1800243e9  xor     r15d, r15d
0x1800243ec  mov     rbx, r8
0x1800243ef  mov     rsi, rdx
0x1800243f2  mov     r14, rcx
0x1800243f5  test    rdx, rdx
0x1800243f8  jz      loc_180024651
0x1800243fe  test    rcx, rcx
0x180024401  jz      loc_180024651
0x180024407  mov     rax, cs:g_pfnResultLoggingCallback
0x18002440e  mov     [rcx], r15w
0x180024412  test    rax, rax
0x180024415  jz      short loc_180024438
0x180024417  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002441e  jz      short loc_180024438
0x180024420  mov     r8, rdx
0x180024423  mov     rdx, rcx
0x180024426  mov     rcx, rbx
0x180024429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002442e  cmp     [r14], r15w
0x180024432  jnz     loc_180024651
0x180024438  mov     ecx, [rbx]
0x18002443a  mov     bpl, 8
0x18002443d  test    ecx, ecx
0x18002443f  jz      short loc_18002448A
0x180024441  sub     ecx, 1
0x180024444  jz      short loc_180024472
0x180024446  sub     ecx, 1
0x180024449  jz      short loc_180024462
0x18002444b  cmp     ecx, 1
0x18002444e  jz      short loc_180024459
0x180024450  lea     rdi, Class
0x180024457  jmp     short loc_180024491
0x180024459  lea     rdi, aFailfast; "FailFast"
0x180024460  jmp     short loc_180024491
0x180024462  lea     rax, aLoghr; "LogHr"
0x180024469  lea     rdi, aLognt; "LogNt"
0x180024470  jmp     short loc_180024480
0x180024472  lea     rax, aReturnhr; "ReturnHr"
0x180024479  lea     rdi, aReturnnt; "ReturnNt"
0x180024480  test    [rbx+4], bpl
0x180024484  cmovz   rdi, rax
0x180024488  jmp     short loc_180024491
0x18002448a  lea     rdi, aException; "Exception"
0x180024491  xor     edx, edx; Val
0x180024493  lea     rcx, [rsp+278h+Buffer]; void *
0x180024498  mov     r8d, 200h; Size
0x18002449e  call    memset_0
0x1800244a3  test    [rbx+4], bpl
0x1800244a7  jz      short loc_1800244CC
0x1800244a9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800244b0  mov     ebp, [rbx+0Ch]
0x1800244b3  test    rax, rax
0x1800244b6  jz      short loc_1800244FC
0x1800244b8  mov     r8d, 100h
0x1800244be  lea     rdx, [rsp+278h+Buffer]
0x1800244c3  mov     ecx, ebp
0x1800244c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244ca  jmp     short loc_1800244FC
0x1800244cc  mov     ebp, [rbx+8]
0x1800244cf  lea     rax, [rsp+278h+Buffer]
0x1800244d4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800244d9  mov     r8d, ebp; dwMessageId
0x1800244dc  mov     [rsp+278h+nSize], 100h; nSize
0x1800244e4  mov     r9d, 400h; dwLanguageId
0x1800244ea  xor     edx, edx; lpSource
0x1800244ec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800244f1  mov     ecx, 1200h; dwFlags
0x1800244f6  call    cs:__imp_FormatMessageW
0x1800244fc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180024500  lea     rsi, [r14+rsi*2]
0x180024504  mov     rax, [rbx+88h]
0x18002450b  mov     rdx, rsi; unsigned __int16 *
0x18002450e  mov     rcx, [rbx+80h]
0x180024515  test    r9, r9
0x180024518  jz      short loc_18002453C
0x18002451a  mov     [rsp+278h+Arguments], rax
0x18002451f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180024526  mov     eax, [rbx+40h]
0x180024529  mov     qword ptr [rsp+278h+nSize], rcx
0x18002452e  mov     rcx, r14; this
0x180024531  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180024535  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002453a  jmp     short loc_180024553
0x18002453c  mov     r9, rcx; unsigned __int16 *
0x18002453f  mov     [rsp+278h+lpBuffer], rax
0x180024544  mov     rcx, r14; this
0x180024547  lea     r8, aHsP; "%hs!%p: "
0x18002454e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024553  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002455a  mov     r14, rax
0x18002455d  test    r9, r9
0x180024560  jz      short loc_180024577
0x180024562  lea     r8, aCallerP; "(caller: %p) "
0x180024569  mov     rdx, rsi; unsigned __int16 *
0x18002456c  mov     rcx, rax; this
0x18002456f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024574  mov     r14, rax
0x180024577  call    cs:__imp_GetCurrentThreadId
0x18002457d  lea     rcx, [rsp+278h+Buffer]
0x180024582  mov     r9, rdi; unsigned __int16 *
0x180024585  mov     [rsp+278h+var_240], rcx
0x18002458a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180024591  mov     dword ptr [rsp+278h+Arguments], ebp
0x180024595  mov     rdx, rsi; unsigned __int16 *
0x180024598  mov     [rsp+278h+nSize], eax
0x18002459c  mov     rcx, r14; this
0x18002459f  mov     eax, [rbx+44h]
0x1800245a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800245a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800245ab  cmp     [rbx+18h], r15
0x1800245af  jnz     short loc_1800245C1
0x1800245b1  cmp     [rbx+48h], r15
0x1800245b5  jnz     short loc_1800245C1
0x1800245b7  cmp     [rbx+30h], r15
0x1800245bb  jz      loc_180024651
0x1800245c1  lea     r8, asc_18002CBA0; "    "
0x1800245c8  mov     rdx, rsi; unsigned __int16 *
0x1800245cb  mov     rcx, rax; this
0x1800245ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800245d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800245d7  test    r9, r9
0x1800245da  jz      short loc_1800245EE
0x1800245dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800245e3  mov     rdx, rsi; unsigned __int16 *
0x1800245e6  mov     rcx, rax; this
0x1800245e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800245ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800245f2  test    r9, r9
0x1800245f5  jz      short loc_180024609
0x1800245f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800245fe  mov     rdx, rsi; unsigned __int16 *
0x180024601  mov     rcx, rax; this
0x180024604  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024609  mov     rcx, [rbx+28h]
0x18002460d  mov     rdx, rsi; unsigned __int16 *
0x180024610  mov     r9, [rbx+30h]; unsigned __int16 *
0x180024614  test    rcx, rcx
0x180024617  jz      short loc_18002462F
0x180024619  mov     [rsp+278h+lpBuffer], rcx
0x18002461e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180024625  mov     rcx, rax; this
0x180024628  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002462d  jmp     short loc_180024651
0x18002462f  mov     rcx, rax; this
0x180024632  test    r9, r9
0x180024635  jz      short loc_180024645
0x180024637  lea     r8, aHs; "[%hs]\n"
0x18002463e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024643  jmp     short loc_180024651
0x180024645  lea     r8, asc_18002CC18; "\n"
0x18002464c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024651  xor     eax, eax
0x180024653  mov     rcx, [rsp+278h+var_38]
0x18002465b  xor     rcx, rsp; StackCookie
0x18002465e  call    __security_check_cookie
0x180024663  mov     rbx, [rsp+278h+arg_18]
0x18002466b  add     rsp, 250h
0x180024672  pop     r15
0x180024674  pop     r14
0x180024676  pop     rdi
0x180024677  pop     rsi
0x180024678  pop     rbp
0x180024679  retn
```
