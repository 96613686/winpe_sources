# DriverEntry

- ea: `0x140007410`
- end: `0x14000743c`
- name: `DriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007444`
- `0x14001b008`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  sub_14001B008();
  return sub_140007444((__int64)DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x140007410  mov     [rsp+arg_0], rbx
0x140007415  push    rdi
0x140007416  sub     rsp, 20h
0x14000741a  mov     rbx, rdx
0x14000741d  mov     rdi, rcx
0x140007420  call    sub_14001B008
0x140007425  mov     rdx, rbx
0x140007428  mov     rcx, rdi
0x14000742b  call    sub_140007444
0x140007430  mov     rbx, [rsp+28h+arg_0]
0x140007435  add     rsp, 20h
0x140007439  pop     rdi
0x14000743a  retn
```
