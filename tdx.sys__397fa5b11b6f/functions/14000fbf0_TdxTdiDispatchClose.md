# TdxTdiDispatchClose

- ea: `0x14000fbf0`
- end: `0x14000fc8a`
- name: `TdxTdiDispatchClose`
- size: `154`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000fbf0`
- `0x140010b90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc5d`
- `ntoskrnl!IofCompleteRequest` at `0x14000fc3c`
- `ntoskrnl!IofCompleteRequest` at `0x14000fc3c`

## pseudocode

```c
__int64 __fastcall TdxTdiDispatchClose(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  PVOID FsContext2; // rax

  if ( a1 != TdxDeviceObject )
  {
    FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
    FsContext2 = FileObject->FsContext2;
    if ( FsContext2 == (PVOID)2 )
    {
      ExFreePoolWithTag(FileObject->FsContext, 0);
      _InterlockedDecrement((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.1 + 5);
    }
    else if ( FsContext2 == (PVOID)1 )
    {
      ExFreePoolWithTag(FileObject->FsContext, 0);
      _InterlockedDecrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    }
    else if ( FsContext2 == (PVOID)3 )
    {
      TdxDeleteControlChannel(FileObject->FsContext);
      _InterlockedDecrement((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 1);
    }
  }
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000fbf0  push    rbx
0x14000fbf2  sub     rsp, 20h
0x14000fbf6  cmp     rcx, cs:TdxDeviceObject
0x14000fbfd  mov     rbx, rdx
0x14000fc00  jz      short loc_14000FC30
0x14000fc02  mov     rax, [rdx+0B8h]
0x14000fc09  mov     rcx, [rax+30h]
0x14000fc0d  mov     rax, [rcx+20h]
0x14000fc11  cmp     rax, 2
0x14000fc15  jnz     short loc_14000FC51
0x14000fc17  mov     rcx, [rcx+18h]; P
0x14000fc1b  xor     edx, edx; Tag
0x14000fc1d  call    cs:__imp_ExFreePoolWithTag
0x14000fc24  nop     dword ptr [rax+rax+00h]
0x14000fc29  lock dec dword ptr cs:WPP_MAIN_CB.Queue+14h
0x14000fc30  xor     edx, edx; PriorityBoost
0x14000fc32  mov     dword ptr [rbx+30h], 0
0x14000fc39  mov     rcx, rbx; Irp
0x14000fc3c  call    cs:__imp_IofCompleteRequest
0x14000fc43  nop     dword ptr [rax+rax+00h]
0x14000fc48  xor     eax, eax
0x14000fc4a  add     rsp, 20h
0x14000fc4e  pop     rbx
0x14000fc4f  retn
0x14000fc51  cmp     rax, 1
0x14000fc55  jnz     short loc_14000FC72
0x14000fc57  mov     rcx, [rcx+18h]; P
0x14000fc5b  xor     edx, edx; Tag
0x14000fc5d  call    cs:__imp_ExFreePoolWithTag
0x14000fc64  nop     dword ptr [rax+rax+00h]
0x14000fc69  lock dec dword ptr cs:WPP_MAIN_CB.Queue+18h
0x14000fc70  jmp     short loc_14000FC30
0x14000fc72  cmp     rax, 3
0x14000fc76  jnz     short loc_14000FC30
0x14000fc78  mov     rcx, [rcx+18h]; P
0x14000fc7c  call    TdxDeleteControlChannel
0x14000fc81  lock dec dword ptr cs:WPP_MAIN_CB.Queue+1Ch
0x14000fc88  jmp     short loc_14000FC30
```
