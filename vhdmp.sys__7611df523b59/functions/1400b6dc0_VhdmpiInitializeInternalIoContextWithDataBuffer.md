# VhdmpiInitializeInternalIoContextWithDataBuffer

- ea: `0x1400b6dc0`
- end: `0x1400b6f5b`
- name: `VhdmpiInitializeInternalIoContextWithDataBuffer`
- size: `411`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400b6cbc`
- `0x1400b6f64`
- `0x1400b9090`
- `0x1400cb990`

## callees

- `0x14001f560`
- `0x1400b6dc0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b6e19`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b6e19`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6ec4`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6ec4`
- `ntoskrnl!KeInitializeEvent` at `0x1400b6f3b`
- `ntoskrnl!KeInitializeEvent` at `0x1400b6f3b`

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
0x1400b6dc0  push    rbx
0x1400b6dc2  push    rsi
0x1400b6dc3  push    rdi
0x1400b6dc4  push    r14
0x1400b6dc6  sub     rsp, 38h
0x1400b6dca  mov     edi, r9d
0x1400b6dcd  mov     r10, rdx
0x1400b6dd0  mov     dword ptr [rcx+48h], 2
0x1400b6dd7  mov     rbx, rcx
0x1400b6dda  mov     [rcx+8], r8d
0x1400b6dde  test    rdx, rdx
0x1400b6de1  jz      short loc_1400B6E37
0x1400b6de3  cmp     [rsp+58h+arg_20], 0
0x1400b6deb  mov     [rcx+10h], rdx
0x1400b6def  jnz     short loc_1400B6E37
0x1400b6df1  test    byte ptr [rdx+0Ah], 5
0x1400b6df5  jz      short loc_1400B6DFD
0x1400b6df7  mov     rax, [rdx+18h]
0x1400b6dfb  jmp     short loc_1400B6E25
0x1400b6dfd  xor     r9d, r9d; RequestedAddress
0x1400b6e00  mov     [rsp+58h+Priority], 40000010h; Priority
0x1400b6e08  xor     edx, edx; AccessMode
0x1400b6e0a  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400b6e12  mov     rcx, r10; MemoryDescriptorList
0x1400b6e15  lea     r8d, [r9+1]; CacheType
0x1400b6e19  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400b6e20  nop     dword ptr [rax+rax+00h]
0x1400b6e25  mov     [rbx], rax
0x1400b6e28  test    rax, rax
0x1400b6e2b  jnz     short loc_1400B6E37
0x1400b6e2d  mov     eax, 0C000009Ah
0x1400b6e32  jmp     loc_1400B6F50
0x1400b6e37  xor     ecx, ecx
0x1400b6e39  mov     [rbx+98h], edi
0x1400b6e3f  call    VhdmpiSrbExtensionSize
0x1400b6e44  mov     ecx, [rbx+8]
0x1400b6e47  mov     edx, 0FFFFFFF0h
0x1400b6e4c  add     rcx, 1FFEh
0x1400b6e53  shr     rcx, 0Ch
0x1400b6e57  lea     ecx, ds:78h[rcx*8]
0x1400b6e5e  lea     esi, [rcx+0Fh]
0x1400b6e61  and     esi, edx
0x1400b6e63  cmp     esi, ecx
0x1400b6e65  jb      loc_1400B6F4B
0x1400b6e6b  lea     ecx, [rsi+rax]
0x1400b6e6e  cmp     ecx, esi
0x1400b6e70  jb      loc_1400B6F4B
0x1400b6e76  lea     eax, [rcx+0Fh]
0x1400b6e79  and     eax, edx
0x1400b6e7b  cmp     eax, ecx
0x1400b6e7d  jb      loc_1400B6F4B
0x1400b6e83  mov     r14d, eax
0x1400b6e86  mov     ecx, 0FFFFFFFFh
0x1400b6e8b  imul    rdi, r14
0x1400b6e8f  cmp     rdi, rcx
0x1400b6e92  ja      loc_1400B6F4B
0x1400b6e98  mov     eax, [rsp+58h+arg_20]
0x1400b6e9f  shl     rax, 3
0x1400b6ea3  cmp     rax, rcx
0x1400b6ea6  ja      loc_1400B6F4B
0x1400b6eac  lea     ecx, [rax+rdi]
0x1400b6eaf  cmp     ecx, eax
0x1400b6eb1  jb      loc_1400B6F4B
0x1400b6eb7  mov     edx, ecx
0x1400b6eb9  mov     r8d, 63444856h
0x1400b6ebf  mov     ecx, 48h ; 'H'
0x1400b6ec4  call    cs:__imp_ExAllocatePool2
0x1400b6ecb  nop     dword ptr [rax+rax+00h]
0x1400b6ed0  mov     rcx, rax
0x1400b6ed3  test    rax, rax
0x1400b6ed6  jz      loc_1400B6E2D
0x1400b6edc  cmp     [rsp+58h+arg_20], 0
0x1400b6ee4  jbe     short loc_1400B6EFB
0x1400b6ee6  mov     eax, edi
0x1400b6ee8  add     rax, rcx
0x1400b6eeb  mov     [rbx+18h], rax
0x1400b6eef  mov     rax, [rsp+58h+arg_28]
0x1400b6ef7  mov     [rbx+20h], rax
0x1400b6efb  mov     rax, [rsp+58h+arg_30]
0x1400b6f03  xor     edx, edx
0x1400b6f05  mov     [rbx+28h], rax
0x1400b6f09  cmp     [rbx+98h], edx
0x1400b6f0f  jbe     short loc_1400B6F32
0x1400b6f11  lea     rax, [rsi+rcx]
0x1400b6f15  mov     [rcx+8], rax
0x1400b6f19  mov     [rbx+rdx*8+0A0h], rcx
0x1400b6f21  inc     edx
0x1400b6f23  mov     [rcx+10h], rbx
0x1400b6f27  add     rcx, r14
0x1400b6f2a  cmp     edx, [rbx+98h]
0x1400b6f30  jb      short loc_1400B6F11
0x1400b6f32  lea     rcx, [rbx+70h]; Event
0x1400b6f36  xor     r8d, r8d; State
0x1400b6f39  xor     edx, edx; Type
0x1400b6f3b  call    cs:__imp_KeInitializeEvent
0x1400b6f42  nop     dword ptr [rax+rax+00h]
0x1400b6f47  xor     eax, eax
0x1400b6f49  jmp     short loc_1400B6F50
0x1400b6f4b  mov     eax, 0C0000095h
0x1400b6f50  add     rsp, 38h
0x1400b6f54  pop     r14
0x1400b6f56  pop     rdi
0x1400b6f57  pop     rsi
0x1400b6f58  pop     rbx
0x1400b6f59  retn
```
