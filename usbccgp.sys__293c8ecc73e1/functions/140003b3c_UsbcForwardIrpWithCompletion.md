# UsbcForwardIrpWithCompletion

- ea: `0x140003b3c`
- end: `0x140003c22`
- name: `UsbcForwardIrpWithCompletion`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002ad0`
- `0x140028800`

## callees

- `0x140003b3c`
- `0x14000a6cc`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140003bc1`
- `ntoskrnl!IofCallDriver` at `0x140003bc1`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140003bab`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140003bab`

## pseudocode

```c
NTSTATUS __fastcall UsbcForwardIrpWithCompletion(
        __int64 a1,
        struct _DEVICE_OBJECT *a2,
        IRP *a3,
        IO_COMPLETION_ROUTINE *a4,
        struct _DEVICE_OBJECT *DeviceObject,
        PVOID Context)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v10; // r14
  NTSTATUS v11; // eax
  int v12; // edx
  _IO_STACK_LOCATION *v14; // rax

  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v10 = *(_QWORD *)(a1 + 1368);
  v11 = IoSetCompletionRoutineEx(DeviceObject, a3, a4, Context, 1u, 1u, 1u);
  if ( v11 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 3;
      WPP_RECORDER_SF_d(v10, v12, 1, 60, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids, v11);
    }
    v14 = a3->Tail.Overlay.CurrentStackLocation;
    v14[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))a4;
    v14[-1].Context = Context;
    v14[-1].Control = -32;
  }
  return IofCallDriver(a2, a3);
}

```

## disassembly

```asm
0x140003b3c  push    rbx
0x140003b3e  push    rbp
0x140003b3f  push    rsi
0x140003b40  push    rdi
0x140003b41  push    r14
0x140003b43  sub     rsp, 40h
0x140003b47  mov     rax, [r8+0B8h]
0x140003b4e  mov     rdi, r9
0x140003b51  mov     rsi, [rsp+68h+Context]
0x140003b59  mov     rbx, r8
0x140003b5c  mov     rbp, rdx
0x140003b5f  mov     [rsp+68h+InvokeOnCancel], 1; InvokeOnCancel
0x140003b64  mov     [rsp+68h+InvokeOnError], 1; InvokeOnError
0x140003b69  mov     r9, rsi; Context
0x140003b6c  movups  xmm0, xmmword ptr [rax]
0x140003b6f  mov     r8, rdi; CompletionRoutine
0x140003b72  mov     [rsp+68h+InvokeOnSuccess], 1; InvokeOnSuccess
0x140003b77  mov     rdx, rbx; Irp
0x140003b7a  movups  xmmword ptr [rax-48h], xmm0
0x140003b7e  movups  xmm1, xmmword ptr [rax+10h]
0x140003b82  movups  xmmword ptr [rax-38h], xmm1
0x140003b86  movups  xmm0, xmmword ptr [rax+20h]
0x140003b8a  movups  xmmword ptr [rax-28h], xmm0
0x140003b8e  movsd   xmm1, qword ptr [rax+30h]
0x140003b93  movsd   qword ptr [rax-18h], xmm1
0x140003b98  mov     byte ptr [rax-45h], 0
0x140003b9c  mov     r14, [rcx+558h]
0x140003ba3  mov     rcx, [rsp+68h+DeviceObject]; DeviceObject
0x140003bab  call    cs:__imp_IoSetCompletionRoutineEx
0x140003bb2  nop     dword ptr [rax+rax+00h]
0x140003bb7  test    eax, eax
0x140003bb9  js      short loc_140003BD9
0x140003bbb  mov     rdx, rbx; Irp
0x140003bbe  mov     rcx, rbp; DeviceObject
0x140003bc1  call    cs:__imp_IofCallDriver
0x140003bc8  nop     dword ptr [rax+rax+00h]
0x140003bcd  add     rsp, 40h
0x140003bd1  pop     r14
0x140003bd3  pop     rdi
0x140003bd4  pop     rsi
0x140003bd5  pop     rbp
0x140003bd6  pop     rbx
0x140003bd7  retn
0x140003bd9  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003be0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140003be7  jz      short loc_140003C0D
0x140003be9  mov     dword ptr [rsp+68h+InvokeOnError], eax
0x140003bed  mov     r9d, 3Ch ; '<'
0x140003bf3  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140003bfa  mov     dl, 3
0x140003bfc  mov     rcx, r14
0x140003bff  mov     qword ptr [rsp+68h+InvokeOnSuccess], rax
0x140003c04  lea     r8d, [r9-3Bh]
0x140003c08  call    WPP_RECORDER_SF_d
0x140003c0d  mov     rax, [rbx+0B8h]
0x140003c14  mov     [rax-10h], rdi
0x140003c18  mov     [rax-8], rsi
0x140003c1c  mov     byte ptr [rax-45h], 0E0h
0x140003c20  jmp     short loc_140003BBB
```
