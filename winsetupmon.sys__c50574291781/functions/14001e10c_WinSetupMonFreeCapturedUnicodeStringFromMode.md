# WinSetupMonFreeCapturedUnicodeStringFromMode

- ea: `0x14001e10c`
- end: `0x14001e142`
- name: `WinSetupMonFreeCapturedUnicodeStringFromMode`
- size: `54`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001e044`
- `0x14001e174`
- `0x14001e23c`
- `0x14001e2ec`
- `0x14001e464`
- `0x14001e524`
- `0x14001e630`
- `0x14001e71c`

## callees

- `0x14001e10c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e127`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e127`

## pseudocode

```c
void __fastcall WinSetupMonFreeCapturedUnicodeStringFromMode(__int64 a1, char a2)
{
  void *v3; // rcx

  if ( a2 == 1 )
  {
    v3 = *(void **)(a1 + 8);
    if ( v3 )
    {
      ExFreePoolWithTag(v3, 0x6E6D7377u);
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
}

```

## disassembly

```asm
0x14001e10c  cmp     dl, 1
0x14001e10f  jnz     short locret_14001E140
0x14001e111  push    rbx
0x14001e112  sub     rsp, 20h
0x14001e116  mov     rbx, rcx
0x14001e119  mov     rcx, [rcx+8]; P
0x14001e11d  test    rcx, rcx
0x14001e120  jz      short loc_14001E13B
0x14001e122  mov     edx, 6E6D7377h; Tag
0x14001e127  call    cs:__imp_ExFreePoolWithTag
0x14001e12e  nop     dword ptr [rax+rax+00h]
0x14001e133  mov     qword ptr [rbx+8], 0
0x14001e13b  add     rsp, 20h
0x14001e13f  pop     rbx
0x14001e140  retn
```
