# _stub_GdiDdDDICreateKeyedMutex2

- ea: `0x140041b30`
- end: `0x140041bd7`
- name: `_stub_GdiDdDDICreateKeyedMutex2`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041b30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041b79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041b79`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateKeyedMutex2` at `0x140041bb3`

## string_xrefs

- `0x140041b5f`: `NtGdiDdDDICreateKeyedMutex2`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateKeyedMutex2(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateKeyedMutex2(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateKeyedMutex2(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041b30  sub     rsp, 48h
0x140041b34  mov     [rsp+48h+var_28], rcx
0x140041b39  mov     [rsp+48h+var_20], rdx
0x140041b3e  mov     [rsp+48h+var_18], r8
0x140041b43  mov     [rsp+48h+var_10], r9
0x140041b48  mov     rcx, 1D7h
0x140041b4f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041b56  nop     dword ptr [rax+rax+00h]
0x140041b5b  test    al, al
0x140041b5d  jz      short loc_140041BB3
0x140041b5f  lea     rcx, aNtgdiddddicrea_8; "NtGdiDdDDICreateKeyedMutex2"
0x140041b66  mov     rdx, 1D7h
0x140041b6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041b74  nop     dword ptr [rax+rax+00h]
0x140041b79  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041b80  nop     dword ptr [rax+rax+00h]
0x140041b85  test    al, al
0x140041b87  jz      short loc_140041BB3
0x140041b89  lea     rcx, W32pServiceTableFilter
0x140041b90  mov     edx, cs:W32pServiceLimitFilter
0x140041b96  mov     rax, 1D7h
0x140041b9d  lea     rcx, [rcx+rdx*4]
0x140041ba1  movsx   eax, byte ptr [rcx+rax]
0x140041ba5  or      eax, eax
0x140041ba7  jle     short loc_140041BAE
0x140041ba9  mov     eax, 0C000001Ch
0x140041bae  add     rsp, 48h
0x140041bb2  retn
0x140041bb3  mov     rax, cs:__imp_NtGdiDdDDICreateKeyedMutex2
0x140041bba  mov     rcx, [rsp+48h+var_28]
0x140041bbf  mov     rdx, [rsp+48h+var_20]
0x140041bc4  mov     r8, [rsp+48h+var_18]
0x140041bc9  mov     r9, [rsp+48h+var_10]
0x140041bce  add     rsp, 48h
0x140041bd2  jmp     rax
```
