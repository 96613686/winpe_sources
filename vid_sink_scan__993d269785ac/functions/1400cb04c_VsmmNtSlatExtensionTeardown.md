# VsmmNtSlatExtensionTeardown

- ea: `0x1400cb04c`
- end: `0x1400cb0ab`
- name: `VsmmNtSlatExtensionTeardown`
- size: `95`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140082b54`
- `0x1400cad84`

## callees

- `0x1400cb04c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb06a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb06a`
- `ntoskrnl!ExUnregisterExtension` at `0x1400cb08d`
- `ntoskrnl!ExUnregisterExtension` at `0x1400cb08d`

## pseudocode

```c
void VsmmNtSlatExtensionTeardown()
{
  _QWORD *v0; // rbx
  void *v1; // rcx

  v0 = VidDeviceExtension;
  v1 = (void *)*((_QWORD *)VidDeviceExtension + 274);
  if ( v1 )
  {
    ExFreePoolWithTag(v1, 0x6D4D6456u);
    v0[274] = 0;
  }
  if ( v0[237] )
  {
    ExUnregisterExtension();
    v0[237] = 0;
  }
}

```

## disassembly

```asm
0x1400cb04c  push    rbx
0x1400cb04e  sub     rsp, 20h
0x1400cb052  mov     rbx, cs:VidDeviceExtension
0x1400cb059  mov     rcx, [rbx+890h]; P
0x1400cb060  test    rcx, rcx
0x1400cb063  jz      short loc_1400CB081
0x1400cb065  mov     edx, 6D4D6456h; Tag
0x1400cb06a  call    cs:__imp_ExFreePoolWithTag
0x1400cb071  nop     dword ptr [rax+rax+00h]
0x1400cb076  mov     qword ptr [rbx+890h], 0
0x1400cb081  mov     rcx, [rbx+768h]
0x1400cb088  test    rcx, rcx
0x1400cb08b  jz      short loc_1400CB0A4
0x1400cb08d  call    cs:__imp_ExUnregisterExtension
0x1400cb094  nop     dword ptr [rax+rax+00h]
0x1400cb099  mov     qword ptr [rbx+768h], 0
0x1400cb0a4  add     rsp, 20h
0x1400cb0a8  pop     rbx
0x1400cb0a9  retn
```
