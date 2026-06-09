# WanNmrpDetachClientWorkerRoutine

- ea: `0x140004680`
- end: `0x1400046f2`
- name: `WanNmrpDetachClientWorkerRoutine`
- size: `114`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400044f0`

## callees

- `0x140004680`
- `0x140017738`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x1400046a7`
- `ntoskrnl!IoFreeWorkItem` at `0x1400046a7`
- `NETIO!NmrProviderDetachClientComplete` at `0x1400046df`
- `NETIO!NmrProviderDetachClientComplete` at `0x1400046df`

## pseudocode

```c
void __fastcall WanNmrpDetachClientWorkerRoutine(PDEVICE_OBJECT DeviceObject, __int64 *Context)
{
  struct _IO_WORKITEM *v3; // rcx

  WanpDeinitializeNdis(Context == &WanNmrV4ProviderState);
  v3 = (struct _IO_WORKITEM *)Context[59];
  if ( v3 )
  {
    IoFreeWorkItem(v3);
    Context[59] = 0;
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)(Context[27] + 32)) == 1 )
    NmrProviderDetachClientComplete(*(HANDLE *)(Context[27] + 16));
}

```

## disassembly

```asm
0x140004680  push    rbx
0x140004682  sub     rsp, 20h
0x140004686  lea     rax, WanNmrV4ProviderState
0x14000468d  mov     rbx, rdx
0x140004690  cmp     rdx, rax
0x140004693  setz    cl
0x140004696  call    WanpDeinitializeNdis
0x14000469b  mov     rcx, [rbx+1D8h]; IoWorkItem
0x1400046a2  test    rcx, rcx
0x1400046a5  jz      short loc_1400046BE
0x1400046a7  call    cs:__imp_IoFreeWorkItem
0x1400046ae  nop     dword ptr [rax+rax+00h]
0x1400046b3  mov     qword ptr [rbx+1D8h], 0
0x1400046be  mov     rcx, [rbx+0D8h]
0x1400046c5  or      eax, 0FFFFFFFFh
0x1400046c8  lock xadd [rcx+20h], eax
0x1400046cd  dec     eax
0x1400046cf  cmp     eax, 1
0x1400046d2  jnz     short loc_1400046EB
0x1400046d4  mov     rcx, [rbx+0D8h]
0x1400046db  mov     rcx, [rcx+10h]; NmrBindingHandle
0x1400046df  call    cs:__imp_NmrProviderDetachClientComplete
0x1400046e6  nop     dword ptr [rax+rax+00h]
0x1400046eb  add     rsp, 20h
0x1400046ef  pop     rbx
0x1400046f0  retn
```
