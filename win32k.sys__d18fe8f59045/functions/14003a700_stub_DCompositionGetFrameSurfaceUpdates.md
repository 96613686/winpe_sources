# _stub_DCompositionGetFrameSurfaceUpdates

- ea: `0x14003a700`
- end: `0x14003a7a7`
- name: `_stub_DCompositionGetFrameSurfaceUpdates`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a700`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a749`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a749`

## string_xrefs

- `0x14003a72f`: `NtDCompositionGetFrameSurfaceUpdates`

## pseudocode

```c
__int64 stub_DCompositionGetFrameSurfaceUpdates()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetFrameSurfaceUpdates();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetFrameSurfaceUpdates();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a700  sub     rsp, 48h
0x14003a704  mov     [rsp+48h+var_28], rcx
0x14003a709  mov     [rsp+48h+var_20], rdx
0x14003a70e  mov     [rsp+48h+var_18], r8
0x14003a713  mov     [rsp+48h+var_10], r9
0x14003a718  mov     rcx, 12Eh
0x14003a71f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a726  nop     dword ptr [rax+rax+00h]
0x14003a72b  test    al, al
0x14003a72d  jz      short loc_14003A783
0x14003a72f  lea     rcx, aNtdcomposition_26; "NtDCompositionGetFrameSurfaceUpdates"
0x14003a736  mov     rdx, 12Eh
0x14003a73d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a744  nop     dword ptr [rax+rax+00h]
0x14003a749  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a750  nop     dword ptr [rax+rax+00h]
0x14003a755  test    al, al
0x14003a757  jz      short loc_14003A783
0x14003a759  lea     rcx, W32pServiceTableFilter
0x14003a760  mov     edx, cs:W32pServiceLimitFilter
0x14003a766  mov     rax, 12Eh
0x14003a76d  lea     rcx, [rcx+rdx*4]
0x14003a771  movsx   eax, byte ptr [rcx+rax]
0x14003a775  or      eax, eax
0x14003a777  jle     short loc_14003A77E
0x14003a779  mov     eax, 0C000001Ch
0x14003a77e  add     rsp, 48h
0x14003a782  retn
0x14003a783  mov     rax, cs:__imp_NtDCompositionGetFrameSurfaceUpdates
0x14003a78a  mov     rcx, [rsp+48h+var_28]
0x14003a78f  mov     rdx, [rsp+48h+var_20]
0x14003a794  mov     r8, [rsp+48h+var_18]
0x14003a799  mov     r9, [rsp+48h+var_10]
0x14003a79e  add     rsp, 48h
0x14003a7a2  jmp     rax
```
