# SpPoolRead(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140034470`
- end: `0x140034599`
- name: `?SpPoolRead@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `297`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140032c8c`
- `0x140032e90`
- `0x140034470`
- `0x140035a50`
- `0x140058fa8`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034565`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034565`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140034540`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140034540`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140034519`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140034519`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400344e8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400344e8`
- `ntoskrnl!IofCompleteRequest` at `0x140034579`
- `ntoskrnl!IofCompleteRequest` at `0x140034579`

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
0x140034470  push    rbx
0x140034472  push    rbp
0x140034473  push    rsi
0x140034474  push    rdi
0x140034475  push    r12
0x140034477  push    r13
0x140034479  push    r14
0x14003447b  push    r15
0x14003447d  sub     rsp, 38h
0x140034481  mov     r14, [rcx+40h]
0x140034485  xor     ebx, ebx
0x140034487  mov     rax, [rdx+0B8h]
0x14003448e  mov     rbp, rdx
0x140034491  lea     rcx, [r14+8]; this
0x140034495  mov     r12d, [rax+8]
0x140034499  mov     r13, [rax+18h]
0x14003449d  mov     [rdx+38h], rbx
0x1400344a1  call    ?AcquireRundownSharedNonQueued@SP_POOL_DEVICE@@QEAAJXZ; SP_POOL_DEVICE::AcquireRundownSharedNonQueued(void)
0x1400344a6  mov     edi, eax
0x1400344a8  test    eax, eax
0x1400344aa  js      loc_140034571
0x1400344b0  cmp     [r14+80h], rbx
0x1400344b7  jnz     short loc_1400344C3
0x1400344b9  mov     edi, 0C000000Eh
0x1400344be  jmp     loc_140034561
0x1400344c3  mov     rcx, [rbp+8]; MemoryDescriptorList
0x1400344c7  test    byte ptr [rcx+0Ah], 5
0x1400344cb  jz      short loc_1400344D3
0x1400344cd  mov     r15, [rcx+18h]
0x1400344d1  jmp     short loc_1400344F7
0x1400344d3  xor     r9d, r9d; RequestedAddress
0x1400344d6  mov     [rsp+78h+Priority], 10h; Priority
0x1400344de  xor     edx, edx; AccessMode
0x1400344e0  mov     [rsp+78h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x1400344e4  lea     r8d, [r9+1]; CacheType
0x1400344e8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400344ef  nop     dword ptr [rax+rax+00h]
0x1400344f4  mov     r15, rax
0x1400344f7  lea     rdx, [r14+88h]
0x1400344fe  lea     rcx, [rsp+78h+arg_0]
0x140034506  call    ?acquire_push_lock_shared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_EX_PUSH_LOCK@@P6AXPEAU1@@_E$1?release_push_lock_shared@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_EX_PUSH_LOCK@@@Z
0x14003450b  mov     rdi, [r14+80h]
0x140034512  lea     rsi, [rdi+10h]
0x140034516  mov     rcx, rsi; SpinLock
0x140034519  call    cs:__imp_ExAcquireSpinLockShared
0x140034520  nop     dword ptr [rax+rax+00h]
0x140034525  mov     rcx, [rdi+8]; this
0x140034529  mov     r9, r15; unsigned __int8 *
0x14003452c  mov     r8d, r12d; unsigned int
0x14003452f  mov     rdx, r13; unsigned __int64
0x140034532  mov     bl, al
0x140034534  call    ?Read@SS_BUFFER@@QEAAJ_KKPEAE@Z; SS_BUFFER::Read(unsigned __int64,ulong,uchar *)
0x140034539  mov     dl, bl; OldIrql
0x14003453b  mov     rcx, rsi; SpinLock
0x14003453e  mov     edi, eax
0x140034540  call    cs:__imp_ExReleaseSpinLockShared
0x140034547  nop     dword ptr [rax+rax+00h]
0x14003454c  lea     rcx, [rsp+78h+arg_0]
0x140034554  call    ??1?$unique_storage@U?$resource_policy@PEAU_EX_PUSH_LOCK@@P6AXPEAU1@@_E$1?release_push_lock_shared@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140034559  test    edi, edi
0x14003455b  js      short loc_140034561
0x14003455d  mov     [rbp+38h], r12
0x140034561  mov     rcx, [r14+58h]; RunRefCacheAware
0x140034565  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14003456c  nop     dword ptr [rax+rax+00h]
0x140034571  xor     edx, edx; PriorityBoost
0x140034573  mov     [rbp+30h], edi
0x140034576  mov     rcx, rbp; Irp
0x140034579  call    cs:__imp_IofCompleteRequest
0x140034580  nop     dword ptr [rax+rax+00h]
0x140034585  mov     eax, edi
0x140034587  add     rsp, 38h
0x14003458b  pop     r15
0x14003458d  pop     r14
0x14003458f  pop     r13
0x140034591  pop     r12
0x140034593  pop     rdi
0x140034594  pop     rsi
0x140034595  pop     rbp
0x140034596  pop     rbx
0x140034597  retn
```
