# _stub_DCompositionRemoveCrossDeviceVisualChild

- ea: `0x14003ac10`
- end: `0x14003acb7`
- name: `_stub_DCompositionRemoveCrossDeviceVisualChild`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ac10`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ac59`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ac59`

## string_xrefs

- `0x14003ac3f`: `NtDCompositionRemoveCrossDeviceVisualChild`

## pseudocode

```c
__int64 stub_DCompositionRemoveCrossDeviceVisualChild()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionRemoveCrossDeviceVisualChild();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionRemoveCrossDeviceVisualChild();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ac10  sub     rsp, 48h
0x14003ac14  mov     [rsp+48h+var_28], rcx
0x14003ac19  mov     [rsp+48h+var_20], rdx
0x14003ac1e  mov     [rsp+48h+var_18], r8
0x14003ac23  mov     [rsp+48h+var_10], r9
0x14003ac28  mov     rcx, 138h
0x14003ac2f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ac36  nop     dword ptr [rax+rax+00h]
0x14003ac3b  test    al, al
0x14003ac3d  jz      short loc_14003AC93
0x14003ac3f  lea     rcx, aNtdcomposition_36; "NtDCompositionRemoveCrossDeviceVisualCh"...
0x14003ac46  mov     rdx, 138h
0x14003ac4d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ac54  nop     dword ptr [rax+rax+00h]
0x14003ac59  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ac60  nop     dword ptr [rax+rax+00h]
0x14003ac65  test    al, al
0x14003ac67  jz      short loc_14003AC93
0x14003ac69  lea     rcx, W32pServiceTableFilter
0x14003ac70  mov     edx, cs:W32pServiceLimitFilter
0x14003ac76  mov     rax, 138h
0x14003ac7d  lea     rcx, [rcx+rdx*4]
0x14003ac81  movsx   eax, byte ptr [rcx+rax]
0x14003ac85  or      eax, eax
0x14003ac87  jle     short loc_14003AC8E
0x14003ac89  mov     eax, 0C000001Ch
0x14003ac8e  add     rsp, 48h
0x14003ac92  retn
0x14003ac93  mov     rax, cs:__imp_NtDCompositionRemoveCrossDeviceVisualChild
0x14003ac9a  mov     rcx, [rsp+48h+var_28]
0x14003ac9f  mov     rdx, [rsp+48h+var_20]
0x14003aca4  mov     r8, [rsp+48h+var_18]
0x14003aca9  mov     r9, [rsp+48h+var_10]
0x14003acae  add     rsp, 48h
0x14003acb2  jmp     rax
```
