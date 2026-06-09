# SqospCreateDevice

- ea: `0x1400111bc`
- end: `0x140011727`
- name: `SqospCreateDevice`
- size: `1387`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFLT_VOLUME Volume)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x140014b80`

## callees

- `0x140003870`
- `0x140003a10`
- `0x140003ec0`
- `0x140004520`
- `0x140004fd0`
- `0x140005b08`
- `0x14000666c`
- `0x140006c50`
- `0x1400077b0`
- `0x140008d20`
- `0x140009240`
- `0x140011138`
- `0x1400111bc`
- `0x140011b00`
- `0x140011c5c`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x140011314`
- `ntoskrnl!InitializeSListHead` at `0x14001132b`
- `ntoskrnl!InitializeSListHead` at `0x140011314`
- `ntoskrnl!InitializeSListHead` at `0x14001132b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400112d1`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400112d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400116be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400116be`
- `ntoskrnl!PcwCreateInstance` at `0x140011583`
- `ntoskrnl!PcwCreateInstance` at `0x140011583`
- `ntoskrnl!KeInitializeTimer` at `0x140011370`
- `ntoskrnl!KeInitializeTimer` at `0x1400113a5`
- `ntoskrnl!KeInitializeTimer` at `0x140011370`
- `ntoskrnl!KeInitializeTimer` at `0x1400113a5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011259`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011342`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011359`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011259`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011342`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011359`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x140011497`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x140011497`
- `ntoskrnl!ObfDereferenceObject` at `0x1400116dc`
- `ntoskrnl!ObfDereferenceObject` at `0x1400116dc`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400112e2`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400112e2`
- `ntoskrnl!KeInitializeDpc` at `0x14001138e`
- `ntoskrnl!KeInitializeDpc` at `0x1400113c3`
- `ntoskrnl!KeInitializeDpc` at `0x14001138e`
- `ntoskrnl!KeInitializeDpc` at `0x1400113c3`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011282`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011282`
- `FLTMGR!FltAllocateContext` at `0x140011227`
- `FLTMGR!FltAllocateContext` at `0x140011227`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140011479`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140011479`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140011598`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140011598`
- `FLTMGR!FltSetInstanceContext` at `0x14001165c`
- `FLTMGR!FltSetInstanceContext` at `0x14001165c`
- `FLTMGR!FltReleaseContext` at `0x1400116fa`
- `FLTMGR!FltReleaseContext` at `0x1400116fa`
- `FLTMGR!FltReleasePushLockEx` at `0x140011642`
- `FLTMGR!FltReleasePushLockEx` at `0x140011642`

## pseudocode

```c
__int64 __fastcall SqospCreateDevice(PFLT_INSTANCE Instance, PFLT_VOLUME Volume, int a3, PFLT_CONTEXT *a4)
{
  NTSTATUS v8; // ebx
  _QWORD *v9; // rbx
  ULONG MaximumProcessorCount; // eax
  int VolumeId; // eax
  struct _UNICODE_STRING *p_DosName; // rdx
  _QWORD *v13; // rbx
  __int64 v14; // rcx
  char *v15; // rdx
  _QWORD *v16; // rdx
  __int64 i; // rcx
  __int64 v18; // r8
  _QWORD *v19; // rcx
  PFLT_CONTEXT DeferredContext; // [rsp+50h] [rbp-49h] BYREF
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+58h] [rbp-41h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+60h] [rbp-39h] BYREF
  __int128 v24; // [rsp+70h] [rbp-29h] BYREF
  struct _PCW_DATA Data; // [rsp+80h] [rbp-19h] BYREF
  char *v26; // [rsp+90h] [rbp-9h]
  int v27; // [rsp+98h] [rbp-1h]
  char *v28; // [rsp+A0h] [rbp+7h]
  int v29; // [rsp+A8h] [rbp+Fh]

  DeferredContext = 0;
  DiskDeviceObject = 0;
  v24 = 0;
  DosName = 0;
  v8 = FltAllocateContext((PFLT_FILTER)Filter, 2u, 0x1140u, (POOL_TYPE)512, &DeferredContext);
  if ( v8 < 0 )
    goto LABEL_44;
  memset(DeferredContext, 0, 0x1140u);
  KeInitializeSpinLock((PKSPIN_LOCK)DeferredContext + 24);
  *((_QWORD *)DeferredContext + 25) = Instance;
  *(_QWORD *)DeferredContext = Volume;
  v9 = DeferredContext;
  v9[5] = IoAllocateWorkItem(DeviceObject);
  if ( !*((_QWORD *)DeferredContext + 5) )
    goto LABEL_3;
  ExInitializeLookasideListEx(
    (PLOOKASIDE_LIST_EX)((char *)DeferredContext + 48),
    0,
    0,
    (POOL_TYPE)516,
    0,
    0x240u,
    0x46535153u,
    0);
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  *((_QWORD *)DeferredContext + 18) = PplpCreateLookasideListEx(MaximumProcessorCount);
  if ( !*((_QWORD *)DeferredContext + 18) )
    goto LABEL_3;
  InitializeSListHead((PSLIST_HEADER)DeferredContext + 16);
  InitializeSListHead((PSLIST_HEADER)DeferredContext + 17);
  KeInitializeSpinLock((PKSPIN_LOCK)DeferredContext + 104);
  KeInitializeSpinLock((PKSPIN_LOCK)DeferredContext + 136);
  KeInitializeTimer((PKTIMER)((char *)DeferredContext + 296));
  KeInitializeDpc((PRKDPC)((char *)DeferredContext + 360), SqosDeviceTimerRoutine, DeferredContext);
  KeInitializeTimer((PKTIMER)((char *)DeferredContext + 4168));
  KeInitializeDpc((PRKDPC)((char *)DeferredContext + 4232), SqosVolumeStatsTimerRoutine, DeferredContext);
  v8 = SqospInitializeDelayedJobQueue(Instance, (char *)DeferredContext + 448);
  if ( v8 >= 0 )
  {
    v8 = SqospInitializeDelayedJobQueue(Instance, (char *)DeferredContext + 640);
    if ( v8 >= 0 )
    {
      *((_DWORD *)DeferredContext + 47) = a3 == 27 || byte_14000D2AA ? 2 : 1;
      VolumeId = SqospQueryVolumeId(Volume);
      v8 = VolumeId;
      if ( VolumeId == -1073741267 )
      {
        if ( *((_DWORD *)DeferredContext + 47) == 2 )
          *((_BYTE *)DeferredContext + 929) = 1;
      }
      else if ( VolumeId < 0 )
      {
        goto LABEL_44;
      }
      v8 = FltGetDiskDeviceObject(Volume, &DiskDeviceObject);
      if ( v8 >= 0 )
      {
        if ( IoVolumeDeviceToDosName(DiskDeviceObject, &DosName) < 0 )
        {
          p_DosName = (struct _UNICODE_STRING *)&v24;
          if ( !(_WORD)v24 )
            p_DosName = (struct _UNICODE_STRING *)&UNKNOWN_OBJECT_NAME;
        }
        else
        {
          p_DosName = &DosName;
        }
        v8 = SqospCopyUnicodeString((PUNICODE_STRING)((char *)DeferredContext + 24), p_DosName);
        if ( v8 >= 0 )
        {
          BalanceInitializeDevice(DeferredContext);
          v13 = DeferredContext;
          v13[22] = SqospCreateClient();
          v14 = *((_QWORD *)DeferredContext + 22);
          if ( v14 )
          {
            *(_BYTE *)(v14 + 124) = 1;
            if ( SqospLookupFlow(*((PKSPIN_LOCK *)DeferredContext + 22)) )
            {
              if ( (_BYTE)word_14000D2A8 )
              {
                Data.Data = DeferredContext;
                v27 = 24;
                v29 = 24;
                v26 = (char *)DeferredContext + 4088;
                Data.Size = 4416;
                v28 = (char *)DeferredContext + 4112;
                PcwCreateInstance(
                  (PPCW_INSTANCE *)DeferredContext + 19,
                  SqosPcDeviceCounterSet,
                  (PCUNICODE_STRING)((char *)DeferredContext + 24),
                  3u,
                  &Data);
              }
              FltAcquirePushLockExclusiveEx(&SqosGlobals, 0);
              v15 = (char *)DeferredContext;
              if ( ClientPort && *((_DWORD *)DeferredContext + 47) == 2 )
              {
                SqospInitializeVolumeStatsReporting(DeferredContext);
                v15 = (char *)DeferredContext;
              }
              if ( !(unsigned __int8)SqospIsNullGuid(v15 + 8) )
              {
                for ( i = qword_14000D148; (__int64 *)i != &qword_14000D148; i = *(_QWORD *)i )
                {
                  v18 = v16[1] - *(_QWORD *)(i - 152);
                  if ( !v18 )
                    v18 = v16[2] - *(_QWORD *)(i - 144);
                  if ( !v18 )
                  {
                    *(_BYTE *)(i + 25) = 1;
                    v16 = DeferredContext;
                  }
                }
              }
              v19 = (_QWORD *)qword_14000D150;
              if ( *(__int64 **)qword_14000D150 != &qword_14000D148 )
                __fastfail(3u);
              v16[21] = qword_14000D150;
              v16[20] = &qword_14000D148;
              *v19 = v16 + 20;
              qword_14000D150 = (__int64)(v16 + 20);
              FltReleasePushLockEx(&SqosGlobals, 0);
              v8 = FltSetInstanceContext(Instance, FLT_SET_CONTEXT_KEEP_IF_EXISTS, DeferredContext, 0);
              if ( v8 >= 0 )
              {
                *a4 = DeferredContext;
                DeferredContext = 0;
              }
              else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  13,
                  WPP_af53c64ad8bd3a498290aca5a9ae070a_Traceguids,
                  (unsigned int)v8);
              }
              goto LABEL_44;
            }
          }
LABEL_3:
          v8 = -1073741670;
        }
      }
    }
  }
LABEL_44:
  if ( DosName.Buffer )
    ExFreePoolWithTag(DosName.Buffer, 0);
  SqospFreeUnicodeString(&v24);
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
  if ( DeferredContext )
  {
    SqospRemoveDevice();
    FltReleaseContext(DeferredContext);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400111bc  push    rbp
0x1400111be  push    rbx
0x1400111bf  push    rsi
0x1400111c0  push    rdi
0x1400111c1  push    r12
0x1400111c3  push    r14
0x1400111c5  push    r15
0x1400111c7  lea     rbp, [rsp-27h]
0x1400111cc  sub     rsp, 0C0h
0x1400111d3  mov     rax, cs:__security_cookie
0x1400111da  xor     rax, rsp
0x1400111dd  mov     [rbp+57h+var_40], rax
0x1400111e1  xor     r12d, r12d
0x1400111e4  lea     rax, [rbp+57h+DeferredContext]
0x1400111e8  mov     r15, r9
0x1400111eb  mov     [rbp+57h+DeferredContext], r12
0x1400111ef  mov     esi, r8d
0x1400111f2  mov     [rbp+57h+DiskDeviceObject], r12
0x1400111f6  mov     rdi, rdx
0x1400111f9  mov     [rsp+0F0h+ReturnedContext], rax; ReturnedContext
0x1400111fe  mov     r14, rcx
0x140011201  lea     edx, [r12+2]; ContextType
0x140011206  mov     rcx, cs:Filter; Filter
0x14001120d  xorps   xmm0, xmm0
0x140011210  xorps   xmm1, xmm1
0x140011213  mov     r9d, 200h; PoolType
0x140011219  mov     r8d, 1140h; ContextSize
0x14001121f  movups  [rbp+57h+var_80], xmm0
0x140011223  movups  xmmword ptr [rbp+57h+DosName.Length], xmm1
0x140011227  call    cs:__imp_FltAllocateContext
0x14001122e  nop     dword ptr [rax+rax+00h]
0x140011233  mov     ebx, eax
0x140011235  test    eax, eax
0x140011237  js      loc_1400116B3
0x14001123d  mov     rcx, [rbp+57h+DeferredContext]; void *
0x140011241  xor     edx, edx; Val
0x140011243  mov     r8d, 1140h; Size
0x140011249  call    memset
0x14001124e  mov     rcx, [rbp+57h+DeferredContext]
0x140011252  add     rcx, 0C0h; SpinLock
0x140011259  call    cs:__imp_KeInitializeSpinLock
0x140011260  nop     dword ptr [rax+rax+00h]
0x140011265  mov     rax, [rbp+57h+DeferredContext]
0x140011269  mov     [rax+0C8h], r14
0x140011270  mov     rax, [rbp+57h+DeferredContext]
0x140011274  mov     [rax], rdi
0x140011277  mov     rcx, cs:DeviceObject; DeviceObject
0x14001127e  mov     rbx, [rbp+57h+DeferredContext]
0x140011282  call    cs:__imp_IoAllocateWorkItem
0x140011289  nop     dword ptr [rax+rax+00h]
0x14001128e  mov     [rbx+28h], rax
0x140011292  mov     rcx, [rbp+57h+DeferredContext]
0x140011296  cmp     [rcx+28h], r12
0x14001129a  jnz     short loc_1400112A6
0x14001129c  mov     ebx, 0C000009Ah
0x1400112a1  jmp     loc_1400116B3
0x1400112a6  mov     [rsp+0F0h+Depth], r12w; Depth
0x1400112ac  add     rcx, 30h ; '0'; Lookaside
0x1400112b0  mov     [rsp+0F0h+Tag], 46535153h; Tag
0x1400112b8  mov     r9d, 204h; PoolType
0x1400112be  mov     [rsp+0F0h+Size], 240h; Size
0x1400112c7  xor     r8d, r8d; Free
0x1400112ca  xor     edx, edx; Allocate
0x1400112cc  mov     dword ptr [rsp+0F0h+ReturnedContext], r12d; Flags
0x1400112d1  call    cs:__imp_ExInitializeLookasideListEx
0x1400112d8  nop     dword ptr [rax+rax+00h]
0x1400112dd  mov     ecx, 0FFFFh; GroupNumber
0x1400112e2  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400112e9  nop     dword ptr [rax+rax+00h]
0x1400112ee  mov     ecx, eax
0x1400112f0  call    PplpCreateLookasideListEx
0x1400112f5  mov     rcx, [rbp+57h+DeferredContext]
0x1400112f9  mov     [rcx+90h], rax
0x140011300  mov     rcx, [rbp+57h+DeferredContext]
0x140011304  cmp     [rcx+90h], r12
0x14001130b  jz      short loc_14001129C
0x14001130d  add     rcx, 100h; SListHead
0x140011314  call    cs:__imp_InitializeSListHead
0x14001131b  nop     dword ptr [rax+rax+00h]
0x140011320  mov     rcx, [rbp+57h+DeferredContext]
0x140011324  add     rcx, 110h; SListHead
0x14001132b  call    cs:__imp_InitializeSListHead
0x140011332  nop     dword ptr [rax+rax+00h]
0x140011337  mov     rcx, [rbp+57h+DeferredContext]
0x14001133b  add     rcx, 340h; SpinLock
0x140011342  call    cs:__imp_KeInitializeSpinLock
0x140011349  nop     dword ptr [rax+rax+00h]
0x14001134e  mov     rcx, [rbp+57h+DeferredContext]
0x140011352  add     rcx, 440h; SpinLock
0x140011359  call    cs:__imp_KeInitializeSpinLock
0x140011360  nop     dword ptr [rax+rax+00h]
0x140011365  mov     rcx, [rbp+57h+DeferredContext]
0x140011369  add     rcx, 128h; Timer
0x140011370  call    cs:__imp_KeInitializeTimer
0x140011377  nop     dword ptr [rax+rax+00h]
0x14001137c  mov     r8, [rbp+57h+DeferredContext]; DeferredContext
0x140011380  lea     rdx, SqosDeviceTimerRoutine; DeferredRoutine
0x140011387  lea     rcx, [r8+168h]; Dpc
0x14001138e  call    cs:__imp_KeInitializeDpc
0x140011395  nop     dword ptr [rax+rax+00h]
0x14001139a  mov     rcx, [rbp+57h+DeferredContext]
0x14001139e  add     rcx, 1048h; Timer
0x1400113a5  call    cs:__imp_KeInitializeTimer
0x1400113ac  nop     dword ptr [rax+rax+00h]
0x1400113b1  mov     r8, [rbp+57h+DeferredContext]; DeferredContext
0x1400113b5  lea     rdx, SqosVolumeStatsTimerRoutine; DeferredRoutine
0x1400113bc  lea     rcx, [r8+1088h]; Dpc
0x1400113c3  call    cs:__imp_KeInitializeDpc
0x1400113ca  nop     dword ptr [rax+rax+00h]
0x1400113cf  mov     rdx, [rbp+57h+DeferredContext]
0x1400113d3  mov     rcx, r14
0x1400113d6  add     rdx, 1C0h
0x1400113dd  call    SqospInitializeDelayedJobQueue
0x1400113e2  mov     ebx, eax
0x1400113e4  test    eax, eax
0x1400113e6  js      loc_1400116B3
0x1400113ec  mov     rdx, [rbp+57h+DeferredContext]
0x1400113f0  mov     rcx, r14
0x1400113f3  add     rdx, 280h
0x1400113fa  call    SqospInitializeDelayedJobQueue
0x1400113ff  mov     ebx, eax
0x140011401  test    eax, eax
0x140011403  js      loc_1400116B3
0x140011409  cmp     esi, 1Bh
0x14001140c  jz      short loc_140011427
0x14001140e  cmp     cs:byte_14000D2AA, r12b
0x140011415  jnz     short loc_140011427
0x140011417  mov     rax, [rbp+57h+DeferredContext]
0x14001141b  mov     dword ptr [rax+0BCh], 1
0x140011425  jmp     short loc_140011435
0x140011427  mov     rax, [rbp+57h+DeferredContext]
0x14001142b  mov     dword ptr [rax+0BCh], 2
0x140011435  mov     r8, [rbp+57h+DeferredContext]
0x140011439  mov     rcx, rdi; Volume
0x14001143c  add     r8, 8
0x140011440  cmp     esi, 1Bh
0x140011443  setz    dl
0x140011446  call    SqospQueryVolumeId
0x14001144b  mov     ebx, eax
0x14001144d  cmp     eax, 0C000022Dh
0x140011452  jnz     short loc_14001146A
0x140011454  mov     rax, [rbp+57h+DeferredContext]
0x140011458  cmp     dword ptr [rax+0BCh], 2
0x14001145f  jnz     short loc_140011472
0x140011461  mov     byte ptr [rax+3A1h], 1
0x140011468  jmp     short loc_140011472
0x14001146a  test    eax, eax
0x14001146c  js      loc_1400116B3
0x140011472  lea     rdx, [rbp+57h+DiskDeviceObject]; DiskDeviceObject
0x140011476  mov     rcx, rdi; Volume
0x140011479  call    cs:__imp_FltGetDiskDeviceObject
0x140011480  nop     dword ptr [rax+rax+00h]
0x140011485  mov     ebx, eax
0x140011487  test    eax, eax
0x140011489  js      loc_1400116B3
0x14001148f  mov     rcx, [rbp+57h+DiskDeviceObject]; VolumeDeviceObject
0x140011493  lea     rdx, [rbp+57h+DosName]; DosName
0x140011497  call    cs:__imp_IoVolumeDeviceToDosName
0x14001149e  nop     dword ptr [rax+rax+00h]
0x1400114a3  test    eax, eax
0x1400114a5  js      short loc_1400114AD
0x1400114a7  lea     rdx, [rbp+57h+DosName]
0x1400114ab  jmp     short loc_1400114BF
0x1400114ad  lea     rdx, [rbp+57h+var_80]
0x1400114b1  cmp     word ptr [rbp+57h+var_80], r12w
0x1400114b6  ja      short loc_1400114BF
0x1400114b8  lea     rdx, UNKNOWN_OBJECT_NAME; SourceString
0x1400114bf  mov     rcx, [rbp+57h+DeferredContext]
0x1400114c3  add     rcx, 18h; DestinationString
0x1400114c7  call    SqospCopyUnicodeString
0x1400114cc  mov     ebx, eax
0x1400114ce  test    eax, eax
0x1400114d0  js      loc_1400116B3
0x1400114d6  mov     rcx, [rbp+57h+DeferredContext]
0x1400114da  call    BalanceInitializeDevice
0x1400114df  mov     rbx, [rbp+57h+DeferredContext]
0x1400114e3  call    SqospCreateClient
0x1400114e8  mov     [rbx+0B0h], rax
0x1400114ef  mov     rax, [rbp+57h+DeferredContext]
0x1400114f3  mov     rcx, [rax+0B0h]
0x1400114fa  test    rcx, rcx
0x1400114fd  jz      loc_14001129C
0x140011503  mov     byte ptr [rcx+7Ch], 1
0x140011507  xor     r9d, r9d
0x14001150a  mov     rcx, [rbp+57h+DeferredContext]
0x14001150e  xor     r8d, r8d
0x140011511  mov     rdx, rcx
0x140011514  mov     rcx, [rcx+0B0h]; SpinLock
0x14001151b  call    SqospLookupFlow
0x140011520  test    rax, rax
0x140011523  jz      loc_14001129C
0x140011529  cmp     byte ptr cs:word_14000D2A8, r12b
0x140011530  mov     ebx, 3
0x140011535  jz      short loc_14001158F
0x140011537  mov     rcx, [rbp+57h+DeferredContext]
0x14001153b  lea     edx, [rbx+15h]
0x14001153e  mov     [rbp+57h+Data.Data], rcx
0x140011542  mov     r9d, ebx; Count
0x140011545  mov     [rbp+57h+var_58], edx
0x140011548  mov     [rbp+57h+var_48], edx
0x14001154b  mov     rdx, cs:SqosPcDeviceCounterSet; Registration
0x140011552  lea     rax, [rcx+0FF8h]
0x140011559  mov     [rbp+57h+var_60], rax
0x14001155d  lea     r8, [rcx+18h]; Name
0x140011561  lea     rax, [rcx+1010h]
0x140011568  mov     [rbp+57h+Data.Size], 1140h
0x14001156f  mov     [rbp+57h+var_50], rax
0x140011573  add     rcx, 98h; Instance
0x14001157a  lea     rax, [rbp+57h+Data]
0x14001157e  mov     [rsp+0F0h+ReturnedContext], rax; Data
0x140011583  call    cs:__imp_PcwCreateInstance
0x14001158a  nop     dword ptr [rax+rax+00h]
0x14001158f  xor     edx, edx
0x140011591  lea     rcx, SqosGlobals
0x140011598  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001159f  nop     dword ptr [rax+rax+00h]
0x1400115a4  cmp     cs:ClientPort, r12
0x1400115ab  mov     rdx, [rbp+57h+DeferredContext]
0x1400115af  jz      short loc_1400115C6
0x1400115b1  cmp     dword ptr [rdx+0BCh], 2
0x1400115b8  jnz     short loc_1400115C6
0x1400115ba  mov     rcx, rdx
0x1400115bd  call    SqospInitializeVolumeStatsReporting
0x1400115c2  mov     rdx, [rbp+57h+DeferredContext]
0x1400115c6  lea     rcx, [rdx+8]
0x1400115ca  call    SqospIsNullGuid
0x1400115cf  lea     r9, qword_14000D148
0x1400115d6  test    al, al
0x1400115d8  jnz     short loc_140011610
0x1400115da  mov     rcx, cs:qword_14000D148
0x1400115e1  jmp     short loc_14001160B
0x1400115e3  mov     r8, [rdx+8]
0x1400115e7  sub     r8, [rcx-98h]
0x1400115ee  jnz     short loc_1400115FB
0x1400115f0  mov     r8, [rdx+10h]
0x1400115f4  sub     r8, [rcx-90h]
0x1400115fb  test    r8, r8
0x1400115fe  jnz     short loc_140011608
0x140011600  mov     byte ptr [rcx+19h], 1
0x140011604  mov     rdx, [rbp+57h+DeferredContext]
0x140011608  mov     rcx, [rcx]
0x14001160b  cmp     rcx, r9
0x14001160e  jnz     short loc_1400115E3
0x140011610  mov     rcx, cs:qword_14000D150
0x140011617  cmp     [rcx], r9
0x14001161a  jz      short loc_140011621
0x14001161c  mov     rcx, rbx
0x14001161f  int     29h; Win8: RtlFailFast(ecx)
0x140011621  lea     rax, [rdx+0A0h]
0x140011628  xor     edx, edx
0x14001162a  mov     [rax+8], rcx
0x14001162e  mov     [rax], r9
0x140011631  mov     [rcx], rax
0x140011634  lea     rcx, SqosGlobals
0x14001163b  mov     cs:qword_14000D150, rax
0x140011642  call    cs:__imp_FltReleasePushLockEx
0x140011649  nop     dword ptr [rax+rax+00h]
0x14001164e  mov     r8, [rbp+57h+DeferredContext]; NewContext
0x140011652  xor     r9d, r9d; OldContext
0x140011655  mov     rcx, r14; Instance
0x140011658  lea     edx, [r9+1]; Operation
0x14001165c  call    cs:__imp_FltSetInstanceContext
0x140011663  nop     dword ptr [rax+rax+00h]
0x140011668  mov     ebx, eax
0x14001166a  test    eax, eax
0x14001166c  jns     short loc_1400116A8
0x14001166e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011675  lea     rax, WPP_GLOBAL_Control
0x14001167c  cmp     rcx, rax
0x14001167f  jz      short loc_1400116B3
0x140011681  mov     eax, [rcx+2Ch]
0x140011684  test    al, 10h
0x140011686  jz      short loc_1400116B3
0x140011688  cmp     byte ptr [rcx+29h], 2
0x14001168c  jb      short loc_1400116B3
0x14001168e  mov     rcx, [rcx+18h]
0x140011692  lea     r8, WPP_af53c64ad8bd3a498290aca5a9ae070a_Traceguids
0x140011699  mov     edx, 0Dh
0x14001169e  mov     r9d, ebx
0x1400116a1  call    WPP_SF_d
0x1400116a6  jmp     short loc_1400116B3
0x1400116a8  mov     rax, [rbp+57h+DeferredContext]
0x1400116ac  mov     [r15], rax
0x1400116af  mov     [rbp+57h+DeferredContext], r12
0x1400116b3  mov     rcx, [rbp+57h+DosName.Buffer]; P
0x1400116b7  test    rcx, rcx
0x1400116ba  jz      short loc_1400116CA
0x1400116bc  xor     edx, edx; Tag
0x1400116be  call    cs:__imp_ExFreePoolWithTag
0x1400116c5  nop     dword ptr [rax+rax+00h]
0x1400116ca  lea     rcx, [rbp+57h+var_80]
0x1400116ce  call    SqospFreeUnicodeString
0x1400116d3  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x1400116d7  test    rcx, rcx
0x1400116da  jz      short loc_1400116E8
0x1400116dc  call    cs:__imp_ObfDereferenceObject
0x1400116e3  nop     dword ptr [rax+rax+00h]
0x1400116e8  mov     rcx, [rbp+57h+DeferredContext]
0x1400116ec  test    rcx, rcx
0x1400116ef  jz      short loc_140011706
  ... truncated ...
```
