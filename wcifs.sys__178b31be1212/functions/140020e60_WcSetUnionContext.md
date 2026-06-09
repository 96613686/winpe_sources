# WcSetUnionContext

- ea: `0x140020e60`
- end: `0x14002214c`
- name: `WcSetUnionContext`
- size: `4844`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020b60`
- `0x140031e90`

## callees

- `0x1400020c4`
- `0x1400024d4`
- `0x140004198`
- `0x140004d7c`
- `0x1400142d0`
- `0x140014570`
- `0x14001d23c`
- `0x14001e4f8`
- `0x14001e80c`
- `0x140020e60`
- `0x14002ca2c`
- `0x14002ee60`
- `0x14002eea4`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x140021ea1`
- `ntoskrnl!PsIsHostSilo` at `0x140021ea1`
- `ntoskrnl!RtlCompareMemory` at `0x140021d2b`
- `ntoskrnl!RtlCompareMemory` at `0x140021d2b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140021e29`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140021e29`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400218f5`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140021d95`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140021f57`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400218f5`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140021d95`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140021f57`
- `ntoskrnl!PsJobType` at `0x140021dff`
- `ntoskrnl!ObIsKernelHandle` at `0x140021df3`
- `ntoskrnl!ObIsKernelHandle` at `0x140021df3`
- `ntoskrnl!PsGetJobSilo` at `0x140021e67`
- `ntoskrnl!PsGetJobSilo` at `0x140021e67`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400217cd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400217cd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400211c5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400211c5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140021794`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140021794`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020ef4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020f0b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021706`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020ef4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020f0b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021706`
- `ntoskrnl!ObfDereferenceObject` at `0x140022099`
- `ntoskrnl!ObfDereferenceObject` at `0x140022099`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140022084`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140022084`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400213db`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400213db`
- `ntoskrnl!ExAllocatePool2` at `0x1400216e6`
- `ntoskrnl!ExAllocatePool2` at `0x1400216e6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400213f3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002146b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400213f3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002146b`
- `FLTMGR!FltAttachVolume` at `0x1400215cb`
- `FLTMGR!FltAttachVolume` at `0x1400215cb`
- `FLTMGR!FltAdjustDeviceStackSizeForIoRedirection` at `0x1400216c0`
- `FLTMGR!FltAdjustDeviceStackSizeForIoRedirection` at `0x1400216c0`
- `FLTMGR!FltIsIoRedirectionAllowed` at `0x140021661`
- `FLTMGR!FltIsIoRedirectionAllowed` at `0x140021661`
- `FLTMGR!FltGetVolumeFromName` at `0x1400215a1`
- `FLTMGR!FltGetVolumeFromName` at `0x1400215a1`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140021d6d`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140021f35`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140021d6d`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140021f35`
- `FLTMGR!FltReleaseResource` at `0x140021f69`
- `FLTMGR!FltReleaseResource` at `0x140021f69`
- `FLTMGR!FltObjectDereference` at `0x1400218c5`
- `FLTMGR!FltObjectDereference` at `0x140021949`
- `FLTMGR!FltObjectDereference` at `0x1400220e8`
- `FLTMGR!FltObjectDereference` at `0x1400220fd`
- `FLTMGR!FltObjectDereference` at `0x140022113`
- `FLTMGR!FltObjectDereference` at `0x1400218c5`
- `FLTMGR!FltObjectDereference` at `0x140021949`
- `FLTMGR!FltObjectDereference` at `0x1400220e8`
- `FLTMGR!FltObjectDereference` at `0x1400220fd`
- `FLTMGR!FltObjectDereference` at `0x140022113`
- `FLTMGR!FltReleaseContext` at `0x14002192c`
- `FLTMGR!FltReleaseContext` at `0x1400220be`
- `FLTMGR!FltReleaseContext` at `0x1400220d3`
- `FLTMGR!FltReleaseContext` at `0x14002192c`
- `FLTMGR!FltReleaseContext` at `0x1400220be`
- `FLTMGR!FltReleaseContext` at `0x1400220d3`
- `FLTMGR!FltGetInstanceContext` at `0x140021223`
- `FLTMGR!FltGetInstanceContext` at `0x1400215ea`
- `FLTMGR!FltGetInstanceContext` at `0x140021629`
- `FLTMGR!FltGetInstanceContext` at `0x140021223`
- `FLTMGR!FltGetInstanceContext` at `0x1400215ea`
- `FLTMGR!FltGetInstanceContext` at `0x140021629`

## pseudocode

```c
__int64 __fastcall WcSetUnionContext(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v5; // rdx
  NTSTATUS v6; // esi
  int v7; // r9d
  USHORT v8; // cx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rax
  unsigned __int16 *v11; // rdi
  int v12; // eax
  unsigned int v13; // r8d
  char v14; // r13
  int InstanceFromVolumeName; // eax
  NTSTATUS InstanceContext; // eax
  int v17; // r9d
  int v18; // eax
  __int64 i; // rax
  __int64 v20; // r8
  __int64 v21; // r13
  unsigned __int64 v22; // rax
  int v23; // eax
  int v24; // edx
  USHORT v25; // ax
  USHORT v26; // ax
  int v27; // eax
  int v28; // edx
  NTSTATUS VolumeFromName; // eax
  NTSTATUS v30; // eax
  NTSTATUS v31; // eax
  NTSTATUS v32; // eax
  NTSTATUS IsIoRedirectionAllowed; // eax
  NTSTATUS v34; // eax
  __int64 Pool2; // rax
  _QWORD *v36; // rax
  int UnicodeString; // eax
  NTSTATUS appended; // eax
  __int16 v39; // ax
  int v40; // ecx
  __int64 v41; // rcx
  __int64 **v42; // rdx
  __int64 *v43; // rax
  int v44; // ecx
  HANDLE v45; // r13
  PVOID inserted; // r13
  struct _ERESOURCE *v47; // rcx
  HANDLE v48; // rcx
  BOOLEAN IsKernelHandle; // al
  NTSTATUS v50; // eax
  int JobSilo; // eax
  int SetSiloContext; // eax
  int v53; // r9d
  __int64 v54; // r13
  struct _ERESOURCE *v55; // rbx
  char v57; // [rsp+38h] [rbp-D0h]
  char v58; // [rsp+38h] [rbp-D0h]
  char v59; // [rsp+38h] [rbp-D0h]
  char v60; // [rsp+40h] [rbp-C8h]
  char v61; // [rsp+40h] [rbp-C8h]
  unsigned __int8 RedirectionAllowed[8]; // [rsp+58h] [rbp-B0h] BYREF
  char *Buffer; // [rsp+60h] [rbp-A8h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v65; // [rsp+70h] [rbp-98h]
  __int64 v66; // [rsp+78h] [rbp-90h] BYREF
  PFLT_INSTANCE RetInstance; // [rsp+80h] [rbp-88h] BYREF
  PFLT_CONTEXT v68; // [rsp+88h] [rbp-80h] BYREF
  int v69; // [rsp+90h] [rbp-78h]
  PFLT_INSTANCE Instance; // [rsp+98h] [rbp-70h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v73; // [rsp+B0h] [rbp-58h] BYREF
  PVOID Object; // [rsp+B8h] [rbp-50h] BYREF
  UNICODE_STRING InstanceName; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int16 *v76; // [rsp+D0h] [rbp-38h]
  HANDLE Handle; // [rsp+D8h] [rbp-30h]
  UNICODE_STRING VolumeName; // [rsp+E0h] [rbp-28h] BYREF
  UNICODE_STRING SourceString; // [rsp+F0h] [rbp-18h] BYREF
  UNICODE_STRING String1; // [rsp+100h] [rbp-8h] BYREF
  UNICODE_STRING v81; // [rsp+110h] [rbp+8h] BYREF
  UNICODE_STRING v82; // [rsp+120h] [rbp+18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+130h] [rbp+28h] BYREF
  unsigned __int8 NewElement; // [rsp+1A0h] [rbp+98h] BYREF

  v3 = a2;
  Instance = 0;
  RetInstance = 0;
  Context = 0;
  v68 = 0;
  v66 = 0;
  v82 = 0;
  Buffer = 0;
  v81 = 0;
  NewElement = 0;
  SourceString = 0;
  RetVolume = 0;
  VolumeName = 0;
  RedirectionAllowed[0] = 0;
  DestinationString = 0;
  Object = 0;
  String1 = 0;
  v72 = 0;
  InstanceName = 0;
  v73 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\");
  RtlInitUnicodeString(&SourceString, &word_14000A898);
  if ( (unsigned int)v3 < 0xA8 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = 13;
      v7 = 31;
      v57 = 124;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  if ( *(_DWORD *)(a1 + 4) > (unsigned int)v3 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = 13;
      v7 = 32;
      v57 = -125;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  if ( *(_DWORD *)a1 != 168 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = 13;
      v7 = 33;
      v57 = -118;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  v8 = *(_WORD *)(a1 + 112);
  if ( v8 > 0x64u )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = 13;
      v7 = 34;
      v57 = -111;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  v5 = *(unsigned int *)(a1 + 8);
  v9 = 28 * v5 + 136;
  if ( v9 > v3 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = 13;
      v7 = 35;
      v57 = -105;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  if ( (unsigned int)v5 < 2 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = 13;
      v7 = 36;
      v57 = -99;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  LODWORD(v5) = *(unsigned __int16 *)(a1 + 160);
  InstanceName.Buffer = (PWSTR)(a1 + 12);
  v10 = *(unsigned int *)(a1 + 156);
  InstanceName.Length = v8;
  InstanceName.MaximumLength = v8;
  if ( (int)v10 + (int)v5 < (unsigned int)v10 || (int)v10 + (int)v5 > (unsigned int)v3 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_193;
    v53 = 37;
    v61 = 13;
    v59 = -83;
    goto LABEL_190;
  }
  if ( v10 < v9 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = 13;
      v7 = 38;
      v57 = -75;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  if ( (*(_DWORD *)(a1 + 152) & 1) == 0 )
  {
    v6 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = 13;
      v7 = 39;
      v57 = -69;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  v11 = (unsigned __int16 *)((unsigned int)v10 + a1);
  Handle = *(HANDLE *)(a1 + 128);
  v12 = WcValidateContainerRootId(v11, v5);
  v6 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = v12;
      v7 = 40;
      v57 = -60;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  v13 = v11[1];
  v81.Length = v13;
  v81.MaximumLength = v13;
  v81.Buffer = v11 + 3;
  v82.Length = v11[2];
  v82.MaximumLength = v82.Length;
  String1.Length = v82.Length - v13;
  v82.Buffer = v11 + 3;
  String1.MaximumLength = v82.Length;
  String1.Buffer = &v11[((unsigned __int64)v13 >> 1) + 3];
  LOBYTE(v65) = RtlEqualUnicodeString(&String1, &DestinationString, 1u);
  v14 = v65;
  InstanceFromVolumeName = WcGetInstanceFromVolumeName(&v81, &InstanceName, &Instance);
  v6 = InstanceFromVolumeName;
  if ( InstanceFromVolumeName < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = InstanceFromVolumeName;
      v7 = 41;
      v57 = -31;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  InstanceContext = FltGetInstanceContext(Instance, &Context);
  v6 = InstanceContext;
  if ( InstanceContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = InstanceContext;
      v7 = 42;
      v57 = -24;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  if ( *((_DWORD *)Context + 2) != 2 )
  {
    v6 = -1073741637;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_193;
    v17 = 43;
    v58 = -18;
LABEL_58:
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_sD(
      wil_details_featureDescriptors_a->DeviceExtension,
      v5,
      11,
      v17,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      v58);
    goto LABEL_193;
  }
  if ( !*((_BYTE *)Context + 296) )
  {
    v6 = -1073741637;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_193;
    v17 = 44;
    v58 = -12;
    goto LABEL_58;
  }
  if ( *((_QWORD *)Context + 7) )
  {
    v6 = -1073741637;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v60 = -69;
      v7 = 45;
      v57 = -1;
      goto LABEL_124;
    }
    goto LABEL_193;
  }
  if ( v14 )
  {
    if ( *(_DWORD *)(a1 + 120) == 1 )
    {
      v6 = -1073741637;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v60 = -69;
        v7 = 46;
        v57 = 7;
        goto LABEL_124;
      }
      goto LABEL_193;
    }
    *((_DWORD *)Context + 73) = 327680;
    *((_DWORD *)Context + 72) = 5;
  }
  v18 = WcCreateUnionContext(&v82, (__int64)&v66);
  v6 = v18;
  if ( v18 >= 0 )
  {
    if ( *(_DWORD *)(a1 + 120) == 2 )
      *(_DWORD *)(v66 + 32) |= 2u;
    ExAcquireFastMutex(&FastMutex);
    if ( byte_14000E240 )
    {
      ExReleaseFastMutex(&FastMutex);
      v6 = -1073741637;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_193;
      v17 = 48;
      v58 = 54;
      goto LABEL_58;
    }
    *(_DWORD *)(v66 + 32) |= 1u;
    ++dword_14000E244;
    ExReleaseFastMutex(&FastMutex);
    for ( i = 1; ; i = (unsigned int)(v69 + 1) )
    {
      v20 = *(unsigned int *)(a1 + 8);
      v69 = i;
      if ( (unsigned int)i >= (unsigned int)v20 )
        break;
      v21 = a1 + 28 * i + 136;
      if ( !v21 )
      {
        v6 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = 13;
        v7 = 49;
        v57 = 69;
        goto LABEL_124;
      }
      v22 = *(unsigned int *)(v21 + 20);
      LODWORD(v5) = *(unsigned __int16 *)(v21 + 24);
      if ( (int)v22 + (int)v5 < (unsigned int)v22 || (int)v22 + (int)v5 > a2 )
      {
        v6 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = 13;
        v7 = 50;
        v57 = 77;
        goto LABEL_124;
      }
      if ( v22 < 28 * v20 + 136 )
      {
        v6 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = 13;
        v7 = 51;
        v57 = 85;
        goto LABEL_124;
      }
      if ( (*(_DWORD *)(v21 + 16) & 1) != 0 )
      {
        v6 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = 13;
        v7 = 52;
        v57 = 96;
        goto LABEL_124;
      }
      v76 = (unsigned __int16 *)((unsigned int)v22 + a1);
      v23 = WcValidateContainerRootId(v76, v5);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v24) = 2;
          WPP_RECORDER_SF_sDdd(
            wil_details_featureDescriptors_a->DeviceExtension,
            v24,
            11,
            53,
            (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
            105,
            v69,
            v23);
        }
        goto LABEL_193;
      }
      v25 = v76[2];
      SourceString.Buffer = v76 + 3;
      SourceString.Length = v25;
      SourceString.MaximumLength = v25;
      v26 = v76[1];
      VolumeName.Buffer = v76 + 3;
      VolumeName.Length = v26;
      VolumeName.MaximumLength = v26;
      v27 = WcGetInstanceFromVolumeName(&VolumeName, &InstanceName, &RetInstance);
      if ( v27 >= 0 )
      {
        v32 = FltGetInstanceContext(RetInstance, &v68);
        v6 = v32;
        if ( v32 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_193;
          v60 = v32;
          v7 = 58;
          v57 = -101;
          goto LABEL_124;
        }
        if ( *((_QWORD *)v68 + 7) )
        {
          v6 = -1073741637;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_193;
          v60 = -69;
          v7 = 59;
          v57 = -88;
          goto LABEL_124;
        }
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v28) = 4;
          WPP_RECORDER_SF_sDd(
            wil_details_featureDescriptors_a->DeviceExtension,
            v28,
            11,
            54,
            (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
            123,
            v27);
        }
        VolumeFromName = FltGetVolumeFromName(Globals, &VolumeName, &RetVolume);
        v6 = VolumeFromName;
        if ( VolumeFromName < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_193;
          v60 = VolumeFromName;
          v7 = 55;
          v57 = 0x80;
          goto LABEL_124;
        }
        v30 = FltAttachVolume(Globals, RetVolume, &InstanceName, &RetInstance);
        v6 = v30;
        if ( v30 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_193;
          v60 = v30;
          v7 = 56;
          v57 = -117;
          goto LABEL_124;
        }
        v31 = FltGetInstanceContext(RetInstance, &v68);
        v6 = v31;
        if ( v31 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_193;
          v60 = v31;
          v7 = 57;
          v57 = -110;
          goto LABEL_124;
        }
      }
      if ( Instance != RetInstance )
      {
        IsIoRedirectionAllowed = FltIsIoRedirectionAllowed(Instance, RetInstance, RedirectionAllowed);
        v6 = IsIoRedirectionAllowed;
        if ( IsIoRedirectionAllowed < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_193;
          v60 = IsIoRedirectionAllowed;
          v7 = 60;
          v57 = -78;
          goto LABEL_124;
        }
        if ( !RedirectionAllowed[0] )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v5) = 4;
            WPP_RECORDER_SF_sD(
              wil_details_featureDescriptors_a->DeviceExtension,
              v5,
              11,
              61,
              (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
              184);
          }
          v34 = FltAdjustDeviceStackSizeForIoRedirection(Instance, RetInstance, 0);
          v6 = v34;
          if ( v34 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_193;
            v60 = v34;
            v7 = 62;
            v57 = -67;
            goto LABEL_124;
          }
        }
      }
      Pool2 = ExAllocatePool2(256, 112, 2037138263);
      Buffer = (char *)Pool2;
      if ( !Pool2 )
      {
        v6 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = -102;
        v7 = 63;
        v57 = -57;
        goto LABEL_124;
      }
      RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 24), 0);
      v36 = Buffer + 48;
      *((_QWORD *)Buffer + 7) = Buffer + 48;
      *v36 = v36;
      *((_QWORD *)Buffer + 5) = 0;
      *((_QWORD *)Buffer + 8) = 0;
      *((_DWORD *)Buffer + 4) = 0;
      v6 = RtlUShortAdd(v76[2], 2u, (USHORT *)Buffer + 13);
      if ( v6 < 0 )
        goto LABEL_193;
      UnicodeString = WcAllocateUnicodeString(2037138263, Buffer + 24);
      v6 = UnicodeString;
      if ( UnicodeString < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = UnicodeString;
        v7 = 64;
        v57 = -38;
        goto LABEL_124;
      }
      Buffer[20] = 1;
      RtlCopyUnicodeString((PUNICODE_STRING)(Buffer + 24), &SourceString);
      v5 = (unsigned __int64)Buffer;
      if ( *((_DWORD *)v68 + 2) != 6
        || *(_WORD *)(*((_QWORD *)Buffer + 4) + 2 * ((unsigned __int64)*((unsigned __int16 *)Buffer + 12) >> 1) - 2) != 92 )
      {
        appended = RtlAppendUnicodeToString((PUNICODE_STRING)(Buffer + 24), L"\\");
        v6 = appended;
        if ( appended < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_193;
          v60 = appended;
          v7 = 65;
          v57 = -19;
          goto LABEL_124;
        }
        v5 = (unsigned __int64)Buffer;
      }
      *(_OWORD *)v5 = *(_OWORD *)v21;
      v39 = *(_WORD *)(v21 + 26);
      if ( (v39 & 2) != 0 )
      {
        if ( (v39 & 1) != 0 )
        {
          v6 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_193;
          v60 = 13;
          v7 = 66;
          v57 = -8;
          goto LABEL_124;
        }
        *((_DWORD *)Buffer + 4) |= 4u;
      }
      if ( (*(_BYTE *)(v21 + 26) & 1) != 0 )
        *((_DWORD *)Buffer + 4) |= 2u;
      if ( (*(_BYTE *)(v21 + 26) & 4) != 0 )
        *((_DWORD *)Buffer + 4) |= 0x40u;
      v40 = *((_DWORD *)v68 + 2);
      if ( v40 == 13 || v40 == 6 )
        *((_DWORD *)Buffer + 4) |= 1u;
      v14 = v65;
      if ( (_BYTE)v65 )
      {
        v6 = WcInitializeDirectoryTable(Buffer, 0x2000);
        if ( v6 < 0 )
          goto LABEL_193;
      }
      v41 = v66 + 168;
      v42 = *(__int64 ***)(v66 + 176);
      if ( *v42 != (__int64 *)(v66 + 168) )
        __fastfail(3u);
      v43 = (__int64 *)(Buffer + 48);
      *((_QWORD *)Buffer + 7) = v42;
      *v43 = v41;
      *v42 = v43;
      *(_QWORD *)(v41 + 8) = v43;
      *((_QWORD *)Buffer + 5) = RetInstance;
      if ( v68 == Context )
      {
        FltObjectDereference(RetInstance);
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v68 + 5);
        *((_DWORD *)Buffer + 4) |= 8u;
      }
      RetInstance = 0;
      if ( !RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(v66 + 64), &Buffer, 8u, &NewElement) )
      {
        v6 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = -102;
        v7 = 67;
        v57 = 57;
        goto LABEL_124;
      }
      if ( !NewElement )
      {
        v6 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = 13;
        v7 = 68;
        v57 = 62;
        goto LABEL_124;
      }
      if ( v6 < 0 )
        goto LABEL_193;
      Buffer = 0;
      FltReleaseContext(v68);
      v68 = 0;
      if ( RetVolume )
      {
        FltObjectDereference(RetVolume);
        RetVolume = 0;
      }
    }
    if ( v14 )
    {
      if ( *((_QWORD *)Context + 7) )
      {
        v6 = -1073741637;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = -69;
        v7 = 69;
        v57 = 85;
LABEL_124:
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v5,
          11,
          v7,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          v57,
          v60);
        goto LABEL_193;
      }
      *(_DWORD *)(v66 + 28) = 1;
      LODWORD(v5) = (_DWORD)Context;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)Context + 7, v66, 0) )
      {
        v6 = -1073741637;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = -69;
        v7 = 70;
        v57 = 98;
        goto LABEL_124;
      }
LABEL_186:
      v66 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 4;
        WPP_RECORDER_SF_sD(
          wil_details_featureDescriptors_a->DeviceExtension,
          v5,
          11,
          78,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          218);
      }
      goto LABEL_191;
    }
    v44 = *((_DWORD *)Context + 70);
    if ( v44 && v44 != *(_DWORD *)(a1 + 116) )
    {
      v6 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_193;
      v60 = 13;
      v7 = 71;
      v57 = 108;
      goto LABEL_124;
    }
    if ( RtlCompareMemory(
           (const void *)(*(_QWORD *)(v66 + 16) + 2 * (((unsigned __int64)*(unsigned __int16 *)(v66 + 8) - 2) >> 1)),
           L"\\",
           2u) == 2 )
      *(_WORD *)(v66 + 8) -= 2;
    v45 = Handle;
    if ( Handle )
    {
      v48 = Handle;
      *(_DWORD *)(v66 + 28) = 3;
      IsKernelHandle = ObIsKernelHandle(v48);
      v50 = ObReferenceObjectByHandle(v45, 4u, (POBJECT_TYPE)PsJobType, IsKernelHandle == 0, &Object, 0);
      v6 = v50;
      if ( v50 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = v50;
        v7 = 72;
        v57 = -100;
        goto LABEL_124;
      }
      JobSilo = PsGetJobSilo(Object, &v72);
      v6 = JobSilo;
      if ( JobSilo < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = JobSilo;
        v7 = 73;
        v57 = -92;
        goto LABEL_124;
      }
      if ( (unsigned __int8)PsIsHostSilo(v72) )
      {
        v6 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_193;
        v60 = 13;
        v7 = 74;
        v57 = -81;
        goto LABEL_124;
      }
      SetSiloContext = WcGetSetSiloContext(v72, Instance, *(unsigned int *)(a1 + 116), a3, &v73);
      v6 = SetSiloContext;
      if ( SetSiloContext < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_191;
        v61 = SetSiloContext;
        v53 = 75;
        v59 = -70;
        goto LABEL_190;
      }
      v54 = v73;
      v55 = (struct _ERESOURCE *)(v73 + 8);
      FltAcquireResourceExclusive((PERESOURCE)(v73 + 8));
      inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(v54 + 112), &v66, 8u, &NewElement);
      v47 = v55;
    }
    else
    {
      *(_DWORD *)(v66 + 28) = 2;
      FltAcquireResourceExclusive((PERESOURCE)((char *)Context + 72));
      inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 176), &v66, 8u, &NewElement);
      if ( inserted && NewElement )
        ++*((_DWORD *)Context + 16);
      *((_DWORD *)Context + 70) = *(_DWORD *)(a1 + 116);
      *((_DWORD *)Context + 71) = a3;
      v47 = (struct _ERESOURCE *)((char *)Context + 72);
    }
    FltReleaseResource(v47);
    if ( inserted )
    {
      if ( NewElement )
      {
        if ( v6 < 0 )
          goto LABEL_191;
        goto LABEL_186;
      }
      v6 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_191;
      v61 = 13;
      v53 = 77;
      v59 = -48;
    }
    else
    {
      v6 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_191;
      v61 = -102;
      v53 = 76;
      v59 = -53;
    }
LABEL_190:
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v5,
      11,
      v53,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      v59,
      v61);
LABEL_191:
    if ( v73 )
      PsDereferenceSiloContext(v73);
    goto LABEL_193;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v60 = v18;
    v7 = 47;
    v57 = 39;
    goto LABEL_124;
  }
LABEL_193:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v66 )
    WcReleaseUnionContext(v66);
  if ( Context )
    FltReleaseContext(Context);
  if ( v68 )
    FltReleaseContext(v68);
  if ( Instance )
    FltObjectDereference(Instance);
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  if ( RetInstance )
    FltObjectDereference(RetInstance);
  if ( Buffer )
    WcCleanupLayer(Buffer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140020e60  mov     rax, rsp
0x140020e63  mov     [rax+8], rbx
0x140020e67  mov     [rax+18h], r8d
0x140020e6b  mov     [rax+10h], edx
0x140020e6e  push    rbp
0x140020e6f  push    rsi
0x140020e70  push    rdi
0x140020e71  push    r12
0x140020e73  push    r13
0x140020e75  push    r14
0x140020e77  push    r15
0x140020e79  lea     rbp, [rax-78h]
0x140020e7d  sub     rsp, 140h
0x140020e84  xor     r15d, r15d
0x140020e87  mov     edi, edx
0x140020e89  xorps   xmm0, xmm0
0x140020e8c  mov     [rbp+70h+Instance], r15
0x140020e90  xorps   xmm1, xmm1
0x140020e93  mov     [rsp+170h+RetInstance], r15
0x140020e98  mov     rbx, rcx
0x140020e9b  mov     [rsp+170h+Context], r15
0x140020ea0  lea     rdx, Source2; "\\"
0x140020ea7  mov     [rbp+70h+var_F0], r15
0x140020eab  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x140020eaf  mov     [rsp+170h+var_100], r15
0x140020eb4  movups  xmmword ptr [rbp+70h+var_58.Length], xmm0
0x140020eb8  mov     [rsp+170h+Buffer], r15
0x140020ebd  mov     r14d, r8d
0x140020ec0  movups  xmmword ptr [rbp+70h+var_68.Length], xmm1
0x140020ec4  mov     [rbp+70h+NewElement], r15b
0x140020ecb  movups  xmmword ptr [rbp+70h+SourceString.Length], xmm0
0x140020ecf  mov     [rbp+70h+RetVolume], r15
0x140020ed3  movups  xmmword ptr [rbp+70h+VolumeName.Length], xmm1
0x140020ed7  mov     [rsp+170h+RedirectionAllowed], r15b
0x140020edc  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x140020ee0  mov     [rbp+70h+var_C0], r15
0x140020ee4  movups  xmmword ptr [rbp+70h+String1.Length], xmm1
0x140020ee8  mov     [rbp+70h+var_D0], r15
0x140020eec  movups  xmmword ptr [rbp+70h+InstanceName.Length], xmm0
0x140020ef0  mov     [rbp+70h+var_C8], r15
0x140020ef4  call    cs:__imp_RtlInitUnicodeString
0x140020efb  nop     dword ptr [rax+rax+00h]
0x140020f00  lea     rdx, word_14000A898; SourceString
0x140020f07  lea     rcx, [rbp+70h+SourceString]; DestinationString
0x140020f0b  call    cs:__imp_RtlInitUnicodeString
0x140020f12  nop     dword ptr [rax+rax+00h]
0x140020f17  mov     eax, 0A8h
0x140020f1c  cmp     edi, eax
0x140020f1e  jnb     short loc_140020F64
0x140020f20  mov     eax, 0C000000Dh
0x140020f25  mov     esi, eax
0x140020f27  lea     rdi, WPP_RECORDER_INITIALIZED
0x140020f2e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140020f35  jz      loc_140022090
0x140020f3b  mov     dword ptr [rsp+170h+var_138], eax
0x140020f3f  lea     r9d, [r15+1Fh]
0x140020f43  mov     dword ptr [rsp+170h+var_140], 47Ch
0x140020f4b  lea     r15, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140020f52  mov     r8d, 0Bh
0x140020f58  lea     r12, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140020f5f  jmp     loc_140021A42
0x140020f64  cmp     [rbx+4], edi
0x140020f67  jbe     short loc_140020F98
0x140020f69  mov     eax, 0C000000Dh
0x140020f6e  mov     esi, eax
0x140020f70  lea     rdi, WPP_RECORDER_INITIALIZED
0x140020f77  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140020f7e  jz      loc_140022090
0x140020f84  mov     dword ptr [rsp+170h+var_138], eax
0x140020f88  mov     r9d, 20h ; ' '
0x140020f8e  mov     dword ptr [rsp+170h+var_140], 483h
0x140020f96  jmp     short loc_140020F4B
0x140020f98  cmp     [rbx], eax
0x140020f9a  jz      short loc_140020FCB
0x140020f9c  mov     eax, 0C000000Dh
0x140020fa1  mov     esi, eax
0x140020fa3  lea     rdi, WPP_RECORDER_INITIALIZED
0x140020faa  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140020fb1  jz      loc_140022090
0x140020fb7  mov     dword ptr [rsp+170h+var_138], eax
0x140020fbb  mov     r9d, 21h ; '!'
0x140020fc1  mov     dword ptr [rsp+170h+var_140], 48Ah
0x140020fc9  jmp     short loc_140020F4B
0x140020fcb  movzx   ecx, word ptr [rbx+70h]
0x140020fcf  cmp     cx, 64h ; 'd'
0x140020fd3  jbe     short loc_140021007
0x140020fd5  mov     eax, 0C000000Dh
0x140020fda  mov     esi, eax
0x140020fdc  lea     rdi, WPP_RECORDER_INITIALIZED
0x140020fe3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140020fea  jz      loc_140022090
0x140020ff0  mov     dword ptr [rsp+170h+var_138], eax
0x140020ff4  mov     r9d, 22h ; '"'
0x140020ffa  mov     dword ptr [rsp+170h+var_140], 491h
0x140021002  jmp     loc_140020F4B
0x140021007  mov     edx, [rbx+8]
0x14002100a  imul    r8, rdx, 1Ch
0x14002100e  add     r8, 88h
0x140021015  cmp     r8, rdi
0x140021018  jbe     short loc_14002104C
0x14002101a  mov     eax, 0C000000Dh
0x14002101f  mov     esi, eax
0x140021021  lea     rdi, WPP_RECORDER_INITIALIZED
0x140021028  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002102f  jz      loc_140022090
0x140021035  mov     dword ptr [rsp+170h+var_138], eax
0x140021039  mov     r9d, 23h ; '#'
0x14002103f  mov     dword ptr [rsp+170h+var_140], 497h
0x140021047  jmp     loc_140020F4B
0x14002104c  cmp     edx, 2
0x14002104f  jnb     short loc_140021083
0x140021051  mov     eax, 0C000000Dh
0x140021056  mov     esi, eax
0x140021058  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002105f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140021066  jz      loc_140022090
0x14002106c  mov     dword ptr [rsp+170h+var_138], eax
0x140021070  mov     r9d, 24h ; '$'
0x140021076  mov     dword ptr [rsp+170h+var_140], 49Dh
0x14002107e  jmp     loc_140020F4B
0x140021083  movzx   edx, word ptr [rbx+0A0h]
0x14002108a  lea     rax, [rbx+0Ch]
0x14002108e  mov     [rbp+70h+InstanceName.Buffer], rax
0x140021092  mov     eax, [rbx+9Ch]
0x140021098  mov     [rbp+70h+InstanceName.Length], cx
0x14002109c  mov     [rbp+70h+InstanceName.MaximumLength], cx
0x1400210a0  lea     ecx, [rax+rdx]
0x1400210a3  cmp     ecx, eax
0x1400210a5  jb      loc_140022021
0x1400210ab  cmp     ecx, edi
0x1400210ad  ja      loc_140022021
0x1400210b3  mov     ecx, eax
0x1400210b5  cmp     rax, r8
0x1400210b8  jnb     short loc_1400210EC
0x1400210ba  mov     eax, 0C000000Dh
0x1400210bf  mov     esi, eax
0x1400210c1  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400210c8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400210cf  jz      loc_140022090
0x1400210d5  mov     dword ptr [rsp+170h+var_138], eax
0x1400210d9  mov     r9d, 26h ; '&'
0x1400210df  mov     dword ptr [rsp+170h+var_140], 4B5h
0x1400210e7  jmp     loc_140020F4B
0x1400210ec  mov     eax, [rbx+98h]
0x1400210f2  mov     r12d, 1
0x1400210f8  test    r12b, al
0x1400210fb  jnz     short loc_14002112E
0x1400210fd  mov     eax, 0C000000Dh
0x140021102  mov     esi, eax
0x140021104  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002110b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140021112  jz      loc_140022090
0x140021118  mov     dword ptr [rsp+170h+var_138], eax
0x14002111c  lea     r9d, [r12+26h]
0x140021121  mov     dword ptr [rsp+170h+var_140], 4BBh
0x140021129  jmp     loc_140020F4B
0x14002112e  mov     rax, [rbx+80h]
0x140021135  lea     rdi, [rcx+rbx]
0x140021139  mov     rcx, rdi
0x14002113c  mov     [rbp+70h+Handle], rax
0x140021140  call    WcValidateContainerRootId
0x140021145  mov     esi, eax
0x140021147  test    eax, eax
0x140021149  jns     short loc_140021176
0x14002114b  lea     rdi, WPP_RECORDER_INITIALIZED
0x140021152  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140021159  jz      loc_140022090
0x14002115f  mov     dword ptr [rsp+170h+var_138], eax
0x140021163  mov     r9d, 28h ; '('
0x140021169  mov     dword ptr [rsp+170h+var_140], 4C4h
0x140021171  jmp     loc_140020F4B
0x140021176  movzx   r8d, word ptr [rdi+2]
0x14002117b  lea     rdx, [rdi+6]
0x14002117f  mov     [rbp+70h+var_68.Length], r8w
0x140021184  mov     [rbp+70h+var_68.MaximumLength], r8w
0x140021189  mov     [rbp+70h+var_68.Buffer], rdx
0x14002118d  movzx   ecx, word ptr [rdi+4]
0x140021191  movzx   eax, cx
0x140021194  mov     [rbp+70h+var_58.Length], cx
0x140021198  sub     ax, r8w
0x14002119c  mov     [rbp+70h+var_58.MaximumLength], cx
0x1400211a0  mov     [rbp+70h+String1.Length], ax
0x1400211a4  mov     eax, r8d
0x1400211a7  shr     rax, 1
0x1400211aa  mov     r8b, r12b; CaseInSensitive
0x1400211ad  mov     [rbp+70h+var_58.Buffer], rdx
0x1400211b1  mov     [rbp+70h+String1.MaximumLength], cx
0x1400211b5  lea     rcx, [rbp+70h+String1]; String1
0x1400211b9  lea     rax, [rdx+rax*2]
0x1400211bd  lea     rdx, [rbp+70h+DestinationString]; String2
0x1400211c1  mov     [rbp+70h+String1.Buffer], rax
0x1400211c5  call    cs:__imp_RtlEqualUnicodeString
0x1400211cc  nop     dword ptr [rax+rax+00h]
0x1400211d1  lea     r8, [rbp+70h+Instance]; RetInstance
0x1400211d5  mov     byte ptr [rsp+170h+var_108], al
0x1400211d9  lea     rdx, [rbp+70h+InstanceName]; InstanceName
0x1400211dd  mov     r13b, al
0x1400211e0  lea     rcx, [rbp+70h+var_68]; VolumeName
0x1400211e4  call    WcGetInstanceFromVolumeName
0x1400211e9  mov     esi, eax
0x1400211eb  test    eax, eax
0x1400211ed  jns     short loc_14002121A
0x1400211ef  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400211f6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400211fd  jz      loc_140022090
0x140021203  mov     dword ptr [rsp+170h+var_138], eax
0x140021207  mov     r9d, 29h ; ')'
0x14002120d  mov     dword ptr [rsp+170h+var_140], 4E1h
0x140021215  jmp     loc_140020F4B
0x14002121a  mov     rcx, [rbp+70h+Instance]; Instance
0x14002121e  lea     rdx, [rsp+170h+Context]; Context
0x140021223  call    cs:__imp_FltGetInstanceContext
0x14002122a  nop     dword ptr [rax+rax+00h]
0x14002122f  mov     esi, eax
0x140021231  test    eax, eax
0x140021233  jns     short loc_140021260
0x140021235  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002123c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140021243  jz      loc_140022090
0x140021249  mov     dword ptr [rsp+170h+var_138], eax
0x14002124d  mov     r9d, 2Ah ; '*'
0x140021253  mov     dword ptr [rsp+170h+var_140], 4E8h
0x14002125b  jmp     loc_140020F4B
0x140021260  mov     rax, [rsp+170h+Context]
0x140021265  cmp     dword ptr [rax+8], 2
0x140021269  jz      short loc_140021297
0x14002126b  mov     esi, 0C00000BBh
0x140021270  lea     rdi, WPP_RECORDER_INITIALIZED
0x140021277  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002127e  jz      loc_140022090
0x140021284  mov     r9d, 2Bh ; '+'
0x14002128a  mov     dword ptr [rsp+170h+var_140], 4EEh
0x140021292  jmp     loc_140021426
0x140021297  mov     rax, [rsp+170h+Context]
0x14002129c  cmp     [rax+128h], r15b
0x1400212a3  jnz     short loc_1400212D1
0x1400212a5  mov     esi, 0C00000BBh
0x1400212aa  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400212b1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400212b8  jz      loc_140022090
0x1400212be  mov     r9d, 2Ch ; ','
0x1400212c4  mov     dword ptr [rsp+170h+var_140], 4F4h
0x1400212cc  jmp     loc_140021426
0x1400212d1  mov     rax, [rsp+170h+Context]
0x1400212d6  cmp     [rax+38h], r15
0x1400212da  jz      short loc_14002130C
0x1400212dc  mov     esi, 0C00000BBh
0x1400212e1  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400212e8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400212ef  jz      loc_140022090
0x1400212f5  mov     dword ptr [rsp+170h+var_138], esi
0x1400212f9  mov     r9d, 2Dh ; '-'
0x1400212ff  mov     dword ptr [rsp+170h+var_140], 4FFh
0x140021307  jmp     loc_140020F4B
0x14002130c  test    r13b, r13b
0x14002130f  jz      short loc_140021365
0x140021311  cmp     [rbx+78h], r12d
0x140021315  jnz     short loc_140021347
0x140021317  mov     esi, 0C00000BBh
0x14002131c  lea     rdi, WPP_RECORDER_INITIALIZED
0x140021323  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002132a  jz      loc_140022090
0x140021330  mov     dword ptr [rsp+170h+var_138], esi
0x140021334  mov     r9d, 2Eh ; '.'
0x14002133a  mov     dword ptr [rsp+170h+var_140], 507h
0x140021342  jmp     loc_140020F4B
0x140021347  mov     rax, [rsp+170h+Context]
0x14002134c  mov     dword ptr [rax+124h], 50000h
0x140021356  mov     rax, [rsp+170h+Context]
0x14002135b  mov     dword ptr [rax+120h], 5
0x140021365  mov     eax, [rbx+78h]
0x140021368  lea     rcx, [rbp+70h+var_58]; SourceString
0x14002136c  mov     r8d, [rbx+74h]
0x140021370  sub     eax, r12d
0x140021373  cmp     eax, r12d
0x140021376  mov     edx, r15d
0x140021379  lea     rax, [rsp+170h+var_100]
0x14002137e  mov     r9d, r14d
0x140021381  setbe   dl
0x140021384  mov     [rsp+170h+Object], rax; __int64
0x140021389  add     edx, r12d
0x14002138c  call    WcCreateUnionContext
0x140021391  mov     esi, eax
0x140021393  test    eax, eax
0x140021395  jns     short loc_1400213C2
0x140021397  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002139e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400213a5  jz      loc_140022090
0x1400213ab  mov     dword ptr [rsp+170h+var_138], eax
0x1400213af  mov     r9d, 2Fh ; '/'
0x1400213b5  mov     dword ptr [rsp+170h+var_140], 527h
0x1400213bd  jmp     loc_140020F4B
0x1400213c2  cmp     dword ptr [rbx+78h], 2
0x1400213c6  jnz     short loc_1400213D1
0x1400213c8  mov     rax, [rsp+170h+var_100]
0x1400213cd  or      dword ptr [rax+20h], 2
0x1400213d1  lea     rdi, FastMutex
0x1400213d8  mov     rcx, rdi; FastMutex
0x1400213db  call    cs:__imp_ExAcquireFastMutex
0x1400213e2  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
