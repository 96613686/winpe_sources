# _stub_DCompositionWaitForCompositorClock

- ea: `0x14003b500`
- end: `0x14003b5a7`
- name: `_stub_DCompositionWaitForCompositorClock`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b500`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b549`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b549`

## string_xrefs

- `0x14003b52f`: `NtDCompositionWaitForCompositorClock`

## pseudocode

```c
__int64 stub_DCompositionWaitForCompositorClock()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionWaitForCompositorClock();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionWaitForCompositorClock();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b500  sub     rsp, 48h
0x14003b504  mov     [rsp+48h+var_28], rcx
0x14003b509  mov     [rsp+48h+var_20], rdx
0x14003b50e  mov     [rsp+48h+var_18], r8
0x14003b513  mov     [rsp+48h+var_10], r9
0x14003b518  mov     rcx, 145h
0x14003b51f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b526  nop     dword ptr [rax+rax+00h]
0x14003b52b  test    al, al
0x14003b52d  jz      short loc_14003B583
0x14003b52f  lea     rcx, aNtdcomposition_49; "NtDCompositionWaitForCompositorClock"
0x14003b536  mov     rdx, 145h
0x14003b53d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b544  nop     dword ptr [rax+rax+00h]
0x14003b549  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b550  nop     dword ptr [rax+rax+00h]
0x14003b555  test    al, al
0x14003b557  jz      short loc_14003B583
0x14003b559  lea     rcx, W32pServiceTableFilter
0x14003b560  mov     edx, cs:W32pServiceLimitFilter
0x14003b566  mov     rax, 145h
0x14003b56d  lea     rcx, [rcx+rdx*4]
0x14003b571  movsx   eax, byte ptr [rcx+rax]
0x14003b575  or      eax, eax
0x14003b577  jle     short loc_14003B57E
0x14003b579  mov     eax, 0C000001Ch
0x14003b57e  add     rsp, 48h
0x14003b582  retn
0x14003b583  mov     rax, cs:__imp_NtDCompositionWaitForCompositorClock
0x14003b58a  mov     rcx, [rsp+48h+var_28]
0x14003b58f  mov     rdx, [rsp+48h+var_20]
0x14003b594  mov     r8, [rsp+48h+var_18]
0x14003b599  mov     r9, [rsp+48h+var_10]
0x14003b59e  add     rsp, 48h
0x14003b5a2  jmp     rax
```
