# DriverEntry

- ea: `0x1400163d0`
- end: `0x1400163fc`
- name: `DriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140016404`
- `0x1400274bc`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  sub_1400274BC();
  return sub_140016404(DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x1400163d0  mov     [rsp+arg_0], rbx
0x1400163d5  push    rdi
0x1400163d6  sub     rsp, 20h
0x1400163da  mov     rbx, rdx
0x1400163dd  mov     rdi, rcx
0x1400163e0  call    sub_1400274BC
0x1400163e5  mov     rdx, rbx
0x1400163e8  mov     rcx, rdi; Driver
0x1400163eb  call    sub_140016404
0x1400163f0  mov     rbx, [rsp+28h+arg_0]
0x1400163f5  add     rsp, 20h
0x1400163f9  pop     rdi
0x1400163fa  retn
```
