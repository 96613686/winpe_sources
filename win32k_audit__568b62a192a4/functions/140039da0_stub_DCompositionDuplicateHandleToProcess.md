# _stub_DCompositionDuplicateHandleToProcess

- ea: `0x140039da0`
- end: `0x140039e47`
- name: `_stub_DCompositionDuplicateHandleToProcess`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039da0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039de9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039de9`

## string_xrefs

- `0x140039dcf`: `NtDCompositionDuplicateHandleToProcess`

## pseudocode

```c
__int64 stub_DCompositionDuplicateHandleToProcess()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionDuplicateHandleToProcess();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionDuplicateHandleToProcess();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039da0  sub     rsp, 48h
0x140039da4  mov     [rsp+48h+var_28], rcx
0x140039da9  mov     [rsp+48h+var_20], rdx
0x140039dae  mov     [rsp+48h+var_18], r8
0x140039db3  mov     [rsp+48h+var_10], r9
0x140039db8  mov     rcx, 123h
0x140039dbf  call    cs:__imp_IsWin32KSyscallFiltered
0x140039dc6  nop     dword ptr [rax+rax+00h]
0x140039dcb  test    al, al
0x140039dcd  jz      short loc_140039E23
0x140039dcf  lea     rcx, aNtdcomposition_15; "NtDCompositionDuplicateHandleToProcess"
0x140039dd6  mov     rdx, 123h
0x140039ddd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039de4  nop     dword ptr [rax+rax+00h]
0x140039de9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039df0  nop     dword ptr [rax+rax+00h]
0x140039df5  test    al, al
0x140039df7  jz      short loc_140039E23
0x140039df9  lea     rcx, W32pServiceTableFilter
0x140039e00  mov     edx, cs:W32pServiceLimitFilter
0x140039e06  mov     rax, 123h
0x140039e0d  lea     rcx, [rcx+rdx*4]
0x140039e11  movsx   eax, byte ptr [rcx+rax]
0x140039e15  or      eax, eax
0x140039e17  jle     short loc_140039E1E
0x140039e19  mov     eax, 0C000001Ch
0x140039e1e  add     rsp, 48h
0x140039e22  retn
0x140039e23  mov     rax, cs:__imp_NtDCompositionDuplicateHandleToProcess
0x140039e2a  mov     rcx, [rsp+48h+var_28]
0x140039e2f  mov     rdx, [rsp+48h+var_20]
0x140039e34  mov     r8, [rsp+48h+var_18]
0x140039e39  mov     r9, [rsp+48h+var_10]
0x140039e3e  add     rsp, 48h
0x140039e42  jmp     rax
```
