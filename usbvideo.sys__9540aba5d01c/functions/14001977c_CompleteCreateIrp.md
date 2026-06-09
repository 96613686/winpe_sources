# CompleteCreateIrp

- ea: `0x14001977c`
- end: `0x140019847`
- name: `CompleteCreateIrp`
- size: `203`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013f40`
- `0x14003a7e0`

## callees

- `0x140006cc8`
- `0x140018990`
- `0x14001977c`
- `0x14001ab4c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001982f`
- `ntoskrnl!IofCompleteRequest` at `0x14001982f`
- `ks!KsGetDeviceForDeviceObject` at `0x1400197f8`
- `ks!KsGetDeviceForDeviceObject` at `0x1400197f8`

## pseudocode

```c
void __fastcall CompleteCreateIrp(PIRP Irp, int a2, int a3)
{
  struct _DEVICE_OBJECT *DeviceObject; // rdi
  int v5; // ecx
  PKSDEVICE DeviceForDeviceObject; // rax
  __int64 v7; // r8
  volatile signed __int32 *Context; // rcx

  DeviceObject = Irp->Tail.Overlay.CurrentStackLocation->DeviceObject;
  Irp->IoStatus.Information = 0;
  v5 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      44,
      WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
      Irp,
      Irp->IoStatus.Status);
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
    McTemplateK0ppq_EtwWriteTransfer(v5, a2, a3, 0, 0, Irp->IoStatus.Status);
  DeviceForDeviceObject = KsGetDeviceForDeviceObject(DeviceObject);
  if ( Irp->IoStatus.Status < 0 )
  {
    if ( DeviceForDeviceObject )
    {
      Context = (volatile signed __int32 *)DeviceForDeviceObject->Context;
      if ( Context )
      {
        _InterlockedDecrement(Context + 211);
        PowerDownDevice(DeviceForDeviceObject->Context, 0, v7);
      }
    }
  }
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x14001977c  mov     [rsp+arg_0], rbx
0x140019781  push    rdi
0x140019782  sub     rsp, 30h
0x140019786  mov     rax, [rcx+0B8h]
0x14001978d  mov     rbx, rcx
0x140019790  mov     rdi, [rax+28h]
0x140019794  mov     qword ptr [rcx+38h], 0
0x14001979c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400197a3  lea     rax, WPP_GLOBAL_Control
0x1400197aa  cmp     rcx, rax
0x1400197ad  jz      short loc_1400197D4
0x1400197af  cmp     byte ptr [rcx+29h], 5
0x1400197b3  jb      short loc_1400197D4
0x1400197b5  mov     eax, [rbx+30h]
0x1400197b8  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x1400197bf  mov     rcx, [rcx+18h]
0x1400197c3  mov     edx, 2Ch ; ','
0x1400197c8  mov     r9, rbx
0x1400197cb  mov     dword ptr [rsp+38h+var_18], eax
0x1400197cf  call    WPP_SF_qD
0x1400197d4  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x1400197db  jz      short loc_1400197F5
0x1400197dd  mov     eax, [rbx+30h]
0x1400197e0  xor     r9d, r9d
0x1400197e3  mov     [rsp+38h+var_10], eax
0x1400197e7  mov     [rsp+38h+var_18], 0
0x1400197f0  call    McTemplateK0ppq_EtwWriteTransfer
0x1400197f5  mov     rcx, rdi; FunctionalDeviceObject
0x1400197f8  call    cs:__imp_KsGetDeviceForDeviceObject
0x1400197ff  nop     dword ptr [rax+rax+00h]
0x140019804  cmp     dword ptr [rbx+30h], 0
0x140019808  jge     short loc_14001982A
0x14001980a  test    rax, rax
0x14001980d  jz      short loc_14001982A
0x14001980f  mov     rcx, [rax+10h]
0x140019813  test    rcx, rcx
0x140019816  jz      short loc_14001982A
0x140019818  lock dec dword ptr [rcx+34Ch]
0x14001981f  xor     edx, edx
0x140019821  mov     rcx, [rax+10h]; Context
0x140019825  call    PowerDownDevice
0x14001982a  xor     edx, edx; PriorityBoost
0x14001982c  mov     rcx, rbx; Irp
0x14001982f  call    cs:__imp_IofCompleteRequest
0x140019836  nop     dword ptr [rax+rax+00h]
0x14001983b  mov     rbx, [rsp+38h+arg_0]
0x140019840  add     rsp, 30h
0x140019844  pop     rdi
0x140019845  retn
```
