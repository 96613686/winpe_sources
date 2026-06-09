# KmclpStartWaitForAction

- ea: `0x14000e148`
- end: `0x14000e30a`
- name: `KmclpStartWaitForAction`
- size: `450`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000bb70`
- `0x14000d310`
- `0x14000defc`
- `0x14000e9e0`

## callees

- `0x14000e148`
- `0x14000f780`
- `0x140011ed0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14000e1c2`
- `ntoskrnl!IoQueueWorkItem` at `0x14000e1c2`
- `ntoskrnl!IofCallDriver` at `0x14000e2eb`
- `ntoskrnl!IofCallDriver` at `0x14000e2eb`
- `ntoskrnl!IoReuseIrp` at `0x14000e25a`
- `ntoskrnl!IoReuseIrp` at `0x14000e25a`

## pseudocode

```c
void __fastcall KmclpStartWaitForAction(_DWORD *Context, __int64 a2, __int64 a3)
{
  struct _IO_WORKITEM *v4; // rcx
  int v5; // eax
  __int64 v6; // r8
  IRP *v7; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v9; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qLd(WPP_GLOBAL_Control->AttachedDevice, 94, a3, Context, Context[550], *((unsigned __int8 *)Context + 2805));
  }
  if ( *((_BYTE *)Context + 2805) )
  {
    v4 = (struct _IO_WORKITEM *)*((_QWORD *)Context + 349);
    *((_BYTE *)Context + 2805) = 0;
    IoQueueWorkItem(v4, KmclpWaitForActionWorkerRoutine, DelayedWorkQueue, Context);
    goto LABEL_14;
  }
  if ( !*((_BYTE *)Context + 2824) )
  {
    v7 = (IRP *)*((_QWORD *)Context + 348);
    IoReuseIrp(v7, 259);
    CurrentStackLocation = v7->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 14;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4112392;
    CurrentStackLocation[-1].Parameters.Create.Options = 0;
    CurrentStackLocation[-1].Parameters.Read.Length = 4;
    CurrentStackLocation[-1].FileObject = (PFILE_OBJECT)*((_QWORD *)Context + 341);
    CurrentStackLocation[-1].DeviceObject = (PDEVICE_OBJECT)*((_QWORD *)Context + 340);
    v7->RequestorMode = 0;
    v7->Tail.Overlay.Thread = KeGetCurrentThread();
    v7->Tail.Overlay.OriginalFileObject = CurrentStackLocation[-1].FileObject;
    v7->AssociatedIrp.MasterIrp = (struct _IRP *)(Context + 700);
    v7->UserBuffer = Context + 700;
    v9 = v7->Tail.Overlay.CurrentStackLocation;
    v9[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)KmclpWaitForActionCompleted;
    v9[-1].Context = Context;
    v9[-1].Control = -32;
    IofCallDriver(CurrentStackLocation[-1].DeviceObject, v7);
    goto LABEL_14;
  }
  v5 = (*((__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(PVOID), _DWORD *))Context + 358))(
         *((_QWORD *)Context + 355),
         KmclpDirectWaitForActionCallback,
         Context);
  if ( v5 >= 0 )
  {
LABEL_14:
    *((_BYTE *)Context + 2804) = 1;
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qLd(WPP_GLOBAL_Control->AttachedDevice, 95, v6, Context, Context[550], v5);
  }
}

```

## disassembly

```asm
0x14000e148  mov     [rsp+arg_0], rbx
0x14000e14d  push    rdi
0x14000e14e  sub     rsp, 30h
0x14000e152  mov     rdi, rcx
0x14000e155  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e15c  lea     rbx, WPP_GLOBAL_Control
0x14000e163  cmp     rcx, rbx
0x14000e166  jz      short loc_14000E19B
0x14000e168  mov     eax, [rcx+2Ch]
0x14000e16b  test    al, 1
0x14000e16d  jz      short loc_14000E19B
0x14000e16f  cmp     byte ptr [rcx+29h], 4
0x14000e173  jb      short loc_14000E19B
0x14000e175  movzx   eax, byte ptr [rdi+0AF5h]
0x14000e17c  mov     edx, 5Eh ; '^'
0x14000e181  mov     rcx, [rcx+18h]
0x14000e185  mov     r9, rdi
0x14000e188  mov     [rsp+38h+var_10], eax
0x14000e18c  mov     eax, [rdi+898h]
0x14000e192  mov     [rsp+38h+var_18], eax
0x14000e196  call    WPP_SF_qLd
0x14000e19b  cmp     byte ptr [rdi+0AF5h], 0
0x14000e1a2  jz      short loc_14000E1D3
0x14000e1a4  mov     rcx, [rdi+0AE8h]; IoWorkItem
0x14000e1ab  lea     rdx, KmclpWaitForActionWorkerRoutine; WorkerRoutine
0x14000e1b2  mov     r9, rdi; Context
0x14000e1b5  mov     byte ptr [rdi+0AF5h], 0
0x14000e1bc  mov     r8d, 1; QueueType
0x14000e1c2  call    cs:__imp_IoQueueWorkItem
0x14000e1c9  nop     dword ptr [rax+rax+00h]
0x14000e1ce  jmp     loc_14000E2F7
0x14000e1d3  cmp     byte ptr [rdi+0B08h], 0
0x14000e1da  jz      short loc_14000E24B
0x14000e1dc  mov     rax, [rdi+0B30h]
0x14000e1e3  lea     rdx, KmclpDirectWaitForActionCallback
0x14000e1ea  mov     rcx, [rdi+0B18h]
0x14000e1f1  mov     r8, rdi
0x14000e1f4  call    _guard_dispatch_icall
0x14000e1f9  test    eax, eax
0x14000e1fb  jns     loc_14000E2F7
0x14000e201  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e208  cmp     rcx, rbx
0x14000e20b  jz      loc_14000E2FE
0x14000e211  mov     edx, [rcx+2Ch]
0x14000e214  test    dl, 1
0x14000e217  jz      loc_14000E2FE
0x14000e21d  cmp     byte ptr [rcx+29h], 2
0x14000e221  jb      loc_14000E2FE
0x14000e227  mov     rcx, [rcx+18h]
0x14000e22b  mov     edx, 5Fh ; '_'
0x14000e230  mov     [rsp+38h+var_10], eax
0x14000e234  mov     r9, rdi
0x14000e237  mov     eax, [rdi+898h]
0x14000e23d  mov     [rsp+38h+var_18], eax
0x14000e241  call    WPP_SF_qLd
0x14000e246  jmp     loc_14000E2FE
0x14000e24b  mov     rbx, [rdi+0AE0h]
0x14000e252  mov     edx, 103h; Iostatus
0x14000e257  mov     rcx, rbx; Irp
0x14000e25a  call    cs:__imp_IoReuseIrp
0x14000e261  nop     dword ptr [rax+rax+00h]
0x14000e266  mov     rcx, [rbx+0B8h]
0x14000e26d  lea     rdx, KmclpWaitForActionCompleted
0x14000e274  mov     byte ptr [rcx-48h], 0Eh
0x14000e278  mov     dword ptr [rcx-30h], 3EC008h
0x14000e27f  mov     dword ptr [rcx-38h], 0
0x14000e286  mov     dword ptr [rcx-40h], 4
0x14000e28d  mov     rax, [rdi+0AA8h]
0x14000e294  mov     [rcx-18h], rax
0x14000e298  mov     rax, [rdi+0AA0h]
0x14000e29f  mov     [rcx-20h], rax
0x14000e2a3  mov     byte ptr [rbx+40h], 0
0x14000e2a7  mov     rax, gs:188h
0x14000e2b0  mov     [rbx+98h], rax
0x14000e2b7  mov     rax, [rcx-18h]
0x14000e2bb  mov     [rbx+0C0h], rax
0x14000e2c2  lea     rax, [rdi+0AF0h]
0x14000e2c9  mov     [rbx+18h], rax
0x14000e2cd  mov     [rbx+70h], rax
0x14000e2d1  mov     rax, [rbx+0B8h]
0x14000e2d8  mov     [rax-10h], rdx
0x14000e2dc  mov     rdx, rbx; Irp
0x14000e2df  mov     [rax-8], rdi
0x14000e2e3  mov     byte ptr [rax-45h], 0E0h
0x14000e2e7  mov     rcx, [rcx-20h]; DeviceObject
0x14000e2eb  call    cs:__imp_IofCallDriver
0x14000e2f2  nop     dword ptr [rax+rax+00h]
0x14000e2f7  mov     byte ptr [rdi+0AF4h], 1
0x14000e2fe  mov     rbx, [rsp+38h+arg_0]
0x14000e303  add     rsp, 30h
0x14000e307  pop     rdi
0x14000e308  retn
```
