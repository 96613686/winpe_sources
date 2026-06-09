# _stub_DxgkCreateHwQueueForUserModeSubmission

- ea: `0x14003bb30`
- end: `0x14003bbd7`
- name: `_stub_DxgkCreateHwQueueForUserModeSubmission`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003bb30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bb79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bb79`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCreateHwQueueForUserModeSubmission` at `0x14003bbb3`

## string_xrefs

- `0x14003bb5f`: `NtDxgkCreateHwQueueForUserModeSubmission`

## pseudocode

```c
__int64 __fastcall stub_DxgkCreateHwQueueForUserModeSubmission(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkCreateHwQueueForUserModeSubmission(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkCreateHwQueueForUserModeSubmission(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[41] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003bb30  sub     rsp, 48h
0x14003bb34  mov     [rsp+48h+var_28], rcx
0x14003bb39  mov     [rsp+48h+var_20], rdx
0x14003bb3e  mov     [rsp+48h+var_18], r8
0x14003bb43  mov     [rsp+48h+var_10], r9
0x14003bb48  mov     rcx, 14Eh
0x14003bb4f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003bb56  nop     dword ptr [rax+rax+00h]
0x14003bb5b  test    al, al
0x14003bb5d  jz      short loc_14003BBB3
0x14003bb5f  lea     rcx, aNtdxgkcreatehw; "NtDxgkCreateHwQueueForUserModeSubmissio"...
0x14003bb66  mov     rdx, 14Eh
0x14003bb6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003bb74  nop     dword ptr [rax+rax+00h]
0x14003bb79  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003bb80  nop     dword ptr [rax+rax+00h]
0x14003bb85  test    al, al
0x14003bb87  jz      short loc_14003BBB3
0x14003bb89  lea     rcx, W32pServiceTableFilter
0x14003bb90  mov     edx, cs:W32pServiceLimitFilter
0x14003bb96  mov     rax, 14Eh
0x14003bb9d  lea     rcx, [rcx+rdx*4]
0x14003bba1  movsx   eax, byte ptr [rcx+rax]
0x14003bba5  or      eax, eax
0x14003bba7  jle     short loc_14003BBAE
0x14003bba9  mov     eax, 0C000001Ch
0x14003bbae  add     rsp, 48h
0x14003bbb2  retn
0x14003bbb3  mov     rax, cs:__imp_NtDxgkCreateHwQueueForUserModeSubmission
0x14003bbba  mov     rcx, [rsp+48h+var_28]
0x14003bbbf  mov     rdx, [rsp+48h+var_20]
0x14003bbc4  mov     r8, [rsp+48h+var_18]
0x14003bbc9  mov     r9, [rsp+48h+var_10]
0x14003bbce  add     rsp, 48h
0x14003bbd2  jmp     rax
```
