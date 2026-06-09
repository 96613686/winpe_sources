# _stub_GdiAbortPath

- ea: `0x14003e680`
- end: `0x14003e727`
- name: `_stub_GdiAbortPath`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e680`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e6c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e6c9`

## string_xrefs

- `0x14003e6af`: `NtGdiAbortPath`

## pseudocode

```c
__int64 stub_GdiAbortPath()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiAbortPath();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiAbortPath();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[49] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e680  sub     rsp, 48h
0x14003e684  mov     [rsp+48h+var_28], rcx
0x14003e689  mov     [rsp+48h+var_20], rdx
0x14003e68e  mov     [rsp+48h+var_18], r8
0x14003e693  mov     [rsp+48h+var_10], r9
0x14003e698  mov     rcx, 18Dh
0x14003e69f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e6a6  nop     dword ptr [rax+rax+00h]
0x14003e6ab  test    al, al
0x14003e6ad  jz      short loc_14003E703
0x14003e6af  lea     rcx, aNtgdiabortpath; "NtGdiAbortPath"
0x14003e6b6  mov     rdx, 18Dh
0x14003e6bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e6c4  nop     dword ptr [rax+rax+00h]
0x14003e6c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e6d0  nop     dword ptr [rax+rax+00h]
0x14003e6d5  test    al, al
0x14003e6d7  jz      short loc_14003E703
0x14003e6d9  lea     rcx, W32pServiceTableFilter
0x14003e6e0  mov     edx, cs:W32pServiceLimitFilter
0x14003e6e6  mov     rax, 18Dh
0x14003e6ed  lea     rcx, [rcx+rdx*4]
0x14003e6f1  movsx   eax, byte ptr [rcx+rax]
0x14003e6f5  or      eax, eax
0x14003e6f7  jle     short loc_14003E6FE
0x14003e6f9  mov     eax, 0C000001Ch
0x14003e6fe  add     rsp, 48h
0x14003e702  retn
0x14003e703  mov     rax, cs:__imp_NtGdiAbortPath
0x14003e70a  mov     rcx, [rsp+48h+var_28]
0x14003e70f  mov     rdx, [rsp+48h+var_20]
0x14003e714  mov     r8, [rsp+48h+var_18]
0x14003e719  mov     r9, [rsp+48h+var_10]
0x14003e71e  add     rsp, 48h
0x14003e722  jmp     rax
```
