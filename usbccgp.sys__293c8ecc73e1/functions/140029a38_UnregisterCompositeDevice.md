# UnregisterCompositeDevice

- ea: `0x140029a38`
- end: `0x140029b2a`
- name: `UnregisterCompositeDevice`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a448`
- `0x140028800`

## callees

- `0x14000a6cc`
- `0x140029a38`
- `0x140029b50`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140029a97`
- `ntoskrnl!IoFreeIrp` at `0x140029a97`
- `ntoskrnl!IoAllocateIrp` at `0x140029a4e`
- `ntoskrnl!IoAllocateIrp` at `0x140029a4e`

## pseudocode

```c
void __fastcall UnregisterCompositeDevice(__int64 a1)
{
  PIRP Irp; // rax
  int v3; // edx
  IRP *v4; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v6; // eax
  int v7; // edx

  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 40) + 76LL), 0);
  v4 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4784135;
    v6 = CallDriverSync(*(PDEVICE_OBJECT *)(a1 + 40), v4, 0, *(struct _DEVICE_OBJECT **)(a1 + 32));
    if ( v6 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 1368),
          v7,
          8,
          77,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          v6);
      }
    }
    else
    {
      *(_BYTE *)(a1 + 1361) = 0;
    }
    IoFreeIrp(v4);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 1368), v3, 8, 76, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids, 154);
  }
}

```

## disassembly

```asm
0x140029a38  mov     [rsp+arg_0], rbx
0x140029a3d  push    rdi
0x140029a3e  sub     rsp, 30h
0x140029a42  mov     rbx, rcx
0x140029a45  xor     edx, edx; ChargeQuota
0x140029a47  mov     rcx, [rcx+28h]
0x140029a4b  mov     cl, [rcx+4Ch]; StackSize
0x140029a4e  call    cs:__imp_IoAllocateIrp
0x140029a55  nop     dword ptr [rax+rax+00h]
0x140029a5a  mov     rdi, rax
0x140029a5d  test    rax, rax
0x140029a60  jz      short loc_140029AAF
0x140029a62  mov     rax, [rax+0B8h]
0x140029a69  xor     r8d, r8d
0x140029a6c  mov     rdx, rdi; Irp
0x140029a6f  mov     byte ptr [rax-48h], 0Fh
0x140029a73  mov     dword ptr [rax-30h], 490007h
0x140029a7a  mov     r9, [rbx+20h]
0x140029a7e  mov     rcx, [rbx+28h]; DeviceObject
0x140029a82  call    CallDriverSync
0x140029a87  mov     ecx, eax
0x140029a89  test    eax, eax
0x140029a8b  js      short loc_140029AED
0x140029a8d  mov     byte ptr [rbx+551h], 0
0x140029a94  mov     rcx, rdi; Irp
0x140029a97  call    cs:__imp_IoFreeIrp
0x140029a9e  nop     dword ptr [rax+rax+00h]
0x140029aa3  mov     rbx, [rsp+38h+arg_0]
0x140029aa8  add     rsp, 30h
0x140029aac  pop     rdi
0x140029aad  retn
0x140029aaf  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029ab6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029abd  jz      short loc_140029AA3
0x140029abf  mov     rcx, [rbx+558h]
0x140029ac6  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x140029acd  mov     r9d, 4Ch ; 'L'
0x140029ad3  mov     [rsp+38h+var_10], 0C000009Ah
0x140029adb  mov     dl, 2
0x140029add  mov     [rsp+38h+var_18], rax
0x140029ae2  lea     r8d, [r9-44h]
0x140029ae6  call    WPP_RECORDER_SF_d
0x140029aeb  jmp     short loc_140029AA3
0x140029aed  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029af4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029afb  jz      short loc_140029A94
0x140029afd  mov     [rsp+38h+var_10], ecx
0x140029b01  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x140029b08  mov     rcx, [rbx+558h]
0x140029b0f  mov     r9d, 4Dh ; 'M'
0x140029b15  mov     dl, 2
0x140029b17  mov     [rsp+38h+var_18], rax
0x140029b1c  lea     r8d, [r9-45h]
0x140029b20  call    WPP_RECORDER_SF_d
0x140029b25  jmp     loc_140029A94
```
