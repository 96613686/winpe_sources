# _stub_GdiDdDDIOpenKeyedMutex

- ea: `0x140044ec0`
- end: `0x140044f67`
- name: `_stub_GdiDdDDIOpenKeyedMutex`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044ec0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044f09`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044f09`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenKeyedMutex` at `0x140044f43`

## string_xrefs

- `0x140044eef`: `NtGdiDdDDIOpenKeyedMutex`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenKeyedMutex(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenKeyedMutex(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenKeyedMutex(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044ec0  sub     rsp, 48h
0x140044ec4  mov     [rsp+48h+var_28], rcx
0x140044ec9  mov     [rsp+48h+var_20], rdx
0x140044ece  mov     [rsp+48h+var_18], r8
0x140044ed3  mov     [rsp+48h+var_10], r9
0x140044ed8  mov     rcx, 222h
0x140044edf  call    cs:__imp_IsWin32KSyscallFiltered
0x140044ee6  nop     dword ptr [rax+rax+00h]
0x140044eeb  test    al, al
0x140044eed  jz      short loc_140044F43
0x140044eef  lea     rcx, aNtgdiddddiopen_3; "NtGdiDdDDIOpenKeyedMutex"
0x140044ef6  mov     rdx, 222h
0x140044efd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044f04  nop     dword ptr [rax+rax+00h]
0x140044f09  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044f10  nop     dword ptr [rax+rax+00h]
0x140044f15  test    al, al
0x140044f17  jz      short loc_140044F43
0x140044f19  lea     rcx, W32pServiceTableFilter
0x140044f20  mov     edx, cs:W32pServiceLimitFilter
0x140044f26  mov     rax, 222h
0x140044f2d  lea     rcx, [rcx+rdx*4]
0x140044f31  movsx   eax, byte ptr [rcx+rax]
0x140044f35  or      eax, eax
0x140044f37  jle     short loc_140044F3E
0x140044f39  mov     eax, 0C000001Ch
0x140044f3e  add     rsp, 48h
0x140044f42  retn
0x140044f43  mov     rax, cs:__imp_NtGdiDdDDIOpenKeyedMutex
0x140044f4a  mov     rcx, [rsp+48h+var_28]
0x140044f4f  mov     rdx, [rsp+48h+var_20]
0x140044f54  mov     r8, [rsp+48h+var_18]
0x140044f59  mov     r9, [rsp+48h+var_10]
0x140044f5e  add     rsp, 48h
0x140044f62  jmp     rax
```
