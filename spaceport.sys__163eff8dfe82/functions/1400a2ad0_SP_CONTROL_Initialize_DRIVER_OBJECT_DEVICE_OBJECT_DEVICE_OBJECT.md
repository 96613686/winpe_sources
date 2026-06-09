# SP_CONTROL::Initialize(_DRIVER_OBJECT *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x1400a2ad0`
- end: `0x1400a38b3`
- name: `?Initialize@SP_CONTROL@@QEAAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@1@Z`
- size: `3555`
- prototype: `int(SP_CONTROL *__hidden this, struct _DRIVER_OBJECT *, struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a43c4`

## callees

- `0x140015b40`
- `0x1400268c0`
- `0x140032fc0`
- `0x14003340c`
- `0x140035b84`
- `0x14008c760`
- `0x1400a2630`
- `0x1400a26e0`
- `0x1400a271c`
- `0x1400a2870`
- `0x1400a2ad0`
- `0x1400a426c`
- `0x1400a4324`
- `0x1400aba3c`
- `0x1400abb70`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x1400a2dd1`
- `ntoskrnl!ExUuidCreate` at `0x1400a2fc2`
- `ntoskrnl!ExUuidCreate` at `0x1400a2dd1`
- `ntoskrnl!ExUuidCreate` at `0x1400a2fc2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400a2e73`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400a2e73`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400a2ec4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400a2ec4`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400a2eb4`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400a2eb4`
- `ntoskrnl!SeLockSubjectContext` at `0x1400a2e67`
- `ntoskrnl!SeLockSubjectContext` at `0x1400a2e67`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400a2e57`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400a2e57`
- `ntoskrnl!ExIsSoftBoot` at `0x1400a3857`
- `ntoskrnl!ExIsSoftBoot` at `0x1400a3857`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400a2e3d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400a2e3d`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400a2d75`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400a2d75`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400a2d98`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400a2d98`
- `ntoskrnl!NtQueryInformationProcess` at `0x1400a370c`
- `ntoskrnl!NtQueryInformationProcess` at `0x1400a370c`
- `ntoskrnl!SeAssignSecurity` at `0x1400a2ea2`
- `ntoskrnl!SeAssignSecurity` at `0x1400a2ea2`
- `ntoskrnl!SePublicDefaultDacl` at `0x1400a2e29`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400a2b20`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400a2b20`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2bf9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2c74`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2d1c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2bf9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2c74`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a2d1c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400a2e13`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400a2e13`
- `ntoskrnl!KeInitializeEvent` at `0x1400a3890`
- `ntoskrnl!KeInitializeEvent` at `0x1400a3890`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2b55`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2b6c`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2b55`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2b6c`

## string_xrefs

- `0x1400a3013`: `EnableCacheLines`
- `0x1400a303e`: `EnableCacheLines`
- `0x1400a30be`: `DisableWriteThrough`
- `0x1400a30e4`: `DisableWriteThrough`
- `0x1400a31b7`: `ScrubDirtyReads`
- `0x1400a31dd`: `ScrubDirtyReads`
- `0x1400a3274`: `NumberOfDestageThreads`
- `0x1400a32a0`: `NumberOfDestageThreads`
- `0x1400a32cb`: `CacheDestageQueueDepth`
- `0x1400a32f9`: `CacheDestageQueueDepth`
- `0x1400a33d1`: `RepairQueueWidth`
- `0x1400a33fd`: `RepairQueueWidth`
- `0x1400a3428`: `RepairQueueDepth`
- `0x1400a3451`: `RepairQueueDepth`

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
0x1400a2ad0  mov     [rsp-8+arg_10], r8
0x1400a2ad5  push    rbp
0x1400a2ad6  push    rbx
0x1400a2ad7  push    rsi
0x1400a2ad8  push    rdi
0x1400a2ad9  push    r12
0x1400a2adb  push    r13
0x1400a2add  push    r14
0x1400a2adf  push    r15
0x1400a2ae1  lea     rbp, [rsp-1Fh]
0x1400a2ae6  sub     rsp, 0A8h
0x1400a2aed  mov     rdi, cs:WPP_MAIN_CB.DeviceExtension
0x1400a2af4  xorps   xmm0, xmm0
0x1400a2af7  xor     eax, eax
0x1400a2af9  mov     rcx, r8; SourceDevice
0x1400a2afc  mov     rbx, r9
0x1400a2aff  mov     [rbp+57h+var_50], rax
0x1400a2b03  mov     r14, r8
0x1400a2b06  mov     [rdi+8], rdx
0x1400a2b0a  mov     rdx, r9; TargetDevice
0x1400a2b0d  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1400a2b11  mov     [rdi], r8
0x1400a2b14  movups  [rbp+57h+var_60], xmm0
0x1400a2b18  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1400a2b1c  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1400a2b20  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1400a2b27  nop     dword ptr [rax+rax+00h]
0x1400a2b2c  xor     r13d, r13d
0x1400a2b2f  mov     [rdi+10h], rax
0x1400a2b33  test    rax, rax
0x1400a2b36  jnz     short loc_1400A2B42
0x1400a2b38  mov     ebx, 0C000000Eh
0x1400a2b3d  jmp     loc_1400A389C
0x1400a2b42  mov     rcx, rdi; this
0x1400a2b45  mov     [rdi+18h], rbx
0x1400a2b49  call    ?GetSmbiosStrings@SP_CONTROL@@QEAAJXZ; SP_CONTROL::GetSmbiosStrings(void)
0x1400a2b4e  mov     ebx, 0FFFFh
0x1400a2b53  mov     ecx, ebx; GroupNumber
0x1400a2b55  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400a2b5c  nop     dword ptr [rax+rax+00h]
0x1400a2b61  mov     edx, 0FFh
0x1400a2b66  cmp     eax, edx
0x1400a2b68  jnb     short loc_1400A2B7A
0x1400a2b6a  mov     ecx, ebx; GroupNumber
0x1400a2b6c  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400a2b73  nop     dword ptr [rax+rax+00h]
0x1400a2b78  mov     edx, eax
0x1400a2b7a  mov     ecx, edx
0x1400a2b7c  mov     esi, 614C7053h
0x1400a2b81  mov     [rdi+150h], edx
0x1400a2b87  xor     r9d, r9d; unsigned int
0x1400a2b8a  shl     rcx, 7; unsigned __int64
0x1400a2b8e  mov     edx, esi; unsigned int
0x1400a2b90  xor     r8d, r8d; unsigned __int8
0x1400a2b93  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400a2b98  mov     [rdi+158h], rax
0x1400a2b9f  test    rax, rax
0x1400a2ba2  jnz     short loc_1400A2BAE
0x1400a2ba4  mov     ebx, 0C000009Ah
0x1400a2ba9  jmp     loc_1400A389C
0x1400a2bae  mov     eax, [rdi+150h]
0x1400a2bb4  mov     ebx, r13d
0x1400a2bb7  mov     r15d, 200h
0x1400a2bbd  mov     r12d, 1
0x1400a2bc3  test    eax, eax
0x1400a2bc5  jz      short loc_1400A2C12
0x1400a2bc7  mov     [rsp+0E0h+Depth], 20h ; ' '; Depth
0x1400a2bce  lea     r8, ?FreePacket@SP_CONTROL@@SAXPEAX@Z; Free
0x1400a2bd5  mov     ecx, ebx
0x1400a2bd7  lea     rdx, ?AllocatePacket@SP_CONTROL@@SAPEAXW4_POOL_TYPE@@_KK@Z; Allocate
0x1400a2bde  shl     rcx, 7
0x1400a2be2  mov     r9d, r15d; Flags
0x1400a2be5  add     rcx, [rdi+158h]; Lookaside
0x1400a2bec  mov     [rsp+0E0h+Tag], esi; Tag
0x1400a2bf0  mov     [rsp+0E0h+Size], 128h; Size
0x1400a2bf9  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400a2c00  nop     dword ptr [rax+rax+00h]
0x1400a2c05  mov     eax, [rdi+150h]
0x1400a2c0b  add     ebx, r12d
0x1400a2c0e  cmp     ebx, eax
0x1400a2c10  jb      short loc_1400A2BC7
0x1400a2c12  mov     ecx, eax
0x1400a2c14  xor     r9d, r9d; unsigned int
0x1400a2c17  shl     rcx, 7; unsigned __int64
0x1400a2c1b  xor     r8d, r8d; unsigned __int8
0x1400a2c1e  mov     edx, esi; unsigned int
0x1400a2c20  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400a2c25  mov     [rdi+160h], rax
0x1400a2c2c  test    rax, rax
0x1400a2c2f  jz      loc_1400A2BA4
0x1400a2c35  mov     eax, [rdi+150h]
0x1400a2c3b  mov     ebx, r13d
0x1400a2c3e  test    eax, eax
0x1400a2c40  jz      short loc_1400A2C90
0x1400a2c42  mov     [rsp+0E0h+Depth], 20h ; ' '; Depth
0x1400a2c49  lea     r8, ?FreePacket@SP_CONTROL@@SAXPEAX@Z; Free
0x1400a2c50  mov     ecx, ebx
0x1400a2c52  lea     rdx, ?AllocatePacket@SP_CONTROL@@SAPEAXW4_POOL_TYPE@@_KK@Z; Allocate
0x1400a2c59  shl     rcx, 7
0x1400a2c5d  mov     r9d, r15d; Flags
0x1400a2c60  add     rcx, [rdi+160h]; Lookaside
0x1400a2c67  mov     [rsp+0E0h+Tag], esi; Tag
0x1400a2c6b  mov     [rsp+0E0h+Size], 5D0h; Size
0x1400a2c74  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400a2c7b  nop     dword ptr [rax+rax+00h]
0x1400a2c80  mov     eax, [rdi+150h]
0x1400a2c86  add     ebx, r12d
0x1400a2c89  cmp     ebx, eax
0x1400a2c8b  jb      short loc_1400A2C42
0x1400a2c8d  xor     r13d, r13d
0x1400a2c90  imul    ecx, eax, 7
0x1400a2c93  xor     r9d, r9d; unsigned int
0x1400a2c96  xor     r8d, r8d; unsigned __int8
0x1400a2c99  mov     edx, esi; unsigned int
0x1400a2c9b  shl     rcx, 7; unsigned __int64
0x1400a2c9f  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400a2ca4  mov     [rdi+168h], rax
0x1400a2cab  test    rax, rax
0x1400a2cae  jz      loc_1400A2BA4
0x1400a2cb4  mov     ecx, [rdi+150h]
0x1400a2cba  imul    eax, ecx, 7
0x1400a2cbd  test    eax, eax
0x1400a2cbf  jz      loc_1400A2D6B
0x1400a2cc5  mov     r15d, 1000h
0x1400a2ccb  mov     esi, r13d
0x1400a2cce  test    esi, esi
0x1400a2cd0  jz      short loc_1400A2CDF
0x1400a2cd2  xor     edx, edx
0x1400a2cd4  mov     eax, esi
0x1400a2cd6  div     ecx
0x1400a2cd8  test    edx, edx
0x1400a2cda  jnz     short loc_1400A2CDF
0x1400a2cdc  add     r15d, r15d
0x1400a2cdf  mov     rcx, [rdi+168h]
0x1400a2ce6  xor     edx, edx
0x1400a2ce8  mov     eax, 100000h
0x1400a2ced  mov     r12d, esi
0x1400a2cf0  div     r15d
0x1400a2cf3  mov     edx, r15d
0x1400a2cf6  mov     r9d, 200h; Flags
0x1400a2cfc  mov     ebx, eax
0x1400a2cfe  shl     r12, 7
0x1400a2d02  mov     [rsp+0E0h+Depth], bx; Depth
0x1400a2d07  add     rcx, r12; Lookaside
0x1400a2d0a  mov     [rsp+0E0h+Tag], 614C7053h; Tag
0x1400a2d12  xor     r8d, r8d; Free
0x1400a2d15  mov     [rsp+0E0h+Size], rdx; Size
0x1400a2d1a  xor     edx, edx; Allocate
0x1400a2d1c  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400a2d23  nop     dword ptr [rax+rax+00h]
0x1400a2d28  mov     rcx, [rdi+168h]
0x1400a2d2f  mov     [rcx+r12+12h], bx
0x1400a2d35  cmp     r15d, 40000h
0x1400a2d3c  jnz     short loc_1400A2D4D
0x1400a2d3e  mov     rax, [rdi+168h]
0x1400a2d45  mov     word ptr [r12+rax+12h], 10h
0x1400a2d4d  mov     ecx, [rdi+150h]
0x1400a2d53  mov     r12d, 1
0x1400a2d59  imul    eax, ecx, 7
0x1400a2d5c  add     esi, r12d
0x1400a2d5f  cmp     esi, eax
0x1400a2d61  jb      loc_1400A2CCE
0x1400a2d67  mov     r14, [rbp+57h+arg_10]
0x1400a2d6b  lea     rdx, Path; "Spaceport\\Parameters"
0x1400a2d72  mov     ecx, r12d; RelativeTo
0x1400a2d75  call    cs:__imp_RtlCheckRegistryKey
0x1400a2d7c  nop     dword ptr [rax+rax+00h]
0x1400a2d81  mov     r15d, 0C0000034h
0x1400a2d87  mov     ebx, eax
0x1400a2d89  cmp     eax, r15d
0x1400a2d8c  jnz     short loc_1400A2DA6
0x1400a2d8e  lea     rdx, Path; "Spaceport\\Parameters"
0x1400a2d95  mov     ecx, r12d; RelativeTo
0x1400a2d98  call    cs:__imp_RtlCreateRegistryKey
0x1400a2d9f  nop     dword ptr [rax+rax+00h]
0x1400a2da4  mov     ebx, eax
0x1400a2da6  test    ebx, ebx
0x1400a2da8  js      loc_1400A389C
0x1400a2dae  lea     rsi, [rdi+170h]
0x1400a2db5  mov     rcx, rdi; this
0x1400a2db8  mov     r8, rsi; struct _GUID *
0x1400a2dbb  lea     rdx, aPrimordialid; "PrimordialId"
0x1400a2dc2  call    ?GetParameter@SP_CONTROL@@QEAAJPEAGPEAU_GUID@@@Z; SP_CONTROL::GetParameter(ushort *,_GUID *)
0x1400a2dc7  mov     ebx, eax
0x1400a2dc9  cmp     eax, r15d
0x1400a2dcc  jnz     short loc_1400A2E04
0x1400a2dce  mov     rcx, rsi; Uuid
0x1400a2dd1  call    cs:__imp_ExUuidCreate
0x1400a2dd8  nop     dword ptr [rax+rax+00h]
0x1400a2ddd  mov     ebx, eax
0x1400a2ddf  test    eax, eax
0x1400a2de1  js      loc_1400A389C
0x1400a2de7  movups  xmm0, xmmword ptr [rsi]
0x1400a2dea  lea     r8, [rbp+57h+var_A0]; struct _GUID
0x1400a2dee  mov     rcx, rdi; this
0x1400a2df1  lea     rdx, aPrimordialid; "PrimordialId"
0x1400a2df8  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x1400a2dfd  call    ?SetParameter@SP_CONTROL@@QEAAJPEAGU_GUID@@E@Z; SP_CONTROL::SetParameter(ushort *,_GUID,uchar)
0x1400a2e02  mov     ebx, eax
0x1400a2e04  test    ebx, ebx
0x1400a2e06  js      loc_1400A389C
0x1400a2e0c  mov     edx, r12d; Revision
0x1400a2e0f  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400a2e13  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400a2e1a  nop     dword ptr [rax+rax+00h]
0x1400a2e1f  mov     ebx, eax
0x1400a2e21  test    eax, eax
0x1400a2e23  js      loc_1400A389C
0x1400a2e29  mov     r8, cs:__imp_SePublicDefaultDacl
0x1400a2e30  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400a2e34  xor     r9d, r9d; DaclDefaulted
0x1400a2e37  mov     dl, r12b; DaclPresent
0x1400a2e3a  mov     r8, [r8]; Dacl
0x1400a2e3d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400a2e44  nop     dword ptr [rax+rax+00h]
0x1400a2e49  mov     ebx, eax
0x1400a2e4b  test    eax, eax
0x1400a2e4d  js      loc_1400A389C
0x1400a2e53  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400a2e57  call    cs:__imp_SeCaptureSubjectContext
0x1400a2e5e  nop     dword ptr [rax+rax+00h]
0x1400a2e63  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400a2e67  call    cs:__imp_SeLockSubjectContext
0x1400a2e6e  nop     dword ptr [rax+rax+00h]
0x1400a2e73  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400a2e7a  nop     dword ptr [rax+rax+00h]
0x1400a2e7f  mov     dword ptr [rsp+0E0h+Depth], r12d; PoolType
0x1400a2e84  lea     r8, [rdi+180h]; NewDescriptor
0x1400a2e8b  mov     qword ptr [rsp+0E0h+Tag], rax; GenericMapping
0x1400a2e90  lea     rdx, [rbp+57h+SecurityDescriptor]; ExplicitDescriptor
0x1400a2e94  lea     rax, [rbp+57h+SubjectContext]
0x1400a2e98  xor     r9d, r9d; IsDirectoryObject
0x1400a2e9b  xor     ecx, ecx; ParentDescriptor
0x1400a2e9d  mov     [rsp+0E0h+Size], rax; SubjectContext
0x1400a2ea2  call    cs:__imp_SeAssignSecurity
0x1400a2ea9  nop     dword ptr [rax+rax+00h]
0x1400a2eae  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400a2eb2  mov     ebx, eax
0x1400a2eb4  call    cs:__imp_SeUnlockSubjectContext
0x1400a2ebb  nop     dword ptr [rax+rax+00h]
0x1400a2ec0  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400a2ec4  call    cs:__imp_SeReleaseSubjectContext
0x1400a2ecb  nop     dword ptr [rax+rax+00h]
0x1400a2ed0  test    ebx, ebx
0x1400a2ed2  js      loc_1400A389C
0x1400a2ed8  mov     ecx, 40000h
0x1400a2edd  mov     dword ptr [rdi+188h], 0E0h
0x1400a2ee7  mov     eax, 800000h
0x1400a2eec  mov     [rdi+1C4h], ecx
0x1400a2ef2  mov     [rdi+1F0h], rax
0x1400a2ef9  lea     rsi, [rdi+190h]
0x1400a2f00  mov     [rdi+1F8h], rax
0x1400a2f07  lea     rdx, aControlid; "ControlId"
0x1400a2f0e  mov     eax, 8000000h
0x1400a2f13  mov     [rdi+1D8h], ecx
0x1400a2f19  mov     [rdi+218h], ecx
0x1400a2f1f  mov     r15d, 4
0x1400a2f25  mov     r8, rsi; struct _GUID *
0x1400a2f28  mov     [rdi+210h], rax
0x1400a2f2f  mov     rcx, rdi; this
0x1400a2f32  mov     [rdi+220h], rax
0x1400a2f39  mov     dword ptr [rdi+1C0h], 3000h
0x1400a2f43  mov     dword ptr [rdi+1DCh], 258h
0x1400a2f4d  mov     qword ptr [rdi+1E0h], 493E0h
0x1400a2f58  mov     dword ptr [rdi+1E8h], 0FFFFFFFFh
0x1400a2f62  mov     [rdi+1EEh], r13b
0x1400a2f69  mov     qword ptr [rdi+208h], 2000000h
0x1400a2f74  mov     [rdi+21Ch], r15d
0x1400a2f7b  mov     dword ptr [rdi+230h], 708h
0x1400a2f85  mov     dword ptr [rdi+234h], 20h ; ' '
0x1400a2f8f  mov     dword ptr [rdi+238h], 2710h
0x1400a2f99  mov     [rdi+23Ch], r12d
0x1400a2fa0  mov     dword ptr [rdi+254h], 15180h
0x1400a2faa  mov     [rdi+264h], r13b
0x1400a2fb1  call    ?GetParameter@SP_CONTROL@@QEAAJPEAGPEAU_GUID@@@Z; SP_CONTROL::GetParameter(ushort *,_GUID *)
0x1400a2fb6  mov     ebx, eax
0x1400a2fb8  cmp     eax, 0C0000034h
0x1400a2fbd  jnz     short loc_1400A2FF9
0x1400a2fbf  mov     rcx, rsi; Uuid
0x1400a2fc2  call    cs:__imp_ExUuidCreate
0x1400a2fc9  nop     dword ptr [rax+rax+00h]
0x1400a2fce  mov     ebx, eax
0x1400a2fd0  test    eax, eax
0x1400a2fd2  js      loc_1400A389C
0x1400a2fd8  movups  xmm0, xmmword ptr [rdi+190h]
0x1400a2fdf  lea     r8, [rbp+57h+var_A0]; struct _GUID
0x1400a2fe3  mov     rcx, rdi; this
0x1400a2fe6  lea     rdx, aControlid; "ControlId"
0x1400a2fed  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x1400a2ff2  call    ?SetParameter@SP_CONTROL@@QEAAJPEAGU_GUID@@E@Z; SP_CONTROL::SetParameter(ushort *,_GUID,uchar)
0x1400a2ff7  mov     ebx, eax
0x1400a2ff9  test    ebx, ebx
0x1400a2ffb  js      loc_1400A389C
0x1400a3001  call    Feature_WriteCacheLines__private_IsEnabledPreCheck
0x1400a3006  lea     rsi, [rdi+1B9h]
0x1400a300d  mov     rcx, rdi; this
0x1400a3010  mov     r8, rsi; unsigned __int8 *
0x1400a3013  lea     rdx, aEnablecachelin; "EnableCacheLines"
0x1400a301a  call    ?GetParameter@SP_CONTROL@@QEAAJPEAGPEAE@Z; SP_CONTROL::GetParameter(ushort *,uchar *)
0x1400a301f  mov     ebx, eax
  ... truncated ...
```
