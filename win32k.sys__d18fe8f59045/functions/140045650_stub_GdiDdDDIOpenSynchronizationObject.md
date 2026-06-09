# _stub_GdiDdDDIOpenSynchronizationObject

- ea: `0x140045650`
- end: `0x1400456f7`
- name: `_stub_GdiDdDDIOpenSynchronizationObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045650`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045699`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045699`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSynchronizationObject` at `0x1400456d3`

## string_xrefs

- `0x14004567f`: `NtGdiDdDDIOpenSynchronizationObject`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenSynchronizationObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenSynchronizationObject(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenSynchronizationObject(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045650  sub     rsp, 48h
0x140045654  mov     [rsp+48h+var_28], rcx
0x140045659  mov     [rsp+48h+var_20], rdx
0x14004565e  mov     [rsp+48h+var_18], r8
0x140045663  mov     [rsp+48h+var_10], r9
0x140045668  mov     rcx, 22Dh
0x14004566f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045676  nop     dword ptr [rax+rax+00h]
0x14004567b  test    al, al
0x14004567d  jz      short loc_1400456D3
0x14004567f  lea     rcx, aNtgdiddddiopen_14; "NtGdiDdDDIOpenSynchronizationObject"
0x140045686  mov     rdx, 22Dh
0x14004568d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045694  nop     dword ptr [rax+rax+00h]
0x140045699  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400456a0  nop     dword ptr [rax+rax+00h]
0x1400456a5  test    al, al
0x1400456a7  jz      short loc_1400456D3
0x1400456a9  lea     rcx, W32pServiceTableFilter
0x1400456b0  mov     edx, cs:W32pServiceLimitFilter
0x1400456b6  mov     rax, 22Dh
0x1400456bd  lea     rcx, [rcx+rdx*4]
0x1400456c1  movsx   eax, byte ptr [rcx+rax]
0x1400456c5  or      eax, eax
0x1400456c7  jle     short loc_1400456CE
0x1400456c9  mov     eax, 0C000001Ch
0x1400456ce  add     rsp, 48h
0x1400456d2  retn
0x1400456d3  mov     rax, cs:__imp_NtGdiDdDDIOpenSynchronizationObject
0x1400456da  mov     rcx, [rsp+48h+var_28]
0x1400456df  mov     rdx, [rsp+48h+var_20]
0x1400456e4  mov     r8, [rsp+48h+var_18]
0x1400456e9  mov     r9, [rsp+48h+var_10]
0x1400456ee  add     rsp, 48h
0x1400456f2  jmp     rax
```
