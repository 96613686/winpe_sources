# UdfDismountVolume

- ea: `0x140012e94`
- end: `0x140013095`
- name: `UdfDismountVolume`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004b594`

## callees

- `0x1400030e0`
- `0x14000ca10`
- `0x14000ca54`
- `0x140012e94`
- `0x14004ce50`
- `0x140052864`
- `0x140054460`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140013015`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013028`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013015`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013028`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012f4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012f4c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140012fa5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140012fa5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140012fd1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140012fd1`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140012f30`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140012f30`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140012feb`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140012feb`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140013004`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140013004`
- `ntoskrnl!FsRtlDismountComplete` at `0x140013067`
- `ntoskrnl!FsRtlDismountComplete` at `0x140013067`

## pseudocode

```c
__int64 __fastcall UdfDismountVolume(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 v6; // rbx
  unsigned int v7; // edi
  KIRQL Irql; // [rsp+68h] [rbp+10h] BYREF
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Irql = 0;
  v9 = 0;
  if ( (unsigned int)UdfDecodeFileObject(CurrentStackLocation->FileObject, &v10, &v9) == 2 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_q(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        14,
        WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
        *(_QWORD *)(a1 + 16));
    }
    FsRtlNotifyVolumeEvent(CurrentStackLocation->FileObject, 1u);
    *(_DWORD *)(a1 + 28) |= 0x40004u;
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    UdfAcquireResource(a1, v6 + 1480, 0, 0);
    if ( *(_DWORD *)(v6 + 52) == 2 )
    {
      UdfFlushVolume(a1, v6, 0, 1, 1, 1);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 1584));
      if ( *(_DWORD *)(v6 + 52) != 4 )
        *(_DWORD *)(v6 + 52) = 3;
      *(_DWORD *)(v6 + 48) |= 0x1000u;
      *(_QWORD *)(v6 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 1584));
      *(_DWORD *)(v9 + 4) |= 8u;
      IoAcquireVpbSpinLock(&Irql);
      *(_WORD *)(*(_QWORD *)(v6 + 8) + 4LL) |= 0x20u;
      IoReleaseVpbSpinLock(Irql);
      v7 = 0;
    }
    else
    {
      v7 = -1073741202;
    }
    ExReleaseResourceLite((PERESOURCE)(v6 + 1480));
    ExReleaseResourceLite(&Resource);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 15, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    FsRtlDismountComplete(*(_QWORD *)(v6 + 24), v7);
    UdfCompleteRequest((void *)a1, a2, v7);
    return v7;
  }
  else
  {
    UdfCompleteRequest((void *)a1, a2, -1073741811);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140012e94  mov     rax, rsp
0x140012e97  mov     [rax+8], rbx
0x140012e9b  push    rbp
0x140012e9c  push    rsi
0x140012e9d  push    rdi
0x140012e9e  push    r13
0x140012ea0  push    r14
0x140012ea2  sub     rsp, 30h
0x140012ea6  mov     rdi, [rdx+0B8h]
0x140012ead  lea     r8, [rax+18h]
0x140012eb1  mov     byte ptr [rax+10h], 0
0x140012eb5  mov     rbp, rdx
0x140012eb8  mov     rsi, rcx
0x140012ebb  mov     qword ptr [rax+18h], 0
0x140012ec3  lea     rdx, [rax+20h]
0x140012ec7  mov     rcx, [rdi+30h]
0x140012ecb  call    UdfDecodeFileObject
0x140012ed0  cmp     eax, 2
0x140012ed3  jz      short loc_140012EEF
0x140012ed5  mov     ebx, 0C000000Dh
0x140012eda  mov     rdx, rbp
0x140012edd  mov     r8d, ebx
0x140012ee0  mov     rcx, rsi
0x140012ee3  call    UdfCompleteRequest
0x140012ee8  mov     eax, ebx
0x140012eea  jmp     loc_140013083
0x140012eef  mov     rbx, [rsi+10h]
0x140012ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x140012efa  lea     r13, WPP_GLOBAL_Control
0x140012f01  cmp     rcx, r13
0x140012f04  jz      short loc_140012F27
0x140012f06  test    dword ptr [rcx+2Ch], 800h
0x140012f0d  jz      short loc_140012F27
0x140012f0f  mov     rcx, [rcx+18h]
0x140012f13  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x140012f1a  mov     edx, 0Eh
0x140012f1f  mov     r9, rbx
0x140012f22  call    WPP_SF_q
0x140012f27  mov     rcx, [rdi+30h]; FileObject
0x140012f2b  mov     edx, 1; EventCode
0x140012f30  call    cs:__imp_FsRtlNotifyVolumeEvent
0x140012f37  nop     dword ptr [rax+rax+00h]
0x140012f3c  or      dword ptr [rsi+1Ch], 40004h
0x140012f43  lea     rcx, Resource; Resource
0x140012f4a  mov     dl, 1; Wait
0x140012f4c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012f53  nop     dword ptr [rax+rax+00h]
0x140012f58  lea     r14, [rbx+5C8h]
0x140012f5f  xor     r9d, r9d
0x140012f62  mov     rdx, r14
0x140012f65  xor     r8d, r8d
0x140012f68  mov     rcx, rsi
0x140012f6b  call    UdfAcquireResource
0x140012f70  cmp     dword ptr [rbx+34h], 2
0x140012f74  jz      short loc_140012F80
0x140012f76  mov     edi, 0C000026Eh
0x140012f7b  jmp     loc_140013012
0x140012f80  mov     [rsp+58h+var_30], 1; char
0x140012f85  mov     r9b, 1
0x140012f88  xor     r8d, r8d
0x140012f8b  mov     [rsp+58h+var_38], 1; char
0x140012f90  mov     rdx, rbx
0x140012f93  mov     rcx, rsi; int
0x140012f96  call    UdfFlushVolume
0x140012f9b  lea     rdi, [rbx+630h]
0x140012fa2  mov     rcx, rdi; FastMutex
0x140012fa5  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140012fac  nop     dword ptr [rax+rax+00h]
0x140012fb1  cmp     dword ptr [rbx+34h], 4
0x140012fb5  jz      short loc_140012FBE
0x140012fb7  mov     dword ptr [rbx+34h], 3
0x140012fbe  bts     dword ptr [rbx+30h], 0Ch
0x140012fc3  mov     rcx, rdi; FastMutex
0x140012fc6  mov     qword ptr [rbx+668h], 0
0x140012fd1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140012fd8  nop     dword ptr [rax+rax+00h]
0x140012fdd  mov     rax, [rsp+58h+arg_10]
0x140012fe2  lea     rcx, [rsp+58h+Irql]; Irql
0x140012fe7  or      dword ptr [rax+4], 8
0x140012feb  call    cs:__imp_IoAcquireVpbSpinLock
0x140012ff2  nop     dword ptr [rax+rax+00h]
0x140012ff7  mov     rax, [rbx+8]
0x140012ffb  or      word ptr [rax+4], 20h
0x140013000  mov     cl, [rsp+58h+Irql]; Irql
0x140013004  call    cs:__imp_IoReleaseVpbSpinLock
0x14001300b  nop     dword ptr [rax+rax+00h]
0x140013010  xor     edi, edi
0x140013012  mov     rcx, r14; Resource
0x140013015  call    cs:__imp_ExReleaseResourceLite
0x14001301c  nop     dword ptr [rax+rax+00h]
0x140013021  lea     rcx, Resource; Resource
0x140013028  call    cs:__imp_ExReleaseResourceLite
0x14001302f  nop     dword ptr [rax+rax+00h]
0x140013034  mov     rcx, cs:WPP_GLOBAL_Control
0x14001303b  cmp     rcx, r13
0x14001303e  jz      short loc_140013061
0x140013040  test    dword ptr [rcx+2Ch], 800h
0x140013047  jz      short loc_140013061
0x140013049  mov     rcx, [rcx+18h]
0x14001304d  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x140013054  mov     edx, 0Fh
0x140013059  mov     r9d, edi
0x14001305c  call    WPP_SF_d
0x140013061  mov     rcx, [rbx+18h]
0x140013065  mov     edx, edi
0x140013067  call    cs:__imp_FsRtlDismountComplete
0x14001306e  nop     dword ptr [rax+rax+00h]
0x140013073  mov     r8d, edi
0x140013076  mov     rdx, rbp
0x140013079  mov     rcx, rsi
0x14001307c  call    UdfCompleteRequest
0x140013081  mov     eax, edi
0x140013083  mov     rbx, [rsp+58h+arg_0]
0x140013088  add     rsp, 30h
0x14001308c  pop     r14
0x14001308e  pop     r13
0x140013090  pop     rdi
0x140013091  pop     rsi
0x140013092  pop     rbp
0x140013093  retn
```
