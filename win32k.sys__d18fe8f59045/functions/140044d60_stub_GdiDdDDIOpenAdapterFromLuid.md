# _stub_GdiDdDDIOpenAdapterFromLuid

- ea: `0x140044d60`
- end: `0x140044e07`
- name: `_stub_GdiDdDDIOpenAdapterFromLuid`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044d60`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044da9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044da9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenAdapterFromLuid` at `0x140044de3`

## string_xrefs

- `0x140044d8f`: `NtGdiDdDDIOpenAdapterFromLuid`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenAdapterFromLuid(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenAdapterFromLuid(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenAdapterFromLuid(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044d60  sub     rsp, 48h
0x140044d64  mov     [rsp+48h+var_28], rcx
0x140044d69  mov     [rsp+48h+var_20], rdx
0x140044d6e  mov     [rsp+48h+var_18], r8
0x140044d73  mov     [rsp+48h+var_10], r9
0x140044d78  mov     rcx, 220h
0x140044d7f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044d86  nop     dword ptr [rax+rax+00h]
0x140044d8b  test    al, al
0x140044d8d  jz      short loc_140044DE3
0x140044d8f  lea     rcx, aNtgdiddddiopen_1; "NtGdiDdDDIOpenAdapterFromLuid"
0x140044d96  mov     rdx, 220h
0x140044d9d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044da4  nop     dword ptr [rax+rax+00h]
0x140044da9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044db0  nop     dword ptr [rax+rax+00h]
0x140044db5  test    al, al
0x140044db7  jz      short loc_140044DE3
0x140044db9  lea     rcx, W32pServiceTableFilter
0x140044dc0  mov     edx, cs:W32pServiceLimitFilter
0x140044dc6  mov     rax, 220h
0x140044dcd  lea     rcx, [rcx+rdx*4]
0x140044dd1  movsx   eax, byte ptr [rcx+rax]
0x140044dd5  or      eax, eax
0x140044dd7  jle     short loc_140044DDE
0x140044dd9  mov     eax, 0C000001Ch
0x140044dde  add     rsp, 48h
0x140044de2  retn
0x140044de3  mov     rax, cs:__imp_NtGdiDdDDIOpenAdapterFromLuid
0x140044dea  mov     rcx, [rsp+48h+var_28]
0x140044def  mov     rdx, [rsp+48h+var_20]
0x140044df4  mov     r8, [rsp+48h+var_18]
0x140044df9  mov     r9, [rsp+48h+var_10]
0x140044dfe  add     rsp, 48h
0x140044e02  jmp     rax
```
