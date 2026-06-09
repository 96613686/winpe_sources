# _stub_ValidateCompositionSurfaceHandle

- ea: `0x14006d3e0`
- end: `0x14006d487`
- name: `_stub_ValidateCompositionSurfaceHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14006d3e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14006d429`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14006d429`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtValidateCompositionSurfaceHandle` at `0x14006d463`

## string_xrefs

- `0x14006d40f`: `NtValidateCompositionSurfaceHandle`

## pseudocode

```c
__int64 __fastcall stub_ValidateCompositionSurfaceHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtValidateCompositionSurfaceHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtValidateCompositionSurfaceHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[185] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14006d3e0  sub     rsp, 48h
0x14006d3e4  mov     [rsp+48h+var_28], rcx
0x14006d3e9  mov     [rsp+48h+var_20], rdx
0x14006d3ee  mov     [rsp+48h+var_18], r8
0x14006d3f3  mov     [rsp+48h+var_10], r9
0x14006d3f8  mov     rcx, 5CFh
0x14006d3ff  call    cs:__imp_IsWin32KSyscallFiltered
0x14006d406  nop     dword ptr [rax+rax+00h]
0x14006d40b  test    al, al
0x14006d40d  jz      short loc_14006D463
0x14006d40f  lea     rcx, aNtvalidatecomp; "NtValidateCompositionSurfaceHandle"
0x14006d416  mov     rdx, 5CFh
0x14006d41d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14006d424  nop     dword ptr [rax+rax+00h]
0x14006d429  call    cs:__imp_PsIsWin32KFilterEnabled
0x14006d430  nop     dword ptr [rax+rax+00h]
0x14006d435  test    al, al
0x14006d437  jz      short loc_14006D463
0x14006d439  lea     rcx, W32pServiceTableFilter
0x14006d440  mov     edx, cs:W32pServiceLimitFilter
0x14006d446  mov     rax, 5CFh
0x14006d44d  lea     rcx, [rcx+rdx*4]
0x14006d451  movsx   eax, byte ptr [rcx+rax]
0x14006d455  or      eax, eax
0x14006d457  jle     short loc_14006D45E
0x14006d459  mov     eax, 0C000001Ch
0x14006d45e  add     rsp, 48h
0x14006d462  retn
0x14006d463  mov     rax, cs:__imp_NtValidateCompositionSurfaceHandle
0x14006d46a  mov     rcx, [rsp+48h+var_28]
0x14006d46f  mov     rdx, [rsp+48h+var_20]
0x14006d474  mov     r8, [rsp+48h+var_18]
0x14006d479  mov     r9, [rsp+48h+var_10]
0x14006d47e  add     rsp, 48h
0x14006d482  jmp     rax
```
