# _stub_DCompositionSyncWait

- ea: `0x14003b360`
- end: `0x14003b407`
- name: `_stub_DCompositionSyncWait`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b360`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b3a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b3a9`

## string_xrefs

- `0x14003b38f`: `NtDCompositionSyncWait`

## pseudocode

```c
__int64 stub_DCompositionSyncWait()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSyncWait();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSyncWait();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b360  sub     rsp, 48h
0x14003b364  mov     [rsp+48h+var_28], rcx
0x14003b369  mov     [rsp+48h+var_20], rdx
0x14003b36e  mov     [rsp+48h+var_18], r8
0x14003b373  mov     [rsp+48h+var_10], r9
0x14003b378  mov     rcx, 140h
0x14003b37f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b386  nop     dword ptr [rax+rax+00h]
0x14003b38b  test    al, al
0x14003b38d  jz      short loc_14003B3E3
0x14003b38f  lea     rcx, aNtdcomposition_44; "NtDCompositionSyncWait"
0x14003b396  mov     rdx, 140h
0x14003b39d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b3a4  nop     dword ptr [rax+rax+00h]
0x14003b3a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b3b0  nop     dword ptr [rax+rax+00h]
0x14003b3b5  test    al, al
0x14003b3b7  jz      short loc_14003B3E3
0x14003b3b9  lea     rcx, W32pServiceTableFilter
0x14003b3c0  mov     edx, cs:W32pServiceLimitFilter
0x14003b3c6  mov     rax, 140h
0x14003b3cd  lea     rcx, [rcx+rdx*4]
0x14003b3d1  movsx   eax, byte ptr [rcx+rax]
0x14003b3d5  or      eax, eax
0x14003b3d7  jle     short loc_14003B3DE
0x14003b3d9  mov     eax, 0C000001Ch
0x14003b3de  add     rsp, 48h
0x14003b3e2  retn
0x14003b3e3  mov     rax, cs:__imp_NtDCompositionSyncWait
0x14003b3ea  mov     rcx, [rsp+48h+var_28]
0x14003b3ef  mov     rdx, [rsp+48h+var_20]
0x14003b3f4  mov     r8, [rsp+48h+var_18]
0x14003b3f9  mov     r9, [rsp+48h+var_10]
0x14003b3fe  add     rsp, 48h
0x14003b402  jmp     rax
```
