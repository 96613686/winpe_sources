# NtUserDisplayConfigGetDeviceInfo

- ea: `0x1400eb020`
- end: `0x1400eb661`
- name: `NtUserDisplayConfigGetDeviceInfo`
- size: `1601`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x14001b904`
- `0x14001c4e4`
- `0x1400325a4`
- `0x140033cf0`
- `0x14004a0d0`
- `0x14004c720`
- `0x1400b05f0`
- `0x1400eb020`
- `0x1400eb670`
- `0x1400eb6b0`
- `0x1400eb71c`
- `0x1400ebd40`
- `0x1400ebe54`
- `0x1401f2204`
- `0x1402381f0`
- `0x140238800`
- `0x1402bb054`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400eb1c5`
- `ntoskrnl!ProbeForRead` at `0x1400eb1c5`
- `ntoskrnl!ExRaiseStatus` at `0x1400eb188`
- `ntoskrnl!ExRaiseStatus` at `0x1400eb199`
- `ntoskrnl!ExRaiseStatus` at `0x1400eb188`
- `ntoskrnl!ExRaiseStatus` at `0x1400eb199`
- `ntoskrnl!ProbeForWrite` at `0x1400eb2eb`
- `ntoskrnl!ProbeForWrite` at `0x1400eb328`
- `ntoskrnl!ProbeForWrite` at `0x1400eb2eb`
- `ntoskrnl!ProbeForWrite` at `0x1400eb328`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400eb1a5`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400eb2cb`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400eb308`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400eb1a5`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400eb2cb`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400eb308`
- `watchdog!WdLogSingleEntry5` at `0x1400eb59a`
- `watchdog!WdLogSingleEntry5` at `0x1400eb59a`
- `watchdog!WdLogSingleEntry2` at `0x1400eb16d`
- `watchdog!WdLogSingleEntry2` at `0x1400eb5be`
- `watchdog!WdLogSingleEntry2` at `0x1400eb613`
- `watchdog!WdLogSingleEntry2` at `0x1400eb639`
- `watchdog!WdLogSingleEntry2` at `0x1400eb16d`
- `watchdog!WdLogSingleEntry2` at `0x1400eb5be`
- `watchdog!WdLogSingleEntry2` at `0x1400eb613`
- `watchdog!WdLogSingleEntry2` at `0x1400eb639`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400eb06a`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400eb39d`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400eb06a`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400eb39d`
- `WIN32K!W32GetUserSessionState` at `0x1400eb5d4`
- `WIN32K!W32GetUserSessionState` at `0x1400eb5d4`

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
0x1400eb020  mov     [rsp+arg_0], rcx
0x1400eb025  push    rbx
0x1400eb026  push    rdi
0x1400eb027  push    r12
0x1400eb029  push    r13
0x1400eb02b  push    r14
0x1400eb02d  push    r15
0x1400eb02f  sub     rsp, 0A8h
0x1400eb036  mov     r14, rcx
0x1400eb039  xor     edi, edi
0x1400eb03b  mov     [rsp+0D8h+Buffer], rdi
0x1400eb040  xor     r12d, r12d
0x1400eb043  mov     [rsp+0D8h+var_90], r12
0x1400eb048  xor     eax, eax
0x1400eb04a  mov     [rsp+0D8h+Address], rax
0x1400eb052  xor     r15d, r15d
0x1400eb055  mov     [rsp+0D8h+var_A8], r15d
0x1400eb05a  mov     [rsp+0D8h+var_9C], eax
0x1400eb05e  mov     [rsp+0D8h+var_A0], eax
0x1400eb062  xor     r13d, r13d
0x1400eb065  mov     [rsp+0D8h+var_A4], r13d
0x1400eb06a  call    cs:__imp_W32GetUserGdiSessionState
0x1400eb071  nop     dword ptr [rax+rax+00h]
0x1400eb076  cmp     [rax+20h], edi
0x1400eb079  jz      loc_1400EB3F0
0x1400eb07f  lea     rcx, [r14+4]
0x1400eb083  call    RtlReadULongFromUser
0x1400eb088  mov     ebx, eax
0x1400eb08a  cmp     eax, 14h
0x1400eb08d  jb      loc_1400EB194
0x1400eb093  mov     r15d, ebx
0x1400eb096  mov     r8d, 63447355h; unsigned int
0x1400eb09c  mov     edx, ebx; unsigned __int64
0x1400eb09e  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400eb0a3  mov     rdi, rax
0x1400eb0a6  mov     [rsp+0D8h+Buffer], rax
0x1400eb0ab  test    rax, rax
0x1400eb0ae  jnz     loc_1400EB1A5
0x1400eb0b4  mov     r12d, 44315706h
0x1400eb0ba  mov     [rsp+0D8h+var_A8], r12d
0x1400eb0bf  mov     rcx, r14
0x1400eb0c2  call    RtlReadULongFromUser
0x1400eb0c7  cmp     eax, 0FFFFFFEBh
0x1400eb0ca  jnz     loc_1400EB162
0x1400eb0d0  cmp     ebx, 808h
0x1400eb0d6  jnz     loc_1400EB162
0x1400eb0dc  lea     rbx, [r14+7E0h]
0x1400eb0e3  mov     rcx, rbx
0x1400eb0e6  call    RtlReadULongFromUser
0x1400eb0eb  mov     [rsp+0D8h+var_9C], eax
0x1400eb0ef  lea     rdi, [r14+7E4h]
0x1400eb0f6  mov     rcx, rdi
0x1400eb0f9  call    RtlReadULongFromUser
0x1400eb0fe  mov     [rsp+0D8h+var_A0], eax
0x1400eb102  mov     [rsp+0D8h+Src], r13d
0x1400eb10a  lea     r8d, [r13+4]; Size
0x1400eb10e  lea     rdx, [rsp+0D8h+Src]; Src
0x1400eb116  mov     rcx, rbx; void *
0x1400eb119  call    RtlCopyToUser
0x1400eb11e  mov     [rsp+0D8h+arg_10], r13d
0x1400eb126  lea     r8d, [r13+4]; Size
0x1400eb12a  lea     rdx, [rsp+0D8h+arg_10]; Src
0x1400eb132  mov     rcx, rdi; void *
0x1400eb135  call    RtlCopyToUser
0x1400eb13a  mov     dword ptr [rsp+0D8h+Address], r12d
0x1400eb142  lea     rcx, [r14+7E8h]; void *
0x1400eb149  lea     r8d, [r13+4]; Size
0x1400eb14d  lea     rdx, [rsp+0D8h+Address]; Src
0x1400eb155  call    RtlCopyToUser
0x1400eb15a  mov     [rsp+0D8h+var_A4], 1
0x1400eb162  mov     r8, r12
0x1400eb165  mov     rdx, r15
0x1400eb168  mov     ecx, 2
0x1400eb16d  call    cs:__imp_WdLogSingleEntry2
0x1400eb174  nop     dword ptr [rax+rax+00h]
0x1400eb179  mov     cs:WdLogGlobalForLineNumber, 8CCh
0x1400eb183  mov     ecx, 0C0000017h; Status
0x1400eb188  call    cs:__imp_ExRaiseStatus
0x1400eb194  mov     ecx, 0C000000Dh; Status
0x1400eb199  call    cs:__imp_ExRaiseStatus
0x1400eb1a5  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400eb1ac  nop     dword ptr [rax+rax+00h]
0x1400eb1b1  neg     rax
0x1400eb1b4  sbb     r8d, r8d
0x1400eb1b7  and     r8d, 0FFFFFFFDh
0x1400eb1bb  add     r8d, 4; Alignment
0x1400eb1bf  mov     rdx, r15; Length
0x1400eb1c2  mov     rcx, r14; Address
0x1400eb1c5  call    cs:__imp_ProbeForRead
0x1400eb1cc  nop     dword ptr [rax+rax+00h]
0x1400eb1d1  mov     r8, r15; Size
0x1400eb1d4  mov     rdx, r14; Src
0x1400eb1d7  mov     rcx, rdi; void *
0x1400eb1da  call    RtlCopyVolatileMemory
0x1400eb1df  mov     [rdi+4], ebx
0x1400eb1e2  jmp     short loc_1400EB20C
0x1400eb1e4  mov     ebx, 0C0000001h
0x1400eb1e9  mov     [rsp+0D8h+arg_10], ebx
0x1400eb1f0  mov     r14, [rsp+0D8h+arg_0]
0x1400eb1f8  mov     rdi, [rsp+0D8h+Buffer]
0x1400eb1fd  mov     r12, [rsp+0D8h+var_90]
0x1400eb202  mov     r13d, [rsp+0D8h+var_A4]
0x1400eb207  jmp     loc_1400EB368
0x1400eb20c  mov     ecx, [rdi]; unsigned __int64
0x1400eb20e  cmp     ecx, 0FFFFFFEBh
0x1400eb211  jz      loc_1400EB4B3
0x1400eb217  cmp     ecx, 0FFFFFFF1h
0x1400eb21a  jz      loc_1400EB3FE
0x1400eb220  xor     ebx, ebx
0x1400eb222  mov     [rsp+0D8h+arg_10], ebx
0x1400eb229  call    ?RequiresUserCritShared@DispConfigTypes@@YA_NW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::RequiresUserCritShared(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400eb22e  mov     dl, al; bool
0x1400eb230  lea     rcx, [rsp+0D8h+Src]; this
0x1400eb238  call    ??0MaybeEnterLeaveCritSharedOnly@@QEAA@_N@Z; MaybeEnterLeaveCritSharedOnly::MaybeEnterLeaveCritSharedOnly(bool)
0x1400eb23d  mov     ecx, [rdi]
0x1400eb23f  call    ?AllowInAnySession@DispConfigTypes@@YA_NW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::AllowInAnySession(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400eb244  test    al, al
0x1400eb246  jz      loc_1400EB39D
0x1400eb24c  test    ebx, ebx
0x1400eb24e  js      short loc_1400EB27F
0x1400eb250  mov     ecx, [rdi]
0x1400eb252  call    ?GetGetterTypeSize@DispConfigTypes@@YAKW4DISPLAYCONFIG_DEVICE_INFO_TYPE@@@Z; DispConfigTypes::GetGetterTypeSize(DISPLAYCONFIG_DEVICE_INFO_TYPE)
0x1400eb257  test    eax, eax
0x1400eb259  jz      loc_1400EB4FB
0x1400eb25f  cmp     [rdi+4], eax
0x1400eb262  jnz     loc_1400EB4FB
0x1400eb268  test    ebx, ebx
0x1400eb26a  js      short loc_1400EB27F
0x1400eb26c  mov     dl, 1; bool
0x1400eb26e  mov     rcx, rdi; struct DISPLAYCONFIG_DEVICE_INFO_HEADER *
0x1400eb271  call    ?DrvDisplayConfigGetDeviceInfoInternal@@YAJPEAUDISPLAYCONFIG_DEVICE_INFO_HEADER@@_N@Z; DrvDisplayConfigGetDeviceInfoInternal(DISPLAYCONFIG_DEVICE_INFO_HEADER *,bool)
0x1400eb276  mov     ebx, eax
0x1400eb278  mov     [rsp+0D8h+arg_10], eax
0x1400eb27f  lea     rcx, [rsp+0D8h+Src]; this
0x1400eb287  call    ??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ; MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)
0x1400eb28c  test    ebx, ebx
0x1400eb28e  js      loc_1400EB50C
0x1400eb294  cmp     ebx, 0C0000023h
0x1400eb29a  jnz     loc_1400EB3CD
0x1400eb2a0  cmp     dword ptr [rdi], 0FFFFFFF1h
0x1400eb2a3  jz      short loc_1400EB2B5
0x1400eb2a5  cmp     dword ptr [rdi], 3
0x1400eb2a8  jnz     short loc_1400EB308
0x1400eb2aa  test    ebx, ebx
0x1400eb2ac  js      short loc_1400EB308
0x1400eb2ae  xor     eax, eax
0x1400eb2b0  mov     [rdi+1Ch], eax
0x1400eb2b3  jmp     short loc_1400EB308
0x1400eb2b5  mov     r15, [rsp+0D8h+Address]
0x1400eb2bd  mov     [rdi+18h], r15
0x1400eb2c1  test    ebx, ebx
0x1400eb2c3  js      short loc_1400EB2A5
0x1400eb2c5  cmp     dword ptr [rdi+14h], 0
0x1400eb2c9  jz      short loc_1400EB2A5
0x1400eb2cb  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400eb2d2  nop     dword ptr [rax+rax+00h]
0x1400eb2d7  neg     rax
0x1400eb2da  sbb     r8d, r8d
0x1400eb2dd  and     r8d, 0FFFFFFFDh
0x1400eb2e1  add     r8d, 4; Alignment
0x1400eb2e5  mov     edx, [rdi+14h]; Length
0x1400eb2e8  mov     rcx, r15; Address
0x1400eb2eb  call    cs:__imp_ProbeForWrite
0x1400eb2f2  nop     dword ptr [rax+rax+00h]
0x1400eb2f7  mov     r8d, [rdi+14h]; Size
0x1400eb2fb  mov     rdx, r12; Src
0x1400eb2fe  mov     rcx, r15; void *
0x1400eb301  call    memmove
0x1400eb306  jmp     short loc_1400EB2A5
0x1400eb308  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400eb30f  nop     dword ptr [rax+rax+00h]
0x1400eb314  neg     rax
0x1400eb317  sbb     r8d, r8d
0x1400eb31a  and     r8d, 0FFFFFFFDh
0x1400eb31e  add     r8d, 4; Alignment
0x1400eb322  mov     edx, [rdi+4]; Length
0x1400eb325  mov     rcx, r14; Address
0x1400eb328  call    cs:__imp_ProbeForWrite
0x1400eb32f  nop     dword ptr [rax+rax+00h]
0x1400eb334  mov     r8d, [rdi+4]; Size
0x1400eb338  mov     rdx, rdi; Src
0x1400eb33b  mov     rcx, r14; void *
0x1400eb33e  call    RtlCopyVolatileMemory
0x1400eb343  jmp     short loc_1400EB368
0x1400eb345  mov     ebx, 0C0000001h
0x1400eb34a  mov     [rsp+0D8h+arg_10], ebx
0x1400eb351  mov     r14, [rsp+0D8h+arg_0]
0x1400eb359  mov     rdi, [rsp+0D8h+Buffer]
0x1400eb35e  mov     r12, [rsp+0D8h+var_90]
0x1400eb363  mov     r13d, [rsp+0D8h+var_A4]
0x1400eb368  test    ebx, ebx
0x1400eb36a  js      loc_1400EB452
0x1400eb370  test    r12, r12
0x1400eb373  jnz     loc_1400EB654
0x1400eb379  test    rdi, rdi
0x1400eb37c  jnz     short loc_1400EB393
0x1400eb37e  mov     eax, ebx
0x1400eb380  add     rsp, 0A8h
0x1400eb387  pop     r15
0x1400eb389  pop     r14
0x1400eb38b  pop     r13
0x1400eb38d  pop     r12
0x1400eb38f  pop     rdi
0x1400eb390  pop     rbx
0x1400eb391  retn
0x1400eb393  mov     rcx, rdi; Buffer
0x1400eb396  call    GreDeleteFastMutex
0x1400eb39b  jmp     short loc_1400EB37E
0x1400eb39d  call    cs:__imp_W32GetUserGdiSessionState
0x1400eb3a4  nop     dword ptr [rax+rax+00h]
0x1400eb3a9  cmp     [rax+24h], ebx
0x1400eb3ac  jnz     loc_1400EB4EA
0x1400eb3b2  call    UserIsWddmConnectedSession
0x1400eb3b7  mov     ecx, 0C0000022h
0x1400eb3bc  test    eax, eax
0x1400eb3be  cmovz   ebx, ecx
0x1400eb3c1  mov     [rsp+0D8h+arg_10], ebx
0x1400eb3c8  jmp     loc_1400EB24C
0x1400eb3cd  cmp     ebx, 80000005h
0x1400eb3d3  jz      loc_1400EB524
0x1400eb3d9  mov     edx, ebx
0x1400eb3db  mov     ecx, [rdi]
0x1400eb3dd  call    _DeviceInfoTranslateStatusDefault
0x1400eb3e2  mov     ebx, eax
0x1400eb3e4  mov     [rsp+0D8h+arg_10], eax
0x1400eb3eb  jmp     loc_1400EB2A0
0x1400eb3f0  mov     ebx, 0C0000001h
0x1400eb3f5  mov     [rsp+0D8h+arg_10], ebx
0x1400eb3fc  jmp     short loc_1400EB457
0x1400eb3fe  cmp     ebx, 20h ; ' '
0x1400eb401  jnz     short loc_1400EB43F
0x1400eb403  mov     eax, [rdi+14h]
0x1400eb406  test    eax, eax
0x1400eb408  jz      loc_1400EB220
0x1400eb40e  mov     edx, eax; unsigned __int64
0x1400eb410  mov     r8d, 63447355h; unsigned int
0x1400eb416  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400eb41b  mov     r12, rax
0x1400eb41e  mov     [rsp+0D8h+var_90], rax
0x1400eb423  test    rax, rax
0x1400eb426  jz      short loc_1400EB446
0x1400eb428  mov     rax, [rdi+18h]
0x1400eb42c  mov     [rsp+0D8h+Address], rax
0x1400eb434  mov     [rdi+18h], r12
0x1400eb438  mov     ecx, [rdi]
0x1400eb43a  jmp     loc_1400EB220
0x1400eb43f  mov     ebx, 0C000000Dh
0x1400eb444  jmp     short loc_1400EB44B
0x1400eb446  mov     ebx, 0C0000017h
0x1400eb44b  mov     [rsp+0D8h+arg_10], ebx
0x1400eb452  mov     r15d, [rsp+0D8h+var_A8]
0x1400eb457  test    r13d, r13d
0x1400eb45a  jz      loc_1400EB370
0x1400eb460  xorps   xmm0, xmm0
0x1400eb463  movups  xmmword ptr [rsp+0D8h+var_58], xmm0
0x1400eb46b  movups  xmmword ptr [rsp+0D8h+var_58+0Ch], xmm0
0x1400eb473  lea     rcx, [rsp+0D8h+var_58]
0x1400eb47b  call    DrvSampleDisplayState
0x1400eb480  mov     eax, [rsp+0D8h+var_9C]
0x1400eb484  cmp     eax, [rsp+0D8h+var_58]
0x1400eb48b  jnz     loc_1400EB535
0x1400eb491  mov     eax, [rsp+0D8h+var_A0]
0x1400eb495  cmp     eax, [rsp+0D8h+var_58+8]
0x1400eb49c  jnz     loc_1400EB535
0x1400eb4a2  mov     r13d, 1
0x1400eb4a8  movsxd  r14, r15d
0x1400eb4ab  movsxd  r15, ebx
0x1400eb4ae  jmp     loc_1400EB5D4
0x1400eb4b3  cmp     ebx, 808h
0x1400eb4b9  jnz     short loc_1400EB43F
0x1400eb4bb  mov     eax, [rdi+7E0h]
0x1400eb4c1  mov     [rsp+0D8h+var_9C], eax
0x1400eb4c5  mov     eax, [rdi+7E4h]
0x1400eb4cb  mov     [rsp+0D8h+var_A0], eax
0x1400eb4cf  mov     qword ptr [rdi+7E0h], 0
0x1400eb4da  mov     r13d, 1
0x1400eb4e0  mov     [rsp+0D8h+var_A4], r13d
0x1400eb4e5  jmp     loc_1400EB220
0x1400eb4ea  mov     ebx, 0C0000001h
0x1400eb4ef  mov     [rsp+0D8h+arg_10], ebx
0x1400eb4f6  jmp     loc_1400EB27F
0x1400eb4fb  mov     ebx, 0C000000Dh
0x1400eb500  mov     [rsp+0D8h+arg_10], ebx
0x1400eb507  jmp     loc_1400EB268
0x1400eb50c  test    r13d, r13d
0x1400eb50f  jz      loc_1400EB294
0x1400eb515  mov     edx, [rdi+7E8h]
0x1400eb51b  mov     [rsp+0D8h+var_A8], edx
0x1400eb51f  jmp     loc_1400EB294
0x1400eb524  mov     ebx, 0C0000023h
0x1400eb529  mov     [rsp+0D8h+arg_10], ebx
0x1400eb530  jmp     loc_1400EB2A0
0x1400eb535  xor     r13d, r13d
0x1400eb538  mov     [rsp+0D8h+Src], r13d
0x1400eb540  lea     rcx, [r14+7E8h]; void *
0x1400eb547  lea     r8d, [r13+4]; Size
0x1400eb54b  lea     rdx, [rsp+0D8h+Src]; Src
0x1400eb553  call    RtlCopyToUser
0x1400eb558  jmp     short loc_1400EB570
0x1400eb55a  mov     rdi, [rsp+0D8h+Buffer]
  ... truncated ...
```
