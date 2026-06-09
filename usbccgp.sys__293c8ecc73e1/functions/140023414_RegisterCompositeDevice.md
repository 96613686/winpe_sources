# RegisterCompositeDevice

- ea: `0x140023414`
- end: `0x140023582`
- name: `RegisterCompositeDevice`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140028f7c`

## callees

- `0x14000a6cc`
- `0x14000f1e8`
- `0x140023414`
- `0x140029b50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002355d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002355d`
- `ntoskrnl!IoFreeIrp` at `0x14002356c`
- `ntoskrnl!IoFreeIrp` at `0x14002356c`
- `ntoskrnl!IoAllocateIrp` at `0x140023457`
- `ntoskrnl!IoAllocateIrp` at `0x140023457`
- `ntoskrnl!ExAllocatePool2` at `0x1400234c6`
- `ntoskrnl!ExAllocatePool2` at `0x1400234c6`

## pseudocode

```c
void __fastcall RegisterCompositeDevice(__int64 a1)
{
  char v1; // dl
  ULONG v2; // r8d
  USBD_HANDLE v4; // rcx
  PIRP Irp; // rax
  int v6; // edx
  IRP *v7; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  int v9; // edx
  _IRP *Pool2; // rdi
  _REGISTER_COMPOSITE_DEVICE v11; // [rsp+30h] [rbp-48h] BYREF

  v1 = *(_BYTE *)(a1 + 1362);
  v2 = *(_DWORD *)(a1 + 116);
  v4 = *(USBD_HANDLE *)(a1 + 1344);
  memset(&v11, 0, sizeof(v11));
  USBD_BuildRegisterCompositeDevice(v4, (COMPOSITE_DEVICE_CAPABILITIES)(v1 & 1), v2, &v11);
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 40) + 76LL), 0);
  v7 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    Pool2 = (_IRP *)ExAllocatePool2(64, (unsigned int)(8 * *(_DWORD *)(a1 + 116)), 1130525525);
    if ( Pool2 )
    {
      CurrentStackLocation[-1].MajorFunction = 15;
      CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)&v11;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4784131;
      v7->AssociatedIrp.MasterIrp = Pool2;
      if ( (int)CallDriverSync(*(PDEVICE_OBJECT *)(a1 + 40), v7, 0, *(struct _DEVICE_OBJECT **)(a1 + 32)) < 0 )
      {
        ExFreePoolWithTag(Pool2, 0x43627355u);
      }
      else
      {
        *(_BYTE *)(a1 + 1361) = 1;
        *(_QWORD *)(a1 + 1352) = Pool2;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v9,
        8,
        75,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        154);
    }
    IoFreeIrp(v7);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 1368), v6, 8, 74, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids, 154);
  }
}

```

## disassembly

```asm
0x140023414  push    rbx
0x140023416  push    rbp
0x140023417  push    rsi
0x140023418  push    rdi
0x140023419  sub     rsp, 58h
0x14002341d  movzx   edx, byte ptr [rcx+552h]
0x140023424  lea     r9, [rsp+78h+var_48]; RegisterCompositeDevice
0x140023429  mov     r8d, [rcx+74h]; FunctionCount
0x14002342d  xor     eax, eax
0x14002342f  mov     rbx, rcx
0x140023432  mov     qword ptr [rsp+78h+var_48.CapabilityFlags.CapabilityFunctionSuspend], rax
0x140023437  mov     rcx, [rcx+540h]; USBDHandle
0x14002343e  xorps   xmm0, xmm0
0x140023441  and     edx, 1; CapabilityFlags
0x140023444  movups  xmmword ptr [rsp+78h+var_48.Version], xmm0
0x140023449  call    USBD_BuildRegisterCompositeDevice
0x14002344e  mov     rcx, [rbx+28h]
0x140023452  xor     edx, edx; ChargeQuota
0x140023454  mov     cl, [rcx+4Ch]; StackSize
0x140023457  call    cs:__imp_IoAllocateIrp
0x14002345e  nop     dword ptr [rax+rax+00h]
0x140023463  mov     rsi, rax
0x140023466  test    rax, rax
0x140023469  jnz     short loc_1400234AE
0x14002346b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023472  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023479  jz      loc_140023578
0x14002347f  mov     rcx, [rbx+558h]
0x140023486  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002348d  lea     r9d, [rsi+4Ah]
0x140023491  mov     [rsp+78h+var_50], 0C000009Ah
0x140023499  lea     r8d, [rsi+8]
0x14002349d  mov     [rsp+78h+var_58], rax
0x1400234a2  mov     dl, 2
0x1400234a4  call    WPP_RECORDER_SF_d
0x1400234a9  jmp     loc_140023578
0x1400234ae  mov     edx, [rbx+74h]
0x1400234b1  mov     ecx, 40h ; '@'
0x1400234b6  mov     rbp, [rax+0B8h]
0x1400234bd  mov     r8d, 43627355h
0x1400234c3  shl     edx, 3
0x1400234c6  call    cs:__imp_ExAllocatePool2
0x1400234cd  nop     dword ptr [rax+rax+00h]
0x1400234d2  mov     rdi, rax
0x1400234d5  test    rax, rax
0x1400234d8  jnz     short loc_140023516
0x1400234da  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400234e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400234e8  jz      short loc_140023569
0x1400234ea  mov     rcx, [rbx+558h]
0x1400234f1  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x1400234f8  lea     r9d, [rdi+4Bh]
0x1400234fc  mov     [rsp+78h+var_50], 0C000009Ah
0x140023504  lea     r8d, [rdi+8]
0x140023508  mov     [rsp+78h+var_58], rax
0x14002350d  mov     dl, 2
0x14002350f  call    WPP_RECORDER_SF_d
0x140023514  jmp     short loc_140023569
0x140023516  mov     byte ptr [rbp-48h], 0Fh
0x14002351a  lea     rax, [rsp+78h+var_48]
0x14002351f  mov     [rbp-40h], rax
0x140023523  xor     r8d, r8d
0x140023526  mov     dword ptr [rbp-30h], 490003h
0x14002352d  mov     rdx, rsi; Irp
0x140023530  mov     [rsi+18h], rdi
0x140023534  mov     r9, [rbx+20h]
0x140023538  mov     rcx, [rbx+28h]; DeviceObject
0x14002353c  call    CallDriverSync
0x140023541  test    eax, eax
0x140023543  js      short loc_140023555
0x140023545  mov     byte ptr [rbx+551h], 1
0x14002354c  mov     [rbx+548h], rdi
0x140023553  jmp     short loc_140023569
0x140023555  mov     edx, 43627355h; Tag
0x14002355a  mov     rcx, rdi; P
0x14002355d  call    cs:__imp_ExFreePoolWithTag
0x140023564  nop     dword ptr [rax+rax+00h]
0x140023569  mov     rcx, rsi; Irp
0x14002356c  call    cs:__imp_IoFreeIrp
0x140023573  nop     dword ptr [rax+rax+00h]
0x140023578  add     rsp, 58h
0x14002357c  pop     rdi
0x14002357d  pop     rsi
0x14002357e  pop     rbp
0x14002357f  pop     rbx
0x140023580  retn
```
