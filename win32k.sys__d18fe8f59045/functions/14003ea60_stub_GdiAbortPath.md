# _stub_GdiAbortPath

- ea: `0x14003ea60`
- end: `0x14003eb07`
- name: `_stub_GdiAbortPath`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ea60`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003eaa9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003eaa9`

## string_xrefs

- `0x14003ea8f`: `NtGdiAbortPath`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[50] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ea60  sub     rsp, 48h
0x14003ea64  mov     [rsp+48h+var_28], rcx
0x14003ea69  mov     [rsp+48h+var_20], rdx
0x14003ea6e  mov     [rsp+48h+var_18], r8
0x14003ea73  mov     [rsp+48h+var_10], r9
0x14003ea78  mov     rcx, 190h
0x14003ea7f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ea86  nop     dword ptr [rax+rax+00h]
0x14003ea8b  test    al, al
0x14003ea8d  jz      short loc_14003EAE3
0x14003ea8f  lea     rcx, aNtgdiabortpath; "NtGdiAbortPath"
0x14003ea96  mov     rdx, 190h
0x14003ea9d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003eaa4  nop     dword ptr [rax+rax+00h]
0x14003eaa9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003eab0  nop     dword ptr [rax+rax+00h]
0x14003eab5  test    al, al
0x14003eab7  jz      short loc_14003EAE3
0x14003eab9  lea     rcx, W32pServiceTableFilter
0x14003eac0  mov     edx, cs:W32pServiceLimitFilter
0x14003eac6  mov     rax, 190h
0x14003eacd  lea     rcx, [rcx+rdx*4]
0x14003ead1  movsx   eax, byte ptr [rcx+rax]
0x14003ead5  or      eax, eax
0x14003ead7  jle     short loc_14003EADE
0x14003ead9  mov     eax, 0C000001Ch
0x14003eade  add     rsp, 48h
0x14003eae2  retn
0x14003eae3  mov     rax, cs:__imp_NtGdiAbortPath
0x14003eaea  mov     rcx, [rsp+48h+var_28]
0x14003eaef  mov     rdx, [rsp+48h+var_20]
0x14003eaf4  mov     r8, [rsp+48h+var_18]
0x14003eaf9  mov     r9, [rsp+48h+var_10]
0x14003eafe  add     rsp, 48h
0x14003eb02  jmp     rax
```
