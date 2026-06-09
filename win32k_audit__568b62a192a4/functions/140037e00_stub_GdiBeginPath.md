# _stub_GdiBeginPath

- ea: `0x140037e00`
- end: `0x140037ea7`
- name: `_stub_GdiBeginPath`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140037e00`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140037e49`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140037e49`

## string_xrefs

- `0x140037e2f`: `NtGdiBeginPath`

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
0x140037e00  sub     rsp, 48h
0x140037e04  mov     [rsp+48h+var_28], rcx
0x140037e09  mov     [rsp+48h+var_20], rdx
0x140037e0e  mov     [rsp+48h+var_18], r8
0x140037e13  mov     [rsp+48h+var_10], r9
0x140037e18  mov     rcx, 0F5h
0x140037e1f  call    cs:__imp_IsWin32KSyscallFiltered
0x140037e26  nop     dword ptr [rax+rax+00h]
0x140037e2b  test    al, al
0x140037e2d  jz      short loc_140037E83
0x140037e2f  lea     rcx, aNtgdibeginpath; "NtGdiBeginPath"
0x140037e36  mov     rdx, 0F5h
0x140037e3d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140037e44  nop     dword ptr [rax+rax+00h]
0x140037e49  call    cs:__imp_PsIsWin32KFilterEnabled
0x140037e50  nop     dword ptr [rax+rax+00h]
0x140037e55  test    al, al
0x140037e57  jz      short loc_140037E83
0x140037e59  lea     rcx, W32pServiceTableFilter
0x140037e60  mov     edx, cs:W32pServiceLimitFilter
0x140037e66  mov     rax, 0F5h
0x140037e6d  lea     rcx, [rcx+rdx*4]
0x140037e71  movsx   eax, byte ptr [rcx+rax]
0x140037e75  or      eax, eax
0x140037e77  jle     short loc_140037E7E
0x140037e79  mov     eax, 0C000001Ch
0x140037e7e  add     rsp, 48h
0x140037e82  retn
0x140037e83  mov     rax, cs:__imp_NtGdiBeginPath
0x140037e8a  mov     rcx, [rsp+48h+var_28]
0x140037e8f  mov     rdx, [rsp+48h+var_20]
0x140037e94  mov     r8, [rsp+48h+var_18]
0x140037e99  mov     r9, [rsp+48h+var_10]
0x140037e9e  add     rsp, 48h
0x140037ea2  jmp     rax
```
