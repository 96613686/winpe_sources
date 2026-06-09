# SpCancelAttach(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14003afc0`
- end: `0x14003b0f2`
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
- `0x14003afc0`
- `0x14009df3c`
- `0x1400b55b0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003b047`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b06b`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b047`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b06b`
- `ntoskrnl!ObfReferenceObject` at `0x14003afeb`
- `ntoskrnl!ObfReferenceObject` at `0x14003afeb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b0da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003b0da`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b0ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b0ce`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003afd8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003afd8`
- `ntoskrnl!IofCompleteRequest` at `0x14003b034`
- `ntoskrnl!IofCompleteRequest` at `0x14003b034`

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
      SP_POOL::DetachSpace(v8, SpaceById, 5);
  }
  ExReleaseResourceLite((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14003afc0  mov     [rsp+arg_0], rbx
0x14003afc5  push    rdi
0x14003afc6  sub     rsp, 20h
0x14003afca  mov     rax, [rdx+0B8h]
0x14003afd1  mov     cl, [rdx+45h]; Irql
0x14003afd4  mov     rdi, [rax+8]
0x14003afd8  call    cs:__imp_IoReleaseCancelSpinLock
0x14003afdf  nop     dword ptr [rax+rax+00h]
0x14003afe4  mov     rcx, [rdi+0A0h]; Object
0x14003afeb  call    cs:__imp_ObfReferenceObject
0x14003aff2  nop     dword ptr [rax+rax+00h]
0x14003aff7  mov     rcx, rdi; this
0x14003affa  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x14003afff  lea     rbx, [rdi+0C10h]
0x14003b006  mov     rcx, [rbx]
0x14003b009  cmp     rcx, rbx
0x14003b00c  jz      short loc_14003B05C
0x14003b00e  cmp     [rcx+8], rbx
0x14003b012  jnz     short loc_14003B055
0x14003b014  mov     rax, [rcx]
0x14003b017  cmp     [rax+8], rcx
0x14003b01b  jnz     short loc_14003B055
0x14003b01d  mov     [rbx], rax
0x14003b020  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003b027  mov     [rax+8], rbx
0x14003b02b  xor     edx, edx; PriorityBoost
0x14003b02d  mov     dword ptr [rcx+30h], 0C0000120h
0x14003b034  call    cs:__imp_IofCompleteRequest
0x14003b03b  nop     dword ptr [rax+rax+00h]
0x14003b040  mov     rcx, [rdi+0A0h]; Object
0x14003b047  call    cs:__imp_ObfDereferenceObject
0x14003b04e  nop     dword ptr [rax+rax+00h]
0x14003b053  jmp     short loc_14003B006
0x14003b055  mov     ecx, 3
0x14003b05a  int     29h; Win8: RtlFailFast(ecx)
0x14003b05c  mov     rcx, rdi; this
0x14003b05f  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x14003b064  mov     rcx, [rdi+0A0h]; Object
0x14003b06b  call    cs:__imp_ObfDereferenceObject
0x14003b072  nop     dword ptr [rax+rax+00h]
0x14003b077  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b07e  xor     edx, edx; unsigned __int8
0x14003b080  add     rcx, 60h ; '`'; Resource
0x14003b084  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x14003b089  lea     rcx, [rdi+18h]; struct _GUID *
0x14003b08d  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x14003b092  mov     rbx, rax
0x14003b095  test    rax, rax
0x14003b098  jz      short loc_14003B0C3
0x14003b09a  mov     rcx, [rax+30h]; this
0x14003b09e  lea     rdx, [rdi+28h]; struct _GUID *
0x14003b0a2  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x14003b0a7  test    rax, rax
0x14003b0aa  jz      short loc_14003B0C3
0x14003b0ac  mov     r9d, 0C0000120h
0x14003b0b2  mov     r8d, 5
0x14003b0b8  mov     rdx, rax
0x14003b0bb  mov     rcx, rbx
0x14003b0be  call    ?DetachSpace@SP_POOL@@QEAAXPEAVSDB_RECORD@@W4_SP_SPACE_DETACH_REASON@@J@Z; SP_POOL::DetachSpace(SDB_RECORD *,_SP_SPACE_DETACH_REASON,long)
0x14003b0c3  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003b0ca  add     rcx, 60h ; '`'; Resource
0x14003b0ce  call    cs:__imp_ExReleaseResourceLite
0x14003b0d5  nop     dword ptr [rax+rax+00h]
0x14003b0da  call    cs:__imp_KeLeaveCriticalRegion
0x14003b0e1  nop     dword ptr [rax+rax+00h]
0x14003b0e6  mov     rbx, [rsp+28h+arg_0]
0x14003b0eb  add     rsp, 20h
0x14003b0ef  pop     rdi
0x14003b0f0  retn
```
