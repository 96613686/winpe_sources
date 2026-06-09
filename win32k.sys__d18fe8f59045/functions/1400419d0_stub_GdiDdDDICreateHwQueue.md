# _stub_GdiDdDDICreateHwQueue

- ea: `0x1400419d0`
- end: `0x140041a77`
- name: `_stub_GdiDdDDICreateHwQueue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400419d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041a19`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041a19`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateHwQueue` at `0x140041a53`

## string_xrefs

- `0x1400419ff`: `NtGdiDdDDICreateHwQueue`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateHwQueue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateHwQueue(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateHwQueue(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400419d0  sub     rsp, 48h
0x1400419d4  mov     [rsp+48h+var_28], rcx
0x1400419d9  mov     [rsp+48h+var_20], rdx
0x1400419de  mov     [rsp+48h+var_18], r8
0x1400419e3  mov     [rsp+48h+var_10], r9
0x1400419e8  mov     rcx, 1D5h
0x1400419ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400419f6  nop     dword ptr [rax+rax+00h]
0x1400419fb  test    al, al
0x1400419fd  jz      short loc_140041A53
0x1400419ff  lea     rcx, aNtgdiddddicrea_6; "NtGdiDdDDICreateHwQueue"
0x140041a06  mov     rdx, 1D5h
0x140041a0d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041a14  nop     dword ptr [rax+rax+00h]
0x140041a19  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041a20  nop     dword ptr [rax+rax+00h]
0x140041a25  test    al, al
0x140041a27  jz      short loc_140041A53
0x140041a29  lea     rcx, W32pServiceTableFilter
0x140041a30  mov     edx, cs:W32pServiceLimitFilter
0x140041a36  mov     rax, 1D5h
0x140041a3d  lea     rcx, [rcx+rdx*4]
0x140041a41  movsx   eax, byte ptr [rcx+rax]
0x140041a45  or      eax, eax
0x140041a47  jle     short loc_140041A4E
0x140041a49  mov     eax, 0C000001Ch
0x140041a4e  add     rsp, 48h
0x140041a52  retn
0x140041a53  mov     rax, cs:__imp_NtGdiDdDDICreateHwQueue
0x140041a5a  mov     rcx, [rsp+48h+var_28]
0x140041a5f  mov     rdx, [rsp+48h+var_20]
0x140041a64  mov     r8, [rsp+48h+var_18]
0x140041a69  mov     r9, [rsp+48h+var_10]
0x140041a6e  add     rsp, 48h
0x140041a72  jmp     rax
```
