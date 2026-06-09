# _stub_DCompositionDestroyChannel

- ea: `0x140039e10`
- end: `0x140039eb7`
- name: `_stub_DCompositionDestroyChannel`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039e10`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039e59`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039e59`

## string_xrefs

- `0x140039e3f`: `NtDCompositionDestroyChannel`

## pseudocode

```c
__int64 stub_DCompositionDestroyChannel()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionDestroyChannel();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionDestroyChannel();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039e10  sub     rsp, 48h
0x140039e14  mov     [rsp+48h+var_28], rcx
0x140039e19  mov     [rsp+48h+var_20], rdx
0x140039e1e  mov     [rsp+48h+var_18], r8
0x140039e23  mov     [rsp+48h+var_10], r9
0x140039e28  mov     rcx, 121h
0x140039e2f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039e36  nop     dword ptr [rax+rax+00h]
0x140039e3b  test    al, al
0x140039e3d  jz      short loc_140039E93
0x140039e3f  lea     rcx, aNtdcomposition_13; "NtDCompositionDestroyChannel"
0x140039e46  mov     rdx, 121h
0x140039e4d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039e54  nop     dword ptr [rax+rax+00h]
0x140039e59  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039e60  nop     dword ptr [rax+rax+00h]
0x140039e65  test    al, al
0x140039e67  jz      short loc_140039E93
0x140039e69  lea     rcx, W32pServiceTableFilter
0x140039e70  mov     edx, cs:W32pServiceLimitFilter
0x140039e76  mov     rax, 121h
0x140039e7d  lea     rcx, [rcx+rdx*4]
0x140039e81  movsx   eax, byte ptr [rcx+rax]
0x140039e85  or      eax, eax
0x140039e87  jle     short loc_140039E8E
0x140039e89  mov     eax, 0C000001Ch
0x140039e8e  add     rsp, 48h
0x140039e92  retn
0x140039e93  mov     rax, cs:__imp_NtDCompositionDestroyChannel
0x140039e9a  mov     rcx, [rsp+48h+var_28]
0x140039e9f  mov     rdx, [rsp+48h+var_20]
0x140039ea4  mov     r8, [rsp+48h+var_18]
0x140039ea9  mov     r9, [rsp+48h+var_10]
0x140039eae  add     rsp, 48h
0x140039eb2  jmp     rax
```
