# _stub_DCompositionCommitSynchronizationObject

- ea: `0x140039560`
- end: `0x140039607`
- name: `_stub_DCompositionCommitSynchronizationObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039560`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400395a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400395a9`

## string_xrefs

- `0x14003958f`: `NtDCompositionCommitSynchronizationObject`

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
0x140039560  sub     rsp, 48h
0x140039564  mov     [rsp+48h+var_28], rcx
0x140039569  mov     [rsp+48h+var_20], rdx
0x14003956e  mov     [rsp+48h+var_18], r8
0x140039573  mov     [rsp+48h+var_10], r9
0x140039578  mov     rcx, 117h
0x14003957f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039586  nop     dword ptr [rax+rax+00h]
0x14003958b  test    al, al
0x14003958d  jz      short loc_1400395E3
0x14003958f  lea     rcx, aNtdcomposition_3; "NtDCompositionCommitSynchronizationObje"...
0x140039596  mov     rdx, 117h
0x14003959d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400395a4  nop     dword ptr [rax+rax+00h]
0x1400395a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400395b0  nop     dword ptr [rax+rax+00h]
0x1400395b5  test    al, al
0x1400395b7  jz      short loc_1400395E3
0x1400395b9  lea     rcx, W32pServiceTableFilter
0x1400395c0  mov     edx, cs:W32pServiceLimitFilter
0x1400395c6  mov     rax, 117h
0x1400395cd  lea     rcx, [rcx+rdx*4]
0x1400395d1  movsx   eax, byte ptr [rcx+rax]
0x1400395d5  or      eax, eax
0x1400395d7  jle     short loc_1400395DE
0x1400395d9  mov     eax, 0C000001Ch
0x1400395de  add     rsp, 48h
0x1400395e2  retn
0x1400395e3  mov     rax, cs:__imp_NtDCompositionCommitSynchronizationObject
0x1400395ea  mov     rcx, [rsp+48h+var_28]
0x1400395ef  mov     rdx, [rsp+48h+var_20]
0x1400395f4  mov     r8, [rsp+48h+var_18]
0x1400395f9  mov     r9, [rsp+48h+var_10]
0x1400395fe  add     rsp, 48h
0x140039602  jmp     rax
```
