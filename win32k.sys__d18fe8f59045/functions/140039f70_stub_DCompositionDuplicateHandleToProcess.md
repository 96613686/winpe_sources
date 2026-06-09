# _stub_DCompositionDuplicateHandleToProcess

- ea: `0x140039f70`
- end: `0x14003a017`
- name: `_stub_DCompositionDuplicateHandleToProcess`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039f70`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039fb9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039fb9`

## string_xrefs

- `0x140039f9f`: `NtDCompositionDuplicateHandleToProcess`

## pseudocode

```c
__int64 stub_DCompositionDuplicateHandleToProcess()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionDuplicateHandleToProcess();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionDuplicateHandleToProcess();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039f70  sub     rsp, 48h
0x140039f74  mov     [rsp+48h+var_28], rcx
0x140039f79  mov     [rsp+48h+var_20], rdx
0x140039f7e  mov     [rsp+48h+var_18], r8
0x140039f83  mov     [rsp+48h+var_10], r9
0x140039f88  mov     rcx, 123h
0x140039f8f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039f96  nop     dword ptr [rax+rax+00h]
0x140039f9b  test    al, al
0x140039f9d  jz      short loc_140039FF3
0x140039f9f  lea     rcx, aNtdcomposition_15; "NtDCompositionDuplicateHandleToProcess"
0x140039fa6  mov     rdx, 123h
0x140039fad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039fb4  nop     dword ptr [rax+rax+00h]
0x140039fb9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039fc0  nop     dword ptr [rax+rax+00h]
0x140039fc5  test    al, al
0x140039fc7  jz      short loc_140039FF3
0x140039fc9  lea     rcx, W32pServiceTableFilter
0x140039fd0  mov     edx, cs:W32pServiceLimitFilter
0x140039fd6  mov     rax, 123h
0x140039fdd  lea     rcx, [rcx+rdx*4]
0x140039fe1  movsx   eax, byte ptr [rcx+rax]
0x140039fe5  or      eax, eax
0x140039fe7  jle     short loc_140039FEE
0x140039fe9  mov     eax, 0C000001Ch
0x140039fee  add     rsp, 48h
0x140039ff2  retn
0x140039ff3  mov     rax, cs:__imp_NtDCompositionDuplicateHandleToProcess
0x140039ffa  mov     rcx, [rsp+48h+var_28]
0x140039fff  mov     rdx, [rsp+48h+var_20]
0x14003a004  mov     r8, [rsp+48h+var_18]
0x14003a009  mov     r9, [rsp+48h+var_10]
0x14003a00e  add     rsp, 48h
0x14003a012  jmp     rax
```
