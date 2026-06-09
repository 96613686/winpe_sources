# _stub_DuplicateCompositionInputSink

- ea: `0x14003b660`
- end: `0x14003b707`
- name: `_stub_DuplicateCompositionInputSink`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b660`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b6a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b6a9`

## string_xrefs

- `0x14003b68f`: `NtDuplicateCompositionInputSink`

## pseudocode

```c
__int64 stub_DuplicateCompositionInputSink()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDuplicateCompositionInputSink();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDuplicateCompositionInputSink();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b660  sub     rsp, 48h
0x14003b664  mov     [rsp+48h+var_28], rcx
0x14003b669  mov     [rsp+48h+var_20], rdx
0x14003b66e  mov     [rsp+48h+var_18], r8
0x14003b673  mov     [rsp+48h+var_10], r9
0x14003b678  mov     rcx, 147h
0x14003b67f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b686  nop     dword ptr [rax+rax+00h]
0x14003b68b  test    al, al
0x14003b68d  jz      short loc_14003B6E3
0x14003b68f  lea     rcx, aNtduplicatecom; "NtDuplicateCompositionInputSink"
0x14003b696  mov     rdx, 147h
0x14003b69d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b6a4  nop     dword ptr [rax+rax+00h]
0x14003b6a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b6b0  nop     dword ptr [rax+rax+00h]
0x14003b6b5  test    al, al
0x14003b6b7  jz      short loc_14003B6E3
0x14003b6b9  lea     rcx, W32pServiceTableFilter
0x14003b6c0  mov     edx, cs:W32pServiceLimitFilter
0x14003b6c6  mov     rax, 147h
0x14003b6cd  lea     rcx, [rcx+rdx*4]
0x14003b6d1  movsx   eax, byte ptr [rcx+rax]
0x14003b6d5  or      eax, eax
0x14003b6d7  jle     short loc_14003B6DE
0x14003b6d9  mov     eax, 0C000001Ch
0x14003b6de  add     rsp, 48h
0x14003b6e2  retn
0x14003b6e3  mov     rax, cs:__imp_NtDuplicateCompositionInputSink
0x14003b6ea  mov     rcx, [rsp+48h+var_28]
0x14003b6ef  mov     rdx, [rsp+48h+var_20]
0x14003b6f4  mov     r8, [rsp+48h+var_18]
0x14003b6f9  mov     r9, [rsp+48h+var_10]
0x14003b6fe  add     rsp, 48h
0x14003b702  jmp     rax
```
