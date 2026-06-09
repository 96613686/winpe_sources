# HUBMISC_InstallMsOs20RegistryProperties

- ea: `0x14002fc38`
- end: `0x14002fe0b`
- name: `HUBMISC_InstallMsOs20RegistryProperties`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140022aa0`

## callees

- `0x1400024b8`
- `0x14002fc38`
- `0x140035764`
- `0x140045570`
- `0x14008b354`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002fcbe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002fcbe`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14002fdad`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14002fdad`

## pseudocode

```c
__int64 __fastcall HUBMISC_InstallMsOs20RegistryProperties(__int64 a1)
{
  __int64 v2; // rbp
  char NextMsOs20Descriptor; // r14
  __int64 v4; // rsi
  __int64 v5; // rbx
  int v6; // eax
  int v7; // edx
  __int64 v8; // rax
  struct _DEVICE_OBJECT *v9; // rax
  NTSTATUS v10; // eax
  int v11; // edx
  ULONG Sizea; // [rsp+28h] [rbp-50h]
  __int64 Size; // [rsp+28h] [rbp-50h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+80h] [rbp+8h] BYREF

  v16 = *(_QWORD *)(a1 + 2496);
  v2 = v16 + *(unsigned __int16 *)(v16 + 8);
  while ( 1 )
  {
    NextMsOs20Descriptor = HUBDESC_GetNextMsOs20Descriptor(v2, &v16);
    if ( !NextMsOs20Descriptor )
      break;
    v4 = v16;
    if ( !v16 )
      break;
    if ( *(_WORD *)(v16 + 2) == 4 )
    {
      DestinationString = 0;
      v5 = *(unsigned __int16 *)(v16 + 6);
      RtlInitUnicodeString(&DestinationString, (PCWSTR)(v16 + 8));
      v6 = HUBREG_WriteValueToDeviceHardwareKey(
             a1,
             (__int64)&DestinationString,
             *(unsigned __int16 *)(v4 + 4),
             *(unsigned __int16 *)(v5 + v4 + 8),
             v5 + v4 + 10);
      if ( v6 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          Sizea = v6;
          LOBYTE(v7) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
            v7,
            5,
            82,
            (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
            Sizea);
        }
        break;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 2472) & 0x100) != 0 )
  {
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(
           WdfDriverGlobals,
           *(_QWORD *)(a1 + 16));
    v9 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 264))(
                                    WdfDriverGlobals,
                                    v8);
    v10 = IoSetDevicePropertyData(v9, &DEVPKEY_Device_ModelId, 0, 0, 0xDu, 0x10u, (PVOID)(*(_QWORD *)(a1 + 2520) + 4LL));
    if ( v10 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(Size) = v10;
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v11,
        5,
        83,
        (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
        Size);
    }
  }
  return NextMsOs20Descriptor != 0 ? 4077 : 4065;
}

```

## disassembly

```asm
0x14002fc38  mov     r11, rsp
0x14002fc3b  mov     [r11+10h], rbx
0x14002fc3f  mov     [r11+18h], rbp
0x14002fc43  push    rsi
0x14002fc44  push    rdi
0x14002fc45  push    r13
0x14002fc47  push    r14
0x14002fc49  push    r15
0x14002fc4b  sub     rsp, 50h
0x14002fc4f  mov     rax, [rcx+9C0h]
0x14002fc56  mov     rdi, rcx
0x14002fc59  mov     [r11+8], rax
0x14002fc5d  mov     ebx, 4
0x14002fc62  movzx   ebp, word ptr [rax+8]
0x14002fc66  add     rbp, rax
0x14002fc69  lea     rdx, [rsp+78h+arg_0]
0x14002fc71  mov     rcx, rbp
0x14002fc74  call    HUBDESC_GetNextMsOs20Descriptor
0x14002fc79  lea     r13, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x14002fc80  mov     r14b, al
0x14002fc83  lea     r15, WPP_RECORDER_INITIALIZED
0x14002fc8a  test    al, al
0x14002fc8c  jz      loc_14002FD27
0x14002fc92  mov     rsi, [rsp+78h+arg_0]
0x14002fc9a  test    rsi, rsi
0x14002fc9d  jz      loc_14002FD27
0x14002fca3  cmp     [rsi+2], bx
0x14002fca7  jnz     short loc_14002FC69
0x14002fca9  xorps   xmm0, xmm0
0x14002fcac  lea     rdx, [rsi+8]; SourceString
0x14002fcb0  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x14002fcb5  movzx   ebx, word ptr [rsi+6]
0x14002fcb9  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14002fcbe  call    cs:__imp_RtlInitUnicodeString
0x14002fcc5  nop     dword ptr [rax+rax+00h]
0x14002fcca  movzx   r9d, word ptr [rbx+rsi+8]
0x14002fcd0  lea     rax, [rsi+0Ah]
0x14002fcd4  movzx   r8d, word ptr [rsi+4]
0x14002fcd9  lea     rdx, [rsp+78h+DestinationString]
0x14002fcde  add     rax, rbx
0x14002fce1  mov     rcx, rdi
0x14002fce4  mov     qword ptr [rsp+78h+Type], rax
0x14002fce9  call    HUBREG_WriteValueToDeviceHardwareKey
0x14002fcee  mov     ebx, 4
0x14002fcf3  test    eax, eax
0x14002fcf5  jns     loc_14002FC69
0x14002fcfb  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14002fd02  jz      short loc_14002FD27
0x14002fd04  mov     rcx, [rdi+8]
0x14002fd08  lea     r9d, [rbx+4Eh]
0x14002fd0c  mov     dword ptr [rsp+78h+Size], eax
0x14002fd10  lea     r8d, [rbx+1]
0x14002fd14  mov     dl, 2
0x14002fd16  mov     qword ptr [rsp+78h+Type], r13
0x14002fd1b  mov     rcx, [rcx+598h]
0x14002fd22  call    WPP_RECORDER_SF_d
0x14002fd27  neg     r14b
0x14002fd2a  sbb     ebx, ebx
0x14002fd2c  and     ebx, 0Ch
0x14002fd2f  test    dword ptr [rdi+9A8h], 100h
0x14002fd39  jz      loc_14002FDEB
0x14002fd3f  mov     rax, cs:WdfFunctions_01015
0x14002fd46  mov     rdx, [rdi+10h]
0x14002fd4a  mov     rcx, cs:WdfDriverGlobals
0x14002fd51  mov     rax, [rax+660h]
0x14002fd58  call    _guard_dispatch_icall
0x14002fd5d  mov     rcx, cs:WdfFunctions_01015
0x14002fd64  mov     rdx, rax
0x14002fd67  mov     r8, [rcx+108h]
0x14002fd6e  mov     rcx, cs:WdfDriverGlobals
0x14002fd75  mov     rax, r8
0x14002fd78  call    _guard_dispatch_icall
0x14002fd7d  mov     rcx, [rdi+9D8h]
0x14002fd84  lea     rdx, DEVPKEY_Device_ModelId; PropertyKey
0x14002fd8b  add     rcx, 4
0x14002fd8f  xor     r9d, r9d; Flags
0x14002fd92  mov     [rsp+78h+Data], rcx; Data
0x14002fd97  xor     r8d, r8d; Lcid
0x14002fd9a  mov     dword ptr [rsp+78h+Size], 10h; Size
0x14002fda2  mov     rcx, rax; Pdo
0x14002fda5  mov     [rsp+78h+Type], 0Dh; Type
0x14002fdad  call    cs:__imp_IoSetDevicePropertyData
0x14002fdb4  nop     dword ptr [rax+rax+00h]
0x14002fdb9  test    eax, eax
0x14002fdbb  jns     short loc_14002FDEB
0x14002fdbd  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14002fdc4  jz      short loc_14002FDEB
0x14002fdc6  mov     rcx, [rdi+8]
0x14002fdca  mov     r9d, 53h ; 'S'
0x14002fdd0  mov     dword ptr [rsp+78h+Size], eax
0x14002fdd4  mov     dl, 2
0x14002fdd6  mov     qword ptr [rsp+78h+Type], r13
0x14002fddb  mov     rcx, [rcx+598h]
0x14002fde2  lea     r8d, [r9-4Eh]
0x14002fde6  call    WPP_RECORDER_SF_d
0x14002fdeb  lea     r11, [rsp+78h+var_28]
0x14002fdf0  mov     rbp, [r11+40h]
0x14002fdf4  lea     eax, [rbx+0FE1h]
0x14002fdfa  mov     rbx, [r11+38h]
0x14002fdfe  mov     rsp, r11
0x14002fe01  pop     r15
0x14002fe03  pop     r14
0x14002fe05  pop     r13
0x14002fe07  pop     rdi
0x14002fe08  pop     rsi
0x14002fe09  retn
```
