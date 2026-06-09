# Smb2LeaseAllocateBufferForLeaseBreakProcessing

- ea: `0x1400161fc`
- end: `0x140016361`
- name: `Smb2LeaseAllocateBufferForLeaseBreakProcessing`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140015af8`

## callees

- `0x140016180`
- `0x1400161fc`
- `0x14002f3ac`
- `0x140038980`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001623c`
- `ntoskrnl!ExAllocatePool2` at `0x14001623c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003cbbe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003cbbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cc14`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cc2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cc14`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003cc2f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400162e3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400162e3`
- `ntoskrnl!MmSizeOfMdl` at `0x14001621c`
- `ntoskrnl!MmSizeOfMdl` at `0x14001621c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001634f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001634f`
- `ntoskrnl!IoAllocateIrp` at `0x14001625b`
- `ntoskrnl!IoAllocateIrp` at `0x14001625b`

## pseudocode

```c
__int64 __fastcall Smb2LeaseAllocateBufferForLeaseBreakProcessing(__int64 a1)
{
  unsigned int v2; // ebx
  _QWORD *Pool2; // rsi
  PIRP Irp; // r14
  struct _MDL *v5; // rdi
  unsigned __int64 v6; // rbx
  __int64 result; // rax
  KIRQL v8; // bl
  bool v9; // zf

  v2 = MmSizeOfMdl((PVOID)0xFFF, 0x80u);
  Pool2 = (_QWORD *)ExAllocatePool2(66, v2 + 360, 1999786828);
  if ( Pool2 )
  {
    Irp = IoAllocateIrp(15, 0);
    if ( Irp )
    {
      v5 = (struct _MDL *)(((unsigned __int64)Pool2 + 135) & 0xFFFFFFFFFFFFFFF8uLL);
      v6 = ((unsigned __int64)&v5->Next + v2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      memset((void *)v6, 78, 0x50u);
      v6 += 80LL;
      v5->Next = 0;
      v5->MdlFlags = 0;
      v5->ByteCount = 128;
      v5->Size = 8 * (((unsigned __int16)((v6 & 0xFFF) + 4223) >> 12) + 6);
      v5->StartVa = (PVOID)(v6 & 0xFFFFFFFFFFFFF000uLL);
      v5->ByteOffset = v6 & 0xFFF;
      MmBuildMdlForNonPagedPool(v5);
      v5->MdlFlags |= 0x1000u;
      Pool2[1] = v5;
      Pool2[5] = Irp;
      Pool2[9] = 0;
      Pool2[10] = 0;
      Pool2[13] = 0;
      Pool2[14] = 0;
      Pool2[15] = 0;
LABEL_4:
      *Pool2 = 128;
      result = 0;
      Pool2[2] = 0;
      Pool2[3] = 0;
      Pool2[4] = 0;
      *((_DWORD *)Pool2 + 12) = 256;
      *((_DWORD *)Pool2 + 22) = 0;
      *(_QWORD *)(a1 + 256) = Pool2;
      return result;
    }
    ExFreePoolWithTag(Pool2, 0);
  }
  v8 = KeAcquireSpinLockRaiseToDpc(&Smb2LowMemLeaseBufferCacheSpinLock);
  Pool2 = (_QWORD *)Smb2RemoveHeadLowMemLeaseBufferList();
  if ( Pool2 )
  {
    KeReleaseSpinLock(&Smb2LowMemLeaseBufferCacheSpinLock, v8);
    goto LABEL_4;
  }
  Smb2ReferenceLease(a1);
  v9 = Smb2LowMemLeaseBufferWaiterListHead == 0;
  *(_QWORD *)(a1 + 256) = 0;
  if ( v9 )
    Smb2LowMemLeaseBufferWaiterListHead = a1;
  else
    *(_QWORD *)(Smb2LowMemLeaseBufferWaiterListTail + 256) = a1;
  Smb2LowMemLeaseBufferWaiterListTail = a1;
  KeReleaseSpinLock(&Smb2LowMemLeaseBufferCacheSpinLock, v8);
  return 259;
}

```

## disassembly

```asm
0x1400161fc  push    rbx
0x1400161fe  push    rbp
0x1400161ff  push    rsi
0x140016200  push    rdi
0x140016201  push    r13
0x140016203  push    r14
0x140016205  push    r15
0x140016207  sub     rsp, 20h
0x14001620b  mov     rbp, rcx
0x14001620e  mov     r13d, 0FFFh
0x140016214  mov     ecx, r13d; Base
0x140016217  mov     edx, 80h; Length
0x14001621c  call    cs:__imp_MmSizeOfMdl
0x140016223  nop     dword ptr [rax+rax+00h]
0x140016228  mov     ecx, 42h ; 'B'
0x14001622d  mov     r8d, 7732534Ch
0x140016233  mov     rbx, rax
0x140016236  lea     edx, [rax+168h]
0x14001623c  call    cs:__imp_ExAllocatePool2
0x140016243  nop     dword ptr [rax+rax+00h]
0x140016248  xor     r15d, r15d
0x14001624b  mov     rsi, rax
0x14001624e  test    rax, rax
0x140016251  jz      loc_14003CBB4
0x140016257  xor     edx, edx; ChargeQuota
0x140016259  mov     cl, 0Fh; StackSize
0x14001625b  call    cs:__imp_IoAllocateIrp
0x140016262  nop     dword ptr [rax+rax+00h]
0x140016267  mov     r14, rax
0x14001626a  test    rax, rax
0x14001626d  jz      loc_14001634A
0x140016273  mov     ebx, ebx
0x140016275  lea     rdi, [rsi+87h]
0x14001627c  add     rbx, 7
0x140016280  lea     edx, [r15+4Eh]; Val
0x140016284  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140016288  lea     r8d, [r15+50h]; Size
0x14001628c  add     rbx, rdi
0x14001628f  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140016293  mov     rcx, rbx; void *
0x140016296  call    memset
0x14001629b  add     rbx, 50h ; 'P'
0x14001629f  mov     [rdi], r15
0x1400162a2  movzx   eax, bx
0x1400162a5  mov     [rdi+0Ah], r15w
0x1400162aa  and     ax, r13w
0x1400162ae  mov     dword ptr [rdi+28h], 80h
0x1400162b5  mov     ecx, 107Fh
0x1400162ba  add     ax, cx
0x1400162bd  mov     rcx, rdi; MemoryDescriptorList
0x1400162c0  shr     ax, 0Ch
0x1400162c4  add     ax, 6
0x1400162c8  shl     ax, 3
0x1400162cc  mov     [rdi+8], ax
0x1400162d0  mov     rax, rbx
0x1400162d3  and     rax, 0FFFFFFFFFFFFF000h
0x1400162d9  and     ebx, r13d
0x1400162dc  mov     [rdi+20h], rax
0x1400162e0  mov     [rdi+2Ch], ebx
0x1400162e3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400162ea  nop     dword ptr [rax+rax+00h]
0x1400162ef  lea     eax, [r13+1]
0x1400162f3  or      [rdi+0Ah], ax
0x1400162f7  mov     [rsi+8], rdi
0x1400162fb  mov     [rsi+28h], r14
0x1400162ff  mov     [rsi+48h], r15
0x140016303  mov     [rsi+50h], r15
0x140016307  mov     [rsi+68h], r15
0x14001630b  mov     [rsi+70h], r15
0x14001630f  mov     [rsi+78h], r15
0x140016313  mov     qword ptr [rsi], 80h
0x14001631a  xor     eax, eax
0x14001631c  mov     [rsi+10h], r15
0x140016320  mov     [rsi+18h], r15
0x140016324  mov     [rsi+20h], r15
0x140016328  mov     dword ptr [rsi+30h], 100h
0x14001632f  mov     [rsi+58h], r15d
0x140016333  mov     [rbp+100h], rsi
0x14001633a  add     rsp, 20h
0x14001633e  pop     r15
0x140016340  pop     r14
0x140016342  pop     r13
0x140016344  pop     rdi
0x140016345  pop     rsi
0x140016346  pop     rbp
0x140016347  pop     rbx
0x140016348  retn
0x14001634a  xor     edx, edx; Tag
0x14001634c  mov     rcx, rsi; P
0x14001634f  call    cs:__imp_ExFreePoolWithTag
0x140016356  nop     dword ptr [rax+rax+00h]
0x14001635b  nop
0x14001635c  jmp     loc_14003CBB4
0x14003cbb4  lea     rdi, Smb2LowMemLeaseBufferCacheSpinLock
0x14003cbbb  mov     rcx, rdi; SpinLock
0x14003cbbe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003cbc5  nop     dword ptr [rax+rax+00h]
0x14003cbca  mov     bl, al
0x14003cbcc  call    Smb2RemoveHeadLowMemLeaseBufferList
0x14003cbd1  mov     rsi, rax
0x14003cbd4  test    rax, rax
0x14003cbd7  jnz     short loc_14003CC2A
0x14003cbd9  mov     rcx, rbp
0x14003cbdc  call    Smb2ReferenceLease
0x14003cbe1  cmp     cs:Smb2LowMemLeaseBufferWaiterListHead, r15
0x14003cbe8  mov     [rbp+100h], r15
0x14003cbef  jnz     short loc_14003CBFA
0x14003cbf1  mov     cs:Smb2LowMemLeaseBufferWaiterListHead, rbp
0x14003cbf8  jmp     short loc_14003CC08
0x14003cbfa  mov     rax, cs:Smb2LowMemLeaseBufferWaiterListTail
0x14003cc01  mov     [rax+100h], rbp
0x14003cc08  mov     dl, bl; NewIrql
0x14003cc0a  mov     cs:Smb2LowMemLeaseBufferWaiterListTail, rbp
0x14003cc11  mov     rcx, rdi; SpinLock
0x14003cc14  call    cs:__imp_KeReleaseSpinLock
0x14003cc1b  nop     dword ptr [rax+rax+00h]
0x14003cc20  mov     eax, 103h
0x14003cc25  jmp     loc_14001633A
0x14003cc2a  mov     dl, bl; NewIrql
0x14003cc2c  mov     rcx, rdi; SpinLock
0x14003cc2f  call    cs:__imp_KeReleaseSpinLock
0x14003cc36  nop     dword ptr [rax+rax+00h]
0x14003cc3b  nop
0x14003cc3c  jmp     loc_140016313
```
