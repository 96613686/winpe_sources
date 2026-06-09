# _stub_GdiDdDDIQueryAllocationResidency

- ea: `0x140045b60`
- end: `0x140045c07`
- name: `_stub_GdiDdDDIQueryAllocationResidency`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045b60`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045ba9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045ba9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIQueryAllocationResidency` at `0x140045be3`

## string_xrefs

- `0x140045b8f`: `NtGdiDdDDIQueryAllocationResidency`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[70] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045b60  sub     rsp, 48h
0x140045b64  mov     [rsp+48h+var_28], rcx
0x140045b69  mov     [rsp+48h+var_20], rdx
0x140045b6e  mov     [rsp+48h+var_18], r8
0x140045b73  mov     [rsp+48h+var_10], r9
0x140045b78  mov     rcx, 237h
0x140045b7f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045b86  nop     dword ptr [rax+rax+00h]
0x140045b8b  test    al, al
0x140045b8d  jz      short loc_140045BE3
0x140045b8f  lea     rcx, aNtgdiddddiquer_0; "NtGdiDdDDIQueryAllocationResidency"
0x140045b96  mov     rdx, 237h
0x140045b9d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045ba4  nop     dword ptr [rax+rax+00h]
0x140045ba9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045bb0  nop     dword ptr [rax+rax+00h]
0x140045bb5  test    al, al
0x140045bb7  jz      short loc_140045BE3
0x140045bb9  lea     rcx, W32pServiceTableFilter
0x140045bc0  mov     edx, cs:W32pServiceLimitFilter
0x140045bc6  mov     rax, 237h
0x140045bcd  lea     rcx, [rcx+rdx*4]
0x140045bd1  movsx   eax, byte ptr [rcx+rax]
0x140045bd5  or      eax, eax
0x140045bd7  jle     short loc_140045BDE
0x140045bd9  mov     eax, 0C000001Ch
0x140045bde  add     rsp, 48h
0x140045be2  retn
0x140045be3  mov     rax, cs:__imp_NtGdiDdDDIQueryAllocationResidency
0x140045bea  mov     rcx, [rsp+48h+var_28]
0x140045bef  mov     rdx, [rsp+48h+var_20]
0x140045bf4  mov     r8, [rsp+48h+var_18]
0x140045bf9  mov     r9, [rsp+48h+var_10]
0x140045bfe  add     rsp, 48h
0x140045c02  jmp     rax
```
