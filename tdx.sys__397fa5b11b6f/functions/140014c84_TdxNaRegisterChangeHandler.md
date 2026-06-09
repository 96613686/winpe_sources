# TdxNaRegisterChangeHandler

- ea: `0x140014c84`
- end: `0x140015032`
- name: `TdxNaRegisterChangeHandler`
- size: `942`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x14001154c`

## callees

- `0x14000e368`
- `0x14000e4ec`
- `0x14000f364`
- `0x140010db4`
- `0x140012b5c`
- `0x140014958`
- `0x140014988`
- `0x140014c84`
- `0x1400151d0`
- `0x1400154a0`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140014f56`
- `ntoskrnl!KeSetTimer` at `0x140014f56`
- `ntoskrnl!KeDelayExecutionThread` at `0x140014e25`
- `ntoskrnl!KeDelayExecutionThread` at `0x140014e25`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014e91`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014e91`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014eae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014ec8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014eae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014ec8`
- `NETIO!NsiGetParameter` at `0x140014d5d`
- `NETIO!NsiGetParameter` at `0x140014d5d`
- `NETIO!NsiGetAllParameters` at `0x140014d09`
- `NETIO!NsiGetAllParameters` at `0x140014de2`
- `NETIO!NsiGetAllParameters` at `0x140014d09`
- `NETIO!NsiGetAllParameters` at `0x140014de2`
- `NETIO!NsiRegisterChangeNotification` at `0x140014fc2`
- `NETIO!NsiRegisterChangeNotification` at `0x140014fc2`

## pseudocode

```c
__int64 __fastcall TdxNaRegisterChangeHandler(_BYTE *a1)
{
  char v1; // si
  char v2; // di
  bool IsV6RegistryDisabled; // r14
  char v4; // r12
  char v5; // bl
  char v6; // r13
  int v7; // r15d
  __int64 v8; // r8
  __int64 v9; // r9
  KIRQL v10; // al
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  char v15; // [rsp+A0h] [rbp+40h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+50h] BYREF

  Interval.QuadPart = -100000;
  v1 = 0;
  v17 = 0;
  v2 = 0;
  *a1 = 1;
  IsV6RegistryDisabled = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    if ( v1 || v5 )
      goto LABEL_14;
    if ( (unsigned int)NsiGetAllParameters(3, &NPI_MS_FL48_MODULEID, 0, 0, 0, 0, 0, &v17, 8, 0, 0) || BYTE4(v17) )
      break;
    if ( !v6 )
    {
      v6 = 1;
      v15 = 1;
      NsiGetParameter(0, &NPI_MS_IPV4_MODULEID, 6, 0, 0, 0, &v15, 1, 44);
      if ( !v15 )
      {
        if ( v2 || IsV6RegistryDisabled )
          goto LABEL_25;
        v5 = 1;
        goto LABEL_16;
      }
      v5 = 0;
    }
LABEL_14:
    if ( v2 || IsV6RegistryDisabled )
      goto LABEL_24;
LABEL_16:
    if ( (unsigned int)NsiGetAllParameters(3, &NPI_MS_FL68_MODULEID, 0, 0, 0, 0, 0, &v17, 8, 0, 0) || BYTE4(v17) )
    {
      v2 = 1;
    }
    else
    {
      if ( v4 )
        goto LABEL_24;
      v4 = 1;
      IsV6RegistryDisabled = TdxIsV6RegistryDisabled();
      if ( !IsV6RegistryDisabled )
        goto LABEL_24;
    }
    if ( v1 || v5 )
      goto LABEL_25;
LABEL_24:
    KeDelayExecutionThread(0, 0, &Interval);
    if ( (unsigned int)++v7 >= 0x12C )
      goto LABEL_25;
  }
  v1 = 1;
  if ( !v2 && !IsV6RegistryDisabled )
    goto LABEL_14;
LABEL_25:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
  {
    if ( !v1 || (v9 = 0, !v2) )
      v9 = 1;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, v8, v9);
  }
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  v11 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
  if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
  {
    _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 16LL), 1u);
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, v10);
    TdxNaRegisterAddressAndInterfaceChangeHandler(0);
    TdxNaRegisterAddressAndInterfaceChangeHandler(41);
    if ( (unsigned __int8)TdxNaWaitForDelayedBinds() )
    {
      Interval.QuadPart = -30000000;
      TdxIncrementNotReadyInterfaceCount(2238);
      _InterlockedExchange((_DWORD *)&qword_14001E508 + 1, 1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
      {
        WPP_SF_sii(WPP_GLOBAL_Control->AttachedDevice, 44);
      }
      KeSetTimer(&TdxProviderReadyContext, Interval, &Dpc);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
      {
        WPP_SF_sii(WPP_GLOBAL_Control->AttachedDevice, 45);
      }
    }
    if ( (int)NsiRegisterChangeNotification(
                &NPI_MS_NDIS_MODULEID,
                1,
                TdxNaInterfaceChangeEvent,
                0,
                &NPI_MS_NDIS_MODULEID,
                &WPP_MAIN_CB.Reserved) >= 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids);
    }
    if ( v11 )
      TdxDereferenceNaProviderContext(v11);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, v10);
  }
  TdxDecrementNotReadyInterfaceCount(0x8F7u, v12, v13);
  return 0;
}

```

## disassembly

```asm
0x140014c84  mov     [rsp-38h+arg_18], rbx
0x140014c89  push    rbp
0x140014c8a  push    rsi
0x140014c8b  push    rdi
0x140014c8c  push    r12
0x140014c8e  push    r13
0x140014c90  push    r14
0x140014c92  push    r15
0x140014c94  mov     rbp, rsp
0x140014c97  sub     rsp, 60h
0x140014c9b  xor     edx, edx
0x140014c9d  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFE7960h
0x140014ca5  mov     sil, dl
0x140014ca8  mov     [rbp+arg_10], rdx
0x140014cac  mov     dil, dl
0x140014caf  mov     byte ptr [rcx], 1
0x140014cb2  mov     r14b, dl
0x140014cb5  mov     r12b, dl
0x140014cb8  mov     bl, dl
0x140014cba  mov     r13b, dl
0x140014cbd  mov     r15d, edx
0x140014cc0  test    sil, sil
0x140014cc3  jnz     loc_140014DA0
0x140014cc9  test    bl, bl
0x140014ccb  jnz     loc_140014DA0
0x140014cd1  mov     [rsp+60h+var_10], edx
0x140014cd5  lea     rax, [rbp+arg_10]
0x140014cd9  mov     [rsp+60h+var_18], rdx
0x140014cde  xor     r9d, r9d
0x140014ce1  mov     [rsp+60h+var_20], 8
0x140014ce9  xor     r8d, r8d
0x140014cec  mov     [rsp+60h+var_28], rax
0x140014cf1  mov     dword ptr [rsp+60h+var_30], edx
0x140014cf5  mov     [rsp+60h+var_38], rdx
0x140014cfa  lea     ecx, [r9+3]
0x140014cfe  mov     dword ptr [rsp+60h+var_40], edx
0x140014d02  lea     rdx, NPI_MS_FL48_MODULEID
0x140014d09  call    cs:__imp_NsiGetAllParameters
0x140014d10  nop     dword ptr [rax+rax+00h]
0x140014d15  xor     edx, edx
0x140014d17  test    eax, eax
0x140014d19  jnz     short loc_140014D8B
0x140014d1b  cmp     byte ptr [rbp+arg_10+4], dl
0x140014d1e  jnz     short loc_140014D8B
0x140014d20  test    r13b, r13b
0x140014d23  jnz     short loc_140014DA0
0x140014d25  mov     [rsp+60h+var_20], 2Ch ; ','
0x140014d2d  lea     rax, [rbp+arg_0]
0x140014d31  mov     dword ptr [rsp+60h+var_28], 1
0x140014d39  lea     r8d, [rdx+6]
0x140014d3d  mov     [rsp+60h+var_30], rax
0x140014d42  mov     r13b, 1
0x140014d45  mov     dword ptr [rsp+60h+var_38], edx
0x140014d49  xor     r9d, r9d
0x140014d4c  mov     dword ptr [rsp+60h+var_40], edx
0x140014d50  xor     ecx, ecx
0x140014d52  lea     rdx, NPI_MS_IPV4_MODULEID
0x140014d59  mov     [rbp+arg_0], r13b
0x140014d5d  call    cs:__imp_NsiGetParameter
0x140014d64  nop     dword ptr [rax+rax+00h]
0x140014d69  xor     edx, edx
0x140014d6b  cmp     [rbp+arg_0], dl
0x140014d6e  jnz     short loc_140014D87
0x140014d70  test    dil, dil
0x140014d73  jnz     loc_140014E46
0x140014d79  test    r14b, r14b
0x140014d7c  jnz     loc_140014E46
0x140014d82  mov     bl, r13b
0x140014d85  jmp     short loc_140014DAA
0x140014d87  mov     bl, dl
0x140014d89  jmp     short loc_140014DA0
0x140014d8b  mov     sil, 1
0x140014d8e  test    dil, dil
0x140014d91  jnz     loc_140014E46
0x140014d97  test    r14b, r14b
0x140014d9a  jnz     loc_140014E46
0x140014da0  test    dil, dil
0x140014da3  jnz     short loc_140014E1D
0x140014da5  test    r14b, r14b
0x140014da8  jnz     short loc_140014E1D
0x140014daa  mov     [rsp+60h+var_10], edx
0x140014dae  lea     rax, [rbp+arg_10]
0x140014db2  mov     [rsp+60h+var_18], rdx
0x140014db7  xor     r9d, r9d
0x140014dba  mov     [rsp+60h+var_20], 8
0x140014dc2  xor     r8d, r8d
0x140014dc5  mov     [rsp+60h+var_28], rax
0x140014dca  mov     dword ptr [rsp+60h+var_30], edx
0x140014dce  mov     [rsp+60h+var_38], rdx
0x140014dd3  lea     ecx, [r9+3]
0x140014dd7  mov     dword ptr [rsp+60h+var_40], edx
0x140014ddb  lea     rdx, NPI_MS_FL68_MODULEID
0x140014de2  call    cs:__imp_NsiGetAllParameters
0x140014de9  nop     dword ptr [rax+rax+00h]
0x140014dee  xor     edx, edx
0x140014df0  test    eax, eax
0x140014df2  jnz     short loc_140014E11
0x140014df4  cmp     byte ptr [rbp+arg_10+4], dl
0x140014df7  jnz     short loc_140014E11
0x140014df9  test    r12b, r12b
0x140014dfc  jnz     short loc_140014E1D
0x140014dfe  mov     r12b, 1
0x140014e01  call    TdxIsV6RegistryDisabled
0x140014e06  xor     edx, edx
0x140014e08  mov     r14b, al
0x140014e0b  test    al, al
0x140014e0d  jz      short loc_140014E1D
0x140014e0f  jmp     short loc_140014E14
0x140014e11  mov     dil, 1
0x140014e14  test    sil, sil
0x140014e17  jnz     short loc_140014E46
0x140014e19  test    bl, bl
0x140014e1b  jnz     short loc_140014E46
0x140014e1d  lea     r8, [rbp+Interval]; Interval
0x140014e21  xor     edx, edx; Alertable
0x140014e23  xor     ecx, ecx; WaitMode
0x140014e25  call    cs:__imp_KeDelayExecutionThread
0x140014e2c  nop     dword ptr [rax+rax+00h]
0x140014e31  inc     r15d
0x140014e34  mov     edx, 0
0x140014e39  cmp     r15d, 12Ch
0x140014e40  jb      loc_140014CC0
0x140014e46  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e4d  lea     r15, WPP_GLOBAL_Control
0x140014e54  cmp     rcx, r15
0x140014e57  jz      short loc_140014E87
0x140014e59  cmp     byte ptr [rcx+29h], 3
0x140014e5d  jb      short loc_140014E87
0x140014e5f  bt      dword ptr [rcx+2Ch], 9
0x140014e64  jnb     short loc_140014E87
0x140014e66  test    sil, sil
0x140014e69  jz      short loc_140014E73
0x140014e6b  mov     r9d, edx
0x140014e6e  test    dil, dil
0x140014e71  jnz     short loc_140014E79
0x140014e73  mov     r9d, 1
0x140014e79  mov     rcx, [rcx+18h]
0x140014e7d  mov     edx, 2Bh ; '+'
0x140014e82  call    WPP_SF_d
0x140014e87  lea     rsi, WPP_MAIN_CB.Queue+30h
0x140014e8e  mov     rcx, rsi; SpinLock
0x140014e91  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014e98  nop     dword ptr [rax+rax+00h]
0x140014e9d  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140014ea4  mov     rcx, rsi; SpinLock
0x140014ea7  mov     dl, al; NewIrql
0x140014ea9  test    rbx, rbx
0x140014eac  jnz     short loc_140014EBF
0x140014eae  call    cs:__imp_KeReleaseSpinLock
0x140014eb5  nop     dword ptr [rax+rax+00h]
0x140014eba  jmp     loc_14001500D
0x140014ebf  mov     edi, 1
0x140014ec4  lock add [rbx+10h], edi
0x140014ec8  call    cs:__imp_KeReleaseSpinLock
0x140014ecf  nop     dword ptr [rax+rax+00h]
0x140014ed4  xor     ecx, ecx
0x140014ed6  call    TdxNaRegisterAddressAndInterfaceChangeHandler
0x140014edb  lea     ecx, [rdi+28h]
0x140014ede  call    TdxNaRegisterAddressAndInterfaceChangeHandler
0x140014ee3  call    TdxNaWaitForDelayedBinds
0x140014ee8  test    al, al
0x140014eea  jz      loc_140014F9E
0x140014ef0  mov     ecx, 8BEh
0x140014ef5  mov     qword ptr [rbp+Interval], 0FFFFFFFFFE363C80h
0x140014efd  call    TdxIncrementNotReadyInterfaceCount
0x140014f02  mov     eax, edi
0x140014f04  xchg    eax, dword ptr cs:qword_14001E508+4
0x140014f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f11  cmp     rcx, r15
0x140014f14  jz      short loc_140014F44
0x140014f16  cmp     byte ptr [rcx+29h], 3
0x140014f1a  jb      short loc_140014F44
0x140014f1c  bt      dword ptr [rcx+2Ch], 9
0x140014f21  jnb     short loc_140014F44
0x140014f23  mov     rax, qword ptr [rbp+Interval]
0x140014f27  lea     edx, [rdi+2Bh]
0x140014f2a  mov     rcx, [rcx+18h]
0x140014f2e  mov     [rsp+60h+var_38], rax
0x140014f33  mov     rax, qword ptr cs:TdxProviderReadyContext.DueTime
0x140014f3a  mov     [rsp+60h+var_40], rax
0x140014f3f  call    WPP_SF_sii
0x140014f44  mov     rdx, qword ptr [rbp+Interval]; DueTime
0x140014f48  lea     r8, Dpc; Dpc
0x140014f4f  lea     rcx, TdxProviderReadyContext; Timer
0x140014f56  call    cs:__imp_KeSetTimer
0x140014f5d  nop     dword ptr [rax+rax+00h]
0x140014f62  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f69  cmp     rcx, r15
0x140014f6c  jz      short loc_140014F9E
0x140014f6e  cmp     byte ptr [rcx+29h], 3
0x140014f72  jb      short loc_140014F9E
0x140014f74  bt      dword ptr [rcx+2Ch], 9
0x140014f79  jnb     short loc_140014F9E
0x140014f7b  mov     rax, qword ptr [rbp+Interval]
0x140014f7f  mov     edx, 2Dh ; '-'
0x140014f84  mov     rcx, [rcx+18h]
0x140014f88  mov     [rsp+60h+var_38], rax
0x140014f8d  mov     rax, qword ptr cs:TdxProviderReadyContext.DueTime
0x140014f94  mov     [rsp+60h+var_40], rax
0x140014f99  call    WPP_SF_sii
0x140014f9e  lea     rax, WPP_MAIN_CB.Reserved
0x140014fa5  xor     r9d, r9d
0x140014fa8  lea     rcx, NPI_MS_NDIS_MODULEID
0x140014faf  mov     [rsp+60h+var_38], rax
0x140014fb4  lea     r8, TdxNaInterfaceChangeEvent
0x140014fbb  mov     [rsp+60h+var_40], rcx
0x140014fc0  mov     edx, edi
0x140014fc2  call    cs:__imp_NsiRegisterChangeNotification
0x140014fc9  nop     dword ptr [rax+rax+00h]
0x140014fce  test    eax, eax
0x140014fd0  js      short loc_140015000
0x140014fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140014fd9  cmp     rcx, r15
0x140014fdc  jz      short loc_140015000
0x140014fde  cmp     byte ptr [rcx+29h], 3
0x140014fe2  jb      short loc_140015000
0x140014fe4  bt      dword ptr [rcx+2Ch], 9
0x140014fe9  jnb     short loc_140015000
0x140014feb  mov     rcx, [rcx+18h]
0x140014fef  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x140014ff6  mov     edx, 2Eh ; '.'
0x140014ffb  call    WPP_SF_
0x140015000  test    rbx, rbx
0x140015003  jz      short loc_14001500D
0x140015005  mov     rcx, rbx
0x140015008  call    TdxDereferenceNaProviderContext
0x14001500d  mov     ecx, 8F7h
0x140015012  call    TdxDecrementNotReadyInterfaceCount
0x140015017  mov     rbx, [rsp+60h+arg_18]
0x14001501f  xor     eax, eax
0x140015021  add     rsp, 60h
0x140015025  pop     r15
0x140015027  pop     r14
0x140015029  pop     r13
0x14001502b  pop     r12
0x14001502d  pop     rdi
0x14001502e  pop     rsi
0x14001502f  pop     rbp
0x140015030  retn
```
