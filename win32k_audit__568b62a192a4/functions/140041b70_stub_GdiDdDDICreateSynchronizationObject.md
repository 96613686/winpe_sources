# _stub_GdiDdDDICreateSynchronizationObject

- ea: `0x140041b70`
- end: `0x140041c17`
- name: `_stub_GdiDdDDICreateSynchronizationObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041b70`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041bb9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041bb9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateSynchronizationObject` at `0x140041bf3`

## string_xrefs

- `0x140041b9f`: `NtGdiDdDDICreateSynchronizationObject`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041b70  sub     rsp, 48h
0x140041b74  mov     [rsp+48h+var_28], rcx
0x140041b79  mov     [rsp+48h+var_20], rdx
0x140041b7e  mov     [rsp+48h+var_18], r8
0x140041b83  mov     [rsp+48h+var_10], r9
0x140041b88  mov     rcx, 1DAh
0x140041b8f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041b96  nop     dword ptr [rax+rax+00h]
0x140041b9b  test    al, al
0x140041b9d  jz      short loc_140041BF3
0x140041b9f  lea     rcx, aNtgdiddddicrea_14; "NtGdiDdDDICreateSynchronizationObject"
0x140041ba6  mov     rdx, 1DAh
0x140041bad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041bb4  nop     dword ptr [rax+rax+00h]
0x140041bb9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041bc0  nop     dword ptr [rax+rax+00h]
0x140041bc5  test    al, al
0x140041bc7  jz      short loc_140041BF3
0x140041bc9  lea     rcx, W32pServiceTableFilter
0x140041bd0  mov     edx, cs:W32pServiceLimitFilter
0x140041bd6  mov     rax, 1DAh
0x140041bdd  lea     rcx, [rcx+rdx*4]
0x140041be1  movsx   eax, byte ptr [rcx+rax]
0x140041be5  or      eax, eax
0x140041be7  jle     short loc_140041BEE
0x140041be9  mov     eax, 0C000001Ch
0x140041bee  add     rsp, 48h
0x140041bf2  retn
0x140041bf3  mov     rax, cs:__imp_NtGdiDdDDICreateSynchronizationObject
0x140041bfa  mov     rcx, [rsp+48h+var_28]
0x140041bff  mov     rdx, [rsp+48h+var_20]
0x140041c04  mov     r8, [rsp+48h+var_18]
0x140041c09  mov     r9, [rsp+48h+var_10]
0x140041c0e  add     rsp, 48h
0x140041c12  jmp     rax
```
