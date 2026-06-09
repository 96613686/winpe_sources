# _stub_GdiDdDDIOpenKeyedMutex2

- ea: `0x140044b90`
- end: `0x140044c37`
- name: `_stub_GdiDdDDIOpenKeyedMutex2`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044b90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044bd9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044bd9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenKeyedMutex2` at `0x140044c13`

## string_xrefs

- `0x140044bbf`: `NtGdiDdDDIOpenKeyedMutex2`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenKeyedMutex2(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenKeyedMutex2(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenKeyedMutex2(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044b90  sub     rsp, 48h
0x140044b94  mov     [rsp+48h+var_28], rcx
0x140044b99  mov     [rsp+48h+var_20], rdx
0x140044b9e  mov     [rsp+48h+var_18], r8
0x140044ba3  mov     [rsp+48h+var_10], r9
0x140044ba8  mov     rcx, 220h
0x140044baf  call    cs:__imp_IsWin32KSyscallFiltered
0x140044bb6  nop     dword ptr [rax+rax+00h]
0x140044bbb  test    al, al
0x140044bbd  jz      short loc_140044C13
0x140044bbf  lea     rcx, aNtgdiddddiopen_4; "NtGdiDdDDIOpenKeyedMutex2"
0x140044bc6  mov     rdx, 220h
0x140044bcd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044bd4  nop     dword ptr [rax+rax+00h]
0x140044bd9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044be0  nop     dword ptr [rax+rax+00h]
0x140044be5  test    al, al
0x140044be7  jz      short loc_140044C13
0x140044be9  lea     rcx, W32pServiceTableFilter
0x140044bf0  mov     edx, cs:W32pServiceLimitFilter
0x140044bf6  mov     rax, 220h
0x140044bfd  lea     rcx, [rcx+rdx*4]
0x140044c01  movsx   eax, byte ptr [rcx+rax]
0x140044c05  or      eax, eax
0x140044c07  jle     short loc_140044C0E
0x140044c09  mov     eax, 0C000001Ch
0x140044c0e  add     rsp, 48h
0x140044c12  retn
0x140044c13  mov     rax, cs:__imp_NtGdiDdDDIOpenKeyedMutex2
0x140044c1a  mov     rcx, [rsp+48h+var_28]
0x140044c1f  mov     rdx, [rsp+48h+var_20]
0x140044c24  mov     r8, [rsp+48h+var_18]
0x140044c29  mov     r9, [rsp+48h+var_10]
0x140044c2e  add     rsp, 48h
0x140044c32  jmp     rax
```
