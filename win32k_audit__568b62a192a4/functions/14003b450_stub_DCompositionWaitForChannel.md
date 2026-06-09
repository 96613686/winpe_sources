# _stub_DCompositionWaitForChannel

- ea: `0x14003b450`
- end: `0x14003b4f7`
- name: `_stub_DCompositionWaitForChannel`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b450`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b499`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b499`

## string_xrefs

- `0x14003b47f`: `NtDCompositionWaitForChannel`

## pseudocode

```c
__int64 stub_DCompositionWaitForChannel()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionWaitForChannel();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionWaitForChannel();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b450  sub     rsp, 48h
0x14003b454  mov     [rsp+48h+var_28], rcx
0x14003b459  mov     [rsp+48h+var_20], rdx
0x14003b45e  mov     [rsp+48h+var_18], r8
0x14003b463  mov     [rsp+48h+var_10], r9
0x14003b468  mov     rcx, 144h
0x14003b46f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b476  nop     dword ptr [rax+rax+00h]
0x14003b47b  test    al, al
0x14003b47d  jz      short loc_14003B4D3
0x14003b47f  lea     rcx, aNtdcomposition_48; "NtDCompositionWaitForChannel"
0x14003b486  mov     rdx, 144h
0x14003b48d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b494  nop     dword ptr [rax+rax+00h]
0x14003b499  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b4a0  nop     dword ptr [rax+rax+00h]
0x14003b4a5  test    al, al
0x14003b4a7  jz      short loc_14003B4D3
0x14003b4a9  lea     rcx, W32pServiceTableFilter
0x14003b4b0  mov     edx, cs:W32pServiceLimitFilter
0x14003b4b6  mov     rax, 144h
0x14003b4bd  lea     rcx, [rcx+rdx*4]
0x14003b4c1  movsx   eax, byte ptr [rcx+rax]
0x14003b4c5  or      eax, eax
0x14003b4c7  jle     short loc_14003B4CE
0x14003b4c9  mov     eax, 0C000001Ch
0x14003b4ce  add     rsp, 48h
0x14003b4d2  retn
0x14003b4d3  mov     rax, cs:__imp_NtDCompositionWaitForChannel
0x14003b4da  mov     rcx, [rsp+48h+var_28]
0x14003b4df  mov     rdx, [rsp+48h+var_20]
0x14003b4e4  mov     r8, [rsp+48h+var_18]
0x14003b4e9  mov     r9, [rsp+48h+var_10]
0x14003b4ee  add     rsp, 48h
0x14003b4f2  jmp     rax
```
