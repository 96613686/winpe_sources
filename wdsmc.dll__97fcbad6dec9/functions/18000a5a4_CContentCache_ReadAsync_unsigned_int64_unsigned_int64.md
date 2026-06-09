# CContentCache::ReadAsync(unsigned __int64,unsigned __int64)

- ea: `0x18000a5a4`
- end: `0x18000a876`
- name: `?ReadAsync@CContentCache@@QEAAK_K0@Z`
- size: `722`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000d30c`

## callees

- `0x180008f4c`
- `0x18000a528`
- `0x18000a5a4`
- `0x18001a9a8`
- `0x180024c14`
- `0x180024ce0`
- `0x180025850`
- `0x1800266a0`
- `0x180026d70`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000a751`
- `KERNEL32!SetEvent` at `0x18000a751`
- `KERNEL32!LeaveCriticalSection` at `0x18000a6b6`
- `KERNEL32!LeaveCriticalSection` at `0x18000a6c8`
- `KERNEL32!LeaveCriticalSection` at `0x18000a851`
- `KERNEL32!LeaveCriticalSection` at `0x18000a6b6`
- `KERNEL32!LeaveCriticalSection` at `0x18000a6c8`
- `KERNEL32!LeaveCriticalSection` at `0x18000a851`
- `KERNEL32!EnterCriticalSection` at `0x18000a5cf`
- `KERNEL32!EnterCriticalSection` at `0x18000a6a2`
- `KERNEL32!EnterCriticalSection` at `0x18000a5cf`
- `KERNEL32!EnterCriticalSection` at `0x18000a6a2`

## string_xrefs

- `0x18000a672`: `base\eco\wds\transport\server\mc\contentcache.cpp`
- `0x18000a725`: `base\eco\wds\transport\server\mc\contentcache.cpp`

## pseudocode

```c
__int64 __fastcall CContentCache::ReadAsync(char *lpCriticalSection, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned int v4; // ebx
  unsigned __int64 v7; // rbp
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  struct CMemoryBuffer *v10; // rax
  const char *v11; // rdx
  struct _RTL_CRITICAL_SECTION *v12; // r14
  HANDLE v13; // r13
  __int64 v14; // r12
  const char *v15; // rdx
  __int64 (__fastcall *DebugInfo)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rbx
  int v17; // eax
  const char *v18; // rdx
  __int64 v19; // rax
  _QWORD *v20; // rax
  _DWORD *v21; // rbp
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned __int64 v27; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  if ( CContentCache::FindCacheBlock((LPCRITICAL_SECTION)lpCriticalSection, a2, a3) )
    goto LABEL_42;
  v7 = a2 + 0xFFFFF;
  if ( a3 < a2 + 0xFFFFF )
    v7 = a3;
  v8 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    v8[5] = 0;
    v8[6] = 0;
    *v8 = 0;
    v8[1] = 0;
    *((_DWORD *)v8 + 4) = 0;
    v8[3] = 0;
    v8[4] = 0;
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    v4 = 8;
    goto LABEL_42;
  }
  *v9 = lpCriticalSection;
  v10 = TptMemoryBufferAllocate(0x100000u);
  v9[1] = v10;
  if ( !v10 )
  {
    v4 = 8;
LABEL_39:
    v25 = v9[1];
    if ( v25 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      v9[1] = 0;
    }
    operator delete(v9);
    goto LABEL_42;
  }
  *((_DWORD *)v9 + 4) = 0;
  v9[3] = a2;
  v9[4] = v7;
  _InterlockedIncrement((volatile signed __int32 *)lpCriticalSection + 18);
  if ( !ElValidateWin32(0, v11, "base\\eco\\wds\\transport\\server\\mc\\contentcache.cpp", 0x120u) )
  {
    v12 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)lpCriticalSection + 6);
    v13 = (HANDLE)*((_QWORD *)lpCriticalSection + 7);
    v14 = *(_QWORD *)(v9[1] + 40LL);
    v27 = 0;
    EnterCriticalSection(v12);
    if ( v12[1].LockCount )
    {
      DebugInfo = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v12[4].DebugInfo;
      LeaveCriticalSection(v12);
      v27 = a2;
      v17 = DebugInfo(v13, v14, (unsigned int)(v7 - a2 + 1), &v27, v9);
      v4 = v17;
      if ( v17 < 0 && (v17 & 0x1FFF0000) == 0x70000 )
        v4 = (unsigned __int16)v17;
      ElValidateWin32(v4, v18, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x374u);
    }
    else
    {
      v4 = 21;
      LeaveCriticalSection(v12);
    }
    if ( ElValidateWin32(v4, v15, "base\\eco\\wds\\transport\\server\\mc\\contentcache.cpp", 0x128u) )
    {
      CMRSWLock::ReaderLock((LPCRITICAL_SECTION)(lpCriticalSection + 88));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpCriticalSection + 18, 0xFFFFFFFF) == 1 )
        SetEvent(*((HANDLE *)lpCriticalSection + 10));
      CMRSWLock::ReaderRelease((struct _RTL_CRITICAL_SECTION *)(lpCriticalSection + 88));
    }
    else
    {
      v19 = *((_QWORD *)lpCriticalSection + 26);
      if ( v19 )
      {
        v9[5] = v19;
        v9[6] = 0;
        *(_QWORD *)(*((_QWORD *)lpCriticalSection + 26) + 48LL) = v9;
        *((_QWORD *)lpCriticalSection + 26) = v9;
      }
      else
      {
        *((_QWORD *)lpCriticalSection + 27) = v9;
        *((_QWORD *)lpCriticalSection + 26) = v9;
        v9[5] = 0;
        v9[6] = 0;
      }
      ++*((_DWORD *)lpCriticalSection + 57);
      while ( *((_DWORD *)lpCriticalSection + 57) > 2u )
      {
        v20 = (_QWORD *)*((_QWORD *)lpCriticalSection + 26);
        v21 = 0;
        if ( v20 )
          v21 = (_DWORD *)*((_QWORD *)lpCriticalSection + 27);
        if ( !v21[4] )
          break;
        if ( v20 )
        {
          v22 = (_QWORD *)*((_QWORD *)lpCriticalSection + 27);
          if ( v20 == v22 )
          {
            *((_QWORD *)lpCriticalSection + 26) = 0;
            *((_QWORD *)lpCriticalSection + 27) = 0;
          }
          else
          {
            v23 = (_QWORD *)v22[6];
            *((_QWORD *)lpCriticalSection + 27) = v23;
            v23[5] = 0;
          }
          --*((_DWORD *)lpCriticalSection + 57);
        }
        v24 = *((_QWORD *)v21 + 1);
        if ( v24 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
          *((_QWORD *)v21 + 1) = 0;
        }
        operator delete(v21);
      }
    }
    if ( v4 )
      goto LABEL_39;
  }
LABEL_42:
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  return v4;
}

```

## disassembly

```asm
0x18000a5a4  mov     [rsp+arg_8], rbx
0x18000a5a9  mov     [rsp+arg_10], rbp
0x18000a5ae  mov     [rsp+arg_18], rsi
0x18000a5b3  push    rdi
0x18000a5b4  push    r12
0x18000a5b6  push    r13
0x18000a5b8  push    r14
0x18000a5ba  push    r15
0x18000a5bc  sub     rsp, 30h
0x18000a5c0  xor     r14d, r14d
0x18000a5c3  mov     rdi, r8
0x18000a5c6  mov     ebx, r14d
0x18000a5c9  mov     r15, rdx
0x18000a5cc  mov     rsi, rcx
0x18000a5cf  call    cs:__imp_EnterCriticalSection
0x18000a5d5  mov     r8, rdi; unsigned __int64
0x18000a5d8  mov     rdx, r15; unsigned __int64
0x18000a5db  mov     rcx, rsi; lpCriticalSection
0x18000a5de  call    ?FindCacheBlock@CContentCache@@AEAAPEAUCacheBlock@1@_K0@Z; CContentCache::FindCacheBlock(unsigned __int64,unsigned __int64)
0x18000a5e3  test    rax, rax
0x18000a5e6  jnz     loc_18000A84E
0x18000a5ec  lea     rbp, [r15+0FFFFFh]
0x18000a5f3  cmp     rdi, rbp
0x18000a5f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a5fd  lea     ecx, [rax+38h]; unsigned __int64
0x18000a600  cmovb   rbp, rdi
0x18000a604  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a609  mov     rdi, rax
0x18000a60c  test    rax, rax
0x18000a60f  jz      short loc_18000A62E
0x18000a611  mov     [rax+28h], r14
0x18000a615  mov     [rax+30h], r14
0x18000a619  mov     [rax], r14
0x18000a61c  mov     [rax+8], r14
0x18000a620  mov     [rax+10h], r14d
0x18000a624  mov     [rax+18h], r14
0x18000a628  mov     [rax+20h], r14
0x18000a62c  jmp     short loc_18000A631
0x18000a62e  mov     rdi, r14
0x18000a631  test    rdi, rdi
0x18000a634  jnz     short loc_18000A63E
0x18000a636  lea     ebx, [rdi+8]
0x18000a639  jmp     loc_18000A84E
0x18000a63e  mov     ecx, 100000h; unsigned int
0x18000a643  mov     [rdi], rsi
0x18000a646  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18000a64b  mov     [rdi+8], rax
0x18000a64f  test    rax, rax
0x18000a652  jnz     short loc_18000A65C
0x18000a654  lea     ebx, [rax+8]
0x18000a657  jmp     loc_18000A82C
0x18000a65c  mov     [rdi+10h], r14d
0x18000a660  mov     [rdi+18h], r15
0x18000a664  mov     [rdi+20h], rbp
0x18000a668  lock inc dword ptr [rsi+48h]
0x18000a66c  mov     r9d, 120h; unsigned int
0x18000a672  lea     r8, aBaseEcoWdsTran_23; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000a679  xor     ecx, ecx; unsigned int
0x18000a67b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000a680  test    eax, eax
0x18000a682  jnz     loc_18000A84E
0x18000a688  mov     rax, [rdi+8]
0x18000a68c  mov     r14, [rsi+30h]
0x18000a690  mov     r13, [rsi+38h]
0x18000a694  mov     rcx, r14; lpCriticalSection
0x18000a697  mov     r12, [rax+28h]
0x18000a69b  xor     eax, eax
0x18000a69d  mov     [rsp+58h+arg_0], rax
0x18000a6a2  call    cs:__imp_EnterCriticalSection
0x18000a6a8  mov     rcx, r14; lpCriticalSection
0x18000a6ab  cmp     [r14+30h], ebx
0x18000a6af  jnz     short loc_18000A6C1
0x18000a6b1  mov     ebx, 15h
0x18000a6b6  call    cs:__imp_LeaveCriticalSection
0x18000a6bc  xor     r14d, r14d
0x18000a6bf  jmp     short loc_18000A71F
0x18000a6c1  mov     rbx, [r14+0A0h]
0x18000a6c8  call    cs:__imp_LeaveCriticalSection
0x18000a6ce  sub     ebp, r15d
0x18000a6d1  mov     [rsp+58h+arg_0], r15
0x18000a6d6  lea     r9, [rsp+58h+arg_0]
0x18000a6db  mov     [rsp+58h+var_38], rdi
0x18000a6e0  mov     rdx, r12
0x18000a6e3  mov     rcx, r13
0x18000a6e6  mov     rax, rbx
0x18000a6e9  lea     r8d, [rbp+1]
0x18000a6ed  call    cs:__guard_dispatch_icall_fptr
0x18000a6f3  xor     r14d, r14d
0x18000a6f6  mov     ebx, eax
0x18000a6f8  test    eax, eax
0x18000a6fa  jns     short loc_18000A70B
0x18000a6fc  and     eax, 1FFF0000h
0x18000a701  cmp     eax, 70000h
0x18000a706  jnz     short loc_18000A70B
0x18000a708  movzx   ebx, bx
0x18000a70b  mov     r9d, 374h; unsigned int
0x18000a711  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000a718  mov     ecx, ebx; unsigned int
0x18000a71a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000a71f  mov     r9d, 128h; unsigned int
0x18000a725  lea     r8, aBaseEcoWdsTran_23; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000a72c  mov     ecx, ebx; unsigned int
0x18000a72e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000a733  test    eax, eax
0x18000a735  jz      short loc_18000A765
0x18000a737  lea     rcx, [rsi+58h]; lpCriticalSection
0x18000a73b  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x18000a740  or      eax, 0FFFFFFFFh
0x18000a743  lock xadd [rsi+48h], eax
0x18000a748  cmp     eax, 1
0x18000a74b  jnz     short loc_18000A757
0x18000a74d  mov     rcx, [rsi+50h]; hEvent
0x18000a751  call    cs:__imp_SetEvent
0x18000a757  lea     rcx, [rsi+58h]; this
0x18000a75b  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000a760  jmp     loc_18000A828
0x18000a765  mov     rax, [rsi+0D0h]
0x18000a76c  test    rax, rax
0x18000a76f  jnz     short loc_18000A789
0x18000a771  mov     [rsi+0D8h], rdi
0x18000a778  mov     [rsi+0D0h], rdi
0x18000a77f  mov     [rdi+28h], r14
0x18000a783  mov     [rdi+30h], r14
0x18000a787  jmp     short loc_18000A7A3
0x18000a789  mov     [rdi+28h], rax
0x18000a78d  mov     [rdi+30h], r14
0x18000a791  mov     rax, [rsi+0D0h]
0x18000a798  mov     [rax+30h], rdi
0x18000a79c  mov     [rsi+0D0h], rdi
0x18000a7a3  inc     dword ptr [rsi+0E4h]
0x18000a7a9  jmp     short loc_18000A81F
0x18000a7ab  mov     rax, [rsi+0D0h]
0x18000a7b2  mov     rbp, r14
0x18000a7b5  test    rax, rax
0x18000a7b8  jz      short loc_18000A7C1
0x18000a7ba  mov     rbp, [rsi+0D8h]
0x18000a7c1  cmp     [rbp+10h], r14d
0x18000a7c5  jz      short loc_18000A828
0x18000a7c7  test    rax, rax
0x18000a7ca  jz      short loc_18000A7FD
0x18000a7cc  mov     rcx, [rsi+0D8h]
0x18000a7d3  cmp     rax, rcx
0x18000a7d6  jnz     short loc_18000A7E8
0x18000a7d8  mov     [rsi+0D0h], r14
0x18000a7df  mov     [rsi+0D8h], r14
0x18000a7e6  jmp     short loc_18000A7F7
0x18000a7e8  mov     rax, [rcx+30h]
0x18000a7ec  mov     [rsi+0D8h], rax
0x18000a7f3  mov     [rax+28h], r14
0x18000a7f7  dec     dword ptr [rsi+0E4h]
0x18000a7fd  mov     rcx, [rbp+8]
0x18000a801  test    rcx, rcx
0x18000a804  jz      short loc_18000A817
0x18000a806  mov     rax, [rcx]
0x18000a809  mov     rax, [rax+8]
0x18000a80d  call    cs:__guard_dispatch_icall_fptr
0x18000a813  mov     [rbp+8], r14
0x18000a817  mov     rcx, rbp; void *
0x18000a81a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a81f  cmp     dword ptr [rsi+0E4h], 2
0x18000a826  ja      short loc_18000A7AB
0x18000a828  test    ebx, ebx
0x18000a82a  jz      short loc_18000A84E
0x18000a82c  mov     rcx, [rdi+8]
0x18000a830  test    rcx, rcx
0x18000a833  jz      short loc_18000A846
0x18000a835  mov     rdx, [rcx]
0x18000a838  mov     rax, [rdx+8]
0x18000a83c  call    cs:__guard_dispatch_icall_fptr
0x18000a842  mov     [rdi+8], r14
0x18000a846  mov     rcx, rdi; void *
0x18000a849  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a84e  mov     rcx, rsi; lpCriticalSection
0x18000a851  call    cs:__imp_LeaveCriticalSection
0x18000a857  mov     rbp, [rsp+58h+arg_10]
0x18000a85c  mov     eax, ebx
0x18000a85e  mov     rbx, [rsp+58h+arg_8]
0x18000a863  mov     rsi, [rsp+58h+arg_18]
0x18000a868  add     rsp, 30h
0x18000a86c  pop     r15
0x18000a86e  pop     r14
0x18000a870  pop     r13
0x18000a872  pop     r12
0x18000a874  pop     rdi
0x18000a875  retn
```
