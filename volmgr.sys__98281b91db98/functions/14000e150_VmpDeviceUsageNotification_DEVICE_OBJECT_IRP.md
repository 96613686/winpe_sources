# VmpDeviceUsageNotification(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14000e150`
- end: `0x14000e265`
- name: `?VmpDeviceUsageNotification@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `277`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140016aa0`

## callees

- `0x1400014d0`
- `0x140005090`
- `0x14000e150`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000e24b`
- `ntoskrnl!IofCallDriver` at `0x14000e24b`
- `ntoskrnl!IofCompleteRequest` at `0x14000e197`
- `ntoskrnl!IofCompleteRequest` at `0x14000e197`

## pseudocode

```c
__int64 __fastcall VmpDeviceUsageNotification(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PVOID DeviceExtension; // rbp
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // esi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v9; // rax
  int v10; // [rsp+20h] [rbp-38h]

  DeviceExtension = a1->DeviceExtension;
  v4 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)DeviceExtension, a2, 1, 1, 0);
  v5 = 259;
  v6 = v4;
  if ( v4 != 259 )
  {
    if ( v4 < 0 )
    {
      a2->IoStatus.Information = 0;
      a2->IoStatus.Status = v4;
      IofCompleteRequest(a2, 0);
      return v6;
    }
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    v9 = a2->Tail.Overlay.CurrentStackLocation;
    v9[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VmpDeviceUsageNotificationCompletionRoutine;
    v9[-1].Context = DeviceExtension;
    v9[-1].Control = -32;
    if ( *((_BYTE *)DeviceExtension + 426) )
    {
      --a2->Tail.Overlay.CurrentStackLocation;
      --a2->CurrentLocation;
      LOBYTE(v10) = 0;
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      (*(void (__fastcall **)(_QWORD, struct _IRP *, void (__fastcall *)(_DWORD *, int), struct _IRP *, int))(*(_QWORD *)(*((_QWORD *)DeviceExtension + 1) + 392LL) + 216LL))(
        *((_QWORD *)DeviceExtension + 54),
        a2,
        VmBroadcastIrpCompletionRoutine,
        a2,
        v10);
    }
    else
    {
      return (unsigned int)IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 46), a2);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14000e150  push    rbx
0x14000e152  push    rbp
0x14000e153  push    rsi
0x14000e154  push    rdi
0x14000e155  sub     rsp, 38h
0x14000e159  mov     rbp, [rcx+40h]
0x14000e15d  mov     r9b, 1; unsigned __int8
0x14000e160  movzx   r8d, r9b; unsigned __int8
0x14000e164  mov     byte ptr [rsp+58h+var_38], 0; char
0x14000e169  mov     rcx, rbp; struct VM_VOLUME_EXTENSION *
0x14000e16c  mov     rdi, rdx
0x14000e16f  call    ?VmpAllSystemsGo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@EEE@Z; VmpAllSystemsGo(VM_VOLUME_EXTENSION *,_IRP *,uchar,uchar,uchar)
0x14000e174  mov     ebx, 103h
0x14000e179  mov     esi, eax
0x14000e17b  cmp     eax, ebx
0x14000e17d  jz      loc_14000E259
0x14000e183  test    eax, eax
0x14000e185  jns     short loc_14000E1AA
0x14000e187  xor     edx, edx; PriorityBoost
0x14000e189  mov     qword ptr [rdi+38h], 0
0x14000e191  mov     rcx, rdi; Irp
0x14000e194  mov     [rdi+30h], eax
0x14000e197  call    cs:__imp_IofCompleteRequest
0x14000e19e  nop     dword ptr [rax+rax+00h]
0x14000e1a3  mov     eax, esi
0x14000e1a5  jmp     loc_14000E25B
0x14000e1aa  mov     rax, [rdi+0B8h]
0x14000e1b1  lea     rcx, VmpDeviceUsageNotificationCompletionRoutine
0x14000e1b8  movups  xmm0, xmmword ptr [rax]
0x14000e1bb  movups  xmmword ptr [rax-48h], xmm0
0x14000e1bf  movups  xmm1, xmmword ptr [rax+10h]
0x14000e1c3  movups  xmmword ptr [rax-38h], xmm1
0x14000e1c7  movups  xmm0, xmmword ptr [rax+20h]
0x14000e1cb  movups  xmmword ptr [rax-28h], xmm0
0x14000e1cf  movsd   xmm1, qword ptr [rax+30h]
0x14000e1d4  movsd   qword ptr [rax-18h], xmm1
0x14000e1d9  mov     byte ptr [rax-45h], 0
0x14000e1dd  mov     rax, [rdi+0B8h]
0x14000e1e4  mov     [rax-10h], rcx
0x14000e1e8  mov     [rax-8], rbp
0x14000e1ec  mov     byte ptr [rax-45h], 0E0h
0x14000e1f0  cmp     byte ptr [rbp+1AAh], 0
0x14000e1f7  jz      short loc_14000E241
0x14000e1f9  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000e201  lea     r8, ?VmBroadcastIrpCompletionRoutine@@YAXPEAXJ@Z; VmBroadcastIrpCompletionRoutine(void *,long)
0x14000e208  dec     byte ptr [rdi+43h]
0x14000e20b  mov     r9, rdi
0x14000e20e  mov     rax, [rdi+0B8h]
0x14000e215  mov     byte ptr [rsp+58h+var_38], 0
0x14000e21a  or      byte ptr [rax+3], 1
0x14000e21e  mov     rax, [rbp+8]
0x14000e222  mov     rcx, [rbp+1B0h]
0x14000e229  mov     rdx, [rax+188h]
0x14000e230  mov     rax, [rdx+0D8h]
0x14000e237  mov     rdx, rdi
0x14000e23a  call    _guard_dispatch_icall
0x14000e23f  jmp     short loc_14000E259
0x14000e241  mov     rcx, [rbp+170h]; DeviceObject
0x14000e248  mov     rdx, rdi; Irp
0x14000e24b  call    cs:__imp_IofCallDriver
0x14000e252  nop     dword ptr [rax+rax+00h]
0x14000e257  mov     ebx, eax
0x14000e259  mov     eax, ebx
0x14000e25b  add     rsp, 38h
0x14000e25f  pop     rdi
0x14000e260  pop     rsi
0x14000e261  pop     rbp
0x14000e262  pop     rbx
0x14000e263  retn
```
