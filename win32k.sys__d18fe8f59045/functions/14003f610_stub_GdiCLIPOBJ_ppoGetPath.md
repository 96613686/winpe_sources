# _stub_GdiCLIPOBJ_ppoGetPath

- ea: `0x14003f610`
- end: `0x14003f6b7`
- name: `_stub_GdiCLIPOBJ_ppoGetPath`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003f610`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003f659`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003f659`

## string_xrefs

- `0x14003f63f`: `NtGdiCLIPOBJ_ppoGetPath`

## pseudocode

```c
__int64 stub_GdiCLIPOBJ_ppoGetPath()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiCLIPOBJ_ppoGetPath();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiCLIPOBJ_ppoGetPath();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[52] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003f610  sub     rsp, 48h
0x14003f614  mov     [rsp+48h+var_28], rcx
0x14003f619  mov     [rsp+48h+var_20], rdx
0x14003f61e  mov     [rsp+48h+var_18], r8
0x14003f623  mov     [rsp+48h+var_10], r9
0x14003f628  mov     rcx, 1A1h
0x14003f62f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003f636  nop     dword ptr [rax+rax+00h]
0x14003f63b  test    al, al
0x14003f63d  jz      short loc_14003F693
0x14003f63f  lea     rcx, aNtgdiclipobjPp; "NtGdiCLIPOBJ_ppoGetPath"
0x14003f646  mov     rdx, 1A1h
0x14003f64d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003f654  nop     dword ptr [rax+rax+00h]
0x14003f659  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003f660  nop     dword ptr [rax+rax+00h]
0x14003f665  test    al, al
0x14003f667  jz      short loc_14003F693
0x14003f669  lea     rcx, W32pServiceTableFilter
0x14003f670  mov     edx, cs:W32pServiceLimitFilter
0x14003f676  mov     rax, 1A1h
0x14003f67d  lea     rcx, [rcx+rdx*4]
0x14003f681  movsx   eax, byte ptr [rcx+rax]
0x14003f685  or      eax, eax
0x14003f687  jle     short loc_14003F68E
0x14003f689  mov     eax, 0C000001Ch
0x14003f68e  add     rsp, 48h
0x14003f692  retn
0x14003f693  mov     rax, cs:__imp_NtGdiCLIPOBJ_ppoGetPath
0x14003f69a  mov     rcx, [rsp+48h+var_28]
0x14003f69f  mov     rdx, [rsp+48h+var_20]
0x14003f6a4  mov     r8, [rsp+48h+var_18]
0x14003f6a9  mov     r9, [rsp+48h+var_10]
0x14003f6ae  add     rsp, 48h
0x14003f6b2  jmp     rax
```
