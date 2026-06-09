# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180042614`
- end: `0x1800428d7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800424c0`
- `0x18004c030`
- `0x18004daa4`
- `0x180094d03`
- `0x180094e17`

## callees

- `0x180042614`
- `0x180043a30`
- `0x18004456c`
- `0x18004ddb8`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800427cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800427cd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180042746`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180042746`

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
          v7 = (const char *)&qword_18009B258;
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
0x180042614  mov     [rsp+arg_18], rbx
0x180042619  push    rbp
0x18004261a  push    rsi
0x18004261b  push    rdi
0x18004261c  push    r14
0x18004261e  push    r15
0x180042620  sub     rsp, 250h
0x180042627  mov     rax, cs:__security_cookie
0x18004262e  xor     rax, rsp
0x180042631  mov     [rsp+278h+var_38], rax
0x180042639  mov     rbx, r8
0x18004263c  mov     rsi, rdx
0x18004263f  mov     r14, rcx
0x180042642  xor     r15d, r15d
0x180042645  test    rdx, rdx
0x180042648  jz      loc_1800428AD
0x18004264e  test    rcx, rcx
0x180042651  jz      loc_1800428AD
0x180042657  mov     [rcx], r15w
0x18004265b  mov     rax, cs:g_pfnResultLoggingCallback
0x180042662  test    rax, rax
0x180042665  jz      short loc_180042688
0x180042667  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18004266e  jz      short loc_180042688
0x180042670  mov     r8, rdx
0x180042673  mov     rdx, rcx
0x180042676  mov     rcx, rbx
0x180042679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004267e  cmp     [r14], r15w
0x180042682  jnz     loc_1800428AD
0x180042688  mov     ecx, [rbx]
0x18004268a  mov     bpl, 8
0x18004268d  test    ecx, ecx
0x18004268f  jz      short loc_1800426DA
0x180042691  sub     ecx, 1
0x180042694  jz      short loc_1800426C2
0x180042696  sub     ecx, 1
0x180042699  jz      short loc_1800426B2
0x18004269b  cmp     ecx, 1
0x18004269e  jz      short loc_1800426A9
0x1800426a0  lea     rdi, qword_18009B258
0x1800426a7  jmp     short loc_1800426E1
0x1800426a9  lea     rdi, aFailfast; "FailFast"
0x1800426b0  jmp     short loc_1800426E1
0x1800426b2  lea     rax, aLoghr; "LogHr"
0x1800426b9  lea     rdi, aLognt; "LogNt"
0x1800426c0  jmp     short loc_1800426D0
0x1800426c2  lea     rax, aReturnhr; "ReturnHr"
0x1800426c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800426d0  test    [rbx+4], bpl
0x1800426d4  cmovz   rdi, rax
0x1800426d8  jmp     short loc_1800426E1
0x1800426da  lea     rdi, aException; "Exception"
0x1800426e1  xor     edx, edx; Val
0x1800426e3  mov     r8d, 200h; Size
0x1800426e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800426ee  call    memset_0
0x1800426f3  test    [rbx+4], bpl
0x1800426f7  jz      short loc_18004271C
0x1800426f9  mov     ebp, [rbx+0Ch]
0x1800426fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180042703  test    rax, rax
0x180042706  jz      short loc_180042752
0x180042708  mov     r8d, 100h
0x18004270e  lea     rdx, [rsp+278h+Buffer]
0x180042713  mov     ecx, ebp
0x180042715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004271a  jmp     short loc_180042752
0x18004271c  mov     ebp, [rbx+8]
0x18004271f  mov     [rsp+278h+Arguments], r15; Arguments
0x180042724  mov     [rsp+278h+nSize], 100h; nSize
0x18004272c  lea     rax, [rsp+278h+Buffer]
0x180042731  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180042736  mov     r9d, 400h; dwLanguageId
0x18004273c  mov     r8d, ebp; dwMessageId
0x18004273f  xor     edx, edx; lpSource
0x180042741  mov     ecx, 1200h; dwFlags
0x180042746  call    cs:__imp_FormatMessageW
0x18004274d  nop     dword ptr [rax+rax+00h]
0x180042752  lea     rsi, [r14+rsi*2]
0x180042756  mov     r9, [rbx+38h]; unsigned __int16 *
0x18004275a  mov     rax, [rbx+88h]
0x180042761  mov     rcx, [rbx+80h]
0x180042768  mov     rdx, rsi; unsigned __int16 *
0x18004276b  test    r9, r9
0x18004276e  jz      short loc_180042792
0x180042770  mov     [rsp+278h+Arguments], rax
0x180042775  mov     qword ptr [rsp+278h+nSize], rcx
0x18004277a  mov     eax, [rbx+40h]
0x18004277d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180042781  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180042788  mov     rcx, r14; this
0x18004278b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042790  jmp     short loc_1800427A9
0x180042792  mov     [rsp+278h+lpBuffer], rax
0x180042797  mov     r9, rcx; unsigned __int16 *
0x18004279a  lea     r8, aHsP; "%hs!%p: "
0x1800427a1  mov     rcx, r14; this
0x1800427a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800427a9  mov     r14, rax
0x1800427ac  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800427b3  test    r9, r9
0x1800427b6  jz      short loc_1800427CD
0x1800427b8  lea     r8, aCallerP; "(caller: %p) "
0x1800427bf  mov     rdx, rsi; unsigned __int16 *
0x1800427c2  mov     rcx, rax; this
0x1800427c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800427ca  mov     r14, rax
0x1800427cd  call    cs:__imp_GetCurrentThreadId
0x1800427d4  nop     dword ptr [rax+rax+00h]
0x1800427d9  lea     rcx, [rsp+278h+Buffer]
0x1800427de  mov     [rsp+278h+var_240], rcx
0x1800427e3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800427e7  mov     [rsp+278h+nSize], eax
0x1800427eb  mov     eax, [rbx+44h]
0x1800427ee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800427f2  mov     r9, rdi; unsigned __int16 *
0x1800427f5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800427fc  mov     rdx, rsi; unsigned __int16 *
0x1800427ff  mov     rcx, r14; this
0x180042802  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042807  cmp     [rbx+18h], r15
0x18004280b  jnz     short loc_18004281D
0x18004280d  cmp     [rbx+48h], r15
0x180042811  jnz     short loc_18004281D
0x180042813  cmp     [rbx+30h], r15
0x180042817  jz      loc_1800428AD
0x18004281d  lea     r8, asc_18009B760; "    "
0x180042824  mov     rdx, rsi; unsigned __int16 *
0x180042827  mov     rcx, rax; this
0x18004282a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004282f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180042833  test    r9, r9
0x180042836  jz      short loc_18004284A
0x180042838  lea     r8, aMsgWs; "Msg:[%ws] "
0x18004283f  mov     rdx, rsi; unsigned __int16 *
0x180042842  mov     rcx, rax; this
0x180042845  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004284a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18004284e  test    r9, r9
0x180042851  jz      short loc_180042865
0x180042853  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18004285a  mov     rdx, rsi; unsigned __int16 *
0x18004285d  mov     rcx, rax; this
0x180042860  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042865  mov     rcx, [rbx+28h]
0x180042869  mov     r9, [rbx+30h]; unsigned __int16 *
0x18004286d  mov     rdx, rsi; unsigned __int16 *
0x180042870  test    rcx, rcx
0x180042873  jz      short loc_18004288B
0x180042875  mov     [rsp+278h+lpBuffer], rcx
0x18004287a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180042881  mov     rcx, rax; this
0x180042884  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180042889  jmp     short loc_1800428AD
0x18004288b  mov     rcx, rax; this
0x18004288e  test    r9, r9
0x180042891  jz      short loc_1800428A1
0x180042893  lea     r8, aHs; "[%hs]\n"
0x18004289a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004289f  jmp     short loc_1800428AD
0x1800428a1  lea     r8, asc_18009B7D8; "\n"
0x1800428a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800428ad  xor     eax, eax
0x1800428af  mov     rcx, [rsp+278h+var_38]
0x1800428b7  xor     rcx, rsp; StackCookie
0x1800428ba  call    __security_check_cookie
0x1800428bf  mov     rbx, [rsp+278h+arg_18]
0x1800428c7  add     rsp, 250h
0x1800428ce  pop     r15
0x1800428d0  pop     r14
0x1800428d2  pop     rdi
0x1800428d3  pop     rsi
0x1800428d4  pop     rbp
0x1800428d5  retn
```
