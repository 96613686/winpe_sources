# _stub_DCompositionCreateChannel

- ea: `0x140039aa0`
- end: `0x140039b47`
- name: `_stub_DCompositionCreateChannel`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039aa0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039ae9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039ae9`

## string_xrefs

- `0x140039acf`: `NtDCompositionCreateChannel`

## pseudocode

```c
__int64 stub_DCompositionCreateChannel()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateChannel();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateChannel();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039aa0  sub     rsp, 48h
0x140039aa4  mov     [rsp+48h+var_28], rcx
0x140039aa9  mov     [rsp+48h+var_20], rdx
0x140039aae  mov     [rsp+48h+var_18], r8
0x140039ab3  mov     [rsp+48h+var_10], r9
0x140039ab8  mov     rcx, 11Ch
0x140039abf  call    cs:__imp_IsWin32KSyscallFiltered
0x140039ac6  nop     dword ptr [rax+rax+00h]
0x140039acb  test    al, al
0x140039acd  jz      short loc_140039B23
0x140039acf  lea     rcx, aNtdcomposition_8; "NtDCompositionCreateChannel"
0x140039ad6  mov     rdx, 11Ch
0x140039add  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039ae4  nop     dword ptr [rax+rax+00h]
0x140039ae9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039af0  nop     dword ptr [rax+rax+00h]
0x140039af5  test    al, al
0x140039af7  jz      short loc_140039B23
0x140039af9  lea     rcx, W32pServiceTableFilter
0x140039b00  mov     edx, cs:W32pServiceLimitFilter
0x140039b06  mov     rax, 11Ch
0x140039b0d  lea     rcx, [rcx+rdx*4]
0x140039b11  movsx   eax, byte ptr [rcx+rax]
0x140039b15  or      eax, eax
0x140039b17  jle     short loc_140039B1E
0x140039b19  mov     eax, 0C000001Ch
0x140039b1e  add     rsp, 48h
0x140039b22  retn
0x140039b23  mov     rax, cs:__imp_NtDCompositionCreateChannel
0x140039b2a  mov     rcx, [rsp+48h+var_28]
0x140039b2f  mov     rdx, [rsp+48h+var_20]
0x140039b34  mov     r8, [rsp+48h+var_18]
0x140039b39  mov     r9, [rsp+48h+var_10]
0x140039b3e  add     rsp, 48h
0x140039b42  jmp     rax
```
