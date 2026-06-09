# CWdsDeviceControllerClient::DeleteDevice(ushort const *)

- ea: `0x180013490`
- end: `0x1800134a0`
- name: `?DeleteDevice@CWdsDeviceControllerClient@@UEAAKPEBG@Z`
- size: `16`
- prototype: `unsigned int __fastcall(CWdsDeviceControllerClient *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerClient::DeleteDevice(
        CWdsDeviceControllerClient *this,
        const unsigned __int16 *a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 1) + 56LL))(
           *((_QWORD *)this + 1),
           a2);
}

```

## disassembly

```asm
0x180013490  mov     rcx, [rcx+8]
0x180013494  mov     rax, [rcx]
0x180013497  mov     rax, [rax+38h]
0x18001349b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
