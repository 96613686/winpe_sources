# RootDeviceAdd

- ea: `0x14002a740`
- end: `0x14002b164`
- name: `RootDeviceAdd`
- size: `2596`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1400038cc`
- `0x140006ca0`
- `0x140006ea0`
- `0x140009718`
- `0x1400140fc`
- `0x140017000`
- `0x140017190`
- `0x140017540`
- `0x14002a740`
- `0x14002c438`
- `0x14002daf4`
- `0x14002e6b0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002abe3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002abe3`
- `ntoskrnl!KeInitializeEvent` at `0x14002ad84`
- `ntoskrnl!KeInitializeEvent` at `0x14002ad84`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002ae6f`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002ae6f`
- `ntoskrnl!ExRegisterCallback` at `0x14002ac47`
- `ntoskrnl!ExRegisterCallback` at `0x14002ac47`
- `ntoskrnl!ExCreateCallback` at `0x14002ac26`
- `ntoskrnl!ExCreateCallback` at `0x14002ac26`
- `ntoskrnl!ExAllocatePool2` at `0x14002ae8d`
- `ntoskrnl!ExAllocatePool2` at `0x14002aec6`
- `ntoskrnl!ExAllocatePool2` at `0x14002ae8d`
- `ntoskrnl!ExAllocatePool2` at `0x14002aec6`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002afbc`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002afbc`

## pseudocode

```c
__int64 __fastcall RootDeviceAdd(__int64 a1, __int64 a2)
{
  int v3; // ebx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdi
  __int64 MaximumProcessorCount; // rbx
  __int64 Pool2; // rax
  __int64 v10; // rax
  struct _DEVICE_OBJECT *v11; // rax
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  int Parameter; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v22; // [rsp+68h] [rbp-98h]
  __int128 v23; // [rsp+78h] [rbp-88h]
  __int64 *v24; // [rsp+88h] [rbp-78h]
  __int128 v25; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-60h]
  _OWORD v27[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v28[2]; // [rsp+C8h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v31[12]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v32[18]; // [rsp+180h] [rbp+80h] BYREF
  GUID v33; // [rsp+210h] [rbp+110h] BYREF
  __int64 v34; // [rsp+220h] [rbp+120h]
  _OWORD v35[2]; // [rsp+228h] [rbp+128h] BYREF

  v19 = a2;
  memset(v32, 0, 0x8Cu);
  memset(v31, 0, sizeof(v31));
  v28[0] = 1835034;
  LODWORD(v24) = 0;
  v34 = 0;
  v18 = 0;
  LODWORD(v26) = 0;
  memset(v27, 0, 28);
  v28[1] = v35;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v33 = 0;
  v25 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v35[0] = *(_OWORD *)L"\\Device\\VMBus";
  *(_OWORD *)((char *)v35 + 12) = *(_OWORD *)L"e\\VMBus";
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 528))(WdfDriverGlobals, a2, 42);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 488))(WdfDriverGlobals, v19, 3);
  memset(v27, 0, sizeof(v27));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x1B )
      LODWORD(v27[0]) = -1;
    else
      LODWORD(v27[0]) = *(_DWORD *)(WdfStructures + 216);
  }
  else
  {
    LODWORD(v27[0]) = 32;
  }
  *((_QWORD *)&v27[0] + 1) = RootFilterAddResourceRequirements;
  *((_QWORD *)&v27[1] + 1) = RootRemoveAddedResources;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 1024))(
    WdfDriverGlobals,
    v19,
    v27);
  memset(v32, 0, sizeof(v32));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x29 )
      LODWORD(v32[0]) = -1;
    else
      LODWORD(v32[0]) = *(_DWORD *)(WdfStructures + 328);
  }
  else
  {
    LODWORD(v32[0]) = 144;
  }
  v32[5] = RootDevicePrepareHardwareChild;
  v32[6] = RootDeviceReleaseHardwareChild;
  v32[9] = RootDeviceSelfManagedIoInit;
  v32[11] = RootDeviceSelfManagedIoRestart;
  v32[10] = RootDeviceSelfManagedIoSuspend;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 440))(
    WdfDriverGlobals,
    v19,
    v32);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 504))(WdfDriverGlobals, v19);
  memset(v31, 0, sizeof(v31));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 2 )
      LODWORD(v31[0]) = -1;
    else
      LODWORD(v31[0]) = *(_DWORD *)(WdfStructures + 16);
  }
  else
  {
    LODWORD(v31[0]) = 96;
  }
  v31[2] = RootDeviceListCreatePdo;
  HIDWORD(v31[0]) = 208;
  v31[5] = InstanceDeviceListIdentificationDescriptionDuplicate;
  v31[7] = InstanceDeviceListIdentificationDescriptionCompare;
  v31[6] = InstanceDeviceListIdentificationDescriptionCleanup;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, _QWORD))(WdfFunctions_01033 + 1040))(
    WdfDriverGlobals,
    v19,
    v31,
    0);
  v21 = 0;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v21) = -1;
    else
      LODWORD(v21) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v21) = 56;
  }
  v24 = off_14001C0C8;
  *((_QWORD *)&v21 + 1) = RootDeviceContextCleanup;
  *(_QWORD *)&v22 = RootDeviceContextDestroy;
  *((_QWORD *)&v22 + 1) = 0x100000002LL;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 536))(
         WdfDriverGlobals,
         v19,
         v28);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const UNICODE_STRING *))(WdfFunctions_01033 + 544))(
           WdfDriverGlobals,
           v19,
           &SDDL_DEVOBJ_KERNEL_ONLY);
    if ( v3 >= 0 )
    {
      LOBYTE(v6) = 14;
      v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, IRP *), __int64, _QWORD, _DWORD))(WdfFunctions_01033 + 584))(
             WdfDriverGlobals,
             v19,
             RootFileRdmaIoctlPreprocess,
             v6,
             0,
             0);
      if ( v3 < 0 )
        return (unsigned int)v3;
      RtlInitUnicodeString(&DestinationString, L"\\Callback\\SoftRestart");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 80;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ExCreateCallback(&KsrCallbackObject, &ObjectAttributes, 0, 1u) >= 0 )
        ExRegisterCallback(KsrCallbackObject, RootDeviceKsrCallback, 0);
      v3 = RootFileInit(v19);
      if ( v3 >= 0 )
      {
        v3 = AddFdoSupportedInterfaces(v19);
        if ( v3 < 0 )
          return (unsigned int)v3;
        v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, __int128 *, __int64 *))(WdfFunctions_01033 + 600))(
               WdfDriverGlobals,
               &v19,
               &v21,
               &v18);
        if ( v3 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                 WdfDriverGlobals,
                 v18,
                 off_14001C0C8);
          *(_DWORD *)v7 = 1953460082;
          *(_QWORD *)(v7 + 88) = v7 + 80;
          *(_QWORD *)(v7 + 80) = v7 + 80;
          *(_QWORD *)(v7 + 104) = v7 + 96;
          *(_QWORD *)(v7 + 96) = v7 + 96;
          *(_QWORD *)(v7 + 136) = v7 + 128;
          *(_QWORD *)(v7 + 128) = v7 + 128;
          *(_DWORD *)(v7 + 24) = 1;
          *(_QWORD *)(v7 + 32) = 0;
          *(_DWORD *)(v7 + 40) = 0;
          KeInitializeEvent((PRKEVENT)(v7 + 48), SynchronizationEvent, 0);
          v26 = 0;
          v25 = 0;
          if ( WdfClientVersionHigherThanFramework )
          {
            if ( (unsigned int)WdfStructureCount <= 0x43 )
              LODWORD(v25) = -1;
            else
              LODWORD(v25) = *(_DWORD *)(WdfStructures + 536);
          }
          else
          {
            LODWORD(v25) = 24;
          }
          LOBYTE(v26) = 1;
          *((_QWORD *)&v25 + 1) = RootNotifyDeviceInterfaceArrival;
          v24 = 0;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          if ( WdfClientVersionHigherThanFramework )
          {
            if ( (unsigned int)WdfStructureCount <= 0x26 )
              LODWORD(v21) = -1;
            else
              LODWORD(v21) = *(_DWORD *)(WdfStructures + 304);
          }
          else
          {
            LODWORD(v21) = 56;
          }
          *(_QWORD *)&v23 = v18;
          *((_QWORD *)&v22 + 1) = 0x100000001LL;
          v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033
                                                                                               + 3032))(
                 WdfDriverGlobals,
                 &v25,
                 &v21,
                 v7 + 160);
          if ( v3 >= 0 )
          {
            MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
            Pool2 = ExAllocatePool2(64, MaximumProcessorCount, 1937072726);
            *(_QWORD *)(v7 + 152) = Pool2;
            if ( !Pool2 )
              return (unsigned int)-1073741670;
            if ( !(unsigned int)IsInterruptEnlightenmentAvailable() )
            {
              v10 = ExAllocatePool2(64, 8 * MaximumProcessorCount, 1937072726);
              if ( (*(_QWORD *)(v7 + 144) = v10) == 0 )
                return (unsigned int)-1073741670;
            }
            v11 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 248))(
                                             WdfDriverGlobals,
                                             v18);
            ChVmContext = v18;
            ChRootDeviceObject = v11;
            v12 = ChOfferCacheInit();
            v3 = 0;
            if ( v12 < 0 )
              v3 = v12;
            if ( v3 >= 0 )
            {
              v3 = XPartInit(v18);
              if ( v3 >= 0 )
              {
                Parameter = -1073741823;
                if ( RtlRunOnceExecuteOnce(&RunOnce, (PRTL_RUN_ONCE_INIT_FN)AwpInitializeQueues, &Parameter, 0) >= 0
                  || (v3 = Parameter, Parameter >= 0) )
                {
                  v3 = UtilExportInit(v18, v7);
                  if ( v3 >= 0 )
                  {
                    LOBYTE(v13) = 1;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                      WdfDriverGlobals,
                      v18,
                      1,
                      v13);
                    LOBYTE(v14) = 1;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                      WdfDriverGlobals,
                      v18,
                      2,
                      v14);
                    LOBYTE(v15) = 1;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                      WdfDriverGlobals,
                      v18,
                      3,
                      v15);
                    LOBYTE(v16) = 1;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                      WdfDriverGlobals,
                      v18,
                      6,
                      v16);
                    v3 = RootIoctlInit(v18);
                    if ( v3 >= 0 )
                    {
                      v33 = GUID_BUS_VMBUS;
                      v34 = 15;
                      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, GUID *))(WdfFunctions_01033 + 680))(
                        WdfDriverGlobals,
                        v18,
                        &v33);
                      return 0;
                    }
                  }
                  else
                  {
                    v4 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      v5 = 20;
                      goto LABEL_26;
                    }
                  }
                }
                else
                {
                  v4 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    v5 = 19;
                    goto LABEL_26;
                  }
                }
              }
              else
              {
                v4 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v5 = 16;
                  goto LABEL_26;
                }
              }
            }
            else
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v5 = 15;
                goto LABEL_26;
              }
            }
          }
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v5 = 14;
            goto LABEL_26;
          }
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v5 = 13;
          goto LABEL_26;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v5 = 12;
        goto LABEL_26;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v5 = 11;
LABEL_26:
      WPP_SF_d(v4->AttachedDevice, v5, WPP_1d82a8cff87b33874cd31050c50ab9c4_Traceguids, (unsigned int)v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002a740  push    rbp
0x14002a742  push    rbx
0x14002a743  push    rdi
0x14002a744  push    r12
0x14002a746  push    r14
0x14002a748  push    r15
0x14002a74a  lea     rbp, [rsp-158h]
0x14002a752  sub     rsp, 258h
0x14002a759  mov     rax, cs:__security_cookie
0x14002a760  xor     rax, rsp
0x14002a763  mov     [rbp+180h+var_38], rax
0x14002a76a  mov     rbx, rdx
0x14002a76d  mov     [rsp+280h+var_238], rdx
0x14002a772  xor     eax, eax
0x14002a774  lea     rcx, [rbp+180h+var_100]; void *
0x14002a77b  xor     edx, edx; Val
0x14002a77d  mov     [rbp+180h+var_FC], eax
0x14002a783  mov     r8d, 8Ch; Size
0x14002a789  call    memset
0x14002a78e  mov     edi, 60h ; '`'
0x14002a793  lea     rcx, [rbp+180h+var_160]; void *
0x14002a797  mov     r8d, edi; Size
0x14002a79a  xor     edx, edx; Val
0x14002a79c  call    memset
0x14002a7a1  movups  xmm1, xmmword ptr cs:aDeviceVmbus+0Ch; "e\\VMBus"
0x14002a7a8  mov     rcx, cs:WdfDriverGlobals
0x14002a7af  lea     r8d, [rdi-36h]
0x14002a7b3  xorps   xmm0, xmm0
0x14002a7b6  mov     [rbp+180h+var_1B8], 1C001Ah
0x14002a7be  xor     eax, eax
0x14002a7c0  mov     rdx, rbx
0x14002a7c3  mov     dword ptr [rbp+180h+var_1F8], eax
0x14002a7c6  mov     [rbp+180h+var_60], rax
0x14002a7cd  mov     [rsp+280h+var_240], rax
0x14002a7d2  mov     dword ptr [rbp+180h+var_1E0], eax
0x14002a7d5  lea     rax, [rbp+180h+var_58]
0x14002a7dc  movups  [rbp+180h+var_1D8], xmm0
0x14002a7e0  mov     [rbp+180h+var_1B0], rax
0x14002a7e4  mov     rax, cs:WdfFunctions_01033
0x14002a7eb  movups  xmmword ptr [rbp+180h+ObjectAttributes.ObjectName], xmm0
0x14002a7ef  movups  [rsp+280h+var_228], xmm0
0x14002a7f4  movups  [rsp+280h+var_218], xmm0
0x14002a7f9  movups  [rsp+280h+var_208], xmm0
0x14002a7fe  movups  [rbp+180h+var_70], xmm0
0x14002a805  movups  [rbp+180h+var_1F0], xmm0
0x14002a809  movups  [rbp+180h+var_1D8+0Ch], xmm0
0x14002a80d  movups  xmmword ptr [rbp+180h+DestinationString.Length], xmm0
0x14002a811  movups  xmmword ptr [rbp+180h+ObjectAttributes.Length], xmm0
0x14002a815  movups  xmmword ptr [rbp+180h+ObjectAttributes+1Ch], xmm0
0x14002a819  movups  xmm0, xmmword ptr cs:aDeviceVmbus; "\\Device\\VMBus"
0x14002a820  movups  xmmword ptr [rbp+180h+var_58], xmm0
0x14002a827  movups  xmmword ptr [rbp+180h+var_58+0Ch], xmm1
0x14002a82e  mov     rax, [rax+210h]
0x14002a835  call    _guard_dispatch_icall
0x14002a83a  mov     rax, cs:WdfFunctions_01033
0x14002a841  lea     r8d, [rdi-5Dh]
0x14002a845  mov     rdx, [rsp+280h+var_238]
0x14002a84a  mov     rcx, cs:WdfDriverGlobals
0x14002a851  mov     rax, [rax+1E8h]
0x14002a858  call    _guard_dispatch_icall
0x14002a85d  xorps   xmm0, xmm0
0x14002a860  or      r12d, 0FFFFFFFFh
0x14002a864  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a86b  movups  [rbp+180h+var_1D8], xmm0
0x14002a86f  movups  [rbp+180h+var_1C8], xmm0
0x14002a873  jz      short loc_14002A896
0x14002a875  cmp     cs:WdfStructureCount, 1Bh
0x14002a87c  jbe     short loc_14002A890
0x14002a87e  mov     rax, cs:WdfStructures
0x14002a885  mov     ecx, [rax+0D8h]
0x14002a88b  mov     dword ptr [rbp+180h+var_1D8], ecx
0x14002a88e  jmp     short loc_14002A89D
0x14002a890  mov     dword ptr [rbp+180h+var_1D8], r12d
0x14002a894  jmp     short loc_14002A89D
0x14002a896  mov     dword ptr [rbp+180h+var_1D8], 20h ; ' '
0x14002a89d  mov     rdx, [rsp+280h+var_238]
0x14002a8a2  lea     rax, RootFilterAddResourceRequirements
0x14002a8a9  mov     rcx, cs:WdfDriverGlobals
0x14002a8b0  lea     r8, [rbp+180h+var_1D8]
0x14002a8b4  mov     qword ptr [rbp+180h+var_1D8+8], rax
0x14002a8b8  lea     rax, RootRemoveAddedResources
0x14002a8bf  mov     qword ptr [rbp+180h+var_1C8+8], rax
0x14002a8c3  mov     rax, cs:WdfFunctions_01033
0x14002a8ca  mov     rax, [rax+400h]
0x14002a8d1  call    _guard_dispatch_icall
0x14002a8d6  mov     ebx, 90h
0x14002a8db  lea     rcx, [rbp+180h+var_100]; void *
0x14002a8e2  mov     r8d, ebx; Size
0x14002a8e5  xor     edx, edx; Val
0x14002a8e7  call    memset
0x14002a8ec  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a8f3  jz      short loc_14002A91C
0x14002a8f5  cmp     cs:WdfStructureCount, 29h ; ')'
0x14002a8fc  jbe     short loc_14002A913
0x14002a8fe  mov     rax, cs:WdfStructures
0x14002a905  mov     ecx, [rax+148h]
0x14002a90b  mov     [rbp+180h+var_100], ecx
0x14002a911  jmp     short loc_14002A922
0x14002a913  mov     [rbp+180h+var_100], r12d
0x14002a91a  jmp     short loc_14002A922
0x14002a91c  mov     [rbp+180h+var_100], ebx
0x14002a922  mov     rdx, [rsp+280h+var_238]
0x14002a927  lea     rax, RootDevicePrepareHardwareChild
0x14002a92e  mov     rcx, cs:WdfDriverGlobals
0x14002a935  lea     r8, [rbp+180h+var_100]
0x14002a93c  mov     [rbp+180h+var_D8], rax
0x14002a943  lea     rax, RootDeviceReleaseHardwareChild
0x14002a94a  mov     [rbp+180h+var_D0], rax
0x14002a951  lea     rax, RootDeviceSelfManagedIoInit
0x14002a958  mov     [rbp+180h+var_B8], rax
0x14002a95f  lea     rax, RootDeviceSelfManagedIoRestart
0x14002a966  mov     [rbp+180h+var_A8], rax
0x14002a96d  lea     rax, RootDeviceSelfManagedIoSuspend
0x14002a974  mov     [rbp+180h+var_B0], rax
0x14002a97b  mov     rax, cs:WdfFunctions_01033
0x14002a982  mov     rax, [rax+1B8h]
0x14002a989  call    _guard_dispatch_icall
0x14002a98e  mov     rax, cs:WdfFunctions_01033
0x14002a995  mov     rdx, [rsp+280h+var_238]
0x14002a99a  mov     rcx, cs:WdfDriverGlobals
0x14002a9a1  mov     rax, [rax+1F8h]
0x14002a9a8  call    _guard_dispatch_icall
0x14002a9ad  mov     r8, rdi; Size
0x14002a9b0  lea     rcx, [rbp+180h+var_160]; void *
0x14002a9b4  xor     edx, edx; Val
0x14002a9b6  call    memset
0x14002a9bb  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a9c2  mov     r15d, 2
0x14002a9c8  jz      short loc_14002A9E8
0x14002a9ca  cmp     cs:WdfStructureCount, r15d
0x14002a9d1  jbe     short loc_14002A9E2
0x14002a9d3  mov     rax, cs:WdfStructures
0x14002a9da  mov     ecx, [rax+10h]
0x14002a9dd  mov     [rbp+180h+var_160], ecx
0x14002a9e0  jmp     short loc_14002A9EB
0x14002a9e2  mov     [rbp+180h+var_160], r12d
0x14002a9e6  jmp     short loc_14002A9EB
0x14002a9e8  mov     [rbp+180h+var_160], edi
0x14002a9eb  mov     rdx, [rsp+280h+var_238]
0x14002a9f0  lea     rax, RootDeviceListCreatePdo
0x14002a9f7  mov     rcx, cs:WdfDriverGlobals
0x14002a9fe  lea     r8, [rbp+180h+var_160]
0x14002aa02  mov     [rbp+180h+var_150], rax
0x14002aa06  xor     r9d, r9d
0x14002aa09  lea     rax, InstanceDeviceListIdentificationDescriptionDuplicate
0x14002aa10  mov     [rbp+180h+var_15C], 0D0h
0x14002aa17  mov     [rbp+180h+var_138], rax
0x14002aa1b  lea     rax, InstanceDeviceListIdentificationDescriptionCompare
0x14002aa22  mov     [rbp+180h+var_128], rax
0x14002aa26  lea     rax, InstanceDeviceListIdentificationDescriptionCleanup
0x14002aa2d  mov     [rbp+180h+var_130], rax
0x14002aa31  mov     rax, cs:WdfFunctions_01033
0x14002aa38  mov     rax, [rax+410h]
0x14002aa3f  call    _guard_dispatch_icall
0x14002aa44  xorps   xmm0, xmm0
0x14002aa47  xor     eax, eax
0x14002aa49  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14002aa4f  movups  [rsp+280h+var_228], xmm0
0x14002aa54  mov     [rbp+180h+var_1F8], rax
0x14002aa58  movups  [rsp+280h+var_218], xmm0
0x14002aa5d  movups  [rsp+280h+var_208], xmm0
0x14002aa62  jz      short loc_14002AA87
0x14002aa64  cmp     cs:WdfStructureCount, 26h ; '&'
0x14002aa6b  jbe     short loc_14002AA80
0x14002aa6d  mov     rax, cs:WdfStructures
0x14002aa74  mov     ecx, [rax+130h]
0x14002aa7a  mov     dword ptr [rsp+280h+var_228], ecx
0x14002aa7e  jmp     short loc_14002AA8F
0x14002aa80  mov     dword ptr [rsp+280h+var_228], r12d
0x14002aa85  jmp     short loc_14002AA8F
0x14002aa87  mov     dword ptr [rsp+280h+var_228], 38h ; '8'
0x14002aa8f  mov     rax, cs:off_14001C0C8
0x14002aa96  lea     r8, [rbp+180h+var_1B8]
0x14002aa9a  mov     rdx, [rsp+280h+var_238]
0x14002aa9f  mov     r14d, 1
0x14002aaa5  mov     rcx, cs:WdfDriverGlobals
0x14002aaac  mov     [rbp+180h+var_1F8], rax
0x14002aab0  lea     rax, RootDeviceContextCleanup
0x14002aab7  mov     qword ptr [rsp+280h+var_228+8], rax
0x14002aabc  lea     rax, RootDeviceContextDestroy
0x14002aac3  mov     qword ptr [rsp+280h+var_218], rax
0x14002aac8  mov     rax, cs:WdfFunctions_01033
0x14002aacf  mov     dword ptr [rsp+280h+var_218+0Ch], r14d
0x14002aad4  mov     dword ptr [rsp+280h+var_218+8], r15d
0x14002aad9  mov     rax, [rax+218h]
0x14002aae0  call    _guard_dispatch_icall
0x14002aae5  mov     ebx, eax
0x14002aae7  test    eax, eax
0x14002aae9  jns     short loc_14002AB34
0x14002aaeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aaf2  lea     rax, WPP_GLOBAL_Control
0x14002aaf9  cmp     rcx, rax
0x14002aafc  jz      loc_14002B141
0x14002ab02  mov     edx, [rcx+2Ch]
0x14002ab05  test    r14b, dl
0x14002ab08  jz      loc_14002B141
0x14002ab0e  cmp     [rcx+29h], r15b
0x14002ab12  jb      loc_14002B141
0x14002ab18  lea     edx, [r14+0Ah]
0x14002ab1c  mov     rcx, [rcx+18h]
0x14002ab20  lea     r8, WPP_1d82a8cff87b33874cd31050c50ab9c4_Traceguids
0x14002ab27  mov     r9d, ebx
0x14002ab2a  call    WPP_SF_d
0x14002ab2f  jmp     loc_14002B141
0x14002ab34  mov     rax, cs:WdfFunctions_01033
0x14002ab3b  lea     r8, SDDL_DEVOBJ_KERNEL_ONLY
0x14002ab42  mov     rdx, [rsp+280h+var_238]
0x14002ab47  mov     rcx, cs:WdfDriverGlobals
0x14002ab4e  mov     rax, [rax+220h]
0x14002ab55  call    _guard_dispatch_icall
0x14002ab5a  mov     ebx, eax
0x14002ab5c  test    eax, eax
0x14002ab5e  jns     short loc_14002AB94
0x14002ab60  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab67  lea     rax, WPP_GLOBAL_Control
0x14002ab6e  cmp     rcx, rax
0x14002ab71  jz      loc_14002B141
0x14002ab77  mov     eax, [rcx+2Ch]
0x14002ab7a  test    r14b, al
0x14002ab7d  jz      loc_14002B141
0x14002ab83  cmp     [rcx+29h], r15b
0x14002ab87  jb      loc_14002B141
0x14002ab8d  mov     edx, 0Ch
0x14002ab92  jmp     short loc_14002AB1C
0x14002ab94  mov     rax, cs:WdfFunctions_01033
0x14002ab9b  lea     r8, RootFileRdmaIoctlPreprocess
0x14002aba2  mov     rdx, [rsp+280h+var_238]
0x14002aba7  mov     r9b, 0Eh
0x14002abaa  mov     rcx, cs:WdfDriverGlobals
0x14002abb1  mov     [rsp+280h+var_258], 0
0x14002abb9  mov     rax, [rax+248h]
0x14002abc0  mov     [rsp+280h+var_260], 0
0x14002abc9  call    _guard_dispatch_icall
0x14002abce  mov     ebx, eax
0x14002abd0  test    eax, eax
0x14002abd2  js      loc_14002B141
0x14002abd8  lea     rdx, aCallbackSoftre; "\\Callback\\SoftRestart"
0x14002abdf  lea     rcx, [rbp+180h+DestinationString]; DestinationString
0x14002abe3  call    cs:__imp_RtlInitUnicodeString
0x14002abea  nop     dword ptr [rax+rax+00h]
0x14002abef  lea     rax, [rbp+180h+DestinationString]
0x14002abf3  mov     [rbp+180h+ObjectAttributes.Length], 30h ; '0'
0x14002abfa  xorps   xmm0, xmm0
0x14002abfd  mov     [rbp+180h+ObjectAttributes.ObjectName], rax
0x14002ac01  mov     r9b, r14b; AllowMultipleCallbacks
0x14002ac04  mov     [rbp+180h+ObjectAttributes.RootDirectory], 0
0x14002ac0c  xor     r8d, r8d; Create
0x14002ac0f  mov     [rbp+180h+ObjectAttributes.Attributes], 50h ; 'P'
0x14002ac16  lea     rdx, [rbp+180h+ObjectAttributes]; ObjectAttributes
0x14002ac1a  lea     rcx, KsrCallbackObject; CallbackObject
0x14002ac21  movdqu  xmmword ptr [rbp+180h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002ac26  call    cs:__imp_ExCreateCallback
0x14002ac2d  nop     dword ptr [rax+rax+00h]
0x14002ac32  test    eax, eax
0x14002ac34  js      short loc_14002AC53
0x14002ac36  mov     rcx, cs:KsrCallbackObject; CallbackObject
0x14002ac3d  lea     rdx, RootDeviceKsrCallback; CallbackFunction
0x14002ac44  xor     r8d, r8d; CallbackContext
0x14002ac47  call    cs:__imp_ExRegisterCallback
0x14002ac4e  nop     dword ptr [rax+rax+00h]
0x14002ac53  mov     rcx, [rsp+280h+var_238]
0x14002ac58  call    RootFileInit
0x14002ac5d  mov     ebx, eax
0x14002ac5f  test    eax, eax
0x14002ac61  jns     short loc_14002AC9A
0x14002ac63  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ac6a  lea     rax, WPP_GLOBAL_Control
0x14002ac71  cmp     rcx, rax
0x14002ac74  jz      loc_14002B141
0x14002ac7a  mov     eax, [rcx+2Ch]
0x14002ac7d  test    r14b, al
0x14002ac80  jz      loc_14002B141
0x14002ac86  cmp     [rcx+29h], r15b
0x14002ac8a  jb      loc_14002B141
0x14002ac90  mov     edx, 0Dh
0x14002ac95  jmp     loc_14002AB1C
0x14002ac9a  mov     rcx, [rsp+280h+var_238]
0x14002ac9f  call    AddFdoSupportedInterfaces
0x14002aca4  mov     ebx, eax
0x14002aca6  test    eax, eax
0x14002aca8  js      loc_14002B141
0x14002acae  mov     rax, cs:WdfFunctions_01033
0x14002acb5  lea     r9, [rsp+280h+var_240]
0x14002acba  mov     rcx, cs:WdfDriverGlobals
0x14002acc1  lea     r8, [rsp+280h+var_228]
0x14002acc6  lea     rdx, [rsp+280h+var_238]
0x14002accb  mov     rax, [rax+258h]
0x14002acd2  call    _guard_dispatch_icall
0x14002acd7  mov     ebx, eax
0x14002acd9  test    eax, eax
0x14002acdb  jns     short loc_14002AD14
0x14002acdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ace4  lea     rax, WPP_GLOBAL_Control
0x14002aceb  cmp     rcx, rax
0x14002acee  jz      loc_14002B141
0x14002acf4  mov     eax, [rcx+2Ch]
0x14002acf7  test    r14b, al
0x14002acfa  jz      loc_14002B141
0x14002ad00  cmp     [rcx+29h], r15b
0x14002ad04  jb      loc_14002B141
  ... truncated ...
```
