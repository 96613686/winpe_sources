# _stub_GdiDdDDIOpenKeyedMutex

- ea: `0x140044ae0`
- end: `0x140044b87`
- name: `_stub_GdiDdDDIOpenKeyedMutex`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044ae0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044b29`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044b29`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenKeyedMutex` at `0x140044b63`

## string_xrefs

- `0x140044b0f`: `NtGdiDdDDIOpenKeyedMutex`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[67] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044ae0  sub     rsp, 48h
0x140044ae4  mov     [rsp+48h+var_28], rcx
0x140044ae9  mov     [rsp+48h+var_20], rdx
0x140044aee  mov     [rsp+48h+var_18], r8
0x140044af3  mov     [rsp+48h+var_10], r9
0x140044af8  mov     rcx, 21Fh
0x140044aff  call    cs:__imp_IsWin32KSyscallFiltered
0x140044b06  nop     dword ptr [rax+rax+00h]
0x140044b0b  test    al, al
0x140044b0d  jz      short loc_140044B63
0x140044b0f  lea     rcx, aNtgdiddddiopen_3; "NtGdiDdDDIOpenKeyedMutex"
0x140044b16  mov     rdx, 21Fh
0x140044b1d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044b24  nop     dword ptr [rax+rax+00h]
0x140044b29  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044b30  nop     dword ptr [rax+rax+00h]
0x140044b35  test    al, al
0x140044b37  jz      short loc_140044B63
0x140044b39  lea     rcx, W32pServiceTableFilter
0x140044b40  mov     edx, cs:W32pServiceLimitFilter
0x140044b46  mov     rax, 21Fh
0x140044b4d  lea     rcx, [rcx+rdx*4]
0x140044b51  movsx   eax, byte ptr [rcx+rax]
0x140044b55  or      eax, eax
0x140044b57  jle     short loc_140044B5E
0x140044b59  mov     eax, 0C000001Ch
0x140044b5e  add     rsp, 48h
0x140044b62  retn
0x140044b63  mov     rax, cs:__imp_NtGdiDdDDIOpenKeyedMutex
0x140044b6a  mov     rcx, [rsp+48h+var_28]
0x140044b6f  mov     rdx, [rsp+48h+var_20]
0x140044b74  mov     r8, [rsp+48h+var_18]
0x140044b79  mov     r9, [rsp+48h+var_10]
0x140044b7e  add     rsp, 48h
0x140044b82  jmp     rax
```
