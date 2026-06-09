# WinSetupMonCreateClose

- ea: `0x140007d00`
- end: `0x140007d2c`
- name: `WinSetupMonCreateClose`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140007d18`
- `ntoskrnl!IofCompleteRequest` at `0x140007d18`

## pseudocode

```c
__int64 __fastcall WinSetupMonCreateClose(__int64 a1, IRP *a2)
{
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140007d00  sub     rsp, 28h
0x140007d04  mov     rcx, rdx; Irp
0x140007d07  mov     qword ptr [rdx+38h], 0
0x140007d0f  mov     dword ptr [rdx+30h], 0
0x140007d16  xor     edx, edx; PriorityBoost
0x140007d18  call    cs:__imp_IofCompleteRequest
0x140007d1f  nop     dword ptr [rax+rax+00h]
0x140007d24  xor     eax, eax
0x140007d26  add     rsp, 28h
0x140007d2a  retn
```
