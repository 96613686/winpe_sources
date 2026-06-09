# _stub_DuplicateCompositionInputSink

- ea: `0x14003b830`
- end: `0x14003b8d7`
- name: `_stub_DuplicateCompositionInputSink`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b830`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b879`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b879`

## string_xrefs

- `0x14003b85f`: `NtDuplicateCompositionInputSink`

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
0x14003b830  sub     rsp, 48h
0x14003b834  mov     [rsp+48h+var_28], rcx
0x14003b839  mov     [rsp+48h+var_20], rdx
0x14003b83e  mov     [rsp+48h+var_18], r8
0x14003b843  mov     [rsp+48h+var_10], r9
0x14003b848  mov     rcx, 147h
0x14003b84f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b856  nop     dword ptr [rax+rax+00h]
0x14003b85b  test    al, al
0x14003b85d  jz      short loc_14003B8B3
0x14003b85f  lea     rcx, aNtduplicatecom; "NtDuplicateCompositionInputSink"
0x14003b866  mov     rdx, 147h
0x14003b86d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b874  nop     dword ptr [rax+rax+00h]
0x14003b879  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b880  nop     dword ptr [rax+rax+00h]
0x14003b885  test    al, al
0x14003b887  jz      short loc_14003B8B3
0x14003b889  lea     rcx, W32pServiceTableFilter
0x14003b890  mov     edx, cs:W32pServiceLimitFilter
0x14003b896  mov     rax, 147h
0x14003b89d  lea     rcx, [rcx+rdx*4]
0x14003b8a1  movsx   eax, byte ptr [rcx+rax]
0x14003b8a5  or      eax, eax
0x14003b8a7  jle     short loc_14003B8AE
0x14003b8a9  mov     eax, 0C000001Ch
0x14003b8ae  add     rsp, 48h
0x14003b8b2  retn
0x14003b8b3  mov     rax, cs:__imp_NtDuplicateCompositionInputSink
0x14003b8ba  mov     rcx, [rsp+48h+var_28]
0x14003b8bf  mov     rdx, [rsp+48h+var_20]
0x14003b8c4  mov     r8, [rsp+48h+var_18]
0x14003b8c9  mov     r9, [rsp+48h+var_10]
0x14003b8ce  add     rsp, 48h
0x14003b8d2  jmp     rax
```
