# _stub_DxgkCheckEngineAccess

- ea: `0x14003b870`
- end: `0x14003b917`
- name: `_stub_DxgkCheckEngineAccess`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b870`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b8b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b8b9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCheckEngineAccess` at `0x14003b8f3`

## string_xrefs

- `0x14003b89f`: `NtDxgkCheckEngineAccess`

## pseudocode

```c
__int64 __fastcall stub_DxgkCheckEngineAccess(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkCheckEngineAccess(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkCheckEngineAccess(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[41] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b870  sub     rsp, 48h
0x14003b874  mov     [rsp+48h+var_28], rcx
0x14003b879  mov     [rsp+48h+var_20], rdx
0x14003b87e  mov     [rsp+48h+var_18], r8
0x14003b883  mov     [rsp+48h+var_10], r9
0x14003b888  mov     rcx, 14Ah
0x14003b88f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b896  nop     dword ptr [rax+rax+00h]
0x14003b89b  test    al, al
0x14003b89d  jz      short loc_14003B8F3
0x14003b89f  lea     rcx, aNtdxgkcheckeng; "NtDxgkCheckEngineAccess"
0x14003b8a6  mov     rdx, 14Ah
0x14003b8ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b8b4  nop     dword ptr [rax+rax+00h]
0x14003b8b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b8c0  nop     dword ptr [rax+rax+00h]
0x14003b8c5  test    al, al
0x14003b8c7  jz      short loc_14003B8F3
0x14003b8c9  lea     rcx, W32pServiceTableFilter
0x14003b8d0  mov     edx, cs:W32pServiceLimitFilter
0x14003b8d6  mov     rax, 14Ah
0x14003b8dd  lea     rcx, [rcx+rdx*4]
0x14003b8e1  movsx   eax, byte ptr [rcx+rax]
0x14003b8e5  or      eax, eax
0x14003b8e7  jle     short loc_14003B8EE
0x14003b8e9  mov     eax, 0C000001Ch
0x14003b8ee  add     rsp, 48h
0x14003b8f2  retn
0x14003b8f3  mov     rax, cs:__imp_NtDxgkCheckEngineAccess
0x14003b8fa  mov     rcx, [rsp+48h+var_28]
0x14003b8ff  mov     rdx, [rsp+48h+var_20]
0x14003b904  mov     r8, [rsp+48h+var_18]
0x14003b909  mov     r9, [rsp+48h+var_10]
0x14003b90e  add     rsp, 48h
0x14003b912  jmp     rax
```
