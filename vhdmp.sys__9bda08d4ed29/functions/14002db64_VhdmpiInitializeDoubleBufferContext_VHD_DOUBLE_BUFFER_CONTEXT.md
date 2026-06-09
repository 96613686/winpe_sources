# VhdmpiInitializeDoubleBufferContext(_VHD_DOUBLE_BUFFER_CONTEXT *)

- ea: `0x14002db64`
- end: `0x14002dc4f`
- name: `?VhdmpiInitializeDoubleBufferContext@@YAJPEAU_VHD_DOUBLE_BUFFER_CONTEXT@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct _VHD_DOUBLE_BUFFER_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140032200`

## callees

- `0x14002dacc`
- `0x14002db64`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14002dbbc`
- `ntoskrnl!IoAllocateMdl` at `0x14002dbbc`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002dbd4`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002dbd4`
- `ntoskrnl!MmSizeOfMdl` at `0x14002dbe8`
- `ntoskrnl!MmSizeOfMdl` at `0x14002dbe8`
- `ntoskrnl!MmAllocateMappingAddress` at `0x14002dc1f`
- `ntoskrnl!MmAllocateMappingAddress` at `0x14002dc1f`
- `ntoskrnl!ExAllocatePool2` at `0x14002db8f`
- `ntoskrnl!ExAllocatePool2` at `0x14002dc00`
- `ntoskrnl!ExAllocatePool2` at `0x14002db8f`
- `ntoskrnl!ExAllocatePool2` at `0x14002dc00`

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
0x14002db64  mov     [rsp+arg_0], rbx
0x14002db69  push    rdi
0x14002db6a  sub     rsp, 30h
0x14002db6e  xorps   xmm0, xmm0
0x14002db71  mov     rdi, rcx
0x14002db74  movups  xmmword ptr [rcx], xmm0
0x14002db77  mov     edx, 1000h
0x14002db7c  mov     r8d, 55444856h
0x14002db82  movups  xmmword ptr [rcx+10h], xmm0
0x14002db86  movups  xmmword ptr [rcx+20h], xmm0
0x14002db8a  mov     ecx, 40h ; '@'
0x14002db8f  call    cs:__imp_ExAllocatePool2
0x14002db96  nop     dword ptr [rax+rax+00h]
0x14002db9b  xor     ebx, ebx
0x14002db9d  mov     [rdi], rax
0x14002dba0  test    rax, rax
0x14002dba3  jz      loc_14002DC34
0x14002dba9  xor     r9d, r9d; ChargeQuota
0x14002dbac  mov     [rsp+38h+Irp], rbx; Irp
0x14002dbb1  xor     r8d, r8d; SecondaryBuffer
0x14002dbb4  mov     edx, 1000h; Length
0x14002dbb9  mov     rcx, rax; VirtualAddress
0x14002dbbc  call    cs:__imp_IoAllocateMdl
0x14002dbc3  nop     dword ptr [rax+rax+00h]
0x14002dbc8  mov     [rdi+8], rax
0x14002dbcc  test    rax, rax
0x14002dbcf  jz      short loc_14002DC34
0x14002dbd1  mov     rcx, rax; MemoryDescriptorList
0x14002dbd4  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14002dbdb  nop     dword ptr [rax+rax+00h]
0x14002dbe0  mov     edx, 1000h; Length
0x14002dbe5  lea     ecx, [rdx-1]; Base
0x14002dbe8  call    cs:__imp_MmSizeOfMdl
0x14002dbef  nop     dword ptr [rax+rax+00h]
0x14002dbf4  mov     r8d, 55444856h
0x14002dbfa  lea     ecx, [rbx+40h]
0x14002dbfd  mov     rdx, rax
0x14002dc00  call    cs:__imp_ExAllocatePool2
0x14002dc07  nop     dword ptr [rax+rax+00h]
0x14002dc0c  mov     [rdi+10h], rax
0x14002dc10  test    rax, rax
0x14002dc13  jz      short loc_14002DC34
0x14002dc15  mov     edx, 55444856h; PoolTag
0x14002dc1a  mov     ecx, 2000h; NumberOfBytes
0x14002dc1f  call    cs:__imp_MmAllocateMappingAddress
0x14002dc26  nop     dword ptr [rax+rax+00h]
0x14002dc2b  mov     [rdi+18h], rax
0x14002dc2f  test    rax, rax
0x14002dc32  jnz     short loc_14002DC41
0x14002dc34  mov     rcx, rdi; struct _VHD_DOUBLE_BUFFER_CONTEXT *
0x14002dc37  mov     ebx, 0C000009Ah
0x14002dc3c  call    ?VhdmpiCleanupDoubleBufferContext@@YAXPEAU_VHD_DOUBLE_BUFFER_CONTEXT@@@Z; VhdmpiCleanupDoubleBufferContext(_VHD_DOUBLE_BUFFER_CONTEXT *)
0x14002dc41  mov     eax, ebx
0x14002dc43  mov     rbx, [rsp+38h+arg_0]
0x14002dc48  add     rsp, 30h
0x14002dc4c  pop     rdi
0x14002dc4d  retn
```
