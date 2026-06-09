# TdxTdiDispatchDeviceControl

- ea: `0x140010f10`
- end: `0x1400112d5`
- name: `TdxTdiDispatchDeviceControl`
- size: `965`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, IRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005fe0`
- `0x140010100`
- `0x140010f10`
- `0x1400121d8`
- `0x14001606c`
- `0x140016fec`
- `0x1400184e0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140010fd0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010fd0`
- `ntoskrnl!IoIs32bitProcess` at `0x140010fed`
- `ntoskrnl!IoIs32bitProcess` at `0x140010fed`
- `ntoskrnl!IoAllocateMdl` at `0x140011164`
- `ntoskrnl!IoAllocateMdl` at `0x140011164`
- `ntoskrnl!MmProbeAndLockPages` at `0x140011189`
- `ntoskrnl!MmProbeAndLockPages` at `0x140011189`
- `ntoskrnl!MmUnlockPages` at `0x14001126d`
- `ntoskrnl!MmUnlockPages` at `0x14001126d`
- `ntoskrnl!IoFreeMdl` at `0x14001127c`
- `ntoskrnl!IoFreeMdl` at `0x14001127c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400111c3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400111c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400110e5`
- `ntoskrnl!ExAllocatePool2` at `0x1400110e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011252`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011252`
- `ntoskrnl!IofCompleteRequest` at `0x1400112b4`
- `ntoskrnl!IofCompleteRequest` at `0x1400112b4`
- `TDI!TdiMapUserRequest` at `0x140010f56`
- `TDI!TdiMapUserRequest` at `0x140010f56`

## pseudocode

```c
__int64 __fastcall TdxTdiDispatchDeviceControl(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  int v4; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  struct _IRP *MasterIrp; // rbx
  BOOLEAN v8; // al
  unsigned int Options; // ecx
  int v10; // edx
  unsigned int v11; // eax
  unsigned int MdlAddress; // ecx
  ULONG Flags; // r13d
  void *MdlAddress_high; // r12
  struct _MDL *v15; // r15
  void *Pool2; // rax
  struct _MDL *Mdl; // rax
  struct _LIST_ENTRY *MappedSystemVa; // rax
  PFILE_OBJECT FileObject; // rcx
  int Information; // eax
  char v21; // [rsp+30h] [rbp-88h]
  __m128i v22; // [rsp+48h] [rbp-70h] BYREF
  __int128 v23; // [rsp+58h] [rbp-60h]
  LIST_ENTRY ThreadListEntry; // [rsp+68h] [rbp-50h]
  int Length; // [rsp+C0h] [rbp+8h]
  void *Src; // [rsp+D0h] [rbp+18h]
  struct _LIST_ENTRY *VirtualAddress; // [rsp+D8h] [rbp+20h]

  a2->IoStatus.Information = 0;
  if ( a1 == TdxDeviceObject )
    goto LABEL_2;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( !TdiMapUserRequest(a1, a2, CurrentStackLocation) )
    return TdxTdiDispatchInternalDeviceControl(a1, a2);
  switch ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart )
  {
    case 0x120003u:
      Information = TdxTcpQueryInformationEx(a2, CurrentStackLocation);
      goto LABEL_52;
    case 0x120028u:
    case 0x128004u:
      Information = TdxTcpSetInformationEx(a2, CurrentStackLocation);
LABEL_52:
      v4 = Information;
      goto LABEL_53;
    case 0x210038u:
      v22 = 0;
      v23 = 0;
      ThreadListEntry = 0;
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      if ( KeGetCurrentIrql() >= 2u )
      {
        v4 = -1073741637;
        goto LABEL_54;
      }
      v8 = IoIs32bitProcess(a2);
      Options = CurrentStackLocation->Parameters.Create.Options;
      if ( v8 )
      {
        if ( Options != 28 )
        {
LABEL_16:
          v4 = -1073741306;
          goto LABEL_54;
        }
        v10 = *(_DWORD *)&MasterIrp->Type;
        v11 = *(_DWORD *)(&MasterIrp->Size + 1);
        MdlAddress = (unsigned int)MasterIrp->MdlAddress;
        Flags = MasterIrp->Flags;
        Length = MasterIrp->AssociatedIrp.IrpCount;
        v22.m128i_i32[0] = *(_DWORD *)&MasterIrp->Type;
        *(__int64 *)((char *)v22.m128i_i64 + 4) = __PAIR64__(MdlAddress, v11);
        DWORD2(v23) = Flags;
        LODWORD(ThreadListEntry.Blink) = Length;
        MdlAddress_high = (void *)HIDWORD(MasterIrp->MdlAddress);
        *(_QWORD *)&v23 = MdlAddress_high;
        VirtualAddress = (struct _LIST_ENTRY *)*(&MasterIrp->Flags + 1);
        ThreadListEntry.Flink = VirtualAddress;
      }
      else
      {
        if ( Options < 0x30 )
          goto LABEL_16;
        v22 = *(__m128i *)&MasterIrp->Type;
        v23 = *(_OWORD *)&MasterIrp->Flags;
        ThreadListEntry = MasterIrp->ThreadListEntry;
        Length = _mm_cvtsi128_si32(_mm_loadl_epi64((const __m128i *)&MasterIrp->ThreadListEntry.Blink));
        VirtualAddress = ThreadListEntry.Flink;
        Flags = MasterIrp->AssociatedIrp.IrpCount;
        MdlAddress_high = (void *)v23;
        v10 = _mm_cvtsi128_si32(v22);
      }
      v15 = 0;
      v21 = 0;
      v4 = 0;
      if ( a2->RequestorMode )
      {
        if ( (unsigned int)(v10 - 1) > 2 )
          goto LABEL_28;
        if ( v10 == 3 )
        {
          if ( !v22.m128i_i32[1] )
            goto LABEL_24;
LABEL_28:
          v4 = -1073741811;
          goto LABEL_54;
        }
        if ( (unsigned int)(v22.m128i_i32[1] - 65532) <= 1 )
          goto LABEL_28;
      }
LABEL_24:
      if ( Flags )
      {
        Src = MdlAddress_high;
        Pool2 = (void *)ExAllocatePool2(64, Flags, 1232626772);
        MdlAddress_high = Pool2;
        *(_QWORD *)&v23 = Pool2;
        if ( !Pool2 )
          goto LABEL_26;
        if ( a2->RequestorMode )
          RtlCopyFromUser(Pool2, Src, Flags);
        else
          RtlCopyVolatileMemory(Pool2, Src, Flags);
      }
      if ( !Length )
        goto LABEL_39;
      Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 1u, 0);
      v15 = Mdl;
      if ( Mdl )
      {
        MmProbeAndLockPages(Mdl, a2->RequestorMode, IoWriteAccess);
        v21 = 1;
        if ( (v15->MdlFlags & 5) != 0 )
          MappedSystemVa = (struct _LIST_ENTRY *)v15->MappedSystemVa;
        else
          MappedSystemVa = (struct _LIST_ENTRY *)MmMapLockedPagesSpecifyCache(v15, 0, MmCached, 0, 0, 0x40000010u);
        ThreadListEntry.Flink = MappedSystemVa;
        if ( !MappedSystemVa )
          v4 = -1073741670;
        goto LABEL_39;
      }
LABEL_26:
      v4 = -1073741801;
LABEL_39:
      if ( v4 >= 0 )
      {
        FileObject = CurrentStackLocation->FileObject;
        if ( (unsigned __int64)FileObject->FsContext2 - 1 <= 1 )
        {
          v4 = TdxIssueIoControlRequest(FileObject->FsContext, a2, &v22);
          Flags = DWORD2(v23);
          MdlAddress_high = (void *)v23;
        }
        else
        {
          v4 = -1073741811;
        }
      }
      if ( MdlAddress_high && Flags )
        ExFreePoolWithTag(MdlAddress_high, 0x49786454u);
      if ( v15 )
      {
        if ( v21 )
          MmUnlockPages(v15);
        IoFreeMdl(v15);
      }
      goto LABEL_53;
    case 0x210203u:
    case 0x210207u:
LABEL_2:
      v4 = -1073741822;
LABEL_54:
      a2->IoStatus.Status = v4;
      IofCompleteRequest(a2, 2);
      return (unsigned int)v4;
  }
  v4 = -1073741811;
LABEL_53:
  if ( v4 != 259 )
    goto LABEL_54;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140010f10  mov     [rsp+arg_8], rdx
0x140010f15  push    rbx
0x140010f16  push    rsi
0x140010f17  push    r12
0x140010f19  push    r13
0x140010f1b  push    r14
0x140010f1d  push    r15
0x140010f1f  sub     rsp, 88h
0x140010f26  mov     rsi, rdx
0x140010f29  mov     rbx, rcx
0x140010f2c  mov     qword ptr [rdx+38h], 0
0x140010f34  cmp     rcx, cs:TdxDeviceObject
0x140010f3b  jnz     short loc_140010F47
0x140010f3d  mov     ebx, 0C0000002h
0x140010f42  jmp     loc_1400112AC
0x140010f47  mov     r14, [rdx+0B8h]
0x140010f4e  mov     [rsp+0B8h+var_78], r14
0x140010f53  mov     r8, r14; IrpSp
0x140010f56  call    cs:__imp_TdiMapUserRequest
0x140010f5d  nop     dword ptr [rax+rax+00h]
0x140010f62  test    eax, eax
0x140010f64  jnz     short loc_140010F76
0x140010f66  mov     rdx, rsi
0x140010f69  mov     rcx, rbx
0x140010f6c  call    TdxTdiDispatchInternalDeviceControl
0x140010f71  jmp     loc_1400112C2
0x140010f76  mov     ecx, [r14+18h]
0x140010f7a  sub     ecx, 120003h
0x140010f80  jz      loc_140011297
0x140010f86  sub     ecx, 25h ; '%'
0x140010f89  jz      loc_14001128A
0x140010f8f  sub     ecx, 7FDCh
0x140010f95  jz      loc_14001128A
0x140010f9b  sub     ecx, 0E8034h
0x140010fa1  jz      short loc_140010FBA
0x140010fa3  sub     ecx, 1CBh
0x140010fa9  jz      short loc_140010F3D
0x140010fab  cmp     ecx, 4
0x140010fae  jz      short loc_140010F3D
0x140010fb0  mov     ebx, 0C000000Dh
0x140010fb5  jmp     loc_1400112A4
0x140010fba  xorps   xmm0, xmm0
0x140010fbd  movups  [rsp+0B8h+var_70], xmm0
0x140010fc2  movups  [rsp+0B8h+var_60], xmm0
0x140010fc7  movups  xmmword ptr [rsp+0B8h+var_50.Flink], xmm0
0x140010fcc  mov     rbx, [rsi+18h]
0x140010fd0  call    cs:__imp_KeGetCurrentIrql
0x140010fd7  nop     dword ptr [rax+rax+00h]
0x140010fdc  cmp     al, 2
0x140010fde  jb      short loc_140010FEA
0x140010fe0  mov     ebx, 0C00000BBh
0x140010fe5  jmp     loc_1400112AC
0x140010fea  mov     rcx, rsi; Irp
0x140010fed  call    cs:__imp_IoIs32bitProcess
0x140010ff4  nop     dword ptr [rax+rax+00h]
0x140010ff9  mov     ecx, [r14+10h]
0x140010ffd  test    al, al
0x140010fff  jz      short loc_140011059
0x140011001  cmp     ecx, 1Ch
0x140011004  jz      short loc_140011010
0x140011006  mov     ebx, 0C0000206h
0x14001100b  jmp     loc_1400112AC
0x140011010  mov     edx, [rbx]
0x140011012  mov     eax, [rbx+4]
0x140011015  mov     ecx, [rbx+8]
0x140011018  mov     r13d, [rbx+10h]
0x14001101c  mov     r8d, [rbx+18h]
0x140011020  mov     [rsp+0B8h+Length], r8d
0x140011028  mov     dword ptr [rsp+0B8h+var_70], edx
0x14001102c  mov     dword ptr [rsp+0B8h+var_70+4], eax
0x140011030  mov     dword ptr [rsp+0B8h+var_70+8], ecx
0x140011034  mov     dword ptr [rsp+0B8h+var_60+8], r13d
0x140011039  mov     dword ptr [rsp+0B8h+var_50.Blink], r8d
0x14001103e  mov     r12d, [rbx+0Ch]
0x140011042  mov     qword ptr [rsp+0B8h+var_60], r12
0x140011047  mov     eax, [rbx+14h]
0x14001104a  mov     [rsp+0B8h+VirtualAddress], rax
0x140011052  mov     [rsp+0B8h+var_50.Flink], rax
0x140011057  jmp     short loc_14001109C
0x140011059  cmp     ecx, 30h ; '0'
0x14001105c  jb      short loc_140011006
0x14001105e  movups  xmm3, xmmword ptr [rbx]
0x140011061  movups  [rsp+0B8h+var_70], xmm3
0x140011066  movups  xmm2, xmmword ptr [rbx+10h]
0x14001106a  movups  [rsp+0B8h+var_60], xmm2
0x14001106f  movups  xmm1, xmmword ptr [rbx+20h]
0x140011073  movups  xmmword ptr [rsp+0B8h+var_50.Flink], xmm1
0x140011078  movq    xmm0, qword ptr [rbx+28h]
0x14001107d  movd    [rsp+0B8h+Length], xmm0
0x140011086  movsd   [rsp+0B8h+VirtualAddress], xmm1
0x14001108f  mov     r13d, [rbx+18h]
0x140011093  movq    r12, xmm2
0x140011098  movd    edx, xmm3
0x14001109c  xor     r15d, r15d
0x14001109f  mov     [rsp+0B8h+var_80], r15
0x1400110a4  mov     [rsp+0B8h+var_88], r15b
0x1400110a9  xor     ebx, ebx
0x1400110ab  cmp     [rsi+40h], bl
0x1400110ae  jz      short loc_1400110CA
0x1400110b0  lea     eax, [rdx-1]
0x1400110b3  cmp     eax, 2
0x1400110b6  ja      short loc_140011112
0x1400110b8  mov     rax, qword ptr [rsp+0B8h+var_70]
0x1400110bd  shr     rax, 20h
0x1400110c1  cmp     edx, 3
0x1400110c4  jnz     short loc_140011108
0x1400110c6  test    eax, eax
0x1400110c8  jnz     short loc_140011112
0x1400110ca  test    r13d, r13d
0x1400110cd  jz      short loc_14001113C
0x1400110cf  mov     [rsp+0B8h+Src], r12
0x1400110d7  mov     edx, r13d
0x1400110da  mov     ecx, 40h ; '@'
0x1400110df  mov     r8d, 49786454h
0x1400110e5  call    cs:__imp_ExAllocatePool2
0x1400110ec  nop     dword ptr [rax+rax+00h]
0x1400110f1  mov     r12, rax
0x1400110f4  mov     qword ptr [rsp+0B8h+var_60], rax
0x1400110f9  test    rax, rax
0x1400110fc  jnz     short loc_14001111C
0x1400110fe  mov     ebx, 0C0000017h
0x140011103  jmp     loc_1400111DF
0x140011108  sub     eax, 0FFFCh
0x14001110d  cmp     eax, 1
0x140011110  ja      short loc_1400110CA
0x140011112  mov     ebx, 0C000000Dh
0x140011117  jmp     loc_1400112AC
0x14001111c  mov     r8d, r13d; Size
0x14001111f  mov     rdx, [rsp+0B8h+Src]; Src
0x140011127  mov     rcx, rax; void *
0x14001112a  cmp     byte ptr [rsi+40h], 0
0x14001112e  jz      short loc_140011137
0x140011130  call    RtlCopyFromUser
0x140011135  jmp     short loc_14001113C
0x140011137  call    RtlCopyVolatileMemory
0x14001113c  mov     eax, [rsp+0B8h+Length]
0x140011143  test    eax, eax
0x140011145  jz      loc_1400111E3
0x14001114b  mov     [rsp+0B8h+Irp], 0; Irp
0x140011154  mov     r9b, 1; ChargeQuota
0x140011157  xor     r8d, r8d; SecondaryBuffer
0x14001115a  mov     edx, eax; Length
0x14001115c  mov     rcx, [rsp+0B8h+VirtualAddress]; VirtualAddress
0x140011164  call    cs:__imp_IoAllocateMdl
0x14001116b  nop     dword ptr [rax+rax+00h]
0x140011170  mov     r15, rax
0x140011173  mov     [rsp+0B8h+var_80], rax
0x140011178  test    rax, rax
0x14001117b  jz      short loc_1400110FE
0x14001117d  mov     r8d, 1; Operation
0x140011183  mov     dl, [rsi+40h]; AccessMode
0x140011186  mov     rcx, rax; MemoryDescriptorList
0x140011189  call    cs:__imp_MmProbeAndLockPages
0x140011190  nop     dword ptr [rax+rax+00h]
0x140011195  mov     [rsp+0B8h+var_88], 1
0x14001119a  test    byte ptr [r15+0Ah], 5
0x14001119f  jz      short loc_1400111A7
0x1400111a1  mov     rax, [r15+18h]
0x1400111a5  jmp     short loc_1400111CF
0x1400111a7  mov     [rsp+0B8h+Priority], 40000010h; Priority
0x1400111af  mov     dword ptr [rsp+0B8h+Irp], 0; BugCheckOnFailure
0x1400111b7  xor     r9d, r9d; RequestedAddress
0x1400111ba  xor     edx, edx; AccessMode
0x1400111bc  lea     r8d, [r9+1]; CacheType
0x1400111c0  mov     rcx, r15; MemoryDescriptorList
0x1400111c3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400111ca  nop     dword ptr [rax+rax+00h]
0x1400111cf  mov     [rsp+0B8h+var_50.Flink], rax
0x1400111d4  mov     ecx, 0C000009Ah
0x1400111d9  test    rax, rax
0x1400111dc  cmovz   ebx, ecx
0x1400111df  mov     [rsp+0B8h+var_84], ebx
0x1400111e3  jmp     short loc_140011207
0x1400111e5  mov     ebx, eax
0x1400111e7  mov     [rsp+0B8h+var_84], eax
0x1400111eb  mov     rsi, [rsp+0B8h+arg_8]
0x1400111f3  mov     r15, [rsp+0B8h+var_80]
0x1400111f8  mov     r13d, dword ptr [rsp+0B8h+var_60+8]
0x1400111fd  mov     r12, qword ptr [rsp+0B8h+var_60]
0x140011202  mov     r14, [rsp+0B8h+var_78]
0x140011207  test    ebx, ebx
0x140011209  js      short loc_140011240
0x14001120b  mov     rcx, [r14+30h]
0x14001120f  mov     rax, [rcx+20h]
0x140011213  dec     rax
0x140011216  cmp     rax, 1
0x14001121a  jbe     short loc_140011223
0x14001121c  mov     ebx, 0C000000Dh
0x140011221  jmp     short loc_140011240
0x140011223  lea     r8, [rsp+0B8h+var_70]
0x140011228  mov     rdx, rsi
0x14001122b  mov     rcx, [rcx+18h]
0x14001122f  call    TdxIssueIoControlRequest
0x140011234  mov     ebx, eax
0x140011236  mov     r13d, dword ptr [rsp+0B8h+var_60+8]
0x14001123b  mov     r12, qword ptr [rsp+0B8h+var_60]
0x140011240  test    r12, r12
0x140011243  jz      short loc_14001125E
0x140011245  test    r13d, r13d
0x140011248  jz      short loc_14001125E
0x14001124a  mov     edx, 49786454h; Tag
0x14001124f  mov     rcx, r12; P
0x140011252  call    cs:__imp_ExFreePoolWithTag
0x140011259  nop     dword ptr [rax+rax+00h]
0x14001125e  test    r15, r15
0x140011261  jz      short loc_1400112A4
0x140011263  cmp     [rsp+0B8h+var_88], 0
0x140011268  jz      short loc_140011279
0x14001126a  mov     rcx, r15; MemoryDescriptorList
0x14001126d  call    cs:__imp_MmUnlockPages
0x140011274  nop     dword ptr [rax+rax+00h]
0x140011279  mov     rcx, r15; Mdl
0x14001127c  call    cs:__imp_IoFreeMdl
0x140011283  nop     dword ptr [rax+rax+00h]
0x140011288  jmp     short loc_1400112A4
0x14001128a  mov     rdx, r14
0x14001128d  mov     rcx, rsi
0x140011290  call    TdxTcpSetInformationEx
0x140011295  jmp     short loc_1400112A2
0x140011297  mov     rdx, r14
0x14001129a  mov     rcx, rsi
0x14001129d  call    TdxTcpQueryInformationEx
0x1400112a2  mov     ebx, eax
0x1400112a4  cmp     ebx, 103h
0x1400112aa  jz      short loc_1400112C0
0x1400112ac  mov     [rsi+30h], ebx
0x1400112af  mov     dl, 2; PriorityBoost
0x1400112b1  mov     rcx, rsi; Irp
0x1400112b4  call    cs:__imp_IofCompleteRequest
0x1400112bb  nop     dword ptr [rax+rax+00h]
0x1400112c0  mov     eax, ebx
0x1400112c2  add     rsp, 88h
0x1400112c9  pop     r15
0x1400112cb  pop     r14
0x1400112cd  pop     r13
0x1400112cf  pop     r12
0x1400112d1  pop     rsi
0x1400112d2  pop     rbx
0x1400112d3  retn
```
