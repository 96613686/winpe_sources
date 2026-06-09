# SIO_RAID5::BuildChildPacketsWriteRow(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x14000a820`
- end: `0x14000ac8c`
- name: `?BuildChildPacketsWriteRow@SIO_RAID5@@QEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `1132`
- prototype: `__int64 __fastcall(SIO_RAID5 *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140009770`

## callees

- `0x140009f80`
- `0x14000a820`
- `0x14000aca0`
- `0x14000acc0`
- `0x14000b0b0`
- `0x14000b170`
- `0x140016160`
- `0x14002f858`
- `0x140068600`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000aa0c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000aa0c`
- `ntoskrnl!IoAllocateMdl` at `0x14000a9ee`
- `ntoskrnl!IoAllocateMdl` at `0x14000a9ee`
- `ntoskrnl!ExAllocatePool2` at `0x14000a879`
- `ntoskrnl!ExAllocatePool2` at `0x14000a9c1`
- `ntoskrnl!ExAllocatePool2` at `0x14000a879`
- `ntoskrnl!ExAllocatePool2` at `0x14000a9c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400690af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400690af`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ac44`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ac44`
- `ntoskrnl!MmMdlPageContentsState` at `0x14000aa1f`
- `ntoskrnl!MmMdlPageContentsState` at `0x14000aa1f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000abaf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000abaf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ab44`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ab44`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ab7a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ab7a`

## pseudocode

```c
__int64 __fastcall SIO_RAID5::BuildChildPacketsWriteRow(
        SIO_RAID5 *this,
        struct SC_PACKET *a2,
        struct SC_SEQUENTIAL *a3)
{
  char v5; // di
  unsigned __int64 v6; // r13
  int v7; // ebp
  struct SP_RESILIENCY_INFO *v8; // rax
  struct SC_PARITY_CONTEXT *Pool2; // rax
  struct SC_PARITY_CONTEXT *v10; // r14
  unsigned __int64 v11; // r13
  int v12; // edi
  unsigned int i; // r12d
  SC_PACKET *v14; // rax
  SC_PACKET *v15; // rbp
  __int64 v16; // r15
  SIO_RAID *v17; // rcx
  __int64 v18; // rdi
  unsigned int v19; // r12d
  SIO_RAID *v20; // rcx
  unsigned int v21; // r8d
  struct SP_RESILIENCY_INFO *v22; // rax
  unsigned int v23; // edx
  __int64 v24; // r15
  void *v25; // rdi
  struct _MDL *Mdl; // rax
  __int64 v27; // r15
  __int64 v29; // rax
  PVOID v30; // rax
  struct SC_PACKET **v31; // rdx
  int v32; // ecx
  unsigned int v33; // edi
  PVOID v34; // rax
  unsigned int v35; // [rsp+70h] [rbp+8h]
  int v36; // [rsp+70h] [rbp+8h]
  unsigned int v37; // [rsp+78h] [rbp+10h]
  unsigned __int64 v38; // [rsp+80h] [rbp+18h]

  if ( a3 )
    return (unsigned int)-1073741822;
  v5 = *((_BYTE *)this + 42);
  v6 = *((_QWORD *)a2 + 17);
  v7 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 384LL) + 40LL);
  v8 = SIO_RAID::Resiliency(this);
  Pool2 = (struct SC_PARITY_CONTEXT *)ExAllocatePool2(64, (unsigned int)(8 * *((_DWORD *)v8 + 4)) + 24LL, 1884844115);
  v10 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v11 = v6 >> v5;
  v12 = 0;
  SC_PARITY::InitializeContext(*(SC_PARITY **)(*((_QWORD *)this + 1) + 384LL), (1 << v7) - 1, Pool2);
  for ( i = 0; ; i = v37 + 1 )
  {
    v37 = i;
    if ( i >= *((_DWORD *)SIO_RAID::Resiliency(this) + 4) )
      break;
    v14 = (SC_PACKET *)SC_PACKET::operator new(0xF8u, *((struct SC_PACKET **)a2 + 1));
    if ( !v14 || (v15 = SC_PACKET::SC_PACKET(v14)) == 0 )
    {
      v12 = -1073741670;
      goto LABEL_18;
    }
    v16 = i;
    if ( *((_DWORD *)SIO_RAID::Provisioning(this) + 7) == 1 )
      v38 = (i + v11 * *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 1) + 384LL) + 44LL))
          % *((unsigned int *)SIO_RAID::Resiliency(v17) + 4);
    else
      LODWORD(v38) = i;
    v18 = *(_QWORD *)(*((_QWORD *)this + 1) + 384LL);
    v19 = *(_DWORD *)(v18 + 40);
    if ( *((_DWORD *)SIO_RAID::Provisioning(this) + 7) == 1 )
    {
      v22 = SIO_RAID::Resiliency(v20);
      v21 = v38;
      v23 = (v16 + v11 * *(unsigned int *)(v18 + 44)) % *((unsigned int *)v22 + 4);
    }
    else
    {
      v23 = v37;
    }
    if ( v23 >= v19 )
    {
      v24 = 1LL << *((_BYTE *)this + 42);
      v35 = 0xFFFF;
      if ( (unsigned int)(v24 - 4096) <= 0x3F000 )
      {
        _BitScanReverse((unsigned int *)&v32, v24);
        v36 = v32;
        if ( 1 << v32 != (_DWORD)v24 )
          v36 = v32 + 1;
        v33 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
        v35 = v33 * (v36 - 12) + (unsigned __int8)(KeGetCurrentProcessorNumberEx(0) % v33);
        v34 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45)
                                                                       + ((unsigned __int64)v35 << 7)));
        v25 = v34;
        if ( v34 )
        {
          memset(v34, 0, (unsigned int)v24);
          goto LABEL_14;
        }
      }
      else
      {
        v25 = (void *)ExAllocatePool2(72, (unsigned int)v24, 1715630163);
        if ( v25 )
        {
LABEL_14:
          Mdl = IoAllocateMdl(v25, v24, 0, 0, 0);
          *((_QWORD *)v15 + 15) = Mdl;
          if ( Mdl )
          {
            v12 = 0;
            MmBuildMdlForNonPagedPool(Mdl);
            MmMdlPageContentsState(*((_QWORD *)v15 + 15), 1);
            *((_WORD *)v15 + 58) = v35;
            *((_DWORD *)v15 + 28) = 3;
          }
          else
          {
            if ( v35 == 0xFFFF )
              ExFreePoolWithTag(v25, 0);
            else
              ExFreeToNPagedLookasideList(
                (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45) + ((unsigned __int64)v35 << 7)),
                v25);
            v12 = -1073741670;
          }
          goto LABEL_16;
        }
      }
      v12 = -1073741670;
LABEL_16:
      v27 = (unsigned int)v38;
      goto LABEL_17;
    }
    v27 = v21;
    v12 = SC_PACKET::Split(v15, a2, (unsigned __int64)v21 << *((_BYTE *)this + 42), 1LL << *((_BYTE *)this + 42), 1u);
LABEL_17:
    if ( v12 < 0 )
      goto LABEL_18;
    v29 = *((_QWORD *)v15 + 15);
    if ( (*(_BYTE *)(v29 + 10) & 5) != 0 )
      v30 = *(PVOID *)(v29 + 24);
    else
      v30 = MmMapLockedPagesSpecifyCache((PMDL)v29, 0, MmCached, 0, 0, 0x40000020u);
    *((_QWORD *)v10 + v27 + 2) = v30;
    *((_QWORD *)v15 + 17) = *((_QWORD *)a2 + 17);
    *((_DWORD *)v15 + 36) = 1LL << *((_BYTE *)this + 42);
    *((_DWORD *)v15 + 37) = v37;
    *((_BYTE *)v15 + 168) = 4;
    *((_BYTE *)v15 + 170) = 1;
    *((_QWORD *)v15 + 30) = this;
    *((_QWORD *)v15 + 1) = *((_QWORD *)a2 + 1);
    *((_QWORD *)v15 + 2) = a2;
    v31 = (struct SC_PACKET **)*((_QWORD *)a2 + 6);
    if ( *v31 != (struct SC_PACKET *)((char *)a2 + 40) )
      __fastfail(3u);
    *((_QWORD *)v15 + 7) = (char *)a2 + 40;
    *((_QWORD *)v15 + 8) = v31;
    *v31 = (SC_PACKET *)((char *)v15 + 56);
    *((_QWORD *)a2 + 6) = (char *)v15 + 56;
    ++*((_DWORD *)a2 + 18);
  }
  SC_PARITY::Execute(*(SC_PARITY **)(*((_QWORD *)this + 1) + 384LL), v10, 1LL << *((_BYTE *)this + 42), 0);
LABEL_18:
  ExFreePoolWithTag(v10, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000a820  mov     [rsp+arg_18], rbx
0x14000a825  push    rbp
0x14000a826  push    rsi
0x14000a827  push    rdi
0x14000a828  push    r12
0x14000a82a  push    r13
0x14000a82c  push    r14
0x14000a82e  push    r15
0x14000a830  sub     rsp, 30h
0x14000a834  mov     rsi, rdx
0x14000a837  mov     rbx, rcx
0x14000a83a  test    r8, r8
0x14000a83d  jnz     loc_14000ABD4
0x14000a843  mov     rax, [rcx+8]
0x14000a847  movzx   edi, byte ptr [rbx+2Ah]
0x14000a84b  mov     r13, [rdx+88h]
0x14000a852  mov     rcx, [rax+180h]
0x14000a859  mov     ebp, [rcx+28h]
0x14000a85c  mov     rcx, rbx; this
0x14000a85f  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14000a864  mov     ecx, 40h ; '@'
0x14000a869  mov     r8d, 70587053h
0x14000a86f  mov     edx, [rax+10h]
0x14000a872  shl     edx, 3
0x14000a875  add     rdx, 18h
0x14000a879  call    cs:__imp_ExAllocatePool2
0x14000a880  nop     dword ptr [rax+rax+00h]
0x14000a885  mov     r14, rax
0x14000a888  test    rax, rax
0x14000a88b  jz      loc_14000ABDE
0x14000a891  movzx   ecx, dil
0x14000a895  mov     edx, 1
0x14000a89a  shr     r13, cl
0x14000a89d  mov     r8, rax; struct SC_PARITY_CONTEXT *
0x14000a8a0  mov     ecx, ebp
0x14000a8a2  xor     edi, edi
0x14000a8a4  shl     edx, cl
0x14000a8a6  mov     rcx, [rbx+8]
0x14000a8aa  dec     edx; unsigned int
0x14000a8ac  mov     rcx, [rcx+180h]; this
0x14000a8b3  call    ?InitializeContext@SC_PARITY@@QEAAXKPEAVSC_PARITY_CONTEXT@@@Z; SC_PARITY::InitializeContext(ulong,SC_PARITY_CONTEXT *)
0x14000a8b8  xor     r12d, r12d
0x14000a8bb  mov     rcx, rbx; this
0x14000a8be  mov     [rsp+68h+arg_8], r12d
0x14000a8c3  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14000a8c8  cmp     r12d, [rax+10h]
0x14000a8cc  jnb     loc_14000AC64
0x14000a8d2  mov     rdx, [rsi+8]; struct SC_PACKET *
0x14000a8d6  mov     ecx, 0F8h; unsigned __int64
0x14000a8db  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x14000a8e0  test    rax, rax
0x14000a8e3  jz      loc_14000AC5A
0x14000a8e9  mov     rcx, rax; this
0x14000a8ec  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14000a8f1  mov     rbp, rax
0x14000a8f4  test    rax, rax
0x14000a8f7  jz      loc_14000AC5A
0x14000a8fd  mov     rcx, rbx; this
0x14000a900  mov     r15d, r12d
0x14000a903  call    ?Provisioning@SIO_RAID@@QEAAPEAU_SP_PROVISIONING_INFO@@XZ; SIO_RAID::Provisioning(void)
0x14000a908  cmp     dword ptr [rax+1Ch], 1
0x14000a90c  jnz     loc_14000ABE8
0x14000a912  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14000a917  xor     edx, edx
0x14000a919  mov     r8d, [rax+10h]
0x14000a91d  mov     rax, [rbx+8]
0x14000a921  mov     rcx, [rax+180h]
0x14000a928  mov     eax, [rcx+2Ch]
0x14000a92b  imul    rax, r13
0x14000a92f  add     rax, r15
0x14000a932  div     r8
0x14000a935  mov     r8, rdx
0x14000a938  mov     [rsp+68h+arg_10], rdx
0x14000a940  mov     rax, [rbx+8]
0x14000a944  mov     rcx, rbx; this
0x14000a947  mov     rdi, [rax+180h]
0x14000a94e  mov     r12d, [rdi+28h]
0x14000a952  call    ?Provisioning@SIO_RAID@@QEAAPEAU_SP_PROVISIONING_INFO@@XZ; SIO_RAID::Provisioning(void)
0x14000a957  cmp     dword ptr [rax+1Ch], 1
0x14000a95b  jnz     loc_14000ABF8
0x14000a961  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14000a966  mov     r8, [rsp+68h+arg_10]
0x14000a96e  xor     edx, edx
0x14000a970  mov     ecx, [rax+10h]
0x14000a973  mov     eax, [rdi+2Ch]
0x14000a976  imul    rax, r13
0x14000a97a  add     rax, r15
0x14000a97d  div     rcx
0x14000a980  cmp     edx, r12d
0x14000a983  mov     r12d, 1
0x14000a989  jb      loc_14000AA72
0x14000a98f  movzx   ecx, byte ptr [rbx+2Ah]
0x14000a993  mov     r15d, r12d
0x14000a996  shl     r15, cl
0x14000a999  mov     [rsp+68h+arg_0], 0FFFFh
0x14000a9a1  lea     eax, [r15-1000h]
0x14000a9a8  cmp     eax, 3F000h
0x14000a9ad  jbe     loc_14000AB55
0x14000a9b3  mov     edx, r15d
0x14000a9b6  mov     ecx, 48h ; 'H'
0x14000a9bb  mov     r8d, 66427053h
0x14000a9c1  call    cs:__imp_ExAllocatePool2
0x14000a9c8  nop     dword ptr [rax+rax+00h]
0x14000a9cd  mov     rdi, rax
0x14000a9d0  test    rax, rax
0x14000a9d3  jz      loc_14000ABC3
0x14000a9d9  xor     r9d, r9d; ChargeQuota
0x14000a9dc  mov     [rsp+68h+Irp], 0; Irp
0x14000a9e5  xor     r8d, r8d; SecondaryBuffer
0x14000a9e8  mov     edx, r15d; Length
0x14000a9eb  mov     rcx, rdi; VirtualAddress
0x14000a9ee  call    cs:__imp_IoAllocateMdl
0x14000a9f5  nop     dword ptr [rax+rax+00h]
0x14000a9fa  mov     [rbp+78h], rax
0x14000a9fe  test    rax, rax
0x14000aa01  jz      loc_14000AC1E
0x14000aa07  mov     rcx, rax; MemoryDescriptorList
0x14000aa0a  xor     edi, edi
0x14000aa0c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000aa13  nop     dword ptr [rax+rax+00h]
0x14000aa18  mov     rcx, [rbp+78h]
0x14000aa1c  mov     edx, r12d
0x14000aa1f  call    cs:__imp_MmMdlPageContentsState
0x14000aa26  nop     dword ptr [rax+rax+00h]
0x14000aa2b  mov     eax, [rsp+68h+arg_0]
0x14000aa2f  mov     [rbp+74h], ax
0x14000aa33  mov     dword ptr [rbp+70h], 3
0x14000aa3a  mov     r15d, dword ptr [rsp+68h+arg_10]
0x14000aa42  test    edi, edi
0x14000aa44  jns     short loc_14000AA99
0x14000aa46  xor     edx, edx; Tag
0x14000aa48  mov     rcx, r14; P
0x14000aa4b  call    cs:__imp_ExFreePoolWithTag
0x14000aa52  nop     dword ptr [rax+rax+00h]
0x14000aa57  mov     rbx, [rsp+68h+arg_18]
0x14000aa5f  mov     eax, edi
0x14000aa61  add     rsp, 30h
0x14000aa65  pop     r15
0x14000aa67  pop     r14
0x14000aa69  pop     r13
0x14000aa6b  pop     r12
0x14000aa6d  pop     rdi
0x14000aa6e  pop     rsi
0x14000aa6f  pop     rbp
0x14000aa70  retn
0x14000aa72  movzx   ecx, byte ptr [rbx+2Ah]
0x14000aa76  mov     r9, r12
0x14000aa79  mov     r15d, r8d
0x14000aa7c  mov     rdx, rsi; struct SC_PACKET *
0x14000aa7f  mov     r8d, r8d
0x14000aa82  shl     r8, cl; unsigned int
0x14000aa85  shl     r9, cl; unsigned int
0x14000aa88  mov     rcx, rbp; this
0x14000aa8b  mov     byte ptr [rsp+68h+Irp], r12b; unsigned __int8
0x14000aa90  call    ?Split@SC_PACKET@@QEAAJPEAV1@KKE@Z; SC_PACKET::Split(SC_PACKET *,ulong,ulong,uchar)
0x14000aa95  mov     edi, eax
0x14000aa97  jmp     short loc_14000AA42
0x14000aa99  mov     rax, [rbp+78h]
0x14000aa9d  test    byte ptr [rax+0Ah], 5
0x14000aaa1  jz      loc_14000AB29
0x14000aaa7  mov     rax, [rax+18h]
0x14000aaab  mov     [r14+r15*8+10h], rax
0x14000aab0  mov     rax, [rsi+88h]
0x14000aab7  mov     [rbp+88h], rax
0x14000aabe  mov     rax, r12
0x14000aac1  movzx   ecx, byte ptr [rbx+2Ah]
0x14000aac5  mov     r12d, [rsp+68h+arg_8]
0x14000aaca  shl     rax, cl
0x14000aacd  lea     rcx, [rsi+28h]
0x14000aad1  mov     [rbp+90h], eax
0x14000aad7  mov     [rbp+94h], r12d
0x14000aade  mov     byte ptr [rbp+0A8h], 4
0x14000aae5  mov     byte ptr [rbp+0AAh], 1
0x14000aaec  mov     [rbp+0F0h], rbx
0x14000aaf3  mov     rax, [rsi+8]
0x14000aaf7  mov     [rbp+8], rax
0x14000aafb  mov     [rbp+10h], rsi
0x14000aaff  mov     rdx, [rcx+8]
0x14000ab03  cmp     [rdx], rcx
0x14000ab06  jnz     loc_14000ABCD
0x14000ab0c  lea     rax, [rbp+38h]
0x14000ab10  mov     [rax], rcx
0x14000ab13  mov     [rax+8], rdx
0x14000ab17  mov     [rdx], rax
0x14000ab1a  mov     [rcx+8], rax
0x14000ab1e  inc     dword ptr [rsi+48h]
0x14000ab21  inc     r12d
0x14000ab24  jmp     loc_14000A8BB
0x14000ab29  mov     [rsp+68h+Priority], 40000020h; Priority
0x14000ab31  xor     r9d, r9d; RequestedAddress
0x14000ab34  mov     r8d, r12d; CacheType
0x14000ab37  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x14000ab3f  xor     edx, edx; AccessMode
0x14000ab41  mov     rcx, rax; MemoryDescriptorList
0x14000ab44  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000ab4b  nop     dword ptr [rax+rax+00h]
0x14000ab50  jmp     loc_14000AAAB
0x14000ab55  bsr     ecx, r15d
0x14000ab59  mov     eax, r12d
0x14000ab5c  shl     eax, cl
0x14000ab5e  mov     [rsp+68h+arg_0], ecx
0x14000ab62  cmp     eax, r15d
0x14000ab65  jnz     loc_14000AC01
0x14000ab6b  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000ab72  xor     ecx, ecx; ProcNumber
0x14000ab74  mov     edi, [rax+150h]
0x14000ab7a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000ab81  nop     dword ptr [rax+rax+00h]
0x14000ab86  xor     edx, edx
0x14000ab88  div     edi
0x14000ab8a  mov     eax, [rsp+68h+arg_0]
0x14000ab8e  add     eax, 0FFFFFFF4h
0x14000ab91  movzx   ecx, dl
0x14000ab94  imul    eax, edi
0x14000ab97  add     ecx, eax
0x14000ab99  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000aba0  mov     [rsp+68h+arg_0], ecx
0x14000aba4  shl     rcx, 7
0x14000aba8  add     rcx, [rax+168h]; Lookaside
0x14000abaf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000abb6  nop     dword ptr [rax+rax+00h]
0x14000abbb  mov     rdi, rax
0x14000abbe  test    rax, rax
0x14000abc1  jnz     short loc_14000AC0C
0x14000abc3  mov     edi, 0C000009Ah
0x14000abc8  jmp     loc_14000AA3A
0x14000abcd  mov     ecx, 3
0x14000abd2  int     29h; Win8: RtlFailFast(ecx)
0x14000abd4  mov     edi, 0C0000002h
0x14000abd9  jmp     loc_14000AA57
0x14000abde  mov     edi, 0C000009Ah
0x14000abe3  jmp     loc_14000AA57
0x14000abe8  mov     r8d, r12d
0x14000abeb  mov     [rsp+68h+arg_10], r8
0x14000abf3  jmp     loc_14000A940
0x14000abf8  mov     edx, [rsp+68h+arg_8]
0x14000abfc  jmp     loc_14000A980
0x14000ac01  inc     ecx
0x14000ac03  mov     [rsp+68h+arg_0], ecx
0x14000ac07  jmp     loc_14000AB6B
0x14000ac0c  mov     r8d, r15d; Size
0x14000ac0f  xor     edx, edx; Val
0x14000ac11  mov     rcx, rax; void *
0x14000ac14  call    memset
0x14000ac19  jmp     loc_14000A9D9
0x14000ac1e  mov     eax, [rsp+68h+arg_0]
0x14000ac22  cmp     eax, 0FFFFh
0x14000ac27  jz      loc_1400690AA
0x14000ac2d  mov     ecx, eax
0x14000ac2f  mov     rdx, rdi; Entry
0x14000ac32  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000ac39  shl     rcx, 7
0x14000ac3d  add     rcx, [rax+168h]; Lookaside
0x14000ac44  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000ac4b  nop     dword ptr [rax+rax+00h]
0x14000ac50  mov     edi, 0C000009Ah
0x14000ac55  jmp     loc_14000AA3A
0x14000ac5a  mov     edi, 0C000009Ah
0x14000ac5f  jmp     loc_14000AA46
0x14000ac64  movzx   ecx, byte ptr [rbx+2Ah]
0x14000ac68  mov     r8d, 1
0x14000ac6e  shl     r8, cl; unsigned int
0x14000ac71  xor     r9d, r9d; unsigned __int8
0x14000ac74  mov     rcx, [rbx+8]
0x14000ac78  mov     rdx, r14; struct SC_PARITY_CONTEXT *
0x14000ac7b  mov     rcx, [rcx+180h]; this
0x14000ac82  call    ?Execute@SC_PARITY@@QEAAXPEAVSC_PARITY_CONTEXT@@KE@Z; SC_PARITY::Execute(SC_PARITY_CONTEXT *,ulong,uchar)
0x14000ac87  jmp     loc_14000AA46
0x1400690aa  xor     edx, edx; Tag
0x1400690ac  mov     rcx, rdi; P
0x1400690af  call    cs:__imp_ExFreePoolWithTag
0x1400690b6  nop     dword ptr [rax+rax+00h]
0x1400690bb  mov     edi, 0C000009Ah
0x1400690c0  jmp     loc_14000AA3A
```
