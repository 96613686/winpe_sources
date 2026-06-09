# _stub_DCompositionGetFrameSurfaceUpdates

- ea: `0x14003a530`
- end: `0x14003a5d7`
- name: `_stub_DCompositionGetFrameSurfaceUpdates`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a530`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a579`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a579`

## string_xrefs

- `0x14003a55f`: `NtDCompositionGetFrameSurfaceUpdates`

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
0x14003a530  sub     rsp, 48h
0x14003a534  mov     [rsp+48h+var_28], rcx
0x14003a539  mov     [rsp+48h+var_20], rdx
0x14003a53e  mov     [rsp+48h+var_18], r8
0x14003a543  mov     [rsp+48h+var_10], r9
0x14003a548  mov     rcx, 12Eh
0x14003a54f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a556  nop     dword ptr [rax+rax+00h]
0x14003a55b  test    al, al
0x14003a55d  jz      short loc_14003A5B3
0x14003a55f  lea     rcx, aNtdcomposition_26; "NtDCompositionGetFrameSurfaceUpdates"
0x14003a566  mov     rdx, 12Eh
0x14003a56d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a574  nop     dword ptr [rax+rax+00h]
0x14003a579  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a580  nop     dword ptr [rax+rax+00h]
0x14003a585  test    al, al
0x14003a587  jz      short loc_14003A5B3
0x14003a589  lea     rcx, W32pServiceTableFilter
0x14003a590  mov     edx, cs:W32pServiceLimitFilter
0x14003a596  mov     rax, 12Eh
0x14003a59d  lea     rcx, [rcx+rdx*4]
0x14003a5a1  movsx   eax, byte ptr [rcx+rax]
0x14003a5a5  or      eax, eax
0x14003a5a7  jle     short loc_14003A5AE
0x14003a5a9  mov     eax, 0C000001Ch
0x14003a5ae  add     rsp, 48h
0x14003a5b2  retn
0x14003a5b3  mov     rax, cs:__imp_NtDCompositionGetFrameSurfaceUpdates
0x14003a5ba  mov     rcx, [rsp+48h+var_28]
0x14003a5bf  mov     rdx, [rsp+48h+var_20]
0x14003a5c4  mov     r8, [rsp+48h+var_18]
0x14003a5c9  mov     r9, [rsp+48h+var_10]
0x14003a5ce  add     rsp, 48h
0x14003a5d2  jmp     rax
```
