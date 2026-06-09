# _stub_DCompositionCommitSynchronizationObject

- ea: `0x140039730`
- end: `0x1400397d7`
- name: `_stub_DCompositionCommitSynchronizationObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039730`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039779`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039779`

## string_xrefs

- `0x14003975f`: `NtDCompositionCommitSynchronizationObject`

## pseudocode

```c
__int64 stub_DCompositionCommitSynchronizationObject()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCommitSynchronizationObject();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCommitSynchronizationObject();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039730  sub     rsp, 48h
0x140039734  mov     [rsp+48h+var_28], rcx
0x140039739  mov     [rsp+48h+var_20], rdx
0x14003973e  mov     [rsp+48h+var_18], r8
0x140039743  mov     [rsp+48h+var_10], r9
0x140039748  mov     rcx, 117h
0x14003974f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039756  nop     dword ptr [rax+rax+00h]
0x14003975b  test    al, al
0x14003975d  jz      short loc_1400397B3
0x14003975f  lea     rcx, aNtdcomposition_3; "NtDCompositionCommitSynchronizationObje"...
0x140039766  mov     rdx, 117h
0x14003976d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039774  nop     dword ptr [rax+rax+00h]
0x140039779  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039780  nop     dword ptr [rax+rax+00h]
0x140039785  test    al, al
0x140039787  jz      short loc_1400397B3
0x140039789  lea     rcx, W32pServiceTableFilter
0x140039790  mov     edx, cs:W32pServiceLimitFilter
0x140039796  mov     rax, 117h
0x14003979d  lea     rcx, [rcx+rdx*4]
0x1400397a1  movsx   eax, byte ptr [rcx+rax]
0x1400397a5  or      eax, eax
0x1400397a7  jle     short loc_1400397AE
0x1400397a9  mov     eax, 0C000001Ch
0x1400397ae  add     rsp, 48h
0x1400397b2  retn
0x1400397b3  mov     rax, cs:__imp_NtDCompositionCommitSynchronizationObject
0x1400397ba  mov     rcx, [rsp+48h+var_28]
0x1400397bf  mov     rdx, [rsp+48h+var_20]
0x1400397c4  mov     r8, [rsp+48h+var_18]
0x1400397c9  mov     r9, [rsp+48h+var_10]
0x1400397ce  add     rsp, 48h
0x1400397d2  jmp     rax
```
