# VmCreate

- ea: `0x140002c20`
- end: `0x140002c49`
- name: `VmCreate`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002c35`
- `ntoskrnl!IofCompleteRequest` at `0x140002c35`

## pseudocode

```c
__int64 __fastcall VmCreate(__int64 a1, IRP *a2)
{
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140002c20  sub     rsp, 28h
0x140002c24  xor     ecx, ecx
0x140002c26  mov     rax, rdx
0x140002c29  mov     [rdx+30h], ecx
0x140002c2c  mov     [rdx+38h], rcx
0x140002c30  xor     edx, edx; PriorityBoost
0x140002c32  mov     rcx, rax; Irp
0x140002c35  call    cs:__imp_IofCompleteRequest
0x140002c3c  nop     dword ptr [rax+rax+00h]
0x140002c41  xor     eax, eax
0x140002c43  add     rsp, 28h
0x140002c47  retn
```
