# Smb2AcknowledgeOplockBreak

- ea: `0x14002b7f8`
- end: `0x14002ba1f`
- name: `Smb2AcknowledgeOplockBreak`
- size: `551`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x140009760`
- `0x140021cc0`
- `0x14002bfc0`
- `0x14002c820`

## callees

- `0x140004960`
- `0x140005070`
- `0x140012790`
- `0x140012ca0`
- `0x140014d60`
- `0x14002143c`
- `0x140022958`
- `0x14002b7f8`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002b9f6`
- `ntoskrnl!IoFreeMdl` at `0x14002b9f6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002b911`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002b911`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b9ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b9ac`
- `ntoskrnl!IoFreeIrp` at `0x14002ba0e`
- `ntoskrnl!IoFreeIrp` at `0x14002ba0e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002b92c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002b92c`
- `ntoskrnl!MmUnlockPages` at `0x14002b9e7`
- `ntoskrnl!MmUnlockPages` at `0x14002b9e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002b829`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002b854`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002b829`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002b854`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002b953`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002b985`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002b953`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002b985`

## string_xrefs

- `0x14002b8f2`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2AcknowledgeOplockBreak(char *P, __int64 a2, __int64 a3)
{
  char v3; // bp
  void *FileHandle; // rbx
  unsigned int v6; // r14d
  __int64 v7; // rdx
  bool v8; // zf
  __int64 v9; // rbx
  __int64 v10; // rbx
  IRP *v12; // rbx
  PCHAR AuxiliaryBuffer; // rcx
  PMDL MdlAddress; // rdi
  struct _MDL *v15; // rsi
  CSHORT MdlFlags; // ax
  int v17; // [rsp+20h] [rbp-58h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v3 = a2;
  FileHandle = (void *)Smb2GetFileHandle(P, a2, a3);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)P + 14, &LockHandle);
  v6 = Smb2AcknowledgeOplockBreakInternal(P, FileHandle, &LockHandle);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)P + 14, &LockHandle);
  if ( !P[286] )
  {
LABEL_12:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return v6;
  }
  P[286] = 0;
  if ( v3 )
  {
    Smb2ReferenceFile(P);
    P[285] = 0;
    *((_QWORD *)P + 6) = Smb2ProcessOplockBreak;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids, P, 0);
    }
    v8 = *((_DWORD *)P + 2) == 5;
    *((_DWORD *)P + 18) = 0;
    if ( v8 )
    {
      LOBYTE(v17) = 1;
      LOBYTE(v7) = 1;
      SRV2_PERF_ENTER_EX(P + 584, v7, 391, "Srv2PostToThreadPool", v17);
    }
    v9 = *(_QWORD *)(*((_QWORD *)P + 8) + 136LL);
    v10 = *(_QWORD *)(v9 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v10, (PSLIST_ENTRY)P + 2) && *(_WORD *)(v10 + 66) )
      RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v10);
    goto LABEL_12;
  }
  v12 = (IRP *)*((_QWORD *)P + 33);
  *((_QWORD *)P + 33) = 0;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v12 )
  {
    Smb2DereferenceFile(P);
    AuxiliaryBuffer = v12->Tail.Overlay.AuxiliaryBuffer;
    if ( AuxiliaryBuffer )
    {
      ExFreePoolWithTag(AuxiliaryBuffer, 0);
      v12->Tail.Overlay.AuxiliaryBuffer = 0;
    }
    MdlAddress = v12->MdlAddress;
    if ( MdlAddress && (MdlAddress->MdlFlags & 4) == 0 )
    {
      do
      {
        v15 = MdlAddress;
        MdlAddress = MdlAddress->Next;
        MdlFlags = v15->MdlFlags;
        if ( (MdlFlags & 2) != 0 || (MdlFlags & 0x20) != 0 )
          MmUnlockPages(v15);
        IoFreeMdl(v15);
      }
      while ( MdlAddress );
      v12->MdlAddress = 0;
    }
    IoFreeIrp(v12);
  }
  return v6;
}

```

## disassembly

```asm
0x14002b7f8  push    rbx
0x14002b7fa  push    rbp
0x14002b7fb  push    rsi
0x14002b7fc  push    rdi
0x14002b7fd  push    r14
0x14002b7ff  sub     rsp, 50h
0x14002b803  xorps   xmm0, xmm0
0x14002b806  xor     eax, eax
0x14002b808  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14002b80d  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14002b812  mov     bpl, dl
0x14002b815  mov     rsi, rcx
0x14002b818  call    Smb2GetFileHandle
0x14002b81d  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14002b822  mov     rbx, rax
0x14002b825  lea     rcx, [rsi+70h]; SpinLock
0x14002b829  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002b830  nop     dword ptr [rax+rax+00h]
0x14002b835  mov     r9b, bpl
0x14002b838  lea     r8, [rsp+78h+LockHandle]; LockHandle
0x14002b83d  mov     rdx, rbx; PVOID
0x14002b840  mov     rcx, rsi; P
0x14002b843  call    Smb2AcknowledgeOplockBreakInternal
0x14002b848  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14002b84d  mov     r14d, eax
0x14002b850  lea     rcx, [rsi+70h]; SpinLock
0x14002b854  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002b85b  nop     dword ptr [rax+rax+00h]
0x14002b860  cmp     byte ptr [rsi+11Eh], 0
0x14002b867  jz      loc_14002B94E
0x14002b86d  mov     byte ptr [rsi+11Eh], 0
0x14002b874  test    bpl, bpl
0x14002b877  jz      loc_14002B96E
0x14002b87d  mov     rcx, rsi
0x14002b880  call    Smb2ReferenceFile
0x14002b885  lea     rax, Smb2ProcessOplockBreak
0x14002b88c  mov     byte ptr [rsi+11Dh], 0
0x14002b893  mov     [rsi+30h], rax
0x14002b897  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002b89e  lea     rax, WPP_GLOBAL_Control
0x14002b8a5  cmp     rcx, rax
0x14002b8a8  jz      short loc_14002B8D9
0x14002b8aa  test    dword ptr [rcx+2Ch], 400000h
0x14002b8b1  jz      short loc_14002B8D9
0x14002b8b3  cmp     byte ptr [rcx+29h], 2
0x14002b8b7  jb      short loc_14002B8D9
0x14002b8b9  mov     rcx, [rcx+18h]
0x14002b8bd  lea     r8, WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids
0x14002b8c4  mov     edx, 2Ch ; ','
0x14002b8c9  mov     [rsp+78h+var_58], 0
0x14002b8d1  mov     r9, rsi
0x14002b8d4  call    WPP_SF_qD
0x14002b8d9  cmp     dword ptr [rsi+8], 5
0x14002b8dd  mov     dword ptr [rsi+48h], 0
0x14002b8e4  jnz     short loc_14002B906
0x14002b8e6  lea     rcx, [rsi+248h]
0x14002b8ed  mov     byte ptr [rsp+78h+var_58], 1
0x14002b8f2  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14002b8f9  mov     r8d, 187h
0x14002b8ff  mov     dl, 1
0x14002b901  call    SRV2_PERF_ENTER_EX
0x14002b906  mov     rax, [rsi+40h]
0x14002b90a  mov     rbx, [rax+88h]
0x14002b911  call    cs:__imp_KeGetCurrentNodeNumber
0x14002b918  nop     dword ptr [rax+rax+00h]
0x14002b91d  movzx   eax, ax
0x14002b920  lea     rdx, [rsi+20h]; ListEntry
0x14002b924  mov     rbx, [rbx+rax*8+8]
0x14002b929  mov     rcx, rbx; ListHead
0x14002b92c  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002b933  nop     dword ptr [rax+rax+00h]
0x14002b938  test    rax, rax
0x14002b93b  jnz     short loc_14002B94E
0x14002b93d  movzx   edx, word ptr [rbx+42h]
0x14002b941  cmp     ax, dx
0x14002b944  jz      short loc_14002B94E
0x14002b946  mov     rcx, rbx
0x14002b949  call    RfspThreadPoolNodeWakeIdleWorker
0x14002b94e  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14002b953  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002b95a  nop     dword ptr [rax+rax+00h]
0x14002b95f  mov     eax, r14d
0x14002b962  add     rsp, 50h
0x14002b966  pop     r14
0x14002b968  pop     rdi
0x14002b969  pop     rsi
0x14002b96a  pop     rbp
0x14002b96b  pop     rbx
0x14002b96c  retn
0x14002b96e  mov     rbx, [rsi+108h]
0x14002b975  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14002b97a  mov     qword ptr [rsi+108h], 0
0x14002b985  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002b98c  nop     dword ptr [rax+rax+00h]
0x14002b991  test    rbx, rbx
0x14002b994  jz      short loc_14002B95F
0x14002b996  mov     rcx, rsi; P
0x14002b999  call    Smb2DereferenceFile
0x14002b99e  mov     rcx, [rbx+0A0h]; P
0x14002b9a5  test    rcx, rcx
0x14002b9a8  jz      short loc_14002B9C3
0x14002b9aa  xor     edx, edx; Tag
0x14002b9ac  call    cs:__imp_ExFreePoolWithTag
0x14002b9b3  nop     dword ptr [rax+rax+00h]
0x14002b9b8  mov     qword ptr [rbx+0A0h], 0
0x14002b9c3  mov     rdi, [rbx+8]
0x14002b9c7  test    rdi, rdi
0x14002b9ca  jz      short loc_14002BA0B
0x14002b9cc  test    byte ptr [rdi+0Ah], 4
0x14002b9d0  jnz     short loc_14002BA0B
0x14002b9d2  mov     rsi, rdi
0x14002b9d5  mov     rdi, [rdi]
0x14002b9d8  movzx   eax, word ptr [rsi+0Ah]
0x14002b9dc  test    al, 2
0x14002b9de  jnz     short loc_14002B9E4
0x14002b9e0  test    al, 20h
0x14002b9e2  jz      short loc_14002B9F3
0x14002b9e4  mov     rcx, rsi; MemoryDescriptorList
0x14002b9e7  call    cs:__imp_MmUnlockPages
0x14002b9ee  nop     dword ptr [rax+rax+00h]
0x14002b9f3  mov     rcx, rsi; Mdl
0x14002b9f6  call    cs:__imp_IoFreeMdl
0x14002b9fd  nop     dword ptr [rax+rax+00h]
0x14002ba02  test    rdi, rdi
0x14002ba05  jnz     short loc_14002B9D2
0x14002ba07  mov     [rbx+8], rdi
0x14002ba0b  mov     rcx, rbx; Irp
0x14002ba0e  call    cs:__imp_IoFreeIrp
0x14002ba15  nop     dword ptr [rax+rax+00h]
0x14002ba1a  jmp     loc_14002B95F
```
