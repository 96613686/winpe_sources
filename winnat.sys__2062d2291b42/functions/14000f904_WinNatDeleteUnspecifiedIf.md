# WinNatDeleteUnspecifiedIf

- ea: `0x14000f904`
- end: `0x14000f94e`
- name: `WinNatDeleteUnspecifiedIf`
- size: `74`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000daf0`
- `0x140010060`

## callees

- `0x14000f904`
- `0x14000f9a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f934`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f934`

## pseudocode

```c
void __fastcall WinNatDeleteUnspecifiedIf(PVOID P)
{
  PVOID *v2; // rcx
  PVOID *v3; // rax

  v2 = *(PVOID **)P;
  if ( v2[1] != P || (v3 = (PVOID *)*((_QWORD *)P + 1), *v3 != P) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = v3;
  WinNatDereferenceInstance(*((PVOID *)P + 4));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000f904  push    rbx
0x14000f906  sub     rsp, 20h
0x14000f90a  mov     rbx, rcx
0x14000f90d  mov     rcx, [rcx]
0x14000f910  cmp     [rcx+8], rbx
0x14000f914  jnz     short loc_14000F947
0x14000f916  mov     rax, [rbx+8]
0x14000f91a  cmp     [rax], rbx
0x14000f91d  jnz     short loc_14000F947
0x14000f91f  mov     [rax], rcx
0x14000f922  mov     [rcx+8], rax
0x14000f926  mov     rcx, [rbx+20h]; P
0x14000f92a  call    WinNatDereferenceInstance
0x14000f92f  xor     edx, edx; Tag
0x14000f931  mov     rcx, rbx; P
0x14000f934  call    cs:__imp_ExFreePoolWithTag
0x14000f93b  nop     dword ptr [rax+rax+00h]
0x14000f940  add     rsp, 20h
0x14000f944  pop     rbx
0x14000f945  retn
0x14000f947  mov     ecx, 3
0x14000f94c  int     29h; Win8: RtlFailFast(ecx)
```
