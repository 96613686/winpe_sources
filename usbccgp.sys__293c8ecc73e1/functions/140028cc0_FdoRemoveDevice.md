# FdoRemoveDevice

- ea: `0x140028cc0`
- end: `0x140028d6f`
- name: `FdoRemoveDevice`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140028800`

## callees

- `0x140008eac`
- `0x14000a448`
- `0x140028cc0`
- `0x140028d78`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140028d04`
- `ntoskrnl!IofCallDriver` at `0x140028d04`
- `ntoskrnl!IoDetachDevice` at `0x140028d16`
- `ntoskrnl!IoDetachDevice` at `0x140028d16`

## pseudocode

```c
__int64 __fastcall FdoRemoveDevice(__int64 a1, IRP *a2)
{
  IRP *v2; // rbx
  unsigned int v4; // ebx
  __int64 v5; // rdx

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qq(
      *(_QWORD *)(a1 + 1368),
      (_DWORD)a2,
      2,
      39,
      (__int64)WPP_54beca300c4a353e079921b0991edb26_Traceguids,
      *(_QWORD *)(a1 + 32),
      (char)v2);
  }
  PrepareParentFDOForRemove(a1, v2);
  ++v2->CurrentLocation;
  ++v2->Tail.Overlay.CurrentStackLocation;
  v2->IoStatus.Status = 0;
  v4 = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 40), v2);
  IoDetachDevice(*(PDEVICE_OBJECT *)(a1 + 40));
  FreeParentFDOResources(a1, v5);
  return v4;
}

```

## disassembly

```asm
0x140028cc0  mov     [rsp+arg_0], rbx
0x140028cc5  push    rdi
0x140028cc6  sub     rsp, 40h
0x140028cca  mov     rbx, rdx
0x140028ccd  mov     rdi, rcx
0x140028cd0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140028cd7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140028cde  jnz     short loc_140028D38
0x140028ce0  mov     rdx, rbx
0x140028ce3  mov     rcx, rdi
0x140028ce6  call    PrepareParentFDOForRemove
0x140028ceb  inc     byte ptr [rbx+43h]
0x140028cee  mov     rdx, rbx; Irp
0x140028cf1  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140028cf9  mov     dword ptr [rbx+30h], 0
0x140028d00  mov     rcx, [rdi+28h]; DeviceObject
0x140028d04  call    cs:__imp_IofCallDriver
0x140028d0b  nop     dword ptr [rax+rax+00h]
0x140028d10  mov     rcx, [rdi+28h]; TargetDevice
0x140028d14  mov     ebx, eax
0x140028d16  call    cs:__imp_IoDetachDevice
0x140028d1d  nop     dword ptr [rax+rax+00h]
0x140028d22  mov     rcx, rdi
0x140028d25  call    FreeParentFDOResources
0x140028d2a  mov     eax, ebx
0x140028d2c  mov     rbx, [rsp+48h+arg_0]
0x140028d31  add     rsp, 40h
0x140028d35  pop     rdi
0x140028d36  retn
0x140028d38  mov     rax, [rcx+20h]
0x140028d3c  mov     r9d, 27h ; '''
0x140028d42  mov     rcx, [rcx+558h]
0x140028d49  mov     dl, 4
0x140028d4b  mov     [rsp+48h+var_18], rbx
0x140028d50  mov     [rsp+48h+var_20], rax
0x140028d55  lea     rax, WPP_54beca300c4a353e079921b0991edb26_Traceguids
0x140028d5c  lea     r8d, [r9-25h]
0x140028d60  mov     [rsp+48h+var_28], rax
0x140028d65  call    WPP_RECORDER_SF_qq
0x140028d6a  jmp     loc_140028CE0
```
