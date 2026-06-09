# HUBPDO_EvtDeviceUsageNotificationEx

- ea: `0x140015eb0`
- end: `0x140016151`
- name: `HUBPDO_EvtDeviceUsageNotificationEx`
- size: `673`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x1400145d8`
- `0x140015eb0`
- `0x14002f0b4`
- `0x140040610`
- `0x1400406c8`
- `0x140045570`
- `0x14008a864`
- `0x14008e98c`

## import_xrefs

- `ntoskrnl!RtlCheckRegistryKey` at `0x140015ed1`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140015ed1`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceUsageNotificationEx(__int64 a1, int a2, char a3)
{
  bool v6; // r14
  __int64 v7; // rbx
  unsigned int ForwardProgressResources; // esi
  __int64 v9; // rax
  int v10; // edi
  int v11; // edi
  int v12; // edx
  __int64 v13; // r10
  char IsBootDeviceExternal; // al
  int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rax
  int v20; // edx

  v6 = RtlCheckRegistryKey(2u, (PWSTR)L"MiniNT") >= 0;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  ForwardProgressResources = 0;
  v9 = *(_QWORD *)(v7 + 24);
  if ( (*(_DWORD *)(v9 + 1648) & 0x10) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(v9 + 1648), 0x10u);
    HUBREG_UpdateSqmFlags(*(_QWORD *)(v7 + 24));
  }
  v10 = a2 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( !v11 )
    {
      if ( !a3 )
        return ForwardProgressResources;
LABEL_28:
      *(_BYTE *)(*(_QWORD *)(v7 + 24) + 1520LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1280LL) = 1;
      return ForwardProgressResources;
    }
    if ( v11 != 2 )
      return ForwardProgressResources;
  }
  else
  {
    IsBootDeviceExternal = HUBBOOT_IsBootDeviceExternal(a1);
    if ( !v6 && IsBootDeviceExternal && (*(_DWORD *)(v7 + 32) & 0x20) == 0 )
      return (unsigned int)-1073741637;
  }
  if ( (*(_DWORD *)(v7 + 32) & 0x20) != 0 )
    return ForwardProgressResources;
  ForwardProgressResources = HUBPDO_AllocateForwardProgressResources(*(_QWORD *)(v7 + 24));
  if ( (ForwardProgressResources & 0x80000000) != 0 )
    return ForwardProgressResources;
  v13 = *(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL);
  if ( (*(_DWORD *)(v13 + 1336) & 1) != 0 )
  {
    if ( !v6 )
    {
      if ( (unsigned __int8)HUBBOOT_IsBootDeviceExternal(a1) )
      {
        v15 = HUBBOOT_RegisterBootDevice(*(_QWORD *)(v7 + 24), *(_QWORD *)(v7 + 24) + 2240LL);
        v16 = *(unsigned int *)(*(_QWORD *)(v7 + 24) + 1640LL);
        if ( (v16 & 2) == 0 )
          WMI_RegisterSurpriseRemovalNotificationInstance(a1);
        if ( v15 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                    WdfDriverGlobals,
                    WdfDriverGlobals->Driver,
                    off_14006B2C0);
            LOBYTE(v18) = 2;
            WPP_RECORDER_SF_d(
              *(_QWORD *)(v17 + 64),
              v18,
              2,
              156,
              (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
              v15);
          }
          HUBMISC_DbgBreak("ExRegisterBootDevice Failed", v16);
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                WdfDriverGlobals,
                WdfDriverGlobals->Driver,
                off_14006B2C0);
        LOBYTE(v20) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(v19 + 64), v20, 2, 157, (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
      }
      _InterlockedOr((volatile signed __int32 *)(v7 + 32), 0x20u);
      _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1336LL), 2u);
    }
    goto LABEL_28;
  }
  ForwardProgressResources = -1073741810;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(v13 + 1432),
      v12,
      5,
      155,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
      14);
  }
  return ForwardProgressResources;
}

```

## disassembly

```asm
0x140015eb0  push    rbx
0x140015eb2  push    rbp
0x140015eb3  push    rsi
0x140015eb4  push    rdi
0x140015eb5  push    r14
0x140015eb7  push    r15
0x140015eb9  sub     rsp, 38h
0x140015ebd  mov     edi, edx
0x140015ebf  mov     rbp, rcx
0x140015ec2  lea     rdx, Path; "MiniNT"
0x140015ec9  mov     ecx, 2; RelativeTo
0x140015ece  mov     r15b, r8b
0x140015ed1  call    cs:__imp_RtlCheckRegistryKey
0x140015ed8  nop     dword ptr [rax+rax+00h]
0x140015edd  mov     r8, cs:WdfFunctions_01015
0x140015ee4  mov     rdx, rbp
0x140015ee7  mov     rcx, cs:WdfDriverGlobals
0x140015eee  mov     r14d, eax
0x140015ef1  shr     r14d, 1Fh
0x140015ef5  xor     r14b, 1
0x140015ef9  mov     rax, [r8+650h]
0x140015f00  mov     r8, cs:off_14006B1D0
0x140015f07  call    _guard_dispatch_icall
0x140015f0c  mov     rbx, rax
0x140015f0f  xor     esi, esi
0x140015f11  mov     rax, [rax+18h]
0x140015f15  mov     ecx, [rax+670h]
0x140015f1b  test    cl, 10h
0x140015f1e  jnz     short loc_140015F31
0x140015f20  lock or dword ptr [rax+670h], 10h
0x140015f28  mov     rcx, [rbx+18h]
0x140015f2c  call    HUBREG_UpdateSqmFlags
0x140015f31  sub     edi, 1
0x140015f34  jz      loc_140015FD8
0x140015f3a  sub     edi, 1
0x140015f3d  jz      loc_140015FCA
0x140015f43  cmp     edi, 2
0x140015f46  jnz     loc_140016141
0x140015f4c  mov     eax, [rbx+20h]
0x140015f4f  test    al, 20h
0x140015f51  jnz     loc_140016141
0x140015f57  mov     rcx, [rbx+18h]
0x140015f5b  call    HUBPDO_AllocateForwardProgressResources
0x140015f60  mov     esi, eax
0x140015f62  test    eax, eax
0x140015f64  js      loc_140016141
0x140015f6a  mov     rcx, [rbx+18h]
0x140015f6e  mov     r10, [rcx+8]
0x140015f72  mov     ecx, [r10+538h]
0x140015f79  test    cl, 1
0x140015f7c  jnz     loc_140016006
0x140015f82  mov     esi, 0C000000Eh
0x140015f87  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140015f8e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015f95  jz      loc_140016141
0x140015f9b  mov     rcx, [r10+598h]
0x140015fa2  lea     r8, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140015fa9  mov     [rsp+68h+var_40], esi
0x140015fad  mov     r9d, 9Bh
0x140015fb3  mov     [rsp+68h+var_48], r8
0x140015fb8  mov     dl, 2
0x140015fba  mov     r8d, 5
0x140015fc0  call    WPP_RECORDER_SF_d
0x140015fc5  jmp     loc_140016141
0x140015fca  test    r15b, r15b
0x140015fcd  jz      loc_140016141
0x140015fd3  jmp     loc_140016127
0x140015fd8  mov     rcx, rbp
0x140015fdb  call    HUBBOOT_IsBootDeviceExternal
0x140015fe0  test    r14b, r14b
0x140015fe3  jnz     loc_140015F4C
0x140015fe9  test    al, al
0x140015feb  jz      loc_140015F4C
0x140015ff1  mov     eax, [rbx+20h]
0x140015ff4  test    al, 20h
0x140015ff6  jnz     loc_140015F4C
0x140015ffc  mov     esi, 0C00000BBh
0x140016001  jmp     loc_140016141
0x140016006  test    r14b, r14b
0x140016009  jnz     loc_140016127
0x14001600f  mov     rcx, rbp
0x140016012  call    HUBBOOT_IsBootDeviceExternal
0x140016017  test    al, al
0x140016019  jz      loc_1400160BA
0x14001601f  mov     rcx, [rbx+18h]
0x140016023  lea     rdx, [rcx+8C0h]
0x14001602a  call    HUBBOOT_RegisterBootDevice
0x14001602f  mov     rcx, [rbx+18h]
0x140016033  mov     edi, eax
0x140016035  mov     edx, [rcx+668h]
0x14001603b  test    dl, 2
0x14001603e  jnz     short loc_140016048
0x140016040  mov     rcx, rbp
0x140016043  call    WMI_RegisterSurpriseRemovalNotificationInstance
0x140016048  test    edi, edi
0x14001604a  jns     loc_140016112
0x140016050  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140016057  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001605e  jz      short loc_1400160AC
0x140016060  mov     rax, cs:WdfFunctions_01015
0x140016067  mov     rcx, cs:WdfDriverGlobals
0x14001606e  mov     r8, cs:off_14006B2C0
0x140016075  mov     rax, [rax+650h]
0x14001607c  mov     rdx, [rcx]
0x14001607f  call    _guard_dispatch_icall
0x140016084  lea     r8, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001608b  mov     [rsp+68h+var_40], edi
0x14001608f  mov     [rsp+68h+var_48], r8
0x140016094  mov     r9d, 9Ch
0x14001609a  mov     r8d, 2
0x1400160a0  mov     rcx, [rax+40h]
0x1400160a4  mov     dl, r8b
0x1400160a7  call    WPP_RECORDER_SF_d
0x1400160ac  lea     rcx, aExregisterboot; "ExRegisterBootDevice Failed"
0x1400160b3  call    HUBMISC_DbgBreak
0x1400160b8  jmp     short loc_140016112
0x1400160ba  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400160c1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400160c8  jz      short loc_140016112
0x1400160ca  mov     rax, cs:WdfFunctions_01015
0x1400160d1  mov     rcx, cs:WdfDriverGlobals
0x1400160d8  mov     r8, cs:off_14006B2C0
0x1400160df  mov     rax, [rax+650h]
0x1400160e6  mov     rdx, [rcx]
0x1400160e9  call    _guard_dispatch_icall
0x1400160ee  lea     r8, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400160f5  mov     r9d, 9Dh
0x1400160fb  mov     [rsp+68h+var_48], r8
0x140016100  mov     r8d, 2
0x140016106  mov     dl, r8b
0x140016109  mov     rcx, [rax+40h]
0x14001610d  call    WPP_RECORDER_SF_
0x140016112  lock or dword ptr [rbx+20h], 20h
0x140016117  mov     rax, [rbx+18h]
0x14001611b  mov     rcx, [rax+8]
0x14001611f  lock or dword ptr [rcx+538h], 2
0x140016127  mov     rax, [rbx+18h]
0x14001612b  mov     byte ptr [rax+5F0h], 1
0x140016132  mov     rax, [rbx+18h]
0x140016136  mov     rcx, [rax+8]
0x14001613a  mov     byte ptr [rcx+500h], 1
0x140016141  mov     eax, esi
0x140016143  add     rsp, 38h
0x140016147  pop     r15
0x140016149  pop     r14
0x14001614b  pop     rdi
0x14001614c  pop     rsi
0x14001614d  pop     rbp
0x14001614e  pop     rbx
0x14001614f  retn
```
