# Win32kSystemTableAdd

- ea: `0x14001b100`
- end: `0x14001b162`
- name: `Win32kSystemTableAdd`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `ntoskrnl!KeAddSystemServiceTable` at `0x14001b123`
- `ntoskrnl!KeAddSystemServiceTable` at `0x14001b14e`
- `ntoskrnl!KeAddSystemServiceTable` at `0x14001b123`
- `ntoskrnl!KeAddSystemServiceTable` at `0x14001b14e`

## pseudocode

```c
__int64 Win32kSystemTableAdd()
{
  KeAddSystemServiceTable(W32pServiceTable, 0, (unsigned int)W32pServiceLimit, W32pArgumentTable, 1);
  KeAddSystemServiceTable(W32pServiceTableFilter, 0, (unsigned int)W32pServiceLimitFilter, W32pArgumentTableFilter, 2);
  return 0;
}

```

## disassembly

```asm
0x14001b100  sub     rsp, 38h
0x14001b104  mov     r8d, cs:W32pServiceLimit
0x14001b10b  lea     r9, W32pArgumentTable
0x14001b112  xor     edx, edx
0x14001b114  mov     [rsp+38h+var_18], 1
0x14001b11c  lea     rcx, W32pServiceTable
0x14001b123  call    cs:__imp_KeAddSystemServiceTable
0x14001b12a  nop     dword ptr [rax+rax+00h]
0x14001b12f  mov     r8d, cs:W32pServiceLimitFilter
0x14001b136  lea     r9, W32pArgumentTableFilter
0x14001b13d  xor     edx, edx
0x14001b13f  mov     [rsp+38h+var_18], 2
0x14001b147  lea     rcx, W32pServiceTableFilter
0x14001b14e  call    cs:__imp_KeAddSystemServiceTable
0x14001b155  nop     dword ptr [rax+rax+00h]
0x14001b15a  xor     eax, eax
0x14001b15c  add     rsp, 38h
0x14001b160  retn
```
