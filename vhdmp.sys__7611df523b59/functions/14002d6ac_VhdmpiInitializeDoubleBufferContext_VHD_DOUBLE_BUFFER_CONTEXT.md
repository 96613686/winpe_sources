# VhdmpiInitializeDoubleBufferContext(_VHD_DOUBLE_BUFFER_CONTEXT *)

- ea: `0x14002d6ac`
- end: `0x14002d797`
- name: `?VhdmpiInitializeDoubleBufferContext@@YAJPEAU_VHD_DOUBLE_BUFFER_CONTEXT@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct _VHD_DOUBLE_BUFFER_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140031d40`

## callees

- `0x14002d614`
- `0x14002d6ac`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14002d704`
- `ntoskrnl!IoAllocateMdl` at `0x14002d704`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002d71c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002d71c`
- `ntoskrnl!MmSizeOfMdl` at `0x14002d730`
- `ntoskrnl!MmSizeOfMdl` at `0x14002d730`
- `ntoskrnl!MmAllocateMappingAddress` at `0x14002d767`
- `ntoskrnl!MmAllocateMappingAddress` at `0x14002d767`
- `ntoskrnl!ExAllocatePool2` at `0x14002d6d7`
- `ntoskrnl!ExAllocatePool2` at `0x14002d748`
- `ntoskrnl!ExAllocatePool2` at `0x14002d6d7`
- `ntoskrnl!ExAllocatePool2` at `0x14002d748`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeDoubleBufferContext(struct _VHD_DOUBLE_BUFFER_CONTEXT *a1)
{
  void *Pool2; // rax
  unsigned int v3; // ebx
  struct _MDL *Mdl; // rax
  SIZE_T v5; // rax
  __int64 v6; // rax
  PVOID MappingAddress; // rax

  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  *((_OWORD *)a1 + 2) = 0;
  Pool2 = (void *)ExAllocatePool2(64, 4096, 1430538326);
  v3 = 0;
  *(_QWORD *)a1 = Pool2;
  if ( !Pool2 )
    goto LABEL_5;
  Mdl = IoAllocateMdl(Pool2, 0x1000u, 0, 0, 0);
  *((_QWORD *)a1 + 1) = Mdl;
  if ( !Mdl
    || (MmBuildMdlForNonPagedPool(Mdl),
        v5 = MmSizeOfMdl((PVOID)0xFFF, 0x1000u),
        v6 = ExAllocatePool2(64, v5, 1430538326),
        (*((_QWORD *)a1 + 2) = v6) == 0)
    || (MappingAddress = MmAllocateMappingAddress(0x2000u, 0x55444856u), (*((_QWORD *)a1 + 3) = MappingAddress) == 0) )
  {
LABEL_5:
    v3 = -1073741670;
    VhdmpiCleanupDoubleBufferContext(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x14002d6ac  mov     [rsp+arg_0], rbx
0x14002d6b1  push    rdi
0x14002d6b2  sub     rsp, 30h
0x14002d6b6  xorps   xmm0, xmm0
0x14002d6b9  mov     rdi, rcx
0x14002d6bc  movups  xmmword ptr [rcx], xmm0
0x14002d6bf  mov     edx, 1000h
0x14002d6c4  mov     r8d, 55444856h
0x14002d6ca  movups  xmmword ptr [rcx+10h], xmm0
0x14002d6ce  movups  xmmword ptr [rcx+20h], xmm0
0x14002d6d2  mov     ecx, 40h ; '@'
0x14002d6d7  call    cs:__imp_ExAllocatePool2
0x14002d6de  nop     dword ptr [rax+rax+00h]
0x14002d6e3  xor     ebx, ebx
0x14002d6e5  mov     [rdi], rax
0x14002d6e8  test    rax, rax
0x14002d6eb  jz      loc_14002D77C
0x14002d6f1  xor     r9d, r9d; ChargeQuota
0x14002d6f4  mov     [rsp+38h+Irp], rbx; Irp
0x14002d6f9  xor     r8d, r8d; SecondaryBuffer
0x14002d6fc  mov     edx, 1000h; Length
0x14002d701  mov     rcx, rax; VirtualAddress
0x14002d704  call    cs:__imp_IoAllocateMdl
0x14002d70b  nop     dword ptr [rax+rax+00h]
0x14002d710  mov     [rdi+8], rax
0x14002d714  test    rax, rax
0x14002d717  jz      short loc_14002D77C
0x14002d719  mov     rcx, rax; MemoryDescriptorList
0x14002d71c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14002d723  nop     dword ptr [rax+rax+00h]
0x14002d728  mov     edx, 1000h; Length
0x14002d72d  lea     ecx, [rdx-1]; Base
0x14002d730  call    cs:__imp_MmSizeOfMdl
0x14002d737  nop     dword ptr [rax+rax+00h]
0x14002d73c  mov     r8d, 55444856h
0x14002d742  lea     ecx, [rbx+40h]
0x14002d745  mov     rdx, rax
0x14002d748  call    cs:__imp_ExAllocatePool2
0x14002d74f  nop     dword ptr [rax+rax+00h]
0x14002d754  mov     [rdi+10h], rax
0x14002d758  test    rax, rax
0x14002d75b  jz      short loc_14002D77C
0x14002d75d  mov     edx, 55444856h; PoolTag
0x14002d762  mov     ecx, 2000h; NumberOfBytes
0x14002d767  call    cs:__imp_MmAllocateMappingAddress
0x14002d76e  nop     dword ptr [rax+rax+00h]
0x14002d773  mov     [rdi+18h], rax
0x14002d777  test    rax, rax
0x14002d77a  jnz     short loc_14002D789
0x14002d77c  mov     rcx, rdi; struct _VHD_DOUBLE_BUFFER_CONTEXT *
0x14002d77f  mov     ebx, 0C000009Ah
0x14002d784  call    ?VhdmpiCleanupDoubleBufferContext@@YAXPEAU_VHD_DOUBLE_BUFFER_CONTEXT@@@Z; VhdmpiCleanupDoubleBufferContext(_VHD_DOUBLE_BUFFER_CONTEXT *)
0x14002d789  mov     eax, ebx
0x14002d78b  mov     rbx, [rsp+38h+arg_0]
0x14002d790  add     rsp, 30h
0x14002d794  pop     rdi
0x14002d795  retn
```
