# VsmmIoctlReadWriteMappedMemoryBlockPageRange

- ea: `0x1400d6f1c`
- end: `0x1400d711f`
- name: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400321a4`

## callees

- `0x1400248f4`
- `0x1400309d0`
- `0x140033b00`
- `0x1400386a0`
- `0x1400d6f1c`
- `0x1400f21a0`
- `0x1400fc5e0`
- `0x1400fd300`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400d6f8a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400d6f8a`

## string_xrefs

- `0x1400d6ff8`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- `0x1400d707a`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- `0x1400d7096`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- `0x1400d70bc`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`
- `0x1400d70fc`: `VsmmIoctlReadWriteMappedMemoryBlockPageRange`

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
  VidLockAcquireShared(v6);
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
    else if ( (*(_DWORD *)(*(_QWORD *)(v12 + 16) + 264LL) & 8) != 0 )
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
0x1400d6f1c  push    rbp
0x1400d6f1e  push    rbx
0x1400d6f1f  push    rsi
0x1400d6f20  push    rdi
0x1400d6f21  push    r12
0x1400d6f23  push    r13
0x1400d6f25  push    r14
0x1400d6f27  push    r15
0x1400d6f29  lea     rbp, [rsp-0Fh]
0x1400d6f2e  sub     rsp, 88h
0x1400d6f35  mov     rsi, [rcx+10A0h]
0x1400d6f3c  xorps   xmm0, xmm0
0x1400d6f3f  mov     r15, rcx
0x1400d6f42  mov     [rbp+47h+var_80], rcx
0x1400d6f46  xorps   xmm1, xmm1
0x1400d6f49  mov     rcx, rsi
0x1400d6f4c  mov     r12, r9
0x1400d6f4f  mov     r14, r8
0x1400d6f52  mov     rbx, rdx
0x1400d6f55  movups  [rbp+47h+var_68], xmm0
0x1400d6f59  movups  [rbp+47h+var_58], xmm0
0x1400d6f5d  movdqu  [rbp+47h+var_78], xmm1
0x1400d6f62  call    VidLockAcquireShared
0x1400d6f67  lea     rcx, [rsi+8]
0x1400d6f6b  mov     rdx, rbx
0x1400d6f6e  call    VidHandleTableLookupEntry
0x1400d6f73  lea     r13, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d6f7a  mov     rdi, rax
0x1400d6f7d  test    rax, rax
0x1400d6f80  jz      loc_1400D70A7
0x1400d6f86  mov     rbx, [rax+58h]
0x1400d6f8a  call    cs:__imp_PsGetCurrentProcess
0x1400d6f91  nop     dword ptr [rax+rax+00h]
0x1400d6f96  cmp     rax, rbx
0x1400d6f99  jnz     loc_1400D70A7
0x1400d6f9f  lock inc dword ptr [rdi+88h]
0x1400d6fa6  mov     rcx, rsi
0x1400d6fa9  call    VidLockRelease
0x1400d6fae  mov     eax, 0FFFFF000h
0x1400d6fb3  cmp     r14, rax
0x1400d6fb6  ja      loc_1400D708B
0x1400d6fbc  mov     r8, [rbp+47h+arg_20]
0x1400d6fc0  cmp     r8, rax
0x1400d6fc3  ja      loc_1400D708B
0x1400d6fc9  mov     rax, [rdi+20h]
0x1400d6fcd  lea     rcx, [r14+r8]
0x1400d6fd1  shl     rax, 0Ch
0x1400d6fd5  cmp     rcx, rax
0x1400d6fd8  ja      loc_1400D708B
0x1400d6fde  mov     rax, [rdi+10h]
0x1400d6fe2  mov     ecx, [rax+108h]
0x1400d6fe8  test    cl, 8
0x1400d6feb  jz      short loc_1400D700C
0x1400d6fed  mov     ebx, 0C000000Dh
0x1400d6ff2  mov     r8d, 101Ch
0x1400d6ff8  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d6fff  mov     rdx, r13
0x1400d7002  call    VidTraceErrorInternal0
0x1400d7007  jmp     loc_1400D70CB
0x1400d700c  movzx   edx, [rbp+47h+arg_28]
0x1400d7010  mov     ecx, edx
0x1400d7012  mov     qword ptr [rbp+47h+var_68], r14
0x1400d7016  and     ecx, 1
0x1400d7019  mov     qword ptr [rbp+47h+var_68+8], r12
0x1400d701d  mov     qword ptr [rbp+47h+var_58], r8
0x1400d7021  mov     byte ptr [rbp+47h+var_58+8], dl
0x1400d7024  mov     dword ptr [rbp+47h+var_58+0Ch], 0
0x1400d702b  mov     r9, [rdi+20h]
0x1400d702f  lea     eax, [rcx+rcx]
0x1400d7032  mov     r8, [rdi+18h]
0x1400d7036  or      eax, ecx
0x1400d7038  mov     rdx, [rdi+10h]
0x1400d703c  lea     rcx, [rbp+47h+var_68]
0x1400d7040  mov     [rsp+0C0h+var_88], rcx
0x1400d7045  lea     rcx, VsmmpReadWriteMappedMemoryCallback
0x1400d704c  mov     [rsp+0C0h+var_90], rcx
0x1400d7051  lea     rcx, [rbp+47h+var_80]
0x1400d7055  mov     [rsp+0C0h+var_98], 0
0x1400d705e  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1400d7062  call    VsmmMemoryBlockMbpRangeVaMap
0x1400d7067  mov     ebx, eax
0x1400d7069  test    eax, eax
0x1400d706b  js      short loc_1400D7074
0x1400d706d  mov     ebx, dword ptr [rbp+47h+var_58+0Ch]
0x1400d7070  test    ebx, ebx
0x1400d7072  jns     short loc_1400D70CB
0x1400d7074  mov     r8d, 1043h
0x1400d707a  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d7081  mov     rdx, r13
0x1400d7084  call    VidTraceErrorInternal0
0x1400d7089  jmp     short loc_1400D70CB
0x1400d708b  mov     ebx, 0C000000Dh
0x1400d7090  mov     r8d, 1015h
0x1400d7096  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d709d  mov     rdx, r13
0x1400d70a0  call    VidTraceErrorInternal0
0x1400d70a5  jmp     short loc_1400D70CB
0x1400d70a7  xor     edi, edi
0x1400d70a9  mov     rcx, rsi
0x1400d70ac  call    VidLockRelease
0x1400d70b1  mov     ebx, 0C0370018h
0x1400d70b6  mov     r8d, 1008h
0x1400d70bc  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d70c3  mov     rdx, r13
0x1400d70c6  call    VidTraceErrorInternal0
0x1400d70cb  lea     rcx, [rbp+47h+var_80]
0x1400d70cf  call    VsmmMemoryBlockMbpRangeVaDestroy
0x1400d70d4  test    rdi, rdi
0x1400d70d7  jz      short loc_1400D70E0
0x1400d70d9  lock dec dword ptr [rdi+88h]
0x1400d70e0  test    ebx, ebx
0x1400d70e2  jns     short loc_1400D7108
0x1400d70e4  lea     rax, [r15+290h]
0x1400d70eb  mov     r9d, ebx
0x1400d70ee  mov     r8d, 1050h
0x1400d70f4  mov     [rsp+0C0h+var_A0], rax
0x1400d70f9  mov     rdx, r13
0x1400d70fc  lea     rcx, aVsmmioctlreadw_0; "VsmmIoctlReadWriteMappedMemoryBlockPage"...
0x1400d7103  call    VidTraceErrorStatusPartitionInternal0
0x1400d7108  mov     eax, ebx
0x1400d710a  add     rsp, 88h
0x1400d7111  pop     r15
0x1400d7113  pop     r14
0x1400d7115  pop     r13
0x1400d7117  pop     r12
0x1400d7119  pop     rdi
0x1400d711a  pop     rsi
0x1400d711b  pop     rbx
0x1400d711c  pop     rbp
0x1400d711d  retn
```
