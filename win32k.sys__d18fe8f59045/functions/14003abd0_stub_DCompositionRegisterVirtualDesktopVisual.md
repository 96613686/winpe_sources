# _stub_DCompositionRegisterVirtualDesktopVisual

- ea: `0x14003abd0`
- end: `0x14003ac77`
- name: `_stub_DCompositionRegisterVirtualDesktopVisual`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003abd0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ac19`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ac19`

## string_xrefs

- `0x14003abff`: `NtDCompositionRegisterVirtualDesktopVisual`

## pseudocode

```c
__int64 stub_DCompositionRegisterVirtualDesktopVisual()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionRegisterVirtualDesktopVisual();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionRegisterVirtualDesktopVisual();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003abd0  sub     rsp, 48h
0x14003abd4  mov     [rsp+48h+var_28], rcx
0x14003abd9  mov     [rsp+48h+var_20], rdx
0x14003abde  mov     [rsp+48h+var_18], r8
0x14003abe3  mov     [rsp+48h+var_10], r9
0x14003abe8  mov     rcx, 135h
0x14003abef  call    cs:__imp_IsWin32KSyscallFiltered
0x14003abf6  nop     dword ptr [rax+rax+00h]
0x14003abfb  test    al, al
0x14003abfd  jz      short loc_14003AC53
0x14003abff  lea     rcx, aNtdcomposition_33; "NtDCompositionRegisterVirtualDesktopVis"...
0x14003ac06  mov     rdx, 135h
0x14003ac0d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ac14  nop     dword ptr [rax+rax+00h]
0x14003ac19  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ac20  nop     dword ptr [rax+rax+00h]
0x14003ac25  test    al, al
0x14003ac27  jz      short loc_14003AC53
0x14003ac29  lea     rcx, W32pServiceTableFilter
0x14003ac30  mov     edx, cs:W32pServiceLimitFilter
0x14003ac36  mov     rax, 135h
0x14003ac3d  lea     rcx, [rcx+rdx*4]
0x14003ac41  movsx   eax, byte ptr [rcx+rax]
0x14003ac45  or      eax, eax
0x14003ac47  jle     short loc_14003AC4E
0x14003ac49  mov     eax, 0C000001Ch
0x14003ac4e  add     rsp, 48h
0x14003ac52  retn
0x14003ac53  mov     rax, cs:__imp_NtDCompositionRegisterVirtualDesktopVisual
0x14003ac5a  mov     rcx, [rsp+48h+var_28]
0x14003ac5f  mov     rdx, [rsp+48h+var_20]
0x14003ac64  mov     r8, [rsp+48h+var_18]
0x14003ac69  mov     r9, [rsp+48h+var_10]
0x14003ac6e  add     rsp, 48h
0x14003ac72  jmp     rax
```
