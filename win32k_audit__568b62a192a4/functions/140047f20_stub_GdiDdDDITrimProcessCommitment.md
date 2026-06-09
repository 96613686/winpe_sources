# _stub_GdiDdDDITrimProcessCommitment

- ea: `0x140047f20`
- end: `0x140047fc7`
- name: `_stub_GdiDdDDITrimProcessCommitment`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140047f20`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140047f69`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140047f69`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDITrimProcessCommitment` at `0x140047fa3`

## string_xrefs

- `0x140047f4f`: `NtGdiDdDDITrimProcessCommitment`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDITrimProcessCommitment(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDITrimProcessCommitment(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDITrimProcessCommitment(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[77] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140047f20  sub     rsp, 48h
0x140047f24  mov     [rsp+48h+var_28], rcx
0x140047f29  mov     [rsp+48h+var_20], rdx
0x140047f2e  mov     [rsp+48h+var_18], r8
0x140047f33  mov     [rsp+48h+var_10], r9
0x140047f38  mov     rcx, 26Bh
0x140047f3f  call    cs:__imp_IsWin32KSyscallFiltered
0x140047f46  nop     dword ptr [rax+rax+00h]
0x140047f4b  test    al, al
0x140047f4d  jz      short loc_140047FA3
0x140047f4f  lea     rcx, aNtgdidddditrim; "NtGdiDdDDITrimProcessCommitment"
0x140047f56  mov     rdx, 26Bh
0x140047f5d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140047f64  nop     dword ptr [rax+rax+00h]
0x140047f69  call    cs:__imp_PsIsWin32KFilterEnabled
0x140047f70  nop     dword ptr [rax+rax+00h]
0x140047f75  test    al, al
0x140047f77  jz      short loc_140047FA3
0x140047f79  lea     rcx, W32pServiceTableFilter
0x140047f80  mov     edx, cs:W32pServiceLimitFilter
0x140047f86  mov     rax, 26Bh
0x140047f8d  lea     rcx, [rcx+rdx*4]
0x140047f91  movsx   eax, byte ptr [rcx+rax]
0x140047f95  or      eax, eax
0x140047f97  jle     short loc_140047F9E
0x140047f99  mov     eax, 0C000001Ch
0x140047f9e  add     rsp, 48h
0x140047fa2  retn
0x140047fa3  mov     rax, cs:__imp_NtGdiDdDDITrimProcessCommitment
0x140047faa  mov     rcx, [rsp+48h+var_28]
0x140047faf  mov     rdx, [rsp+48h+var_20]
0x140047fb4  mov     r8, [rsp+48h+var_18]
0x140047fb9  mov     r9, [rsp+48h+var_10]
0x140047fbe  add     rsp, 48h
0x140047fc2  jmp     rax
```
