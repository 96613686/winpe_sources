# _stub_CompositionSetDropTarget

- ea: `0x140038dd0`
- end: `0x140038e77`
- name: `_stub_CompositionSetDropTarget`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038dd0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038e19`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038e19`

## string_xrefs

- `0x140038dff`: `NtCompositionSetDropTarget`

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
0x140038dd0  sub     rsp, 48h
0x140038dd4  mov     [rsp+48h+var_28], rcx
0x140038dd9  mov     [rsp+48h+var_20], rdx
0x140038dde  mov     [rsp+48h+var_18], r8
0x140038de3  mov     [rsp+48h+var_10], r9
0x140038de8  mov     rcx, 10Ch
0x140038def  call    cs:__imp_IsWin32KSyscallFiltered
0x140038df6  nop     dword ptr [rax+rax+00h]
0x140038dfb  test    al, al
0x140038dfd  jz      short loc_140038E53
0x140038dff  lea     rcx, aNtcompositions; "NtCompositionSetDropTarget"
0x140038e06  mov     rdx, 10Ch
0x140038e0d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038e14  nop     dword ptr [rax+rax+00h]
0x140038e19  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038e20  nop     dword ptr [rax+rax+00h]
0x140038e25  test    al, al
0x140038e27  jz      short loc_140038E53
0x140038e29  lea     rcx, W32pServiceTableFilter
0x140038e30  mov     edx, cs:W32pServiceLimitFilter
0x140038e36  mov     rax, 10Ch
0x140038e3d  lea     rcx, [rcx+rdx*4]
0x140038e41  movsx   eax, byte ptr [rcx+rax]
0x140038e45  or      eax, eax
0x140038e47  jle     short loc_140038E4E
0x140038e49  mov     eax, 0C000001Ch
0x140038e4e  add     rsp, 48h
0x140038e52  retn
0x140038e53  mov     rax, cs:__imp_NtCompositionSetDropTarget
0x140038e5a  mov     rcx, [rsp+48h+var_28]
0x140038e5f  mov     rdx, [rsp+48h+var_20]
0x140038e64  mov     r8, [rsp+48h+var_18]
0x140038e69  mov     r9, [rsp+48h+var_10]
0x140038e6e  add     rsp, 48h
0x140038e72  jmp     rax
```
