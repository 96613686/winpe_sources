# _stub_DCompositionWaitForChannel

- ea: `0x14003b620`
- end: `0x14003b6c7`
- name: `_stub_DCompositionWaitForChannel`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b620`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b669`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b669`

## string_xrefs

- `0x14003b64f`: `NtDCompositionWaitForChannel`

## pseudocode

```c
__int64 stub_DCompositionWaitForChannel()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionWaitForChannel();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionWaitForChannel();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b620  sub     rsp, 48h
0x14003b624  mov     [rsp+48h+var_28], rcx
0x14003b629  mov     [rsp+48h+var_20], rdx
0x14003b62e  mov     [rsp+48h+var_18], r8
0x14003b633  mov     [rsp+48h+var_10], r9
0x14003b638  mov     rcx, 144h
0x14003b63f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b646  nop     dword ptr [rax+rax+00h]
0x14003b64b  test    al, al
0x14003b64d  jz      short loc_14003B6A3
0x14003b64f  lea     rcx, aNtdcomposition_48; "NtDCompositionWaitForChannel"
0x14003b656  mov     rdx, 144h
0x14003b65d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b664  nop     dword ptr [rax+rax+00h]
0x14003b669  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b670  nop     dword ptr [rax+rax+00h]
0x14003b675  test    al, al
0x14003b677  jz      short loc_14003B6A3
0x14003b679  lea     rcx, W32pServiceTableFilter
0x14003b680  mov     edx, cs:W32pServiceLimitFilter
0x14003b686  mov     rax, 144h
0x14003b68d  lea     rcx, [rcx+rdx*4]
0x14003b691  movsx   eax, byte ptr [rcx+rax]
0x14003b695  or      eax, eax
0x14003b697  jle     short loc_14003B69E
0x14003b699  mov     eax, 0C000001Ch
0x14003b69e  add     rsp, 48h
0x14003b6a2  retn
0x14003b6a3  mov     rax, cs:__imp_NtDCompositionWaitForChannel
0x14003b6aa  mov     rcx, [rsp+48h+var_28]
0x14003b6af  mov     rdx, [rsp+48h+var_20]
0x14003b6b4  mov     r8, [rsp+48h+var_18]
0x14003b6b9  mov     r9, [rsp+48h+var_10]
0x14003b6be  add     rsp, 48h
0x14003b6c2  jmp     rax
```
