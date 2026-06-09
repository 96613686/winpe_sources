# Win32kSystemTableAdd

- ea: `0x14001b150`
- end: `0x14001b1b2`
- name: `Win32kSystemTableAdd`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `ntoskrnl!KeAddSystemServiceTable` at `0x14001b173`
- `ntoskrnl!KeAddSystemServiceTable` at `0x14001b19e`
- `ntoskrnl!KeAddSystemServiceTable` at `0x14001b173`
- `ntoskrnl!KeAddSystemServiceTable` at `0x14001b19e`

## pseudocode

```c
__int64 Win32kSystemTableAdd()
{
  KeAddSystemServiceTable(W32pServiceTable, 0, (unsigned int)W32pServiceLimit, &W32pArgumentTable, 1);
  KeAddSystemServiceTable(W32pServiceTableFilter, 0, (unsigned int)W32pServiceLimitFilter, &W32pArgumentTableFilter, 2);
  return 0;
}

```

## disassembly

```asm
0x14001b150  sub     rsp, 38h
0x14001b154  mov     r8d, cs:W32pServiceLimit
0x14001b15b  lea     r9, W32pArgumentTable
0x14001b162  xor     edx, edx
0x14001b164  mov     [rsp+38h+var_18], 1
0x14001b16c  lea     rcx, W32pServiceTable
0x14001b173  call    cs:__imp_KeAddSystemServiceTable
0x14001b17a  nop     dword ptr [rax+rax+00h]
0x14001b17f  mov     r8d, cs:W32pServiceLimitFilter
0x14001b186  lea     r9, W32pArgumentTableFilter
0x14001b18d  xor     edx, edx
0x14001b18f  mov     [rsp+38h+var_18], 2
0x14001b197  lea     rcx, W32pServiceTableFilter
0x14001b19e  call    cs:__imp_KeAddSystemServiceTable
0x14001b1a5  nop     dword ptr [rax+rax+00h]
0x14001b1aa  xor     eax, eax
0x14001b1ac  add     rsp, 38h
0x14001b1b0  retn
```
