# SpRepairSpaceCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x1400a0b40`
- end: `0x1400a0f33`
- name: `?SpRepairSpaceCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `1011`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140011970`
- `0x140015dd0`
- `0x14001d3f0`
- `0x14001e160`
- `0x14001e4a0`
- `0x14001eac0`
- `0x1400216f0`
- `0x140021a90`
- `0x140027010`
- `0x1400398a8`
- `0x1400428dc`
- `0x1400430ac`
- `0x140043250`
- `0x140047138`
- `0x140068110`
- `0x140068600`
- `0x14008f2f8`
- `0x14008f438`
- `0x14009cfb4`
- `0x1400a0b40`
- `0x1400aa6e0`
- `0x1400aa914`
- `0x1400ac558`
- `0x1400ac6e4`
- `0x1400ac920`
- `0x1400af5a8`
- `0x1400b58c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400a0d15`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a0d15`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400a0e22`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400a0e22`

## pseudocode

```c
__int64 __fastcall SpRepairSpaceCallback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  void *v5; // r14
  int v6; // r12d
  char *v7; // rbx
  int i; // edi
  int v9; // eax
  __int64 v10; // r8
  int v11; // esi
  SP_DEVICE *v12; // rcx
  char v13; // r15
  struct SP_SPACE *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rcx
  _QWORD *Shared; // rax
  __int64 v18; // r8
  char v19; // si
  int j; // edi
  SP_DEVICE *v21; // rcx
  SIO_CACHE *v22; // rcx
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  void *v25; // [rsp+38h] [rbp-C8h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v27; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[96]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v29[32]; // [rsp+C0h] [rbp-40h] BYREF

  v24 = 0;
  v29[0] = 3;
  memset(&v29[1], 0, 0x70u);
  v5 = 0;
  v25 = 0;
  v6 = 0;
  SP_WORK::SP_WORK((SP_WORK *)v28);
  v7 = (char *)a1->DeviceExtension + 8;
  Interval.QuadPart = 0;
  SP_WORK::RebalanceMetadata((SP_WORK *)v28, (struct _SP_ID *)(v7 + 24));
  for ( i = 0; ; ++i )
  {
    v9 = SP_DEVICE::AcquireRundownSharedNonQueued((PEX_RUNDOWN_REF_CACHE_AWARE *)v7);
    if ( i >= 7 )
      break;
    v11 = v9;
    if ( v9 < 0 )
      goto LABEL_49;
    LOBYTE(v10) = 1;
    v13 = SIO_SPACE::NeedRepair(*((_QWORD *)v7 + 403), (unsigned int)i, v10);
    if ( v13 && !*((_QWORD *)v7 + 385) )
    {
      v14 = (struct SP_SPACE *)*((_QWORD *)v7 + 403);
      *((_QWORD *)v7 + 385) = MEMORY[0xFFFFF78000000014];
      SP_DEVICE::CollectHealthChangeTelemetry(v12, 1u, v14);
      SP_DEVICE::CollectRepairStateTelemetry(v7, 1);
    }
    SP_DEVICE::ReleaseRundownShared((SP_DEVICE *)v7);
    if ( !v13 )
      continue;
    if ( i )
    {
      switch ( i )
      {
        case 1:
          goto LABEL_21;
        case 2:
          goto LABEL_16;
        case 3:
        case 4:
          goto LABEL_21;
        case 5:
LABEL_16:
          SP_DEVICE::AcquireMutex((SP_DEVICE *)v7);
          v15 = *((_QWORD *)v7 + 403);
          if ( !v15 )
            goto LABEL_34;
          if ( (int)SIO_SPACE::GetRepairWork(v15, (unsigned int)i, &v25, &v24) < 0 )
          {
            v5 = v25;
LABEL_34:
            SP_DEVICE::ReleaseMutex((SP_DEVICE *)v7);
            if ( v5 )
              SC_ENV_ALLOCATOR::operator delete[](v5);
            goto LABEL_49;
          }
          SP_DEVICE::ReleaseMutex((SP_DEVICE *)v7);
          v6 = SP_WORK::RepairSpace((SP_WORK *)v28, (struct _SP_ID *)(v7 + 24), v25, v24);
          SC_ENV_ALLOCATOR::operator delete[](v25);
          v5 = 0;
          v25 = 0;
          if ( v6 >= 0 )
          {
            v27 = *(struct _GUID *)(v7 + 24);
            SpRefreshPoolWork(&v27);
            KeWaitForSingleObject((char *)WPP_MAIN_CB.DeviceExtension + 952, Executive, 0, 0, 0);
          }
          break;
        case 6:
LABEL_21:
          if ( i == 3 )
          {
            v11 = SP_DEVICE::AcquireRundownSharedNonQueued((PEX_RUNDOWN_REF_CACHE_AWARE *)v7);
            if ( v11 < 0 )
              goto LABEL_49;
            SIO_SPACE::LostClear(*((SIO_SPACE **)v7 + 403));
            SP_DEVICE::ReleaseRundownShared((SP_DEVICE *)v7);
          }
          SpAcquireResourceShared((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96), 0);
          SP_DEVICE::AcquireMutex((SP_DEVICE *)v7);
          v16 = *((_QWORD *)v7 + 403);
          if ( v16 )
            v6 = SP_SPACE::Repair(v16, (unsigned int)i);
          else
            v11 = -1073741632;
          SP_DEVICE::ReleaseMutex((SP_DEVICE *)v7);
          SpReleaseResourceShared((struct _ERESOURCE *)((char *)WPP_MAIN_CB.DeviceExtension + 96));
          if ( v11 == -1073741632 )
            goto LABEL_49;
          if ( i == 3 )
            SP_WORK::ScopeRegeneration((SP_WORK *)v28, (struct _SP_ID *)(v7 + 24));
          break;
      }
    }
    else if ( SP_WORKITEM::IsTimeout((SP_WORKITEM *)(v7 + 2864)) )
    {
      goto LABEL_21;
    }
    if ( (int)SP_DEVICE::AcquireRundownSharedNonQueued((PEX_RUNDOWN_REF_CACHE_AWARE *)v7) < 0 )
      goto LABEL_49;
    Shared = SIO_COUNTERS::GetShared((SIO_COUNTERS *)(*((_QWORD *)v7 + 403) + 160LL));
    ++Shared[i + 49];
    *((_DWORD *)Shared + i + 112) = v6;
    SP_DEVICE::ReleaseRundownShared((SP_DEVICE *)v7);
    Interval.QuadPart = -50000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  if ( v9 >= 0 )
  {
    SP_SPACE::GetHealth(*((SP_SPACE **)v7 + 403), (struct _SIO_HEALTH_CONTEXT *)v29);
    v19 = 0;
    for ( j = 1; j < 7; ++j )
    {
      LOBYTE(v18) = 1;
      if ( (unsigned __int8)SIO_SPACE::NeedRepair(*((_QWORD *)v7 + 403), (unsigned int)j, v18) )
      {
        v19 = 1;
        break;
      }
    }
    SP_DEVICE::CollectRepairStateTelemetry(v7, 2);
    if ( v29[0] != 3 || v19 )
    {
      SP_WORKITEM::Insert(v7 + 2864, 0, 0x493E0u, 0);
    }
    else if ( *((_QWORD *)v7 + 385) )
    {
      SP_DEVICE::CollectHealthChangeTelemetry(v21, 0, *((struct SP_SPACE **)v7 + 403));
      v22 = (SIO_CACHE *)*((_QWORD *)v7 + 17);
      *((_QWORD *)v7 + 385) = 0;
      if ( v22 )
        SIO_CACHE::OnCommit(v22);
    }
    SP_DEVICE::ReleaseRundownShared((SP_DEVICE *)v7);
  }
LABEL_49:
  SP_WORK::~SP_WORK((SP_WORK *)v28);
  return 0;
}

```

## disassembly

```asm
0x1400a0b40  push    rbp
0x1400a0b42  push    rbx
0x1400a0b43  push    rsi
0x1400a0b44  push    rdi
0x1400a0b45  push    r12
0x1400a0b47  push    r13
0x1400a0b49  push    r14
0x1400a0b4b  push    r15
0x1400a0b4d  lea     rbp, [rsp-58h]
0x1400a0b52  sub     rsp, 158h
0x1400a0b59  mov     rax, cs:__security_cookie
0x1400a0b60  xor     rax, rsp
0x1400a0b63  mov     [rbp+90h+var_50], rax
0x1400a0b67  xor     edx, edx; Val
0x1400a0b69  mov     [rsp+190h+var_160], 0
0x1400a0b71  mov     rbx, rcx
0x1400a0b74  mov     [rbp+90h+var_D0], 3
0x1400a0b7b  lea     rcx, [rbp+90h+var_CC]; void *
0x1400a0b7f  lea     r8d, [rdx+70h]; Size
0x1400a0b83  call    memset
0x1400a0b88  xor     r14d, r14d
0x1400a0b8b  lea     rcx, [rsp+190h+var_130]; this
0x1400a0b90  mov     [rsp+190h+var_158], r14
0x1400a0b95  xor     r12d, r12d
0x1400a0b98  call    ??0SP_WORK@@QEAA@XZ; SP_WORK::SP_WORK(void)
0x1400a0b9d  mov     rbx, [rbx+40h]
0x1400a0ba1  lea     rcx, [rsp+190h+var_130]; this
0x1400a0ba6  add     rbx, 8
0x1400a0baa  mov     qword ptr [rsp+190h+Interval], r12
0x1400a0baf  lea     r13, [rbx+18h]
0x1400a0bb3  mov     rdx, r13; struct _SP_ID *
0x1400a0bb6  call    ?RebalanceMetadata@SP_WORK@@QEAAJPEAU_SP_ID@@@Z; SP_WORK::RebalanceMetadata(_SP_ID *)
0x1400a0bbb  xor     edi, edi
0x1400a0bbd  mov     rcx, rbx; this
0x1400a0bc0  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x1400a0bc5  cmp     edi, 7
0x1400a0bc8  jge     loc_1400A0E58
0x1400a0bce  mov     esi, eax
0x1400a0bd0  test    eax, eax
0x1400a0bd2  js      loc_1400A0F06
0x1400a0bd8  mov     rcx, [rbx+0C98h]
0x1400a0bdf  mov     r8b, 1
0x1400a0be2  mov     edx, edi
0x1400a0be4  call    ?NeedRepair@SIO_SPACE@@QEAAEW4_SC_REPAIR_PHASE@@E@Z; SIO_SPACE::NeedRepair(_SC_REPAIR_PHASE,uchar)
0x1400a0be9  mov     r15b, al
0x1400a0bec  test    al, al
0x1400a0bee  jz      short loc_1400A0C29
0x1400a0bf0  cmp     qword ptr [rbx+0C08h], 0
0x1400a0bf8  jnz     short loc_1400A0C29
0x1400a0bfa  mov     rax, 0FFFFF78000000014h
0x1400a0c04  mov     dl, 1; unsigned __int8
0x1400a0c06  mov     rax, [rax]
0x1400a0c09  mov     r8, [rbx+0C98h]; struct SP_SPACE *
0x1400a0c10  mov     [rbx+0C08h], rax
0x1400a0c17  call    ?CollectHealthChangeTelemetry@SP_DEVICE@@QEAAXEPEAVSP_SPACE@@@Z; SP_DEVICE::CollectHealthChangeTelemetry(uchar,SP_SPACE *)
0x1400a0c1c  mov     edx, 1
0x1400a0c21  mov     rcx, rbx
0x1400a0c24  call    ?CollectRepairStateTelemetry@SP_DEVICE@@QEAAXW4_SP_REPAIR_COUNTERS_ENTRY_POINT@@@Z; SP_DEVICE::CollectRepairStateTelemetry(_SP_REPAIR_COUNTERS_ENTRY_POINT)
0x1400a0c29  mov     rcx, rbx; this
0x1400a0c2c  call    ?ReleaseRundownShared@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownShared(void)
0x1400a0c31  test    r15b, r15b
0x1400a0c34  jz      loc_1400A0E2E
0x1400a0c3a  mov     ecx, edi
0x1400a0c3c  test    edi, edi
0x1400a0c3e  jz      loc_1400A0D26
0x1400a0c44  sub     ecx, 1
0x1400a0c47  jz      loc_1400A0D3A
0x1400a0c4d  sub     ecx, 1
0x1400a0c50  jz      short loc_1400A0C77
0x1400a0c52  sub     ecx, 1
0x1400a0c55  jz      loc_1400A0D3A
0x1400a0c5b  sub     ecx, 1
0x1400a0c5e  jz      loc_1400A0D3A
0x1400a0c64  sub     ecx, 1
0x1400a0c67  jz      short loc_1400A0C77
0x1400a0c69  cmp     ecx, 1
0x1400a0c6c  jz      loc_1400A0D3A
0x1400a0c72  jmp     loc_1400A0DD2
0x1400a0c77  mov     rcx, rbx; this
0x1400a0c7a  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x1400a0c7f  mov     rcx, [rbx+0C98h]
0x1400a0c86  test    rcx, rcx
0x1400a0c89  jz      loc_1400A0E3A
0x1400a0c8f  lea     r9, [rsp+190h+var_160]
0x1400a0c94  mov     edx, edi
0x1400a0c96  lea     r8, [rsp+190h+var_158]
0x1400a0c9b  call    ?GetRepairWork@SIO_SPACE@@QEAAJW4_SC_REPAIR_PHASE@@PEAPEAVSP_REPAIR_WORK@@PEAK@Z; SIO_SPACE::GetRepairWork(_SC_REPAIR_PHASE,SP_REPAIR_WORK * *,ulong *)
0x1400a0ca0  test    eax, eax
0x1400a0ca2  js      loc_1400A0E35
0x1400a0ca8  mov     rcx, rbx; this
0x1400a0cab  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x1400a0cb0  mov     r9d, [rsp+190h+var_160]; unsigned int
0x1400a0cb5  lea     rcx, [rsp+190h+var_130]; this
0x1400a0cba  mov     r8, [rsp+190h+var_158]; void *
0x1400a0cbf  mov     rdx, r13; struct _SP_ID *
0x1400a0cc2  call    ?RepairSpace@SP_WORK@@QEAAJPEAU_SP_ID@@PEAXK@Z; SP_WORK::RepairSpace(_SP_ID *,void *,ulong)
0x1400a0cc7  mov     rcx, [rsp+190h+var_158]; void *
0x1400a0ccc  mov     r12d, eax
0x1400a0ccf  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a0cd4  xor     r14d, r14d
0x1400a0cd7  mov     [rsp+190h+var_158], r14
0x1400a0cdc  test    r12d, r12d
0x1400a0cdf  js      loc_1400A0DD2
0x1400a0ce5  movups  xmm0, xmmword ptr [r13+0]
0x1400a0cea  lea     rcx, [rsp+190h+var_140]; struct _GUID *
0x1400a0cef  movdqu  xmmword ptr [rsp+190h+var_140.Data1], xmm0
0x1400a0cf5  call    ?SpRefreshPoolWork@@YAJU_GUID@@@Z; SpRefreshPoolWork(_GUID)
0x1400a0cfa  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a0d01  xor     r9d, r9d; Alertable
0x1400a0d04  add     rcx, 3B8h; Object
0x1400a0d0b  mov     [rsp+190h+Timeout], r14; Timeout
0x1400a0d10  xor     r8d, r8d; WaitMode
0x1400a0d13  xor     edx, edx; WaitReason
0x1400a0d15  call    cs:__imp_KeWaitForSingleObject
0x1400a0d1c  nop     dword ptr [rax+rax+00h]
0x1400a0d21  jmp     loc_1400A0DD2
0x1400a0d26  lea     rcx, [rbx+0B30h]; this
0x1400a0d2d  call    ?IsTimeout@SP_WORKITEM@@QEAAEXZ; SP_WORKITEM::IsTimeout(void)
0x1400a0d32  test    al, al
0x1400a0d34  jz      loc_1400A0DD2
0x1400a0d3a  cmp     edi, 3
0x1400a0d3d  jnz     short loc_1400A0D65
0x1400a0d3f  mov     rcx, rbx; this
0x1400a0d42  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x1400a0d47  mov     esi, eax
0x1400a0d49  test    eax, eax
0x1400a0d4b  js      loc_1400A0F06
0x1400a0d51  mov     rcx, [rbx+0C98h]; this
0x1400a0d58  call    ?LostClear@SIO_SPACE@@QEAAJXZ; SIO_SPACE::LostClear(void)
0x1400a0d5d  mov     rcx, rbx; this
0x1400a0d60  call    ?ReleaseRundownShared@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownShared(void)
0x1400a0d65  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a0d6c  xor     edx, edx; unsigned __int8
0x1400a0d6e  add     rcx, 60h ; '`'; Resource
0x1400a0d72  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400a0d77  mov     rcx, rbx; this
0x1400a0d7a  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x1400a0d7f  mov     rcx, [rbx+0C98h]
0x1400a0d86  test    rcx, rcx
0x1400a0d89  jz      short loc_1400A0D97
0x1400a0d8b  mov     edx, edi
0x1400a0d8d  call    ?Repair@SP_SPACE@@QEAAJW4_SC_REPAIR_PHASE@@@Z; SP_SPACE::Repair(_SC_REPAIR_PHASE)
0x1400a0d92  mov     r12d, eax
0x1400a0d95  jmp     short loc_1400A0D9C
0x1400a0d97  mov     esi, 0C00000C0h
0x1400a0d9c  mov     rcx, rbx; this
0x1400a0d9f  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x1400a0da4  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a0dab  add     rcx, 60h ; '`'; struct _ERESOURCE *
0x1400a0daf  call    ?SpReleaseResourceShared@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceShared(_ERESOURCE *)
0x1400a0db4  cmp     esi, 0C00000C0h
0x1400a0dba  jz      loc_1400A0F06
0x1400a0dc0  cmp     edi, 3
0x1400a0dc3  jnz     short loc_1400A0DD2
0x1400a0dc5  mov     rdx, r13; struct _SP_ID *
0x1400a0dc8  lea     rcx, [rsp+190h+var_130]; this
0x1400a0dcd  call    ?ScopeRegeneration@SP_WORK@@QEAAJPEAU_SP_ID@@@Z; SP_WORK::ScopeRegeneration(_SP_ID *)
0x1400a0dd2  mov     rcx, rbx; this
0x1400a0dd5  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x1400a0dda  test    eax, eax
0x1400a0ddc  js      loc_1400A0F06
0x1400a0de2  mov     rcx, [rbx+0C98h]
0x1400a0de9  add     rcx, 0A0h; this
0x1400a0df0  call    ?GetShared@SIO_COUNTERS@@QEAAPEAXXZ; SIO_COUNTERS::GetShared(void)
0x1400a0df5  movsxd  rcx, edi
0x1400a0df8  inc     qword ptr [rax+rcx*8+188h]
0x1400a0e00  mov     [rax+rcx*4+1C0h], r12d
0x1400a0e08  mov     rcx, rbx; this
0x1400a0e0b  call    ?ReleaseRundownShared@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownShared(void)
0x1400a0e10  lea     r8, [rsp+190h+Interval]; Interval
0x1400a0e15  mov     qword ptr [rsp+190h+Interval], 0FFFFFFFFFD050F80h
0x1400a0e1e  xor     edx, edx; Alertable
0x1400a0e20  xor     ecx, ecx; WaitMode
0x1400a0e22  call    cs:__imp_KeDelayExecutionThread
0x1400a0e29  nop     dword ptr [rax+rax+00h]
0x1400a0e2e  inc     edi
0x1400a0e30  jmp     loc_1400A0BBD
0x1400a0e35  mov     r14, [rsp+190h+var_158]
0x1400a0e3a  mov     rcx, rbx; this
0x1400a0e3d  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x1400a0e42  test    r14, r14
0x1400a0e45  jz      loc_1400A0F06
0x1400a0e4b  mov     rcx, r14; void *
0x1400a0e4e  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a0e53  jmp     loc_1400A0F06
0x1400a0e58  test    eax, eax
0x1400a0e5a  js      loc_1400A0F06
0x1400a0e60  mov     rcx, [rbx+0C98h]; this
0x1400a0e67  lea     rdx, [rbp+90h+var_D0]; struct _SIO_HEALTH_CONTEXT *
0x1400a0e6b  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *)
0x1400a0e70  xor     sil, sil
0x1400a0e73  mov     edi, 1
0x1400a0e78  cmp     edi, 7
0x1400a0e7b  jge     short loc_1400A0E99
0x1400a0e7d  mov     rcx, [rbx+0C98h]
0x1400a0e84  mov     r8b, 1
0x1400a0e87  mov     edx, edi
0x1400a0e89  call    ?NeedRepair@SIO_SPACE@@QEAAEW4_SC_REPAIR_PHASE@@E@Z; SIO_SPACE::NeedRepair(_SC_REPAIR_PHASE,uchar)
0x1400a0e8e  test    al, al
0x1400a0e90  jnz     short loc_1400A0E96
0x1400a0e92  inc     edi
0x1400a0e94  jmp     short loc_1400A0E78
0x1400a0e96  mov     sil, 1
0x1400a0e99  mov     edx, 2
0x1400a0e9e  mov     rcx, rbx
0x1400a0ea1  call    ?CollectRepairStateTelemetry@SP_DEVICE@@QEAAXW4_SP_REPAIR_COUNTERS_ENTRY_POINT@@@Z; SP_DEVICE::CollectRepairStateTelemetry(_SP_REPAIR_COUNTERS_ENTRY_POINT)
0x1400a0ea6  cmp     [rbp+90h+var_D0], 3
0x1400a0eaa  jnz     short loc_1400A0EE7
0x1400a0eac  test    sil, sil
0x1400a0eaf  jnz     short loc_1400A0EE7
0x1400a0eb1  cmp     qword ptr [rbx+0C08h], 0
0x1400a0eb9  jz      short loc_1400A0EFE
0x1400a0ebb  mov     r8, [rbx+0C98h]; struct SP_SPACE *
0x1400a0ec2  xor     edx, edx; unsigned __int8
0x1400a0ec4  call    ?CollectHealthChangeTelemetry@SP_DEVICE@@QEAAXEPEAVSP_SPACE@@@Z; SP_DEVICE::CollectHealthChangeTelemetry(uchar,SP_SPACE *)
0x1400a0ec9  mov     rcx, [rbx+88h]; this
0x1400a0ed0  mov     qword ptr [rbx+0C08h], 0
0x1400a0edb  test    rcx, rcx
0x1400a0ede  jz      short loc_1400A0EFE
0x1400a0ee0  call    ?OnCommit@SIO_CACHE@@QEAAXXZ; SIO_CACHE::OnCommit(void)
0x1400a0ee5  jmp     short loc_1400A0EFE
0x1400a0ee7  lea     rcx, [rbx+0B30h]; Context
0x1400a0eee  xor     r9d, r9d; unsigned __int8
0x1400a0ef1  xor     edx, edx; struct _LIST_ENTRY *
0x1400a0ef3  mov     r8d, 493E0h; unsigned int
0x1400a0ef9  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400a0efe  mov     rcx, rbx; this
0x1400a0f01  call    ?ReleaseRundownShared@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownShared(void)
0x1400a0f06  lea     rcx, [rsp+190h+var_130]; this
0x1400a0f0b  call    ??1SP_WORK@@QEAA@XZ; SP_WORK::~SP_WORK(void)
0x1400a0f10  xor     eax, eax
0x1400a0f12  mov     rcx, [rbp+90h+var_50]
0x1400a0f16  xor     rcx, rsp; StackCookie
0x1400a0f19  call    __security_check_cookie
0x1400a0f1e  add     rsp, 158h
0x1400a0f25  pop     r15
0x1400a0f27  pop     r14
0x1400a0f29  pop     r13
0x1400a0f2b  pop     r12
0x1400a0f2d  pop     rdi
0x1400a0f2e  pop     rsi
0x1400a0f2f  pop     rbx
0x1400a0f30  pop     rbp
0x1400a0f31  retn
```
