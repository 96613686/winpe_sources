# _stub_GdiDdDDICreateSynchronizationObject

- ea: `0x140041f50`
- end: `0x140041ff7`
- name: `_stub_GdiDdDDICreateSynchronizationObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041f50`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041f99`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041f99`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateSynchronizationObject` at `0x140041fd3`

## string_xrefs

- `0x140041f7f`: `NtGdiDdDDICreateSynchronizationObject`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateSynchronizationObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateSynchronizationObject(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateSynchronizationObject(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041f50  sub     rsp, 48h
0x140041f54  mov     [rsp+48h+var_28], rcx
0x140041f59  mov     [rsp+48h+var_20], rdx
0x140041f5e  mov     [rsp+48h+var_18], r8
0x140041f63  mov     [rsp+48h+var_10], r9
0x140041f68  mov     rcx, 1DDh
0x140041f6f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041f76  nop     dword ptr [rax+rax+00h]
0x140041f7b  test    al, al
0x140041f7d  jz      short loc_140041FD3
0x140041f7f  lea     rcx, aNtgdiddddicrea_14; "NtGdiDdDDICreateSynchronizationObject"
0x140041f86  mov     rdx, 1DDh
0x140041f8d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041f94  nop     dword ptr [rax+rax+00h]
0x140041f99  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041fa0  nop     dword ptr [rax+rax+00h]
0x140041fa5  test    al, al
0x140041fa7  jz      short loc_140041FD3
0x140041fa9  lea     rcx, W32pServiceTableFilter
0x140041fb0  mov     edx, cs:W32pServiceLimitFilter
0x140041fb6  mov     rax, 1DDh
0x140041fbd  lea     rcx, [rcx+rdx*4]
0x140041fc1  movsx   eax, byte ptr [rcx+rax]
0x140041fc5  or      eax, eax
0x140041fc7  jle     short loc_140041FCE
0x140041fc9  mov     eax, 0C000001Ch
0x140041fce  add     rsp, 48h
0x140041fd2  retn
0x140041fd3  mov     rax, cs:__imp_NtGdiDdDDICreateSynchronizationObject
0x140041fda  mov     rcx, [rsp+48h+var_28]
0x140041fdf  mov     rdx, [rsp+48h+var_20]
0x140041fe4  mov     r8, [rsp+48h+var_18]
0x140041fe9  mov     r9, [rsp+48h+var_10]
0x140041fee  add     rsp, 48h
0x140041ff2  jmp     rax
```
