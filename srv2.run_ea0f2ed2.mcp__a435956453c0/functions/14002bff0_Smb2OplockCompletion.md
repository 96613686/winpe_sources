# Smb2OplockCompletion

- ea: `0x14002bff0`
- end: `0x14002c356`
- name: `Smb2OplockCompletion`
- size: `870`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140004960`
- `0x140005070`
- `0x140012790`
- `0x140012ca0`
- `0x1400222ec`
- `0x1400225c4`
- `0x140022958`
- `0x14002bff0`
- `0x14002d240`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002c322`
- `ntoskrnl!IoFreeMdl` at `0x14002c322`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002c1af`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002c1af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c2d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c2d8`
- `ntoskrnl!IoFreeIrp` at `0x14002c33a`
- `ntoskrnl!IoFreeIrp` at `0x14002c33a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002c1ca`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002c1ca`
- `ntoskrnl!MmUnlockPages` at `0x14002c313`
- `ntoskrnl!MmUnlockPages` at `0x14002c313`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002c018`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002c018`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002c11b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002c23b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002c11b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002c23b`

## string_xrefs

- `0x14002c190`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2OplockCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v5; // r8
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rdx
  bool v10; // dl
  __int64 v11; // rax
  bool v12; // zf
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // eax
  PCHAR AuxiliaryBuffer; // rcx
  PMDL MdlAddress; // rbx
  struct _MDL *v19; // rdi
  CSHORT MdlFlags; // ax
  int v22; // [rsp+20h] [rbp-68h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a3 + 112), &LockHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDdd(
      WPP_GLOBAL_Control->AttachedDevice,
      32,
      v5,
      a3,
      a2->IoStatus.Status,
      *(_DWORD *)(a3 + 12),
      *(_DWORD *)(a3 + 280));
  }
  if ( a2->IoStatus.Status >= 0 )
  {
    v6 = *(_DWORD *)(a3 + 12);
    if ( v6 != 221 && v6 != 227 )
    {
      v7 = *(_DWORD *)(a3 + 280);
      if ( v7 == 2 )
      {
        *(_DWORD *)(a3 + 280) = 3;
        v8 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 460), 1u);
        if ( (unsigned int)v8 < 0x10 )
        {
          *(_DWORD *)(a3 + 4 * v8 + 464) = 3;
          *(_DWORD *)(a3 + 4 * v8 + 528) = 1853;
        }
      }
      else if ( v7 == 1 )
      {
        *(_DWORD *)(a3 + 280) = 3;
        v11 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 460), 1u);
        if ( (unsigned int)v11 < 0x10 )
        {
          *(_DWORD *)(a3 + 4 * v11 + 464) = 3;
          *(_DWORD *)(a3 + 4 * v11 + 528) = 1866;
        }
        *(_BYTE *)(a3 + 286) = 1;
        goto LABEL_18;
      }
      Smb2ReferenceFile(a3);
      v10 = a2->IoStatus.Information == 7 && !*(_BYTE *)(a3 + 236);
      *(_BYTE *)(a3 + 285) = v10;
      *(_QWORD *)(a3 + 48) = Smb2ProcessOplockBreak;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 35, &WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids, a3, v10);
      }
      v12 = *(_DWORD *)(a3 + 8) == 5;
      *(_DWORD *)(a3 + 72) = 0;
      if ( v12 )
      {
        LOBYTE(v22) = 1;
        LOBYTE(v9) = 1;
        SRV2_PERF_ENTER_EX(a3 + 584, v9, 391, "Srv2PostToThreadPool", v22);
      }
      v13 = *(_QWORD *)(*(_QWORD *)(a3 + 64) + 136LL);
      v14 = *(_QWORD *)(v13 + 8LL * KeGetCurrentNodeNumber() + 8);
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v14, (PSLIST_ENTRY)(a3 + 32)) && *(_WORD *)(v14 + 66) )
        RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v14);
LABEL_18:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      return 3221225494LL;
    }
  }
  *(_QWORD *)(a3 + 264) = 0;
  *(_DWORD *)(a3 + 280) = 0;
  v15 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 460), 1u);
  if ( (unsigned int)v15 < 0x10 )
  {
    *(_DWORD *)(a3 + 4 * v15 + 464) = 0;
    *(_DWORD *)(a3 + 4 * v15 + 528) = 1819;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v16 = *(_DWORD *)(a3 + 12);
  if ( v16 == 221 || v16 == 227 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, &WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids, a3);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      &WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids,
      (unsigned int)a2->IoStatus.Status,
      a3);
  }
  Smb2DereferenceFile((PVOID)a3);
  AuxiliaryBuffer = a2->Tail.Overlay.AuxiliaryBuffer;
  if ( AuxiliaryBuffer )
  {
    ExFreePoolWithTag(AuxiliaryBuffer, 0);
    a2->Tail.Overlay.AuxiliaryBuffer = 0;
  }
  MdlAddress = a2->MdlAddress;
  if ( MdlAddress && (MdlAddress->MdlFlags & 4) == 0 )
  {
    do
    {
      v19 = MdlAddress;
      MdlAddress = MdlAddress->Next;
      MdlFlags = v19->MdlFlags;
      if ( (MdlFlags & 2) != 0 || (MdlFlags & 0x20) != 0 )
        MmUnlockPages(v19);
      IoFreeMdl(v19);
    }
    while ( MdlAddress );
    a2->MdlAddress = 0;
  }
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14002bff0  push    rbx
0x14002bff2  push    rsi
0x14002bff3  push    rdi
0x14002bff4  push    r12
0x14002bff6  sub     rsp, 68h
0x14002bffa  mov     rsi, rdx
0x14002bffd  lea     rcx, [r8+70h]; SpinLock
0x14002c001  xorps   xmm0, xmm0
0x14002c004  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14002c009  xor     eax, eax
0x14002c00b  mov     rdi, r8
0x14002c00e  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14002c013  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14002c018  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002c01f  nop     dword ptr [rax+rax+00h]
0x14002c024  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c02b  lea     r12, WPP_GLOBAL_Control
0x14002c032  cmp     rcx, r12
0x14002c035  jz      short loc_14002C06D
0x14002c037  bt      dword ptr [rcx+2Ch], 16h
0x14002c03c  jnb     short loc_14002C06D
0x14002c03e  cmp     byte ptr [rcx+29h], 2
0x14002c042  jb      short loc_14002C06D
0x14002c044  mov     eax, [rdi+118h]
0x14002c04a  mov     edx, 20h ; ' '
0x14002c04f  mov     rcx, [rcx+18h]
0x14002c053  mov     r9, rdi
0x14002c056  mov     [rsp+88h+var_58], eax
0x14002c05a  mov     eax, [rdi+0Ch]
0x14002c05d  mov     [rsp+88h+var_60], eax
0x14002c061  mov     eax, [rsi+30h]
0x14002c064  mov     dword ptr [rsp+88h+var_68], eax
0x14002c068  call    WPP_SF_qDdd
0x14002c06d  cmp     dword ptr [rsi+30h], 0
0x14002c071  jl      loc_14002C1F9
0x14002c077  mov     eax, [rdi+0Ch]
0x14002c07a  cmp     eax, 0DDh
0x14002c07f  jz      loc_14002C1F9
0x14002c085  cmp     eax, 0E3h
0x14002c08a  jz      loc_14002C1F9
0x14002c090  mov     eax, [rdi+118h]
0x14002c096  cmp     eax, 2
0x14002c099  jnz     short loc_14002C0E2
0x14002c09b  lea     ecx, [rax+1]
0x14002c09e  mov     [rdi+118h], ecx
0x14002c0a4  lea     eax, [rcx-2]
0x14002c0a7  lock xadd [rdi+1CCh], eax
0x14002c0af  cmp     eax, 10h
0x14002c0b2  jnb     short loc_14002C0C6
0x14002c0b4  mov     [rdi+rax*4+1D0h], ecx
0x14002c0bb  mov     dword ptr [rdi+rax*4+210h], 73Dh
0x14002c0c6  mov     rcx, rdi
0x14002c0c9  call    Smb2ReferenceFile
0x14002c0ce  cmp     qword ptr [rsi+38h], 7
0x14002c0d3  jnz     short loc_14002C12C
0x14002c0d5  cmp     byte ptr [rdi+0ECh], 0
0x14002c0dc  jnz     short loc_14002C12C
0x14002c0de  mov     dl, 1
0x14002c0e0  jmp     short loc_14002C12E
0x14002c0e2  cmp     eax, 1
0x14002c0e5  jnz     short loc_14002C0C6
0x14002c0e7  lea     ecx, [rax+2]
0x14002c0ea  mov     [rdi+118h], ecx
0x14002c0f0  lock xadd [rdi+1CCh], eax
0x14002c0f8  cmp     eax, 10h
0x14002c0fb  jnb     short loc_14002C10F
0x14002c0fd  mov     [rdi+rax*4+1D0h], ecx
0x14002c104  mov     dword ptr [rdi+rax*4+210h], 74Ah
0x14002c10f  mov     byte ptr [rdi+11Eh], 1
0x14002c116  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14002c11b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002c122  nop     dword ptr [rax+rax+00h]
0x14002c127  jmp     loc_14002C346
0x14002c12c  xor     dl, dl
0x14002c12e  lea     rax, Smb2ProcessOplockBreak
0x14002c135  mov     [rdi+11Dh], dl
0x14002c13b  mov     [rdi+30h], rax
0x14002c13f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c146  cmp     rcx, r12
0x14002c149  jz      short loc_14002C177
0x14002c14b  bt      dword ptr [rcx+2Ch], 16h
0x14002c150  jnb     short loc_14002C177
0x14002c152  cmp     byte ptr [rcx+29h], 2
0x14002c156  jb      short loc_14002C177
0x14002c158  mov     rcx, [rcx+18h]
0x14002c15c  lea     r8, WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids
0x14002c163  movzx   eax, dl
0x14002c166  mov     r9, rdi
0x14002c169  mov     edx, 23h ; '#'
0x14002c16e  mov     dword ptr [rsp+88h+var_68], eax
0x14002c172  call    WPP_SF_qD
0x14002c177  cmp     dword ptr [rdi+8], 5
0x14002c17b  mov     dword ptr [rdi+48h], 0
0x14002c182  jnz     short loc_14002C1A4
0x14002c184  lea     rcx, [rdi+248h]
0x14002c18b  mov     byte ptr [rsp+88h+var_68], 1
0x14002c190  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14002c197  mov     r8d, 187h
0x14002c19d  mov     dl, 1
0x14002c19f  call    SRV2_PERF_ENTER_EX
0x14002c1a4  mov     rax, [rdi+40h]
0x14002c1a8  mov     rbx, [rax+88h]
0x14002c1af  call    cs:__imp_KeGetCurrentNodeNumber
0x14002c1b6  nop     dword ptr [rax+rax+00h]
0x14002c1bb  movzx   eax, ax
0x14002c1be  lea     rdx, [rdi+20h]; ListEntry
0x14002c1c2  mov     rbx, [rbx+rax*8+8]
0x14002c1c7  mov     rcx, rbx; ListHead
0x14002c1ca  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002c1d1  nop     dword ptr [rax+rax+00h]
0x14002c1d6  test    rax, rax
0x14002c1d9  jnz     loc_14002C116
0x14002c1df  movzx   edx, word ptr [rbx+42h]
0x14002c1e3  cmp     ax, dx
0x14002c1e6  jz      loc_14002C116
0x14002c1ec  mov     rcx, rbx
0x14002c1ef  call    RfspThreadPoolNodeWakeIdleWorker
0x14002c1f4  jmp     loc_14002C116
0x14002c1f9  mov     qword ptr [rdi+108h], 0
0x14002c204  mov     eax, 1
0x14002c209  mov     dword ptr [rdi+118h], 0
0x14002c213  lock xadd [rdi+1CCh], eax
0x14002c21b  cmp     eax, 10h
0x14002c21e  jnb     short loc_14002C236
0x14002c220  mov     dword ptr [rdi+rax*4+1D0h], 0
0x14002c22b  mov     dword ptr [rdi+rax*4+210h], 71Bh
0x14002c236  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14002c23b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002c242  nop     dword ptr [rax+rax+00h]
0x14002c247  mov     eax, [rdi+0Ch]
0x14002c24a  cmp     eax, 0DDh
0x14002c24f  jz      short loc_14002C291
0x14002c251  cmp     eax, 0E3h
0x14002c256  jz      short loc_14002C291
0x14002c258  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c25f  cmp     rcx, r12
0x14002c262  jz      short loc_14002C2C2
0x14002c264  bt      dword ptr [rcx+2Ch], 16h
0x14002c269  jnb     short loc_14002C2C2
0x14002c26b  cmp     byte ptr [rcx+29h], 1
0x14002c26f  jb      short loc_14002C2C2
0x14002c271  mov     r9d, [rsi+30h]
0x14002c275  lea     r8, WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids
0x14002c27c  mov     rcx, [rcx+18h]
0x14002c280  mov     edx, 22h ; '"'
0x14002c285  mov     [rsp+88h+var_68], rdi
0x14002c28a  call    WPP_SF_dq
0x14002c28f  jmp     short loc_14002C2C2
0x14002c291  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c298  cmp     rcx, r12
0x14002c29b  jz      short loc_14002C2C2
0x14002c29d  bt      dword ptr [rcx+2Ch], 16h
0x14002c2a2  jnb     short loc_14002C2C2
0x14002c2a4  cmp     byte ptr [rcx+29h], 1
0x14002c2a8  jb      short loc_14002C2C2
0x14002c2aa  mov     rcx, [rcx+18h]
0x14002c2ae  lea     r8, WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids
0x14002c2b5  mov     edx, 21h ; '!'
0x14002c2ba  mov     r9, rdi
0x14002c2bd  call    WPP_SF_q
0x14002c2c2  mov     rcx, rdi; P
0x14002c2c5  call    Smb2DereferenceFile
0x14002c2ca  mov     rcx, [rsi+0A0h]; P
0x14002c2d1  test    rcx, rcx
0x14002c2d4  jz      short loc_14002C2EF
0x14002c2d6  xor     edx, edx; Tag
0x14002c2d8  call    cs:__imp_ExFreePoolWithTag
0x14002c2df  nop     dword ptr [rax+rax+00h]
0x14002c2e4  mov     qword ptr [rsi+0A0h], 0
0x14002c2ef  mov     rbx, [rsi+8]
0x14002c2f3  test    rbx, rbx
0x14002c2f6  jz      short loc_14002C337
0x14002c2f8  test    byte ptr [rbx+0Ah], 4
0x14002c2fc  jnz     short loc_14002C337
0x14002c2fe  mov     rdi, rbx
0x14002c301  mov     rbx, [rbx]
0x14002c304  movzx   eax, word ptr [rdi+0Ah]
0x14002c308  test    al, 2
0x14002c30a  jnz     short loc_14002C310
0x14002c30c  test    al, 20h
0x14002c30e  jz      short loc_14002C31F
0x14002c310  mov     rcx, rdi; MemoryDescriptorList
0x14002c313  call    cs:__imp_MmUnlockPages
0x14002c31a  nop     dword ptr [rax+rax+00h]
0x14002c31f  mov     rcx, rdi; Mdl
0x14002c322  call    cs:__imp_IoFreeMdl
0x14002c329  nop     dword ptr [rax+rax+00h]
0x14002c32e  test    rbx, rbx
0x14002c331  jnz     short loc_14002C2FE
0x14002c333  mov     [rsi+8], rbx
0x14002c337  mov     rcx, rsi; Irp
0x14002c33a  call    cs:__imp_IoFreeIrp
0x14002c341  nop     dword ptr [rax+rax+00h]
0x14002c346  mov     eax, 0C0000016h
0x14002c34b  add     rsp, 68h
0x14002c34f  pop     r12
0x14002c351  pop     rdi
0x14002c352  pop     rsi
0x14002c353  pop     rbx
0x14002c354  retn
```
