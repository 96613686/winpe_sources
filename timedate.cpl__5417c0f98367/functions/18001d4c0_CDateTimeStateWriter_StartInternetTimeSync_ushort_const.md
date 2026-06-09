# CDateTimeStateWriter::StartInternetTimeSync(ushort const *)

- ea: `0x18001d4c0`
- end: `0x18001d5f5`
- name: `?StartInternetTimeSync@CDateTimeStateWriter@@UEAAJPEBG@Z`
- size: `309`
- prototype: `__int64 __fastcall(CDateTimeStateWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800089c8`
- `0x1800092c4`
- `0x180015700`
- `0x18001d4c0`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18001d526`
- `SHLWAPI!__imp_SHCreateThread` at `0x18001d526`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001d53f`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001d53f`

## pseudocode

```c
__int64 __fastcall CDateTimeStateWriter::StartInternetTimeSync(CDateTimeStateWriter *this, const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  __int64 v6; // r9
  __int64 v7; // rdx
  __int32 v8; // r11d
  int v10; // [rsp+20h] [rbp-28h]
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = StringCchLengthW(a2, 0x100u, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (unsigned int)v4;
    v7 = 240;
LABEL_12:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\cpls\\utc\\state.cpp",
      (const char *)v6,
      v10);
    return v5;
  }
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 11, 1, 0) )
  {
    (*(void (__fastcall **)(CDateTimeStateWriter *))(*(_QWORD *)this + 8LL))(this);
    if ( !SHCreateThread(CDateTimeStateWriter::s_SyncInternetTimeThreadProc, this, 0x11u, 0) )
    {
      v5 = -2147467259;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"shell\\cpls\\utc\\state.cpp",
        (const char *)0x80004005LL,
        v10);
      (*(void (__fastcall **)(CDateTimeStateWriter *))(*(_QWORD *)this + 16LL))(this);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"shell\\cpls\\utc\\state.cpp",
        (const char *)0x80004005LL,
        v11);
      v6 = 2147500037LL;
      _InterlockedExchange((volatile __int32 *)this + 11, 0);
      v7 = 259;
      goto LABEL_12;
    }
    v5 = 0;
    _InterlockedExchange((volatile __int32 *)this + 11, 2);
  }
  if ( StrCmpICW(a2, (LPCWSTR)this + 24) )
  {
    _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 2, 3);
    _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 2, 4);
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 2, 2) == 2 )
  {
    StringCchCopyW((unsigned __int16 *)this + 24, 0x100u, a2);
    _InterlockedExchange((volatile __int32 *)this + 11, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x18001d4c0  push    rbx
0x18001d4c2  push    rbp
0x18001d4c3  push    rsi
0x18001d4c4  push    rdi
0x18001d4c5  push    r14; int
0x18001d4c7  sub     rsp, 20h
0x18001d4cb  mov     rsi, rdx
0x18001d4ce  mov     rbx, rcx
0x18001d4d1  mov     rcx, rsi; unsigned __int16 *
0x18001d4d4  xor     r8d, r8d; unsigned __int64 *
0x18001d4d7  mov     edx, 100h; unsigned __int64
0x18001d4dc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001d4e1  mov     edi, eax
0x18001d4e3  test    eax, eax
0x18001d4e5  jns     short loc_18001D4F4
0x18001d4e7  mov     r9d, eax
0x18001d4ea  mov     edx, 0F0h
0x18001d4ef  jmp     loc_18001D5E2
0x18001d4f4  mov     ecx, 1
0x18001d4f9  xor     eax, eax
0x18001d4fb  lea     r14d, [rcx+1]
0x18001d4ff  lock cmpxchg [rbx+2Ch], ecx
0x18001d504  jnz     short loc_18001D538
0x18001d506  mov     rax, [rbx]
0x18001d509  mov     rcx, rbx
0x18001d50c  mov     rax, [rax+8]
0x18001d510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d515  xor     r9d, r9d; pfnCallback
0x18001d518  lea     r8d, [r14+0Fh]; flags
0x18001d51c  mov     rdx, rbx; pData
0x18001d51f  lea     rcx, ?s_SyncInternetTimeThreadProc@CDateTimeStateWriter@@CAKPEAX@Z; pfnThreadProc
0x18001d526  call    cs:__imp_SHCreateThread
0x18001d52c  test    eax, eax
0x18001d52e  jz      short loc_18001D58F
0x18001d530  mov     eax, r14d
0x18001d533  xor     edi, edi
0x18001d535  xchg    eax, [rbx+2Ch]
0x18001d538  lea     rdx, [rbx+30h]; pszStr2
0x18001d53c  mov     rcx, rsi; pszStr1
0x18001d53f  call    cs:__imp_StrCmpICW
0x18001d545  mov     r11d, 3
0x18001d54b  test    eax, eax
0x18001d54d  jz      short loc_18001D562
0x18001d54f  mov     eax, r11d
0x18001d552  lock cmpxchg [rbx+2Ch], r14d
0x18001d558  lea     eax, [r11+1]
0x18001d55c  lock cmpxchg [rbx+2Ch], r14d
0x18001d562  mov     eax, r14d
0x18001d565  lock cmpxchg [rbx+2Ch], r14d
0x18001d56b  jnz     short loc_18001D582
0x18001d56d  mov     r8, rsi; unsigned __int16 *
0x18001d570  lea     rcx, [rbx+30h]; unsigned __int16 *
0x18001d574  mov     edx, 100h; unsigned __int64
0x18001d579  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d57e  xchg    r11d, [rbx+2Ch]
0x18001d582  mov     eax, edi
0x18001d584  add     rsp, 20h
0x18001d588  pop     r14
0x18001d58a  pop     rdi
0x18001d58b  pop     rsi
0x18001d58c  pop     rbp
0x18001d58d  pop     rbx
0x18001d58e  retn
0x18001d58f  mov     rcx, [rsp+48h]; this
0x18001d594  lea     r8, aShellCplsUtcSt; "shell\\cpls\\utc\\state.cpp"
0x18001d59b  mov     edi, 80004005h
0x18001d5a0  mov     edx, 124h; void *
0x18001d5a5  mov     r9d, edi; char *
0x18001d5a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d5ad  mov     rax, [rbx]
0x18001d5b0  mov     rcx, rbx
0x18001d5b3  mov     rax, [rax+10h]
0x18001d5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5bc  mov     rcx, [rsp+48h]; this
0x18001d5c1  lea     r8, aShellCplsUtcSt; "shell\\cpls\\utc\\state.cpp"
0x18001d5c8  mov     r9d, edi; char *
0x18001d5cb  mov     edx, 0F8h; void *
0x18001d5d0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d5d5  xor     eax, eax
0x18001d5d7  mov     r9d, edi; char *
0x18001d5da  xchg    eax, [rbx+2Ch]
0x18001d5dd  mov     edx, 103h; void *
0x18001d5e2  mov     rcx, [rsp+48h]; this
0x18001d5e7  lea     r8, aShellCplsUtcSt; "shell\\cpls\\utc\\state.cpp"
0x18001d5ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d5f3  jmp     short loc_18001D582
```
