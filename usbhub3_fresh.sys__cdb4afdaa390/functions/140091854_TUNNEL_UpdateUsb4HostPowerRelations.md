# TUNNEL_UpdateUsb4HostPowerRelations

- ea: `0x140091854`
- end: `0x140091a06`
- name: `TUNNEL_UpdateUsb4HostPowerRelations`
- size: `434`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140090ae0`

## callees

- `0x1400072b0`
- `0x1400419b0`
- `0x140045570`
- `0x140091854`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400919cb`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400919cb`
- `ntoskrnl!PoFxAddComponentRelation` at `0x1400918b2`
- `ntoskrnl!PoFxAddComponentRelation` at `0x1400918b2`

## pseudocode

```c
__int64 __fastcall TUNNEL_UpdateUsb4HostPowerRelations(_QWORD *a1, __int64 a2)
{
  int v4; // eax
  int v5; // edx
  int v6; // ecx
  int v7; // r8d
  char v8; // si
  struct _DEVICE_OBJECT *v9; // rax

  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(a2 + 16),
    0);
  if ( !*(_DWORD *)(a2 + 40) || *(_BYTE *)(a2 + 44) )
  {
LABEL_13:
    v9 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 264))(
                                    WdfDriverGlobals,
                                    a1[2]);
    IoInvalidateDeviceRelations(v9, PowerRelations);
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
             WdfDriverGlobals,
             *(_QWORD *)(a2 + 16));
  }
  v4 = PoFxAddComponentRelation(a1[328], 0, *(_QWORD *)(a2 + 32), &GUID_NULL);
  v8 = v4;
  if ( v4 >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_qd(
        a1[317],
        v5,
        3,
        38,
        (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids,
        *(_QWORD *)(a2 + 32),
        v4);
    }
    if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
      McTemplateK0ppq_EtwWriteTransfer(
        v6,
        (unsigned int)USBHUB3_ETW_EVENT_HUB_ADDED_COMPONENT_RELATION,
        v7,
        a1[31],
        *(_QWORD *)(a2 + 32),
        v8);
    *(_BYTE *)(a2 + 44) = 1;
    goto LABEL_13;
  }
  if ( (byte_14006ED43 & 0x40) != 0 )
    McTemplateK0ppq_EtwWriteTransfer(
      *(_QWORD *)(a2 + 32),
      (unsigned int)USBHUB3_ETW_EVENT_HUB_ADD_COMPONENT_RELATION_FAILURE,
      v7,
      a1[31],
      *(_QWORD *)(a2 + 32),
      v4);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_qd(
      a1[317],
      v5,
      3,
      37,
      (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids,
      *(_QWORD *)(a2 + 32),
      v8);
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
           WdfDriverGlobals,
           *(_QWORD *)(a2 + 16));
}

```

## disassembly

```asm
0x140091854  mov     [rsp+arg_0], rbx
0x140091859  mov     [rsp+arg_8], rsi
0x14009185e  push    rdi
0x14009185f  sub     rsp, 40h
0x140091863  mov     rax, cs:WdfFunctions_01015
0x14009186a  mov     rbx, rdx
0x14009186d  mov     rdx, [rdx+10h]
0x140091871  mov     rdi, rcx
0x140091874  mov     rcx, cs:WdfDriverGlobals
0x14009187b  xor     r8d, r8d
0x14009187e  mov     rax, [rax+9C8h]
0x140091885  call    _guard_dispatch_icall
0x14009188a  cmp     dword ptr [rbx+28h], 0
0x14009188e  jz      loc_1400919A5
0x140091894  cmp     byte ptr [rbx+2Ch], 0
0x140091898  jnz     loc_1400919A5
0x14009189e  mov     r8, [rbx+20h]
0x1400918a2  lea     r9, GUID_NULL
0x1400918a9  mov     rcx, [rdi+0A40h]
0x1400918b0  xor     edx, edx
0x1400918b2  call    cs:__imp_PoFxAddComponentRelation
0x1400918b9  nop     dword ptr [rax+rax+00h]
0x1400918be  mov     esi, eax
0x1400918c0  test    eax, eax
0x1400918c2  jns     short loc_140091937
0x1400918c4  test    cs:byte_14006ED43, 40h
0x1400918cb  jz      short loc_1400918ED
0x1400918cd  mov     rcx, [rbx+20h]
0x1400918d1  lea     rdx, USBHUB3_ETW_EVENT_HUB_ADD_COMPONENT_RELATION_FAILURE
0x1400918d8  mov     r9, [rdi+0F8h]
0x1400918df  mov     dword ptr [rsp+48h+var_20], eax
0x1400918e3  mov     [rsp+48h+var_28], rcx
0x1400918e8  call    McTemplateK0ppq_EtwWriteTransfer
0x1400918ed  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400918f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400918fb  jz      loc_1400919D7
0x140091901  mov     rax, [rbx+20h]
0x140091905  mov     r9d, 25h ; '%'
0x14009190b  mov     rcx, [rdi+9E8h]
0x140091912  mov     dl, 2
0x140091914  mov     [rsp+48h+var_18], esi
0x140091918  mov     [rsp+48h+var_20], rax
0x14009191d  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x140091924  lea     r8d, [r9-22h]
0x140091928  mov     [rsp+48h+var_28], rax
0x14009192d  call    WPP_RECORDER_SF_qd
0x140091932  jmp     loc_1400919D7
0x140091937  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009193e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140091945  jz      short loc_140091978
0x140091947  mov     rax, [rbx+20h]
0x14009194b  mov     r9d, 26h ; '&'
0x140091951  mov     rcx, [rdi+9E8h]
0x140091958  mov     dl, 4
0x14009195a  mov     [rsp+48h+var_18], esi
0x14009195e  mov     [rsp+48h+var_20], rax
0x140091963  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x14009196a  lea     r8d, [r9-23h]
0x14009196e  mov     [rsp+48h+var_28], rax
0x140091973  call    WPP_RECORDER_SF_qd
0x140091978  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x14009197f  jz      short loc_1400919A1
0x140091981  mov     rax, [rbx+20h]
0x140091985  lea     rdx, USBHUB3_ETW_EVENT_HUB_ADDED_COMPONENT_RELATION
0x14009198c  mov     r9, [rdi+0F8h]
0x140091993  mov     dword ptr [rsp+48h+var_20], esi
0x140091997  mov     [rsp+48h+var_28], rax
0x14009199c  call    McTemplateK0ppq_EtwWriteTransfer
0x1400919a1  mov     byte ptr [rbx+2Ch], 1
0x1400919a5  mov     rax, cs:WdfFunctions_01015
0x1400919ac  mov     rdx, [rdi+10h]
0x1400919b0  mov     rcx, cs:WdfDriverGlobals
0x1400919b7  mov     rax, [rax+108h]
0x1400919be  call    _guard_dispatch_icall
0x1400919c3  mov     edx, 2; Type
0x1400919c8  mov     rcx, rax; DeviceObject
0x1400919cb  call    cs:__imp_IoInvalidateDeviceRelations
0x1400919d2  nop     dword ptr [rax+rax+00h]
0x1400919d7  mov     rax, cs:WdfFunctions_01015
0x1400919de  mov     rdx, [rbx+10h]
0x1400919e2  mov     rcx, cs:WdfDriverGlobals
0x1400919e9  mov     rax, [rax+9D0h]
0x1400919f0  call    _guard_dispatch_icall
0x1400919f5  mov     rbx, [rsp+48h+arg_0]
0x1400919fa  mov     rsi, [rsp+48h+arg_8]
0x1400919ff  add     rsp, 40h
0x140091a03  pop     rdi
0x140091a04  retn
```
