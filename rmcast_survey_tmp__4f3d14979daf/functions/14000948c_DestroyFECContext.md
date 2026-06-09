# DestroyFECContext

- ea: `0x14000948c`
- end: `0x1400094f9`
- name: `DestroyFECContext`
- size: `109`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005c0c`
- `0x140005e3c`
- `0x140012efc`

## callees

- `0x14000948c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400094a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094de`

## pseudocode

```c
void __fastcall DestroyFECContext(_QWORD *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (void *)a1[2];
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    a1[2] = 0;
  }
  v3 = (void *)a1[3];
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    a1[3] = 0;
  }
  v4 = (void *)a1[1];
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    a1[1] = 0;
  }
}

```

## disassembly

```asm
0x14000948c  push    rbx
0x14000948e  sub     rsp, 20h
0x140009492  mov     rbx, rcx
0x140009495  mov     rcx, [rcx+10h]; P
0x140009499  test    rcx, rcx
0x14000949c  jz      short loc_1400094B4
0x14000949e  xor     edx, edx; Tag
0x1400094a0  call    cs:__imp_ExFreePoolWithTag
0x1400094a7  nop     dword ptr [rax+rax+00h]
0x1400094ac  mov     qword ptr [rbx+10h], 0
0x1400094b4  mov     rcx, [rbx+18h]; P
0x1400094b8  test    rcx, rcx
0x1400094bb  jz      short loc_1400094D3
0x1400094bd  xor     edx, edx; Tag
0x1400094bf  call    cs:__imp_ExFreePoolWithTag
0x1400094c6  nop     dword ptr [rax+rax+00h]
0x1400094cb  mov     qword ptr [rbx+18h], 0
0x1400094d3  mov     rcx, [rbx+8]; P
0x1400094d7  test    rcx, rcx
0x1400094da  jz      short loc_1400094F2
0x1400094dc  xor     edx, edx; Tag
0x1400094de  call    cs:__imp_ExFreePoolWithTag
0x1400094e5  nop     dword ptr [rax+rax+00h]
0x1400094ea  mov     qword ptr [rbx+8], 0
0x1400094f2  add     rsp, 20h
0x1400094f6  pop     rbx
0x1400094f7  retn
```
