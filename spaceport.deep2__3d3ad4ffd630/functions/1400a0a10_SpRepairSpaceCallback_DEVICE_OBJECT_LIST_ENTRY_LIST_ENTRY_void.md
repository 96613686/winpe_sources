# SpRepairSpaceCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x1400a0a10`
- end: `0x1400a0e03`
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
- `0x1400397e8`
- `0x14004281c`
- `0x140042fec`
- `0x140043190`
- `0x140047078`
- `0x140067fc0`
- `0x1400684c0`
- `0x14008f2f8`
- `0x14008f438`
- `0x14009cf94`
- `0x1400a0a10`
- `0x1400aa534`
- `0x1400aa774`
- `0x1400ac3b8`
- `0x1400ac544`
- `0x1400ac780`
- `0x1400af408`
- `0x1400b5720`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400a0be5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a0be5`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400a0cf2`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400a0cf2`

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
0x1400a0a10  push    rbp
0x1400a0a12  push    rbx
0x1400a0a13  push    rsi
0x1400a0a14  push    rdi
0x1400a0a15  push    r12
0x1400a0a17  push    r13
0x1400a0a19  push    r14
0x1400a0a1b  push    r15
0x1400a0a1d  lea     rbp, [rsp-58h]
0x1400a0a22  sub     rsp, 158h
0x1400a0a29  mov     rax, cs:__security_cookie
0x1400a0a30  xor     rax, rsp
0x1400a0a33  mov     [rbp+90h+var_50], rax
0x1400a0a37  xor     edx, edx; Val
0x1400a0a39  mov     [rsp+190h+var_160], 0
0x1400a0a41  mov     rbx, rcx
0x1400a0a44  mov     [rbp+90h+var_D0], 3
0x1400a0a4b  lea     rcx, [rbp+90h+var_CC]; void *
0x1400a0a4f  lea     r8d, [rdx+70h]; Size
0x1400a0a53  call    memset
0x1400a0a58  xor     r14d, r14d
0x1400a0a5b  lea     rcx, [rsp+190h+var_130]; this
0x1400a0a60  mov     [rsp+190h+var_158], r14
0x1400a0a65  xor     r12d, r12d
0x1400a0a68  call    ??0SP_WORK@@QEAA@XZ; SP_WORK::SP_WORK(void)
0x1400a0a6d  mov     rbx, [rbx+40h]
0x1400a0a71  lea     rcx, [rsp+190h+var_130]; this
0x1400a0a76  add     rbx, 8
0x1400a0a7a  mov     qword ptr [rsp+190h+Interval], r12
0x1400a0a7f  lea     r13, [rbx+18h]
0x1400a0a83  mov     rdx, r13; struct _SP_ID *
0x1400a0a86  call    ?RebalanceMetadata@SP_WORK@@QEAAJPEAU_SP_ID@@@Z; SP_WORK::RebalanceMetadata(_SP_ID *)
0x1400a0a8b  xor     edi, edi
0x1400a0a8d  mov     rcx, rbx; this
0x1400a0a90  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x1400a0a95  cmp     edi, 7
0x1400a0a98  jge     loc_1400A0D28
0x1400a0a9e  mov     esi, eax
0x1400a0aa0  test    eax, eax
0x1400a0aa2  js      loc_1400A0DD6
0x1400a0aa8  mov     rcx, [rbx+0C98h]
0x1400a0aaf  mov     r8b, 1
0x1400a0ab2  mov     edx, edi
0x1400a0ab4  call    ?NeedRepair@SIO_SPACE@@QEAAEW4_SC_REPAIR_PHASE@@E@Z; SIO_SPACE::NeedRepair(_SC_REPAIR_PHASE,uchar)
0x1400a0ab9  mov     r15b, al
0x1400a0abc  test    al, al
0x1400a0abe  jz      short loc_1400A0AF9
0x1400a0ac0  cmp     qword ptr [rbx+0C08h], 0
0x1400a0ac8  jnz     short loc_1400A0AF9
0x1400a0aca  mov     rax, 0FFFFF78000000014h
0x1400a0ad4  mov     dl, 1; unsigned __int8
0x1400a0ad6  mov     rax, [rax]
0x1400a0ad9  mov     r8, [rbx+0C98h]; struct SP_SPACE *
0x1400a0ae0  mov     [rbx+0C08h], rax
0x1400a0ae7  call    ?CollectHealthChangeTelemetry@SP_DEVICE@@QEAAXEPEAVSP_SPACE@@@Z; SP_DEVICE::CollectHealthChangeTelemetry(uchar,SP_SPACE *)
0x1400a0aec  mov     edx, 1
0x1400a0af1  mov     rcx, rbx
0x1400a0af4  call    ?CollectRepairStateTelemetry@SP_DEVICE@@QEAAXW4_SP_REPAIR_COUNTERS_ENTRY_POINT@@@Z; SP_DEVICE::CollectRepairStateTelemetry(_SP_REPAIR_COUNTERS_ENTRY_POINT)
0x1400a0af9  mov     rcx, rbx; this
0x1400a0afc  call    ?ReleaseRundownShared@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownShared(void)
0x1400a0b01  test    r15b, r15b
0x1400a0b04  jz      loc_1400A0CFE
0x1400a0b0a  mov     ecx, edi
0x1400a0b0c  test    edi, edi
0x1400a0b0e  jz      loc_1400A0BF6
0x1400a0b14  sub     ecx, 1
0x1400a0b17  jz      loc_1400A0C0A
0x1400a0b1d  sub     ecx, 1
0x1400a0b20  jz      short loc_1400A0B47
0x1400a0b22  sub     ecx, 1
0x1400a0b25  jz      loc_1400A0C0A
0x1400a0b2b  sub     ecx, 1
0x1400a0b2e  jz      loc_1400A0C0A
0x1400a0b34  sub     ecx, 1
0x1400a0b37  jz      short loc_1400A0B47
0x1400a0b39  cmp     ecx, 1
0x1400a0b3c  jz      loc_1400A0C0A
0x1400a0b42  jmp     loc_1400A0CA2
0x1400a0b47  mov     rcx, rbx; this
0x1400a0b4a  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x1400a0b4f  mov     rcx, [rbx+0C98h]
0x1400a0b56  test    rcx, rcx
0x1400a0b59  jz      loc_1400A0D0A
0x1400a0b5f  lea     r9, [rsp+190h+var_160]
0x1400a0b64  mov     edx, edi
0x1400a0b66  lea     r8, [rsp+190h+var_158]
0x1400a0b6b  call    ?GetRepairWork@SIO_SPACE@@QEAAJW4_SC_REPAIR_PHASE@@PEAPEAVSP_REPAIR_WORK@@PEAK@Z; SIO_SPACE::GetRepairWork(_SC_REPAIR_PHASE,SP_REPAIR_WORK * *,ulong *)
0x1400a0b70  test    eax, eax
0x1400a0b72  js      loc_1400A0D05
0x1400a0b78  mov     rcx, rbx; this
0x1400a0b7b  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x1400a0b80  mov     r9d, [rsp+190h+var_160]; unsigned int
0x1400a0b85  lea     rcx, [rsp+190h+var_130]; this
0x1400a0b8a  mov     r8, [rsp+190h+var_158]; void *
0x1400a0b8f  mov     rdx, r13; struct _SP_ID *
0x1400a0b92  call    ?RepairSpace@SP_WORK@@QEAAJPEAU_SP_ID@@PEAXK@Z; SP_WORK::RepairSpace(_SP_ID *,void *,ulong)
0x1400a0b97  mov     rcx, [rsp+190h+var_158]; void *
0x1400a0b9c  mov     r12d, eax
0x1400a0b9f  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a0ba4  xor     r14d, r14d
0x1400a0ba7  mov     [rsp+190h+var_158], r14
0x1400a0bac  test    r12d, r12d
0x1400a0baf  js      loc_1400A0CA2
0x1400a0bb5  movups  xmm0, xmmword ptr [r13+0]
0x1400a0bba  lea     rcx, [rsp+190h+var_140]; struct _GUID *
0x1400a0bbf  movdqu  xmmword ptr [rsp+190h+var_140.Data1], xmm0
0x1400a0bc5  call    ?SpRefreshPoolWork@@YAJU_GUID@@@Z; SpRefreshPoolWork(_GUID)
0x1400a0bca  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a0bd1  xor     r9d, r9d; Alertable
0x1400a0bd4  add     rcx, 3B8h; Object
0x1400a0bdb  mov     [rsp+190h+Timeout], r14; Timeout
0x1400a0be0  xor     r8d, r8d; WaitMode
0x1400a0be3  xor     edx, edx; WaitReason
0x1400a0be5  call    cs:__imp_KeWaitForSingleObject
0x1400a0bec  nop     dword ptr [rax+rax+00h]
0x1400a0bf1  jmp     loc_1400A0CA2
0x1400a0bf6  lea     rcx, [rbx+0B30h]; this
0x1400a0bfd  call    ?IsTimeout@SP_WORKITEM@@QEAAEXZ; SP_WORKITEM::IsTimeout(void)
0x1400a0c02  test    al, al
0x1400a0c04  jz      loc_1400A0CA2
0x1400a0c0a  cmp     edi, 3
0x1400a0c0d  jnz     short loc_1400A0C35
0x1400a0c0f  mov     rcx, rbx; this
0x1400a0c12  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x1400a0c17  mov     esi, eax
0x1400a0c19  test    eax, eax
0x1400a0c1b  js      loc_1400A0DD6
0x1400a0c21  mov     rcx, [rbx+0C98h]; this
0x1400a0c28  call    ?LostClear@SIO_SPACE@@QEAAJXZ; SIO_SPACE::LostClear(void)
0x1400a0c2d  mov     rcx, rbx; this
0x1400a0c30  call    ?ReleaseRundownShared@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownShared(void)
0x1400a0c35  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a0c3c  xor     edx, edx; unsigned __int8
0x1400a0c3e  add     rcx, 60h ; '`'; Resource
0x1400a0c42  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400a0c47  mov     rcx, rbx; this
0x1400a0c4a  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x1400a0c4f  mov     rcx, [rbx+0C98h]
0x1400a0c56  test    rcx, rcx
0x1400a0c59  jz      short loc_1400A0C67
0x1400a0c5b  mov     edx, edi
0x1400a0c5d  call    ?Repair@SP_SPACE@@QEAAJW4_SC_REPAIR_PHASE@@@Z; SP_SPACE::Repair(_SC_REPAIR_PHASE)
0x1400a0c62  mov     r12d, eax
0x1400a0c65  jmp     short loc_1400A0C6C
0x1400a0c67  mov     esi, 0C00000C0h
0x1400a0c6c  mov     rcx, rbx; this
0x1400a0c6f  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x1400a0c74  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a0c7b  add     rcx, 60h ; '`'; struct _ERESOURCE *
0x1400a0c7f  call    ?SpReleaseResourceShared@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceShared(_ERESOURCE *)
0x1400a0c84  cmp     esi, 0C00000C0h
0x1400a0c8a  jz      loc_1400A0DD6
0x1400a0c90  cmp     edi, 3
0x1400a0c93  jnz     short loc_1400A0CA2
0x1400a0c95  mov     rdx, r13; struct _SP_ID *
0x1400a0c98  lea     rcx, [rsp+190h+var_130]; this
0x1400a0c9d  call    ?ScopeRegeneration@SP_WORK@@QEAAJPEAU_SP_ID@@@Z; SP_WORK::ScopeRegeneration(_SP_ID *)
0x1400a0ca2  mov     rcx, rbx; this
0x1400a0ca5  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x1400a0caa  test    eax, eax
0x1400a0cac  js      loc_1400A0DD6
0x1400a0cb2  mov     rcx, [rbx+0C98h]
0x1400a0cb9  add     rcx, 0A0h; this
0x1400a0cc0  call    ?GetShared@SIO_COUNTERS@@QEAAPEAXXZ; SIO_COUNTERS::GetShared(void)
0x1400a0cc5  movsxd  rcx, edi
0x1400a0cc8  inc     qword ptr [rax+rcx*8+188h]
0x1400a0cd0  mov     [rax+rcx*4+1C0h], r12d
0x1400a0cd8  mov     rcx, rbx; this
0x1400a0cdb  call    ?ReleaseRundownShared@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownShared(void)
0x1400a0ce0  lea     r8, [rsp+190h+Interval]; Interval
0x1400a0ce5  mov     qword ptr [rsp+190h+Interval], 0FFFFFFFFFD050F80h
0x1400a0cee  xor     edx, edx; Alertable
0x1400a0cf0  xor     ecx, ecx; WaitMode
0x1400a0cf2  call    cs:__imp_KeDelayExecutionThread
0x1400a0cf9  nop     dword ptr [rax+rax+00h]
0x1400a0cfe  inc     edi
0x1400a0d00  jmp     loc_1400A0A8D
0x1400a0d05  mov     r14, [rsp+190h+var_158]
0x1400a0d0a  mov     rcx, rbx; this
0x1400a0d0d  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x1400a0d12  test    r14, r14
0x1400a0d15  jz      loc_1400A0DD6
0x1400a0d1b  mov     rcx, r14; void *
0x1400a0d1e  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x1400a0d23  jmp     loc_1400A0DD6
0x1400a0d28  test    eax, eax
0x1400a0d2a  js      loc_1400A0DD6
0x1400a0d30  mov     rcx, [rbx+0C98h]; this
0x1400a0d37  lea     rdx, [rbp+90h+var_D0]; struct _SIO_HEALTH_CONTEXT *
0x1400a0d3b  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *)
0x1400a0d40  xor     sil, sil
0x1400a0d43  mov     edi, 1
0x1400a0d48  cmp     edi, 7
0x1400a0d4b  jge     short loc_1400A0D69
0x1400a0d4d  mov     rcx, [rbx+0C98h]
0x1400a0d54  mov     r8b, 1
0x1400a0d57  mov     edx, edi
0x1400a0d59  call    ?NeedRepair@SIO_SPACE@@QEAAEW4_SC_REPAIR_PHASE@@E@Z; SIO_SPACE::NeedRepair(_SC_REPAIR_PHASE,uchar)
0x1400a0d5e  test    al, al
0x1400a0d60  jnz     short loc_1400A0D66
0x1400a0d62  inc     edi
0x1400a0d64  jmp     short loc_1400A0D48
0x1400a0d66  mov     sil, 1
0x1400a0d69  mov     edx, 2
0x1400a0d6e  mov     rcx, rbx
0x1400a0d71  call    ?CollectRepairStateTelemetry@SP_DEVICE@@QEAAXW4_SP_REPAIR_COUNTERS_ENTRY_POINT@@@Z; SP_DEVICE::CollectRepairStateTelemetry(_SP_REPAIR_COUNTERS_ENTRY_POINT)
0x1400a0d76  cmp     [rbp+90h+var_D0], 3
0x1400a0d7a  jnz     short loc_1400A0DB7
0x1400a0d7c  test    sil, sil
0x1400a0d7f  jnz     short loc_1400A0DB7
0x1400a0d81  cmp     qword ptr [rbx+0C08h], 0
0x1400a0d89  jz      short loc_1400A0DCE
0x1400a0d8b  mov     r8, [rbx+0C98h]; struct SP_SPACE *
0x1400a0d92  xor     edx, edx; unsigned __int8
0x1400a0d94  call    ?CollectHealthChangeTelemetry@SP_DEVICE@@QEAAXEPEAVSP_SPACE@@@Z; SP_DEVICE::CollectHealthChangeTelemetry(uchar,SP_SPACE *)
0x1400a0d99  mov     rcx, [rbx+88h]; this
0x1400a0da0  mov     qword ptr [rbx+0C08h], 0
0x1400a0dab  test    rcx, rcx
0x1400a0dae  jz      short loc_1400A0DCE
0x1400a0db0  call    ?OnCommit@SIO_CACHE@@QEAAXXZ; SIO_CACHE::OnCommit(void)
0x1400a0db5  jmp     short loc_1400A0DCE
0x1400a0db7  lea     rcx, [rbx+0B30h]; Context
0x1400a0dbe  xor     r9d, r9d; unsigned __int8
0x1400a0dc1  xor     edx, edx; struct _LIST_ENTRY *
0x1400a0dc3  mov     r8d, 493E0h; unsigned int
0x1400a0dc9  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400a0dce  mov     rcx, rbx; this
0x1400a0dd1  call    ?ReleaseRundownShared@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownShared(void)
0x1400a0dd6  lea     rcx, [rsp+190h+var_130]; this
0x1400a0ddb  call    ??1SP_WORK@@QEAA@XZ; SP_WORK::~SP_WORK(void)
0x1400a0de0  xor     eax, eax
0x1400a0de2  mov     rcx, [rbp+90h+var_50]
0x1400a0de6  xor     rcx, rsp; StackCookie
0x1400a0de9  call    __security_check_cookie
0x1400a0dee  add     rsp, 158h
0x1400a0df5  pop     r15
0x1400a0df7  pop     r14
0x1400a0df9  pop     r13
0x1400a0dfb  pop     r12
0x1400a0dfd  pop     rdi
0x1400a0dfe  pop     rsi
0x1400a0dff  pop     rbx
0x1400a0e00  pop     rbp
0x1400a0e01  retn
```
