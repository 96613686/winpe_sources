# _stub_DxgkCreateHwQueueForUserModeSubmission

- ea: `0x14003bdb0`
- end: `0x14003be57`
- name: `_stub_DxgkCreateHwQueueForUserModeSubmission`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003bdb0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bdf9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bdf9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCreateHwQueueForUserModeSubmission` at `0x14003be33`

## string_xrefs

- `0x14003bddf`: `NtDxgkCreateHwQueueForUserModeSubmission`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[41] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003bdb0  sub     rsp, 48h
0x14003bdb4  mov     [rsp+48h+var_28], rcx
0x14003bdb9  mov     [rsp+48h+var_20], rdx
0x14003bdbe  mov     [rsp+48h+var_18], r8
0x14003bdc3  mov     [rsp+48h+var_10], r9
0x14003bdc8  mov     rcx, 14Fh
0x14003bdcf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003bdd6  nop     dword ptr [rax+rax+00h]
0x14003bddb  test    al, al
0x14003bddd  jz      short loc_14003BE33
0x14003bddf  lea     rcx, aNtdxgkcreatehw; "NtDxgkCreateHwQueueForUserModeSubmissio"...
0x14003bde6  mov     rdx, 14Fh
0x14003bded  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003bdf4  nop     dword ptr [rax+rax+00h]
0x14003bdf9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003be00  nop     dword ptr [rax+rax+00h]
0x14003be05  test    al, al
0x14003be07  jz      short loc_14003BE33
0x14003be09  lea     rcx, W32pServiceTableFilter
0x14003be10  mov     edx, cs:W32pServiceLimitFilter
0x14003be16  mov     rax, 14Fh
0x14003be1d  lea     rcx, [rcx+rdx*4]
0x14003be21  movsx   eax, byte ptr [rcx+rax]
0x14003be25  or      eax, eax
0x14003be27  jle     short loc_14003BE2E
0x14003be29  mov     eax, 0C000001Ch
0x14003be2e  add     rsp, 48h
0x14003be32  retn
0x14003be33  mov     rax, cs:__imp_NtDxgkCreateHwQueueForUserModeSubmission
0x14003be3a  mov     rcx, [rsp+48h+var_28]
0x14003be3f  mov     rdx, [rsp+48h+var_20]
0x14003be44  mov     r8, [rsp+48h+var_18]
0x14003be49  mov     r9, [rsp+48h+var_10]
0x14003be4e  add     rsp, 48h
0x14003be52  jmp     rax
```
