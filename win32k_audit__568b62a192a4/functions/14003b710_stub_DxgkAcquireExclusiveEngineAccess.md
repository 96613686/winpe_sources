# _stub_DxgkAcquireExclusiveEngineAccess

- ea: `0x14003b710`
- end: `0x14003b7b7`
- name: `_stub_DxgkAcquireExclusiveEngineAccess`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b710`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b759`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b759`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkAcquireExclusiveEngineAccess` at `0x14003b793`

## string_xrefs

- `0x14003b73f`: `NtDxgkAcquireExclusiveEngineAccess`

## pseudocode

```c
__int64 __fastcall stub_DxgkAcquireExclusiveEngineAccess(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkAcquireExclusiveEngineAccess(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkAcquireExclusiveEngineAccess(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[41] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b710  sub     rsp, 48h
0x14003b714  mov     [rsp+48h+var_28], rcx
0x14003b719  mov     [rsp+48h+var_20], rdx
0x14003b71e  mov     [rsp+48h+var_18], r8
0x14003b723  mov     [rsp+48h+var_10], r9
0x14003b728  mov     rcx, 148h
0x14003b72f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b736  nop     dword ptr [rax+rax+00h]
0x14003b73b  test    al, al
0x14003b73d  jz      short loc_14003B793
0x14003b73f  lea     rcx, aNtdxgkacquiree; "NtDxgkAcquireExclusiveEngineAccess"
0x14003b746  mov     rdx, 148h
0x14003b74d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b754  nop     dword ptr [rax+rax+00h]
0x14003b759  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b760  nop     dword ptr [rax+rax+00h]
0x14003b765  test    al, al
0x14003b767  jz      short loc_14003B793
0x14003b769  lea     rcx, W32pServiceTableFilter
0x14003b770  mov     edx, cs:W32pServiceLimitFilter
0x14003b776  mov     rax, 148h
0x14003b77d  lea     rcx, [rcx+rdx*4]
0x14003b781  movsx   eax, byte ptr [rcx+rax]
0x14003b785  or      eax, eax
0x14003b787  jle     short loc_14003B78E
0x14003b789  mov     eax, 0C000001Ch
0x14003b78e  add     rsp, 48h
0x14003b792  retn
0x14003b793  mov     rax, cs:__imp_NtDxgkAcquireExclusiveEngineAccess
0x14003b79a  mov     rcx, [rsp+48h+var_28]
0x14003b79f  mov     rdx, [rsp+48h+var_20]
0x14003b7a4  mov     r8, [rsp+48h+var_18]
0x14003b7a9  mov     r9, [rsp+48h+var_10]
0x14003b7ae  add     rsp, 48h
0x14003b7b2  jmp     rax
```
