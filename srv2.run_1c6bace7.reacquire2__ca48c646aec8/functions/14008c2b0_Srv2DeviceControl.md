# Srv2DeviceControl

- ea: `0x14008c2b0`
- end: `0x14008c446`
- name: `Srv2DeviceControl`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14008c170`

## callees

- `0x14002019c`
- `0x140059338`
- `0x140059540`
- `0x14008c2b0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008c413`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008c413`
- `ntoskrnl!IofCompleteRequest` at `0x14008c3ed`
- `ntoskrnl!IofCompleteRequest` at `0x14008c3ed`
- `ntoskrnl!IoGetCurrentProcess` at `0x14008c2e6`
- `ntoskrnl!IoGetCurrentProcess` at `0x14008c2e6`
- `ntoskrnl!ProbeForRead` at `0x14009b75c`
- `ntoskrnl!ProbeForRead` at `0x14009b774`
- `ntoskrnl!ProbeForRead` at `0x14009b75c`
- `ntoskrnl!ProbeForRead` at `0x14009b774`

## pseudocode

```c
__int64 __fastcall Srv2DeviceControl(__int64 a1, IRP *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int LowPart; // r13d
  SIZE_T Length; // r12
  struct _IRP *Parameters; // rdi
  PVOID MappedSystemVa; // rsi
  PMDL MdlAddress; // rcx
  struct _IRP *MasterIrp; // r15
  int Options; // [rsp+90h] [rbp+18h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids);
  }
  if ( IoGetCurrentProcess() != Srv2ServerProcess )
  {
    v3 = Srv2QueueIrpToSystem(a2);
    goto LABEL_4;
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( (LowPart & 3) != 0 )
  {
    if ( (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & 3) == 1
      || (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & 3) == 2 )
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      if ( (_DWORD)Length )
      {
        MdlAddress = a2->MdlAddress;
        if ( (MdlAddress->MdlFlags & 5) != 0 )
          MappedSystemVa = MdlAddress->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
        if ( !MappedSystemVa )
        {
          v4 = -1073741670;
          goto LABEL_17;
        }
      }
      else
      {
        MappedSystemVa = 0;
      }
      LODWORD(Parameters) = (_DWORD)MasterIrp;
      goto LABEL_9;
    }
    if ( (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & 3) == 3 )
    {
      Parameters = (struct _IRP *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
      MappedSystemVa = a2->UserBuffer;
      if ( a2->RequestorMode == 1 )
      {
        ProbeForRead(Parameters, CurrentStackLocation->Parameters.Create.Options, 1u);
        ProbeForRead(MappedSystemVa, Length, 1u);
      }
      goto LABEL_9;
    }
    Parameters = 0;
  }
  else
  {
    Parameters = a2->AssociatedIrp.MasterIrp;
  }
  MappedSystemVa = Parameters;
LABEL_9:
  v3 = Srv2ProcessFsctl(
         (int)CurrentStackLocation->FileObject,
         (int)a2 + 48,
         (int)Parameters,
         Options,
         (__int64)MappedSystemVa,
         Length,
         LowPart,
         (__int64)&a2->IoStatus,
         (__int64)CurrentStackLocation->DeviceObject,
         a2);
LABEL_4:
  v4 = v3;
  if ( v3 != 259 )
  {
LABEL_17:
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 2);
  }
  return v4;
}

```

## disassembly

```asm
0x14008c2b0  mov     [rsp+arg_0], rbx
0x14008c2b5  mov     [rsp+arg_18], rsi
0x14008c2ba  mov     [rsp+arg_8], rdx
0x14008c2bf  push    rdi
0x14008c2c0  push    r12
0x14008c2c2  push    r13
0x14008c2c4  push    r14
0x14008c2c6  push    r15
0x14008c2c8  sub     rsp, 50h
0x14008c2cc  mov     rbx, rdx
0x14008c2cf  lea     rax, WPP_GLOBAL_Control
0x14008c2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c2dd  cmp     rcx, rax
0x14008c2e0  jnz     loc_14008C39A
0x14008c2e6  call    cs:__imp_IoGetCurrentProcess
0x14008c2ed  nop     dword ptr [rax+rax+00h]
0x14008c2f2  cmp     rax, cs:Srv2ServerProcess
0x14008c2f9  jz      short loc_14008C32E
0x14008c2fb  mov     rcx, rbx; Context
0x14008c2fe  call    Srv2QueueIrpToSystem
0x14008c303  mov     edi, eax
0x14008c305  cmp     edi, 103h
0x14008c30b  jnz     loc_14008C3E5
0x14008c311  mov     eax, edi
0x14008c313  lea     r11, [rsp+78h+var_28]
0x14008c318  mov     rbx, [r11+30h]
0x14008c31c  mov     rsi, [r11+48h]
0x14008c320  mov     rsp, r11
0x14008c323  pop     r15
0x14008c325  pop     r14
0x14008c327  pop     r13
0x14008c329  pop     r12
0x14008c32b  pop     rdi
0x14008c32c  retn
0x14008c32e  mov     r14, [rbx+0B8h]
0x14008c335  mov     r13d, [r14+18h]
0x14008c339  mov     ecx, [r14+10h]
0x14008c33d  mov     [rsp+78h+arg_10], ecx
0x14008c344  mov     r12d, [r14+8]
0x14008c348  mov     eax, r13d
0x14008c34b  and     eax, 3
0x14008c34e  jnz     loc_14008C424
0x14008c354  mov     rdi, [rbx+18h]
0x14008c358  mov     rsi, rdi
0x14008c35b  lea     rdx, [rbx+30h]; int
0x14008c35f  mov     [rsp+78h+Irp], rbx; Irp
0x14008c364  mov     rax, [r14+28h]
0x14008c368  mov     [rsp+78h+var_38], rax; __int64
0x14008c36d  mov     [rsp+78h+var_40], rdx; __int64
0x14008c372  mov     [rsp+78h+var_48], r13d; int
0x14008c377  mov     [rsp+78h+Priority], r12d; int
0x14008c37c  mov     qword ptr [rsp+78h+BugCheckOnFailure], rsi; __int64
0x14008c381  mov     r9d, [rsp+78h+arg_10]; int
0x14008c389  mov     r8, rdi; int
0x14008c38c  mov     rcx, [r14+30h]; int
0x14008c390  call    Srv2ProcessFsctl
0x14008c395  jmp     loc_14008C303
0x14008c39a  mov     eax, [rcx+2Ch]
0x14008c39d  test    al, 4
0x14008c39f  jz      loc_14008C2E6
0x14008c3a5  cmp     byte ptr [rcx+29h], 2
0x14008c3a9  jb      loc_14008C2E6
0x14008c3af  mov     edx, 0Fh
0x14008c3b4  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x14008c3bb  mov     rcx, [rcx+18h]
0x14008c3bf  call    WPP_SF_
0x14008c3c4  jmp     loc_14008C2E6
0x14008c3c9  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14008c3cd  test    byte ptr [rcx+0Ah], 5
0x14008c3d1  jz      short loc_14008C3FE
0x14008c3d3  mov     rsi, [rcx+18h]
0x14008c3d7  test    rsi, rsi
0x14008c3da  jnz     loc_14009B7A6
0x14008c3e0  mov     edi, 0C000009Ah
0x14008c3e5  mov     [rbx+30h], edi
0x14008c3e8  mov     dl, 2; PriorityBoost
0x14008c3ea  mov     rcx, rbx; Irp
0x14008c3ed  call    cs:__imp_IofCompleteRequest
0x14008c3f4  nop     dword ptr [rax+rax+00h]
0x14008c3f9  jmp     loc_14008C311
0x14008c3fe  mov     [rsp+78h+Priority], 40000010h; Priority
0x14008c406  mov     [rsp+78h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14008c40a  xor     r9d, r9d; RequestedAddress
0x14008c40d  xor     edx, edx; AccessMode
0x14008c40f  lea     r8d, [r9+1]; CacheType
0x14008c413  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008c41a  nop     dword ptr [rax+rax+00h]
0x14008c41f  mov     rsi, rax
0x14008c422  jmp     short loc_14008C3D7
0x14008c424  sub     eax, 1
0x14008c427  jz      loc_14009B795
0x14008c42d  sub     eax, 1
0x14008c430  jz      loc_14009B795
0x14008c436  cmp     eax, 1
0x14008c439  jz      loc_14009B73E
0x14008c43f  xor     edi, edi
0x14008c441  jmp     loc_14008C358
0x14009b73e  mov     rdi, [r14+20h]
0x14009b742  mov     rsi, [rbx+70h]
0x14009b746  cmp     byte ptr [rbx+40h], 1
0x14009b74a  jnz     loc_14008C35B
0x14009b750  mov     rdx, rcx; Length
0x14009b753  mov     r8d, 1; Alignment
0x14009b759  mov     rcx, rdi; Address
0x14009b75c  call    cs:__imp_ProbeForRead
0x14009b763  nop     dword ptr [rax+rax+00h]
0x14009b768  mov     rdx, r12; Length
0x14009b76b  mov     r8d, 1; Alignment
0x14009b771  mov     rcx, rsi; Address
0x14009b774  call    cs:__imp_ProbeForRead
0x14009b77b  nop     dword ptr [rax+rax+00h]
0x14009b780  nop
0x14009b781  jmp     loc_14008C35B
0x14009b786  mov     edi, eax
0x14009b788  mov     rbx, [rsp+78h+arg_8]
0x14009b790  jmp     loc_14008C305
0x14009b795  mov     r15, [rbx+18h]
0x14009b799  xor     edi, edi
0x14009b79b  test    r12d, r12d
0x14009b79e  jnz     loc_14008C3C9
0x14009b7a4  mov     esi, edi
0x14009b7a6  mov     rdi, r15
0x14009b7a9  jmp     loc_14008C35B
```
