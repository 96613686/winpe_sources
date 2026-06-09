# CTsUrbResultControlDescriptor::Initialize(uchar *,ulong,ulong,CSimpleHash *,CSimpleHash *,CSimpleHash *,_MDL *)

- ea: `0x140004fb0`
- end: `0x1400050ae`
- name: `?Initialize@CTsUrbResultControlDescriptor@@EEAAJPEAEKKPEAVCSimpleHash@@11PEAU_MDL@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(CTsUrbResultControlDescriptor *this, unsigned __int8 *, int, unsigned int, struct CSimpleHash *, struct CSimpleHash *, struct CSimpleHash *, PMDL MemoryDescriptorList)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000491c`
- `0x140004fb0`
- `0x140006440`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000503a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000503a`

## pseudocode

```c
__int64 __fastcall CTsUrbResultControlDescriptor::Initialize(
        CTsUrbResultControlDescriptor *this,
        unsigned __int8 *a2,
        int a3,
        unsigned int a4,
        struct CSimpleHash *a5,
        struct CSimpleHash *a6,
        struct CSimpleHash *a7,
        PMDL MemoryDescriptorList)
{
  __int64 result; // rax
  struct _URB *Urb; // rdi
  PVOID MappedSystemVa; // rbp

  if ( !MemoryDescriptorList || a3 != 12 || *(_WORD *)a2 != 12 || a4 < 8 )
    return 3221225485LL;
  Urb = CTsUrbResult::AllocateUrb(this, 0x88u);
  if ( !Urb )
    return 3221225495LL;
  if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
    MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
  memset(&Urb->UrbSelectInterface.Hdr.Function, 0, 0x86u);
  Urb->UrbHeader.Length = 136;
  Urb->UrbHeader.Function = *((_WORD *)a2 + 1);
  Urb->UrbControlTransfer.SetupPacket[2] = a2[8];
  Urb->UrbControlTransfer.SetupPacket[3] = a2[9];
  Urb->UrbControlDescriptorRequest.LanguageId = *((_WORD *)a2 + 5);
  Urb->UrbControlTransfer.TransferBufferLength = MemoryDescriptorList->ByteCount;
  result = 0;
  Urb->UrbSelectInterface.Interface.InterfaceHandle = MappedSystemVa;
  *((_QWORD *)this + 214) = MemoryDescriptorList;
  *((_WORD *)this + 853) = 8;
  return result;
}

```

## disassembly

```asm
0x140004fb0  push    rbx
0x140004fb2  push    rbp
0x140004fb3  push    rsi
0x140004fb4  push    rdi
0x140004fb5  push    r12
0x140004fb7  push    r14
0x140004fb9  push    r15
0x140004fbb  sub     rsp, 30h
0x140004fbf  mov     rbx, [rsp+68h+MemoryDescriptorList]
0x140004fc7  mov     rsi, rdx
0x140004fca  mov     r14, rcx
0x140004fcd  test    rbx, rbx
0x140004fd0  jnz     short loc_140004FDC
0x140004fd2  mov     eax, 0C000000Dh
0x140004fd7  jmp     loc_14000509E
0x140004fdc  mov     eax, 0Ch
0x140004fe1  cmp     r8d, eax
0x140004fe4  jnz     short loc_140004FD2
0x140004fe6  cmp     [rdx], ax
0x140004fe9  jnz     short loc_140004FD2
0x140004feb  lea     r15d, [rax-4]
0x140004fef  cmp     r9d, r15d
0x140004ff2  jb      short loc_140004FD2
0x140004ff4  lea     r12d, [rax+7Ch]
0x140004ff8  mov     edx, r12d; unsigned int
0x140004ffb  call    ?AllocateUrb@CTsUrbResult@@IEAAPEAU_URB@@K@Z; CTsUrbResult::AllocateUrb(ulong)
0x140005000  mov     rdi, rax
0x140005003  test    rax, rax
0x140005006  jnz     short loc_140005012
0x140005008  mov     eax, 0C0000017h
0x14000500d  jmp     loc_14000509E
0x140005012  test    byte ptr [rbx+0Ah], 5
0x140005016  jz      short loc_14000501E
0x140005018  mov     rbp, [rbx+18h]
0x14000501c  jmp     short loc_140005049
0x14000501e  xor     r9d, r9d; RequestedAddress
0x140005021  mov     [rsp+68h+Priority], 40000010h; Priority
0x140005029  xor     edx, edx; AccessMode
0x14000502b  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140005033  mov     rcx, rbx; MemoryDescriptorList
0x140005036  lea     r8d, [r9+1]; CacheType
0x14000503a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140005041  nop     dword ptr [rax+rax+00h]
0x140005046  mov     rbp, rax
0x140005049  lea     rcx, [rdi+2]; void *
0x14000504d  xor     edx, edx; Val
0x14000504f  mov     r8d, 86h; Size
0x140005055  call    memset
0x14000505a  mov     [rdi], r12w
0x14000505e  movzx   eax, word ptr [rsi+2]
0x140005062  mov     [rdi+2], ax
0x140005066  mov     al, [rsi+8]
0x140005069  mov     [rdi+82h], al
0x14000506f  mov     al, [rsi+9]
0x140005072  mov     [rdi+83h], al
0x140005078  movzx   eax, word ptr [rsi+0Ah]
0x14000507c  mov     [rdi+84h], ax
0x140005083  mov     eax, [rbx+28h]
0x140005086  mov     [rdi+24h], eax
0x140005089  xor     eax, eax
0x14000508b  mov     [rdi+28h], rbp
0x14000508f  mov     [r14+6B0h], rbx
0x140005096  mov     [r14+6AAh], r15w
0x14000509e  add     rsp, 30h
0x1400050a2  pop     r15
0x1400050a4  pop     r14
0x1400050a6  pop     r12
0x1400050a8  pop     rdi
0x1400050a9  pop     rsi
0x1400050aa  pop     rbp
0x1400050ab  pop     rbx
0x1400050ac  retn
```
