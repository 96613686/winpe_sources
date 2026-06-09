# TUNNEL_ReleaseUsb4HostPowerReference

- ea: `0x140091598`
- end: `0x14009174a`
- name: `TUNNEL_ReleaseUsb4HostPowerReference`
- size: `434`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140091750`

## callees

- `0x1400072b0`
- `0x1400419b0`
- `0x140045570`
- `0x140091598`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14009170f`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14009170f`
- `ntoskrnl!PoFxRemoveComponentRelation` at `0x1400915f6`
- `ntoskrnl!PoFxRemoveComponentRelation` at `0x1400915f6`

## pseudocode

```c
__int64 __fastcall TUNNEL_ReleaseUsb4HostPowerReference(_QWORD *a1, __int64 a2)
{
  bool v4; // zf
  int v5; // eax
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  char v9; // si
  struct _DEVICE_OBJECT *v10; // rax

  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(a2 + 16),
    0);
  v4 = (*(_DWORD *)(a2 + 40))-- == 1;
  if ( v4 && *(_BYTE *)(a2 + 44) == 1 )
  {
    v5 = PoFxRemoveComponentRelation(a1[328], 0, *(_QWORD *)(a2 + 32), &GUID_NULL);
    v9 = v5;
    if ( v5 >= 0 )
    {
      if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
        McTemplateK0ppq_EtwWriteTransfer(
          v7,
          (unsigned int)USBHUB3_ETW_EVENT_HUB_REMOVED_COMPONENT_RELATION,
          v8,
          a1[31],
          *(_QWORD *)(a2 + 32),
          v5);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 4;
        WPP_RECORDER_SF_qd(
          a1[317],
          v6,
          3,
          42,
          (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids,
          *(_QWORD *)(a2 + 32),
          v9);
      }
      *(_BYTE *)(a2 + 44) = 0;
      v10 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 264))(
                                       WdfDriverGlobals,
                                       a1[2]);
      IoInvalidateDeviceRelations(v10, PowerRelations);
    }
    else
    {
      if ( (byte_14006ED43 & 0x40) != 0 )
        McTemplateK0ppq_EtwWriteTransfer(
          *(_QWORD *)(a2 + 32),
          (unsigned int)USBHUB3_ETW_EVENT_HUB_REMOVE_COMPONENT_RELATION_FAILURE,
          v8,
          a1[31],
          *(_QWORD *)(a2 + 32),
          v5);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_qd(
          a1[317],
          v6,
          3,
          41,
          (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids,
          *(_QWORD *)(a2 + 32),
          v9);
      }
    }
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
           WdfDriverGlobals,
           *(_QWORD *)(a2 + 16));
}

```

## disassembly

```asm
0x140091598  mov     [rsp+arg_0], rbx
0x14009159d  mov     [rsp+arg_10], rsi
0x1400915a2  push    rdi
0x1400915a3  sub     rsp, 40h
0x1400915a7  mov     rax, cs:WdfFunctions_01015
0x1400915ae  mov     rbx, rdx
0x1400915b1  mov     rdx, [rdx+10h]
0x1400915b5  mov     rdi, rcx
0x1400915b8  mov     rcx, cs:WdfDriverGlobals
0x1400915bf  xor     r8d, r8d
0x1400915c2  mov     rax, [rax+9C8h]
0x1400915c9  call    _guard_dispatch_icall
0x1400915ce  add     dword ptr [rbx+28h], 0FFFFFFFFh
0x1400915d2  jnz     loc_14009171B
0x1400915d8  cmp     byte ptr [rbx+2Ch], 1
0x1400915dc  jnz     loc_14009171B
0x1400915e2  mov     r8, [rbx+20h]
0x1400915e6  lea     r9, GUID_NULL
0x1400915ed  mov     rcx, [rdi+0A40h]
0x1400915f4  xor     edx, edx
0x1400915f6  call    cs:__imp_PoFxRemoveComponentRelation
0x1400915fd  nop     dword ptr [rax+rax+00h]
0x140091602  mov     esi, eax
0x140091604  test    eax, eax
0x140091606  jns     short loc_14009167B
0x140091608  test    cs:byte_14006ED43, 40h
0x14009160f  jz      short loc_140091631
0x140091611  mov     rcx, [rbx+20h]
0x140091615  lea     rdx, USBHUB3_ETW_EVENT_HUB_REMOVE_COMPONENT_RELATION_FAILURE
0x14009161c  mov     r9, [rdi+0F8h]
0x140091623  mov     dword ptr [rsp+48h+var_20], eax
0x140091627  mov     [rsp+48h+var_28], rcx
0x14009162c  call    McTemplateK0ppq_EtwWriteTransfer
0x140091631  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140091638  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009163f  jz      loc_14009171B
0x140091645  mov     rax, [rbx+20h]
0x140091649  mov     r9d, 29h ; ')'
0x14009164f  mov     rcx, [rdi+9E8h]
0x140091656  mov     dl, 2
0x140091658  mov     [rsp+48h+var_18], esi
0x14009165c  mov     [rsp+48h+var_20], rax
0x140091661  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x140091668  lea     r8d, [r9-26h]
0x14009166c  mov     [rsp+48h+var_28], rax
0x140091671  call    WPP_RECORDER_SF_qd
0x140091676  jmp     loc_14009171B
0x14009167b  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x140091682  jz      short loc_1400916A4
0x140091684  mov     rax, [rbx+20h]
0x140091688  lea     rdx, USBHUB3_ETW_EVENT_HUB_REMOVED_COMPONENT_RELATION
0x14009168f  mov     r9, [rdi+0F8h]
0x140091696  mov     dword ptr [rsp+48h+var_20], esi
0x14009169a  mov     [rsp+48h+var_28], rax
0x14009169f  call    McTemplateK0ppq_EtwWriteTransfer
0x1400916a4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400916ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400916b2  jz      short loc_1400916E5
0x1400916b4  mov     rax, [rbx+20h]
0x1400916b8  mov     r9d, 2Ah ; '*'
0x1400916be  mov     rcx, [rdi+9E8h]
0x1400916c5  mov     dl, 4
0x1400916c7  mov     [rsp+48h+var_18], esi
0x1400916cb  mov     [rsp+48h+var_20], rax
0x1400916d0  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x1400916d7  lea     r8d, [r9-27h]
0x1400916db  mov     [rsp+48h+var_28], rax
0x1400916e0  call    WPP_RECORDER_SF_qd
0x1400916e5  mov     byte ptr [rbx+2Ch], 0
0x1400916e9  mov     rax, cs:WdfFunctions_01015
0x1400916f0  mov     rdx, [rdi+10h]
0x1400916f4  mov     rcx, cs:WdfDriverGlobals
0x1400916fb  mov     rax, [rax+108h]
0x140091702  call    _guard_dispatch_icall
0x140091707  mov     edx, 2; Type
0x14009170c  mov     rcx, rax; DeviceObject
0x14009170f  call    cs:__imp_IoInvalidateDeviceRelations
0x140091716  nop     dword ptr [rax+rax+00h]
0x14009171b  mov     rax, cs:WdfFunctions_01015
0x140091722  mov     rdx, [rbx+10h]
0x140091726  mov     rcx, cs:WdfDriverGlobals
0x14009172d  mov     rax, [rax+9D0h]
0x140091734  call    _guard_dispatch_icall
0x140091739  mov     rbx, [rsp+48h+arg_0]
0x14009173e  mov     rsi, [rsp+48h+arg_10]
0x140091743  add     rsp, 40h
0x140091747  pop     rdi
0x140091748  retn
```
