# _stub_GdiBeginPath

- ea: `0x140037fd0`
- end: `0x140038077`
- name: `_stub_GdiBeginPath`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140037fd0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038019`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038019`

## string_xrefs

- `0x140037fff`: `NtGdiBeginPath`

## pseudocode

```c
__int64 stub_GdiBeginPath()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiBeginPath();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiBeginPath();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[30] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140037fd0  sub     rsp, 48h
0x140037fd4  mov     [rsp+48h+var_28], rcx
0x140037fd9  mov     [rsp+48h+var_20], rdx
0x140037fde  mov     [rsp+48h+var_18], r8
0x140037fe3  mov     [rsp+48h+var_10], r9
0x140037fe8  mov     rcx, 0F5h
0x140037fef  call    cs:__imp_IsWin32KSyscallFiltered
0x140037ff6  nop     dword ptr [rax+rax+00h]
0x140037ffb  test    al, al
0x140037ffd  jz      short loc_140038053
0x140037fff  lea     rcx, aNtgdibeginpath; "NtGdiBeginPath"
0x140038006  mov     rdx, 0F5h
0x14003800d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038014  nop     dword ptr [rax+rax+00h]
0x140038019  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038020  nop     dword ptr [rax+rax+00h]
0x140038025  test    al, al
0x140038027  jz      short loc_140038053
0x140038029  lea     rcx, W32pServiceTableFilter
0x140038030  mov     edx, cs:W32pServiceLimitFilter
0x140038036  mov     rax, 0F5h
0x14003803d  lea     rcx, [rcx+rdx*4]
0x140038041  movsx   eax, byte ptr [rcx+rax]
0x140038045  or      eax, eax
0x140038047  jle     short loc_14003804E
0x140038049  mov     eax, 0C000001Ch
0x14003804e  add     rsp, 48h
0x140038052  retn
0x140038053  mov     rax, cs:__imp_NtGdiBeginPath
0x14003805a  mov     rcx, [rsp+48h+var_28]
0x14003805f  mov     rdx, [rsp+48h+var_20]
0x140038064  mov     r8, [rsp+48h+var_18]
0x140038069  mov     r9, [rsp+48h+var_10]
0x14003806e  add     rsp, 48h
0x140038072  jmp     rax
```
