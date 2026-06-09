# VsmmIoctlReadWriteMappedMemoryBlockPageRange

- ea: `0x1400d457c`
- end: `0x1400d477c`
- name: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- size: `512`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, __int64, unsigned __int64, char)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140031fa4`

## callees

- `0x140024754`
- `0x1400307d0`
- `0x140033900`
- `0x140038630`
- `0x1400d457c`
- `0x1400efa10`
- `0x1400f9d70`
- `0x1400faa8c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400d45ea`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400d45ea`

## string_xrefs

- `0x1400d4655`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- `0x1400d46d7`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- `0x1400d46f3`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- `0x1400d4719`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- `0x1400d4759`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`

## pseudocode

```c
__int64 __fastcall VsmmIoctlReadWriteMappedMemoryBlockPageRange(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        char a6)
{
  __int64 v6; // rsi
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rbx
  int v14; // ebx
  __int64 v16; // [rsp+40h] [rbp-39h] BYREF
  __int128 v17; // [rsp+48h] [rbp-31h]
  __int128 v18; // [rsp+58h] [rbp-21h] BYREF
  __int128 v19; // [rsp+68h] [rbp-11h]

  v6 = *(_QWORD *)(a1 + 4256);
  v16 = a1;
  v18 = 0;
  v19 = 0;
  v17 = 0;
  VidLockAcquireShared(v6, a2, a3);
  v11 = VidHandleTableLookupEntry(v6 + 8, a2);
  v12 = v11;
  if ( v11 && (v13 = *(_QWORD *)(v11 + 88), PsGetCurrentProcess() == v13) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 136));
    VidLockRelease(v6);
    if ( a3 > 0xFFFFF000 || a5 > 0xFFFFF000 || a3 + a5 > *(_QWORD *)(v12 + 32) << 12 )
    {
      v14 = -1073741811;
      VidTraceErrorInternal0(
        "VsmmIoctlReadWriteMappedMemoryBlockPageRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        4117);
    }
    else if ( (*(_DWORD *)(*(_QWORD *)(v12 + 16) + 20LL) & 8) != 0 )
    {
      v14 = -1073741811;
      VidTraceErrorInternal0(
        "VsmmIoctlReadWriteMappedMemoryBlockPageRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        4124);
    }
    else
    {
      *(_QWORD *)&v18 = a3;
      *((_QWORD *)&v18 + 1) = a4;
      *(_QWORD *)&v19 = a5;
      BYTE8(v19) = a6;
      HIDWORD(v19) = 0;
      v14 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD, __int64 (__fastcall *)(), __int128 *))VsmmMemoryBlockMbpRangeVaMap)(
              &v16,
              *(_QWORD *)(v12 + 16),
              *(_QWORD *)(v12 + 24),
              *(_QWORD *)(v12 + 32),
              a6 & 1 | (2 * (a6 & 1u)),
              0,
              VsmmpReadWriteMappedMemoryCallback,
              &v18);
      if ( v14 < 0 || (v14 = HIDWORD(v19), v19 < 0) )
        VidTraceErrorInternal0(
          "VsmmIoctlReadWriteMappedMemoryBlockPageRange",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
          4163);
    }
  }
  else
  {
    v12 = 0;
    VidLockRelease(v6);
    v14 = -1070137320;
    VidTraceErrorInternal0(
      "VsmmIoctlReadWriteMappedMemoryBlockPageRange",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
      4104);
  }
  VsmmMemoryBlockMbpRangeVaDestroy(&v16);
  if ( v12 )
    _InterlockedDecrement((volatile signed __int32 *)(v12 + 136));
  if ( v14 < 0 )
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VsmmIoctlReadWriteMappedMemoryBlockPageRange",
      (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
      4176,
      v14,
      a1 + 656);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400d457c  push    rbp
0x1400d457e  push    rbx
0x1400d457f  push    rsi
0x1400d4580  push    rdi
0x1400d4581  push    r12
0x1400d4583  push    r13
0x1400d4585  push    r14
0x1400d4587  push    r15
0x1400d4589  lea     rbp, [rsp-0Fh]
0x1400d458e  sub     rsp, 88h
0x1400d4595  mov     rsi, [rcx+10A0h]
0x1400d459c  xorps   xmm0, xmm0
0x1400d459f  mov     r15, rcx
0x1400d45a2  mov     [rbp+47h+var_80], rcx
0x1400d45a6  xorps   xmm1, xmm1
0x1400d45a9  mov     rcx, rsi
0x1400d45ac  mov     r12, r9
0x1400d45af  mov     r14, r8
0x1400d45b2  mov     rbx, rdx
0x1400d45b5  movups  [rbp+47h+var_68], xmm0
0x1400d45b9  movups  [rbp+47h+var_58], xmm0
0x1400d45bd  movdqu  [rbp+47h+var_78], xmm1
0x1400d45c2  call    VidLockAcquireShared
0x1400d45c7  lea     rcx, [rsi+8]
0x1400d45cb  mov     rdx, rbx
0x1400d45ce  call    VidHandleTableLookupEntry
0x1400d45d3  lea     r13, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d45da  mov     rdi, rax
0x1400d45dd  test    rax, rax
0x1400d45e0  jz      loc_1400D4704
0x1400d45e6  mov     rbx, [rax+58h]
0x1400d45ea  call    cs:__imp_PsGetCurrentProcess
0x1400d45f1  nop     dword ptr [rax+rax+00h]
0x1400d45f6  cmp     rax, rbx
0x1400d45f9  jnz     loc_1400D4704
0x1400d45ff  lock inc dword ptr [rdi+88h]
0x1400d4606  mov     rcx, rsi
0x1400d4609  call    VidLockRelease
0x1400d460e  mov     eax, 0FFFFF000h
0x1400d4613  cmp     r14, rax
0x1400d4616  ja      loc_1400D46E8
0x1400d461c  mov     r8, [rbp+47h+arg_20]
0x1400d4620  cmp     r8, rax
0x1400d4623  ja      loc_1400D46E8
0x1400d4629  mov     rax, [rdi+20h]
0x1400d462d  lea     rcx, [r14+r8]
0x1400d4631  shl     rax, 0Ch
0x1400d4635  cmp     rcx, rax
0x1400d4638  ja      loc_1400D46E8
0x1400d463e  mov     rax, [rdi+10h]
0x1400d4642  mov     ecx, [rax+14h]
0x1400d4645  test    cl, 8
0x1400d4648  jz      short loc_1400D4669
0x1400d464a  mov     ebx, 0C000000Dh
0x1400d464f  mov     r8d, 101Ch
0x1400d4655  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d465c  mov     rdx, r13
0x1400d465f  call    VidTraceErrorInternal0
0x1400d4664  jmp     loc_1400D4728
0x1400d4669  movzx   edx, [rbp+47h+arg_28]
0x1400d466d  mov     ecx, edx
0x1400d466f  mov     qword ptr [rbp+47h+var_68], r14
0x1400d4673  and     ecx, 1
0x1400d4676  mov     qword ptr [rbp+47h+var_68+8], r12
0x1400d467a  mov     qword ptr [rbp+47h+var_58], r8
0x1400d467e  mov     byte ptr [rbp+47h+var_58+8], dl
0x1400d4681  mov     dword ptr [rbp+47h+var_58+0Ch], 0
0x1400d4688  mov     r9, [rdi+20h]
0x1400d468c  lea     eax, [rcx+rcx]
0x1400d468f  mov     r8, [rdi+18h]
0x1400d4693  or      eax, ecx
0x1400d4695  mov     rdx, [rdi+10h]
0x1400d4699  lea     rcx, [rbp+47h+var_68]
0x1400d469d  mov     [rsp+0C0h+var_88], rcx
0x1400d46a2  lea     rcx, VsmmpReadWriteMappedMemoryCallback
0x1400d46a9  mov     [rsp+0C0h+var_90], rcx
0x1400d46ae  lea     rcx, [rbp+47h+var_80]
0x1400d46b2  mov     [rsp+0C0h+var_98], 0
0x1400d46bb  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1400d46bf  call    VsmmMemoryBlockMbpRangeVaMap
0x1400d46c4  mov     ebx, eax
0x1400d46c6  test    eax, eax
0x1400d46c8  js      short loc_1400D46D1
0x1400d46ca  mov     ebx, dword ptr [rbp+47h+var_58+0Ch]
0x1400d46cd  test    ebx, ebx
0x1400d46cf  jns     short loc_1400D4728
0x1400d46d1  mov     r8d, 1043h
0x1400d46d7  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d46de  mov     rdx, r13
0x1400d46e1  call    VidTraceErrorInternal0
0x1400d46e6  jmp     short loc_1400D4728
0x1400d46e8  mov     ebx, 0C000000Dh
0x1400d46ed  mov     r8d, 1015h
0x1400d46f3  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d46fa  mov     rdx, r13
0x1400d46fd  call    VidTraceErrorInternal0
0x1400d4702  jmp     short loc_1400D4728
0x1400d4704  xor     edi, edi
0x1400d4706  mov     rcx, rsi
0x1400d4709  call    VidLockRelease
0x1400d470e  mov     ebx, 0C0370018h
0x1400d4713  mov     r8d, 1008h
0x1400d4719  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d4720  mov     rdx, r13
0x1400d4723  call    VidTraceErrorInternal0
0x1400d4728  lea     rcx, [rbp+47h+var_80]
0x1400d472c  call    VsmmMemoryBlockMbpRangeVaDestroy
0x1400d4731  test    rdi, rdi
0x1400d4734  jz      short loc_1400D473D
0x1400d4736  lock dec dword ptr [rdi+88h]
0x1400d473d  test    ebx, ebx
0x1400d473f  jns     short loc_1400D4765
0x1400d4741  lea     rax, [r15+290h]
0x1400d4748  mov     r9d, ebx
0x1400d474b  mov     r8d, 1050h
0x1400d4751  mov     [rsp+0C0h+var_A0], rax
0x1400d4756  mov     rdx, r13
0x1400d4759  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d4760  call    VidTraceErrorStatusPartitionInternal0
0x1400d4765  mov     eax, ebx
0x1400d4767  add     rsp, 88h
0x1400d476e  pop     r15
0x1400d4770  pop     r14
0x1400d4772  pop     r13
0x1400d4774  pop     r12
0x1400d4776  pop     rdi
0x1400d4777  pop     rsi
0x1400d4778  pop     rbx
0x1400d4779  pop     rbp
0x1400d477a  retn
```
