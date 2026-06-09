# SIO_COUNTERS::Initialize(ulong,ulong)

- ea: `0x14003e9d8`
- end: `0x14003ea7b`
- name: `?Initialize@SIO_COUNTERS@@QEAAJKK@Z`
- size: `163`
- prototype: `__int64 __fastcall(SIO_COUNTERS *__hidden this, unsigned int, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022500`
- `0x140040fac`
- `0x1400428f0`
- `0x140042d14`
- `0x140046a94`
- `0x14008f898`
- `0x1400b0aa0`
- `0x1400b145c`

## callees

- `0x1400268c0`
- `0x14003e9d8`

## import_xrefs

- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14003e9e9`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14003e9e9`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14003ea19`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14003ea19`

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
0x14003e9d8  push    rbx
0x14003e9da  push    rbp
0x14003e9db  push    rsi
0x14003e9dc  push    rdi
0x14003e9dd  sub     rsp, 28h
0x14003e9e1  mov     edi, r8d
0x14003e9e4  mov     ebx, edx
0x14003e9e6  mov     rsi, rcx
0x14003e9e9  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x14003e9f0  nop     dword ptr [rax+rax+00h]
0x14003e9f5  mov     ebp, eax
0x14003e9f7  lea     edx, [rbx-1]
0x14003e9fa  add     edx, eax
0x14003e9fc  mov     ecx, 0FFFFh; GroupNumber
0x14003ea01  lea     r9d, [rbp-1]
0x14003ea05  not     r9d
0x14003ea08  and     edx, r9d
0x14003ea0b  mov     [rsi+4], edx
0x14003ea0e  lea     edx, [rdi-1]
0x14003ea11  add     edx, eax
0x14003ea13  and     edx, r9d
0x14003ea16  mov     [rsi+8], edx
0x14003ea19  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14003ea20  nop     dword ptr [rax+rax+00h]
0x14003ea25  mov     [rsi], eax
0x14003ea27  xor     r9d, r9d; unsigned int
0x14003ea2a  imul    eax, [rsi+8]
0x14003ea2e  xor     r8d, r8d; unsigned __int8
0x14003ea31  mov     edx, 43497053h; unsigned int
0x14003ea36  add     eax, [rsi+4]
0x14003ea39  lea     ecx, [rax+rbp]; unsigned __int64
0x14003ea3c  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003ea41  mov     [rsi+20h], rax
0x14003ea45  mov     rdx, rax
0x14003ea48  test    rax, rax
0x14003ea4b  jnz     short loc_14003EA54
0x14003ea4d  mov     eax, 0C000009Ah
0x14003ea52  jmp     short loc_14003EA71
0x14003ea54  lea     rcx, [rbp-1]
0x14003ea58  xor     eax, eax
0x14003ea5a  add     rdx, rcx
0x14003ea5d  not     rcx
0x14003ea60  and     rdx, rcx
0x14003ea63  mov     ecx, [rsi+4]
0x14003ea66  add     rcx, rdx
0x14003ea69  mov     [rsi+10h], rdx
0x14003ea6d  mov     [rsi+18h], rcx
0x14003ea71  add     rsp, 28h
0x14003ea75  pop     rdi
0x14003ea76  pop     rsi
0x14003ea77  pop     rbp
0x14003ea78  pop     rbx
0x14003ea79  retn
```
