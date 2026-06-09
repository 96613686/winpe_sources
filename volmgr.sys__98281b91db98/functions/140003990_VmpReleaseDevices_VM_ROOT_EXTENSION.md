# VmpReleaseDevices(VM_ROOT_EXTENSION *)

- ea: `0x140003990`
- end: `0x1400039ac`
- name: `?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z`
- size: `28`
- prototype: `void __fastcall(struct VM_ROOT_EXTENSION *)`
- caller_count: `15`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000e010`
- `0x14000fbc0`
- `0x1400127f0`
- `0x1400129d0`
- `0x140012b3c`
- `0x140012fa0`
- `0x1400132f8`
- `0x140013594`
- `0x1400136b8`
- `0x1400139b4`
- `0x14001462c`
- `0x140014838`
- `0x140016130`
- `0x140016540`
- `0x140016aa0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000399a`
- `ntoskrnl!KeReleaseMutex` at `0x14000399a`

## pseudocode

```c
void __fastcall VmpReleaseDevices(struct _KMUTANT *a1)
{
  KeReleaseMutex(a1 + 2, 0);
}

```

## disassembly

```asm
0x140003990  sub     rsp, 28h
0x140003994  add     rcx, 70h ; 'p'; Mutex
0x140003998  xor     edx, edx; Wait
0x14000399a  call    cs:__imp_KeReleaseMutex
0x1400039a1  nop     dword ptr [rax+rax+00h]
0x1400039a6  add     rsp, 28h
0x1400039aa  retn
```
