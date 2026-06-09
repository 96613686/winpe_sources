# VhdmpiSrbPartBuildMdl(VHD_SRB_PART *,ulong,ulong,void * *)

- ea: `0x140016d70`
- end: `0x140016e65`
- name: `?VhdmpiSrbPartBuildMdl@@YAPEAU_MDL@@PEAUVHD_SRB_PART@@KKPEAPEAX@Z`
- size: `245`
- prototype: `struct _MDL *__fastcall(struct VHD_SRB_PART *, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140016e6c`

## callees

- `0x140016d70`
- `0x140016f88`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016e34`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016e34`
- `ntoskrnl!IoAllocateMdl` at `0x140016dd1`
- `ntoskrnl!IoAllocateMdl` at `0x140016dd1`
- `ntoskrnl!IoBuildPartialMdl` at `0x140016e01`
- `ntoskrnl!IoBuildPartialMdl` at `0x140016e01`

## pseudocode

```c
struct _MDL *__fastcall VhdmpiSrbPartBuildMdl(struct VHD_SRB_PART *a1, unsigned int a2, ULONG a3, void **a4)
{
  __int64 v4; // r10
  struct _MDL *v8; // rdi
  char *v9; // r15
  struct _MDL *Mdl; // rax
  struct _MDL *v11; // rbx
  PVOID v13; // rax

  v4 = *(_QWORD *)a1;
  v8 = *(struct _MDL **)(*(_QWORD *)a1 + 72LL);
  if ( *((_QWORD *)a1 + 11) == *(_QWORD *)(*(_QWORD *)a1 + 32LL) && !a2 && a3 == *(_DWORD *)(v4 + 52) )
  {
    v11 = *(struct _MDL **)(*(_QWORD *)a1 + 72LL);
  }
  else
  {
    v9 = (char *)v8->StartVa
       + v8->ByteOffset
       + (unsigned __int64)(unsigned int)(*((_DWORD *)a1 + 22) - *(_DWORD *)(v4 + 32))
       + a2;
    Mdl = IoAllocateMdl(v9, a3, 0, 0, 0);
    v11 = Mdl;
    if ( !Mdl )
      return 0;
    IoBuildPartialMdl(v8, Mdl, v9, a3);
  }
  if ( a4 )
  {
    v13 = (v11->MdlFlags & 5) != 0
        ? v11->MappedSystemVa
        : MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000010u);
    *a4 = v13;
    if ( !v13 )
    {
      VhdmpiSrbPartFreeMdl(a1, v11);
      return 0;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x140016d70  push    rbx
0x140016d72  push    rbp
0x140016d73  push    rsi
0x140016d74  push    rdi
0x140016d75  push    r14
0x140016d77  push    r15
0x140016d79  sub     rsp, 38h
0x140016d7d  mov     r10, [rcx]
0x140016d80  mov     ebp, r8d
0x140016d83  mov     r14, r9
0x140016d86  mov     r8d, edx
0x140016d89  mov     rsi, rcx
0x140016d8c  mov     rax, [r10+20h]
0x140016d90  mov     rdi, [r10+48h]
0x140016d94  cmp     [rcx+58h], rax
0x140016d98  jnz     short loc_140016DA8
0x140016d9a  test    edx, edx
0x140016d9c  jnz     short loc_140016DA8
0x140016d9e  cmp     ebp, [r10+34h]
0x140016da2  jz      loc_140016E4D
0x140016da8  mov     r15d, [rcx+58h]
0x140016dac  xor     r9d, r9d; ChargeQuota
0x140016daf  sub     r15d, [r10+20h]
0x140016db3  mov     edx, ebp; Length
0x140016db5  mov     eax, [rdi+2Ch]
0x140016db8  add     r15, rax
0x140016dbb  mov     [rsp+68h+Irp], 0; Irp
0x140016dc4  add     r15, [rdi+20h]
0x140016dc8  add     r15, r8
0x140016dcb  xor     r8d, r8d; SecondaryBuffer
0x140016dce  mov     rcx, r15; VirtualAddress
0x140016dd1  call    cs:__imp_IoAllocateMdl
0x140016dd8  nop     dword ptr [rax+rax+00h]
0x140016ddd  mov     rbx, rax
0x140016de0  test    rax, rax
0x140016de3  jnz     short loc_140016DF5
0x140016de5  xor     eax, eax
0x140016de7  add     rsp, 38h
0x140016deb  pop     r15
0x140016ded  pop     r14
0x140016def  pop     rdi
0x140016df0  pop     rsi
0x140016df1  pop     rbp
0x140016df2  pop     rbx
0x140016df3  retn
0x140016df5  mov     r9d, ebp; Length
0x140016df8  mov     r8, r15; VirtualAddress
0x140016dfb  mov     rdx, rax; TargetMdl
0x140016dfe  mov     rcx, rdi; SourceMdl
0x140016e01  call    cs:__imp_IoBuildPartialMdl
0x140016e08  nop     dword ptr [rax+rax+00h]
0x140016e0d  test    r14, r14
0x140016e10  jz      short loc_140016E48
0x140016e12  test    byte ptr [rbx+0Ah], 5
0x140016e16  jnz     short loc_140016E52
0x140016e18  xor     r9d, r9d; RequestedAddress
0x140016e1b  mov     [rsp+68h+Priority], 40000010h; Priority
0x140016e23  xor     edx, edx; AccessMode
0x140016e25  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x140016e2d  mov     rcx, rbx; MemoryDescriptorList
0x140016e30  lea     r8d, [r9+1]; CacheType
0x140016e34  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140016e3b  nop     dword ptr [rax+rax+00h]
0x140016e40  mov     [r14], rax
0x140016e43  test    rax, rax
0x140016e46  jz      short loc_140016E58
0x140016e48  mov     rax, rbx
0x140016e4b  jmp     short loc_140016DE7
0x140016e4d  mov     rbx, rdi
0x140016e50  jmp     short loc_140016E0D
0x140016e52  mov     rax, [rbx+18h]
0x140016e56  jmp     short loc_140016E40
0x140016e58  mov     rdx, rbx; struct _MDL *
0x140016e5b  mov     rcx, rsi; struct VHD_SRB_PART *
0x140016e5e  call    ?VhdmpiSrbPartFreeMdl@@YAXPEAUVHD_SRB_PART@@PEAU_MDL@@@Z; VhdmpiSrbPartFreeMdl(VHD_SRB_PART *,_MDL *)
0x140016e63  jmp     short loc_140016DE5
```
