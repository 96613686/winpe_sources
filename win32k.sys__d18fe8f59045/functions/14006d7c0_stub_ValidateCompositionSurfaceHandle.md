# _stub_ValidateCompositionSurfaceHandle

- ea: `0x14006d7c0`
- end: `0x14006d867`
- name: `_stub_ValidateCompositionSurfaceHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14006d7c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14006d809`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14006d809`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtValidateCompositionSurfaceHandle` at `0x14006d843`

## string_xrefs

- `0x14006d7ef`: `NtValidateCompositionSurfaceHandle`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[186] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14006d7c0  sub     rsp, 48h
0x14006d7c4  mov     [rsp+48h+var_28], rcx
0x14006d7c9  mov     [rsp+48h+var_20], rdx
0x14006d7ce  mov     [rsp+48h+var_18], r8
0x14006d7d3  mov     [rsp+48h+var_10], r9
0x14006d7d8  mov     rcx, 5D2h
0x14006d7df  call    cs:__imp_IsWin32KSyscallFiltered
0x14006d7e6  nop     dword ptr [rax+rax+00h]
0x14006d7eb  test    al, al
0x14006d7ed  jz      short loc_14006D843
0x14006d7ef  lea     rcx, aNtvalidatecomp; "NtValidateCompositionSurfaceHandle"
0x14006d7f6  mov     rdx, 5D2h
0x14006d7fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14006d804  nop     dword ptr [rax+rax+00h]
0x14006d809  call    cs:__imp_PsIsWin32KFilterEnabled
0x14006d810  nop     dword ptr [rax+rax+00h]
0x14006d815  test    al, al
0x14006d817  jz      short loc_14006D843
0x14006d819  lea     rcx, W32pServiceTableFilter
0x14006d820  mov     edx, cs:W32pServiceLimitFilter
0x14006d826  mov     rax, 5D2h
0x14006d82d  lea     rcx, [rcx+rdx*4]
0x14006d831  movsx   eax, byte ptr [rcx+rax]
0x14006d835  or      eax, eax
0x14006d837  jle     short loc_14006D83E
0x14006d839  mov     eax, 0C000001Ch
0x14006d83e  add     rsp, 48h
0x14006d842  retn
0x14006d843  mov     rax, cs:__imp_NtValidateCompositionSurfaceHandle
0x14006d84a  mov     rcx, [rsp+48h+var_28]
0x14006d84f  mov     rdx, [rsp+48h+var_20]
0x14006d854  mov     r8, [rsp+48h+var_18]
0x14006d859  mov     r9, [rsp+48h+var_10]
0x14006d85e  add     rsp, 48h
0x14006d862  jmp     rax
```
