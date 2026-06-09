# _stub_DCompositionGetChannels

- ea: `0x14003a060`
- end: `0x14003a107`
- name: `_stub_DCompositionGetChannels`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a060`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a0a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a0a9`

## string_xrefs

- `0x14003a08f`: `NtDCompositionGetChannels`

## pseudocode

```c
__int64 stub_DCompositionGetChannels()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetChannels();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetChannels();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a060  sub     rsp, 48h
0x14003a064  mov     [rsp+48h+var_28], rcx
0x14003a069  mov     [rsp+48h+var_20], rdx
0x14003a06e  mov     [rsp+48h+var_18], r8
0x14003a073  mov     [rsp+48h+var_10], r9
0x14003a078  mov     rcx, 127h
0x14003a07f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a086  nop     dword ptr [rax+rax+00h]
0x14003a08b  test    al, al
0x14003a08d  jz      short loc_14003A0E3
0x14003a08f  lea     rcx, aNtdcomposition_19; "NtDCompositionGetChannels"
0x14003a096  mov     rdx, 127h
0x14003a09d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a0a4  nop     dword ptr [rax+rax+00h]
0x14003a0a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a0b0  nop     dword ptr [rax+rax+00h]
0x14003a0b5  test    al, al
0x14003a0b7  jz      short loc_14003A0E3
0x14003a0b9  lea     rcx, W32pServiceTableFilter
0x14003a0c0  mov     edx, cs:W32pServiceLimitFilter
0x14003a0c6  mov     rax, 127h
0x14003a0cd  lea     rcx, [rcx+rdx*4]
0x14003a0d1  movsx   eax, byte ptr [rcx+rax]
0x14003a0d5  or      eax, eax
0x14003a0d7  jle     short loc_14003A0DE
0x14003a0d9  mov     eax, 0C000001Ch
0x14003a0de  add     rsp, 48h
0x14003a0e2  retn
0x14003a0e3  mov     rax, cs:__imp_NtDCompositionGetChannels
0x14003a0ea  mov     rcx, [rsp+48h+var_28]
0x14003a0ef  mov     rdx, [rsp+48h+var_20]
0x14003a0f4  mov     r8, [rsp+48h+var_18]
0x14003a0f9  mov     r9, [rsp+48h+var_10]
0x14003a0fe  add     rsp, 48h
0x14003a102  jmp     rax
```
