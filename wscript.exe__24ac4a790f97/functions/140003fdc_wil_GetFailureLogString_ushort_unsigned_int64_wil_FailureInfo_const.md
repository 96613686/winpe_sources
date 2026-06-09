# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003fdc`
- end: `0x140004292`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400031fc`
- `0x140003464`
- `0x140004664`

## callees

- `0x140003fdc`
- `0x140004964`
- `0x14001755a`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000418f`
- `KERNEL32!GetCurrentThreadId` at `0x14000418f`
- `KERNEL32!FormatMessageW` at `0x14000410e`
- `KERNEL32!FormatMessageW` at `0x14000410e`

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
          v8 = (const char *)&dword_14001AEA4;
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
0x140003fdc  mov     [rsp+arg_18], rbx
0x140003fe1  push    rbp
0x140003fe2  push    rsi
0x140003fe3  push    rdi
0x140003fe4  push    r14
0x140003fe6  push    r15
0x140003fe8  sub     rsp, 250h
0x140003fef  mov     rax, cs:__security_cookie
0x140003ff6  xor     rax, rsp
0x140003ff9  mov     [rsp+278h+var_38], rax
0x140004001  xor     r15d, r15d
0x140004004  mov     rbx, r8
0x140004007  mov     rsi, rdx
0x14000400a  mov     r14, rcx
0x14000400d  test    rdx, rdx
0x140004010  jz      loc_140004269
0x140004016  test    rcx, rcx
0x140004019  jz      loc_140004269
0x14000401f  mov     rax, cs:g_pfnResultLoggingCallback
0x140004026  mov     [rcx], r15w
0x14000402a  test    rax, rax
0x14000402d  jz      short loc_140004050
0x14000402f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004036  jz      short loc_140004050
0x140004038  mov     r8, rdx
0x14000403b  mov     rdx, rcx
0x14000403e  mov     rcx, rbx
0x140004041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004046  cmp     [r14], r15w
0x14000404a  jnz     loc_140004269
0x140004050  mov     ecx, [rbx]
0x140004052  mov     bpl, 8
0x140004055  test    ecx, ecx
0x140004057  jz      short loc_1400040A2
0x140004059  sub     ecx, 1
0x14000405c  jz      short loc_14000408A
0x14000405e  sub     ecx, 1
0x140004061  jz      short loc_14000407A
0x140004063  cmp     ecx, 1
0x140004066  jz      short loc_140004071
0x140004068  lea     rdi, dword_14001AEA4
0x14000406f  jmp     short loc_1400040A9
0x140004071  lea     rdi, aFailfast; "FailFast"
0x140004078  jmp     short loc_1400040A9
0x14000407a  lea     rax, aLoghr; "LogHr"
0x140004081  lea     rdi, aLognt; "LogNt"
0x140004088  jmp     short loc_140004098
0x14000408a  lea     rax, aReturnhr; "ReturnHr"
0x140004091  lea     rdi, aReturnnt; "ReturnNt"
0x140004098  test    [rbx+4], bpl
0x14000409c  cmovz   rdi, rax
0x1400040a0  jmp     short loc_1400040A9
0x1400040a2  lea     rdi, aException; "Exception"
0x1400040a9  xor     edx, edx; Val
0x1400040ab  lea     rcx, [rsp+278h+Buffer]; void *
0x1400040b0  mov     r8d, 200h; Size
0x1400040b6  call    memset_0
0x1400040bb  test    [rbx+4], bpl
0x1400040bf  jz      short loc_1400040E4
0x1400040c1  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400040c8  mov     ebp, [rbx+0Ch]
0x1400040cb  test    rax, rax
0x1400040ce  jz      short loc_140004114
0x1400040d0  mov     r8d, 100h
0x1400040d6  lea     rdx, [rsp+278h+Buffer]
0x1400040db  mov     ecx, ebp
0x1400040dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040e2  jmp     short loc_140004114
0x1400040e4  mov     ebp, [rbx+8]
0x1400040e7  lea     rax, [rsp+278h+Buffer]
0x1400040ec  mov     [rsp+278h+Arguments], r15; Arguments
0x1400040f1  mov     r8d, ebp; dwMessageId
0x1400040f4  mov     [rsp+278h+nSize], 100h; nSize
0x1400040fc  mov     r9d, 400h; dwLanguageId
0x140004102  xor     edx, edx; lpSource
0x140004104  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004109  mov     ecx, 1200h; dwFlags
0x14000410e  call    cs:__imp_FormatMessageW
0x140004114  mov     r9, [rbx+38h]; unsigned __int16 *
0x140004118  lea     rsi, [r14+rsi*2]
0x14000411c  mov     rax, [rbx+88h]
0x140004123  mov     rdx, rsi; unsigned __int16 *
0x140004126  mov     rcx, [rbx+80h]
0x14000412d  test    r9, r9
0x140004130  jz      short loc_140004154
0x140004132  mov     [rsp+278h+Arguments], rax
0x140004137  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000413e  mov     eax, [rbx+40h]
0x140004141  mov     qword ptr [rsp+278h+nSize], rcx
0x140004146  mov     rcx, r14; this
0x140004149  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000414d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004152  jmp     short loc_14000416B
0x140004154  mov     r9, rcx; unsigned __int16 *
0x140004157  mov     [rsp+278h+lpBuffer], rax
0x14000415c  mov     rcx, r14; this
0x14000415f  lea     r8, aHsP; "%hs!%p: "
0x140004166  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000416b  mov     r9, [rbx+90h]; unsigned __int16 *
0x140004172  mov     r14, rax
0x140004175  test    r9, r9
0x140004178  jz      short loc_14000418F
0x14000417a  lea     r8, aCallerP; "(caller: %p) "
0x140004181  mov     rdx, rsi; unsigned __int16 *
0x140004184  mov     rcx, rax; this
0x140004187  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000418c  mov     r14, rax
0x14000418f  call    cs:__imp_GetCurrentThreadId
0x140004195  lea     rcx, [rsp+278h+Buffer]
0x14000419a  mov     r9, rdi; unsigned __int16 *
0x14000419d  mov     [rsp+278h+var_240], rcx
0x1400041a2  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400041a9  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400041ad  mov     rdx, rsi; unsigned __int16 *
0x1400041b0  mov     [rsp+278h+nSize], eax
0x1400041b4  mov     rcx, r14; this
0x1400041b7  mov     eax, [rbx+44h]
0x1400041ba  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400041be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400041c3  cmp     [rbx+18h], r15
0x1400041c7  jnz     short loc_1400041D9
0x1400041c9  cmp     [rbx+48h], r15
0x1400041cd  jnz     short loc_1400041D9
0x1400041cf  cmp     [rbx+30h], r15
0x1400041d3  jz      loc_140004269
0x1400041d9  lea     r8, asc_14001AF90; "    "
0x1400041e0  mov     rdx, rsi; unsigned __int16 *
0x1400041e3  mov     rcx, rax; this
0x1400041e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400041eb  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400041ef  test    r9, r9
0x1400041f2  jz      short loc_140004206
0x1400041f4  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400041fb  mov     rdx, rsi; unsigned __int16 *
0x1400041fe  mov     rcx, rax; this
0x140004201  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004206  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000420a  test    r9, r9
0x14000420d  jz      short loc_140004221
0x14000420f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140004216  mov     rdx, rsi; unsigned __int16 *
0x140004219  mov     rcx, rax; this
0x14000421c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004221  mov     rcx, [rbx+28h]
0x140004225  mov     rdx, rsi; unsigned __int16 *
0x140004228  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000422c  test    rcx, rcx
0x14000422f  jz      short loc_140004247
0x140004231  mov     [rsp+278h+lpBuffer], rcx
0x140004236  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000423d  mov     rcx, rax; this
0x140004240  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004245  jmp     short loc_140004269
0x140004247  mov     rcx, rax; this
0x14000424a  test    r9, r9
0x14000424d  jz      short loc_14000425D
0x14000424f  lea     r8, aHs; "[%hs]\n"
0x140004256  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000425b  jmp     short loc_140004269
0x14000425d  lea     r8, asc_14001B008; "\n"
0x140004264  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004269  xor     eax, eax
0x14000426b  mov     rcx, [rsp+278h+var_38]
0x140004273  xor     rcx, rsp; StackCookie
0x140004276  call    __security_check_cookie
0x14000427b  mov     rbx, [rsp+278h+arg_18]
0x140004283  add     rsp, 250h
0x14000428a  pop     r15
0x14000428c  pop     r14
0x14000428e  pop     rdi
0x14000428f  pop     rsi
0x140004290  pop     rbp
0x140004291  retn
```
