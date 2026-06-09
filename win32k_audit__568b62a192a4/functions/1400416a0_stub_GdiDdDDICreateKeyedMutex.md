# _stub_GdiDdDDICreateKeyedMutex

- ea: `0x1400416a0`
- end: `0x140041747`
- name: `_stub_GdiDdDDICreateKeyedMutex`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400416a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400416e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400416e9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateKeyedMutex` at `0x140041723`

## string_xrefs

- `0x1400416cf`: `NtGdiDdDDICreateKeyedMutex`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateKeyedMutex(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateKeyedMutex(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateKeyedMutex(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400416a0  sub     rsp, 48h
0x1400416a4  mov     [rsp+48h+var_28], rcx
0x1400416a9  mov     [rsp+48h+var_20], rdx
0x1400416ae  mov     [rsp+48h+var_18], r8
0x1400416b3  mov     [rsp+48h+var_10], r9
0x1400416b8  mov     rcx, 1D3h
0x1400416bf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400416c6  nop     dword ptr [rax+rax+00h]
0x1400416cb  test    al, al
0x1400416cd  jz      short loc_140041723
0x1400416cf  lea     rcx, aNtgdiddddicrea_7; "NtGdiDdDDICreateKeyedMutex"
0x1400416d6  mov     rdx, 1D3h
0x1400416dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400416e4  nop     dword ptr [rax+rax+00h]
0x1400416e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400416f0  nop     dword ptr [rax+rax+00h]
0x1400416f5  test    al, al
0x1400416f7  jz      short loc_140041723
0x1400416f9  lea     rcx, W32pServiceTableFilter
0x140041700  mov     edx, cs:W32pServiceLimitFilter
0x140041706  mov     rax, 1D3h
0x14004170d  lea     rcx, [rcx+rdx*4]
0x140041711  movsx   eax, byte ptr [rcx+rax]
0x140041715  or      eax, eax
0x140041717  jle     short loc_14004171E
0x140041719  mov     eax, 0C000001Ch
0x14004171e  add     rsp, 48h
0x140041722  retn
0x140041723  mov     rax, cs:__imp_NtGdiDdDDICreateKeyedMutex
0x14004172a  mov     rcx, [rsp+48h+var_28]
0x14004172f  mov     rdx, [rsp+48h+var_20]
0x140041734  mov     r8, [rsp+48h+var_18]
0x140041739  mov     r9, [rsp+48h+var_10]
0x14004173e  add     rsp, 48h
0x140041742  jmp     rax
```
