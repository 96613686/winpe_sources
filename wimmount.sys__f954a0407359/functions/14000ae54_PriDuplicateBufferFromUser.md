# PriDuplicateBufferFromUser

- ea: `0x14000ae54`
- end: `0x14000aed9`
- name: `PriDuplicateBufferFromUser`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b110`
- `0x14000b4b8`
- `0x14000b6b4`

## callees

- `0x140001044`
- `0x14000ae54`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ae83`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ae83`

## pseudocode

```c
__int64 __fastcall PriDuplicateBufferFromUser(_QWORD *a1, void *a2, unsigned int a3)
{
  unsigned int v5; // edi
  size_t v6; // r14
  PVOID PoolWithTag; // rax
  PVOID v8; // rbx

  v5 = 0;
  v6 = a3;
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, a3, 0x574D6365u);
  v8 = PoolWithTag;
  if ( PoolWithTag )
  {
    RtlCopyFromUser(PoolWithTag, a2, v6);
    *a1 = v8;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v5;
}

```

## disassembly

```asm
0x14000ae54  mov     [rsp+arg_8], rbx
0x14000ae59  mov     [rsp+arg_10], rsi
0x14000ae5e  mov     [rsp+arg_0], rcx
0x14000ae63  push    rdi
0x14000ae64  push    r14
0x14000ae66  push    r15
0x14000ae68  sub     rsp, 20h
0x14000ae6c  mov     r15, rdx
0x14000ae6f  mov     rsi, rcx
0x14000ae72  xor     edi, edi
0x14000ae74  mov     r14d, r8d
0x14000ae77  mov     r8d, 574D6365h; Tag
0x14000ae7d  mov     edx, r14d; NumberOfBytes
0x14000ae80  lea     ecx, [rdi+1]; PoolType
0x14000ae83  call    cs:__imp_ExAllocatePoolWithTag
0x14000ae8a  nop     dword ptr [rax+rax+00h]
0x14000ae8f  mov     rbx, rax
0x14000ae92  mov     [rsp+38h+arg_18], rax
0x14000ae97  test    rax, rax
0x14000ae9a  jnz     short loc_14000AEA3
0x14000ae9c  mov     edi, 0C000009Ah
0x14000aea1  jmp     short loc_14000AEC2
0x14000aea3  mov     r8, r14; Size
0x14000aea6  mov     rdx, r15; Src
0x14000aea9  mov     rcx, rax; void *
0x14000aeac  call    RtlCopyFromUser
0x14000aeb1  jmp     short loc_14000AEBF
0x14000aeb3  mov     edi, eax
0x14000aeb5  mov     rsi, [rsp+38h+arg_0]
0x14000aeba  mov     rbx, [rsp+38h+arg_18]
0x14000aebf  mov     [rsi], rbx
0x14000aec2  mov     eax, edi
0x14000aec4  mov     rbx, [rsp+38h+arg_8]
0x14000aec9  mov     rsi, [rsp+38h+arg_10]
0x14000aece  add     rsp, 20h
0x14000aed2  pop     r15
0x14000aed4  pop     r14
0x14000aed6  pop     rdi
0x14000aed7  retn
```
