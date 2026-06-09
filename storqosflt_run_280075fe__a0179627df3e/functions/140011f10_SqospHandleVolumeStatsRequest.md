# SqospHandleVolumeStatsRequest

- ea: `0x140011f10`
- end: `0x14001208b`
- name: `SqospHandleVolumeStatsRequest`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012a70`

## callees

- `0x140004340`
- `0x140007938`
- `0x140011f10`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14001204f`
- `ntoskrnl!MmUnlockPages` at `0x14001204f`
- `ntoskrnl!MmProbeAndLockPages` at `0x140011fc5`
- `ntoskrnl!MmProbeAndLockPages` at `0x140011fc5`
- `ntoskrnl!IoAllocateMdl` at `0x140011f94`
- `ntoskrnl!IoAllocateMdl` at `0x140011f94`
- `ntoskrnl!IoFreeMdl` at `0x14001205e`
- `ntoskrnl!IoFreeMdl` at `0x14001205e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011ffd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011ffd`
- `FLTMGR!FltReleaseContext` at `0x140012072`
- `FLTMGR!FltReleaseContext` at `0x140012072`

## pseudocode

```c
__int64 __fastcall SqospHandleVolumeStatsRequest(__int64 a1, unsigned int a2, void *a3, ULONG a4, __int64 a5)
{
  void *DeviceByVolumeId; // rsi
  struct _MDL *v8; // rdi
  unsigned int v9; // ebx
  struct _MDL *Mdl; // rax
  PVOID MappedSystemVa; // rax
  char v13; // [rsp+30h] [rbp-58h]
  _OWORD v14[4]; // [rsp+48h] [rbp-40h] BYREF

  DeviceByVolumeId = 0;
  v8 = 0;
  v13 = 0;
  if ( a2 >= 0x220 )
  {
    if ( a4 >= 0x278 )
    {
      v14[0] = *(_OWORD *)(a1 + 528);
      DeviceByVolumeId = (void *)SqospFindDeviceByVolumeId(v14);
      if ( DeviceByVolumeId )
      {
        Mdl = IoAllocateMdl(a3, a4, 0, 0, 0);
        v8 = Mdl;
        if ( Mdl
          && ((MmProbeAndLockPages(Mdl, 0, IoWriteAccess), v13 = 1, (v8->MdlFlags & 5) == 0)
            ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000010u))
            : (MappedSystemVa = v8->MappedSystemVa),
              MappedSystemVa) )
        {
          v9 = SqospWriteVolumeStats(DeviceByVolumeId, MappedSystemVa, a4, a5);
        }
        else
        {
          v9 = -1073741670;
        }
      }
      else
      {
        v9 = -1073741275;
      }
    }
    else
    {
      v9 = -1073741789;
    }
  }
  else
  {
    v9 = -1073741811;
  }
  if ( v8 )
  {
    if ( v13 )
      MmUnlockPages(v8);
    IoFreeMdl(v8);
  }
  if ( DeviceByVolumeId )
    FltReleaseContext(DeviceByVolumeId);
  return v9;
}

```

## disassembly

```asm
0x140011f10  push    rbx
0x140011f12  push    rsi
0x140011f13  push    rdi
0x140011f14  push    r14
0x140011f16  sub     rsp, 68h
0x140011f1a  mov     ebx, r9d
0x140011f1d  mov     r14, r8
0x140011f20  xor     esi, esi
0x140011f22  mov     [rsp+88h+var_50], rsi
0x140011f27  xor     edi, edi
0x140011f29  mov     [rsp+88h+var_58], sil
0x140011f2e  cmp     edx, 220h
0x140011f34  jnb     short loc_140011F40
0x140011f36  mov     ebx, 0C000000Dh
0x140011f3b  jmp     loc_140012040
0x140011f40  cmp     ebx, 278h
0x140011f46  jnb     short loc_140011F52
0x140011f48  mov     ebx, 0C0000023h
0x140011f4d  jmp     loc_140012040
0x140011f52  movups  xmm0, xmmword ptr [rcx+210h]
0x140011f59  movdqu  [rsp+88h+var_40], xmm0
0x140011f5f  lea     rcx, [rsp+88h+var_40]
0x140011f64  call    SqospFindDeviceByVolumeId
0x140011f69  mov     rsi, rax
0x140011f6c  mov     [rsp+88h+var_50], rax
0x140011f71  test    rax, rax
0x140011f74  jnz     short loc_140011F80
0x140011f76  mov     ebx, 0C0000225h
0x140011f7b  jmp     loc_140012040
0x140011f80  mov     [rsp+88h+Irp], 0; Irp
0x140011f89  xor     r9d, r9d; ChargeQuota
0x140011f8c  xor     r8d, r8d; SecondaryBuffer
0x140011f8f  mov     edx, ebx; Length
0x140011f91  mov     rcx, r14; VirtualAddress
0x140011f94  call    cs:__imp_IoAllocateMdl
0x140011f9b  nop     dword ptr [rax+rax+00h]
0x140011fa0  mov     rdi, rax
0x140011fa3  mov     [rsp+88h+var_48], rax
0x140011fa8  test    rax, rax
0x140011fab  jnz     short loc_140011FB7
0x140011fad  mov     ebx, 0C000009Ah
0x140011fb2  jmp     loc_140012040
0x140011fb7  mov     r14d, 1
0x140011fbd  mov     r8d, r14d; Operation
0x140011fc0  xor     edx, edx; AccessMode
0x140011fc2  mov     rcx, rdi; MemoryDescriptorList
0x140011fc5  call    cs:__imp_MmProbeAndLockPages
0x140011fcc  nop     dword ptr [rax+rax+00h]
0x140011fd1  mov     [rsp+88h+var_58], r14b
0x140011fd6  test    byte ptr [rdi+0Ah], 5
0x140011fda  jz      short loc_140011FE2
0x140011fdc  mov     rax, [rdi+18h]
0x140011fe0  jmp     short loc_140012009
0x140011fe2  mov     [rsp+88h+Priority], 40000010h; Priority
0x140011fea  mov     dword ptr [rsp+88h+Irp], 0; BugCheckOnFailure
0x140011ff2  xor     r9d, r9d; RequestedAddress
0x140011ff5  mov     r8d, r14d; CacheType
0x140011ff8  xor     edx, edx; AccessMode
0x140011ffa  mov     rcx, rdi; MemoryDescriptorList
0x140011ffd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012004  nop     dword ptr [rax+rax+00h]
0x140012009  test    rax, rax
0x14001200c  jz      short loc_140011FAD
0x14001200e  mov     r9, [rsp+88h+arg_20]
0x140012016  mov     r8d, ebx
0x140012019  mov     rdx, rax
0x14001201c  mov     rcx, rsi
0x14001201f  call    SqospWriteVolumeStats
0x140012024  mov     ebx, eax
0x140012026  jmp     short loc_140012040
0x140012028  mov     ebx, eax
0x14001202a  mov     rsi, [rsp+88h+var_50]
0x14001202f  mov     rdi, [rsp+88h+var_48]
0x140012034  jmp     short loc_140012040
0x140012036  mov     ebx, eax
0x140012038  mov     rsi, [rsp+88h+var_50]
0x14001203d  mov     rdi, rsi
0x140012040  test    rdi, rdi
0x140012043  jz      short loc_14001206A
0x140012045  cmp     [rsp+88h+var_58], 0
0x14001204a  jz      short loc_14001205B
0x14001204c  mov     rcx, rdi; MemoryDescriptorList
0x14001204f  call    cs:__imp_MmUnlockPages
0x140012056  nop     dword ptr [rax+rax+00h]
0x14001205b  mov     rcx, rdi; Mdl
0x14001205e  call    cs:__imp_IoFreeMdl
0x140012065  nop     dword ptr [rax+rax+00h]
0x14001206a  test    rsi, rsi
0x14001206d  jz      short loc_14001207E
0x14001206f  mov     rcx, rsi; Context
0x140012072  call    cs:__imp_FltReleaseContext
0x140012079  nop     dword ptr [rax+rax+00h]
0x14001207e  mov     eax, ebx
0x140012080  add     rsp, 68h
0x140012084  pop     r14
0x140012086  pop     rdi
0x140012087  pop     rsi
0x140012088  pop     rbx
0x140012089  retn
```
