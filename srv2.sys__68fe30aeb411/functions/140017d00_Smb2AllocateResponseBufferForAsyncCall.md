# Smb2AllocateResponseBufferForAsyncCall

- ea: `0x140017d00`
- end: `0x140017edf`
- name: `Smb2AllocateResponseBufferForAsyncCall`
- size: `479`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140007090`
- `0x14001f050`
- `0x14001ffec`
- `0x140059008`
- `0x140070518`
- `0x1400828f0`
- `0x140086110`
- `0x140086de0`

## callees

- `0x140017d00`
- `0x140038980`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140017d48`
- `ntoskrnl!ExAllocatePool2` at `0x140017d48`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140017e12`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140017e12`
- `ntoskrnl!MmSizeOfMdl` at `0x140017d20`
- `ntoskrnl!MmSizeOfMdl` at `0x140017d20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017ec6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017ec6`
- `ntoskrnl!IoAllocateIrp` at `0x140017d6e`
- `ntoskrnl!IoAllocateIrp` at `0x140017d6e`

## pseudocode

```c
__int64 __fastcall Smb2AllocateResponseBufferForAsyncCall(PVOID *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // eax
  unsigned int v8; // r15d
  unsigned int v9; // r12d
  __int64 Pool2; // rax
  PIRP Irp; // r14
  struct _MDL *v12; // rsi
  unsigned __int64 v13; // rdi
  __int64 v14; // r8
  __int64 result; // rax

  v7 = MmSizeOfMdl((PVOID)0xFFF, a2);
  v8 = v7 + a2 + 208;
  v9 = v7;
  Pool2 = ExAllocatePool2(66, v8 + 24, 1999786828);
  *a1 = (PVOID)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  Irp = IoAllocateIrp(15, 0);
  if ( Irp )
  {
    v12 = (struct _MDL *)(((unsigned __int64)*a1 + 135) & 0xFFFFFFFFFFFFFFF8uLL);
    memset((void *)(((unsigned __int64)&v12->Next + v9 + 7) & 0xFFFFFFFFFFFFFFF8uLL), 78, 0x50u);
    v13 = (((unsigned __int64)&v12->Next + v9 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 80;
    v12->StartVa = (PVOID)(v13 & 0xFFFFFFFFFFFFF000uLL);
    v12->ByteOffset = v13 & 0xFFF;
    v14 = v8 - v9 - 208;
    v12->Next = 0;
    v12->MdlFlags = 0;
    v12->Size = 8 * (((v14 + (v13 & 0xFFF) + 4095) >> 12) + 6);
    v12->ByteCount = v14;
    MmBuildMdlForNonPagedPool(v12);
    v12->MdlFlags |= 0x1000u;
    *(_DWORD *)*a1 = a2;
    *((_QWORD *)*a1 + 1) = v12;
    *((_QWORD *)*a1 + 2) = 0;
    *((_QWORD *)*a1 + 3) = 0;
    *((_QWORD *)*a1 + 4) = 0;
    *((_DWORD *)*a1 + 1) = 0;
    *((_QWORD *)*a1 + 5) = Irp;
    *((_DWORD *)*a1 + 12) = 256;
    *((_QWORD *)*a1 + 9) = a3;
    *((_QWORD *)*a1 + 10) = a4;
    *((_DWORD *)*a1 + 22) = 0;
    *((_QWORD *)*a1 + 13) = 0;
    *((_QWORD *)*a1 + 14) = 0;
    *((_QWORD *)*a1 + 15) = 0;
    return 0;
  }
  else
  {
    ExFreePoolWithTag(*a1, 0);
    result = 3221225626LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140017d00  mov     [rsp+arg_10], r8
0x140017d05  push    rbx
0x140017d06  push    rbp
0x140017d07  push    r12
0x140017d09  push    r13
0x140017d0b  push    r15
0x140017d0d  sub     rsp, 20h
0x140017d11  mov     ebp, edx
0x140017d13  mov     rbx, rcx
0x140017d16  mov     edx, edx; Length
0x140017d18  mov     ecx, 0FFFh; Base
0x140017d1d  mov     r13, r9
0x140017d20  call    cs:__imp_MmSizeOfMdl
0x140017d27  nop     dword ptr [rax+rax+00h]
0x140017d2c  lea     r15d, [rbp+0D0h]
0x140017d33  mov     ecx, 42h ; 'B'
0x140017d38  add     r15d, eax
0x140017d3b  mov     r8d, 7732534Ch
0x140017d41  mov     r12, rax
0x140017d44  lea     edx, [r15+18h]
0x140017d48  call    cs:__imp_ExAllocatePool2
0x140017d4f  nop     dword ptr [rax+rax+00h]
0x140017d54  mov     [rbx], rax
0x140017d57  test    rax, rax
0x140017d5a  jz      loc_140017EAE
0x140017d60  mov     [rsp+48h+arg_0], rsi
0x140017d65  xor     edx, edx; ChargeQuota
0x140017d67  mov     cl, 0Fh; StackSize
0x140017d69  mov     [rsp+48h+arg_18], r14
0x140017d6e  call    cs:__imp_IoAllocateIrp
0x140017d75  nop     dword ptr [rax+rax+00h]
0x140017d7a  mov     rsi, [rbx]
0x140017d7d  mov     r14, rax
0x140017d80  test    rax, rax
0x140017d83  jz      loc_140017EC1
0x140017d89  mov     [rsp+48h+arg_8], rdi
0x140017d8e  add     rsi, 87h
0x140017d95  mov     eax, r12d
0x140017d98  and     rsi, 0FFFFFFFFFFFFFFF8h
0x140017d9c  mov     edx, 4Eh ; 'N'; Val
0x140017da1  mov     r8d, 50h ; 'P'; Size
0x140017da7  lea     rdi, [rsi+7]
0x140017dab  add     rdi, rax
0x140017dae  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140017db2  mov     rcx, rdi; void *
0x140017db5  call    memset
0x140017dba  add     rdi, 50h ; 'P'
0x140017dbe  sub     r15d, r12d
0x140017dc1  mov     edx, edi
0x140017dc3  and     rdi, 0FFFFFFFFFFFFF000h
0x140017dca  mov     ecx, edx
0x140017dcc  mov     [rsi+20h], rdi
0x140017dd0  and     ecx, 0FFFh
0x140017dd6  and     edx, 0FFFh
0x140017ddc  add     rcx, 0FFFh
0x140017de3  mov     [rsi+2Ch], edx
0x140017de6  lea     r8d, [r15-0D0h]
0x140017ded  xor     r15d, r15d
0x140017df0  add     rcx, r8
0x140017df3  mov     [rsi], r15
0x140017df6  shr     rcx, 0Ch
0x140017dfa  add     cx, 6
0x140017dfe  mov     [rsi+0Ah], r15w
0x140017e03  shl     cx, 3
0x140017e07  mov     [rsi+8], cx
0x140017e0b  mov     rcx, rsi; MemoryDescriptorList
0x140017e0e  mov     [rsi+28h], r8d
0x140017e12  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140017e19  nop     dword ptr [rax+rax+00h]
0x140017e1e  mov     rcx, [rsp+48h+arg_10]
0x140017e23  mov     eax, 1000h
0x140017e28  or      [rsi+0Ah], ax
0x140017e2c  mov     rax, [rbx]
0x140017e2f  mov     rdi, [rsp+48h+arg_8]
0x140017e34  mov     [rax], ebp
0x140017e36  mov     rax, [rbx]
0x140017e39  mov     [rax+8], rsi
0x140017e3d  mov     rax, [rbx]
0x140017e40  mov     [rax+10h], r15
0x140017e44  mov     rax, [rbx]
0x140017e47  mov     [rax+18h], r15
0x140017e4b  mov     rax, [rbx]
0x140017e4e  mov     [rax+20h], r15
0x140017e52  mov     rax, [rbx]
0x140017e55  mov     [rax+4], r15d
0x140017e59  mov     rax, [rbx]
0x140017e5c  mov     [rax+28h], r14
0x140017e60  mov     rax, [rbx]
0x140017e63  mov     dword ptr [rax+30h], 100h
0x140017e6a  mov     rax, [rbx]
0x140017e6d  mov     [rax+48h], rcx
0x140017e71  mov     rax, [rbx]
0x140017e74  mov     [rax+50h], r13
0x140017e78  mov     rax, [rbx]
0x140017e7b  mov     [rax+58h], r15d
0x140017e7f  mov     rax, [rbx]
0x140017e82  mov     [rax+68h], r15
0x140017e86  mov     rax, [rbx]
0x140017e89  mov     [rax+70h], r15
0x140017e8d  mov     rax, [rbx]
0x140017e90  mov     [rax+78h], r15
0x140017e94  xor     eax, eax
0x140017e96  mov     rsi, [rsp+48h+arg_0]
0x140017e9b  mov     r14, [rsp+48h+arg_18]
0x140017ea0  add     rsp, 20h
0x140017ea4  pop     r15
0x140017ea6  pop     r13
0x140017ea8  pop     r12
0x140017eaa  pop     rbp
0x140017eab  pop     rbx
0x140017eac  retn
0x140017eae  mov     eax, 0C000009Ah
0x140017eb3  add     rsp, 20h
0x140017eb7  pop     r15
0x140017eb9  pop     r13
0x140017ebb  pop     r12
0x140017ebd  pop     rbp
0x140017ebe  pop     rbx
0x140017ebf  retn
0x140017ec1  xor     edx, edx; Tag
0x140017ec3  mov     rcx, rsi; P
0x140017ec6  call    cs:__imp_ExFreePoolWithTag
0x140017ecd  nop     dword ptr [rax+rax+00h]
0x140017ed2  xor     r15d, r15d
0x140017ed5  mov     eax, 0C000009Ah
0x140017eda  mov     [rbx], r15
0x140017edd  jmp     short loc_140017E96
```
