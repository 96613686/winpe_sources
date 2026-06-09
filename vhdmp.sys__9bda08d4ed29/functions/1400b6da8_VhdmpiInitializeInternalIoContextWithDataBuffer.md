# VhdmpiInitializeInternalIoContextWithDataBuffer

- ea: `0x1400b6da8`
- end: `0x1400b6f43`
- name: `VhdmpiInitializeInternalIoContextWithDataBuffer`
- size: `411`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400b6ca4`
- `0x1400b6f4c`
- `0x1400b9080`
- `0x1400cb980`

## callees

- `0x14001f980`
- `0x1400b6da8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b6e01`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b6e01`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6eac`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6eac`
- `ntoskrnl!KeInitializeEvent` at `0x1400b6f23`
- `ntoskrnl!KeInitializeEvent` at `0x1400b6f23`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeInternalIoContextWithDataBuffer(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // rdi
  PVOID v9; // rax
  int v11; // eax
  __int64 v12; // rsi
  unsigned int v13; // ecx
  unsigned int v14; // eax
  __int64 v15; // r14
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rax
  __int64 Pool2; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx

  v7 = a4;
  *(_DWORD *)(a1 + 72) = 2;
  *(_DWORD *)(a1 + 8) = a3;
  if ( a2 )
  {
    *(_QWORD *)(a1 + 16) = a2;
    if ( !a5 )
    {
      v9 = (*(_BYTE *)(a2 + 10) & 5) != 0
         ? *(PVOID *)(a2 + 24)
         : MmMapLockedPagesSpecifyCache((PMDL)a2, 0, MmCached, 0, 0, 0x40000010u);
      *(_QWORD *)a1 = v9;
      if ( !v9 )
        return 3221225626LL;
    }
  }
  *(_DWORD *)(a1 + 152) = v7;
  v11 = VhdmpiSrbExtensionSize(0);
  v12 = (8 * (unsigned int)(((unsigned __int64)*(unsigned int *)(a1 + 8) + 8190) >> 12) + 135) & 0xFFFFFFF0;
  if ( (unsigned int)v12 < 8 * (unsigned int)(((unsigned __int64)*(unsigned int *)(a1 + 8) + 8190) >> 12) + 120 )
    return 3221225621LL;
  v13 = v12 + v11;
  if ( (int)v12 + v11 < (unsigned int)v12 )
    return 3221225621LL;
  v14 = (v13 + 15) & 0xFFFFFFF0;
  if ( v14 < v13 )
    return 3221225621LL;
  v15 = v14;
  v16 = v14 * v7;
  if ( v16 > 0xFFFFFFFF )
    return 3221225621LL;
  v17 = 8LL * a5;
  if ( v17 > 0xFFFFFFFF || (int)v17 + (int)v16 < (unsigned int)v17 )
    return 3221225621LL;
  Pool2 = ExAllocatePool2(72, (unsigned int)(v17 + v16), 1665419350);
  v19 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  if ( a5 )
  {
    *(_QWORD *)(a1 + 24) = Pool2 + (unsigned int)v16;
    *(_QWORD *)(a1 + 32) = a6;
  }
  v20 = 0;
  for ( *(_QWORD *)(a1 + 40) = a7; (unsigned int)v20 < *(_DWORD *)(a1 + 152); v19 += v15 )
  {
    *(_QWORD *)(v19 + 8) = v12 + v19;
    *(_QWORD *)(a1 + 8 * v20 + 160) = v19;
    v20 = (unsigned int)(v20 + 1);
    *(_QWORD *)(v19 + 16) = a1;
  }
  KeInitializeEvent((PRKEVENT)(a1 + 112), NotificationEvent, 0);
  return 0;
}

```

## disassembly

```asm
0x1400b6da8  push    rbx
0x1400b6daa  push    rsi
0x1400b6dab  push    rdi
0x1400b6dac  push    r14
0x1400b6dae  sub     rsp, 38h
0x1400b6db2  mov     edi, r9d
0x1400b6db5  mov     r10, rdx
0x1400b6db8  mov     dword ptr [rcx+48h], 2
0x1400b6dbf  mov     rbx, rcx
0x1400b6dc2  mov     [rcx+8], r8d
0x1400b6dc6  test    rdx, rdx
0x1400b6dc9  jz      short loc_1400B6E1F
0x1400b6dcb  cmp     [rsp+58h+arg_20], 0
0x1400b6dd3  mov     [rcx+10h], rdx
0x1400b6dd7  jnz     short loc_1400B6E1F
0x1400b6dd9  test    byte ptr [rdx+0Ah], 5
0x1400b6ddd  jz      short loc_1400B6DE5
0x1400b6ddf  mov     rax, [rdx+18h]
0x1400b6de3  jmp     short loc_1400B6E0D
0x1400b6de5  xor     r9d, r9d; RequestedAddress
0x1400b6de8  mov     [rsp+58h+Priority], 40000010h; Priority
0x1400b6df0  xor     edx, edx; AccessMode
0x1400b6df2  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400b6dfa  mov     rcx, r10; MemoryDescriptorList
0x1400b6dfd  lea     r8d, [r9+1]; CacheType
0x1400b6e01  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400b6e08  nop     dword ptr [rax+rax+00h]
0x1400b6e0d  mov     [rbx], rax
0x1400b6e10  test    rax, rax
0x1400b6e13  jnz     short loc_1400B6E1F
0x1400b6e15  mov     eax, 0C000009Ah
0x1400b6e1a  jmp     loc_1400B6F38
0x1400b6e1f  xor     ecx, ecx
0x1400b6e21  mov     [rbx+98h], edi
0x1400b6e27  call    VhdmpiSrbExtensionSize
0x1400b6e2c  mov     ecx, [rbx+8]
0x1400b6e2f  mov     edx, 0FFFFFFF0h
0x1400b6e34  add     rcx, 1FFEh
0x1400b6e3b  shr     rcx, 0Ch
0x1400b6e3f  lea     ecx, ds:78h[rcx*8]
0x1400b6e46  lea     esi, [rcx+0Fh]
0x1400b6e49  and     esi, edx
0x1400b6e4b  cmp     esi, ecx
0x1400b6e4d  jb      loc_1400B6F33
0x1400b6e53  lea     ecx, [rsi+rax]
0x1400b6e56  cmp     ecx, esi
0x1400b6e58  jb      loc_1400B6F33
0x1400b6e5e  lea     eax, [rcx+0Fh]
0x1400b6e61  and     eax, edx
0x1400b6e63  cmp     eax, ecx
0x1400b6e65  jb      loc_1400B6F33
0x1400b6e6b  mov     r14d, eax
0x1400b6e6e  mov     ecx, 0FFFFFFFFh
0x1400b6e73  imul    rdi, r14
0x1400b6e77  cmp     rdi, rcx
0x1400b6e7a  ja      loc_1400B6F33
0x1400b6e80  mov     eax, [rsp+58h+arg_20]
0x1400b6e87  shl     rax, 3
0x1400b6e8b  cmp     rax, rcx
0x1400b6e8e  ja      loc_1400B6F33
0x1400b6e94  lea     ecx, [rax+rdi]
0x1400b6e97  cmp     ecx, eax
0x1400b6e99  jb      loc_1400B6F33
0x1400b6e9f  mov     edx, ecx
0x1400b6ea1  mov     r8d, 63444856h
0x1400b6ea7  mov     ecx, 48h ; 'H'
0x1400b6eac  call    cs:__imp_ExAllocatePool2
0x1400b6eb3  nop     dword ptr [rax+rax+00h]
0x1400b6eb8  mov     rcx, rax
0x1400b6ebb  test    rax, rax
0x1400b6ebe  jz      loc_1400B6E15
0x1400b6ec4  cmp     [rsp+58h+arg_20], 0
0x1400b6ecc  jbe     short loc_1400B6EE3
0x1400b6ece  mov     eax, edi
0x1400b6ed0  add     rax, rcx
0x1400b6ed3  mov     [rbx+18h], rax
0x1400b6ed7  mov     rax, [rsp+58h+arg_28]
0x1400b6edf  mov     [rbx+20h], rax
0x1400b6ee3  mov     rax, [rsp+58h+arg_30]
0x1400b6eeb  xor     edx, edx
0x1400b6eed  mov     [rbx+28h], rax
0x1400b6ef1  cmp     [rbx+98h], edx
0x1400b6ef7  jbe     short loc_1400B6F1A
0x1400b6ef9  lea     rax, [rsi+rcx]
0x1400b6efd  mov     [rcx+8], rax
0x1400b6f01  mov     [rbx+rdx*8+0A0h], rcx
0x1400b6f09  inc     edx
0x1400b6f0b  mov     [rcx+10h], rbx
0x1400b6f0f  add     rcx, r14
0x1400b6f12  cmp     edx, [rbx+98h]
0x1400b6f18  jb      short loc_1400B6EF9
0x1400b6f1a  lea     rcx, [rbx+70h]; Event
0x1400b6f1e  xor     r8d, r8d; State
0x1400b6f21  xor     edx, edx; Type
0x1400b6f23  call    cs:__imp_KeInitializeEvent
0x1400b6f2a  nop     dword ptr [rax+rax+00h]
0x1400b6f2f  xor     eax, eax
0x1400b6f31  jmp     short loc_1400B6F38
0x1400b6f33  mov     eax, 0C0000095h
0x1400b6f38  add     rsp, 38h
0x1400b6f3c  pop     r14
0x1400b6f3e  pop     rdi
0x1400b6f3f  pop     rsi
0x1400b6f40  pop     rbx
0x1400b6f41  retn
```
