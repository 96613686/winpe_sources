# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004324`
- end: `0x1400045da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1400028dc`
- `0x140002b4c`
- `0x140005ce8`
- `0x1400083f0`

## callees

- `0x140004324`
- `0x140005fe8`
- `0x14002e3e2`
- `0x14002e420`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400044d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400044d7`
- `KERNEL32!FormatMessageW` at `0x140004456`
- `KERNEL32!FormatMessageW` at `0x140004456`

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
          v7 = (const char *)&dword_1400326D4;
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
0x140004324  mov     [rsp+arg_18], rbx
0x140004329  push    rbp
0x14000432a  push    rsi
0x14000432b  push    rdi
0x14000432c  push    r14
0x14000432e  push    r15
0x140004330  sub     rsp, 250h
0x140004337  mov     rax, cs:__security_cookie
0x14000433e  xor     rax, rsp
0x140004341  mov     [rsp+278h+var_38], rax
0x140004349  mov     rbx, r8
0x14000434c  mov     rsi, rdx
0x14000434f  mov     r14, rcx
0x140004352  xor     r15d, r15d
0x140004355  test    rdx, rdx
0x140004358  jz      loc_1400045B1
0x14000435e  test    rcx, rcx
0x140004361  jz      loc_1400045B1
0x140004367  mov     [rcx], r15w
0x14000436b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004372  test    rax, rax
0x140004375  jz      short loc_140004398
0x140004377  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000437e  jz      short loc_140004398
0x140004380  mov     r8, rdx
0x140004383  mov     rdx, rcx
0x140004386  mov     rcx, rbx
0x140004389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000438e  cmp     [r14], r15w
0x140004392  jnz     loc_1400045B1
0x140004398  mov     ecx, [rbx]
0x14000439a  mov     bpl, 8
0x14000439d  test    ecx, ecx
0x14000439f  jz      short loc_1400043EA
0x1400043a1  sub     ecx, 1
0x1400043a4  jz      short loc_1400043D2
0x1400043a6  sub     ecx, 1
0x1400043a9  jz      short loc_1400043C2
0x1400043ab  cmp     ecx, 1
0x1400043ae  jz      short loc_1400043B9
0x1400043b0  lea     rdi, dword_1400326D4
0x1400043b7  jmp     short loc_1400043F1
0x1400043b9  lea     rdi, aFailfast; "FailFast"
0x1400043c0  jmp     short loc_1400043F1
0x1400043c2  lea     rax, aLoghr; "LogHr"
0x1400043c9  lea     rdi, aLognt; "LogNt"
0x1400043d0  jmp     short loc_1400043E0
0x1400043d2  lea     rax, aReturnhr; "ReturnHr"
0x1400043d9  lea     rdi, aReturnnt; "ReturnNt"
0x1400043e0  test    [rbx+4], bpl
0x1400043e4  cmovz   rdi, rax
0x1400043e8  jmp     short loc_1400043F1
0x1400043ea  lea     rdi, aException; "Exception"
0x1400043f1  xor     edx, edx; Val
0x1400043f3  mov     r8d, 200h; Size
0x1400043f9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400043fe  call    memset_0
0x140004403  test    [rbx+4], bpl
0x140004407  jz      short loc_14000442C
0x140004409  mov     ebp, [rbx+0Ch]
0x14000440c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004413  test    rax, rax
0x140004416  jz      short loc_14000445C
0x140004418  mov     r8d, 100h
0x14000441e  lea     rdx, [rsp+278h+Buffer]
0x140004423  mov     ecx, ebp
0x140004425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000442a  jmp     short loc_14000445C
0x14000442c  mov     ebp, [rbx+8]
0x14000442f  mov     [rsp+278h+Arguments], r15; Arguments
0x140004434  mov     [rsp+278h+nSize], 100h; nSize
0x14000443c  lea     rax, [rsp+278h+Buffer]
0x140004441  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004446  mov     r9d, 400h; dwLanguageId
0x14000444c  mov     r8d, ebp; dwMessageId
0x14000444f  xor     edx, edx; lpSource
0x140004451  mov     ecx, 1200h; dwFlags
0x140004456  call    cs:__imp_FormatMessageW
0x14000445c  lea     rsi, [r14+rsi*2]
0x140004460  mov     r9, [rbx+38h]; unsigned __int16 *
0x140004464  mov     rax, [rbx+88h]
0x14000446b  mov     rcx, [rbx+80h]
0x140004472  mov     rdx, rsi; unsigned __int16 *
0x140004475  test    r9, r9
0x140004478  jz      short loc_14000449C
0x14000447a  mov     [rsp+278h+Arguments], rax
0x14000447f  mov     qword ptr [rsp+278h+nSize], rcx
0x140004484  mov     eax, [rbx+40h]
0x140004487  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000448b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004492  mov     rcx, r14; this
0x140004495  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000449a  jmp     short loc_1400044B3
0x14000449c  mov     [rsp+278h+lpBuffer], rax
0x1400044a1  mov     r9, rcx; unsigned __int16 *
0x1400044a4  lea     r8, aHsP; "%hs!%p: "
0x1400044ab  mov     rcx, r14; this
0x1400044ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044b3  mov     r14, rax
0x1400044b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400044bd  test    r9, r9
0x1400044c0  jz      short loc_1400044D7
0x1400044c2  lea     r8, aCallerP; "(caller: %p) "
0x1400044c9  mov     rdx, rsi; unsigned __int16 *
0x1400044cc  mov     rcx, rax; this
0x1400044cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044d4  mov     r14, rax
0x1400044d7  call    cs:__imp_GetCurrentThreadId
0x1400044dd  lea     rcx, [rsp+278h+Buffer]
0x1400044e2  mov     [rsp+278h+var_240], rcx
0x1400044e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400044eb  mov     [rsp+278h+nSize], eax
0x1400044ef  mov     eax, [rbx+44h]
0x1400044f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400044f6  mov     r9, rdi; unsigned __int16 *
0x1400044f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004500  mov     rdx, rsi; unsigned __int16 *
0x140004503  mov     rcx, r14; this
0x140004506  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000450b  cmp     [rbx+18h], r15
0x14000450f  jnz     short loc_140004521
0x140004511  cmp     [rbx+48h], r15
0x140004515  jnz     short loc_140004521
0x140004517  cmp     [rbx+30h], r15
0x14000451b  jz      loc_1400045B1
0x140004521  lea     r8, asc_140032828; "    "
0x140004528  mov     rdx, rsi; unsigned __int16 *
0x14000452b  mov     rcx, rax; this
0x14000452e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004533  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004537  test    r9, r9
0x14000453a  jz      short loc_14000454E
0x14000453c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004543  mov     rdx, rsi; unsigned __int16 *
0x140004546  mov     rcx, rax; this
0x140004549  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000454e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140004552  test    r9, r9
0x140004555  jz      short loc_140004569
0x140004557  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000455e  mov     rdx, rsi; unsigned __int16 *
0x140004561  mov     rcx, rax; this
0x140004564  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004569  mov     rcx, [rbx+28h]
0x14000456d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140004571  mov     rdx, rsi; unsigned __int16 *
0x140004574  test    rcx, rcx
0x140004577  jz      short loc_14000458F
0x140004579  mov     [rsp+278h+lpBuffer], rcx
0x14000457e  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x140004585  mov     rcx, rax; this
0x140004588  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000458d  jmp     short loc_1400045B1
0x14000458f  mov     rcx, rax; this
0x140004592  test    r9, r9
0x140004595  jz      short loc_1400045A5
0x140004597  lea     r8, aHs_0; "[%hs]\n"
0x14000459e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045a3  jmp     short loc_1400045B1
0x1400045a5  lea     r8, asc_1400328A0; "\n"
0x1400045ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400045b1  xor     eax, eax
0x1400045b3  mov     rcx, [rsp+278h+var_38]
0x1400045bb  xor     rcx, rsp; StackCookie
0x1400045be  call    __security_check_cookie
0x1400045c3  mov     rbx, [rsp+278h+arg_18]
0x1400045cb  add     rsp, 250h
0x1400045d2  pop     r15
0x1400045d4  pop     r14
0x1400045d6  pop     rdi
0x1400045d7  pop     rsi
0x1400045d8  pop     rbp
0x1400045d9  retn
```
