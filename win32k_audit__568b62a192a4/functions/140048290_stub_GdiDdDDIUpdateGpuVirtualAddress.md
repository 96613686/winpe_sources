# _stub_GdiDdDDIUpdateGpuVirtualAddress

- ea: `0x140048290`
- end: `0x140048337`
- name: `_stub_GdiDdDDIUpdateGpuVirtualAddress`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140048290`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400482d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400482d9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIUpdateGpuVirtualAddress` at `0x140048313`

## string_xrefs

- `0x1400482bf`: `NtGdiDdDDIUpdateGpuVirtualAddress`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[78] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140048290  sub     rsp, 48h
0x140048294  mov     [rsp+48h+var_28], rcx
0x140048299  mov     [rsp+48h+var_20], rdx
0x14004829e  mov     [rsp+48h+var_18], r8
0x1400482a3  mov     [rsp+48h+var_10], r9
0x1400482a8  mov     rcx, 270h
0x1400482af  call    cs:__imp_IsWin32KSyscallFiltered
0x1400482b6  nop     dword ptr [rax+rax+00h]
0x1400482bb  test    al, al
0x1400482bd  jz      short loc_140048313
0x1400482bf  lea     rcx, aNtgdiddddiupda_0; "NtGdiDdDDIUpdateGpuVirtualAddress"
0x1400482c6  mov     rdx, 270h
0x1400482cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400482d4  nop     dword ptr [rax+rax+00h]
0x1400482d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400482e0  nop     dword ptr [rax+rax+00h]
0x1400482e5  test    al, al
0x1400482e7  jz      short loc_140048313
0x1400482e9  lea     rcx, W32pServiceTableFilter
0x1400482f0  mov     edx, cs:W32pServiceLimitFilter
0x1400482f6  mov     rax, 270h
0x1400482fd  lea     rcx, [rcx+rdx*4]
0x140048301  movsx   eax, byte ptr [rcx+rax]
0x140048305  or      eax, eax
0x140048307  jle     short loc_14004830E
0x140048309  mov     eax, 0C000001Ch
0x14004830e  add     rsp, 48h
0x140048312  retn
0x140048313  mov     rax, cs:__imp_NtGdiDdDDIUpdateGpuVirtualAddress
0x14004831a  mov     rcx, [rsp+48h+var_28]
0x14004831f  mov     rdx, [rsp+48h+var_20]
0x140048324  mov     r8, [rsp+48h+var_18]
0x140048329  mov     r9, [rsp+48h+var_10]
0x14004832e  add     rsp, 48h
0x140048332  jmp     rax
```
