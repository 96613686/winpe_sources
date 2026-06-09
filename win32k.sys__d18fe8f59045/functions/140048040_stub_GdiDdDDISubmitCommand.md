# _stub_GdiDdDDISubmitCommand

- ea: `0x140048040`
- end: `0x1400480e7`
- name: `_stub_GdiDdDDISubmitCommand`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140048040`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048089`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048089`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDISubmitCommand` at `0x1400480c3`

## string_xrefs

- `0x14004806f`: `NtGdiDdDDISubmitCommand`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDISubmitCommand(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDISubmitCommand(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDISubmitCommand(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[77] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140048040  sub     rsp, 48h
0x140048044  mov     [rsp+48h+var_28], rcx
0x140048049  mov     [rsp+48h+var_20], rdx
0x14004804e  mov     [rsp+48h+var_18], r8
0x140048053  mov     [rsp+48h+var_10], r9
0x140048058  mov     rcx, 26Ah
0x14004805f  call    cs:__imp_IsWin32KSyscallFiltered
0x140048066  nop     dword ptr [rax+rax+00h]
0x14004806b  test    al, al
0x14004806d  jz      short loc_1400480C3
0x14004806f  lea     rcx, aNtgdiddddisubm; "NtGdiDdDDISubmitCommand"
0x140048076  mov     rdx, 26Ah
0x14004807d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140048084  nop     dword ptr [rax+rax+00h]
0x140048089  call    cs:__imp_PsIsWin32KFilterEnabled
0x140048090  nop     dword ptr [rax+rax+00h]
0x140048095  test    al, al
0x140048097  jz      short loc_1400480C3
0x140048099  lea     rcx, W32pServiceTableFilter
0x1400480a0  mov     edx, cs:W32pServiceLimitFilter
0x1400480a6  mov     rax, 26Ah
0x1400480ad  lea     rcx, [rcx+rdx*4]
0x1400480b1  movsx   eax, byte ptr [rcx+rax]
0x1400480b5  or      eax, eax
0x1400480b7  jle     short loc_1400480BE
0x1400480b9  mov     eax, 0C000001Ch
0x1400480be  add     rsp, 48h
0x1400480c2  retn
0x1400480c3  mov     rax, cs:__imp_NtGdiDdDDISubmitCommand
0x1400480ca  mov     rcx, [rsp+48h+var_28]
0x1400480cf  mov     rdx, [rsp+48h+var_20]
0x1400480d4  mov     r8, [rsp+48h+var_18]
0x1400480d9  mov     r9, [rsp+48h+var_10]
0x1400480de  add     rsp, 48h
0x1400480e2  jmp     rax
```
