# _stub_DCompositionGetFrameId

- ea: `0x14003a270`
- end: `0x14003a317`
- name: `_stub_DCompositionGetFrameId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a270`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a2b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a2b9`

## string_xrefs

- `0x14003a29f`: `NtDCompositionGetFrameId`

## pseudocode

```c
__int64 stub_DCompositionGetFrameId()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetFrameId();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetFrameId();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a270  sub     rsp, 48h
0x14003a274  mov     [rsp+48h+var_28], rcx
0x14003a279  mov     [rsp+48h+var_20], rdx
0x14003a27e  mov     [rsp+48h+var_18], r8
0x14003a283  mov     [rsp+48h+var_10], r9
0x14003a288  mov     rcx, 12Ah
0x14003a28f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a296  nop     dword ptr [rax+rax+00h]
0x14003a29b  test    al, al
0x14003a29d  jz      short loc_14003A2F3
0x14003a29f  lea     rcx, aNtdcomposition_22; "NtDCompositionGetFrameId"
0x14003a2a6  mov     rdx, 12Ah
0x14003a2ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a2b4  nop     dword ptr [rax+rax+00h]
0x14003a2b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a2c0  nop     dword ptr [rax+rax+00h]
0x14003a2c5  test    al, al
0x14003a2c7  jz      short loc_14003A2F3
0x14003a2c9  lea     rcx, W32pServiceTableFilter
0x14003a2d0  mov     edx, cs:W32pServiceLimitFilter
0x14003a2d6  mov     rax, 12Ah
0x14003a2dd  lea     rcx, [rcx+rdx*4]
0x14003a2e1  movsx   eax, byte ptr [rcx+rax]
0x14003a2e5  or      eax, eax
0x14003a2e7  jle     short loc_14003A2EE
0x14003a2e9  mov     eax, 0C000001Ch
0x14003a2ee  add     rsp, 48h
0x14003a2f2  retn
0x14003a2f3  mov     rax, cs:__imp_NtDCompositionGetFrameId
0x14003a2fa  mov     rcx, [rsp+48h+var_28]
0x14003a2ff  mov     rdx, [rsp+48h+var_20]
0x14003a304  mov     r8, [rsp+48h+var_18]
0x14003a309  mov     r9, [rsp+48h+var_10]
0x14003a30e  add     rsp, 48h
0x14003a312  jmp     rax
```
