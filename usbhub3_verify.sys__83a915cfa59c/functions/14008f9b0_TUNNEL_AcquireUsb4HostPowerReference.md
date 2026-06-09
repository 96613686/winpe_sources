# TUNNEL_AcquireUsb4HostPowerReference

- ea: `0x14008f9b0`
- end: `0x14008fb6b`
- name: `TUNNEL_AcquireUsb4HostPowerReference`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14008fb74`

## callees

- `0x1400072b0`
- `0x1400419b0`
- `0x140045570`
- `0x14008f9b0`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14008fb30`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14008fb30`
- `ntoskrnl!PoFxAddComponentRelation` at `0x14008fa17`
- `ntoskrnl!PoFxAddComponentRelation` at `0x14008fa17`

## pseudocode

```c
__int64 __fastcall TUNNEL_AcquireUsb4HostPowerReference(_QWORD *a1, __int64 a2)
{
  int v4; // r8d
  __int64 v5; // r8
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  char v10; // si
  struct _DEVICE_OBJECT *v11; // rax

  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(a2 + 16),
    0);
  v4 = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a2 + 40) = v4 + 1;
  if ( !v4 )
  {
    v5 = *(_QWORD *)(a2 + 32);
    if ( v5 )
    {
      v6 = PoFxAddComponentRelation(a1[328], 0, v5, &GUID_NULL);
      v10 = v6;
      if ( v6 >= 0 )
      {
        if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 4) != 0 )
          McTemplateK0ppq_EtwWriteTransfer(
            v8,
            (unsigned int)USBHUB3_ETW_EVENT_HUB_ADDED_COMPONENT_RELATION,
            v9,
            a1[31],
            *(_QWORD *)(a2 + 32),
            v6);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = 4;
          WPP_RECORDER_SF_qd(
            a1[317],
            v7,
            3,
            40,
            (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids,
            *(_QWORD *)(a2 + 32),
            v10);
        }
        *(_BYTE *)(a2 + 44) = 1;
        v11 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 264))(
                                         WdfDriverGlobals,
                                         a1[2]);
        IoInvalidateDeviceRelations(v11, PowerRelations);
      }
      else
      {
        if ( (byte_14006ED43 & 0x40) != 0 )
          McTemplateK0ppq_EtwWriteTransfer(
            *(_QWORD *)(a2 + 32),
            (unsigned int)USBHUB3_ETW_EVENT_HUB_ADD_COMPONENT_RELATION_FAILURE,
            v9,
            a1[31],
            *(_QWORD *)(a2 + 32),
            v6);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = 2;
          WPP_RECORDER_SF_qd(
            a1[317],
            v7,
            3,
            39,
            (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids,
            *(_QWORD *)(a2 + 32),
            v10);
        }
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
0x14008f9b0  mov     [rsp+arg_0], rbx
0x14008f9b5  mov     [rsp+arg_8], rsi
0x14008f9ba  push    rdi
0x14008f9bb  sub     rsp, 40h
0x14008f9bf  mov     rax, cs:WdfFunctions_01015
0x14008f9c6  mov     rbx, rdx
0x14008f9c9  mov     rdx, [rdx+10h]
0x14008f9cd  mov     rdi, rcx
0x14008f9d0  mov     rcx, cs:WdfDriverGlobals
0x14008f9d7  xor     r8d, r8d
0x14008f9da  mov     rax, [rax+9C8h]
0x14008f9e1  call    _guard_dispatch_icall
0x14008f9e6  mov     r8d, [rbx+28h]
0x14008f9ea  lea     eax, [r8+1]
0x14008f9ee  mov     [rbx+28h], eax
0x14008f9f1  test    r8d, r8d
0x14008f9f4  jnz     loc_14008FB3C
0x14008f9fa  mov     r8, [rbx+20h]
0x14008f9fe  test    r8, r8
0x14008fa01  jz      loc_14008FB3C
0x14008fa07  mov     rcx, [rdi+0A40h]
0x14008fa0e  lea     r9, GUID_NULL
0x14008fa15  xor     edx, edx
0x14008fa17  call    cs:__imp_PoFxAddComponentRelation
0x14008fa1e  nop     dword ptr [rax+rax+00h]
0x14008fa23  mov     esi, eax
0x14008fa25  test    eax, eax
0x14008fa27  jns     short loc_14008FA9C
0x14008fa29  test    cs:byte_14006ED43, 40h
0x14008fa30  jz      short loc_14008FA52
0x14008fa32  mov     rcx, [rbx+20h]
0x14008fa36  lea     rdx, USBHUB3_ETW_EVENT_HUB_ADD_COMPONENT_RELATION_FAILURE
0x14008fa3d  mov     r9, [rdi+0F8h]
0x14008fa44  mov     dword ptr [rsp+48h+var_20], eax
0x14008fa48  mov     [rsp+48h+var_28], rcx
0x14008fa4d  call    McTemplateK0ppq_EtwWriteTransfer
0x14008fa52  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008fa59  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008fa60  jz      loc_14008FB3C
0x14008fa66  mov     rax, [rbx+20h]
0x14008fa6a  mov     r9d, 27h ; '''
0x14008fa70  mov     rcx, [rdi+9E8h]
0x14008fa77  mov     dl, 2
0x14008fa79  mov     [rsp+48h+var_18], esi
0x14008fa7d  mov     [rsp+48h+var_20], rax
0x14008fa82  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x14008fa89  lea     r8d, [r9-24h]
0x14008fa8d  mov     [rsp+48h+var_28], rax
0x14008fa92  call    WPP_RECORDER_SF_qd
0x14008fa97  jmp     loc_14008FB3C
0x14008fa9c  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 4
0x14008faa3  jz      short loc_14008FAC5
0x14008faa5  mov     rax, [rbx+20h]
0x14008faa9  lea     rdx, USBHUB3_ETW_EVENT_HUB_ADDED_COMPONENT_RELATION
0x14008fab0  mov     r9, [rdi+0F8h]
0x14008fab7  mov     dword ptr [rsp+48h+var_20], esi
0x14008fabb  mov     [rsp+48h+var_28], rax
0x14008fac0  call    McTemplateK0ppq_EtwWriteTransfer
0x14008fac5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008facc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008fad3  jz      short loc_14008FB06
0x14008fad5  mov     rax, [rbx+20h]
0x14008fad9  mov     r9d, 28h ; '('
0x14008fadf  mov     rcx, [rdi+9E8h]
0x14008fae6  mov     dl, 4
0x14008fae8  mov     [rsp+48h+var_18], esi
0x14008faec  mov     [rsp+48h+var_20], rax
0x14008faf1  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x14008faf8  lea     r8d, [r9-25h]
0x14008fafc  mov     [rsp+48h+var_28], rax
0x14008fb01  call    WPP_RECORDER_SF_qd
0x14008fb06  mov     byte ptr [rbx+2Ch], 1
0x14008fb0a  mov     rax, cs:WdfFunctions_01015
0x14008fb11  mov     rdx, [rdi+10h]
0x14008fb15  mov     rcx, cs:WdfDriverGlobals
0x14008fb1c  mov     rax, [rax+108h]
0x14008fb23  call    _guard_dispatch_icall
0x14008fb28  mov     edx, 2; Type
0x14008fb2d  mov     rcx, rax; DeviceObject
0x14008fb30  call    cs:__imp_IoInvalidateDeviceRelations
0x14008fb37  nop     dword ptr [rax+rax+00h]
0x14008fb3c  mov     rax, cs:WdfFunctions_01015
0x14008fb43  mov     rdx, [rbx+10h]
0x14008fb47  mov     rcx, cs:WdfDriverGlobals
0x14008fb4e  mov     rax, [rax+9D0h]
0x14008fb55  call    _guard_dispatch_icall
0x14008fb5a  mov     rbx, [rsp+48h+arg_0]
0x14008fb5f  mov     rsi, [rsp+48h+arg_8]
0x14008fb64  add     rsp, 40h
0x14008fb68  pop     rdi
0x14008fb69  retn
```
