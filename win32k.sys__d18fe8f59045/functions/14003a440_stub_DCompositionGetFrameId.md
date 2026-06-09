# _stub_DCompositionGetFrameId

- ea: `0x14003a440`
- end: `0x14003a4e7`
- name: `_stub_DCompositionGetFrameId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a440`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a489`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a489`

## string_xrefs

- `0x14003a46f`: `NtDCompositionGetFrameId`

## pseudocode

```c
__int64 stub_DCompositionGetFrameId()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetFrameId();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetFrameId();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a440  sub     rsp, 48h
0x14003a444  mov     [rsp+48h+var_28], rcx
0x14003a449  mov     [rsp+48h+var_20], rdx
0x14003a44e  mov     [rsp+48h+var_18], r8
0x14003a453  mov     [rsp+48h+var_10], r9
0x14003a458  mov     rcx, 12Ah
0x14003a45f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a466  nop     dword ptr [rax+rax+00h]
0x14003a46b  test    al, al
0x14003a46d  jz      short loc_14003A4C3
0x14003a46f  lea     rcx, aNtdcomposition_22; "NtDCompositionGetFrameId"
0x14003a476  mov     rdx, 12Ah
0x14003a47d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a484  nop     dword ptr [rax+rax+00h]
0x14003a489  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a490  nop     dword ptr [rax+rax+00h]
0x14003a495  test    al, al
0x14003a497  jz      short loc_14003A4C3
0x14003a499  lea     rcx, W32pServiceTableFilter
0x14003a4a0  mov     edx, cs:W32pServiceLimitFilter
0x14003a4a6  mov     rax, 12Ah
0x14003a4ad  lea     rcx, [rcx+rdx*4]
0x14003a4b1  movsx   eax, byte ptr [rcx+rax]
0x14003a4b5  or      eax, eax
0x14003a4b7  jle     short loc_14003A4BE
0x14003a4b9  mov     eax, 0C000001Ch
0x14003a4be  add     rsp, 48h
0x14003a4c2  retn
0x14003a4c3  mov     rax, cs:__imp_NtDCompositionGetFrameId
0x14003a4ca  mov     rcx, [rsp+48h+var_28]
0x14003a4cf  mov     rdx, [rsp+48h+var_20]
0x14003a4d4  mov     r8, [rsp+48h+var_18]
0x14003a4d9  mov     r9, [rsp+48h+var_10]
0x14003a4de  add     rsp, 48h
0x14003a4e2  jmp     rax
```
