# CMPCritSecPool::GetCritSecFromPool(CCriticalSection * *)

- ea: `0x383844c00`
- end: `0x383844cb6`
- name: `?GetCritSecFromPool@CMPCritSecPool@@QEAA_NPEAPEAVCCriticalSection@@@Z`
- size: `182`
- prototype: `bool __fastcall(CMPCritSecPool *__hidden this, struct CCriticalSection **)`
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x383844d94`
- `0x38384c2d0`
- `0x38384d2c0`
- `0x38384d420`
- `0x383858c30`
- `0x383868700`
- `0x383870370`
- `0x3838814b0`
- `0x3838832d0`
- `0x3838873a0`
- `0x38388b390`
- `0x38388b950`
- `0x383895640`
- `0x383895ec0`
- `0x38389a170`
- `0x3838a0ef0`
- `0x3838b9d60`
- `0x3839bff20`
- `0x3839d5bb0`
- `0x3839d78a0`
- `0x3839d9380`
- `0x3839e0dd0`
- `0x383a2e300`
- `0x383a50870`
- `0x383a67090`
- `0x383a79ec0`
- `0x383a92740`
- `0x383ad3c60`

## callees

- `0x383844c00`
- `0x383844e18`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3838f3464`
- `KERNEL32!GetLastError` at `0x3838f3464`
- `KERNEL32!TlsGetValue` at `0x383844c24`
- `KERNEL32!TlsGetValue` at `0x383844c24`
- `KERNEL32!TlsSetValue` at `0x383844c8c`
- `KERNEL32!TlsSetValue` at `0x383844c8c`
- `KERNEL32!InterlockedPopEntrySList` at `0x383844c59`
- `KERNEL32!InterlockedPopEntrySList` at `0x383844c59`

## pseudocode

```c
bool __fastcall CMPCritSecPool::GetCritSecFromPool(CMPCritSecPool *this, struct CCriticalSection **a2)
{
  struct CMPCritSecPool *v2; // rbx
  __int64 v4; // rbp
  unsigned __int64 v5; // rsi
  PSLIST_ENTRY v6; // rax
  PSLIST_ENTRY v7; // rax

  v2 = g_pMPCritSecPool;
  v4 = 214013LL * (_QWORD)TlsGetValue(g_tlsCSTLSIndex);
  v5 = (((unsigned __int64)(v4 + 2531011) >> 16) & 0x7FFF) % *((unsigned int *)v2 + 2);
  v6 = InterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)v2 + 32LL * (unsigned int)v5));
  if ( v6 )
    v7 = v6 - 1;
  else
    v7 = 0;
  *(_QWORD *)this = v7;
  if ( v7 )
    *((_DWORD *)&v7[2].Next + 3) = v5;
  else
    *(_QWORD *)this = CreateCriticalSection(v5);
  if ( !TlsSetValue(g_tlsCSTLSIndex, (LPVOID)(v4 + 2531011)) )
    GetLastError();
  return *(_QWORD *)this != 0;
}

```

## disassembly

```asm
0x383844c00  mov     [rsp+arg_0], rbx
0x383844c05  mov     [rsp+arg_8], rbp
0x383844c0a  mov     [rsp+arg_10], rsi
0x383844c0f  push    rdi
0x383844c10  sub     rsp, 20h
0x383844c14  mov     rbx, cs:?g_pMPCritSecPool@@3PEAVCMPCritSecPool@@EA; CMPCritSecPool * g_pMPCritSecPool
0x383844c1b  mov     rdi, rcx
0x383844c1e  mov     ecx, cs:?g_tlsCSTLSIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x383844c24  call    cs:__imp_TlsGetValue
0x383844c2a  mov     r8d, [rbx+8]
0x383844c2e  xor     edx, edx
0x383844c30  mov     rbp, rax
0x383844c33  imul    rbp, 343FDh
0x383844c3a  lea     rax, [rbp+269EC3h]
0x383844c41  shr     rax, 10h
0x383844c45  and     eax, 7FFFh
0x383844c4a  div     r8
0x383844c4d  mov     ecx, edx
0x383844c4f  mov     rsi, rdx
0x383844c52  shl     rcx, 5
0x383844c56  add     rcx, [rbx]; ListHead
0x383844c59  call    cs:__imp_InterlockedPopEntrySList
0x383844c5f  xor     ebx, ebx
0x383844c61  test    rax, rax
0x383844c64  jz      loc_383844DF8
0x383844c6a  add     rax, 0FFFFFFFFFFFFFFF0h
0x383844c6e  jmp     short $+2
0x383844c70  mov     [rdi], rax
0x383844c73  test    rax, rax
0x383844c76  jz      loc_383844E00
0x383844c7c  mov     [rax+2Ch], esi
0x383844c7f  mov     ecx, cs:?g_tlsCSTLSIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x383844c85  lea     rdx, [rbp+269EC3h]; lpTlsValue
0x383844c8c  call    cs:__imp_TlsSetValue
0x383844c92  cmp     eax, 1
0x383844c95  jnz     loc_3838F3464
0x383844c9b  cmp     [rdi], rbx
0x383844c9e  mov     rbp, [rsp+28h+arg_8]
0x383844ca3  mov     rsi, [rsp+28h+arg_10]
0x383844ca8  mov     rbx, [rsp+28h+arg_0]
0x383844cad  setnz   al
0x383844cb0  add     rsp, 20h
0x383844cb4  pop     rdi
0x383844cb5  retn
0x383844df8  mov     rax, rbx
0x383844dfb  jmp     loc_383844C70
0x383844e00  mov     ecx, esi; unsigned int
0x383844e02  call    ?CreateCriticalSection@@YAPEAVCCriticalSection@@K@Z; CreateCriticalSection(ulong)
0x383844e07  mov     [rdi], rax
0x383844e0a  jmp     loc_383844C7F
0x3838f3464  call    cs:__imp_GetLastError
0x3838f346a  nop
0x3838f346b  jmp     loc_383844C9B
```
