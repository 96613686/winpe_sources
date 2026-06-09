# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180035884`
- end: `0x180035b3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800333d0`
- `0x180033638`
- `0x1800362d0`
- `0x180039920`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180035884`
- `0x1800365d0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035a37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800359b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800359b6`

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
          v7 = DirectoryName;
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
                          Buffer);
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
0x180035884  mov     [rsp+arg_18], rbx
0x180035889  push    rbp
0x18003588a  push    rsi
0x18003588b  push    rdi
0x18003588c  push    r14
0x18003588e  push    r15
0x180035890  sub     rsp, 250h
0x180035897  mov     rax, cs:__security_cookie
0x18003589e  xor     rax, rsp
0x1800358a1  mov     [rsp+278h+var_38], rax
0x1800358a9  mov     rbx, r8
0x1800358ac  mov     rsi, rdx
0x1800358af  mov     r14, rcx
0x1800358b2  xor     r15d, r15d
0x1800358b5  test    rdx, rdx
0x1800358b8  jz      loc_180035B11
0x1800358be  test    rcx, rcx
0x1800358c1  jz      loc_180035B11
0x1800358c7  mov     [rcx], r15w
0x1800358cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800358d2  test    rax, rax
0x1800358d5  jz      short loc_1800358F8
0x1800358d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800358de  jz      short loc_1800358F8
0x1800358e0  mov     r8, rdx
0x1800358e3  mov     rdx, rcx
0x1800358e6  mov     rcx, rbx
0x1800358e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358ee  cmp     [r14], r15w
0x1800358f2  jnz     loc_180035B11
0x1800358f8  mov     ecx, [rbx]
0x1800358fa  mov     bpl, 8
0x1800358fd  test    ecx, ecx
0x1800358ff  jz      short loc_18003594A
0x180035901  sub     ecx, 1
0x180035904  jz      short loc_180035932
0x180035906  sub     ecx, 1
0x180035909  jz      short loc_180035922
0x18003590b  cmp     ecx, 1
0x18003590e  jz      short loc_180035919
0x180035910  lea     rdi, DirectoryName
0x180035917  jmp     short loc_180035951
0x180035919  lea     rdi, aFailfast; "FailFast"
0x180035920  jmp     short loc_180035951
0x180035922  lea     rax, aLoghr; "LogHr"
0x180035929  lea     rdi, aLognt; "LogNt"
0x180035930  jmp     short loc_180035940
0x180035932  lea     rax, aReturnhr; "ReturnHr"
0x180035939  lea     rdi, aReturnnt; "ReturnNt"
0x180035940  test    [rbx+4], bpl
0x180035944  cmovz   rdi, rax
0x180035948  jmp     short loc_180035951
0x18003594a  lea     rdi, aException; "Exception"
0x180035951  xor     edx, edx; Val
0x180035953  mov     r8d, 200h; Size
0x180035959  lea     rcx, [rsp+278h+Buffer]; void *
0x18003595e  call    memset_0
0x180035963  test    [rbx+4], bpl
0x180035967  jz      short loc_18003598C
0x180035969  mov     ebp, [rbx+0Ch]
0x18003596c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180035973  test    rax, rax
0x180035976  jz      short loc_1800359BC
0x180035978  mov     r8d, 100h
0x18003597e  lea     rdx, [rsp+278h+Buffer]
0x180035983  mov     ecx, ebp
0x180035985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003598a  jmp     short loc_1800359BC
0x18003598c  mov     ebp, [rbx+8]
0x18003598f  mov     [rsp+278h+Arguments], r15; Arguments
0x180035994  mov     [rsp+278h+nSize], 100h; nSize
0x18003599c  lea     rax, [rsp+278h+Buffer]
0x1800359a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800359a6  mov     r9d, 400h; dwLanguageId
0x1800359ac  mov     r8d, ebp; dwMessageId
0x1800359af  xor     edx, edx; lpSource
0x1800359b1  mov     ecx, 1200h; dwFlags
0x1800359b6  call    cs:__imp_FormatMessageW
0x1800359bc  lea     rsi, [r14+rsi*2]
0x1800359c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800359c4  mov     rax, [rbx+88h]
0x1800359cb  mov     rcx, [rbx+80h]
0x1800359d2  mov     rdx, rsi; unsigned __int16 *
0x1800359d5  test    r9, r9
0x1800359d8  jz      short loc_1800359FC
0x1800359da  mov     [rsp+278h+Arguments], rax
0x1800359df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800359e4  mov     eax, [rbx+40h]
0x1800359e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800359eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800359f2  mov     rcx, r14; this
0x1800359f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800359fa  jmp     short loc_180035A13
0x1800359fc  mov     [rsp+278h+lpBuffer], rax
0x180035a01  mov     r9, rcx; unsigned __int16 *
0x180035a04  lea     r8, aHsP; "%hs!%p: "
0x180035a0b  mov     rcx, r14; this
0x180035a0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035a13  mov     r14, rax
0x180035a16  mov     r9, [rbx+90h]; unsigned __int16 *
0x180035a1d  test    r9, r9
0x180035a20  jz      short loc_180035A37
0x180035a22  lea     r8, aCallerP; "(caller: %p) "
0x180035a29  mov     rdx, rsi; unsigned __int16 *
0x180035a2c  mov     rcx, rax; this
0x180035a2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035a34  mov     r14, rax
0x180035a37  call    cs:__imp_GetCurrentThreadId
0x180035a3d  lea     rcx, [rsp+278h+Buffer]
0x180035a42  mov     [rsp+278h+var_240], rcx
0x180035a47  mov     dword ptr [rsp+278h+Arguments], ebp
0x180035a4b  mov     [rsp+278h+nSize], eax
0x180035a4f  mov     eax, [rbx+44h]
0x180035a52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180035a56  mov     r9, rdi; unsigned __int16 *
0x180035a59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180035a60  mov     rdx, rsi; unsigned __int16 *
0x180035a63  mov     rcx, r14; this
0x180035a66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035a6b  cmp     [rbx+18h], r15
0x180035a6f  jnz     short loc_180035A81
0x180035a71  cmp     [rbx+48h], r15
0x180035a75  jnz     short loc_180035A81
0x180035a77  cmp     [rbx+30h], r15
0x180035a7b  jz      loc_180035B11
0x180035a81  lea     r8, asc_1800A50D8; "    "
0x180035a88  mov     rdx, rsi; unsigned __int16 *
0x180035a8b  mov     rcx, rax; this
0x180035a8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035a93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180035a97  test    r9, r9
0x180035a9a  jz      short loc_180035AAE
0x180035a9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180035aa3  mov     rdx, rsi; unsigned __int16 *
0x180035aa6  mov     rcx, rax; this
0x180035aa9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035aae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180035ab2  test    r9, r9
0x180035ab5  jz      short loc_180035AC9
0x180035ab7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180035abe  mov     rdx, rsi; unsigned __int16 *
0x180035ac1  mov     rcx, rax; this
0x180035ac4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035ac9  mov     rcx, [rbx+28h]
0x180035acd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180035ad1  mov     rdx, rsi; unsigned __int16 *
0x180035ad4  test    rcx, rcx
0x180035ad7  jz      short loc_180035AEF
0x180035ad9  mov     [rsp+278h+lpBuffer], rcx
0x180035ade  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180035ae5  mov     rcx, rax; this
0x180035ae8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035aed  jmp     short loc_180035B11
0x180035aef  mov     rcx, rax; this
0x180035af2  test    r9, r9
0x180035af5  jz      short loc_180035B05
0x180035af7  lea     r8, aHs; "[%hs]\n"
0x180035afe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035b03  jmp     short loc_180035B11
0x180035b05  lea     r8, asc_1800A5150; "\n"
0x180035b0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180035b11  xor     eax, eax
0x180035b13  mov     rcx, [rsp+278h+var_38]
0x180035b1b  xor     rcx, rsp; StackCookie
0x180035b1e  call    __security_check_cookie
0x180035b23  mov     rbx, [rsp+278h+arg_18]
0x180035b2b  add     rsp, 250h
0x180035b32  pop     r15
0x180035b34  pop     r14
0x180035b36  pop     rdi
0x180035b37  pop     rsi
0x180035b38  pop     rbp
0x180035b39  retn
```
