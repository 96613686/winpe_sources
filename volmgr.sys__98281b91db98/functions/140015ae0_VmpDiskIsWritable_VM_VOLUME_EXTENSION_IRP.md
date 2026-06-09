# VmpDiskIsWritable(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140015ae0`
- end: `0x140015b9e`
- name: `?VmpDiskIsWritable@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x140015ae0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140015b42`
- `ntoskrnl!IofCallDriver` at `0x140015b42`

## pseudocode

```c
NTSTATUS __fastcall VmpDiskIsWritable(PDEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v3; // rax
  char v5; // [rsp+20h] [rbp-18h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v3 = a2->Tail.Overlay.CurrentStackLocation;
  v3[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VmpRefCountCompletionRoutine;
  v3[-1].Context = (PVOID)458788;
  v3[-1].Control = -32;
  if ( !*((_BYTE *)a1 + 426) )
    return IofCallDriver(a1[43], a2);
  --a2->Tail.Overlay.CurrentStackLocation;
  --a2->CurrentLocation;
  v5 = 1;
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  (*(void (__fastcall **)(PDEVICE_OBJECT, struct _IRP *, void (__fastcall *)(_DWORD *, int), struct _IRP *, char))&a1[1][1].Vpb[2].SerialNumber)(
    a1[54],
    a2,
    VmBroadcastIrpCompletionRoutine,
    a2,
    v5);
  return 259;
}

```

## disassembly

```asm
0x140015ae0  sub     rsp, 38h
0x140015ae4  mov     rax, [rdx+0B8h]
0x140015aeb  mov     r10, rcx
0x140015aee  lea     rcx, VmpRefCountCompletionRoutine
0x140015af5  movups  xmm0, xmmword ptr [rax]
0x140015af8  movups  xmmword ptr [rax-48h], xmm0
0x140015afc  movups  xmm1, xmmword ptr [rax+10h]
0x140015b00  movups  xmmword ptr [rax-38h], xmm1
0x140015b04  movups  xmm0, xmmword ptr [rax+20h]
0x140015b08  movups  xmmword ptr [rax-28h], xmm0
0x140015b0c  movsd   xmm1, qword ptr [rax+30h]
0x140015b11  movsd   qword ptr [rax-18h], xmm1
0x140015b16  mov     byte ptr [rax-45h], 0
0x140015b1a  mov     rax, [rdx+0B8h]
0x140015b21  mov     [rax-10h], rcx
0x140015b25  mov     qword ptr [rax-8], 70024h
0x140015b2d  mov     byte ptr [rax-45h], 0E0h
0x140015b31  cmp     byte ptr [r10+1AAh], 0
0x140015b39  jnz     short loc_140015B54
0x140015b3b  mov     rcx, [r10+158h]; DeviceObject
0x140015b42  call    cs:__imp_IofCallDriver
0x140015b49  nop     dword ptr [rax+rax+00h]
0x140015b4e  add     rsp, 38h
0x140015b52  retn
0x140015b54  add     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140015b5c  lea     r8, ?VmBroadcastIrpCompletionRoutine@@YAXPEAXJ@Z; VmBroadcastIrpCompletionRoutine(void *,long)
0x140015b63  dec     byte ptr [rdx+43h]
0x140015b66  mov     r9, rdx
0x140015b69  mov     rax, [rdx+0B8h]
0x140015b70  mov     [rsp+38h+var_18], 1
0x140015b75  or      byte ptr [rax+3], 1
0x140015b79  mov     rax, [r10+8]
0x140015b7d  mov     rcx, [rax+188h]
0x140015b84  mov     rax, [rcx+0D8h]
0x140015b8b  mov     rcx, [r10+1B0h]
0x140015b92  call    _guard_dispatch_icall
0x140015b97  mov     eax, 103h
0x140015b9c  jmp     short loc_140015B4E
```
