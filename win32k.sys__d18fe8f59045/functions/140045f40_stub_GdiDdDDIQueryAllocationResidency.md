# _stub_GdiDdDDIQueryAllocationResidency

- ea: `0x140045f40`
- end: `0x140045fe7`
- name: `_stub_GdiDdDDIQueryAllocationResidency`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045f40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045f89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045f89`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIQueryAllocationResidency` at `0x140045fc3`

## string_xrefs

- `0x140045f6f`: `NtGdiDdDDIQueryAllocationResidency`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIQueryAllocationResidency(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIQueryAllocationResidency(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIQueryAllocationResidency(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[71] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045f40  sub     rsp, 48h
0x140045f44  mov     [rsp+48h+var_28], rcx
0x140045f49  mov     [rsp+48h+var_20], rdx
0x140045f4e  mov     [rsp+48h+var_18], r8
0x140045f53  mov     [rsp+48h+var_10], r9
0x140045f58  mov     rcx, 23Ah
0x140045f5f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045f66  nop     dword ptr [rax+rax+00h]
0x140045f6b  test    al, al
0x140045f6d  jz      short loc_140045FC3
0x140045f6f  lea     rcx, aNtgdiddddiquer_0; "NtGdiDdDDIQueryAllocationResidency"
0x140045f76  mov     rdx, 23Ah
0x140045f7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045f84  nop     dword ptr [rax+rax+00h]
0x140045f89  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045f90  nop     dword ptr [rax+rax+00h]
0x140045f95  test    al, al
0x140045f97  jz      short loc_140045FC3
0x140045f99  lea     rcx, W32pServiceTableFilter
0x140045fa0  mov     edx, cs:W32pServiceLimitFilter
0x140045fa6  mov     rax, 23Ah
0x140045fad  lea     rcx, [rcx+rdx*4]
0x140045fb1  movsx   eax, byte ptr [rcx+rax]
0x140045fb5  or      eax, eax
0x140045fb7  jle     short loc_140045FBE
0x140045fb9  mov     eax, 0C000001Ch
0x140045fbe  add     rsp, 48h
0x140045fc2  retn
0x140045fc3  mov     rax, cs:__imp_NtGdiDdDDIQueryAllocationResidency
0x140045fca  mov     rcx, [rsp+48h+var_28]
0x140045fcf  mov     rdx, [rsp+48h+var_20]
0x140045fd4  mov     r8, [rsp+48h+var_18]
0x140045fd9  mov     r9, [rsp+48h+var_10]
0x140045fde  add     rsp, 48h
0x140045fe2  jmp     rax
```
