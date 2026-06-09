# SP_CONTROL::Initialize(_DRIVER_OBJECT *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x1400a29a0`
- end: `0x1400a3783`
- name: `?Initialize@SP_CONTROL@@QEAAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@1@Z`
- size: `3555`
- prototype: `__int64 __fastcall(SP_CONTROL *this, struct _DRIVER_OBJECT *, struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a4294`

## callees

- `0x140015b40`
- `0x1400268c0`
- `0x140032f10`
- `0x14003335c`
- `0x140035ac4`
- `0x14008c760`
- `0x1400a2500`
- `0x1400a25b0`
- `0x1400a25ec`
- `0x1400a2740`
- `0x1400a29a0`
- `0x1400a413c`
- `0x1400a41f4`
- `0x1400ab89c`
- `0x1400ab9d0`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x1400a2ca1`
- `ntoskrnl!ExUuidCreate` at `0x1400a2e92`
- `ntoskrnl!ExUuidCreate` at `0x1400a2ca1`
- `ntoskrnl!ExUuidCreate` at `0x1400a2e92`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400a2d43`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400a2d43`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400a2d94`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400a2d94`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400a2d84`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400a2d84`
- `ntoskrnl!SeLockSubjectContext` at `0x1400a2d37`
- `ntoskrnl!SeLockSubjectContext` at `0x1400a2d37`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400a2d27`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400a2d27`
- `ntoskrnl!ExIsSoftBoot` at `0x1400a3727`
- `ntoskrnl!ExIsSoftBoot` at `0x1400a3727`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400a2d0d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400a2d0d`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400a2c45`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400a2c45`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400a2c68`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400a2c68`
- `ntoskrnl!NtQueryInformationProcess` at `0x1400a35dc`
- `ntoskrnl!NtQueryInformationProcess` at `0x1400a35dc`
- `ntoskrnl!SeAssignSecurity` at `0x1400a2d72`
- `ntoskrnl!SeAssignSecurity` at `0x1400a2d72`
- `ntoskrnl!SePublicDefaultDacl` at `0x1400a2cf9`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400a29f0`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400a29f0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2ac9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2b44`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2bec`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2ac9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2b44`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2bec`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400a2ce3`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400a2ce3`
- `ntoskrnl!KeInitializeEvent` at `0x1400a3760`
- `ntoskrnl!KeInitializeEvent` at `0x1400a3760`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2a25`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2a3c`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2a25`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2a3c`

## string_xrefs

- `0x1400a2ee3`: `EnableCacheLines`
- `0x1400a2f0e`: `EnableCacheLines`
- `0x1400a2f8e`: `DisableWriteThrough`
- `0x1400a2fb4`: `DisableWriteThrough`
- `0x1400a3087`: `ScrubDirtyReads`
- `0x1400a30ad`: `ScrubDirtyReads`
- `0x1400a3144`: `NumberOfDestageThreads`
- `0x1400a3170`: `NumberOfDestageThreads`
- `0x1400a319b`: `CacheDestageQueueDepth`
- `0x1400a31c9`: `CacheDestageQueueDepth`
- `0x1400a32a1`: `RepairQueueWidth`
- `0x1400a32cd`: `RepairQueueWidth`
- `0x1400a32f8`: `RepairQueueDepth`
- `0x1400a3321`: `RepairQueueDepth`

## pseudocode

```c
__int64 __fastcall SP_CONTROL::Initialize(
        SP_CONTROL *this,
        struct _DRIVER_OBJECT *a2,
        struct _DEVICE_OBJECT *a3,
        struct _DEVICE_OBJECT *a4)
{
  _DWORD *DeviceExtension; // rdi
  struct _DEVICE_OBJECT *v6; // r14
  PDEVICE_OBJECT v7; // rax
  NTSTATUS RegistryKey; // ebx
  ULONG MaximumProcessorCount; // eax
  ULONG v10; // edx
  void *v11; // rax
  unsigned int v12; // eax
  unsigned int i; // ebx
  void *v14; // rax
  unsigned int v15; // eax
  unsigned int j; // ebx
  void *v17; // rax
  unsigned int v18; // ecx
  unsigned int v19; // r15d
  unsigned int v20; // esi
  unsigned __int64 v21; // r12
  unsigned __int8 v22; // r9
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  unsigned __int8 v24; // r9
  _BYTE *v25; // rsi
  int v26; // eax
  struct _GUID v28; // [rsp+40h] [rbp-49h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-39h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v31; // [rsp+90h] [rbp+7h]
  __int64 v32; // [rsp+100h] [rbp+77h] BYREF

  v32 = (__int64)a3;
  DeviceExtension = WPP_MAIN_CB.DeviceExtension;
  v31 = 0;
  v6 = a3;
  *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1) = a2;
  SecurityDescriptor[0] = 0;
  *(_QWORD *)DeviceExtension = a3;
  SecurityDescriptor[1] = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v7 = IoAttachDeviceToDeviceStack(a3, a4);
  *((_QWORD *)DeviceExtension + 2) = v7;
  if ( v7 )
  {
    *((_QWORD *)DeviceExtension + 3) = a4;
    SP_CONTROL::GetSmbiosStrings((SP_CONTROL *)DeviceExtension);
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    v10 = 255;
    if ( MaximumProcessorCount < 0xFF )
      v10 = KeQueryMaximumProcessorCountEx(0xFFFFu);
    DeviceExtension[84] = v10;
    v11 = SC_ENV::Allocate((unsigned __int64)v10 << 7, 0x614C7053u, 0, 0);
    *((_QWORD *)DeviceExtension + 43) = v11;
    if ( !v11 )
      return (unsigned int)-1073741670;
    v12 = DeviceExtension[84];
    for ( i = 0; i < v12; ++i )
    {
      ExInitializeNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)DeviceExtension + 43) + ((unsigned __int64)i << 7)),
        SP_CONTROL::AllocatePacket,
        SP_CONTROL::FreePacket,
        0x200u,
        0x128u,
        0x614C7053u,
        0x20u);
      v12 = DeviceExtension[84];
    }
    v14 = SC_ENV::Allocate((unsigned __int64)v12 << 7, 0x614C7053u, 0, 0);
    *((_QWORD *)DeviceExtension + 44) = v14;
    if ( !v14 )
      return (unsigned int)-1073741670;
    v15 = DeviceExtension[84];
    for ( j = 0; j < v15; ++j )
    {
      ExInitializeNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)DeviceExtension + 44) + ((unsigned __int64)j << 7)),
        SP_CONTROL::AllocatePacket,
        SP_CONTROL::FreePacket,
        0x200u,
        0x5D0u,
        0x614C7053u,
        0x20u);
      v15 = DeviceExtension[84];
    }
    v17 = SC_ENV::Allocate((unsigned __int64)(7 * v15) << 7, 0x614C7053u, 0, 0);
    *((_QWORD *)DeviceExtension + 45) = v17;
    if ( v17 )
    {
      v18 = DeviceExtension[84];
      if ( 7 * v18 )
      {
        v19 = 4096;
        v20 = 0;
        do
        {
          if ( v20 && !(v20 % v18) )
            v19 *= 2;
          v21 = (unsigned __int64)v20 << 7;
          ExInitializeNPagedLookasideList(
            (PNPAGED_LOOKASIDE_LIST)(v21 + *((_QWORD *)DeviceExtension + 45)),
            0,
            0,
            0x200u,
            v19,
            0x614C7053u,
            0x100000 / v19);
          *(_WORD *)(*((_QWORD *)DeviceExtension + 45) + v21 + 18) = 0x100000 / v19;
          if ( v19 == 0x40000 )
            *(_WORD *)(v21 + *((_QWORD *)DeviceExtension + 45) + 18) = 16;
          v18 = DeviceExtension[84];
          ++v20;
        }
        while ( v20 < 7 * v18 );
        v6 = (struct _DEVICE_OBJECT *)v32;
      }
      RegistryKey = RtlCheckRegistryKey(1u, (PWSTR)L"Spaceport\\Parameters");
      if ( RegistryKey == -1073741772 )
        RegistryKey = RtlCreateRegistryKey(1u, (PWSTR)L"Spaceport\\Parameters");
      if ( RegistryKey >= 0 )
      {
        RegistryKey = SP_CONTROL::GetParameter(
                        (SP_CONTROL *)DeviceExtension,
                        L"PrimordialId",
                        (struct _GUID *)DeviceExtension + 23);
        if ( RegistryKey == -1073741772 )
        {
          RegistryKey = ExUuidCreate((UUID *)DeviceExtension + 23);
          if ( RegistryKey < 0 )
            return (unsigned int)RegistryKey;
          v28 = (struct _GUID)*((_OWORD *)DeviceExtension + 23);
          RegistryKey = SP_CONTROL::SetParameter((SP_CONTROL *)DeviceExtension, L"PrimordialId", &v28, v22);
        }
        if ( RegistryKey >= 0 )
        {
          RegistryKey = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
          if ( RegistryKey >= 0 )
          {
            RegistryKey = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, SePublicDefaultDacl, 0);
            if ( RegistryKey >= 0 )
            {
              SeCaptureSubjectContext(&SubjectContext);
              SeLockSubjectContext(&SubjectContext);
              FileObjectGenericMapping = IoGetFileObjectGenericMapping();
              RegistryKey = SeAssignSecurity(
                              0,
                              SecurityDescriptor,
                              (PSECURITY_DESCRIPTOR *)DeviceExtension + 48,
                              0,
                              &SubjectContext,
                              FileObjectGenericMapping,
                              PagedPool);
              SeUnlockSubjectContext(&SubjectContext);
              SeReleaseSubjectContext(&SubjectContext);
              if ( RegistryKey >= 0 )
              {
                DeviceExtension[98] = 224;
                DeviceExtension[113] = 0x40000;
                *((_QWORD *)DeviceExtension + 62) = 0x800000;
                *((_QWORD *)DeviceExtension + 63) = 0x800000;
                DeviceExtension[118] = 0x40000;
                DeviceExtension[134] = 0x40000;
                *((_QWORD *)DeviceExtension + 66) = 0x8000000;
                *((_QWORD *)DeviceExtension + 68) = 0x8000000;
                DeviceExtension[112] = 12288;
                DeviceExtension[119] = 600;
                *((_QWORD *)DeviceExtension + 60) = 300000;
                DeviceExtension[122] = -1;
                *((_BYTE *)DeviceExtension + 494) = 0;
                *((_QWORD *)DeviceExtension + 65) = 0x2000000;
                DeviceExtension[135] = 4;
                DeviceExtension[140] = 1800;
                DeviceExtension[141] = 32;
                DeviceExtension[142] = 10000;
                DeviceExtension[143] = 1;
                DeviceExtension[149] = 86400;
                *((_BYTE *)DeviceExtension + 612) = 0;
                RegistryKey = SP_CONTROL::GetParameter(
                                (SP_CONTROL *)DeviceExtension,
                                L"ControlId",
                                (struct _GUID *)DeviceExtension + 25);
                if ( RegistryKey == -1073741772 )
                {
                  RegistryKey = ExUuidCreate((UUID *)DeviceExtension + 25);
                  if ( RegistryKey < 0 )
                    return (unsigned int)RegistryKey;
                  v28 = (struct _GUID)*((_OWORD *)DeviceExtension + 25);
                  RegistryKey = SP_CONTROL::SetParameter((SP_CONTROL *)DeviceExtension, L"ControlId", &v28, v24);
                }
                if ( RegistryKey >= 0 )
                {
                  Feature_WriteCacheLines__private_IsEnabledPreCheck();
                  v25 = (char *)DeviceExtension + 441;
                  RegistryKey = SP_CONTROL::GetParameter(
                                  (SP_CONTROL *)DeviceExtension,
                                  L"EnableCacheLines",
                                  (unsigned __int8 *)DeviceExtension + 441);
                  if ( RegistryKey == -1073741772 || *v25 != 1 )
                  {
                    *v25 = 1;
                    LODWORD(v32) = 1;
                    RegistryKey = SP_CONTROL::SetParameter(
                                    (SP_CONTROL *)DeviceExtension,
                                    L"EnableCacheLines",
                                    4u,
                                    &v32,
                                    4u,
                                    1u);
                  }
                  if ( RegistryKey >= 0 )
                  {
                    RegistryKey = SP_CONTROL::GetParameter(
                                    (SP_CONTROL *)DeviceExtension,
                                    L"AllowPagedPool",
                                    (unsigned __int8 *)DeviceExtension + 442);
                    if ( RegistryKey == -1073741772 )
                    {
                      *((_BYTE *)DeviceExtension + 442) = 0;
                      LODWORD(v32) = 0;
                      RegistryKey = SP_CONTROL::SetParameter(
                                      (SP_CONTROL *)DeviceExtension,
                                      L"AllowPagedPool",
                                      4u,
                                      &v32,
                                      4u,
                                      1u);
                    }
                    if ( RegistryKey >= 0 )
                    {
                      RegistryKey = SP_CONTROL::GetParameter(
                                      (SP_CONTROL *)DeviceExtension,
                                      L"DisableWriteThrough",
                                      (unsigned __int8 *)DeviceExtension + 444);
                      if ( RegistryKey == -1073741772 )
                      {
                        *((_BYTE *)DeviceExtension + 444) = 0;
                        LODWORD(v32) = 0;
                        RegistryKey = SP_CONTROL::SetParameter(
                                        (SP_CONTROL *)DeviceExtension,
                                        L"DisableWriteThrough",
                                        4u,
                                        &v32,
                                        4u,
                                        1u);
                      }
                      if ( RegistryKey >= 0 )
                      {
                        RegistryKey = SP_CONTROL::GetParameter(
                                        (SP_CONTROL *)DeviceExtension,
                                        L"DisableCrashConsistency",
                                        (unsigned __int8 *)DeviceExtension + 445);
                        if ( RegistryKey == -1073741772 )
                        {
                          *((_BYTE *)DeviceExtension + 445) = 0;
                          LODWORD(v32) = 0;
                          RegistryKey = SP_CONTROL::SetParameter(
                                          (SP_CONTROL *)DeviceExtension,
                                          L"DisableCrashConsistency",
                                          4u,
                                          &v32,
                                          4u,
                                          1u);
                        }
                        if ( RegistryKey >= 0 )
                        {
                          RegistryKey = SP_CONTROL::GetParameter(
                                          (SP_CONTROL *)DeviceExtension,
                                          L"DisableDiscovery",
                                          (unsigned __int8 *)DeviceExtension + 433);
                          if ( RegistryKey == -1073741772 )
                          {
                            *((_BYTE *)DeviceExtension + 433) = 0;
                            LODWORD(v32) = 0;
                            RegistryKey = SP_CONTROL::SetParameter(
                                            (SP_CONTROL *)DeviceExtension,
                                            L"DisableDiscovery",
                                            4u,
                                            &v32,
                                            4u,
                                            1u);
                          }
                          if ( RegistryKey >= 0 )
                          {
                            RegistryKey = SP_CONTROL::GetParameter(
                                            (SP_CONTROL *)DeviceExtension,
                                            L"ScrubDirtyReads",
                                            (unsigned __int8 *)DeviceExtension + 493);
                            if ( RegistryKey == -1073741772 )
                            {
                              *((_BYTE *)DeviceExtension + 493) = 0;
                              LODWORD(v32) = 0;
                              RegistryKey = SP_CONTROL::SetParameter(
                                              (SP_CONTROL *)DeviceExtension,
                                              L"ScrubDirtyReads",
                                              4u,
                                              &v32,
                                              4u,
                                              1u);
                            }
                            if ( RegistryKey >= 0 )
                            {
                              DeviceExtension[128] = -8;
                              RegistryKey = SP_CONTROL::GetParameter(
                                              (SP_CONTROL *)DeviceExtension,
                                              L"MinimumParityLogSize",
                                              0xBu,
                                              DeviceExtension + 128);
                              if ( RegistryKey == -1073741772 )
                              {
                                *((_QWORD *)DeviceExtension + 64) = 0x40000000;
                                v32 = 0x40000000;
                                RegistryKey = SP_CONTROL::SetParameter(
                                                (SP_CONTROL *)DeviceExtension,
                                                L"MinimumParityLogSize",
                                                0xBu,
                                                &v32,
                                                8u,
                                                1u);
                              }
                              if ( RegistryKey >= 0 )
                              {
                                RegistryKey = SP_CONTROL::GetParameter(
                                                (SP_CONTROL *)DeviceExtension,
                                                L"NumberOfDestageThreads",
                                                4u,
                                                DeviceExtension + 138);
                                if ( RegistryKey == -1073741772 )
                                {
                                  DeviceExtension[138] = -1;
                                  LODWORD(v32) = -1;
                                  RegistryKey = SP_CONTROL::SetParameter(
                                                  (SP_CONTROL *)DeviceExtension,
                                                  L"NumberOfDestageThreads",
                                                  4u,
                                                  &v32,
                                                  4u,
                                                  1u);
                                }
                                if ( RegistryKey >= 0 )
                                {
                                  RegistryKey = SP_CONTROL::GetParameter(
                                                  (SP_CONTROL *)DeviceExtension,
                                                  L"CacheDestageQueueDepth",
                                                  4u,
                                                  DeviceExtension + 139);
                                  if ( RegistryKey == -1073741772 )
                                  {
                                    DeviceExtension[139] = 16;
                                    LODWORD(v32) = 16;
                                    RegistryKey = SP_CONTROL::SetParameter(
                                                    (SP_CONTROL *)DeviceExtension,
                                                    L"CacheDestageQueueDepth",
                                                    4u,
                                                    &v32,
                                                    4u,
                                                    1u);
                                  }
                                  if ( RegistryKey >= 0 )
                                  {
                                    RegistryKey = SP_CONTROL::GetParameter(
                                                    (SP_CONTROL *)DeviceExtension,
                                                    L"ReallocationInterval",
                                                    4u,
                                                    DeviceExtension + 114);
                                    if ( RegistryKey == -1073741772 )
                                    {
                                      DeviceExtension[114] = 0;
                                      LODWORD(v32) = 0;
                                      RegistryKey = SP_CONTROL::SetParameter(
                                                      (SP_CONTROL *)DeviceExtension,
                                                      L"ReallocationInterval",
                                                      4u,
                                                      &v32,
                                                      4u,
                                                      1u);
                                    }
                                    if ( RegistryKey >= 0 )
                                    {
                                      RegistryKey = SP_CONTROL::GetParameter(
                                                      (SP_CONTROL *)DeviceExtension,
                                                      L"ReallocationsPerInterval",
                                                      4u,
                                                      DeviceExtension + 115);
                                      if ( RegistryKey == -1073741772 )
                                      {
                                        DeviceExtension[115] = -1;
                                        LODWORD(v32) = -1;
                                        RegistryKey = SP_CONTROL::SetParameter(
                                                        (SP_CONTROL *)DeviceExtension,
                                                        L"ReallocationsPerInterval",
                                                        4u,
                                                        &v32,
                                                        4u,
                                                        1u);
                                      }
                                      if ( RegistryKey >= 0 )
                                      {
                                        RegistryKey = SP_CONTROL::GetParameter(
                                                        (SP_CONTROL *)DeviceExtension,
                                                        L"RepairQueueWidth",
                                                        4u,
                                                        DeviceExtension + 116);
                                        if ( RegistryKey == -1073741772 )
                                        {
                                          DeviceExtension[116] = -1;
                                          LODWORD(v32) = -1;
                                          RegistryKey = SP_CONTROL::SetParameter(
                                                          (SP_CONTROL *)DeviceExtension,
                                                          L"RepairQueueWidth",
                                                          4u,
                                                          &v32,
                                                          4u,
                                                          1u);
                                        }
                                        if ( RegistryKey >= 0 )
                                        {
                                          RegistryKey = SP_CONTROL::GetParameter(
                                                          (SP_CONTROL *)DeviceExtension,
                                                          L"RepairQueueDepth",
                                                          4u,
                                                          DeviceExtension + 117);
                                          if ( RegistryKey == -1073741772 )
                                          {
                                            DeviceExtension[117] = 4;
                                            LODWORD(v32) = 4;
                                            RegistryKey = SP_CONTROL::SetParameter(
                                                            (SP_CONTROL *)DeviceExtension,
                                                            L"RepairQueueDepth",
                                                            4u,
                                                            &v32,
                                                            4u,
                                                            1u);
                                          }
                                          if ( RegistryKey >= 0 )
                                          {
                                            RegistryKey = SP_CONTROL::GetParameter(
                                                            (SP_CONTROL *)DeviceExtension,
                                                            L"SwTimeout",
                                                            4u,
                                                            DeviceExtension + 144);
                                            if ( RegistryKey == -1073741772 )
                                            {
                                              DeviceExtension[144] = -1;
                                              LODWORD(v32) = -1;
                                              RegistryKey = SP_CONTROL::SetParameter(
                                                              (SP_CONTROL *)DeviceExtension,
                                                              L"SwTimeout",
                                                              4u,
                                                              &v32,
                                                              4u,
                                                              1u);
                                            }
                                            if ( RegistryKey >= 0 )
                                            {
                                              RegistryKey = SP_CONTROL::GetParameter(
                                                              (SP_CONTROL *)DeviceExtension,
                                                              L"HwTimeout",
                                                              4u,
                                                              DeviceExtension + 145);
                                              if ( RegistryKey == -1073741772 )
                                              {
                                                DeviceExtension[145] = 6000;
                                                LODWORD(v32) = 6000;
                                                RegistryKey = SP_CONTROL::SetParameter(
                                                                (SP_CONTROL *)DeviceExtension,
                                                                L"HwTimeout",
                                                                4u,
                                                                &v32,
                                                                4u,
                                                                1u);
                                              }
                                              if ( RegistryKey >= 0 )
                                              {
                                                RegistryKey = SP_CONTROL::GetParameter(
                                                                (SP_CONTROL *)DeviceExtension,
                                                                L"ResetTimeout",
                                                                4u,
                                                                DeviceExtension + 146);
                                                if ( RegistryKey == -1073741772 )
                                                {
                                                  DeviceExtension[146] = 15000;
                                                  LODWORD(v32) = 15000;
                                                  RegistryKey = SP_CONTROL::SetParameter(
                                                                  (SP_CONTROL *)DeviceExtension,
                                                                  L"ResetTimeout",
                                                                  4u,
                                                                  &v32,
                                                                  4u,
                                                                  1u);
                                                }
                                                if ( RegistryKey >= 0 )
                                                {
                                                  RegistryKey = SP_CONTROL::GetParameter(
                                                                  (SP_CONTROL *)DeviceExtension,
                                                                  L"ResetUnresponsiveTimeout",
                                                                  4u,
                                                                  DeviceExtension + 147);
                                                  if ( RegistryKey == -1073741772 )
                                                  {
                                                    DeviceExtension[147] = 10000;
                                                    LODWORD(v32) = 10000;
                                                    RegistryKey = SP_CONTROL::SetParameter(
                                                                    (SP_CONTROL *)DeviceExtension,
                                                                    L"ResetUnresponsiveTimeout",
                                                                    4u,
                                                                    &v32,
                                                                    4u,
                                                                    1u);
                                                  }
                                                  if ( RegistryKey >= 0 )
                                                  {
                                                    RegistryKey = SP_CONTROL::GetParameter(
                                                                    (SP_CONTROL *)DeviceExtension,
                                                                    L"ResetInterval",
                                                                    4u,
                                                                    DeviceExtension + 148);
                                                    if ( RegistryKey == -1073741772 )
                                                    {
                                                      DeviceExtension[148] = 20000;
                                                      LODWORD(v32) = 20000;
                                                      RegistryKey = SP_CONTROL::SetParameter(
                                                                      (SP_CONTROL *)DeviceExtension,
                                                                      L"ResetInterval",
                                                                      4u,
                                                                      &v32,
                                                                      4u,
                                                                      1u);
                                                    }
                                                    if ( RegistryKey >= 0 )
                                                    {
                                                      RegistryKey = SP_CONTROL::GetParameter(
                                                                      (SP_CONTROL *)DeviceExtension,
                                                                      L"NumberOfRegionLocks",
                                                                      4u,
                                                                      DeviceExtension + 151);
                                                      if ( RegistryKey == -1073741772 )
                                                      {
                                                        DeviceExtension[151] = 256;
                                                        LODWORD(v32) = 256;
                                                        RegistryKey = SP_CONTROL::SetParameter(
                                                                        (SP_CONTROL *)DeviceExtension,
                                                                        L"NumberOfRegionLocks",
                                                                        4u,
                                                                        &v32,
                                                                        4u,
                                                                        1u);
                                                      }
                                                      if ( RegistryKey >= 0 )
                                                      {
                                                        RegistryKey = SP_CONTROL::GetParameter(
                                                                        (SP_CONTROL *)DeviceExtension,
                                                                        L"ScrubDelay",
                                                                        4u,
                                                                        DeviceExtension + 152);
                                                        if ( RegistryKey == -1073741772 )
                                                        {
                                                          DeviceExtension[152] = 900000;
                                                          LODWORD(v32) = 900000;
                                                          RegistryKey = SP_CONTROL::SetParameter(
                                                                          (SP_CONTROL *)DeviceExtension,
                                                                          L"ScrubDelay",
                                                                          4u,
                                                                          &v32,
                                                                          4u,
                                                                          1u);
                                                        }
                                                        if ( RegistryKey >= 0 )
                                                        {
                                                          RegistryKey = SP_CONTROL_WORK::Initialize((SP_CONTROL_WORK *)(DeviceExtension + 156));
                                                          if ( RegistryKey >= 0 )
                                                          {
                                                            RegistryKey = NtQueryInformationProcess(
                                                                            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                                                            ProcessCookie,
                                                                            DeviceExtension + 190,
                                                                            4u,
                                                                            0);
                                                            if ( RegistryKey >= 0 )
                                                            {
                                                              SC_ENV::QueryPerformanceCounter((unsigned __int64 *)DeviceExtension + 96);
                                                              RegistryKey = SP_WORKITEM::Initialize(
                                                                              (SP_WORKITEM *)(DeviceExtension + 194),
                                                                              v6,
                                                                              (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SpReadyCallback,
                                                                              0);
                                                              if ( RegistryKey >= 0 )
                                                              {
                                                                RegistryKey = SP_WORKITEM::Initialize(
                                                                                (SP_WORKITEM *)(DeviceExtension + 246),
                                                                                v6,
                                                                                (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SpDriveReadyCallback,
                                                                                0);
                                                                if ( RegistryKey >= 0 )
                                                                {
                                                                  RegistryKey = SP_WORKITEM::Initialize(
                                                                                  (SP_WORKITEM *)(DeviceExtension + 298),
                                                                                  v6,
                                                                                  (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SpDriveRequestRepairCallback,
                                                                                  0);
                                                                  if ( RegistryKey >= 0 )
                                                                  {
                                                                    RegistryKey = SP_WORKITEM::Initialize(
                                                                                    (SP_WORKITEM *)(DeviceExtension + 350),
                                                                                    v6,
                                                                                    (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SpWnfCallback,
                                                                                    DeviceExtension + 402);
                                                                    if ( RegistryKey >= 0 )
                                                                    {
                                                                      RegistryKey = SP_WORKITEM::Initialize(
                                                                                      (SP_WORKITEM *)(DeviceExtension + 404),
                                                                                      v6,
                                                                                      (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SpEnclosureCallback,
                                                                                      0);
                                                                      if ( RegistryKey >= 0 )
                                                                      {
                                                                        RegistryKey = SP_WORKITEM::Initialize(
                                                                                        (SP_WORKITEM *)(DeviceExtension + 456),
                                                                                        v6,
                                                                                        (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SpRebalanceCallback,
                                                                                        0);
                                                                        if ( RegistryKey >= 0 )
                                                                        {
                                                                          RegistryKey = SP_WORKITEM::Initialize(
                                                                                          (SP_WORKITEM *)(DeviceExtension + 508),
                                                                                          v6,
                                                                                          (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SpPrmCallback,
                                                                                          0);
                                                                          if ( RegistryKey >= 0 )
                                                                          {
                                                                            RegistryKey = SP_WORKITEM::Initialize(
                                                                                            (SP_WORKITEM *)(DeviceExtension + 560),
                                                                                            v6,
                                                                                            (int (*)(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *))SpCensusCallback,
                                                                                            0);
                                                                            if ( RegistryKey >= 0 )
                                                                            {
                                                                              RegistryKey = SP_ATTRIBUTES::Initialize(
                                                                                              (SP_ATTRIBUTES *)(DeviceExtension + 612),
                                                                                              v6);
                                                                              if ( RegistryKey >= 0 )
                                                                              {
                                                                                if ( (unsigned __int8)ExIsSoftBoot() )
                                                                                  v26 = SP_CONTROL::InitializeKsrData((SP_CONTROL *)DeviceExtension);
                                                                                else
                                                                                  v26 = SP_CONTROL::InitializeBootData((SP_CONTROL *)DeviceExtension);
                                                                                RegistryKey = v26;
                                                                                if ( v26 >= 0 )
                                                                                {
                                                                                  *(_DWORD *)(*(_QWORD *)DeviceExtension
                                                                                            + 48LL) &= ~0x80u;
                                                                                  KeInitializeEvent(
                                                                                    (PRKEVENT)(DeviceExtension + 734),
                                                                                    NotificationEvent,
                                                                                    0);
                                                                                }
                                                                              }
                                                                            }
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741810;
  }
  return (unsigned int)RegistryKey;
}

```

## disassembly

```asm
0x1400a29a0  mov     [rsp-8+arg_10], r8
0x1400a29a5  push    rbp
0x1400a29a6  push    rbx
0x1400a29a7  push    rsi
0x1400a29a8  push    rdi
0x1400a29a9  push    r12
0x1400a29ab  push    r13
0x1400a29ad  push    r14
0x1400a29af  push    r15
0x1400a29b1  lea     rbp, [rsp-1Fh]
0x1400a29b6  sub     rsp, 0A8h
0x1400a29bd  mov     rdi, cs:WPP_MAIN_CB.DeviceExtension
0x1400a29c4  xorps   xmm0, xmm0
0x1400a29c7  xor     eax, eax
0x1400a29c9  mov     rcx, r8; SourceDevice
0x1400a29cc  mov     rbx, r9
0x1400a29cf  mov     [rbp+57h+var_50], rax
0x1400a29d3  mov     r14, r8
0x1400a29d6  mov     [rdi+8], rdx
0x1400a29da  mov     rdx, r9; TargetDevice
0x1400a29dd  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1400a29e1  mov     [rdi], r8
0x1400a29e4  movups  [rbp+57h+var_60], xmm0
0x1400a29e8  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1400a29ec  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1400a29f0  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1400a29f7  nop     dword ptr [rax+rax+00h]
0x1400a29fc  xor     r13d, r13d
0x1400a29ff  mov     [rdi+10h], rax
0x1400a2a03  test    rax, rax
0x1400a2a06  jnz     short loc_1400A2A12
0x1400a2a08  mov     ebx, 0C000000Eh
0x1400a2a0d  jmp     loc_1400A376C
0x1400a2a12  mov     rcx, rdi; this
0x1400a2a15  mov     [rdi+18h], rbx
0x1400a2a19  call    ?GetSmbiosStrings@SP_CONTROL@@QEAAJXZ; SP_CONTROL::GetSmbiosStrings(void)
0x1400a2a1e  mov     ebx, 0FFFFh
0x1400a2a23  mov     ecx, ebx; GroupNumber
0x1400a2a25  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400a2a2c  nop     dword ptr [rax+rax+00h]
0x1400a2a31  mov     edx, 0FFh
0x1400a2a36  cmp     eax, edx
0x1400a2a38  jnb     short loc_1400A2A4A
0x1400a2a3a  mov     ecx, ebx; GroupNumber
0x1400a2a3c  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400a2a43  nop     dword ptr [rax+rax+00h]
0x1400a2a48  mov     edx, eax
0x1400a2a4a  mov     ecx, edx
0x1400a2a4c  mov     esi, 614C7053h
0x1400a2a51  mov     [rdi+150h], edx
0x1400a2a57  xor     r9d, r9d; unsigned int
0x1400a2a5a  shl     rcx, 7; unsigned __int64
0x1400a2a5e  mov     edx, esi; unsigned int
0x1400a2a60  xor     r8d, r8d; unsigned __int8
0x1400a2a63  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400a2a68  mov     [rdi+158h], rax
0x1400a2a6f  test    rax, rax
0x1400a2a72  jnz     short loc_1400A2A7E
0x1400a2a74  mov     ebx, 0C000009Ah
0x1400a2a79  jmp     loc_1400A376C
0x1400a2a7e  mov     eax, [rdi+150h]
0x1400a2a84  mov     ebx, r13d
0x1400a2a87  mov     r15d, 200h
0x1400a2a8d  mov     r12d, 1
0x1400a2a93  test    eax, eax
0x1400a2a95  jz      short loc_1400A2AE2
0x1400a2a97  mov     [rsp+0E0h+Depth], 20h ; ' '; Depth
0x1400a2a9e  lea     r8, ?FreePacket@SP_CONTROL@@SAXPEAX@Z; Free
0x1400a2aa5  mov     ecx, ebx
0x1400a2aa7  lea     rdx, ?AllocatePacket@SP_CONTROL@@SAPEAXW4_POOL_TYPE@@_KK@Z; Allocate
0x1400a2aae  shl     rcx, 7
0x1400a2ab2  mov     r9d, r15d; Flags
0x1400a2ab5  add     rcx, [rdi+158h]; Lookaside
0x1400a2abc  mov     [rsp+0E0h+Tag], esi; Tag
0x1400a2ac0  mov     [rsp+0E0h+Size], 128h; Size
0x1400a2ac9  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400a2ad0  nop     dword ptr [rax+rax+00h]
0x1400a2ad5  mov     eax, [rdi+150h]
0x1400a2adb  add     ebx, r12d
0x1400a2ade  cmp     ebx, eax
0x1400a2ae0  jb      short loc_1400A2A97
0x1400a2ae2  mov     ecx, eax
0x1400a2ae4  xor     r9d, r9d; unsigned int
0x1400a2ae7  shl     rcx, 7; unsigned __int64
0x1400a2aeb  xor     r8d, r8d; unsigned __int8
0x1400a2aee  mov     edx, esi; unsigned int
0x1400a2af0  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400a2af5  mov     [rdi+160h], rax
0x1400a2afc  test    rax, rax
0x1400a2aff  jz      loc_1400A2A74
0x1400a2b05  mov     eax, [rdi+150h]
0x1400a2b0b  mov     ebx, r13d
0x1400a2b0e  test    eax, eax
0x1400a2b10  jz      short loc_1400A2B60
0x1400a2b12  mov     [rsp+0E0h+Depth], 20h ; ' '; Depth
0x1400a2b19  lea     r8, ?FreePacket@SP_CONTROL@@SAXPEAX@Z; Free
0x1400a2b20  mov     ecx, ebx
0x1400a2b22  lea     rdx, ?AllocatePacket@SP_CONTROL@@SAPEAXW4_POOL_TYPE@@_KK@Z; Allocate
0x1400a2b29  shl     rcx, 7
0x1400a2b2d  mov     r9d, r15d; Flags
0x1400a2b30  add     rcx, [rdi+160h]; Lookaside
0x1400a2b37  mov     [rsp+0E0h+Tag], esi; Tag
0x1400a2b3b  mov     [rsp+0E0h+Size], 5D0h; Size
0x1400a2b44  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400a2b4b  nop     dword ptr [rax+rax+00h]
0x1400a2b50  mov     eax, [rdi+150h]
0x1400a2b56  add     ebx, r12d
0x1400a2b59  cmp     ebx, eax
0x1400a2b5b  jb      short loc_1400A2B12
0x1400a2b5d  xor     r13d, r13d
0x1400a2b60  imul    ecx, eax, 7
0x1400a2b63  xor     r9d, r9d; unsigned int
0x1400a2b66  xor     r8d, r8d; unsigned __int8
0x1400a2b69  mov     edx, esi; unsigned int
0x1400a2b6b  shl     rcx, 7; unsigned __int64
0x1400a2b6f  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400a2b74  mov     [rdi+168h], rax
0x1400a2b7b  test    rax, rax
0x1400a2b7e  jz      loc_1400A2A74
0x1400a2b84  mov     ecx, [rdi+150h]
0x1400a2b8a  imul    eax, ecx, 7
0x1400a2b8d  test    eax, eax
0x1400a2b8f  jz      loc_1400A2C3B
0x1400a2b95  mov     r15d, 1000h
0x1400a2b9b  mov     esi, r13d
0x1400a2b9e  test    esi, esi
0x1400a2ba0  jz      short loc_1400A2BAF
0x1400a2ba2  xor     edx, edx
0x1400a2ba4  mov     eax, esi
0x1400a2ba6  div     ecx
0x1400a2ba8  test    edx, edx
0x1400a2baa  jnz     short loc_1400A2BAF
0x1400a2bac  add     r15d, r15d
0x1400a2baf  mov     rcx, [rdi+168h]
0x1400a2bb6  xor     edx, edx
0x1400a2bb8  mov     eax, 100000h
0x1400a2bbd  mov     r12d, esi
0x1400a2bc0  div     r15d
0x1400a2bc3  mov     edx, r15d
0x1400a2bc6  mov     r9d, 200h; Flags
0x1400a2bcc  mov     ebx, eax
0x1400a2bce  shl     r12, 7
0x1400a2bd2  mov     [rsp+0E0h+Depth], bx; Depth
0x1400a2bd7  add     rcx, r12; Lookaside
0x1400a2bda  mov     [rsp+0E0h+Tag], 614C7053h; Tag
0x1400a2be2  xor     r8d, r8d; Free
0x1400a2be5  mov     [rsp+0E0h+Size], rdx; Size
0x1400a2bea  xor     edx, edx; Allocate
0x1400a2bec  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400a2bf3  nop     dword ptr [rax+rax+00h]
0x1400a2bf8  mov     rcx, [rdi+168h]
0x1400a2bff  mov     [rcx+r12+12h], bx
0x1400a2c05  cmp     r15d, 40000h
0x1400a2c0c  jnz     short loc_1400A2C1D
0x1400a2c0e  mov     rax, [rdi+168h]
0x1400a2c15  mov     word ptr [r12+rax+12h], 10h
0x1400a2c1d  mov     ecx, [rdi+150h]
0x1400a2c23  mov     r12d, 1
0x1400a2c29  imul    eax, ecx, 7
0x1400a2c2c  add     esi, r12d
0x1400a2c2f  cmp     esi, eax
0x1400a2c31  jb      loc_1400A2B9E
0x1400a2c37  mov     r14, [rbp+57h+arg_10]
0x1400a2c3b  lea     rdx, Path; "Spaceport\\Parameters"
0x1400a2c42  mov     ecx, r12d; RelativeTo
0x1400a2c45  call    cs:__imp_RtlCheckRegistryKey
0x1400a2c4c  nop     dword ptr [rax+rax+00h]
0x1400a2c51  mov     r15d, 0C0000034h
0x1400a2c57  mov     ebx, eax
0x1400a2c59  cmp     eax, r15d
0x1400a2c5c  jnz     short loc_1400A2C76
0x1400a2c5e  lea     rdx, Path; "Spaceport\\Parameters"
0x1400a2c65  mov     ecx, r12d; RelativeTo
0x1400a2c68  call    cs:__imp_RtlCreateRegistryKey
0x1400a2c6f  nop     dword ptr [rax+rax+00h]
0x1400a2c74  mov     ebx, eax
0x1400a2c76  test    ebx, ebx
0x1400a2c78  js      loc_1400A376C
0x1400a2c7e  lea     rsi, [rdi+170h]
0x1400a2c85  mov     rcx, rdi; this
0x1400a2c88  mov     r8, rsi; struct _GUID *
0x1400a2c8b  lea     rdx, aPrimordialid; "PrimordialId"
0x1400a2c92  call    ?GetParameter@SP_CONTROL@@QEAAJPEAGPEAU_GUID@@@Z; SP_CONTROL::GetParameter(ushort *,_GUID *)
0x1400a2c97  mov     ebx, eax
0x1400a2c99  cmp     eax, r15d
0x1400a2c9c  jnz     short loc_1400A2CD4
0x1400a2c9e  mov     rcx, rsi; Uuid
0x1400a2ca1  call    cs:__imp_ExUuidCreate
0x1400a2ca8  nop     dword ptr [rax+rax+00h]
0x1400a2cad  mov     ebx, eax
0x1400a2caf  test    eax, eax
0x1400a2cb1  js      loc_1400A376C
0x1400a2cb7  movups  xmm0, xmmword ptr [rsi]
0x1400a2cba  lea     r8, [rbp+57h+var_A0]; struct _GUID
0x1400a2cbe  mov     rcx, rdi; this
0x1400a2cc1  lea     rdx, aPrimordialid; "PrimordialId"
0x1400a2cc8  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x1400a2ccd  call    ?SetParameter@SP_CONTROL@@QEAAJPEAGU_GUID@@E@Z; SP_CONTROL::SetParameter(ushort *,_GUID,uchar)
0x1400a2cd2  mov     ebx, eax
0x1400a2cd4  test    ebx, ebx
0x1400a2cd6  js      loc_1400A376C
0x1400a2cdc  mov     edx, r12d; Revision
0x1400a2cdf  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400a2ce3  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400a2cea  nop     dword ptr [rax+rax+00h]
0x1400a2cef  mov     ebx, eax
0x1400a2cf1  test    eax, eax
0x1400a2cf3  js      loc_1400A376C
0x1400a2cf9  mov     r8, cs:__imp_SePublicDefaultDacl
0x1400a2d00  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400a2d04  xor     r9d, r9d; DaclDefaulted
0x1400a2d07  mov     dl, r12b; DaclPresent
0x1400a2d0a  mov     r8, [r8]; Dacl
0x1400a2d0d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400a2d14  nop     dword ptr [rax+rax+00h]
0x1400a2d19  mov     ebx, eax
0x1400a2d1b  test    eax, eax
0x1400a2d1d  js      loc_1400A376C
0x1400a2d23  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400a2d27  call    cs:__imp_SeCaptureSubjectContext
0x1400a2d2e  nop     dword ptr [rax+rax+00h]
0x1400a2d33  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400a2d37  call    cs:__imp_SeLockSubjectContext
0x1400a2d3e  nop     dword ptr [rax+rax+00h]
0x1400a2d43  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400a2d4a  nop     dword ptr [rax+rax+00h]
0x1400a2d4f  mov     dword ptr [rsp+0E0h+Depth], r12d; PoolType
0x1400a2d54  lea     r8, [rdi+180h]; NewDescriptor
0x1400a2d5b  mov     qword ptr [rsp+0E0h+Tag], rax; GenericMapping
0x1400a2d60  lea     rdx, [rbp+57h+SecurityDescriptor]; ExplicitDescriptor
0x1400a2d64  lea     rax, [rbp+57h+SubjectContext]
0x1400a2d68  xor     r9d, r9d; IsDirectoryObject
0x1400a2d6b  xor     ecx, ecx; ParentDescriptor
0x1400a2d6d  mov     [rsp+0E0h+Size], rax; SubjectContext
0x1400a2d72  call    cs:__imp_SeAssignSecurity
0x1400a2d79  nop     dword ptr [rax+rax+00h]
0x1400a2d7e  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400a2d82  mov     ebx, eax
0x1400a2d84  call    cs:__imp_SeUnlockSubjectContext
0x1400a2d8b  nop     dword ptr [rax+rax+00h]
0x1400a2d90  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400a2d94  call    cs:__imp_SeReleaseSubjectContext
0x1400a2d9b  nop     dword ptr [rax+rax+00h]
0x1400a2da0  test    ebx, ebx
0x1400a2da2  js      loc_1400A376C
0x1400a2da8  mov     ecx, 40000h
0x1400a2dad  mov     dword ptr [rdi+188h], 0E0h
0x1400a2db7  mov     eax, 800000h
0x1400a2dbc  mov     [rdi+1C4h], ecx
0x1400a2dc2  mov     [rdi+1F0h], rax
0x1400a2dc9  lea     rsi, [rdi+190h]
0x1400a2dd0  mov     [rdi+1F8h], rax
0x1400a2dd7  lea     rdx, aControlid; "ControlId"
0x1400a2dde  mov     eax, 8000000h
0x1400a2de3  mov     [rdi+1D8h], ecx
0x1400a2de9  mov     [rdi+218h], ecx
0x1400a2def  mov     r15d, 4
0x1400a2df5  mov     r8, rsi; struct _GUID *
0x1400a2df8  mov     [rdi+210h], rax
0x1400a2dff  mov     rcx, rdi; this
0x1400a2e02  mov     [rdi+220h], rax
0x1400a2e09  mov     dword ptr [rdi+1C0h], 3000h
0x1400a2e13  mov     dword ptr [rdi+1DCh], 258h
0x1400a2e1d  mov     qword ptr [rdi+1E0h], 493E0h
0x1400a2e28  mov     dword ptr [rdi+1E8h], 0FFFFFFFFh
0x1400a2e32  mov     [rdi+1EEh], r13b
0x1400a2e39  mov     qword ptr [rdi+208h], 2000000h
0x1400a2e44  mov     [rdi+21Ch], r15d
0x1400a2e4b  mov     dword ptr [rdi+230h], 708h
0x1400a2e55  mov     dword ptr [rdi+234h], 20h ; ' '
0x1400a2e5f  mov     dword ptr [rdi+238h], 2710h
0x1400a2e69  mov     [rdi+23Ch], r12d
0x1400a2e70  mov     dword ptr [rdi+254h], 15180h
0x1400a2e7a  mov     [rdi+264h], r13b
0x1400a2e81  call    ?GetParameter@SP_CONTROL@@QEAAJPEAGPEAU_GUID@@@Z; SP_CONTROL::GetParameter(ushort *,_GUID *)
0x1400a2e86  mov     ebx, eax
0x1400a2e88  cmp     eax, 0C0000034h
0x1400a2e8d  jnz     short loc_1400A2EC9
0x1400a2e8f  mov     rcx, rsi; Uuid
0x1400a2e92  call    cs:__imp_ExUuidCreate
0x1400a2e99  nop     dword ptr [rax+rax+00h]
0x1400a2e9e  mov     ebx, eax
0x1400a2ea0  test    eax, eax
0x1400a2ea2  js      loc_1400A376C
0x1400a2ea8  movups  xmm0, xmmword ptr [rdi+190h]
0x1400a2eaf  lea     r8, [rbp+57h+var_A0]; struct _GUID
0x1400a2eb3  mov     rcx, rdi; this
0x1400a2eb6  lea     rdx, aControlid; "ControlId"
0x1400a2ebd  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x1400a2ec2  call    ?SetParameter@SP_CONTROL@@QEAAJPEAGU_GUID@@E@Z; SP_CONTROL::SetParameter(ushort *,_GUID,uchar)
0x1400a2ec7  mov     ebx, eax
0x1400a2ec9  test    ebx, ebx
0x1400a2ecb  js      loc_1400A376C
0x1400a2ed1  call    Feature_WriteCacheLines__private_IsEnabledPreCheck
0x1400a2ed6  lea     rsi, [rdi+1B9h]
0x1400a2edd  mov     rcx, rdi; this
0x1400a2ee0  mov     r8, rsi; unsigned __int8 *
0x1400a2ee3  lea     rdx, aEnablecachelin; "EnableCacheLines"
0x1400a2eea  call    ?GetParameter@SP_CONTROL@@QEAAJPEAGPEAE@Z; SP_CONTROL::GetParameter(ushort *,uchar *)
0x1400a2eef  mov     ebx, eax
  ... truncated ...
```
