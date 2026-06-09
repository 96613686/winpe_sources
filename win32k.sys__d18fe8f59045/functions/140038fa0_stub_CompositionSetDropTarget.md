# _stub_CompositionSetDropTarget

- ea: `0x140038fa0`
- end: `0x140039047`
- name: `_stub_CompositionSetDropTarget`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038fa0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038fe9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038fe9`

## string_xrefs

- `0x140038fcf`: `NtCompositionSetDropTarget`

## pseudocode

```c
__int64 stub_CompositionSetDropTarget()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtCompositionSetDropTarget();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtCompositionSetDropTarget();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140038fa0  sub     rsp, 48h
0x140038fa4  mov     [rsp+48h+var_28], rcx
0x140038fa9  mov     [rsp+48h+var_20], rdx
0x140038fae  mov     [rsp+48h+var_18], r8
0x140038fb3  mov     [rsp+48h+var_10], r9
0x140038fb8  mov     rcx, 10Ch
0x140038fbf  call    cs:__imp_IsWin32KSyscallFiltered
0x140038fc6  nop     dword ptr [rax+rax+00h]
0x140038fcb  test    al, al
0x140038fcd  jz      short loc_140039023
0x140038fcf  lea     rcx, aNtcompositions; "NtCompositionSetDropTarget"
0x140038fd6  mov     rdx, 10Ch
0x140038fdd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038fe4  nop     dword ptr [rax+rax+00h]
0x140038fe9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038ff0  nop     dword ptr [rax+rax+00h]
0x140038ff5  test    al, al
0x140038ff7  jz      short loc_140039023
0x140038ff9  lea     rcx, W32pServiceTableFilter
0x140039000  mov     edx, cs:W32pServiceLimitFilter
0x140039006  mov     rax, 10Ch
0x14003900d  lea     rcx, [rcx+rdx*4]
0x140039011  movsx   eax, byte ptr [rcx+rax]
0x140039015  or      eax, eax
0x140039017  jle     short loc_14003901E
0x140039019  mov     eax, 0C000001Ch
0x14003901e  add     rsp, 48h
0x140039022  retn
0x140039023  mov     rax, cs:__imp_NtCompositionSetDropTarget
0x14003902a  mov     rcx, [rsp+48h+var_28]
0x14003902f  mov     rdx, [rsp+48h+var_20]
0x140039034  mov     r8, [rsp+48h+var_18]
0x140039039  mov     r9, [rsp+48h+var_10]
0x14003903e  add     rsp, 48h
0x140039042  jmp     rax
```
