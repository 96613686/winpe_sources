# NtUserDisplayConfigGetDeviceInfo

- ea: `0x1400f01b0`
- end: `0x1400f07f1`
- name: `NtUserDisplayConfigGetDeviceInfo`
- size: `1601`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x140029224`
- `0x140029e04`
- `0x14006e970`
- `0x14006f3a4`
- `0x14007b930`
- `0x14007df80`
- `0x1400a1c30`
- `0x1400f01b0`
- `0x1400f0800`
- `0x1400f0840`
- `0x1400f08ac`
- `0x1400f0ed0`
- `0x1400f0fe4`
- `0x1401f2a64`
- `0x140238970`
- `0x140238f80`
- `0x1402bb054`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400f0355`
- `ntoskrnl!ProbeForRead` at `0x1400f0355`
- `ntoskrnl!ExRaiseStatus` at `0x1400f0318`
- `ntoskrnl!ExRaiseStatus` at `0x1400f0329`
- `ntoskrnl!ExRaiseStatus` at `0x1400f0318`
- `ntoskrnl!ExRaiseStatus` at `0x1400f0329`
- `ntoskrnl!ProbeForWrite` at `0x1400f047b`
- `ntoskrnl!ProbeForWrite` at `0x1400f04b8`
- `ntoskrnl!ProbeForWrite` at `0x1400f047b`
- `ntoskrnl!ProbeForWrite` at `0x1400f04b8`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400f0335`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400f045b`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400f0498`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400f0335`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400f045b`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400f0498`
- `watchdog!WdLogSingleEntry5` at `0x1400f072a`
- `watchdog!WdLogSingleEntry5` at `0x1400f072a`
- `watchdog!WdLogSingleEntry2` at `0x1400f02fd`
- `watchdog!WdLogSingleEntry2` at `0x1400f074e`
- `watchdog!WdLogSingleEntry2` at `0x1400f07a3`
- `watchdog!WdLogSingleEntry2` at `0x1400f07c9`
- `watchdog!WdLogSingleEntry2` at `0x1400f02fd`
- `watchdog!WdLogSingleEntry2` at `0x1400f074e`
- `watchdog!WdLogSingleEntry2` at `0x1400f07a3`
- `watchdog!WdLogSingleEntry2` at `0x1400f07c9`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400f01fa`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400f052d`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400f01fa`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400f052d`
- `WIN32K!W32GetUserSessionState` at `0x1400f0764`
- `WIN32K!W32GetUserSessionState` at `0x1400f0764`

## pseudocode

```c
__int64 __fastcall NtUserDisplayConfigGetDeviceInfo(char *a1)
{
  volatile void **v2; // rdi
  void *v3; // r12
  unsigned int v4; // r15d
  int v5; // r13d
  unsigned int ULongFromUser; // eax
  unsigned __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r15
  __int64 CurrentProcessWow64Process; // rax
  unsigned __int64 v11; // rcx
  int DeviceInfoInternal; // ebx
  char v13; // al
  int GetterTypeSize; // eax
  volatile void *v15; // r15
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // r13d
  __int64 v24; // r14
  __int64 v25; // r15
  __int64 UserSessionState; // rax
  unsigned int v27; // [rsp+30h] [rbp-A8h]
  __int64 v28; // [rsp+38h] [rbp-A0h]
  _DWORD v29[22]; // [rsp+80h] [rbp-58h] BYREF
  int Src; // [rsp+E8h] [rbp+10h] BYREF
  int v31; // [rsp+F0h] [rbp+18h] BYREF
  volatile void *Address; // [rsp+F8h] [rbp+20h] BYREF

  v2 = 0;
  v3 = 0;
  Address = 0;
  v4 = 0;
  v27 = 0;
  v28 = 0;
  v5 = 0;
  if ( !*(_DWORD *)(W32GetUserGdiSessionState() + 32) )
  {
    DeviceInfoInternal = -1073741823;
    v31 = -1073741823;
    goto LABEL_47;
  }
  ULongFromUser = RtlReadULongFromUser(a1 + 4);
  v8 = ULongFromUser;
  if ( ULongFromUser < 0x14 )
    ExRaiseStatus(-1073741811);
  v9 = ULongFromUser;
  v2 = (volatile void **)Win32AllocPoolWithQuotaZInitImpl(v7, ULongFromUser, 0x63447355u);
  if ( !v2 )
  {
    if ( (unsigned int)RtlReadULongFromUser(a1) == -21 && v8 == 2056 )
    {
      RtlReadULongFromUser(a1 + 2016);
      RtlReadULongFromUser(a1 + 2020);
      Src = 0;
      RtlCopyToUser(a1 + 2016, &Src, 4u);
      v31 = 0;
      RtlCopyToUser(a1 + 2020, &v31, 4u);
      LODWORD(Address) = 1144084230;
      RtlCopyToUser(a1 + 2024, &Address, 4u);
    }
    WdLogSingleEntry2(2, v9, 1144084230);
    WdLogGlobalForLineNumber = 2252;
    ExRaiseStatus(-1073741801);
  }
  CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
  ProbeForRead(a1, v8, CurrentProcessWow64Process != 0 ? 1 : 4);
  RtlCopyVolatileMemory(v2, a1, v8);
  *((_DWORD *)v2 + 1) = v8;
  v11 = *(unsigned int *)v2;
  if ( (_DWORD)v11 != -21 )
  {
    if ( (_DWORD)v11 != -15 )
      goto LABEL_11;
    if ( v8 == 32 )
    {
      v19 = *((_DWORD *)v2 + 5);
      if ( !v19 )
        goto LABEL_11;
      v3 = Win32AllocPoolWithQuotaZInitImpl(v11, v19, 0x63447355u);
      if ( v3 )
      {
        Address = v2[3];
        v2[3] = v3;
        goto LABEL_11;
      }
      DeviceInfoInternal = -1073741801;
LABEL_45:
      v31 = DeviceInfoInternal;
LABEL_46:
      v4 = v27;
LABEL_47:
      if ( v5 )
      {
        memset(v29, 0, 28);
        DrvSampleDisplayState(v29);
        if ( v28 == __PAIR64__(v29[0], v29[2]) )
        {
          v23 = 1;
          v24 = (int)v4;
          v25 = DeviceInfoInternal;
        }
        else
        {
          v23 = 0;
          Src = 0;
          RtlCopyToUser(a1 + 2024, &Src, 4u);
          v24 = (int)v4;
          WdLogSingleEntry5(2, HIDWORD(v28), (unsigned int)v28, v29[0], v29[2], (int)v4);
          WdLogGlobalForLineNumber = 2429;
          v25 = DeviceInfoInternal;
          WdLogSingleEntry2(2, DeviceInfoInternal, v24);
          WdLogGlobalForLineNumber = 2434;
        }
        UserSessionState = W32GetUserSessionState(v21, v20, v22);
        if ( *(_DWORD *)(UserSessionState + 56768) )
        {
          WdLogSingleEntry2(2, v25, v24);
          WdLogGlobalForLineNumber = 2464;
        }
        else if ( v23 )
        {
          *(_DWORD *)(UserSessionState + 56768) = 1;
          DrvCreateLiveDumpWithWdLogs((unsigned int)DeviceInfoInternal, v27);
        }
        else
        {
          WdLogSingleEntry2(2, v25, v24);
          WdLogGlobalForLineNumber = 2456;
        }
      }
      goto LABEL_27;
    }
LABEL_43:
    DeviceInfoInternal = -1073741811;
    goto LABEL_45;
  }
  if ( v8 != 2056 )
    goto LABEL_43;
  HIDWORD(v28) = *((_DWORD *)v2 + 504);
  LODWORD(v28) = *((_DWORD *)v2 + 505);
  v2[252] = 0;
  v5 = 1;
LABEL_11:
  DeviceInfoInternal = 0;
  v31 = 0;
  v13 = DispConfigTypes::RequiresUserCritShared();
  MaybeEnterLeaveCritSharedOnly::MaybeEnterLeaveCritSharedOnly((MaybeEnterLeaveCritSharedOnly *)&Src, v13);
  if ( !(unsigned __int8)DispConfigTypes::AllowInAnySession(*(unsigned int *)v2) )
  {
    if ( *(_DWORD *)(W32GetUserGdiSessionState() + 36) )
    {
      DeviceInfoInternal = -1073741823;
      v31 = -1073741823;
      goto LABEL_17;
    }
    if ( !(unsigned int)UserIsWddmConnectedSession() )
      DeviceInfoInternal = -1073741790;
    v31 = DeviceInfoInternal;
  }
  if ( DeviceInfoInternal >= 0 )
  {
    GetterTypeSize = DispConfigTypes::GetGetterTypeSize(*(unsigned int *)v2);
    if ( !GetterTypeSize || *((_DWORD *)v2 + 1) != GetterTypeSize )
    {
      DeviceInfoInternal = -1073741811;
      v31 = -1073741811;
    }
    if ( DeviceInfoInternal >= 0 )
    {
      DeviceInfoInternal = DrvDisplayConfigGetDeviceInfoInternal((struct DISPLAYCONFIG_DEVICE_INFO_HEADER *)v2, 1);
      v31 = DeviceInfoInternal;
    }
  }
LABEL_17:
  MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly((MaybeEnterLeaveCritSharedOnly *)&Src);
  if ( DeviceInfoInternal < 0 && v5 )
    v27 = *((_DWORD *)v2 + 506);
  if ( DeviceInfoInternal != -1073741789 )
  {
    if ( DeviceInfoInternal == -2147483643 )
    {
      DeviceInfoInternal = -1073741789;
      v31 = -1073741789;
    }
    else
    {
      DeviceInfoInternal = DeviceInfoTranslateStatusDefault(*(unsigned int *)v2, (unsigned int)DeviceInfoInternal);
      v31 = DeviceInfoInternal;
    }
  }
  if ( *(_DWORD *)v2 == -15 )
  {
    v15 = Address;
    v2[3] = Address;
    if ( DeviceInfoInternal >= 0 )
    {
      if ( *((_DWORD *)v2 + 5) )
      {
        v16 = PsGetCurrentProcessWow64Process();
        ProbeForWrite(v15, *((unsigned int *)v2 + 5), v16 != 0 ? 1 : 4);
        memmove((void *)v15, v3, *((unsigned int *)v2 + 5));
      }
    }
  }
  if ( *(_DWORD *)v2 == 3 && DeviceInfoInternal >= 0 )
    *((_DWORD *)v2 + 7) = 0;
  v17 = PsGetCurrentProcessWow64Process();
  ProbeForWrite(a1, *((unsigned int *)v2 + 1), v17 != 0 ? 1 : 4);
  RtlCopyVolatileMemory(a1, v2, *((unsigned int *)v2 + 1));
  if ( DeviceInfoInternal < 0 )
    goto LABEL_46;
LABEL_27:
  if ( v3 )
    GreDeleteFastMutex(v3);
  if ( v2 )
    GreDeleteFastMutex(v2);
  return (unsigned int)DeviceInfoInternal;
}

```

## disassembly

```asm
0x1400f01b0  mov     [rsp+arg_0], rcx
0x1400f01b5  push    rbx
0x1400f01b6  push    rdi
0x1400f01b7  push    r12
0x1400f01b9  push    r13
0x1400f01bb  push    r14
0x1400f01bd  push    r15
0x1400f01bf  sub     rsp, 0A8h
0x1400f01c6  mov     r14, rcx
0x1400f01c9  xor     edi, edi
0x1400f01cb  mov     [rsp+0D8h+Buffer], rdi
0x1400f01d0  xor     r12d, r12d
0x1400f01d3  mov     [rsp+0D8h+var_90], r12
0x1400f01d8  xor     eax, eax
0x1400f01da  mov     [rsp+0D8h+Address], rax
0x1400f01e2  xor     r15d, r15d
0x1400f01e5  mov     [rsp+0D8h+var_A8], r15d
0x1400f01ea  mov     [rsp+0D8h+var_9C], eax
0x1400f01ee  mov     [rsp+0D8h+var_A0], eax
0x1400f01f2  xor     r13d, r13d
0x1400f01f5  mov     [rsp+0D8h+var_A4], r13d
0x1400f01fa  call    cs:__imp_W32GetUserGdiSessionState
0x1400f0201  nop     dword ptr [rax+rax+00h]
0x1400f0206  cmp     [rax+20h], edi
0x1400f0209  jz      loc_1400F0580
0x1400f020f  lea     rcx, [r14+4]
0x1400f0213  call    RtlReadULongFromUser
0x1400f0218  mov     ebx, eax
0x1400f021a  cmp     eax, 14h
0x1400f021d  jb      loc_1400F0324
0x1400f0223  mov     r15d, ebx
0x1400f0226  mov     r8d, 63447355h; unsigned int
0x1400f022c  mov     edx, ebx; unsigned __int64
0x1400f022e  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400f0233  mov     rdi, rax
0x1400f0236  mov     [rsp+0D8h+Buffer], rax
0x1400f023b  test    rax, rax
0x1400f023e  jnz     loc_1400F0335
0x1400f0244  mov     r12d, 44315706h
0x1400f024a  mov     [rsp+0D8h+var_A8], r12d
0x1400f024f  mov     rcx, r14
0x1400f0252  call    RtlReadULongFromUser
0x1400f0257  cmp     eax, 0FFFFFFEBh
0x1400f025a  jnz     loc_1400F02F2
0x1400f0260  cmp     ebx, 808h
0x1400f0266  jnz     loc_1400F02F2
0x1400f026c  lea     rbx, [r14+7E0h]
0x1400f0273  mov     rcx, rbx
0x1400f0276  call    RtlReadULongFromUser
0x1400f027b  mov     [rsp+0D8h+var_9C], eax
0x1400f027f  lea     rdi, [r14+7E4h]
0x1400f0286  mov     rcx, rdi
0x1400f0289  call    RtlReadULongFromUser
0x1400f028e  mov     [rsp+0D8h+var_A0], eax
0x1400f0292  mov     [rsp+0D8h+Src], r13d
0x1400f029a  lea     r8d, [r13+4]; Size
0x1400f029e  lea     rdx, [rsp+0D8h+Src]; Src
0x1400f02a6  mov     rcx, rbx; void *
0x1400f02a9  call    RtlCopyToUser
0x1400f02ae  mov     [rsp+0D8h+arg_10], r13d
0x1400f02b6  lea     r8d, [r13+4]; Size
0x1400f02ba  lea     rdx, [rsp+0D8h+arg_10]; Src
0x1400f02c2  mov     rcx, rdi; void *
0x1400f02c5  call    RtlCopyToUser
0x1400f02ca  mov     dword ptr [rsp+0D8h+Address], r12d
0x1400f02d2  lea     rcx, [r14+7E8h]; void *
0x1400f02d9  lea     r8d, [r13+4]; Size
0x1400f02dd  lea     rdx, [rsp+0D8h+Address]; Src
0x1400f02e5  call    RtlCopyToUser
0x1400f02ea  mov     [rsp+0D8h+var_A4], 1
0x1400f02f2  mov     r8, r12
0x1400f02f5  mov     rdx, r15
0x1400f02f8  mov     ecx, 2
0x1400f02fd  call    cs:__imp_WdLogSingleEntry2
0x1400f0304  nop     dword ptr [rax+rax+00h]
0x1400f0309  mov     cs:WdLogGlobalForLineNumber, 8CCh
0x1400f0313  mov     ecx, 0C0000017h; Status
0x1400f0318  call    cs:__imp_ExRaiseStatus
0x1400f0324  mov     ecx, 0C000000Dh; Status
0x1400f0329  call    cs:__imp_ExRaiseStatus
0x1400f0335  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400f033c  nop     dword ptr [rax+rax+00h]
0x1400f0341  neg     rax
0x1400f0344  sbb     r8d, r8d
0x1400f0347  and     r8d, 0FFFFFFFDh
0x1400f034b  add     r8d, 4; Alignment
0x1400f034f  mov     rdx, r15; Length
0x1400f0352  mov     rcx, r14; Address
0x1400f0355  call    cs:__imp_ProbeForRead
0x1400f035c  nop     dword ptr [rax+rax+00h]
0x1400f0361  mov     r8, r15; Size
0x1400f0364  mov     rdx, r14; Src
0x1400f0367  mov     rcx, rdi; void *
0x1400f036a  call    RtlCopyVolatileMemory
0x1400f036f  mov     [rdi+4], ebx
0x1400f0372  jmp     short loc_1400F039C
0x1400f0374  mov     ebx, 0C0000001h
0x1400f0379  mov     [rsp+0D8h+arg_10], ebx
0x1400f0380  mov     r14, [rsp+0D8h+arg_0]
0x1400f0388  mov     rdi, [rsp+0D8h+Buffer]
0x1400f038d  mov     r12, [rsp+0D8h+var_90]
0x1400f0392  mov     r13d, [rsp+0D8h+var_A4]
0x1400f0397  jmp     loc_1400F04F8
0x1400f039c  mov     ecx, [rdi]; unsigned __int64
0x1400f039e  cmp     ecx, 0FFFFFFEBh
0x1400f03a1  jz      loc_1400F0643
0x1400f03a7  cmp     ecx, 0FFFFFFF1h
0x1400f03aa  jz      loc_1400F058E
0x1400f03b0  xor     ebx, ebx
0x1400f03b2  mov     [rsp+0D8h+arg_10], ebx
0x1400f03b9  call    ?RequiresUserCritShared@DispConfigTypes@@YA_NW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::RequiresUserCritShared(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400f03be  mov     dl, al; bool
0x1400f03c0  lea     rcx, [rsp+0D8h+Src]; this
0x1400f03c8  call    ??0MaybeEnterLeaveCritSharedOnly@@QEAA@_N@Z; MaybeEnterLeaveCritSharedOnly::MaybeEnterLeaveCritSharedOnly(bool)
0x1400f03cd  mov     ecx, [rdi]
0x1400f03cf  call    ?AllowInAnySession@DispConfigTypes@@YA_NW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::AllowInAnySession(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400f03d4  test    al, al
0x1400f03d6  jz      loc_1400F052D
0x1400f03dc  test    ebx, ebx
0x1400f03de  js      short loc_1400F040F
0x1400f03e0  mov     ecx, [rdi]
0x1400f03e2  call    ?GetGetterTypeSize@DispConfigTypes@@YAKW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::GetGetterTypeSize(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400f03e7  test    eax, eax
0x1400f03e9  jz      loc_1400F068B
0x1400f03ef  cmp     [rdi+4], eax
0x1400f03f2  jnz     loc_1400F068B
0x1400f03f8  test    ebx, ebx
0x1400f03fa  js      short loc_1400F040F
0x1400f03fc  mov     dl, 1; bool
0x1400f03fe  mov     rcx, rdi; struct DISPLAYCONFIG_DEVICE_INFO_HEADER *
0x1400f0401  call    ?DrvDisplayConfigGetDeviceInfoInternal@@YAJPEAUDISPLAYCONFIG_DEVICE_INFO_HEADER@@_N@Z; DrvDisplayConfigGetDeviceInfoInternal(DISPLAYCONFIG_DEVICE_INFO_HEADER *,bool)
0x1400f0406  mov     ebx, eax
0x1400f0408  mov     [rsp+0D8h+arg_10], eax
0x1400f040f  lea     rcx, [rsp+0D8h+Src]; this
0x1400f0417  call    ??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ; MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)
0x1400f041c  test    ebx, ebx
0x1400f041e  js      loc_1400F069C
0x1400f0424  cmp     ebx, 0C0000023h
0x1400f042a  jnz     loc_1400F055D
0x1400f0430  cmp     dword ptr [rdi], 0FFFFFFF1h
0x1400f0433  jz      short loc_1400F0445
0x1400f0435  cmp     dword ptr [rdi], 3
0x1400f0438  jnz     short loc_1400F0498
0x1400f043a  test    ebx, ebx
0x1400f043c  js      short loc_1400F0498
0x1400f043e  xor     eax, eax
0x1400f0440  mov     [rdi+1Ch], eax
0x1400f0443  jmp     short loc_1400F0498
0x1400f0445  mov     r15, [rsp+0D8h+Address]
0x1400f044d  mov     [rdi+18h], r15
0x1400f0451  test    ebx, ebx
0x1400f0453  js      short loc_1400F0435
0x1400f0455  cmp     dword ptr [rdi+14h], 0
0x1400f0459  jz      short loc_1400F0435
0x1400f045b  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400f0462  nop     dword ptr [rax+rax+00h]
0x1400f0467  neg     rax
0x1400f046a  sbb     r8d, r8d
0x1400f046d  and     r8d, 0FFFFFFFDh
0x1400f0471  add     r8d, 4; Alignment
0x1400f0475  mov     edx, [rdi+14h]; Length
0x1400f0478  mov     rcx, r15; Address
0x1400f047b  call    cs:__imp_ProbeForWrite
0x1400f0482  nop     dword ptr [rax+rax+00h]
0x1400f0487  mov     r8d, [rdi+14h]; Size
0x1400f048b  mov     rdx, r12; Src
0x1400f048e  mov     rcx, r15; void *
0x1400f0491  call    memmove
0x1400f0496  jmp     short loc_1400F0435
0x1400f0498  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400f049f  nop     dword ptr [rax+rax+00h]
0x1400f04a4  neg     rax
0x1400f04a7  sbb     r8d, r8d
0x1400f04aa  and     r8d, 0FFFFFFFDh
0x1400f04ae  add     r8d, 4; Alignment
0x1400f04b2  mov     edx, [rdi+4]; Length
0x1400f04b5  mov     rcx, r14; Address
0x1400f04b8  call    cs:__imp_ProbeForWrite
0x1400f04bf  nop     dword ptr [rax+rax+00h]
0x1400f04c4  mov     r8d, [rdi+4]; Size
0x1400f04c8  mov     rdx, rdi; Src
0x1400f04cb  mov     rcx, r14; void *
0x1400f04ce  call    RtlCopyVolatileMemory
0x1400f04d3  jmp     short loc_1400F04F8
0x1400f04d5  mov     ebx, 0C0000001h
0x1400f04da  mov     [rsp+0D8h+arg_10], ebx
0x1400f04e1  mov     r14, [rsp+0D8h+arg_0]
0x1400f04e9  mov     rdi, [rsp+0D8h+Buffer]
0x1400f04ee  mov     r12, [rsp+0D8h+var_90]
0x1400f04f3  mov     r13d, [rsp+0D8h+var_A4]
0x1400f04f8  test    ebx, ebx
0x1400f04fa  js      loc_1400F05E2
0x1400f0500  test    r12, r12
0x1400f0503  jnz     loc_1400F07E4
0x1400f0509  test    rdi, rdi
0x1400f050c  jnz     short loc_1400F0523
0x1400f050e  mov     eax, ebx
0x1400f0510  add     rsp, 0A8h
0x1400f0517  pop     r15
0x1400f0519  pop     r14
0x1400f051b  pop     r13
0x1400f051d  pop     r12
0x1400f051f  pop     rdi
0x1400f0520  pop     rbx
0x1400f0521  retn
0x1400f0523  mov     rcx, rdi; Buffer
0x1400f0526  call    GreDeleteFastMutex
0x1400f052b  jmp     short loc_1400F050E
0x1400f052d  call    cs:__imp_W32GetUserGdiSessionState
0x1400f0534  nop     dword ptr [rax+rax+00h]
0x1400f0539  cmp     [rax+24h], ebx
0x1400f053c  jnz     loc_1400F067A
0x1400f0542  call    UserIsWddmConnectedSession
0x1400f0547  mov     ecx, 0C0000022h
0x1400f054c  test    eax, eax
0x1400f054e  cmovz   ebx, ecx
0x1400f0551  mov     [rsp+0D8h+arg_10], ebx
0x1400f0558  jmp     loc_1400F03DC
0x1400f055d  cmp     ebx, 80000005h
0x1400f0563  jz      loc_1400F06B4
0x1400f0569  mov     edx, ebx
0x1400f056b  mov     ecx, [rdi]
0x1400f056d  call    _DeviceInfoTranslateStatusDefault
0x1400f0572  mov     ebx, eax
0x1400f0574  mov     [rsp+0D8h+arg_10], eax
0x1400f057b  jmp     loc_1400F0430
0x1400f0580  mov     ebx, 0C0000001h
0x1400f0585  mov     [rsp+0D8h+arg_10], ebx
0x1400f058c  jmp     short loc_1400F05E7
0x1400f058e  cmp     ebx, 20h ; ' '
0x1400f0591  jnz     short loc_1400F05CF
0x1400f0593  mov     eax, [rdi+14h]
0x1400f0596  test    eax, eax
0x1400f0598  jz      loc_1400F03B0
0x1400f059e  mov     edx, eax; unsigned __int64
0x1400f05a0  mov     r8d, 63447355h; unsigned int
0x1400f05a6  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400f05ab  mov     r12, rax
0x1400f05ae  mov     [rsp+0D8h+var_90], rax
0x1400f05b3  test    rax, rax
0x1400f05b6  jz      short loc_1400F05D6
0x1400f05b8  mov     rax, [rdi+18h]
0x1400f05bc  mov     [rsp+0D8h+Address], rax
0x1400f05c4  mov     [rdi+18h], r12
0x1400f05c8  mov     ecx, [rdi]
0x1400f05ca  jmp     loc_1400F03B0
0x1400f05cf  mov     ebx, 0C000000Dh
0x1400f05d4  jmp     short loc_1400F05DB
0x1400f05d6  mov     ebx, 0C0000017h
0x1400f05db  mov     [rsp+0D8h+arg_10], ebx
0x1400f05e2  mov     r15d, [rsp+0D8h+var_A8]
0x1400f05e7  test    r13d, r13d
0x1400f05ea  jz      loc_1400F0500
0x1400f05f0  xorps   xmm0, xmm0
0x1400f05f3  movups  xmmword ptr [rsp+0D8h+var_58], xmm0
0x1400f05fb  movups  xmmword ptr [rsp+0D8h+var_58+0Ch], xmm0
0x1400f0603  lea     rcx, [rsp+0D8h+var_58]
0x1400f060b  call    DrvSampleDisplayState
0x1400f0610  mov     eax, [rsp+0D8h+var_9C]
0x1400f0614  cmp     eax, [rsp+0D8h+var_58]
0x1400f061b  jnz     loc_1400F06C5
0x1400f0621  mov     eax, [rsp+0D8h+var_A0]
0x1400f0625  cmp     eax, [rsp+0D8h+var_58+8]
0x1400f062c  jnz     loc_1400F06C5
0x1400f0632  mov     r13d, 1
0x1400f0638  movsxd  r14, r15d
0x1400f063b  movsxd  r15, ebx
0x1400f063e  jmp     loc_1400F0764
0x1400f0643  cmp     ebx, 808h
0x1400f0649  jnz     short loc_1400F05CF
0x1400f064b  mov     eax, [rdi+7E0h]
0x1400f0651  mov     [rsp+0D8h+var_9C], eax
0x1400f0655  mov     eax, [rdi+7E4h]
0x1400f065b  mov     [rsp+0D8h+var_A0], eax
0x1400f065f  mov     qword ptr [rdi+7E0h], 0
0x1400f066a  mov     r13d, 1
0x1400f0670  mov     [rsp+0D8h+var_A4], r13d
0x1400f0675  jmp     loc_1400F03B0
0x1400f067a  mov     ebx, 0C0000001h
0x1400f067f  mov     [rsp+0D8h+arg_10], ebx
0x1400f0686  jmp     loc_1400F040F
0x1400f068b  mov     ebx, 0C000000Dh
0x1400f0690  mov     [rsp+0D8h+arg_10], ebx
0x1400f0697  jmp     loc_1400F03F8
0x1400f069c  test    r13d, r13d
0x1400f069f  jz      loc_1400F0424
0x1400f06a5  mov     edx, [rdi+7E8h]
0x1400f06ab  mov     [rsp+0D8h+var_A8], edx
0x1400f06af  jmp     loc_1400F0424
0x1400f06b4  mov     ebx, 0C0000023h
0x1400f06b9  mov     [rsp+0D8h+arg_10], ebx
0x1400f06c0  jmp     loc_1400F0430
0x1400f06c5  xor     r13d, r13d
0x1400f06c8  mov     [rsp+0D8h+Src], r13d
0x1400f06d0  lea     rcx, [r14+7E8h]; void *
0x1400f06d7  lea     r8d, [r13+4]; Size
0x1400f06db  lea     rdx, [rsp+0D8h+Src]; Src
0x1400f06e3  call    RtlCopyToUser
0x1400f06e8  jmp     short loc_1400F0700
0x1400f06ea  mov     rdi, [rsp+0D8h+Buffer]
  ... truncated ...
```
