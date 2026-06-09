# SpIoctlCreatePool(_IRP *)

- ea: `0x140092fbc`
- end: `0x140093654`
- name: `?SpIoctlCreatePool@@YAJPEAU_IRP@@@Z`
- size: `1688`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400b57b0`

## callees

- `0x14000200c`
- `0x1400028ec`
- `0x14001c760`
- `0x14001e4a0`
- `0x140021df0`
- `0x14002ce90`
- `0x14002d1c0`
- `0x14002e104`
- `0x14002e43c`
- `0x14002e6c4`
- `0x140032e04`
- `0x140033478`
- `0x1400345a0`
- `0x14003bfac`
- `0x140058c7c`
- `0x140058cc8`
- `0x140058e94`
- `0x14005ffb0`
- `0x140060124`
- `0x140060660`
- `0x1400629e0`
- `0x140066218`
- `0x140068000`
- `0x14008ce50`
- `0x140092244`
- `0x14009256c`
- `0x140092fbc`
- `0x14009c600`
- `0x14009c910`
- `0x14009d794`
- `0x14009e3b8`
- `0x1400a378c`
- `0x1400a4c44`
- `0x1400a5210`
- `0x1400aace8`
- `0x1400ac6f0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140093525`
- `ntoskrnl!ObfDereferenceObject` at `0x140093525`
- `ntoskrnl!ObfReferenceObject` at `0x14009325b`
- `ntoskrnl!ObfReferenceObject` at `0x14009325b`

## pseudocode

```c
__int64 __fastcall SpIoctlCreatePool(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int v3; // ebx
  struct _IRP *MasterIrp; // rdi
  unsigned __int64 Options; // rax
  __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned int SortKey; // r8d
  struct _GUID *v10; // rsi
  int v11; // eax
  unsigned __int64 v12; // rcx
  struct SDB_DRIVE *v13; // r13
  struct SS_STORE_CACHE *v14; // r12
  SS_STORE_CACHE *v15; // rax
  SS_STORE_CACHE *v16; // rax
  unsigned int v17; // edx
  SDB_POOL_CONFIG *v18; // rax
  SDB_POOL_CONFIG *v19; // rax
  SDB_POOL_CONFIG *v20; // rsi
  struct SDB_POOL *v21; // r14
  int v22; // eax
  SP_POOL_DEVICE *v23; // r14
  SP_POOL *v24; // rax
  SP_POOL *v25; // r15
  char *v26; // rdx
  PVOID *v27; // rax
  struct SDB_POOL *v28; // rcx
  __int128 v29; // xmm0
  ULONG v30; // r14d
  __int128 *v31; // rsi
  __int128 v32; // xmm1
  __int64 v33; // r9
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  ULONG DeviceType; // ecx
  const char *v40; // r9
  unsigned int v42[2]; // [rsp+20h] [rbp-49h]
  unsigned int v43[2]; // [rsp+20h] [rbp-49h]
  struct _GUID v44; // [rsp+40h] [rbp-29h] BYREF
  GUID v45; // [rsp+50h] [rbp-19h] BYREF
  __int128 v46; // [rsp+60h] [rbp-9h] BYREF
  _OWORD v47[5]; // [rsp+70h] [rbp+7h] BYREF
  struct SDB_DRIVE *v48; // [rsp+D0h] [rbp+67h] BYREF
  SP_POOL_DEVICE *v49; // [rsp+D8h] [rbp+6Fh] BYREF
  struct SDB_POOL *v50; // [rsp+E0h] [rbp+77h] BYREF
  __int128 *v51; // [rsp+E8h] [rbp+7Fh] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v49 = 0;
  v48 = 0;
  v50 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids);
  }
  SpAcquireResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  if ( CurrentStackLocation->Parameters.Create.Options < 0xB10 )
    goto LABEL_6;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type != 2832 )
  {
    v3 = -1058602968;
    goto LABEL_68;
  }
  if ( MasterIrp[12].Overlay.AllocationSize.HighPart > 0x1Du
    && !(unsigned int)Feature_SpacesPoolVersion2700__private_IsEnabledDeviceUsageNoInline() )
  {
    v3 = -1073741637;
    goto LABEL_68;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( (unsigned int)Options < *(_DWORD *)(&MasterIrp->Size + 1) )
  {
LABEL_6:
    v3 = -1073741820;
    goto LABEL_68;
  }
  v6 = *((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 5);
  if ( (unsigned int)v6 < 0xB10
    || (v7 = 16LL * MasterIrp[12].Tail.Overlay.DeviceQueueEntry.SortKey + v6, v7 > Options)
    || (v8 = *((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 7), v7 > v8)
    || v8 + 16LL * *((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 6) > CurrentStackLocation->Parameters.Create.Options )
  {
    v3 = -1073741811;
    goto LABEL_68;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice);
  }
  v3 = SpAccessCheck(*((PSECURITY_DESCRIPTOR *)WPP_MAIN_CB.DeviceExtension + 48), a1);
  if ( v3 >= 0 )
  {
    SortKey = MasterIrp[12].Tail.Overlay.DeviceQueueEntry.SortKey;
    v10 = (struct _GUID *)((char *)MasterIrp + *((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 5));
    v44 = *(struct _GUID *)&MasterIrp->MdlAddress;
    v3 = SpValidateDrives(&v44, v10, SortKey);
    if ( v3 >= 0 )
    {
      v3 = SpPoolCopyHelper((struct _SP_POOL_INFO *)MasterIrp, &v50);
      if ( v3 < 0 )
      {
LABEL_66:
        if ( v50 )
          (**(void (__fastcall ***)(struct SDB_POOL *, __int64))v50)(v50, 1);
        goto LABEL_68;
      }
      v11 = SpDrivesCopyHelper(
              *((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 8),
              v10,
              MasterIrp[12].Tail.Overlay.DeviceQueueEntry.SortKey,
              &v48);
      v13 = v48;
      v3 = v11;
      if ( v11 >= 0 )
      {
        v14 = 0;
        if ( !BYTE2(MasterIrp[12].Overlay.AllocationSize.u.LowPart) )
          goto LABEL_30;
        v15 = (SS_STORE_CACHE *)SS_STORE_CACHE::operator new(v12);
        if ( !v15 || (v16 = SS_STORE_CACHE::SS_STORE_CACHE(v15), (v14 = v16) == 0) )
        {
          v3 = -1073741670;
          goto LABEL_62;
        }
        v3 = SS_STORE_CACHE::Initialize(v16);
        if ( v3 >= 0 )
        {
LABEL_30:
          v18 = (SDB_POOL_CONFIG *)SDB_POOL_CONFIG::operator new(v12);
          if ( v18 && (v19 = SDB_POOL_CONFIG::SDB_POOL_CONFIG(v18), (v20 = v19) != 0) )
          {
            v3 = SDB_POOL_CONFIG::Initialize(v19);
            if ( v3 < 0 )
              goto LABEL_58;
            v21 = v50;
            v3 = SDB_POOL_CONFIG::Create(
                   v20,
                   v50,
                   v13,
                   MasterIrp[12].Tail.Overlay.DeviceQueueEntry.SortKey,
                   *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 8) - 0x2000,
                   v14);
            if ( v3 < 0 )
              goto LABEL_58;
            v44 = (struct _GUID)*((_OWORD *)v21 + 2);
            v22 = SpCreatePoolDevice(&v44, &v49);
            v23 = v49;
            v3 = v22;
            if ( v22 >= 0 )
            {
              ObfReferenceObject(*(PVOID *)v49);
              SP_POOL_DEVICE::AcquireMutex(v23);
              v3 = SP_POOL_DEVICE::Initialize(v23);
              if ( v3 >= 0 )
              {
                v24 = (SP_POOL *)SC_ENV_ALLOCATOR::operator new(0x1E0u, 0x6C507053u, 0, 0);
                if ( v24 && (v25 = SP_POOL::SP_POOL(v24)) != 0 )
                {
                  v26 = (char *)WPP_MAIN_CB.DeviceExtension + 208;
                  v27 = (PVOID *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 27);
                  if ( *v27 != (char *)WPP_MAIN_CB.DeviceExtension + 208 )
                    __fastfail(3u);
                  v28 = v50;
                  *(_QWORD *)v25 = v26;
                  *((_QWORD *)v25 + 1) = v27;
                  *v27 = v25;
                  *((_QWORD *)v26 + 1) = v25;
                  *((_QWORD *)v25 + 6) = v20;
                  v20 = 0;
                  *((_WORD *)v25 + 32) = 257;
                  *((_BYTE *)v25 + 70) = BYTE2(MasterIrp[12].Overlay.AllocationSize.u.LowPart);
                  *((_DWORD *)v25 + 26) = 1;
                  v29 = *((_OWORD *)v28 + 2);
                  v51 = (__int128 *)((char *)v25 + 108);
                  *(_QWORD *)&v44.Data1 = 0;
                  *(_OWORD *)((char *)v25 + 108) = v29;
                  *(_QWORD *)v42 = MasterIrp[12].Tail.Overlay.DeviceQueueEntry.SortKey;
                  v3 = SP_POOL::ExecuteTransaction(v25, 3, v28);
                  if ( v3 < 0 )
                  {
                    SpPoolRemove(v25);
                  }
                  else
                  {
                    SDB_POOL_CONFIG::UpdateTolerance(*((SDB_POOL_CONFIG **)v25 + 6));
                    if ( MasterIrp[12].Tail.Overlay.DeviceQueueEntry.SortKey )
                    {
                      v30 = 0;
                      v31 = v51;
                      do
                      {
                        v48 = (struct SDB_DRIVE *)*((_QWORD *)v13 + 40 * v30 + 28);
                        SP_DRIVE::ResetTempDefaults(v48);
                        SP_DRIVE::Connect(v48, *((struct SDB_POOL_CONFIG **)v25 + 6));
                        v42[0] = 4;
                        v32 = *((_OWORD *)WPP_MAIN_CB.DeviceExtension + 23);
                        v45 = *(GUID *)((char *)v48 + 508);
                        v46 = v32;
                        v47[0] = GUID_SPACEPORT_DRIVE_NOTIFICATION;
                        SpNotify(v47, &v46, &v45, 7, *(_QWORD *)v42, 0, v48);
                        v43[0] = 0;
                        if ( v30 )
                        {
                          v33 = 8;
                          v35 = *v31;
                          v47[0] = *(_OWORD *)((char *)v48 + 508);
                          v46 = v35;
                          v45 = GUID_SPACEPORT_DRIVE_NOTIFICATION;
                        }
                        else
                        {
                          v33 = 2;
                          v47[0] = GUID_NULL;
                          v34 = *v31;
                          v45 = GUID_SPACEPORT_POOL_NOTIFICATION;
                          v46 = v34;
                        }
                        SpNotify(&v45, &v46, v47, v33, *(_QWORD *)v43, v25, v48);
                        ++v30;
                      }
                      while ( v30 < MasterIrp[12].Tail.Overlay.DeviceQueueEntry.SortKey );
                      v20 = *(SDB_POOL_CONFIG **)&v44.Data1;
                      v23 = v49;
                    }
                    if ( (unsigned int)dword_14007F050 > 5
                      && (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
                    {
                      v48 = (struct SDB_DRIVE *)*((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 6);
                      v49 = (SP_POOL_DEVICE *)MasterIrp[12].Tail.Overlay.DeviceQueueEntry.SortKey;
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                        v36,
                        (unsigned int)byte_14007520D,
                        v37,
                        v38,
                        (__int64)&v51,
                        (__int64)&v49,
                        (__int64)&v48);
                    }
                    *((_QWORD *)v23 + 14) = v25;
                    *((_QWORD *)v23 + 15) = v14;
                    v14 = 0;
                    *((_QWORD *)v25 + 7) = v23;
                    SP_POOL_DEVICE::ReleaseMutex(v23);
                    v23 = 0;
                  }
                }
                else
                {
                  v3 = -1073741670;
                }
              }
            }
            if ( v23 )
            {
              SpDeletePoolDevice(v23);
              SP_POOL_DEVICE::ReleaseMutex(v23);
              ObfDereferenceObject(*(PVOID *)v23);
            }
            if ( v20 )
LABEL_58:
              (**(void (__fastcall ***)(SDB_POOL_CONFIG *, __int64))v20)(v20, 1);
          }
          else
          {
            v3 = -1073741670;
          }
          if ( !v14 )
            goto LABEL_62;
        }
        SS_STORE_CACHE::`scalar deleting destructor'(v14, v17);
      }
LABEL_62:
      if ( v13 )
      {
        if ( *((_QWORD *)v13 - 1) )
          (**(void (__fastcall ***)(struct SDB_DRIVE *, __int64))v13)(v13, 3);
        else
          SC_ENV_ALLOCATOR::operator delete[]((char *)v13 - 8);
      }
      goto LABEL_66;
    }
  }
LABEL_68:
  SpReleaseResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  if ( v3 >= 0 || v3 == -2147483643 || v3 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v40 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v40 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v40,
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140092fbc  push    rbp
0x140092fbe  push    rbx
0x140092fbf  push    rsi
0x140092fc0  push    rdi
0x140092fc1  push    r12
0x140092fc3  push    r13
0x140092fc5  push    r14
0x140092fc7  push    r15
0x140092fc9  lea     rbp, [rsp-1Fh]
0x140092fce  sub     rsp, 88h
0x140092fd5  mov     rsi, [rcx+0B8h]
0x140092fdc  mov     rbx, rcx
0x140092fdf  mov     [rbp+57h+arg_8], 0
0x140092fe7  mov     [rbp+57h+arg_0], 0
0x140092fef  mov     [rbp+57h+arg_10], 0
0x140092ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x140092ffe  lea     r15, WPP_GLOBAL_Control
0x140093005  cmp     rcx, r15
0x140093008  jz      short loc_14009302C
0x14009300a  mov     eax, [rcx+2Ch]
0x14009300d  test    al, 1
0x14009300f  jz      short loc_14009302C
0x140093011  cmp     byte ptr [rcx+29h], 3
0x140093015  jb      short loc_14009302C
0x140093017  mov     rcx, [rcx+18h]
0x14009301b  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x140093022  mov     edx, 14h
0x140093027  call    WPP_SF_
0x14009302c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140093033  add     rcx, 60h ; '`'; Resource
0x140093037  call    ?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpAcquireResourceExclusive(_ERESOURCE *)
0x14009303c  mov     r14d, 0B10h
0x140093042  cmp     [rsi+10h], r14d
0x140093046  jnb     short loc_140093052
0x140093048  mov     ebx, 0C0000004h
0x14009304d  jmp     loc_1400935A7
0x140093052  mov     rdi, [rbx+18h]
0x140093056  cmp     [rdi], r14d
0x140093059  jz      short loc_140093065
0x14009305b  mov     ebx, 0C0E70028h
0x140093060  jmp     loc_1400935A7
0x140093065  cmp     dword ptr [rdi+0A1Ch], 1Dh
0x14009306c  jbe     short loc_140093081
0x14009306e  call    Feature_SpacesPoolVersion2700__private_IsEnabledDeviceUsageNoInline
0x140093073  test    eax, eax
0x140093075  jnz     short loc_140093081
0x140093077  mov     ebx, 0C00000BBh
0x14009307c  jmp     loc_1400935A7
0x140093081  mov     eax, [rsi+10h]
0x140093084  cmp     eax, [rdi+4]
0x140093087  jb      short loc_140093048
0x140093089  mov     edx, [rdi+0A4Ch]
0x14009308f  cmp     edx, r14d
0x140093092  jnb     short loc_14009309E
0x140093094  mov     ebx, 0C000000Dh
0x140093099  jmp     loc_1400935A7
0x14009309e  mov     r9d, [rdi+0A48h]
0x1400930a5  mov     r8, rax
0x1400930a8  mov     ecx, r9d
0x1400930ab  shl     rcx, 4
0x1400930af  add     rdx, rcx
0x1400930b2  cmp     rdx, rax
0x1400930b5  ja      short loc_140093094
0x1400930b7  mov     ecx, [rdi+0A54h]
0x1400930bd  cmp     rdx, rcx
0x1400930c0  ja      short loc_140093094
0x1400930c2  mov     edx, [rdi+0A50h]
0x1400930c8  mov     eax, edx
0x1400930ca  shl     rax, 4
0x1400930ce  add     rax, rcx
0x1400930d1  cmp     rax, r8
0x1400930d4  ja      short loc_140093094
0x1400930d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400930dd  cmp     rcx, r15
0x1400930e0  jz      short loc_1400930FC
0x1400930e2  mov     eax, [rcx+2Ch]
0x1400930e5  test    al, 20h
0x1400930e7  jz      short loc_1400930FC
0x1400930e9  cmp     byte ptr [rcx+29h], 3
0x1400930ed  jb      short loc_1400930FC
0x1400930ef  mov     rcx, [rcx+18h]
0x1400930f3  mov     [rsp+0C0h+var_A0], edx
0x1400930f7  call    WPP_SF_dd
0x1400930fc  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140093103  mov     rdx, rbx; struct _IRP *
0x140093106  mov     rcx, [rcx+180h]; SecurityDescriptor
0x14009310d  call    ?SpAccessCheck@@YAJPEAXPEAU_IRP@@@Z; SpAccessCheck(void *,_IRP *)
0x140093112  mov     ebx, eax
0x140093114  test    eax, eax
0x140093116  js      loc_1400935A7
0x14009311c  mov     esi, [rdi+0A4Ch]
0x140093122  lea     rcx, [rbp+57h+var_80]; struct _GUID
0x140093126  movups  xmm0, xmmword ptr [rdi+8]
0x14009312a  mov     r8d, [rdi+0A48h]; unsigned int
0x140093131  add     rsi, rdi
0x140093134  mov     rdx, rsi; struct _GUID *
0x140093137  movdqu  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x14009313c  call    ?SpValidateDrives@@YAJU_GUID@@PEAU1@K@Z; SpValidateDrives(_GUID,_GUID *,ulong)
0x140093141  mov     ebx, eax
0x140093143  test    eax, eax
0x140093145  js      loc_1400935A7
0x14009314b  lea     rdx, [rbp+57h+arg_10]; struct SDB_POOL **
0x14009314f  mov     rcx, rdi; struct _SP_POOL_INFO *
0x140093152  call    ?SpPoolCopyHelper@@YAJPEAU_SP_POOL_INFO@@PEAPEAVSDB_POOL@@@Z; SpPoolCopyHelper(_SP_POOL_INFO *,SDB_POOL * *)
0x140093157  mov     ebx, eax
0x140093159  test    eax, eax
0x14009315b  js      loc_14009358E
0x140093161  mov     ecx, [rdi+0A58h]; unsigned __int64
0x140093167  lea     r9, [rbp+57h+arg_0]; struct SDB_DRIVE **
0x14009316b  mov     r8d, [rdi+0A48h]; unsigned int
0x140093172  mov     rdx, rsi; struct _GUID *
0x140093175  call    ?SpDrivesCopyHelper@@YAJ_KPEAU_GUID@@KPEAPEAVSDB_DRIVE@@@Z; SpDrivesCopyHelper(unsigned __int64,_GUID *,ulong,SDB_DRIVE * *)
0x14009317a  mov     r13, [rbp+57h+arg_0]
0x14009317e  mov     ebx, eax
0x140093180  test    eax, eax
0x140093182  js      loc_14009355D
0x140093188  xor     r12d, r12d
0x14009318b  cmp     [rdi+0A1Ah], r12b
0x140093192  jz      short loc_1400931C8
0x140093194  call    ??2SS_STORE_CACHE@@SAPEAX_K@Z; SS_STORE_CACHE::operator new(unsigned __int64)
0x140093199  test    rax, rax
0x14009319c  jz      loc_1400932D1
0x1400931a2  mov     rcx, rax; this
0x1400931a5  call    ??0SS_STORE_CACHE@@QEAA@XZ; SS_STORE_CACHE::SS_STORE_CACHE(void)
0x1400931aa  mov     r12, rax
0x1400931ad  test    rax, rax
0x1400931b0  jz      loc_1400932D1
0x1400931b6  mov     rcx, rax; this
0x1400931b9  call    ?Initialize@SS_STORE_CACHE@@QEAAJXZ; SS_STORE_CACHE::Initialize(void)
0x1400931be  mov     ebx, eax
0x1400931c0  test    eax, eax
0x1400931c2  js      loc_140093555
0x1400931c8  call    ??2SDB_POOL_CONFIG@@SAPEAX_K@Z; SDB_POOL_CONFIG::operator new(unsigned __int64)
0x1400931cd  test    rax, rax
0x1400931d0  jz      loc_14009354B
0x1400931d6  mov     rcx, rax; this
0x1400931d9  call    ??0SDB_POOL_CONFIG@@QEAA@XZ; SDB_POOL_CONFIG::SDB_POOL_CONFIG(void)
0x1400931de  mov     rsi, rax
0x1400931e1  test    rax, rax
0x1400931e4  jz      loc_14009354B
0x1400931ea  mov     rcx, rax; this
0x1400931ed  call    ?Initialize@SDB_POOL_CONFIG@@UEAAJXZ; SDB_POOL_CONFIG::Initialize(void)
0x1400931f2  mov     ebx, eax
0x1400931f4  test    eax, eax
0x1400931f6  js      loc_140093536
0x1400931fc  mov     eax, [rdi+0A58h]
0x140093202  mov     r8, r13; struct SDB_DRIVE *
0x140093205  mov     r14, [rbp+57h+arg_10]
0x140093209  sub     eax, 2000h
0x14009320e  mov     r9d, [rdi+0A48h]; unsigned int
0x140093215  mov     rdx, r14; struct SDB_POOL *
0x140093218  mov     [rsp+0C0h+var_98], r12; struct SS_STORE_CACHE *
0x14009321d  mov     rcx, rsi; this
0x140093220  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x140093224  call    ?Create@SDB_POOL_CONFIG@@QEAAJPEAVSDB_POOL@@PEAVSDB_DRIVE@@KKPEAVSS_STORE_CACHE@@@Z; SDB_POOL_CONFIG::Create(SDB_POOL *,SDB_DRIVE *,ulong,ulong,SS_STORE_CACHE *)
0x140093229  mov     ebx, eax
0x14009322b  test    eax, eax
0x14009322d  js      loc_140093536
0x140093233  movups  xmm0, xmmword ptr [r14+20h]
0x140093238  lea     rdx, [rbp+57h+arg_8]; struct SP_POOL_DEVICE **
0x14009323c  lea     rcx, [rbp+57h+var_80]; struct _GUID
0x140093240  movdqu  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x140093245  call    ?SpCreatePoolDevice@@YAJU_GUID@@PEAPEAVSP_POOL_DEVICE@@@Z; SpCreatePoolDevice(_GUID,SP_POOL_DEVICE * *)
0x14009324a  mov     r14, [rbp+57h+arg_8]
0x14009324e  mov     ebx, eax
0x140093250  test    eax, eax
0x140093252  js      loc_14009350D
0x140093258  mov     rcx, [r14]; Object
0x14009325b  call    cs:__imp_ObfReferenceObject
0x140093262  nop     dword ptr [rax+rax+00h]
0x140093267  mov     rcx, r14; this
0x14009326a  call    ?AcquireMutex@SP_POOL_DEVICE@@QEAAXXZ; SP_POOL_DEVICE::AcquireMutex(void)
0x14009326f  mov     rcx, r14; this
0x140093272  call    ?Initialize@SP_POOL_DEVICE@@QEAAJXZ; SP_POOL_DEVICE::Initialize(void)
0x140093277  mov     ebx, eax
0x140093279  test    eax, eax
0x14009327b  js      loc_14009350D
0x140093281  xor     r9d, r9d; unsigned __int64
0x140093284  xor     r8d, r8d; unsigned __int8
0x140093287  mov     edx, 6C507053h; unsigned int
0x14009328c  mov     ecx, 1E0h; unsigned __int64
0x140093291  call    ??2SC_ENV_ALLOCATOR@@SAPEAX_KKE0@Z; SC_ENV_ALLOCATOR::operator new(unsigned __int64,ulong,uchar,unsigned __int64)
0x140093296  test    rax, rax
0x140093299  jz      loc_140093508
0x14009329f  mov     rcx, rax; this
0x1400932a2  call    ??0SP_POOL@@QEAA@XZ; SP_POOL::SP_POOL(void)
0x1400932a7  mov     r15, rax
0x1400932aa  test    rax, rax
0x1400932ad  jz      loc_140093508
0x1400932b3  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension
0x1400932ba  add     rdx, 0D0h
0x1400932c1  mov     rax, [rdx+8]
0x1400932c5  cmp     [rax], rdx
0x1400932c8  jz      short loc_1400932DB
0x1400932ca  mov     ecx, 3
0x1400932cf  int     29h; Win8: RtlFailFast(ecx)
0x1400932d1  mov     ebx, 0C000009Ah
0x1400932d6  jmp     loc_14009355D
0x1400932db  mov     rcx, [rbp+57h+arg_10]
0x1400932df  mov     r9, r13
0x1400932e2  mov     [r15], rdx
0x1400932e5  mov     r8, rcx
0x1400932e8  mov     [r15+8], rax
0x1400932ec  mov     [rax], r15
0x1400932ef  mov     [rdx+8], r15
0x1400932f3  mov     [r15+30h], rsi
0x1400932f7  xor     esi, esi
0x1400932f9  mov     word ptr [r15+40h], 101h
0x140093300  mov     al, [rdi+0A1Ah]
0x140093306  mov     [r15+46h], al
0x14009330a  lea     rax, [r15+6Ch]
0x14009330e  mov     dword ptr [r15+68h], 1
0x140093316  lea     edx, [rsi+3]
0x140093319  movups  xmm0, xmmword ptr [rcx+20h]
0x14009331d  mov     [rbp+57h+arg_18], rax
0x140093321  mov     rcx, r15
0x140093324  mov     qword ptr [rbp+57h+var_80.Data1], rsi
0x140093328  movdqu  xmmword ptr [rax], xmm0
0x14009332c  mov     eax, [rdi+0A48h]
0x140093332  mov     qword ptr [rsp+0C0h+var_A0], rax
0x140093337  call    ?ExecuteTransaction@SP_POOL@@QEAAJW4TRANSACTION_CODE@@PEAX11@Z; SP_POOL::ExecuteTransaction(TRANSACTION_CODE,void *,void *,void *)
0x14009333c  mov     ebx, eax
0x14009333e  test    eax, eax
0x140093340  js      loc_1400934FE
0x140093346  mov     rcx, [r15+30h]; this
0x14009334a  call    ?UpdateTolerance@SDB_POOL_CONFIG@@QEAAXXZ; SDB_POOL_CONFIG::UpdateTolerance(void)
0x14009334f  cmp     [rdi+0A48h], esi
0x140093355  jbe     loc_14009347A
0x14009335b  mov     r14d, esi
0x14009335e  mov     rsi, [rbp+57h+arg_18]
0x140093362  mov     eax, r14d
0x140093365  lea     rcx, [rax+rax*4]
0x140093369  shl     rcx, 6
0x14009336d  mov     rax, [rcx+r13+0E0h]
0x140093375  mov     rcx, rax; this
0x140093378  mov     [rbp+57h+arg_0], rax
0x14009337c  call    ?ResetTempDefaults@SP_DRIVE@@QEAAXXZ; SP_DRIVE::ResetTempDefaults(void)
0x140093381  mov     rdx, [r15+30h]; struct SDB_POOL_CONFIG *
0x140093385  mov     rcx, [rbp+57h+arg_0]; this
0x140093389  call    ?Connect@SP_DRIVE@@QEAAXPEAVSDB_POOL_CONFIG@@@Z; SP_DRIVE::Connect(SDB_POOL_CONFIG *)
0x14009338e  mov     rcx, [rbp+57h+arg_0]
0x140093392  lea     r8, [rbp+57h+var_70]
0x140093396  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14009339d  lea     rdx, [rbp+57h+var_60]
0x1400933a1  mov     [rsp+0C0h+var_90], rcx
0x1400933a6  mov     r9d, 7
0x1400933ac  mov     [rsp+0C0h+var_98], 0
0x1400933b5  movups  xmm0, xmmword ptr [rcx+1FCh]
0x1400933bc  lea     rcx, [rbp+57h+var_50]
0x1400933c0  mov     [rsp+0C0h+var_A0], 4
0x1400933c8  movups  xmm1, xmmword ptr [rax+170h]
0x1400933cf  movdqu  [rbp+57h+var_70], xmm0
0x1400933d4  movups  xmm0, xmmword ptr cs:GUID_SPACEPORT_DRIVE_NOTIFICATION.Data1
0x1400933db  movdqu  [rbp+57h+var_60], xmm1
0x1400933e0  movdqu  [rbp+57h+var_50], xmm0
0x1400933e5  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x1400933ea  mov     rax, [rbp+57h+arg_0]
0x1400933ee  lea     r8, [rbp+57h+var_50]
0x1400933f2  mov     [rsp+0C0h+var_90], rax
0x1400933f7  lea     rdx, [rbp+57h+var_60]
0x1400933fb  mov     [rsp+0C0h+var_98], r15
0x140093400  lea     rcx, [rbp+57h+var_70]
0x140093404  mov     [rsp+0C0h+var_A0], 0
0x14009340c  test    r14d, r14d
0x14009340f  jnz     short loc_140093437
0x140093411  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140093418  lea     r9d, [r14+2]
0x14009341c  movups  xmm1, xmmword ptr cs:GUID_SPACEPORT_POOL_NOTIFICATION.Data1
0x140093423  movdqu  [rbp+57h+var_50], xmm0
0x140093428  movups  xmm0, xmmword ptr [rsi]
0x14009342b  movdqu  [rbp+57h+var_70], xmm1
0x140093430  movdqu  [rbp+57h+var_60], xmm0
0x140093435  jmp     short loc_14009345D
0x140093437  movups  xmm0, xmmword ptr [rax+1FCh]
0x14009343e  mov     r9d, 8
0x140093444  movups  xmm1, xmmword ptr [rsi]
0x140093447  movdqu  [rbp+57h+var_50], xmm0
0x14009344c  movups  xmm0, xmmword ptr cs:GUID_SPACEPORT_DRIVE_NOTIFICATION.Data1
0x140093453  movdqu  [rbp+57h+var_60], xmm1
0x140093458  movdqu  [rbp+57h+var_70], xmm0
0x14009345d  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x140093462  inc     r14d
0x140093465  cmp     r14d, [rdi+0A48h]
0x14009346c  jb      loc_140093362
0x140093472  mov     rsi, qword ptr [rbp+57h+var_80.Data1]
0x140093476  mov     r14, [rbp+57h+arg_8]
0x14009347a  mov     eax, cs:dword_14007F050
0x140093480  cmp     eax, 5
0x140093483  jbe     short loc_1400934E2
0x140093485  mov     rdx, 400000000000h
0x14009348f  lea     rcx, dword_14007F050
0x140093496  call    _tlgKeywordOn
0x14009349b  test    al, al
0x14009349d  jz      short loc_1400934E2
0x14009349f  mov     eax, [rdi+0A50h]
0x1400934a5  lea     rdx, byte_14007520D
0x1400934ac  mov     [rbp+57h+arg_0], rax
0x1400934b0  mov     eax, [rdi+0A48h]
0x1400934b6  mov     [rbp+57h+arg_8], rax
0x1400934ba  mov     rax, [rbp+57h+arg_18]
  ... truncated ...
```
