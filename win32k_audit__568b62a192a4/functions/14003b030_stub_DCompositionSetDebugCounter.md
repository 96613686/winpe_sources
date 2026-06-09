# _stub_DCompositionSetDebugCounter

- ea: `0x14003b030`
- end: `0x14003b0d7`
- name: `_stub_DCompositionSetDebugCounter`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b030`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b079`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b079`

## string_xrefs

- `0x14003b05f`: `NtDCompositionSetDebugCounter`

## pseudocode

```c
__int64 stub_DCompositionSetDebugCounter()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSetDebugCounter();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSetDebugCounter();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b030  sub     rsp, 48h
0x14003b034  mov     [rsp+48h+var_28], rcx
0x14003b039  mov     [rsp+48h+var_20], rdx
0x14003b03e  mov     [rsp+48h+var_18], r8
0x14003b043  mov     [rsp+48h+var_10], r9
0x14003b048  mov     rcx, 13Eh
0x14003b04f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b056  nop     dword ptr [rax+rax+00h]
0x14003b05b  test    al, al
0x14003b05d  jz      short loc_14003B0B3
0x14003b05f  lea     rcx, aNtdcomposition_42; "NtDCompositionSetDebugCounter"
0x14003b066  mov     rdx, 13Eh
0x14003b06d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b074  nop     dword ptr [rax+rax+00h]
0x14003b079  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b080  nop     dword ptr [rax+rax+00h]
0x14003b085  test    al, al
0x14003b087  jz      short loc_14003B0B3
0x14003b089  lea     rcx, W32pServiceTableFilter
0x14003b090  mov     edx, cs:W32pServiceLimitFilter
0x14003b096  mov     rax, 13Eh
0x14003b09d  lea     rcx, [rcx+rdx*4]
0x14003b0a1  movsx   eax, byte ptr [rcx+rax]
0x14003b0a5  or      eax, eax
0x14003b0a7  jle     short loc_14003B0AE
0x14003b0a9  mov     eax, 0C000001Ch
0x14003b0ae  add     rsp, 48h
0x14003b0b2  retn
0x14003b0b3  mov     rax, cs:__imp_NtDCompositionSetDebugCounter
0x14003b0ba  mov     rcx, [rsp+48h+var_28]
0x14003b0bf  mov     rdx, [rsp+48h+var_20]
0x14003b0c4  mov     r8, [rsp+48h+var_18]
0x14003b0c9  mov     r9, [rsp+48h+var_10]
0x14003b0ce  add     rsp, 48h
0x14003b0d2  jmp     rax
```
