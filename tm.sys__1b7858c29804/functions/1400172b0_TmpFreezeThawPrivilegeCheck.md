# TmpFreezeThawPrivilegeCheck

- ea: `0x1400172b0`
- end: `0x1400172e4`
- name: `TmpFreezeThawPrivilegeCheck`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140016b10`
- `0x140017280`

## import_xrefs

- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1400172c7`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1400172c7`
- `ntoskrnl!SeExports` at `0x1400172b4`

## pseudocode

```c
__int64 TmpFreezeThawPrivilegeCheck()
{
  return SeSinglePrivilegeCheck(SeExports->SeRestorePrivilege, 1) == 0 ? 0xC0000061 : 0;
}

```

## disassembly

```asm
0x1400172b0  sub     rsp, 28h
0x1400172b4  mov     rax, cs:__imp_SeExports
0x1400172bb  mov     dl, 1; PreviousMode
0x1400172bd  mov     rcx, [rax]
0x1400172c0  mov     rcx, [rcx+80h]; PrivilegeValue
0x1400172c7  call    cs:__imp_SeSinglePrivilegeCheck
0x1400172ce  nop     dword ptr [rax+rax+00h]
0x1400172d3  neg     al
0x1400172d5  sbb     eax, eax
0x1400172d7  not     eax
0x1400172d9  and     eax, 0C0000061h
0x1400172de  add     rsp, 28h
0x1400172e2  retn
```
