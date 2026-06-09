# SIO_COUNTERS::Initialize(ulong,ulong)

- ea: `0x14003ea98`
- end: `0x14003eb3b`
- name: `?Initialize@SIO_COUNTERS@@QEAAJKK@Z`
- size: `163`
- prototype: `__int64 __fastcall(SIO_COUNTERS *__hidden this, unsigned int, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022500`
- `0x14004106c`
- `0x1400429b0`
- `0x140042dd4`
- `0x140046b54`
- `0x14008f898`
- `0x1400b0c40`
- `0x1400b15fc`

## callees

- `0x1400268c0`
- `0x14003ea98`

## import_xrefs

- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14003eaa9`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14003eaa9`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14003ead9`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14003ead9`

## pseudocode

```c
__int64 __fastcall SIO_COUNTERS::Initialize(SIO_COUNTERS *this, int a2, int a3)
{
  ULONG RecommendedSharedDataAlignment; // eax
  __int64 v7; // rbp
  int v8; // r9d
  ULONG ActiveProcessorCount; // eax
  void *v10; // rax
  void *v11; // rdx
  __int64 result; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx

  RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
  v7 = RecommendedSharedDataAlignment;
  v8 = ~(RecommendedSharedDataAlignment - 1);
  *((_DWORD *)this + 1) = v8 & (RecommendedSharedDataAlignment + a2 - 1);
  *((_DWORD *)this + 2) = v8 & (RecommendedSharedDataAlignment + a3 - 1);
  ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  *(_DWORD *)this = ActiveProcessorCount;
  v10 = SC_ENV::Allocate(
          *((_DWORD *)this + 1) + *((_DWORD *)this + 2) * ActiveProcessorCount + (unsigned int)v7,
          0x43497053u,
          0,
          0);
  *((_QWORD *)this + 4) = v10;
  v11 = v10;
  if ( !v10 )
    return 3221225626LL;
  result = 0;
  v13 = ~(v7 - 1) & ((unsigned __int64)v11 + v7 - 1);
  v14 = *((unsigned int *)this + 1);
  *((_QWORD *)this + 2) = v13;
  *((_QWORD *)this + 3) = v13 + v14;
  return result;
}

```

## disassembly

```asm
0x14003ea98  push    rbx
0x14003ea9a  push    rbp
0x14003ea9b  push    rsi
0x14003ea9c  push    rdi
0x14003ea9d  sub     rsp, 28h
0x14003eaa1  mov     edi, r8d
0x14003eaa4  mov     ebx, edx
0x14003eaa6  mov     rsi, rcx
0x14003eaa9  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x14003eab0  nop     dword ptr [rax+rax+00h]
0x14003eab5  mov     ebp, eax
0x14003eab7  lea     edx, [rbx-1]
0x14003eaba  add     edx, eax
0x14003eabc  mov     ecx, 0FFFFh; GroupNumber
0x14003eac1  lea     r9d, [rbp-1]
0x14003eac5  not     r9d
0x14003eac8  and     edx, r9d
0x14003eacb  mov     [rsi+4], edx
0x14003eace  lea     edx, [rdi-1]
0x14003ead1  add     edx, eax
0x14003ead3  and     edx, r9d
0x14003ead6  mov     [rsi+8], edx
0x14003ead9  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14003eae0  nop     dword ptr [rax+rax+00h]
0x14003eae5  mov     [rsi], eax
0x14003eae7  xor     r9d, r9d; unsigned int
0x14003eaea  imul    eax, [rsi+8]
0x14003eaee  xor     r8d, r8d; unsigned __int8
0x14003eaf1  mov     edx, 43497053h; unsigned int
0x14003eaf6  add     eax, [rsi+4]
0x14003eaf9  lea     ecx, [rax+rbp]; unsigned __int64
0x14003eafc  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003eb01  mov     [rsi+20h], rax
0x14003eb05  mov     rdx, rax
0x14003eb08  test    rax, rax
0x14003eb0b  jnz     short loc_14003EB14
0x14003eb0d  mov     eax, 0C000009Ah
0x14003eb12  jmp     short loc_14003EB31
0x14003eb14  lea     rcx, [rbp-1]
0x14003eb18  xor     eax, eax
0x14003eb1a  add     rdx, rcx
0x14003eb1d  not     rcx
0x14003eb20  and     rdx, rcx
0x14003eb23  mov     ecx, [rsi+4]
0x14003eb26  add     rcx, rdx
0x14003eb29  mov     [rsi+10h], rdx
0x14003eb2d  mov     [rsi+18h], rcx
0x14003eb31  add     rsp, 28h
0x14003eb35  pop     rdi
0x14003eb36  pop     rsi
0x14003eb37  pop     rbp
0x14003eb38  pop     rbx
0x14003eb39  retn
```
