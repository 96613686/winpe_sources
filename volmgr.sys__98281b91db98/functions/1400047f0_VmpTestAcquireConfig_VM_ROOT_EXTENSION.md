# VmpTestAcquireConfig(VM_ROOT_EXTENSION *)

- ea: `0x1400047f0`
- end: `0x14000482a`
- name: `?VmpTestAcquireConfig@@YAEPEAVVM_ROOT_EXTENSION@@@Z`
- size: `58`
- prototype: `unsigned __int8 __fastcall(struct VM_ROOT_EXTENSION *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## callers

- `0x140012b3c`
- `0x14001462c`
- `0x140014838`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140004813`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004813`

## pseudocode

```c
bool __fastcall VmpTestAcquireConfig(struct VM_ROOT_EXTENSION *a1)
{
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp+8h] BYREF

  Timeout.QuadPart = 0;
  return KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, &Timeout) == 0;
}

```

## disassembly

```asm
0x1400047f0  sub     rsp, 38h
0x1400047f4  lea     rax, [rsp+38h+arg_0]
0x1400047f9  mov     qword ptr [rsp+38h+arg_0], 0
0x140004802  add     rcx, 38h ; '8'; Object
0x140004806  mov     [rsp+38h+Timeout], rax; Timeout
0x14000480b  xor     r9d, r9d; Alertable
0x14000480e  xor     r8d, r8d; WaitMode
0x140004811  xor     edx, edx; WaitReason
0x140004813  call    cs:__imp_KeWaitForSingleObject
0x14000481a  nop     dword ptr [rax+rax+00h]
0x14000481f  test    eax, eax
0x140004821  setz    al
0x140004824  add     rsp, 38h
0x140004828  retn
```
