# _stub_DxgkAcquireExclusiveEngineAccess

- ea: `0x14003b8e0`
- end: `0x14003b987`
- name: `_stub_DxgkAcquireExclusiveEngineAccess`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b8e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b929`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b929`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkAcquireExclusiveEngineAccess` at `0x14003b963`

## string_xrefs

- `0x14003b90f`: `NtDxgkAcquireExclusiveEngineAccess`

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
0x14003b8e0  sub     rsp, 48h
0x14003b8e4  mov     [rsp+48h+var_28], rcx
0x14003b8e9  mov     [rsp+48h+var_20], rdx
0x14003b8ee  mov     [rsp+48h+var_18], r8
0x14003b8f3  mov     [rsp+48h+var_10], r9
0x14003b8f8  mov     rcx, 148h
0x14003b8ff  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b906  nop     dword ptr [rax+rax+00h]
0x14003b90b  test    al, al
0x14003b90d  jz      short loc_14003B963
0x14003b90f  lea     rcx, aNtdxgkacquiree; "NtDxgkAcquireExclusiveEngineAccess"
0x14003b916  mov     rdx, 148h
0x14003b91d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b924  nop     dword ptr [rax+rax+00h]
0x14003b929  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b930  nop     dword ptr [rax+rax+00h]
0x14003b935  test    al, al
0x14003b937  jz      short loc_14003B963
0x14003b939  lea     rcx, W32pServiceTableFilter
0x14003b940  mov     edx, cs:W32pServiceLimitFilter
0x14003b946  mov     rax, 148h
0x14003b94d  lea     rcx, [rcx+rdx*4]
0x14003b951  movsx   eax, byte ptr [rcx+rax]
0x14003b955  or      eax, eax
0x14003b957  jle     short loc_14003B95E
0x14003b959  mov     eax, 0C000001Ch
0x14003b95e  add     rsp, 48h
0x14003b962  retn
0x14003b963  mov     rax, cs:__imp_NtDxgkAcquireExclusiveEngineAccess
0x14003b96a  mov     rcx, [rsp+48h+var_28]
0x14003b96f  mov     rdx, [rsp+48h+var_20]
0x14003b974  mov     r8, [rsp+48h+var_18]
0x14003b979  mov     r9, [rsp+48h+var_10]
0x14003b97e  add     rsp, 48h
0x14003b982  jmp     rax
```
