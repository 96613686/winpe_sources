# _stub_DCompositionUpdatePointerCapture

- ea: `0x14003b570`
- end: `0x14003b617`
- name: `_stub_DCompositionUpdatePointerCapture`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b570`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b5b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b5b9`

## string_xrefs

- `0x14003b59f`: `NtDCompositionUpdatePointerCapture`

## pseudocode

```c
__int64 stub_DCompositionUpdatePointerCapture()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionUpdatePointerCapture();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionUpdatePointerCapture();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b570  sub     rsp, 48h
0x14003b574  mov     [rsp+48h+var_28], rcx
0x14003b579  mov     [rsp+48h+var_20], rdx
0x14003b57e  mov     [rsp+48h+var_18], r8
0x14003b583  mov     [rsp+48h+var_10], r9
0x14003b588  mov     rcx, 143h
0x14003b58f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b596  nop     dword ptr [rax+rax+00h]
0x14003b59b  test    al, al
0x14003b59d  jz      short loc_14003B5F3
0x14003b59f  lea     rcx, aNtdcomposition_47; "NtDCompositionUpdatePointerCapture"
0x14003b5a6  mov     rdx, 143h
0x14003b5ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b5b4  nop     dword ptr [rax+rax+00h]
0x14003b5b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b5c0  nop     dword ptr [rax+rax+00h]
0x14003b5c5  test    al, al
0x14003b5c7  jz      short loc_14003B5F3
0x14003b5c9  lea     rcx, W32pServiceTableFilter
0x14003b5d0  mov     edx, cs:W32pServiceLimitFilter
0x14003b5d6  mov     rax, 143h
0x14003b5dd  lea     rcx, [rcx+rdx*4]
0x14003b5e1  movsx   eax, byte ptr [rcx+rax]
0x14003b5e5  or      eax, eax
0x14003b5e7  jle     short loc_14003B5EE
0x14003b5e9  mov     eax, 0C000001Ch
0x14003b5ee  add     rsp, 48h
0x14003b5f2  retn
0x14003b5f3  mov     rax, cs:__imp_NtDCompositionUpdatePointerCapture
0x14003b5fa  mov     rcx, [rsp+48h+var_28]
0x14003b5ff  mov     rdx, [rsp+48h+var_20]
0x14003b604  mov     r8, [rsp+48h+var_18]
0x14003b609  mov     r9, [rsp+48h+var_10]
0x14003b60e  add     rsp, 48h
0x14003b612  jmp     rax
```
