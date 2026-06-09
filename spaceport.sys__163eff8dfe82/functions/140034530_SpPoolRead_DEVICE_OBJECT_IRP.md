# SpPoolRead(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140034530`
- end: `0x140034659`
- name: `?SpPoolRead@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `297`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140032d40`
- `0x140032f40`
- `0x140034530`
- `0x140035b10`
- `0x1400590a8`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034625`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034625`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140034600`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140034600`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400345d9`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400345d9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400345a8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400345a8`
- `ntoskrnl!IofCompleteRequest` at `0x140034639`
- `ntoskrnl!IofCompleteRequest` at `0x140034639`

## pseudocode

```c
__int64 __fastcall SpPoolRead(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG_PTR Length; // r12
  unsigned __int64 QuadPart; // r13
  NTSTATUS v7; // edi
  PMDL MdlAddress; // rcx
  unsigned __int8 *MappedSystemVa; // r15
  __int64 v10; // rdi
  KIRQL v11; // bl
  NTSTATUS v12; // eax
  volatile LONG *v13; // rcx
  char v15; // [rsp+80h] [rbp+8h] BYREF

  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Length = CurrentStackLocation->Parameters.Read.Length;
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  a2->IoStatus.Information = 0;
  v7 = SP_POOL_DEVICE::AcquireRundownSharedNonQueued((SP_POOL_DEVICE *)(DeviceExtension + 8));
  if ( v7 >= 0 )
  {
    if ( *((_QWORD *)DeviceExtension + 16) )
    {
      MdlAddress = a2->MdlAddress;
      if ( (MdlAddress->MdlFlags & 5) != 0 )
        MappedSystemVa = (unsigned __int8 *)MdlAddress->MappedSystemVa;
      else
        MappedSystemVa = (unsigned __int8 *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x10u);
      wil::acquire_push_lock_shared(&v15, DeviceExtension + 136);
      v10 = *((_QWORD *)DeviceExtension + 16);
      v11 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)(v10 + 16));
      v12 = SS_BUFFER::Read(*(SS_BUFFER **)(v10 + 8), QuadPart, Length, MappedSystemVa);
      v13 = (volatile LONG *)(v10 + 16);
      v7 = v12;
      ExReleaseSpinLockShared(v13, v11);
      __1__unique_storage_U__resource_policy_PEAU_EX_PUSH_LOCK__P6AXPEAU1___E_1_release_push_lock_shared_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v15);
      if ( v7 >= 0 )
        a2->IoStatus.Information = Length;
    }
    else
    {
      v7 = -1073741810;
    }
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 11));
  }
  a2->IoStatus.Status = v7;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140034530  push    rbx
0x140034532  push    rbp
0x140034533  push    rsi
0x140034534  push    rdi
0x140034535  push    r12
0x140034537  push    r13
0x140034539  push    r14
0x14003453b  push    r15
0x14003453d  sub     rsp, 38h
0x140034541  mov     r14, [rcx+40h]
0x140034545  xor     ebx, ebx
0x140034547  mov     rax, [rdx+0B8h]
0x14003454e  mov     rbp, rdx
0x140034551  lea     rcx, [r14+8]; this
0x140034555  mov     r12d, [rax+8]
0x140034559  mov     r13, [rax+18h]
0x14003455d  mov     [rdx+38h], rbx
0x140034561  call    ?AcquireRundownSharedNonQueued@SP_POOL_DEVICE@@QEAAJXZ; SP_POOL_DEVICE::AcquireRundownSharedNonQueued(void)
0x140034566  mov     edi, eax
0x140034568  test    eax, eax
0x14003456a  js      loc_140034631
0x140034570  cmp     [r14+80h], rbx
0x140034577  jnz     short loc_140034583
0x140034579  mov     edi, 0C000000Eh
0x14003457e  jmp     loc_140034621
0x140034583  mov     rcx, [rbp+8]; MemoryDescriptorList
0x140034587  test    byte ptr [rcx+0Ah], 5
0x14003458b  jz      short loc_140034593
0x14003458d  mov     r15, [rcx+18h]
0x140034591  jmp     short loc_1400345B7
0x140034593  xor     r9d, r9d; RequestedAddress
0x140034596  mov     [rsp+78h+Priority], 10h; Priority
0x14003459e  xor     edx, edx; AccessMode
0x1400345a0  mov     [rsp+78h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x1400345a4  lea     r8d, [r9+1]; CacheType
0x1400345a8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400345af  nop     dword ptr [rax+rax+00h]
0x1400345b4  mov     r15, rax
0x1400345b7  lea     rdx, [r14+88h]
0x1400345be  lea     rcx, [rsp+78h+arg_0]
0x1400345c6  call    ?acquire_push_lock_shared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_EX_PUSH_LOCK@@P6AXPEAU1@@_E$1?release_push_lock_shared@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_EX_PUSH_LOCK@@@Z
0x1400345cb  mov     rdi, [r14+80h]
0x1400345d2  lea     rsi, [rdi+10h]
0x1400345d6  mov     rcx, rsi; SpinLock
0x1400345d9  call    cs:__imp_ExAcquireSpinLockShared
0x1400345e0  nop     dword ptr [rax+rax+00h]
0x1400345e5  mov     rcx, [rdi+8]; this
0x1400345e9  mov     r9, r15; unsigned __int8 *
0x1400345ec  mov     r8d, r12d; unsigned int
0x1400345ef  mov     rdx, r13; unsigned __int64
0x1400345f2  mov     bl, al
0x1400345f4  call    ?Read@SS_BUFFER@@QEAAJ_KKPEAE@Z; SS_BUFFER::Read(unsigned __int64,ulong,uchar *)
0x1400345f9  mov     dl, bl; OldIrql
0x1400345fb  mov     rcx, rsi; SpinLock
0x1400345fe  mov     edi, eax
0x140034600  call    cs:__imp_ExReleaseSpinLockShared
0x140034607  nop     dword ptr [rax+rax+00h]
0x14003460c  lea     rcx, [rsp+78h+arg_0]
0x140034614  call    ??1?$unique_storage@U?$resource_policy@PEAU_EX_PUSH_LOCK@@P6AXPEAU1@@_E$1?release_push_lock_shared@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140034619  test    edi, edi
0x14003461b  js      short loc_140034621
0x14003461d  mov     [rbp+38h], r12
0x140034621  mov     rcx, [r14+58h]; RunRefCacheAware
0x140034625  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14003462c  nop     dword ptr [rax+rax+00h]
0x140034631  xor     edx, edx; PriorityBoost
0x140034633  mov     [rbp+30h], edi
0x140034636  mov     rcx, rbp; Irp
0x140034639  call    cs:__imp_IofCompleteRequest
0x140034640  nop     dword ptr [rax+rax+00h]
0x140034645  mov     eax, edi
0x140034647  add     rsp, 38h
0x14003464b  pop     r15
0x14003464d  pop     r14
0x14003464f  pop     r13
0x140034651  pop     r12
0x140034653  pop     rdi
0x140034654  pop     rsi
0x140034655  pop     rbp
0x140034656  pop     rbx
0x140034657  retn
```
