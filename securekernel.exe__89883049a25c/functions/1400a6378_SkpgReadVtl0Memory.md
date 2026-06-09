# SkpgReadVtl0Memory

- ea: `0x1400a6378`
- end: `0x1400a64f6`
- name: `SkpgReadVtl0Memory`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400a4df8`

## callees

- `0x140002410`
- `0x14000f0f0`
- `0x1400202b0`
- `0x140037e68`
- `0x1400a5734`
- `0x1400a589c`
- `0x1400a62d4`
- `0x1400a6378`
- `0x1400ac1b4`
- `0x1400f2fc0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkpgReadVtl0Memory(__int64 a1, __int64 a2, __int64 a3)
{
  _DWORD *v3; // rbx
  _DWORD *Pool; // rax
  unsigned __int8 CurrentIrql; // bp
  __int64 v9; // r8
  int v10; // r15d
  __int64 v11; // rdi
  unsigned int Memory; // esi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx

  v3 = 0;
  if ( SkpgExternalContext )
  {
    CurrentIrql = KeGetCurrentIrql();
    __writecr8(5u);
    SkAcquireSpinLockExclusiveAtDpcLevel(&SkpgVerificationLock);
    v11 = SkpgExternalContext;
    v10 = *(_DWORD *)(SkpgExternalContext + 244);
    *(_DWORD *)(SkpgExternalContext + 68) = 0;
    *(_OWORD *)v11 = 0;
    *(_OWORD *)(v11 + 16) = 0;
    *(_QWORD *)(v11 + 32) = 0;
    *(_DWORD *)(v11 + 452) = HIDWORD(KeGetPcr()->NtTib.ExceptionList[12].Next);
  }
  else
  {
    Pool = (_DWORD *)SkAllocatePool(512, 0x3B0u);
    v3 = Pool;
    if ( !Pool )
      return 3221225626LL;
    memset_0(Pool, 0, 0x3B0u);
    v3[61] |= 0x80000u;
    v3[22] = 888;
    v3[23] = 2;
    v3[25] = 920;
    v3[26] = 1;
    CurrentIrql = KeGetCurrentIrql();
    __writecr8(5u);
    SkAcquireSpinLockExclusiveAtDpcLevel(&SkpgVerificationLock);
    v10 = 0;
    v11 = (__int64)v3;
  }
  *(_DWORD *)(v11 + 244) |= 0x40000u;
  Memory = SkpgReadMemory(v11, a1, v9, a3);
  SkpgFlushMappings(v11);
  v14 = *(unsigned int *)(v11 + 244);
  if ( (v14 & 2) != 0 )
    SkpgReleaseTbFlushLock(v11);
  if ( !v3 )
  {
    *(_DWORD *)(v11 + 244) ^= (v10 ^ *(_DWORD *)(v11 + 244)) & 0x40000;
    SkpgExternalVerificationEnd(v11, 0);
  }
  SkpgVerificationLock = 0;
  SkTrackSpinLockRelease(v14, v13);
  LOBYTE(v15) = CurrentIrql;
  SkeLowerIrql(v15);
  if ( v3 )
    SkFreePool(512, v3);
  return Memory;
}

```

## disassembly

```asm
0x1400a6378  push    rbx
0x1400a637a  push    rbp
0x1400a637b  push    rsi
0x1400a637c  push    rdi
0x1400a637d  push    r14
0x1400a637f  push    r15
0x1400a6381  sub     rsp, 28h
0x1400a6385  xor     ebx, ebx
0x1400a6387  mov     rsi, r8
0x1400a638a  cmp     cs:SkpgExternalContext, rbx
0x1400a6391  mov     r14, rcx
0x1400a6394  jnz     short loc_1400A6411
0x1400a6396  mov     edi, 3B0h
0x1400a639b  mov     r8d, 56526750h
0x1400a63a1  mov     edx, edi
0x1400a63a3  mov     ecx, 200h
0x1400a63a8  call    SkAllocatePool
0x1400a63ad  mov     rbx, rax
0x1400a63b0  test    rax, rax
0x1400a63b3  jnz     short loc_1400A63BF
0x1400a63b5  mov     eax, 0C000009Ah
0x1400a63ba  jmp     loc_1400A64E8
0x1400a63bf  mov     r8, rdi; Size
0x1400a63c2  xor     edx, edx; Val
0x1400a63c4  mov     rcx, rbx; void *
0x1400a63c7  call    memset_0
0x1400a63cc  bts     dword ptr [rbx+0F4h], 13h
0x1400a63d4  mov     dword ptr [rbx+58h], 378h
0x1400a63db  mov     dword ptr [rbx+5Ch], 2
0x1400a63e2  mov     dword ptr [rbx+64h], 398h
0x1400a63e9  mov     dword ptr [rbx+68h], 1
0x1400a63f0  mov     rbp, cr8
0x1400a63f4  mov     ecx, 5
0x1400a63f9  mov     cr8, rcx
0x1400a63fd  lea     rcx, SkpgVerificationLock
0x1400a6404  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x1400a6409  xor     r15d, r15d
0x1400a640c  mov     rdi, rbx
0x1400a640f  jmp     short loc_1400A6460
0x1400a6411  mov     rbp, cr8
0x1400a6415  mov     ecx, 5
0x1400a641a  mov     cr8, rcx
0x1400a641e  lea     rcx, SkpgVerificationLock
0x1400a6425  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x1400a642a  mov     rdi, cs:SkpgExternalContext
0x1400a6431  xorps   xmm0, xmm0
0x1400a6434  xor     eax, eax
0x1400a6436  mov     r15d, [rdi+0F4h]
0x1400a643d  mov     [rdi+44h], ebx
0x1400a6440  movups  xmmword ptr [rdi], xmm0
0x1400a6443  movups  xmmword ptr [rdi+10h], xmm0
0x1400a6447  mov     [rdi+20h], rax
0x1400a644b  mov     rax, gs:0
0x1400a6454  mov     ecx, [rax+0C4h]
0x1400a645a  mov     [rdi+1C4h], ecx
0x1400a6460  bts     dword ptr [rdi+0F4h], 12h
0x1400a6468  mov     r9, rsi
0x1400a646b  mov     rdx, r14
0x1400a646e  mov     rcx, rdi
0x1400a6471  call    SkpgReadMemory
0x1400a6476  mov     rcx, rdi
0x1400a6479  mov     esi, eax
0x1400a647b  call    SkpgFlushMappings
0x1400a6480  mov     ecx, [rdi+0F4h]
0x1400a6486  test    cl, 2
0x1400a6489  jz      short loc_1400A6493
0x1400a648b  mov     rcx, rdi
0x1400a648e  call    SkpgReleaseTbFlushLock
0x1400a6493  test    rbx, rbx
0x1400a6496  jnz     short loc_1400A64BD
0x1400a6498  mov     r8d, [rdi+0F4h]
0x1400a649f  xor     edx, edx
0x1400a64a1  mov     eax, r8d
0x1400a64a4  mov     rcx, rdi
0x1400a64a7  xor     eax, r15d
0x1400a64aa  and     eax, 40000h
0x1400a64af  xor     eax, r8d
0x1400a64b2  mov     [rdi+0F4h], eax
0x1400a64b8  call    SkpgExternalVerificationEnd
0x1400a64bd  mov     cs:SkpgVerificationLock, 0
0x1400a64c7  call    SkTrackSpinLockRelease
0x1400a64cc  mov     cl, bpl
0x1400a64cf  call    SkeLowerIrql
0x1400a64d4  test    rbx, rbx
0x1400a64d7  jz      short loc_1400A64E6
0x1400a64d9  mov     rdx, rbx
0x1400a64dc  mov     ecx, 200h
0x1400a64e1  call    SkFreePool
0x1400a64e6  mov     eax, esi
0x1400a64e8  add     rsp, 28h
0x1400a64ec  pop     r15
0x1400a64ee  pop     r14
0x1400a64f0  pop     rdi
0x1400a64f1  pop     rsi
0x1400a64f2  pop     rbp
0x1400a64f3  pop     rbx
0x1400a64f4  retn
```
