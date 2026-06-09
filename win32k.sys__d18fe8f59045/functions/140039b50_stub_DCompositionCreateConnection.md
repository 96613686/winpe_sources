# _stub_DCompositionCreateConnection

- ea: `0x140039b50`
- end: `0x140039bf7`
- name: `_stub_DCompositionCreateConnection`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039b50`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039b99`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039b99`

## string_xrefs

- `0x140039b7f`: `NtDCompositionCreateConnection`

## pseudocode

```c
__int64 stub_DCompositionCreateConnection()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateConnection();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateConnection();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039b50  sub     rsp, 48h
0x140039b54  mov     [rsp+48h+var_28], rcx
0x140039b59  mov     [rsp+48h+var_20], rdx
0x140039b5e  mov     [rsp+48h+var_18], r8
0x140039b63  mov     [rsp+48h+var_10], r9
0x140039b68  mov     rcx, 11Dh
0x140039b6f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039b76  nop     dword ptr [rax+rax+00h]
0x140039b7b  test    al, al
0x140039b7d  jz      short loc_140039BD3
0x140039b7f  lea     rcx, aNtdcomposition_9; "NtDCompositionCreateConnection"
0x140039b86  mov     rdx, 11Dh
0x140039b8d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039b94  nop     dword ptr [rax+rax+00h]
0x140039b99  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039ba0  nop     dword ptr [rax+rax+00h]
0x140039ba5  test    al, al
0x140039ba7  jz      short loc_140039BD3
0x140039ba9  lea     rcx, W32pServiceTableFilter
0x140039bb0  mov     edx, cs:W32pServiceLimitFilter
0x140039bb6  mov     rax, 11Dh
0x140039bbd  lea     rcx, [rcx+rdx*4]
0x140039bc1  movsx   eax, byte ptr [rcx+rax]
0x140039bc5  or      eax, eax
0x140039bc7  jle     short loc_140039BCE
0x140039bc9  mov     eax, 0C000001Ch
0x140039bce  add     rsp, 48h
0x140039bd2  retn
0x140039bd3  mov     rax, cs:__imp_NtDCompositionCreateConnection
0x140039bda  mov     rcx, [rsp+48h+var_28]
0x140039bdf  mov     rdx, [rsp+48h+var_20]
0x140039be4  mov     r8, [rsp+48h+var_18]
0x140039be9  mov     r9, [rsp+48h+var_10]
0x140039bee  add     rsp, 48h
0x140039bf2  jmp     rax
```
