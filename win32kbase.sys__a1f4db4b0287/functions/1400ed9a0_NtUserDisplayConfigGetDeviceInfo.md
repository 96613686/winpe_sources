# NtUserDisplayConfigGetDeviceInfo

- ea: `0x1400ed9a0`
- end: `0x1400edfe1`
- name: `NtUserDisplayConfigGetDeviceInfo`
- size: `1601`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x140012794`
- `0x140013374`
- `0x140029324`
- `0x14002aa70`
- `0x1400411c0`
- `0x140043810`
- `0x1400c9d00`
- `0x1400ed9a0`
- `0x1400edff0`
- `0x1400ee030`
- `0x1400ee09c`
- `0x1400ee6c0`
- `0x1400ee7d4`
- `0x1401f29c4`
- `0x140238ba0`
- `0x140239180`
- `0x1402bd054`
- `0x1402bd244`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400edb45`
- `ntoskrnl!ProbeForRead` at `0x1400edb45`
- `ntoskrnl!ExRaiseStatus` at `0x1400edb08`
- `ntoskrnl!ExRaiseStatus` at `0x1400edb19`
- `ntoskrnl!ExRaiseStatus` at `0x1400edb08`
- `ntoskrnl!ExRaiseStatus` at `0x1400edb19`
- `ntoskrnl!ProbeForWrite` at `0x1400edc6b`
- `ntoskrnl!ProbeForWrite` at `0x1400edca8`
- `ntoskrnl!ProbeForWrite` at `0x1400edc6b`
- `ntoskrnl!ProbeForWrite` at `0x1400edca8`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400edb25`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400edc4b`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400edc88`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400edb25`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400edc4b`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400edc88`
- `watchdog!WdLogSingleEntry5` at `0x1400edf1a`
- `watchdog!WdLogSingleEntry5` at `0x1400edf1a`
- `watchdog!WdLogSingleEntry2` at `0x1400edaed`
- `watchdog!WdLogSingleEntry2` at `0x1400edf3e`
- `watchdog!WdLogSingleEntry2` at `0x1400edf93`
- `watchdog!WdLogSingleEntry2` at `0x1400edfb9`
- `watchdog!WdLogSingleEntry2` at `0x1400edaed`
- `watchdog!WdLogSingleEntry2` at `0x1400edf3e`
- `watchdog!WdLogSingleEntry2` at `0x1400edf93`
- `watchdog!WdLogSingleEntry2` at `0x1400edfb9`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400ed9ea`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400edd1d`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400ed9ea`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400edd1d`
- `WIN32K!W32GetUserSessionState` at `0x1400edf54`
- `WIN32K!W32GetUserSessionState` at `0x1400edf54`

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
  __int64 v20; // rcx
  int v21; // r13d
  __int64 v22; // r14
  __int64 v23; // r15
  __int64 UserSessionState; // rax
  unsigned int v25; // [rsp+30h] [rbp-A8h]
  __int64 v26; // [rsp+38h] [rbp-A0h]
  _DWORD v27[22]; // [rsp+80h] [rbp-58h] BYREF
  int Src; // [rsp+E8h] [rbp+10h] BYREF
  int v29; // [rsp+F0h] [rbp+18h] BYREF
  volatile void *Address; // [rsp+F8h] [rbp+20h] BYREF

  v2 = 0;
  v3 = 0;
  Address = 0;
  v4 = 0;
  v25 = 0;
  v26 = 0;
  v5 = 0;
  if ( !*(_DWORD *)(W32GetUserGdiSessionState() + 32) )
  {
    DeviceInfoInternal = -1073741823;
    v29 = -1073741823;
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
      v29 = 0;
      RtlCopyToUser(a1 + 2020, &v29, 4u);
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
      v29 = DeviceInfoInternal;
LABEL_46:
      v4 = v25;
LABEL_47:
      if ( v5 )
      {
        memset(v27, 0, 28);
        DrvSampleDisplayState(v27);
        if ( v26 == __PAIR64__(v27[0], v27[2]) )
        {
          v21 = 1;
          v22 = (int)v4;
          v23 = DeviceInfoInternal;
        }
        else
        {
          v21 = 0;
          Src = 0;
          RtlCopyToUser(a1 + 2024, &Src, 4u);
          v22 = (int)v4;
          WdLogSingleEntry5(2, HIDWORD(v26), (unsigned int)v26, v27[0], v27[2], (int)v4);
          WdLogGlobalForLineNumber = 2429;
          v23 = DeviceInfoInternal;
          WdLogSingleEntry2(2, DeviceInfoInternal, v22);
          WdLogGlobalForLineNumber = 2434;
        }
        UserSessionState = W32GetUserSessionState(v20);
        if ( *(_DWORD *)(UserSessionState + 56768) )
        {
          WdLogSingleEntry2(2, v23, v22);
          WdLogGlobalForLineNumber = 2464;
        }
        else if ( v21 )
        {
          *(_DWORD *)(UserSessionState + 56768) = 1;
          DrvCreateLiveDumpWithWdLogs((unsigned int)DeviceInfoInternal, v25);
        }
        else
        {
          WdLogSingleEntry2(2, v23, v22);
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
  HIDWORD(v26) = *((_DWORD *)v2 + 504);
  LODWORD(v26) = *((_DWORD *)v2 + 505);
  v2[252] = 0;
  v5 = 1;
LABEL_11:
  DeviceInfoInternal = 0;
  v29 = 0;
  v13 = DispConfigTypes::RequiresUserCritShared();
  MaybeEnterLeaveCritSharedOnly::MaybeEnterLeaveCritSharedOnly((MaybeEnterLeaveCritSharedOnly *)&Src, v13);
  if ( !(unsigned __int8)DispConfigTypes::AllowInAnySession(*(unsigned int *)v2) )
  {
    if ( *(_DWORD *)(W32GetUserGdiSessionState() + 36) )
    {
      DeviceInfoInternal = -1073741823;
      v29 = -1073741823;
      goto LABEL_17;
    }
    if ( !(unsigned int)UserIsWddmConnectedSession() )
      DeviceInfoInternal = -1073741790;
    v29 = DeviceInfoInternal;
  }
  if ( DeviceInfoInternal >= 0 )
  {
    GetterTypeSize = DispConfigTypes::GetGetterTypeSize(*(unsigned int *)v2);
    if ( !GetterTypeSize || *((_DWORD *)v2 + 1) != GetterTypeSize )
    {
      DeviceInfoInternal = -1073741811;
      v29 = -1073741811;
    }
    if ( DeviceInfoInternal >= 0 )
    {
      DeviceInfoInternal = DrvDisplayConfigGetDeviceInfoInternal((struct DISPLAYCONFIG_DEVICE_INFO_HEADER *)v2, 1);
      v29 = DeviceInfoInternal;
    }
  }
LABEL_17:
  MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly((MaybeEnterLeaveCritSharedOnly *)&Src);
  if ( DeviceInfoInternal < 0 && v5 )
    v25 = *((_DWORD *)v2 + 506);
  if ( DeviceInfoInternal != -1073741789 )
  {
    if ( DeviceInfoInternal == -2147483643 )
    {
      DeviceInfoInternal = -1073741789;
      v29 = -1073741789;
    }
    else
    {
      DeviceInfoInternal = DeviceInfoTranslateStatusDefault(*(unsigned int *)v2, (unsigned int)DeviceInfoInternal);
      v29 = DeviceInfoInternal;
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
0x1400ed9a0  mov     [rsp+arg_0], rcx
0x1400ed9a5  push    rbx
0x1400ed9a6  push    rdi
0x1400ed9a7  push    r12
0x1400ed9a9  push    r13
0x1400ed9ab  push    r14
0x1400ed9ad  push    r15
0x1400ed9af  sub     rsp, 0A8h
0x1400ed9b6  mov     r14, rcx
0x1400ed9b9  xor     edi, edi
0x1400ed9bb  mov     [rsp+0D8h+Buffer], rdi
0x1400ed9c0  xor     r12d, r12d
0x1400ed9c3  mov     [rsp+0D8h+var_90], r12
0x1400ed9c8  xor     eax, eax
0x1400ed9ca  mov     [rsp+0D8h+Address], rax
0x1400ed9d2  xor     r15d, r15d
0x1400ed9d5  mov     [rsp+0D8h+var_A8], r15d
0x1400ed9da  mov     [rsp+0D8h+var_9C], eax
0x1400ed9de  mov     [rsp+0D8h+var_A0], eax
0x1400ed9e2  xor     r13d, r13d
0x1400ed9e5  mov     [rsp+0D8h+var_A4], r13d
0x1400ed9ea  call    cs:__imp_W32GetUserGdiSessionState
0x1400ed9f1  nop     dword ptr [rax+rax+00h]
0x1400ed9f6  cmp     [rax+20h], edi
0x1400ed9f9  jz      loc_1400EDD70
0x1400ed9ff  lea     rcx, [r14+4]
0x1400eda03  call    RtlReadULongFromUser
0x1400eda08  mov     ebx, eax
0x1400eda0a  cmp     eax, 14h
0x1400eda0d  jb      loc_1400EDB14
0x1400eda13  mov     r15d, ebx
0x1400eda16  mov     r8d, 63447355h; unsigned int
0x1400eda1c  mov     edx, ebx; unsigned __int64
0x1400eda1e  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400eda23  mov     rdi, rax
0x1400eda26  mov     [rsp+0D8h+Buffer], rax
0x1400eda2b  test    rax, rax
0x1400eda2e  jnz     loc_1400EDB25
0x1400eda34  mov     r12d, 44315706h
0x1400eda3a  mov     [rsp+0D8h+var_A8], r12d
0x1400eda3f  mov     rcx, r14
0x1400eda42  call    RtlReadULongFromUser
0x1400eda47  cmp     eax, 0FFFFFFEBh
0x1400eda4a  jnz     loc_1400EDAE2
0x1400eda50  cmp     ebx, 808h
0x1400eda56  jnz     loc_1400EDAE2
0x1400eda5c  lea     rbx, [r14+7E0h]
0x1400eda63  mov     rcx, rbx
0x1400eda66  call    RtlReadULongFromUser
0x1400eda6b  mov     [rsp+0D8h+var_9C], eax
0x1400eda6f  lea     rdi, [r14+7E4h]
0x1400eda76  mov     rcx, rdi
0x1400eda79  call    RtlReadULongFromUser
0x1400eda7e  mov     [rsp+0D8h+var_A0], eax
0x1400eda82  mov     [rsp+0D8h+Src], r13d
0x1400eda8a  lea     r8d, [r13+4]; Size
0x1400eda8e  lea     rdx, [rsp+0D8h+Src]; Src
0x1400eda96  mov     rcx, rbx; void *
0x1400eda99  call    RtlCopyToUser
0x1400eda9e  mov     [rsp+0D8h+arg_10], r13d
0x1400edaa6  lea     r8d, [r13+4]; Size
0x1400edaaa  lea     rdx, [rsp+0D8h+arg_10]; Src
0x1400edab2  mov     rcx, rdi; void *
0x1400edab5  call    RtlCopyToUser
0x1400edaba  mov     dword ptr [rsp+0D8h+Address], r12d
0x1400edac2  lea     rcx, [r14+7E8h]; void *
0x1400edac9  lea     r8d, [r13+4]; Size
0x1400edacd  lea     rdx, [rsp+0D8h+Address]; Src
0x1400edad5  call    RtlCopyToUser
0x1400edada  mov     [rsp+0D8h+var_A4], 1
0x1400edae2  mov     r8, r12
0x1400edae5  mov     rdx, r15
0x1400edae8  mov     ecx, 2
0x1400edaed  call    cs:__imp_WdLogSingleEntry2
0x1400edaf4  nop     dword ptr [rax+rax+00h]
0x1400edaf9  mov     cs:WdLogGlobalForLineNumber, 8CCh
0x1400edb03  mov     ecx, 0C0000017h; Status
0x1400edb08  call    cs:__imp_ExRaiseStatus
0x1400edb14  mov     ecx, 0C000000Dh; Status
0x1400edb19  call    cs:__imp_ExRaiseStatus
0x1400edb25  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400edb2c  nop     dword ptr [rax+rax+00h]
0x1400edb31  neg     rax
0x1400edb34  sbb     r8d, r8d
0x1400edb37  and     r8d, 0FFFFFFFDh
0x1400edb3b  add     r8d, 4; Alignment
0x1400edb3f  mov     rdx, r15; Length
0x1400edb42  mov     rcx, r14; Address
0x1400edb45  call    cs:__imp_ProbeForRead
0x1400edb4c  nop     dword ptr [rax+rax+00h]
0x1400edb51  mov     r8, r15; Size
0x1400edb54  mov     rdx, r14; Src
0x1400edb57  mov     rcx, rdi; void *
0x1400edb5a  call    RtlCopyVolatileMemory
0x1400edb5f  mov     [rdi+4], ebx
0x1400edb62  jmp     short loc_1400EDB8C
0x1400edb64  mov     ebx, 0C0000001h
0x1400edb69  mov     [rsp+0D8h+arg_10], ebx
0x1400edb70  mov     r14, [rsp+0D8h+arg_0]
0x1400edb78  mov     rdi, [rsp+0D8h+Buffer]
0x1400edb7d  mov     r12, [rsp+0D8h+var_90]
0x1400edb82  mov     r13d, [rsp+0D8h+var_A4]
0x1400edb87  jmp     loc_1400EDCE8
0x1400edb8c  mov     ecx, [rdi]; unsigned __int64
0x1400edb8e  cmp     ecx, 0FFFFFFEBh
0x1400edb91  jz      loc_1400EDE33
0x1400edb97  cmp     ecx, 0FFFFFFF1h
0x1400edb9a  jz      loc_1400EDD7E
0x1400edba0  xor     ebx, ebx
0x1400edba2  mov     [rsp+0D8h+arg_10], ebx
0x1400edba9  call    ?RequiresUserCritShared@DispConfigTypes@@YA_NW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::RequiresUserCritShared(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400edbae  mov     dl, al; bool
0x1400edbb0  lea     rcx, [rsp+0D8h+Src]; this
0x1400edbb8  call    ??0MaybeEnterLeaveCritSharedOnly@@QEAA@_N@Z; MaybeEnterLeaveCritSharedOnly::MaybeEnterLeaveCritSharedOnly(bool)
0x1400edbbd  mov     ecx, [rdi]
0x1400edbbf  call    ?AllowInAnySession@DispConfigTypes@@YA_NW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::AllowInAnySession(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400edbc4  test    al, al
0x1400edbc6  jz      loc_1400EDD1D
0x1400edbcc  test    ebx, ebx
0x1400edbce  js      short loc_1400EDBFF
0x1400edbd0  mov     ecx, [rdi]
0x1400edbd2  call    ?GetGetterTypeSize@DispConfigTypes@@YAKW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::GetGetterTypeSize(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400edbd7  test    eax, eax
0x1400edbd9  jz      loc_1400EDE7B
0x1400edbdf  cmp     [rdi+4], eax
0x1400edbe2  jnz     loc_1400EDE7B
0x1400edbe8  test    ebx, ebx
0x1400edbea  js      short loc_1400EDBFF
0x1400edbec  mov     dl, 1; bool
0x1400edbee  mov     rcx, rdi; struct DISPLAYCONFIG_DEVICE_INFO_HEADER *
0x1400edbf1  call    ?DrvDisplayConfigGetDeviceInfoInternal@@YAJPEAUDISPLAYCONFIG_DEVICE_INFO_HEADER@@_N@Z; DrvDisplayConfigGetDeviceInfoInternal(DISPLAYCONFIG_DEVICE_INFO_HEADER *,bool)
0x1400edbf6  mov     ebx, eax
0x1400edbf8  mov     [rsp+0D8h+arg_10], eax
0x1400edbff  lea     rcx, [rsp+0D8h+Src]; this
0x1400edc07  call    ??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ; MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)
0x1400edc0c  test    ebx, ebx
0x1400edc0e  js      loc_1400EDE8C
0x1400edc14  cmp     ebx, 0C0000023h
0x1400edc1a  jnz     loc_1400EDD4D
0x1400edc20  cmp     dword ptr [rdi], 0FFFFFFF1h
0x1400edc23  jz      short loc_1400EDC35
0x1400edc25  cmp     dword ptr [rdi], 3
0x1400edc28  jnz     short loc_1400EDC88
0x1400edc2a  test    ebx, ebx
0x1400edc2c  js      short loc_1400EDC88
0x1400edc2e  xor     eax, eax
0x1400edc30  mov     [rdi+1Ch], eax
0x1400edc33  jmp     short loc_1400EDC88
0x1400edc35  mov     r15, [rsp+0D8h+Address]
0x1400edc3d  mov     [rdi+18h], r15
0x1400edc41  test    ebx, ebx
0x1400edc43  js      short loc_1400EDC25
0x1400edc45  cmp     dword ptr [rdi+14h], 0
0x1400edc49  jz      short loc_1400EDC25
0x1400edc4b  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400edc52  nop     dword ptr [rax+rax+00h]
0x1400edc57  neg     rax
0x1400edc5a  sbb     r8d, r8d
0x1400edc5d  and     r8d, 0FFFFFFFDh
0x1400edc61  add     r8d, 4; Alignment
0x1400edc65  mov     edx, [rdi+14h]; Length
0x1400edc68  mov     rcx, r15; Address
0x1400edc6b  call    cs:__imp_ProbeForWrite
0x1400edc72  nop     dword ptr [rax+rax+00h]
0x1400edc77  mov     r8d, [rdi+14h]; Size
0x1400edc7b  mov     rdx, r12; Src
0x1400edc7e  mov     rcx, r15; void *
0x1400edc81  call    memmove
0x1400edc86  jmp     short loc_1400EDC25
0x1400edc88  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400edc8f  nop     dword ptr [rax+rax+00h]
0x1400edc94  neg     rax
0x1400edc97  sbb     r8d, r8d
0x1400edc9a  and     r8d, 0FFFFFFFDh
0x1400edc9e  add     r8d, 4; Alignment
0x1400edca2  mov     edx, [rdi+4]; Length
0x1400edca5  mov     rcx, r14; Address
0x1400edca8  call    cs:__imp_ProbeForWrite
0x1400edcaf  nop     dword ptr [rax+rax+00h]
0x1400edcb4  mov     r8d, [rdi+4]; Size
0x1400edcb8  mov     rdx, rdi; Src
0x1400edcbb  mov     rcx, r14; void *
0x1400edcbe  call    RtlCopyVolatileMemory
0x1400edcc3  jmp     short loc_1400EDCE8
0x1400edcc5  mov     ebx, 0C0000001h
0x1400edcca  mov     [rsp+0D8h+arg_10], ebx
0x1400edcd1  mov     r14, [rsp+0D8h+arg_0]
0x1400edcd9  mov     rdi, [rsp+0D8h+Buffer]
0x1400edcde  mov     r12, [rsp+0D8h+var_90]
0x1400edce3  mov     r13d, [rsp+0D8h+var_A4]
0x1400edce8  test    ebx, ebx
0x1400edcea  js      loc_1400EDDD2
0x1400edcf0  test    r12, r12
0x1400edcf3  jnz     loc_1400EDFD4
0x1400edcf9  test    rdi, rdi
0x1400edcfc  jnz     short loc_1400EDD13
0x1400edcfe  mov     eax, ebx
0x1400edd00  add     rsp, 0A8h
0x1400edd07  pop     r15
0x1400edd09  pop     r14
0x1400edd0b  pop     r13
0x1400edd0d  pop     r12
0x1400edd0f  pop     rdi
0x1400edd10  pop     rbx
0x1400edd11  retn
0x1400edd13  mov     rcx, rdi; Buffer
0x1400edd16  call    GreDeleteFastMutex
0x1400edd1b  jmp     short loc_1400EDCFE
0x1400edd1d  call    cs:__imp_W32GetUserGdiSessionState
0x1400edd24  nop     dword ptr [rax+rax+00h]
0x1400edd29  cmp     [rax+24h], ebx
0x1400edd2c  jnz     loc_1400EDE6A
0x1400edd32  call    UserIsWddmConnectedSession
0x1400edd37  mov     ecx, 0C0000022h
0x1400edd3c  test    eax, eax
0x1400edd3e  cmovz   ebx, ecx
0x1400edd41  mov     [rsp+0D8h+arg_10], ebx
0x1400edd48  jmp     loc_1400EDBCC
0x1400edd4d  cmp     ebx, 80000005h
0x1400edd53  jz      loc_1400EDEA4
0x1400edd59  mov     edx, ebx
0x1400edd5b  mov     ecx, [rdi]
0x1400edd5d  call    _DeviceInfoTranslateStatusDefault
0x1400edd62  mov     ebx, eax
0x1400edd64  mov     [rsp+0D8h+arg_10], eax
0x1400edd6b  jmp     loc_1400EDC20
0x1400edd70  mov     ebx, 0C0000001h
0x1400edd75  mov     [rsp+0D8h+arg_10], ebx
0x1400edd7c  jmp     short loc_1400EDDD7
0x1400edd7e  cmp     ebx, 20h ; ' '
0x1400edd81  jnz     short loc_1400EDDBF
0x1400edd83  mov     eax, [rdi+14h]
0x1400edd86  test    eax, eax
0x1400edd88  jz      loc_1400EDBA0
0x1400edd8e  mov     edx, eax; unsigned __int64
0x1400edd90  mov     r8d, 63447355h; unsigned int
0x1400edd96  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400edd9b  mov     r12, rax
0x1400edd9e  mov     [rsp+0D8h+var_90], rax
0x1400edda3  test    rax, rax
0x1400edda6  jz      short loc_1400EDDC6
0x1400edda8  mov     rax, [rdi+18h]
0x1400eddac  mov     [rsp+0D8h+Address], rax
0x1400eddb4  mov     [rdi+18h], r12
0x1400eddb8  mov     ecx, [rdi]
0x1400eddba  jmp     loc_1400EDBA0
0x1400eddbf  mov     ebx, 0C000000Dh
0x1400eddc4  jmp     short loc_1400EDDCB
0x1400eddc6  mov     ebx, 0C0000017h
0x1400eddcb  mov     [rsp+0D8h+arg_10], ebx
0x1400eddd2  mov     r15d, [rsp+0D8h+var_A8]
0x1400eddd7  test    r13d, r13d
0x1400eddda  jz      loc_1400EDCF0
0x1400edde0  xorps   xmm0, xmm0
0x1400edde3  movups  xmmword ptr [rsp+0D8h+var_58], xmm0
0x1400eddeb  movups  xmmword ptr [rsp+0D8h+var_58+0Ch], xmm0
0x1400eddf3  lea     rcx, [rsp+0D8h+var_58]
0x1400eddfb  call    DrvSampleDisplayState
0x1400ede00  mov     eax, [rsp+0D8h+var_9C]
0x1400ede04  cmp     eax, [rsp+0D8h+var_58]
0x1400ede0b  jnz     loc_1400EDEB5
0x1400ede11  mov     eax, [rsp+0D8h+var_A0]
0x1400ede15  cmp     eax, [rsp+0D8h+var_58+8]
0x1400ede1c  jnz     loc_1400EDEB5
0x1400ede22  mov     r13d, 1
0x1400ede28  movsxd  r14, r15d
0x1400ede2b  movsxd  r15, ebx
0x1400ede2e  jmp     loc_1400EDF54
0x1400ede33  cmp     ebx, 808h
0x1400ede39  jnz     short loc_1400EDDBF
0x1400ede3b  mov     eax, [rdi+7E0h]
0x1400ede41  mov     [rsp+0D8h+var_9C], eax
0x1400ede45  mov     eax, [rdi+7E4h]
0x1400ede4b  mov     [rsp+0D8h+var_A0], eax
0x1400ede4f  mov     qword ptr [rdi+7E0h], 0
0x1400ede5a  mov     r13d, 1
0x1400ede60  mov     [rsp+0D8h+var_A4], r13d
0x1400ede65  jmp     loc_1400EDBA0
0x1400ede6a  mov     ebx, 0C0000001h
0x1400ede6f  mov     [rsp+0D8h+arg_10], ebx
0x1400ede76  jmp     loc_1400EDBFF
0x1400ede7b  mov     ebx, 0C000000Dh
0x1400ede80  mov     [rsp+0D8h+arg_10], ebx
0x1400ede87  jmp     loc_1400EDBE8
0x1400ede8c  test    r13d, r13d
0x1400ede8f  jz      loc_1400EDC14
0x1400ede95  mov     edx, [rdi+7E8h]
0x1400ede9b  mov     [rsp+0D8h+var_A8], edx
0x1400ede9f  jmp     loc_1400EDC14
0x1400edea4  mov     ebx, 0C0000023h
0x1400edea9  mov     [rsp+0D8h+arg_10], ebx
0x1400edeb0  jmp     loc_1400EDC20
0x1400edeb5  xor     r13d, r13d
0x1400edeb8  mov     [rsp+0D8h+Src], r13d
0x1400edec0  lea     rcx, [r14+7E8h]; void *
0x1400edec7  lea     r8d, [r13+4]; Size
0x1400edecb  lea     rdx, [rsp+0D8h+Src]; Src
0x1400eded3  call    RtlCopyToUser
0x1400eded8  jmp     short loc_1400EDEF0
0x1400ededa  mov     rdi, [rsp+0D8h+Buffer]
  ... truncated ...
```
