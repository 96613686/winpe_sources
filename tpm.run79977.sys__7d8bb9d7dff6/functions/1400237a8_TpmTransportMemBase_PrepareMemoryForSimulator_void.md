# TpmTransportMemBase::PrepareMemoryForSimulator(void)

- ea: `0x1400237a8`
- end: `0x1400239a2`
- name: `?PrepareMemoryForSimulator@TpmTransportMemBase@@AEAAJXZ`
- size: `506`
- prototype: `__int64 __fastcall(TpmTransportMemBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140023450`

## callees

- `0x140022adc`
- `0x1400237a8`
- `0x140024cf4`
- `0x140039780`

## import_xrefs

- `ntoskrnl!MmGetPhysicalAddress` at `0x140023897`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140023910`
- `ntoskrnl!MmGetPhysicalAddress` at `0x14002393e`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140023897`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140023910`
- `ntoskrnl!MmGetPhysicalAddress` at `0x14002393e`
- `ntoskrnl!MmAllocateContiguousMemorySpecifyCache` at `0x1400237e5`
- `ntoskrnl!MmAllocateContiguousMemorySpecifyCache` at `0x1400237e5`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x140023878`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400238f1`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x140023878`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400238f1`

## pseudocode

```c
__int64 __fastcall TpmTransportMemBase::PrepareMemoryForSimulator(TpmTransportMemBase *this)
{
  _OWORD *ContiguousMemorySpecifyCache; // rax
  int v3; // ebx
  void *ContiguousNodeMemory; // rax
  void *v5; // rax
  PHYSICAL_ADDRESS PhysicalAddress; // rax
  union _LARGE_INTEGER v8; // [rsp+70h] [rbp+18h] BYREF
  __int64 v9; // [rsp+78h] [rbp+20h]

  v9 = 0;
  v8.QuadPart = 0;
  ContiguousMemorySpecifyCache = MmAllocateContiguousMemorySpecifyCache(
                                   0x30u,
                                   0,
                                   (PHYSICAL_ADDRESS)-1LL,
                                   0,
                                   MmNonCached);
  *((_QWORD *)this + 39) = ContiguousMemorySpecifyCache;
  if ( !ContiguousMemorySpecifyCache )
    goto LABEL_2;
  *ContiguousMemorySpecifyCache = 0;
  ContiguousMemorySpecifyCache[1] = 0;
  ContiguousMemorySpecifyCache[2] = 0;
  **((_DWORD **)this + 39) = 0;
  *(_DWORD *)(*((_QWORD *)this + 39) + 4LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 39) + 8LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 39) + 12LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 39) + 24LL) = 0x2000;
  *(_DWORD *)(*((_QWORD *)this + 39) + 36LL) = 0x2000;
  ContiguousNodeMemory = (void *)MmAllocateContiguousNodeMemory(0x2000, 0, -1, 0, 4, 0x80000000);
  *((_QWORD *)this + 40) = ContiguousNodeMemory;
  if ( !ContiguousNodeMemory )
    goto LABEL_2;
  *(PHYSICAL_ADDRESS *)(*((_QWORD *)this + 39) + 28LL) = MmGetPhysicalAddress(ContiguousNodeMemory);
  v5 = (void *)((unsigned int)Feature_TpmDrvReadOnlyRespBuf__private_IsEnabledDeviceUsageNoInline()
              ? MmAllocateContiguousNodeMemory(0x2000, 0, -1, 0, 2, 0x80000000)
              : MmAllocateContiguousNodeMemory(0x2000, 0, -1, 0, 4, 0x80000000));
  *((_QWORD *)this + 41) = v5;
  if ( !v5 )
  {
LABEL_2:
    v3 = -1073741670;
LABEL_11:
    (*(void (__fastcall **)(TpmTransportMemBase *))(*(_QWORD *)this + 136LL))(this);
    *((_DWORD *)this + 128) = 0;
    return (unsigned int)v3;
  }
  *(PHYSICAL_ADDRESS *)(*((_QWORD *)this + 39) + 40LL) = MmGetPhysicalAddress(v5);
  PhysicalAddress = MmGetPhysicalAddress(*((PVOID *)this + 39));
  v3 = TpmTransportType::SwapAcpiTableControlArea(PhysicalAddress, &v8);
  if ( v3 < 0 )
    goto LABEL_11;
  *((_DWORD *)this + 128) = 1;
  if ( v8.QuadPart )
  {
    v3 = -1073741823;
    goto LABEL_11;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400237a8  push    rbx
0x1400237aa  push    rbp
0x1400237ab  push    r12
0x1400237ad  push    r14
0x1400237af  push    r15
0x1400237b1  sub     rsp, 30h
0x1400237b5  xor     ebp, ebp
0x1400237b7  mov     qword ptr [rsp+58h+HighestAcceptableAddress], 0FFFFFFFFFFFFFFFFh
0x1400237c0  mov     r8, qword ptr [rsp+58h+HighestAcceptableAddress]; HighestAcceptableAddress
0x1400237c5  mov     r14, rcx
0x1400237c8  mov     ebx, ebp
0x1400237ca  mov     [rsp+58h+arg_18], rbp
0x1400237cf  mov     r9d, ebx; BoundaryAddressMultiple
0x1400237d2  mov     [rsp+58h+arg_8], rbp
0x1400237d7  lea     ecx, [rbp+30h]; NumberOfBytes
0x1400237da  mov     qword ptr [rsp+58h+arg_10], rbp
0x1400237df  mov     edx, ebp; LowestAcceptableAddress
0x1400237e1  mov     [rsp+58h+CacheType], ebp; CacheType
0x1400237e5  call    cs:__imp_MmAllocateContiguousMemorySpecifyCache
0x1400237ec  nop     dword ptr [rax+rax+00h]
0x1400237f1  mov     [r14+138h], rax
0x1400237f8  test    rax, rax
0x1400237fb  jnz     short loc_140023807
0x1400237fd  mov     ebx, 0C000009Ah
0x140023802  jmp     loc_140023979
0x140023807  mov     r8, qword ptr [rsp+58h+HighestAcceptableAddress]
0x14002380c  xorps   xmm0, xmm0
0x14002380f  mov     rdx, [rsp+58h+arg_8]
0x140023814  mov     r12d, 2000h
0x14002381a  movups  xmmword ptr [rax], xmm0
0x14002381d  mov     [rsp+58h+var_30], 80000000h
0x140023825  mov     r9, rbx
0x140023828  movups  xmmword ptr [rax+10h], xmm0
0x14002382c  mov     ecx, r12d
0x14002382f  mov     [rsp+58h+CacheType], 4
0x140023837  movups  xmmword ptr [rax+20h], xmm0
0x14002383b  mov     rax, [r14+138h]
0x140023842  mov     [rax], ebp
0x140023844  mov     rax, [r14+138h]
0x14002384b  mov     [rax+4], ebp
0x14002384e  mov     rax, [r14+138h]
0x140023855  mov     [rax+8], ebp
0x140023858  mov     rax, [r14+138h]
0x14002385f  mov     [rax+0Ch], ebp
0x140023862  mov     rax, [r14+138h]
0x140023869  mov     [rax+18h], r12d
0x14002386d  mov     rax, [r14+138h]
0x140023874  mov     [rax+24h], r12d
0x140023878  call    cs:__imp_MmAllocateContiguousNodeMemory
0x14002387f  nop     dword ptr [rax+rax+00h]
0x140023884  mov     [r14+140h], rax
0x14002388b  test    rax, rax
0x14002388e  jz      loc_1400237FD
0x140023894  mov     rcx, rax; BaseAddress
0x140023897  call    cs:__imp_MmGetPhysicalAddress
0x14002389e  nop     dword ptr [rax+rax+00h]
0x1400238a3  mov     rcx, [r14+138h]
0x1400238aa  mov     rdx, rax
0x1400238ad  shr     rdx, 20h
0x1400238b1  mov     [rcx+20h], edx
0x1400238b4  mov     rdx, [r14+138h]
0x1400238bb  mov     [rdx+1Ch], eax
0x1400238be  call    Feature_TpmDrvReadOnlyRespBuf__private_IsEnabledDeviceUsageNoInline
0x1400238c3  mov     r8, qword ptr [rsp+58h+HighestAcceptableAddress]
0x1400238c8  mov     r9, rbx
0x1400238cb  mov     rdx, [rsp+58h+arg_8]
0x1400238d0  mov     ecx, r12d
0x1400238d3  mov     [rsp+58h+var_30], 80000000h
0x1400238db  test    eax, eax
0x1400238dd  jz      short loc_1400238E9
0x1400238df  mov     [rsp+58h+CacheType], 2
0x1400238e7  jmp     short loc_1400238F1
0x1400238e9  mov     [rsp+58h+CacheType], 4
0x1400238f1  call    cs:__imp_MmAllocateContiguousNodeMemory
0x1400238f8  nop     dword ptr [rax+rax+00h]
0x1400238fd  mov     [r14+148h], rax
0x140023904  test    rax, rax
0x140023907  jz      loc_1400237FD
0x14002390d  mov     rcx, rax; BaseAddress
0x140023910  call    cs:__imp_MmGetPhysicalAddress
0x140023917  nop     dword ptr [rax+rax+00h]
0x14002391c  mov     rcx, [r14+138h]
0x140023923  mov     rdx, rax
0x140023926  shr     rdx, 20h
0x14002392a  mov     [rcx+2Ch], edx
0x14002392d  mov     rcx, [r14+138h]
0x140023934  mov     [rcx+28h], eax
0x140023937  mov     rcx, [r14+138h]; BaseAddress
0x14002393e  call    cs:__imp_MmGetPhysicalAddress
0x140023945  nop     dword ptr [rax+rax+00h]
0x14002394a  mov     rcx, rax; union _LARGE_INTEGER
0x14002394d  lea     rdx, [rsp+58h+arg_10]; union _LARGE_INTEGER *
0x140023952  call    ?SwapAcpiTableControlArea@TpmTransportType@@SAJT_LARGE_INTEGER@@PEAT2@@Z; TpmTransportType::SwapAcpiTableControlArea(_LARGE_INTEGER,_LARGE_INTEGER *)
0x140023957  mov     ebx, eax
0x140023959  test    eax, eax
0x14002395b  js      short loc_140023979
0x14002395d  mov     dword ptr [r14+200h], 1
0x140023968  cmp     dword ptr [rsp+58h+arg_10+4], ebp
0x14002396c  jnz     short loc_140023974
0x14002396e  cmp     dword ptr [rsp+58h+arg_10], ebp
0x140023972  jz      short loc_140023992
0x140023974  mov     ebx, 0C0000001h
0x140023979  mov     rax, [r14]
0x14002397c  mov     rcx, r14
0x14002397f  mov     rax, [rax+88h]
0x140023986  call    _guard_dispatch_icall
0x14002398b  mov     [r14+200h], ebp
0x140023992  mov     eax, ebx
0x140023994  add     rsp, 30h
0x140023998  pop     r15
0x14002399a  pop     r14
0x14002399c  pop     r12
0x14002399e  pop     rbp
0x14002399f  pop     rbx
0x1400239a0  retn
```
