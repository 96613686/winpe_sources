# _stub_DCompositionCreateSharedResourceHandle

- ea: `0x140039ae0`
- end: `0x140039b87`
- name: `_stub_DCompositionCreateSharedResourceHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039ae0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039b29`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039b29`

## string_xrefs

- `0x140039b0f`: `NtDCompositionCreateSharedResourceHandle`

## pseudocode

```c
__int64 stub_DCompositionCreateSharedResourceHandle()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateSharedResourceHandle();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateSharedResourceHandle();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039ae0  sub     rsp, 48h
0x140039ae4  mov     [rsp+48h+var_28], rcx
0x140039ae9  mov     [rsp+48h+var_20], rdx
0x140039aee  mov     [rsp+48h+var_18], r8
0x140039af3  mov     [rsp+48h+var_10], r9
0x140039af8  mov     rcx, 11Fh
0x140039aff  call    cs:__imp_IsWin32KSyscallFiltered
0x140039b06  nop     dword ptr [rax+rax+00h]
0x140039b0b  test    al, al
0x140039b0d  jz      short loc_140039B63
0x140039b0f  lea     rcx, aNtdcomposition_11; "NtDCompositionCreateSharedResourceHandl"...
0x140039b16  mov     rdx, 11Fh
0x140039b1d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039b24  nop     dword ptr [rax+rax+00h]
0x140039b29  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039b30  nop     dword ptr [rax+rax+00h]
0x140039b35  test    al, al
0x140039b37  jz      short loc_140039B63
0x140039b39  lea     rcx, W32pServiceTableFilter
0x140039b40  mov     edx, cs:W32pServiceLimitFilter
0x140039b46  mov     rax, 11Fh
0x140039b4d  lea     rcx, [rcx+rdx*4]
0x140039b51  movsx   eax, byte ptr [rcx+rax]
0x140039b55  or      eax, eax
0x140039b57  jle     short loc_140039B5E
0x140039b59  mov     eax, 0C000001Ch
0x140039b5e  add     rsp, 48h
0x140039b62  retn
0x140039b63  mov     rax, cs:__imp_NtDCompositionCreateSharedResourceHandle
0x140039b6a  mov     rcx, [rsp+48h+var_28]
0x140039b6f  mov     rdx, [rsp+48h+var_20]
0x140039b74  mov     r8, [rsp+48h+var_18]
0x140039b79  mov     r9, [rsp+48h+var_10]
0x140039b7e  add     rsp, 48h
0x140039b82  jmp     rax
```
