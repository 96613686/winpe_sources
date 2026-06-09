# _stub_DCompositionDuplicateSwapchainHandleToDwm

- ea: `0x140039e50`
- end: `0x140039ef7`
- name: `_stub_DCompositionDuplicateSwapchainHandleToDwm`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039e50`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039e99`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039e99`

## string_xrefs

- `0x140039e7f`: `NtDCompositionDuplicateSwapchainHandleToDwm`

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
0x140039e50  sub     rsp, 48h
0x140039e54  mov     [rsp+48h+var_28], rcx
0x140039e59  mov     [rsp+48h+var_20], rdx
0x140039e5e  mov     [rsp+48h+var_18], r8
0x140039e63  mov     [rsp+48h+var_10], r9
0x140039e68  mov     rcx, 124h
0x140039e6f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039e76  nop     dword ptr [rax+rax+00h]
0x140039e7b  test    al, al
0x140039e7d  jz      short loc_140039ED3
0x140039e7f  lea     rcx, aNtdcomposition_16; "NtDCompositionDuplicateSwapchainHandleT"...
0x140039e86  mov     rdx, 124h
0x140039e8d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039e94  nop     dword ptr [rax+rax+00h]
0x140039e99  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039ea0  nop     dword ptr [rax+rax+00h]
0x140039ea5  test    al, al
0x140039ea7  jz      short loc_140039ED3
0x140039ea9  lea     rcx, W32pServiceTableFilter
0x140039eb0  mov     edx, cs:W32pServiceLimitFilter
0x140039eb6  mov     rax, 124h
0x140039ebd  lea     rcx, [rcx+rdx*4]
0x140039ec1  movsx   eax, byte ptr [rcx+rax]
0x140039ec5  or      eax, eax
0x140039ec7  jle     short loc_140039ECE
0x140039ec9  mov     eax, 0C000001Ch
0x140039ece  add     rsp, 48h
0x140039ed2  retn
0x140039ed3  mov     rax, cs:__imp_NtDCompositionDuplicateSwapchainHandleToDwm
0x140039eda  mov     rcx, [rsp+48h+var_28]
0x140039edf  mov     rdx, [rsp+48h+var_20]
0x140039ee4  mov     r8, [rsp+48h+var_18]
0x140039ee9  mov     r9, [rsp+48h+var_10]
0x140039eee  add     rsp, 48h
0x140039ef2  jmp     rax
```
