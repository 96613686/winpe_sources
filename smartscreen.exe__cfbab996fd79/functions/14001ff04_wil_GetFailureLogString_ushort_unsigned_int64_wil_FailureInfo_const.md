# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14001ff04`
- end: `0x1400201c7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14001880c`
- `0x14001fdb0`
- `0x14002f238`

## callees

- `0x14001ff04`
- `0x140026c20`
- `0x14002f1c8`
- `0x140064940`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400200bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400200bd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140020036`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140020036`

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
          v7 = word_1400726BA;
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
0x14001ff04  mov     [rsp+arg_18], rbx
0x14001ff09  push    rbp
0x14001ff0a  push    rsi
0x14001ff0b  push    rdi
0x14001ff0c  push    r14
0x14001ff0e  push    r15
0x14001ff10  sub     rsp, 250h
0x14001ff17  mov     rax, cs:__security_cookie
0x14001ff1e  xor     rax, rsp
0x14001ff21  mov     [rsp+278h+var_38], rax
0x14001ff29  mov     rbx, r8
0x14001ff2c  mov     rsi, rdx
0x14001ff2f  mov     r14, rcx
0x14001ff32  xor     r15d, r15d
0x14001ff35  test    rdx, rdx
0x14001ff38  jz      loc_14002019D
0x14001ff3e  test    rcx, rcx
0x14001ff41  jz      loc_14002019D
0x14001ff47  mov     [rcx], r15w
0x14001ff4b  mov     rax, cs:g_pfnResultLoggingCallback
0x14001ff52  test    rax, rax
0x14001ff55  jz      short loc_14001FF78
0x14001ff57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14001ff5e  jz      short loc_14001FF78
0x14001ff60  mov     r8, rdx
0x14001ff63  mov     rdx, rcx
0x14001ff66  mov     rcx, rbx
0x14001ff69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ff6e  cmp     [r14], r15w
0x14001ff72  jnz     loc_14002019D
0x14001ff78  mov     ecx, [rbx]
0x14001ff7a  mov     bpl, 8
0x14001ff7d  test    ecx, ecx
0x14001ff7f  jz      short loc_14001FFCA
0x14001ff81  sub     ecx, 1
0x14001ff84  jz      short loc_14001FFB2
0x14001ff86  sub     ecx, 1
0x14001ff89  jz      short loc_14001FFA2
0x14001ff8b  cmp     ecx, 1
0x14001ff8e  jz      short loc_14001FF99
0x14001ff90  lea     rdi, word_1400726BA
0x14001ff97  jmp     short loc_14001FFD1
0x14001ff99  lea     rdi, aFailfast; "FailFast"
0x14001ffa0  jmp     short loc_14001FFD1
0x14001ffa2  lea     rax, aLoghr; "LogHr"
0x14001ffa9  lea     rdi, aLognt; "LogNt"
0x14001ffb0  jmp     short loc_14001FFC0
0x14001ffb2  lea     rax, aReturnhr; "ReturnHr"
0x14001ffb9  lea     rdi, aReturnnt; "ReturnNt"
0x14001ffc0  test    [rbx+4], bpl
0x14001ffc4  cmovz   rdi, rax
0x14001ffc8  jmp     short loc_14001FFD1
0x14001ffca  lea     rdi, aException; "Exception"
0x14001ffd1  xor     edx, edx; Val
0x14001ffd3  mov     r8d, 200h; Size
0x14001ffd9  lea     rcx, [rsp+278h+Buffer]; void *
0x14001ffde  call    memset
0x14001ffe3  test    [rbx+4], bpl
0x14001ffe7  jz      short loc_14002000C
0x14001ffe9  mov     ebp, [rbx+0Ch]
0x14001ffec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14001fff3  test    rax, rax
0x14001fff6  jz      short loc_140020042
0x14001fff8  mov     r8d, 100h
0x14001fffe  lea     rdx, [rsp+278h+Buffer]
0x140020003  mov     ecx, ebp
0x140020005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002000a  jmp     short loc_140020042
0x14002000c  mov     ebp, [rbx+8]
0x14002000f  mov     [rsp+278h+Arguments], r15; Arguments
0x140020014  mov     [rsp+278h+nSize], 100h; nSize
0x14002001c  lea     rax, [rsp+278h+Buffer]
0x140020021  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140020026  mov     r9d, 400h; dwLanguageId
0x14002002c  mov     r8d, ebp; dwMessageId
0x14002002f  xor     edx, edx; lpSource
0x140020031  mov     ecx, 1200h; dwFlags
0x140020036  call    cs:__imp_FormatMessageW
0x14002003d  nop     dword ptr [rax+rax+00h]
0x140020042  lea     rsi, [r14+rsi*2]
0x140020046  mov     r9, [rbx+38h]; unsigned __int16 *
0x14002004a  mov     rax, [rbx+88h]
0x140020051  mov     rcx, [rbx+80h]
0x140020058  mov     rdx, rsi; unsigned __int16 *
0x14002005b  test    r9, r9
0x14002005e  jz      short loc_140020082
0x140020060  mov     [rsp+278h+Arguments], rax
0x140020065  mov     qword ptr [rsp+278h+nSize], rcx
0x14002006a  mov     eax, [rbx+40h]
0x14002006d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140020071  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140020078  mov     rcx, r14; this
0x14002007b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140020080  jmp     short loc_140020099
0x140020082  mov     [rsp+278h+lpBuffer], rax
0x140020087  mov     r9, rcx; unsigned __int16 *
0x14002008a  lea     r8, aHsP; "%hs!%p: "
0x140020091  mov     rcx, r14; this
0x140020094  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140020099  mov     r14, rax
0x14002009c  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400200a3  test    r9, r9
0x1400200a6  jz      short loc_1400200BD
0x1400200a8  lea     r8, aCallerP; "(caller: %p) "
0x1400200af  mov     rdx, rsi; unsigned __int16 *
0x1400200b2  mov     rcx, rax; this
0x1400200b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400200ba  mov     r14, rax
0x1400200bd  call    cs:__imp_GetCurrentThreadId
0x1400200c4  nop     dword ptr [rax+rax+00h]
0x1400200c9  lea     rcx, [rsp+278h+Buffer]
0x1400200ce  mov     [rsp+278h+var_240], rcx
0x1400200d3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400200d7  mov     [rsp+278h+nSize], eax
0x1400200db  mov     eax, [rbx+44h]
0x1400200de  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400200e2  mov     r9, rdi; unsigned __int16 *
0x1400200e5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400200ec  mov     rdx, rsi; unsigned __int16 *
0x1400200ef  mov     rcx, r14; this
0x1400200f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400200f7  cmp     [rbx+18h], r15
0x1400200fb  jnz     short loc_14002010D
0x1400200fd  cmp     [rbx+48h], r15
0x140020101  jnz     short loc_14002010D
0x140020103  cmp     [rbx+30h], r15
0x140020107  jz      loc_14002019D
0x14002010d  lea     r8, asc_1400734D0; "    "
0x140020114  mov     rdx, rsi; unsigned __int16 *
0x140020117  mov     rcx, rax; this
0x14002011a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002011f  mov     r9, [rbx+18h]; unsigned __int16 *
0x140020123  test    r9, r9
0x140020126  jz      short loc_14002013A
0x140020128  lea     r8, aMsgWs; "Msg:[%ws] "
0x14002012f  mov     rdx, rsi; unsigned __int16 *
0x140020132  mov     rcx, rax; this
0x140020135  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002013a  mov     r9, [rbx+48h]; unsigned __int16 *
0x14002013e  test    r9, r9
0x140020141  jz      short loc_140020155
0x140020143  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14002014a  mov     rdx, rsi; unsigned __int16 *
0x14002014d  mov     rcx, rax; this
0x140020150  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140020155  mov     rcx, [rbx+28h]
0x140020159  mov     r9, [rbx+30h]; unsigned __int16 *
0x14002015d  mov     rdx, rsi; unsigned __int16 *
0x140020160  test    rcx, rcx
0x140020163  jz      short loc_14002017B
0x140020165  mov     [rsp+278h+lpBuffer], rcx
0x14002016a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140020171  mov     rcx, rax; this
0x140020174  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140020179  jmp     short loc_14002019D
0x14002017b  mov     rcx, rax; this
0x14002017e  test    r9, r9
0x140020181  jz      short loc_140020191
0x140020183  lea     r8, aHs; "[%hs]\n"
0x14002018a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002018f  jmp     short loc_14002019D
0x140020191  lea     r8, asc_140073548; "\n"
0x140020198  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002019d  xor     eax, eax
0x14002019f  mov     rcx, [rsp+278h+var_38]
0x1400201a7  xor     rcx, rsp; StackCookie
0x1400201aa  call    __security_check_cookie
0x1400201af  mov     rbx, [rsp+278h+arg_18]
0x1400201b7  add     rsp, 250h
0x1400201be  pop     r15
0x1400201c0  pop     r14
0x1400201c2  pop     rdi
0x1400201c3  pop     rsi
0x1400201c4  pop     rbp
0x1400201c5  retn
```
