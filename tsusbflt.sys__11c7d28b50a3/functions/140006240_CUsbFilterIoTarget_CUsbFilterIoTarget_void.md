# CUsbFilterIoTarget::~CUsbFilterIoTarget(void)

- ea: `0x140006240`
- end: `0x14000626f`
- name: `??1CUsbFilterIoTarget@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(CUsbFilterIoTarget *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006d2c`
- `0x140009650`

## callees

- `0x140006240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006254`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006254`

## pseudocode

```c
void __fastcall CUsbFilterIoTarget::~CUsbFilterIoTarget(CUsbFilterIoTarget *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x140006240  push    rbx
0x140006242  sub     rsp, 20h
0x140006246  mov     rbx, rcx
0x140006249  mov     rcx, [rcx+8]; P
0x14000624d  test    rcx, rcx
0x140006250  jz      short loc_140006268
0x140006252  xor     edx, edx; Tag
0x140006254  call    cs:__imp_ExFreePoolWithTag
0x14000625b  nop     dword ptr [rax+rax+00h]
0x140006260  mov     qword ptr [rbx+8], 0
0x140006268  add     rsp, 20h
0x14000626c  pop     rbx
0x14000626d  retn
```
