# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180048764`
- end: `0x180048a27`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180047c88`
- `0x180048d84`

## callees

- `0x180048764`
- `0x180049098`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180048896`
- `KERNEL32!FormatMessageW` at `0x180048896`
- `KERNEL32!GetCurrentThreadId` at `0x18004891d`
- `KERNEL32!GetCurrentThreadId` at `0x18004891d`

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
          v8 = (const char *)&byte_180081648;
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
0x180048764  mov     [rsp+arg_18], rbx
0x180048769  push    rbp
0x18004876a  push    rsi
0x18004876b  push    rdi
0x18004876c  push    r14
0x18004876e  push    r15
0x180048770  sub     rsp, 250h
0x180048777  mov     rax, cs:__security_cookie
0x18004877e  xor     rax, rsp
0x180048781  mov     [rsp+278h+var_38], rax
0x180048789  xor     r15d, r15d
0x18004878c  mov     rbx, r8
0x18004878f  mov     rsi, rdx
0x180048792  mov     r14, rcx
0x180048795  test    rdx, rdx
0x180048798  jz      loc_1800489FD
0x18004879e  test    rcx, rcx
0x1800487a1  jz      loc_1800489FD
0x1800487a7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800487ae  mov     [rcx], r15w
0x1800487b2  test    rax, rax
0x1800487b5  jz      short loc_1800487D8
0x1800487b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800487be  jz      short loc_1800487D8
0x1800487c0  mov     r8, rdx
0x1800487c3  mov     rdx, rcx
0x1800487c6  mov     rcx, rbx
0x1800487c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487ce  cmp     [r14], r15w
0x1800487d2  jnz     loc_1800489FD
0x1800487d8  mov     ecx, [rbx]
0x1800487da  mov     bpl, 8
0x1800487dd  test    ecx, ecx
0x1800487df  jz      short loc_18004882A
0x1800487e1  sub     ecx, 1
0x1800487e4  jz      short loc_180048812
0x1800487e6  sub     ecx, 1
0x1800487e9  jz      short loc_180048802
0x1800487eb  cmp     ecx, 1
0x1800487ee  jz      short loc_1800487F9
0x1800487f0  lea     rdi, byte_180081648
0x1800487f7  jmp     short loc_180048831
0x1800487f9  lea     rdi, aFailfast; "FailFast"
0x180048800  jmp     short loc_180048831
0x180048802  lea     rax, aLoghr; "LogHr"
0x180048809  lea     rdi, aLognt; "LogNt"
0x180048810  jmp     short loc_180048820
0x180048812  lea     rax, aReturnhr; "ReturnHr"
0x180048819  lea     rdi, aReturnnt; "ReturnNt"
0x180048820  test    [rbx+4], bpl
0x180048824  cmovz   rdi, rax
0x180048828  jmp     short loc_180048831
0x18004882a  lea     rdi, aException; "Exception"
0x180048831  xor     edx, edx; Val
0x180048833  lea     rcx, [rsp+278h+Buffer]; void *
0x180048838  mov     r8d, 200h; Size
0x18004883e  call    memset_0
0x180048843  test    [rbx+4], bpl
0x180048847  jz      short loc_18004886C
0x180048849  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180048850  mov     ebp, [rbx+0Ch]
0x180048853  test    rax, rax
0x180048856  jz      short loc_1800488A2
0x180048858  mov     r8d, 100h
0x18004885e  lea     rdx, [rsp+278h+Buffer]
0x180048863  mov     ecx, ebp
0x180048865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004886a  jmp     short loc_1800488A2
0x18004886c  mov     ebp, [rbx+8]
0x18004886f  lea     rax, [rsp+278h+Buffer]
0x180048874  mov     [rsp+278h+Arguments], r15; Arguments
0x180048879  mov     r8d, ebp; dwMessageId
0x18004887c  mov     [rsp+278h+nSize], 100h; nSize
0x180048884  mov     r9d, 400h; dwLanguageId
0x18004888a  xor     edx, edx; lpSource
0x18004888c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180048891  mov     ecx, 1200h; dwFlags
0x180048896  call    cs:__imp_FormatMessageW
0x18004889d  nop     dword ptr [rax+rax+00h]
0x1800488a2  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800488a6  lea     rsi, [r14+rsi*2]
0x1800488aa  mov     rax, [rbx+88h]
0x1800488b1  mov     rdx, rsi; unsigned __int16 *
0x1800488b4  mov     rcx, [rbx+80h]
0x1800488bb  test    r9, r9
0x1800488be  jz      short loc_1800488E2
0x1800488c0  mov     [rsp+278h+Arguments], rax
0x1800488c5  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800488cc  mov     eax, [rbx+40h]
0x1800488cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800488d4  mov     rcx, r14; this
0x1800488d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800488db  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800488e0  jmp     short loc_1800488F9
0x1800488e2  mov     r9, rcx; unsigned __int16 *
0x1800488e5  mov     [rsp+278h+lpBuffer], rax
0x1800488ea  mov     rcx, r14; this
0x1800488ed  lea     r8, aHsP; "%hs!%p: "
0x1800488f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800488f9  mov     r9, [rbx+90h]; unsigned __int16 *
0x180048900  mov     r14, rax
0x180048903  test    r9, r9
0x180048906  jz      short loc_18004891D
0x180048908  lea     r8, aCallerP; "(caller: %p) "
0x18004890f  mov     rdx, rsi; unsigned __int16 *
0x180048912  mov     rcx, rax; this
0x180048915  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004891a  mov     r14, rax
0x18004891d  call    cs:__imp_GetCurrentThreadId
0x180048924  nop     dword ptr [rax+rax+00h]
0x180048929  lea     rcx, [rsp+278h+Buffer]
0x18004892e  mov     r9, rdi; unsigned __int16 *
0x180048931  mov     [rsp+278h+var_240], rcx
0x180048936  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18004893d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180048941  mov     rdx, rsi; unsigned __int16 *
0x180048944  mov     [rsp+278h+nSize], eax
0x180048948  mov     rcx, r14; this
0x18004894b  mov     eax, [rbx+44h]
0x18004894e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180048952  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180048957  cmp     [rbx+18h], r15
0x18004895b  jnz     short loc_18004896D
0x18004895d  cmp     [rbx+48h], r15
0x180048961  jnz     short loc_18004896D
0x180048963  cmp     [rbx+30h], r15
0x180048967  jz      loc_1800489FD
0x18004896d  lea     r8, asc_180081D38; "    "
0x180048974  mov     rdx, rsi; unsigned __int16 *
0x180048977  mov     rcx, rax; this
0x18004897a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004897f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180048983  test    r9, r9
0x180048986  jz      short loc_18004899A
0x180048988  lea     r8, aMsgWs; "Msg:[%ws] "
0x18004898f  mov     rdx, rsi; unsigned __int16 *
0x180048992  mov     rcx, rax; this
0x180048995  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004899a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18004899e  test    r9, r9
0x1800489a1  jz      short loc_1800489B5
0x1800489a3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800489aa  mov     rdx, rsi; unsigned __int16 *
0x1800489ad  mov     rcx, rax; this
0x1800489b0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800489b5  mov     rcx, [rbx+28h]
0x1800489b9  mov     rdx, rsi; unsigned __int16 *
0x1800489bc  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800489c0  test    rcx, rcx
0x1800489c3  jz      short loc_1800489DB
0x1800489c5  mov     [rsp+278h+lpBuffer], rcx
0x1800489ca  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800489d1  mov     rcx, rax; this
0x1800489d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800489d9  jmp     short loc_1800489FD
0x1800489db  mov     rcx, rax; this
0x1800489de  test    r9, r9
0x1800489e1  jz      short loc_1800489F1
0x1800489e3  lea     r8, aHs; "[%hs]\n"
0x1800489ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800489ef  jmp     short loc_1800489FD
0x1800489f1  lea     r8, asc_18007FF34; "\n"
0x1800489f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800489fd  xor     eax, eax
0x1800489ff  mov     rcx, [rsp+278h+var_38]
0x180048a07  xor     rcx, rsp; StackCookie
0x180048a0a  call    __security_check_cookie
0x180048a0f  mov     rbx, [rsp+278h+arg_18]
0x180048a17  add     rsp, 250h
0x180048a1e  pop     r15
0x180048a20  pop     r14
0x180048a22  pop     rdi
0x180048a23  pop     rsi
0x180048a24  pop     rbp
0x180048a25  retn
```
