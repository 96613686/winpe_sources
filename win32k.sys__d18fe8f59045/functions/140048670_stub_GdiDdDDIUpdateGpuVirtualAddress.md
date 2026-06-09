# _stub_GdiDdDDIUpdateGpuVirtualAddress

- ea: `0x140048670`
- end: `0x140048717`
- name: `_stub_GdiDdDDIUpdateGpuVirtualAddress`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140048670`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400486b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400486b9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIUpdateGpuVirtualAddress` at `0x1400486f3`

## string_xrefs

- `0x14004869f`: `NtGdiDdDDIUpdateGpuVirtualAddress`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIUpdateGpuVirtualAddress(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIUpdateGpuVirtualAddress(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIUpdateGpuVirtualAddress(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[78] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140048670  sub     rsp, 48h
0x140048674  mov     [rsp+48h+var_28], rcx
0x140048679  mov     [rsp+48h+var_20], rdx
0x14004867e  mov     [rsp+48h+var_18], r8
0x140048683  mov     [rsp+48h+var_10], r9
0x140048688  mov     rcx, 273h
0x14004868f  call    cs:__imp_IsWin32KSyscallFiltered
0x140048696  nop     dword ptr [rax+rax+00h]
0x14004869b  test    al, al
0x14004869d  jz      short loc_1400486F3
0x14004869f  lea     rcx, aNtgdiddddiupda_0; "NtGdiDdDDIUpdateGpuVirtualAddress"
0x1400486a6  mov     rdx, 273h
0x1400486ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400486b4  nop     dword ptr [rax+rax+00h]
0x1400486b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400486c0  nop     dword ptr [rax+rax+00h]
0x1400486c5  test    al, al
0x1400486c7  jz      short loc_1400486F3
0x1400486c9  lea     rcx, W32pServiceTableFilter
0x1400486d0  mov     edx, cs:W32pServiceLimitFilter
0x1400486d6  mov     rax, 273h
0x1400486dd  lea     rcx, [rcx+rdx*4]
0x1400486e1  movsx   eax, byte ptr [rcx+rax]
0x1400486e5  or      eax, eax
0x1400486e7  jle     short loc_1400486EE
0x1400486e9  mov     eax, 0C000001Ch
0x1400486ee  add     rsp, 48h
0x1400486f2  retn
0x1400486f3  mov     rax, cs:__imp_NtGdiDdDDIUpdateGpuVirtualAddress
0x1400486fa  mov     rcx, [rsp+48h+var_28]
0x1400486ff  mov     rdx, [rsp+48h+var_20]
0x140048704  mov     r8, [rsp+48h+var_18]
0x140048709  mov     r9, [rsp+48h+var_10]
0x14004870e  add     rsp, 48h
0x140048712  jmp     rax
```
