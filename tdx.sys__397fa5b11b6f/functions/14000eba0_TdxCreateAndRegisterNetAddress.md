# TdxCreateAndRegisterNetAddress

- ea: `0x14000eba0`
- end: `0x14000f0f5`
- name: `TdxCreateAndRegisterNetAddress`
- size: `1365`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000e630`

## callees

- `0x14000daa0`
- `0x14000db08`
- `0x14000e1b0`
- `0x14000eba0`
- `0x14000f0fc`
- `0x14000f324`
- `0x14000f438`
- `0x140012e90`
- `0x1400151d0`
- `0x1400184b0`
- `0x140018600`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000eeb1`
- `ntoskrnl!KeReleaseMutex` at `0x14000ef40`
- `ntoskrnl!KeReleaseMutex` at `0x14000f017`
- `ntoskrnl!KeReleaseMutex` at `0x14000f093`
- `ntoskrnl!KeReleaseMutex` at `0x14000eeb1`
- `ntoskrnl!KeReleaseMutex` at `0x14000ef40`
- `ntoskrnl!KeReleaseMutex` at `0x14000f017`
- `ntoskrnl!KeReleaseMutex` at `0x14000f093`
- `ntoskrnl!RtlCompareMemory` at `0x14000ecb4`
- `ntoskrnl!RtlCompareMemory` at `0x14000ecb4`
- `ntoskrnl!ExAllocatePool2` at `0x14000ec15`
- `ntoskrnl!ExAllocatePool2` at `0x14000ec15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eec5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eec5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ec5f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000eefe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f071`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ec5f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000eefe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f071`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ed81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ed81`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000edc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000edc1`
- `NETIO!NsiGetAllParameters` at `0x14000ee7b`
- `NETIO!NsiGetAllParameters` at `0x14000ee7b`
- `TDI!TdiDeregisterDeviceObject` at `0x14000f0ab`
- `TDI!TdiDeregisterDeviceObject` at `0x14000f0ab`
- `TDI!TdiRegisterNetAddress` at `0x14000ed64`
- `TDI!TdiRegisterNetAddress` at `0x14000ed64`

## pseudocode

```c
__int64 __fastcall TdxCreateAndRegisterNetAddress(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        const UCHAR *a4,
        __int64 a5,
        int *a6)
{
  bool v9; // zf
  __int64 Pool2; // rax
  __int64 v11; // r14
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v12; // r15
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v13; // rbx
  __int128 v14; // xmm0
  int v15; // eax
  NTSTATUS AllParameters; // ebx
  __int64 v17; // r8
  KIRQL v18; // al
  __int64 v19; // rdx
  __int64 v21; // r8
  __int64 DeviceObject; // rax
  void *v23; // rdi
  __int64 v24; // [rsp+60h] [rbp-81h] BYREF
  __int64 v25; // [rsp+68h] [rbp-79h] BYREF
  __int64 Source2; // [rsp+70h] [rbp-71h] BYREF
  __int64 v27; // [rsp+78h] [rbp-69h]
  _OWORD v28[2]; // [rsp+80h] [rbp-61h] BYREF
  _DWORD Address[8]; // [rsp+A0h] [rbp-41h] BYREF
  TDI_PNP_CONTEXT Context; // [rsp+C0h] [rbp-21h] BYREF

  v27 = a2;
  v24 = 0;
  v9 = a6[1] == 4;
  v25 = 0;
  memset(v28, 0, sizeof(v28));
  if ( !v9 )
    return 3221225473LL;
  if ( a3 + 48 < a3 )
    return 3221225485LL;
  Pool2 = ExAllocatePool2(64, a3 + 48, 1853383764);
  v11 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 24) = Pool2 + 48;
    *(_DWORD *)(Pool2 + 16) = a3;
    memmove((void *)(Pool2 + 48), a4, a3);
    KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
    v12 = 0;
    v13 = WPP_MAIN_CB.DeviceQueue.1;
    Source2 = *(_QWORD *)a4;
    while ( *(struct _DEVICE_OBJECT **)&v13 != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
    {
      if ( *(_DWORD *)(*(_QWORD *)&v13 + 20LL) == a1
        && (*(_DWORD *)(*(_QWORD *)&v13 + 304LL) & 8) == 0
        && RtlCompareMemory((const void *)(*(_QWORD *)&v13 + 24LL), &Source2, 8u) == 8 )
      {
        v12 = v13;
        break;
      }
      v13 = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&v13;
    }
    v24 = (__int64)v12;
    if ( v12 )
    {
      if ( *(_DWORD *)(*(_QWORD *)&v12 + 36LL) != 24 )
        goto LABEL_13;
      if ( a1 )
      {
        if ( a1 != 41 || (int)Ipv6UnicastAddressScope(a4 + 8) >= 3 )
        {
LABEL_13:
          *(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C *)(v11 + 32) = v12;
          _InterlockedIncrement((volatile signed __int32 *)(v24 + 16));
          TdxUpdateDeviceObjectState(*(_QWORD *)(v11 + 32), a1, a4 + 8);
          memset(&Address[1], 0, 26);
          if ( a1 )
          {
            v14 = *(_OWORD *)(a4 + 8);
            v15 = *a6;
            Address[0] = 1507354;
            *(_OWORD *)((char *)&Address[2] + 2) = v14;
            *(_DWORD *)((char *)&Address[6] + 2) = v15;
          }
          else
          {
            *(_DWORD *)((char *)&Address[1] + 2) = *((_DWORD *)a4 + 2);
            Address[0] = 131086;
          }
          *(_DWORD *)&Context.ContextSize = 196616;
          *(_QWORD *)Context.ContextData = *(_QWORD *)(*(_QWORD *)(v11 + 32) + 296LL);
          AllParameters = TdiRegisterNetAddress(
                            (PTA_ADDRESS)Address,
                            (PUNICODE_STRING)(*(_QWORD *)(v11 + 32) + 40LL),
                            &Context,
                            (HANDLE *)(v11 + 40));
          if ( AllParameters >= 0 )
          {
            v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
            v19 = *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type;
            if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type + 8LL) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue )
              __fastfail(3u);
            *(_QWORD *)v11 = *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type;
            *(_QWORD *)(v11 + 8) = &WPP_MAIN_CB.DeviceQueue;
            *(_QWORD *)(v19 + 8) = v11;
            *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = v11;
            KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v18);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                31,
                WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
                v11,
                v24);
            }
            return (unsigned int)AllParameters;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, v17, (unsigned int)AllParameters);
          }
          KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
          v23 = (void *)TdxDereferenceDeviceObjectContext(v24);
          KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
          if ( v23 )
            TdiDeregisterDeviceObject(v23);
LABEL_25:
          ExFreePoolWithTag((PVOID)v11, 0x6E786454u);
          return (unsigned int)AllParameters;
        }
      }
      else if ( Ipv4UnicastAddressScope(a4 + 8) >= ScopeLevelSubnet )
      {
        goto LABEL_13;
      }
      AllParameters = -1073741823;
LABEL_24:
      KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
      goto LABEL_25;
    }
    v25 = *(_QWORD *)a4;
    AllParameters = NsiGetAllParameters(3, v27, 7, &v25, 8, 0, 0, 0, 0, v28, 32);
    if ( AllParameters < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, v21, (unsigned int)AllParameters);
      }
      goto LABEL_24;
    }
    if ( DWORD1(v28[0]) == 24 )
    {
      if ( !a1 )
      {
        if ( Ipv4UnicastAddressScope(a4 + 8) >= ScopeLevelSubnet )
          goto LABEL_44;
LABEL_48:
        KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
        AllParameters = 0;
        goto LABEL_25;
      }
      if ( a1 == 41 && (int)Ipv6UnicastAddressScope(a4 + 8) < 3 )
        goto LABEL_48;
    }
LABEL_44:
    AllParameters = TdxCreateAndRegisterDeviceObject(&v25, a1, v28, &v24);
    if ( AllParameters >= 0 )
    {
      v12 = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)v24;
      goto LABEL_13;
    }
    goto LABEL_24;
  }
  KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
  DeviceObject = TdxFindDeviceObject(&WPP_MAIN_CB.DeviceQueue.Busy, *(_QWORD *)a4, a1);
  v24 = DeviceObject;
  if ( DeviceObject )
    TdxUpdateDeviceObjectState(DeviceObject, a1, a4 + 8);
  else
    KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x14000eba0  push    rbp
0x14000eba2  push    rbx
0x14000eba3  push    rsi
0x14000eba4  push    rdi
0x14000eba5  push    r12
0x14000eba7  push    r13
0x14000eba9  lea     rbp, [rsp-17h]
0x14000ebae  sub     rsp, 0F8h
0x14000ebb5  mov     rax, cs:__security_cookie
0x14000ebbc  xor     rax, rsp
0x14000ebbf  mov     [rbp+3Fh+var_50], rax
0x14000ebc3  mov     r12, [rbp+3Fh+arg_28]
0x14000ebc7  xor     esi, esi
0x14000ebc9  xorps   xmm0, xmm0
0x14000ebcc  mov     ebx, r8d
0x14000ebcf  mov     r13, r9
0x14000ebd2  mov     [rbp+3Fh+var_A8], rdx
0x14000ebd6  mov     edi, ecx
0x14000ebd8  mov     [rsp+120h+var_C0], rsi
0x14000ebdd  cmp     dword ptr [r12+4], 4
0x14000ebe3  mov     [rbp+3Fh+var_B8], rsi
0x14000ebe7  movups  [rbp+3Fh+var_A0], xmm0
0x14000ebeb  movups  [rbp+3Fh+var_90], xmm0
0x14000ebef  jnz     loc_14000EED6
0x14000ebf5  lea     eax, [rbx+30h]
0x14000ebf8  cmp     eax, ebx
0x14000ebfa  jb      loc_14000EEE0
0x14000ec00  mov     edx, eax
0x14000ec02  mov     ecx, 40h ; '@'
0x14000ec07  mov     r8d, 6E786454h
0x14000ec0d  mov     [rsp+120h+var_30], r14
0x14000ec15  call    cs:__imp_ExAllocatePool2
0x14000ec1c  nop     dword ptr [rax+rax+00h]
0x14000ec21  mov     r14, rax
0x14000ec24  test    rax, rax
0x14000ec27  jz      loc_14000EEEA
0x14000ec2d  lea     rcx, [rax+30h]; void *
0x14000ec31  mov     [rsp+120h+var_38], r15
0x14000ec39  mov     r8d, ebx; Size
0x14000ec3c  mov     [rax+18h], rcx
0x14000ec40  mov     rdx, r13; Src
0x14000ec43  mov     [rax+10h], ebx
0x14000ec46  call    memmove
0x14000ec4b  xor     r9d, r9d; Alertable
0x14000ec4e  mov     [rsp+120h+Timeout], rsi; Timeout
0x14000ec53  xor     r8d, r8d; WaitMode
0x14000ec56  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Object
0x14000ec5d  xor     edx, edx; WaitReason
0x14000ec5f  call    cs:__imp_KeWaitForSingleObject
0x14000ec66  nop     dword ptr [rax+rax+00h]
0x14000ec6b  mov     rax, [r13+0]
0x14000ec6f  mov     r15d, esi
0x14000ec72  mov     rbx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000ec79  lea     rsi, WPP_MAIN_CB.DeviceQueue.20h
0x14000ec80  mov     [rbp+3Fh+Source2], rax
0x14000ec84  mov     edx, 8
0x14000ec89  nop     dword ptr [rax+00000000h]
0x14000ec90  cmp     rbx, rsi
0x14000ec93  jz      short loc_14000ECCD
0x14000ec95  cmp     [rbx+14h], edi
0x14000ec98  jnz     short loc_14000ECA4
0x14000ec9a  mov     eax, [rbx+130h]
0x14000eca0  test    al, 8
0x14000eca2  jz      short loc_14000ECA9
0x14000eca4  mov     rbx, [rbx]
0x14000eca7  jmp     short loc_14000EC90
0x14000eca9  mov     r8, rdx; Length
0x14000ecac  lea     rcx, [rbx+18h]; Source1
0x14000ecb0  lea     rdx, [rbp+3Fh+Source2]; Source2
0x14000ecb4  call    cs:__imp_RtlCompareMemory
0x14000ecbb  nop     dword ptr [rax+rax+00h]
0x14000ecc0  mov     edx, 8
0x14000ecc5  cmp     rax, rdx
0x14000ecc8  jnz     short loc_14000ECA4
0x14000ecca  mov     r15, rbx
0x14000eccd  mov     [rsp+120h+var_C0], r15
0x14000ecd2  mov     esi, 3
0x14000ecd7  test    r15, r15
0x14000ecda  jz      loc_14000EE2C
0x14000ece0  cmp     dword ptr [r15+24h], 18h
0x14000ece5  jz      loc_14000EF56
0x14000eceb  mov     [r14+20h], r15
0x14000ecef  mov     rax, [rsp+120h+var_C0]
0x14000ecf4  lock inc dword ptr [rax+10h]
0x14000ecf8  mov     rcx, [r14+20h]
0x14000ecfc  lea     r8, [r13+8]
0x14000ed00  mov     edx, edi
0x14000ed02  call    TdxUpdateDeviceObjectState
0x14000ed07  xor     r15d, r15d
0x14000ed0a  xorps   xmm0, xmm0
0x14000ed0d  mov     [rbp+3Fh+var_6C], r15
0x14000ed11  mov     [rbp+3Fh+var_64], r15w
0x14000ed16  movdqu  xmmword ptr [rbp+3Fh+Address.Address], xmm0
0x14000ed1b  test    edi, edi
0x14000ed1d  jz      loc_14000EE19
0x14000ed23  movups  xmm0, xmmword ptr [r13+8]
0x14000ed28  mov     eax, [r12]
0x14000ed2c  mov     dword ptr [rbp+3Fh+Address.AddressLength], 17001Ah
0x14000ed33  movups  xmmword ptr [rbp-37h], xmm0
0x14000ed37  mov     dword ptr [rbp+3Fh+var_6C+6], eax
0x14000ed3a  mov     dword ptr [rbp+3Fh+Context.ContextSize], 30008h
0x14000ed41  lea     r9, [r14+28h]; RegistrationHandle
0x14000ed45  mov     rax, [r14+20h]
0x14000ed49  lea     r8, [rbp+3Fh+Context]; Context
0x14000ed4d  mov     rcx, [rax+128h]
0x14000ed54  mov     qword ptr [rbp+3Fh+Context.ContextData], rcx
0x14000ed58  lea     rcx, [rbp+3Fh+Address]; Address
0x14000ed5c  mov     rdx, [r14+20h]
0x14000ed60  add     rdx, 28h ; '('; DeviceName
0x14000ed64  call    cs:__imp_TdiRegisterNetAddress
0x14000ed6b  nop     dword ptr [rax+rax+00h]
0x14000ed70  mov     ebx, eax
0x14000ed72  test    eax, eax
0x14000ed74  js      loc_14000F02A
0x14000ed7a  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000ed81  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ed88  nop     dword ptr [rax+rax+00h]
0x14000ed8d  mov     rdx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x14000ed94  lea     r8, WPP_MAIN_CB.DeviceQueue
0x14000ed9b  cmp     [rdx+8], r8
0x14000ed9f  jnz     loc_14000F0BC
0x14000eda5  mov     [r14], rdx
0x14000eda8  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000edaf  mov     [r14+8], r8
0x14000edb3  mov     [rdx+8], r14
0x14000edb7  movzx   edx, al; NewIrql
0x14000edba  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, r14
0x14000edc1  call    cs:__imp_KeReleaseSpinLock
0x14000edc8  nop     dword ptr [rax+rax+00h]
0x14000edcd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edd4  lea     rax, WPP_GLOBAL_Control
0x14000eddb  cmp     rcx, rax
0x14000edde  jz      short loc_14000EDEA
0x14000ede0  cmp     [rcx+29h], sil
0x14000ede4  jnb     loc_14000F0C1
0x14000edea  mov     r15, [rsp+120h+var_38]
0x14000edf2  mov     eax, ebx
0x14000edf4  mov     r14, [rsp+120h+var_30]
0x14000edfc  mov     rcx, [rbp+3Fh+var_50]
0x14000ee00  xor     rcx, rsp; StackCookie
0x14000ee03  call    __security_check_cookie
0x14000ee08  add     rsp, 0F8h
0x14000ee0f  pop     r13
0x14000ee11  pop     r12
0x14000ee13  pop     rdi
0x14000ee14  pop     rsi
0x14000ee15  pop     rbx
0x14000ee16  pop     rbp
0x14000ee17  retn
0x14000ee19  mov     eax, [r13+8]
0x14000ee1d  mov     [rbp-3Bh], eax
0x14000ee20  mov     dword ptr [rbp+3Fh+Address.AddressLength], 2000Eh
0x14000ee27  jmp     loc_14000ED3A
0x14000ee2c  mov     rax, [r13+0]
0x14000ee30  lea     r9, [rbp+3Fh+var_B8]
0x14000ee34  mov     [rsp+120h+var_D0], 20h ; ' '
0x14000ee3c  mov     r8d, 7
0x14000ee42  mov     [rbp+3Fh+var_B8], rax
0x14000ee46  mov     ecx, esi
0x14000ee48  lea     rax, [rbp+3Fh+var_A0]
0x14000ee4c  mov     [rsp+120h+var_D8], rax
0x14000ee51  mov     [rsp+120h+var_E0], 0
0x14000ee59  mov     [rsp+120h+var_E8], 0
0x14000ee62  mov     [rsp+120h+var_F0], 0
0x14000ee6a  mov     [rsp+120h+var_F8], 0
0x14000ee73  mov     dword ptr [rsp+120h+Timeout], edx
0x14000ee77  mov     rdx, [rbp+3Fh+var_A8]
0x14000ee7b  call    cs:__imp_NsiGetAllParameters
0x14000ee82  nop     dword ptr [rax+rax+00h]
0x14000ee87  mov     ebx, eax
0x14000ee89  test    eax, eax
0x14000ee8b  jns     loc_14000EFBD
0x14000ee91  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee98  lea     rax, WPP_GLOBAL_Control
0x14000ee9f  cmp     rcx, rax
0x14000eea2  jnz     loc_14000EF90
0x14000eea8  xor     edx, edx; Wait
0x14000eeaa  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000eeb1  call    cs:__imp_KeReleaseMutex
0x14000eeb8  nop     dword ptr [rax+rax+00h]
0x14000eebd  mov     edx, 6E786454h; Tag
0x14000eec2  mov     rcx, r14; P
0x14000eec5  call    cs:__imp_ExFreePoolWithTag
0x14000eecc  nop     dword ptr [rax+rax+00h]
0x14000eed1  jmp     loc_14000EDEA
0x14000eed6  mov     eax, 0C0000001h
0x14000eedb  jmp     loc_14000EDFC
0x14000eee0  mov     eax, 0C000000Dh
0x14000eee5  jmp     loc_14000EDFC
0x14000eeea  xor     r9d, r9d; Alertable
0x14000eeed  mov     [rsp+120h+Timeout], rsi; Timeout
0x14000eef2  xor     r8d, r8d; WaitMode
0x14000eef5  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Object
0x14000eefc  xor     edx, edx; WaitReason
0x14000eefe  call    cs:__imp_KeWaitForSingleObject
0x14000ef05  nop     dword ptr [rax+rax+00h]
0x14000ef0a  mov     rdx, [r13+0]
0x14000ef0e  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h
0x14000ef15  mov     r8d, edi
0x14000ef18  call    TdxFindDeviceObject
0x14000ef1d  mov     [rsp+120h+var_C0], rax
0x14000ef22  test    rax, rax
0x14000ef25  jz      short loc_14000EF37
0x14000ef27  lea     r8, [r13+8]
0x14000ef2b  mov     edx, edi
0x14000ef2d  mov     rcx, rax
0x14000ef30  call    TdxUpdateDeviceObjectState
0x14000ef35  jmp     short loc_14000EF4C
0x14000ef37  xor     edx, edx; Wait
0x14000ef39  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000ef40  call    cs:__imp_KeReleaseMutex
0x14000ef47  nop     dword ptr [rax+rax+00h]
0x14000ef4c  mov     eax, 0C0000017h
0x14000ef51  jmp     loc_14000EDF4
0x14000ef56  test    edi, edi
0x14000ef58  jnz     short loc_14000EF6C
0x14000ef5a  lea     rcx, [r13+8]; Address
0x14000ef5e  call    Ipv4UnicastAddressScope
0x14000ef63  cmp     eax, esi
0x14000ef65  jl      short loc_14000EF86
0x14000ef67  jmp     loc_14000ECEB
0x14000ef6c  cmp     edi, 29h ; ')'
0x14000ef6f  jnz     loc_14000ECEB
0x14000ef75  lea     rcx, [r13+8]
0x14000ef79  call    Ipv6UnicastAddressScope
0x14000ef7e  cmp     eax, esi
0x14000ef80  jge     loc_14000ECEB
0x14000ef86  mov     ebx, 0C0000001h
0x14000ef8b  jmp     loc_14000EEA8
0x14000ef90  cmp     [rcx+29h], sil
0x14000ef94  jb      loc_14000EEA8
0x14000ef9a  test    dword ptr [rcx+2Ch], 200h
0x14000efa1  jz      loc_14000EEA8
0x14000efa7  mov     rcx, [rcx+18h]
0x14000efab  mov     edx, 1Dh
0x14000efb0  mov     r9d, ebx
0x14000efb3  call    WPP_SF_d
0x14000efb8  jmp     loc_14000EEA8
0x14000efbd  cmp     dword ptr [rbp+3Fh+var_A0+4], 18h
0x14000efc1  jnz     short loc_14000EFD4
0x14000efc3  test    edi, edi
0x14000efc5  jnz     short loc_14000EFFC
0x14000efc7  lea     rcx, [r13+8]; Address
0x14000efcb  call    Ipv4UnicastAddressScope
0x14000efd0  cmp     eax, esi
0x14000efd2  jl      short loc_14000F00E
0x14000efd4  lea     r9, [rsp+120h+var_C0]
0x14000efd9  mov     edx, edi
0x14000efdb  lea     r8, [rbp+3Fh+var_A0]
0x14000efdf  lea     rcx, [rbp+3Fh+var_B8]
0x14000efe3  call    TdxCreateAndRegisterDeviceObject
0x14000efe8  mov     ebx, eax
0x14000efea  test    eax, eax
0x14000efec  js      loc_14000EEA8
0x14000eff2  mov     r15, [rsp+120h+var_C0]
0x14000eff7  jmp     loc_14000ECEB
0x14000effc  cmp     edi, 29h ; ')'
0x14000efff  jnz     short loc_14000EFD4
0x14000f001  lea     rcx, [r13+8]
0x14000f005  call    Ipv6UnicastAddressScope
0x14000f00a  cmp     eax, esi
0x14000f00c  jge     short loc_14000EFD4
0x14000f00e  xor     edx, edx; Wait
0x14000f010  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000f017  call    cs:__imp_KeReleaseMutex
0x14000f01e  nop     dword ptr [rax+rax+00h]
0x14000f023  xor     ebx, ebx
0x14000f025  jmp     loc_14000EEBD
0x14000f02a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f031  lea     rax, WPP_GLOBAL_Control
0x14000f038  cmp     rcx, rax
0x14000f03b  jz      short loc_14000F05D
0x14000f03d  cmp     [rcx+29h], sil
0x14000f041  jb      short loc_14000F05D
0x14000f043  test    dword ptr [rcx+2Ch], 200h
0x14000f04a  jz      short loc_14000F05D
0x14000f04c  mov     rcx, [rcx+18h]
0x14000f050  mov     edx, 1Eh
0x14000f055  mov     r9d, ebx
0x14000f058  call    WPP_SF_d
0x14000f05d  xor     r9d, r9d; Alertable
0x14000f060  mov     [rsp+120h+Timeout], r15; Timeout
0x14000f065  xor     r8d, r8d; WaitMode
0x14000f068  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Object
0x14000f06f  xor     edx, edx; WaitReason
0x14000f071  call    cs:__imp_KeWaitForSingleObject
0x14000f078  nop     dword ptr [rax+rax+00h]
0x14000f07d  mov     rcx, [rsp+120h+var_C0]
0x14000f082  call    TdxDereferenceDeviceObjectContext
0x14000f087  xor     edx, edx; Wait
0x14000f089  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000f090  mov     rdi, rax
0x14000f093  call    cs:__imp_KeReleaseMutex
0x14000f09a  nop     dword ptr [rax+rax+00h]
0x14000f09f  test    rdi, rdi
0x14000f0a2  jz      loc_14000EEBD
0x14000f0a8  mov     rcx, rdi; RegistrationHandle
0x14000f0ab  call    cs:__imp_TdiDeregisterDeviceObject
0x14000f0b2  nop     dword ptr [rax+rax+00h]
0x14000f0b7  jmp     loc_14000EEBD
  ... truncated ...
```
