# _stub_GdiDdDDIOpenSynchronizationObject

- ea: `0x140045270`
- end: `0x140045317`
- name: `_stub_GdiDdDDIOpenSynchronizationObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045270`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400452b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400452b9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenSynchronizationObject` at `0x1400452f3`

## string_xrefs

- `0x14004529f`: `NtGdiDdDDIOpenSynchronizationObject`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[69] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045270  sub     rsp, 48h
0x140045274  mov     [rsp+48h+var_28], rcx
0x140045279  mov     [rsp+48h+var_20], rdx
0x14004527e  mov     [rsp+48h+var_18], r8
0x140045283  mov     [rsp+48h+var_10], r9
0x140045288  mov     rcx, 22Ah
0x14004528f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045296  nop     dword ptr [rax+rax+00h]
0x14004529b  test    al, al
0x14004529d  jz      short loc_1400452F3
0x14004529f  lea     rcx, aNtgdiddddiopen_14; "NtGdiDdDDIOpenSynchronizationObject"
0x1400452a6  mov     rdx, 22Ah
0x1400452ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400452b4  nop     dword ptr [rax+rax+00h]
0x1400452b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400452c0  nop     dword ptr [rax+rax+00h]
0x1400452c5  test    al, al
0x1400452c7  jz      short loc_1400452F3
0x1400452c9  lea     rcx, W32pServiceTableFilter
0x1400452d0  mov     edx, cs:W32pServiceLimitFilter
0x1400452d6  mov     rax, 22Ah
0x1400452dd  lea     rcx, [rcx+rdx*4]
0x1400452e1  movsx   eax, byte ptr [rcx+rax]
0x1400452e5  or      eax, eax
0x1400452e7  jle     short loc_1400452EE
0x1400452e9  mov     eax, 0C000001Ch
0x1400452ee  add     rsp, 48h
0x1400452f2  retn
0x1400452f3  mov     rax, cs:__imp_NtGdiDdDDIOpenSynchronizationObject
0x1400452fa  mov     rcx, [rsp+48h+var_28]
0x1400452ff  mov     rdx, [rsp+48h+var_20]
0x140045304  mov     r8, [rsp+48h+var_18]
0x140045309  mov     r9, [rsp+48h+var_10]
0x14004530e  add     rsp, 48h
0x140045312  jmp     rax
```
