# SpCancelAttach(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14003b080`
- end: `0x14003b1b2`
- name: `?SpCancelAttach@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `306`
- prototype: `void __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000b3e0`
- `0x14001d3f0`
- `0x1400216f0`
- `0x140021a90`
- `0x14003b080`
- `0x14009df5c`
- `0x1400b5750`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003b107`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b12b`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b107`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b12b`
- `ntoskrnl!ObfReferenceObject` at `0x14003b0ab`
- `ntoskrnl!ObfReferenceObject` at `0x14003b0ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b19a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b19a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b18e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b18e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003b098`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003b098`
- `ntoskrnl!IofCompleteRequest` at `0x14003b0f4`
- `ntoskrnl!IofCompleteRequest` at `0x14003b0f4`

## pseudocode

```c
void __fastcall SpCancelAttach(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  ACCESS_MASK *p_DesiredAccess; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rax
  IRP *v6; // rcx
  struct SP_POOL *PoolById; // rax
  struct SP_POOL *v8; // rbx
  struct SDB_RECORD *SpaceById; // rax

  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  ObfReferenceObject(*(PVOID *)&SecurityContext[6].DesiredAccess);
  SP_DEVICE::AcquireMutex((SP_DEVICE *)SecurityContext);
  p_DesiredAccess = &SecurityContext[128].DesiredAccess;
  while ( 1 )
  {
    v4 = *(_QWORD **)p_DesiredAccess;
    if ( *(ACCESS_MASK **)p_DesiredAccess == p_DesiredAccess )
      break;
    if ( (ACCESS_MASK *)v4[1] != p_DesiredAccess || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
      __fastfail(3u);
    *(_QWORD *)p_DesiredAccess = v5;
    v6 = (IRP *)(v4 - 21);
    v5[1] = p_DesiredAccess;
    v6->IoStatus.Status = -1073741536;
    IofCompleteRequest(v6, 0);
    ObfDereferenceObject(*(PVOID *)&SecurityContext[6].DesiredAccess);
  }
  SP_DEVICE::ReleaseMutex((SP_DEVICE *)SecurityContext);
  ObfDereferenceObject(*(PVOID *)&SecurityContext[6].DesiredAccess);
  SpAcquireResourceShared((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96), 0);
  PoolById = SpFindPoolById((struct _GUID *)&SecurityContext[1]);
  v8 = PoolById;
  if ( PoolById )
  {
    SpaceById = SDB_POOL_CONFIG::FindSpaceById(
                  *((SDB_POOL_CONFIG **)PoolById + 6),
                  (struct _GUID *)&SecurityContext[1].DesiredAccess);
    if ( SpaceById )
      SP_POOL::DetachSpace(v8, SpaceById, 5, 3221225760LL);
  }
  ExReleaseResourceLite((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14003b080  mov     [rsp+arg_0], rbx
0x14003b085  push    rdi
0x14003b086  sub     rsp, 20h
0x14003b08a  mov     rax, [rdx+0B8h]
0x14003b091  mov     cl, [rdx+45h]; Irql
0x14003b094  mov     rdi, [rax+8]
0x14003b098  call    cs:__imp_IoReleaseCancelSpinLock
0x14003b09f  nop     dword ptr [rax+rax+00h]
0x14003b0a4  mov     rcx, [rdi+0A0h]; Object
0x14003b0ab  call    cs:__imp_ObfReferenceObject
0x14003b0b2  nop     dword ptr [rax+rax+00h]
0x14003b0b7  mov     rcx, rdi; this
0x14003b0ba  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x14003b0bf  lea     rbx, [rdi+0C10h]
0x14003b0c6  mov     rcx, [rbx]
0x14003b0c9  cmp     rcx, rbx
0x14003b0cc  jz      short loc_14003B11C
0x14003b0ce  cmp     [rcx+8], rbx
0x14003b0d2  jnz     short loc_14003B115
0x14003b0d4  mov     rax, [rcx]
0x14003b0d7  cmp     [rax+8], rcx
0x14003b0db  jnz     short loc_14003B115
0x14003b0dd  mov     [rbx], rax
0x14003b0e0  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003b0e7  mov     [rax+8], rbx
0x14003b0eb  xor     edx, edx; PriorityBoost
0x14003b0ed  mov     dword ptr [rcx+30h], 0C0000120h
0x14003b0f4  call    cs:__imp_IofCompleteRequest
0x14003b0fb  nop     dword ptr [rax+rax+00h]
0x14003b100  mov     rcx, [rdi+0A0h]; Object
0x14003b107  call    cs:__imp_ObfDereferenceObject
0x14003b10e  nop     dword ptr [rax+rax+00h]
0x14003b113  jmp     short loc_14003B0C6
0x14003b115  mov     ecx, 3
0x14003b11a  int     29h; Win8: RtlFailFast(ecx)
0x14003b11c  mov     rcx, rdi; this
0x14003b11f  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x14003b124  mov     rcx, [rdi+0A0h]; Object
0x14003b12b  call    cs:__imp_ObfDereferenceObject
0x14003b132  nop     dword ptr [rax+rax+00h]
0x14003b137  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b13e  xor     edx, edx; unsigned __int8
0x14003b140  add     rcx, 60h ; '`'; Resource
0x14003b144  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x14003b149  lea     rcx, [rdi+18h]; struct _GUID *
0x14003b14d  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x14003b152  mov     rbx, rax
0x14003b155  test    rax, rax
0x14003b158  jz      short loc_14003B183
0x14003b15a  mov     rcx, [rax+30h]; this
0x14003b15e  lea     rdx, [rdi+28h]; struct _GUID *
0x14003b162  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x14003b167  test    rax, rax
0x14003b16a  jz      short loc_14003B183
0x14003b16c  mov     r9d, 0C0000120h
0x14003b172  mov     r8d, 5
0x14003b178  mov     rdx, rax
0x14003b17b  mov     rcx, rbx
0x14003b17e  call    ?DetachSpace@SP_POOL@@QEAAXPEAVSDB_RECORD@@W4_SP_SPACE_DETACH_REASON@@J@Z; SP_POOL::DetachSpace(SDB_RECORD *,_SP_SPACE_DETACH_REASON,long)
0x14003b183  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b18a  add     rcx, 60h ; '`'; Resource
0x14003b18e  call    cs:__imp_ExReleaseResourceLite
0x14003b195  nop     dword ptr [rax+rax+00h]
0x14003b19a  call    cs:__imp_KeLeaveCriticalRegion
0x14003b1a1  nop     dword ptr [rax+rax+00h]
0x14003b1a6  mov     rbx, [rsp+28h+arg_0]
0x14003b1ab  add     rsp, 20h
0x14003b1af  pop     rdi
0x14003b1b0  retn
```
