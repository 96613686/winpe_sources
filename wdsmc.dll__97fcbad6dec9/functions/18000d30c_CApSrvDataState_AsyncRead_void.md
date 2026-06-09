# CApSrvDataState::AsyncRead(void)

- ea: `0x18000d30c`
- end: `0x18000d44d`
- name: `?AsyncRead@CApSrvDataState@@AEAAKXZ`
- size: `321`
- prototype: `unsigned int __fastcall(CApSrvDataState *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d454`

## callees

- `0x18000a5a4`
- `0x18000d30c`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000d426`
- `KERNEL32!LeaveCriticalSection` at `0x18000d426`
- `KERNEL32!EnterCriticalSection` at `0x18000d33b`
- `KERNEL32!EnterCriticalSection` at `0x18000d33b`

## string_xrefs

- `0x18000d3d7`: `WDSMCSE[0x%x] AsyncRead - Offsets=%I64u-%I64u, BlkRange=%I64u-%I64u`

## pseudocode

```c
__int64 __fastcall CApSrvDataState::AsyncRead(CApSrvDataState *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  __int64 v3; // r14
  __int64 v4; // r15
  const char *v5; // rdx
  unsigned int Async; // esi
  __int64 v7; // rsi
  unsigned __int64 v8; // r12
  unsigned __int64 v9; // rsi
  unsigned __int32 v10; // edi
  const char *v11; // rdx

  v1 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  v3 = 0;
  v4 = 0;
  EnterCriticalSection(v1);
  if ( *((_DWORD *)this + 331) < *((_DWORD *)this + 330) )
  {
    v3 = *((_QWORD *)this + 166);
    Async = 0;
    v4 = *(_QWORD *)(*((_QWORD *)this + 164) + 16LL * *((unsigned int *)this + 331) + 8);
  }
  else
  {
    Async = 259;
  }
  if ( !ElValidateWin32(Async, v5, "base\\eco\\wds\\transport\\server\\mc\\apsrvdatastate.cpp", 0x15Du) )
  {
    v7 = *((unsigned int *)this + 70) * (v4 + 1);
    v8 = v3 * *((unsigned int *)this + 70);
    if ( v7 - 1 >= (unsigned __int64)(*((_QWORD *)this + 33) - 1LL) )
      v7 = *((_QWORD *)this + 33);
    v9 = v7 - 1;
    if ( g_ErrLibTraceFunctionEx )
    {
      v10 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 3) + 2216LL), 0);
      g_ErrLibTraceFunctionEx(
        0x10000u,
        L"WDSMCSE[0x%x] AsyncRead - Offsets=%I64u-%I64u, BlkRange=%I64u-%I64u",
        v10,
        v8,
        v9,
        v3,
        v4);
    }
    Async = CContentCache::ReadAsync((char *)this + 32, v8, v9);
    ElValidateWin32(Async, v11, "base\\eco\\wds\\transport\\server\\mc\\apsrvdatastate.cpp", 0x16Bu);
  }
  LeaveCriticalSection(v1);
  return Async;
}

```

## disassembly

```asm
0x18000d30c  mov     rax, rsp
0x18000d30f  mov     [rax+8], rbx
0x18000d313  mov     [rax+10h], rbp
0x18000d317  mov     [rax+18h], rsi
0x18000d31b  mov     [rax+20h], rdi
0x18000d31f  push    r12
0x18000d321  push    r14
0x18000d323  push    r15
0x18000d325  sub     rsp, 40h
0x18000d329  mov     rbp, [rcx+8]
0x18000d32d  mov     rbx, rcx
0x18000d330  xor     edi, edi
0x18000d332  mov     rcx, rbp; lpCriticalSection
0x18000d335  mov     r14d, edi
0x18000d338  mov     r15d, edi
0x18000d33b  call    cs:__imp_EnterCriticalSection
0x18000d341  mov     eax, [rbx+52Ch]
0x18000d347  cmp     eax, [rbx+528h]
0x18000d34d  jb      short loc_18000D356
0x18000d34f  mov     esi, 103h
0x18000d354  jmp     short loc_18000D371
0x18000d356  mov     r14, [rbx+530h]
0x18000d35d  mov     rcx, rax
0x18000d360  mov     rax, [rbx+520h]
0x18000d367  add     rcx, rcx
0x18000d36a  mov     esi, edi
0x18000d36c  mov     r15, [rax+rcx*8+8]
0x18000d371  mov     r9d, 15Dh; unsigned int
0x18000d377  lea     r8, aBaseEcoWdsTran_24; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000d37e  mov     ecx, esi; unsigned int
0x18000d380  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d385  test    eax, eax
0x18000d387  jnz     loc_18000D423
0x18000d38d  mov     eax, [rbx+118h]
0x18000d393  lea     rsi, [r15+1]
0x18000d397  mov     rdx, [rbx+108h]
0x18000d39e  mov     r12d, eax
0x18000d3a1  imul    rsi, rax
0x18000d3a5  imul    r12, r14
0x18000d3a9  lea     rcx, [rsi-1]
0x18000d3ad  lea     rax, [rdx-1]
0x18000d3b1  cmp     rcx, rax
0x18000d3b4  cmovnb  rsi, rdx
0x18000d3b8  dec     rsi
0x18000d3bb  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rdi; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000d3c2  jz      short loc_18000D3FE
0x18000d3c4  mov     rax, [rbx+18h]
0x18000d3c8  lock xadd [rax+8A8h], edi
0x18000d3d0  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000d3d7  lea     rdx, aWdsmcse0xXAsyn; "WDSMCSE[0x%x] AsyncRead - Offsets=%I64u"...
0x18000d3de  mov     [rsp+58h+var_28], r15
0x18000d3e3  mov     r9, r12
0x18000d3e6  mov     [rsp+58h+var_30], r14
0x18000d3eb  mov     r8d, edi
0x18000d3ee  mov     ecx, 10000h
0x18000d3f3  mov     [rsp+58h+var_38], rsi
0x18000d3f8  call    cs:__guard_dispatch_icall_fptr
0x18000d3fe  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000d402  mov     r8, rsi; unsigned __int64
0x18000d405  mov     rdx, r12; unsigned __int64
0x18000d408  call    ?ReadAsync@CContentCache@@QEAAK_K0@Z; CContentCache::ReadAsync(unsigned __int64,unsigned __int64)
0x18000d40d  mov     r9d, 16Bh; unsigned int
0x18000d413  lea     r8, aBaseEcoWdsTran_24; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000d41a  mov     ecx, eax; unsigned int
0x18000d41c  mov     esi, eax
0x18000d41e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d423  mov     rcx, rbp; lpCriticalSection
0x18000d426  call    cs:__imp_LeaveCriticalSection
0x18000d42c  mov     rbx, [rsp+58h+arg_0]
0x18000d431  mov     eax, esi
0x18000d433  mov     rsi, [rsp+58h+arg_10]
0x18000d438  mov     rbp, [rsp+58h+arg_8]
0x18000d43d  mov     rdi, [rsp+58h+arg_18]
0x18000d442  add     rsp, 40h
0x18000d446  pop     r15
0x18000d448  pop     r14
0x18000d44a  pop     r12
0x18000d44c  retn
```
