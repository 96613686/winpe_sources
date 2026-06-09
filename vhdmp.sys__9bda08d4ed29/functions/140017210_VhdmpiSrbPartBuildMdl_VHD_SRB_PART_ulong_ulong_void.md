# VhdmpiSrbPartBuildMdl(VHD_SRB_PART *,ulong,ulong,void * *)

- ea: `0x140017210`
- end: `0x140017305`
- name: `?VhdmpiSrbPartBuildMdl@@YAPEAU_MDL@@PEAUVHD_SRB_PART@@KKPEAPEAX@Z`
- size: `245`
- prototype: `struct _MDL *__fastcall(struct VHD_SRB_PART *, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001730c`

## callees

- `0x140017210`
- `0x140017428`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400172d4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400172d4`
- `ntoskrnl!IoAllocateMdl` at `0x140017271`
- `ntoskrnl!IoAllocateMdl` at `0x140017271`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400172a1`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400172a1`

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
0x140017210  push    rbx
0x140017212  push    rbp
0x140017213  push    rsi
0x140017214  push    rdi
0x140017215  push    r14
0x140017217  push    r15
0x140017219  sub     rsp, 38h
0x14001721d  mov     r10, [rcx]
0x140017220  mov     ebp, r8d
0x140017223  mov     r14, r9
0x140017226  mov     r8d, edx
0x140017229  mov     rsi, rcx
0x14001722c  mov     rax, [r10+20h]
0x140017230  mov     rdi, [r10+48h]
0x140017234  cmp     [rcx+58h], rax
0x140017238  jnz     short loc_140017248
0x14001723a  test    edx, edx
0x14001723c  jnz     short loc_140017248
0x14001723e  cmp     ebp, [r10+34h]
0x140017242  jz      loc_1400172ED
0x140017248  mov     r15d, [rcx+58h]
0x14001724c  xor     r9d, r9d; ChargeQuota
0x14001724f  sub     r15d, [r10+20h]
0x140017253  mov     edx, ebp; Length
0x140017255  mov     eax, [rdi+2Ch]
0x140017258  add     r15, rax
0x14001725b  mov     [rsp+68h+Irp], 0; Irp
0x140017264  add     r15, [rdi+20h]
0x140017268  add     r15, r8
0x14001726b  xor     r8d, r8d; SecondaryBuffer
0x14001726e  mov     rcx, r15; VirtualAddress
0x140017271  call    cs:__imp_IoAllocateMdl
0x140017278  nop     dword ptr [rax+rax+00h]
0x14001727d  mov     rbx, rax
0x140017280  test    rax, rax
0x140017283  jnz     short loc_140017295
0x140017285  xor     eax, eax
0x140017287  add     rsp, 38h
0x14001728b  pop     r15
0x14001728d  pop     r14
0x14001728f  pop     rdi
0x140017290  pop     rsi
0x140017291  pop     rbp
0x140017292  pop     rbx
0x140017293  retn
0x140017295  mov     r9d, ebp; Length
0x140017298  mov     r8, r15; VirtualAddress
0x14001729b  mov     rdx, rax; TargetMdl
0x14001729e  mov     rcx, rdi; SourceMdl
0x1400172a1  call    cs:__imp_IoBuildPartialMdl
0x1400172a8  nop     dword ptr [rax+rax+00h]
0x1400172ad  test    r14, r14
0x1400172b0  jz      short loc_1400172E8
0x1400172b2  test    byte ptr [rbx+0Ah], 5
0x1400172b6  jnz     short loc_1400172F2
0x1400172b8  xor     r9d, r9d; RequestedAddress
0x1400172bb  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400172c3  xor     edx, edx; AccessMode
0x1400172c5  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x1400172cd  mov     rcx, rbx; MemoryDescriptorList
0x1400172d0  lea     r8d, [r9+1]; CacheType
0x1400172d4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400172db  nop     dword ptr [rax+rax+00h]
0x1400172e0  mov     [r14], rax
0x1400172e3  test    rax, rax
0x1400172e6  jz      short loc_1400172F8
0x1400172e8  mov     rax, rbx
0x1400172eb  jmp     short loc_140017287
0x1400172ed  mov     rbx, rdi
0x1400172f0  jmp     short loc_1400172AD
0x1400172f2  mov     rax, [rbx+18h]
0x1400172f6  jmp     short loc_1400172E0
0x1400172f8  mov     rdx, rbx; struct _MDL *
0x1400172fb  mov     rcx, rsi; struct VHD_SRB_PART *
0x1400172fe  call    ?VhdmpiSrbPartFreeMdl@@YAXPEAUVHD_SRB_PART@@PEAU_MDL@@@Z; VhdmpiSrbPartFreeMdl(VHD_SRB_PART *,_MDL *)
0x140017303  jmp     short loc_140017285
```
