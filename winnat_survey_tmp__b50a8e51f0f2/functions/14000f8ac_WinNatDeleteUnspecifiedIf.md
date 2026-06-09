# WinNatDeleteUnspecifiedIf

- ea: `0x14000f8ac`
- end: `0x14000f8f6`
- name: `WinNatDeleteUnspecifiedIf`
- size: `74`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000db20`
- `0x140010000`

## callees

- `0x14000f8ac`
- `0x14000f94c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f8dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f8dc`

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
0x14000f8ac  push    rbx
0x14000f8ae  sub     rsp, 20h
0x14000f8b2  mov     rbx, rcx
0x14000f8b5  mov     rcx, [rcx]
0x14000f8b8  cmp     [rcx+8], rbx
0x14000f8bc  jnz     short loc_14000F8EF
0x14000f8be  mov     rax, [rbx+8]
0x14000f8c2  cmp     [rax], rbx
0x14000f8c5  jnz     short loc_14000F8EF
0x14000f8c7  mov     [rax], rcx
0x14000f8ca  mov     [rcx+8], rax
0x14000f8ce  mov     rcx, [rbx+20h]; P
0x14000f8d2  call    WinNatDereferenceInstance
0x14000f8d7  xor     edx, edx; Tag
0x14000f8d9  mov     rcx, rbx; P
0x14000f8dc  call    cs:__imp_ExFreePoolWithTag
0x14000f8e3  nop     dword ptr [rax+rax+00h]
0x14000f8e8  add     rsp, 20h
0x14000f8ec  pop     rbx
0x14000f8ed  retn
0x14000f8ef  mov     ecx, 3
0x14000f8f4  int     29h; Win8: RtlFailFast(ecx)
```
