# _stub_DCompositionDuplicateSwapchainHandleToDwm

- ea: `0x14003a020`
- end: `0x14003a0c7`
- name: `_stub_DCompositionDuplicateSwapchainHandleToDwm`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a020`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a069`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a069`

## string_xrefs

- `0x14003a04f`: `NtDCompositionDuplicateSwapchainHandleToDwm`

## pseudocode

```c
__int64 stub_DCompositionDuplicateSwapchainHandleToDwm()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionDuplicateSwapchainHandleToDwm();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionDuplicateSwapchainHandleToDwm();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a020  sub     rsp, 48h
0x14003a024  mov     [rsp+48h+var_28], rcx
0x14003a029  mov     [rsp+48h+var_20], rdx
0x14003a02e  mov     [rsp+48h+var_18], r8
0x14003a033  mov     [rsp+48h+var_10], r9
0x14003a038  mov     rcx, 124h
0x14003a03f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a046  nop     dword ptr [rax+rax+00h]
0x14003a04b  test    al, al
0x14003a04d  jz      short loc_14003A0A3
0x14003a04f  lea     rcx, aNtdcomposition_16; "NtDCompositionDuplicateSwapchainHandleT"...
0x14003a056  mov     rdx, 124h
0x14003a05d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a064  nop     dword ptr [rax+rax+00h]
0x14003a069  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a070  nop     dword ptr [rax+rax+00h]
0x14003a075  test    al, al
0x14003a077  jz      short loc_14003A0A3
0x14003a079  lea     rcx, W32pServiceTableFilter
0x14003a080  mov     edx, cs:W32pServiceLimitFilter
0x14003a086  mov     rax, 124h
0x14003a08d  lea     rcx, [rcx+rdx*4]
0x14003a091  movsx   eax, byte ptr [rcx+rax]
0x14003a095  or      eax, eax
0x14003a097  jle     short loc_14003A09E
0x14003a099  mov     eax, 0C000001Ch
0x14003a09e  add     rsp, 48h
0x14003a0a2  retn
0x14003a0a3  mov     rax, cs:__imp_NtDCompositionDuplicateSwapchainHandleToDwm
0x14003a0aa  mov     rcx, [rsp+48h+var_28]
0x14003a0af  mov     rdx, [rsp+48h+var_20]
0x14003a0b4  mov     r8, [rsp+48h+var_18]
0x14003a0b9  mov     r9, [rsp+48h+var_10]
0x14003a0be  add     rsp, 48h
0x14003a0c2  jmp     rax
```
