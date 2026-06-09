# FreeResourcesObjectBag_IfCreateFailure

- ea: `0x14001b218`
- end: `0x14001b2ed`
- name: `FreeResourcesObjectBag_IfCreateFailure`
- size: `213`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140013f40`
- `0x14003a7e0`

## callees

- `0x14001b218`
- `0x14003aebc`

## import_xrefs

- `ks!KsGetDeviceForDeviceObject` at `0x14001b23f`
- `ks!KsGetDeviceForDeviceObject` at `0x14001b23f`
- `ks!KsGetFilterFromIrp` at `0x14001b260`
- `ks!KsGetFilterFromIrp` at `0x14001b260`
- `ks!KsReleaseDevice` at `0x14001b2d0`
- `ks!KsReleaseDevice` at `0x14001b2d0`
- `ks!KsAcquireDevice` at `0x14001b251`
- `ks!KsAcquireDevice` at `0x14001b251`
- `ks!KsRemoveItemFromObjectBag` at `0x14001b28c`
- `ks!KsRemoveItemFromObjectBag` at `0x14001b28c`

## pseudocode

```c
void __fastcall FreeResourcesObjectBag_IfCreateFailure(PIRP Irp)
{
  struct _KSDEVICE *DeviceForDeviceObject; // rsi
  PKSFILTER FilterFromIrp; // rax
  PVOID Context; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8

  if ( Irp->IoStatus.Status < 0 )
  {
    DeviceForDeviceObject = KsGetDeviceForDeviceObject(Irp->Tail.Overlay.CurrentStackLocation->DeviceObject);
    KsAcquireDevice(DeviceForDeviceObject);
    FilterFromIrp = KsGetFilterFromIrp(Irp);
    if ( FilterFromIrp )
    {
      Context = FilterFromIrp->Context;
      FilterFromIrp->Context = 0;
      if ( Context )
      {
        if ( !KsRemoveItemFromObjectBag(FilterFromIrp->Bag, Context, 1u)
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qDq(WPP_GLOBAL_Control->AttachedDevice, v5, v6, Irp, Irp->IoStatus.Status, Context);
        }
      }
    }
    KsReleaseDevice(DeviceForDeviceObject);
  }
}

```

## disassembly

```asm
0x14001b218  mov     [rsp+arg_0], rbx
0x14001b21d  mov     [rsp+arg_8], rsi
0x14001b222  push    rdi
0x14001b223  sub     rsp, 30h
0x14001b227  cmp     dword ptr [rcx+30h], 0
0x14001b22b  mov     rbx, rcx
0x14001b22e  jge     loc_14001B2DC
0x14001b234  mov     rcx, [rcx+0B8h]
0x14001b23b  mov     rcx, [rcx+28h]; FunctionalDeviceObject
0x14001b23f  call    cs:__imp_KsGetDeviceForDeviceObject
0x14001b246  nop     dword ptr [rax+rax+00h]
0x14001b24b  mov     rcx, rax; Device
0x14001b24e  mov     rsi, rax
0x14001b251  call    cs:__imp_KsAcquireDevice
0x14001b258  nop     dword ptr [rax+rax+00h]
0x14001b25d  mov     rcx, rbx; Irp
0x14001b260  call    cs:__imp_KsGetFilterFromIrp
0x14001b267  nop     dword ptr [rax+rax+00h]
0x14001b26c  test    rax, rax
0x14001b26f  jz      short loc_14001B2CD
0x14001b271  mov     rdi, [rax+10h]
0x14001b275  mov     qword ptr [rax+10h], 0
0x14001b27d  test    rdi, rdi
0x14001b280  jz      short loc_14001B2CD
0x14001b282  mov     rcx, [rax+8]; ObjectBag
0x14001b286  mov     r8b, 1; Free
0x14001b289  mov     rdx, rdi; Item
0x14001b28c  call    cs:__imp_KsRemoveItemFromObjectBag
0x14001b293  nop     dword ptr [rax+rax+00h]
0x14001b298  test    eax, eax
0x14001b29a  jnz     short loc_14001B2CD
0x14001b29c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b2a3  lea     rax, WPP_GLOBAL_Control
0x14001b2aa  cmp     rcx, rax
0x14001b2ad  jz      short loc_14001B2CD
0x14001b2af  cmp     byte ptr [rcx+29h], 2
0x14001b2b3  jb      short loc_14001B2CD
0x14001b2b5  mov     eax, [rbx+30h]
0x14001b2b8  mov     r9, rbx
0x14001b2bb  mov     rcx, [rcx+18h]
0x14001b2bf  mov     [rsp+38h+var_10], rdi
0x14001b2c4  mov     [rsp+38h+var_18], eax
0x14001b2c8  call    WPP_SF_qDq
0x14001b2cd  mov     rcx, rsi; Device
0x14001b2d0  call    cs:__imp_KsReleaseDevice
0x14001b2d7  nop     dword ptr [rax+rax+00h]
0x14001b2dc  mov     rbx, [rsp+38h+arg_0]
0x14001b2e1  mov     rsi, [rsp+38h+arg_8]
0x14001b2e6  add     rsp, 30h
0x14001b2ea  pop     rdi
0x14001b2eb  retn
```
