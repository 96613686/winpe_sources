# _stub_DCompositionRemoveCrossDeviceVisualChild

- ea: `0x14003ade0`
- end: `0x14003ae87`
- name: `_stub_DCompositionRemoveCrossDeviceVisualChild`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ade0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ae29`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ae29`

## string_xrefs

- `0x14003ae0f`: `NtDCompositionRemoveCrossDeviceVisualChild`

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
0x14003ade0  sub     rsp, 48h
0x14003ade4  mov     [rsp+48h+var_28], rcx
0x14003ade9  mov     [rsp+48h+var_20], rdx
0x14003adee  mov     [rsp+48h+var_18], r8
0x14003adf3  mov     [rsp+48h+var_10], r9
0x14003adf8  mov     rcx, 138h
0x14003adff  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ae06  nop     dword ptr [rax+rax+00h]
0x14003ae0b  test    al, al
0x14003ae0d  jz      short loc_14003AE63
0x14003ae0f  lea     rcx, aNtdcomposition_36; "NtDCompositionRemoveCrossDeviceVisualCh"...
0x14003ae16  mov     rdx, 138h
0x14003ae1d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ae24  nop     dword ptr [rax+rax+00h]
0x14003ae29  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ae30  nop     dword ptr [rax+rax+00h]
0x14003ae35  test    al, al
0x14003ae37  jz      short loc_14003AE63
0x14003ae39  lea     rcx, W32pServiceTableFilter
0x14003ae40  mov     edx, cs:W32pServiceLimitFilter
0x14003ae46  mov     rax, 138h
0x14003ae4d  lea     rcx, [rcx+rdx*4]
0x14003ae51  movsx   eax, byte ptr [rcx+rax]
0x14003ae55  or      eax, eax
0x14003ae57  jle     short loc_14003AE5E
0x14003ae59  mov     eax, 0C000001Ch
0x14003ae5e  add     rsp, 48h
0x14003ae62  retn
0x14003ae63  mov     rax, cs:__imp_NtDCompositionRemoveCrossDeviceVisualChild
0x14003ae6a  mov     rcx, [rsp+48h+var_28]
0x14003ae6f  mov     rdx, [rsp+48h+var_20]
0x14003ae74  mov     r8, [rsp+48h+var_18]
0x14003ae79  mov     r9, [rsp+48h+var_10]
0x14003ae7e  add     rsp, 48h
0x14003ae82  jmp     rax
```
