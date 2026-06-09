# _stub_DxgkCreateDoorbell

- ea: `0x14003bd00`
- end: `0x14003bda7`
- name: `_stub_DxgkCreateDoorbell`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003bd00`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bd49`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bd49`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCreateDoorbell` at `0x14003bd83`

## string_xrefs

- `0x14003bd2f`: `NtDxgkCreateDoorbell`

## pseudocode

```c
__int64 __fastcall stub_DxgkCreateDoorbell(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkCreateDoorbell(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkCreateDoorbell(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[41] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003bd00  sub     rsp, 48h
0x14003bd04  mov     [rsp+48h+var_28], rcx
0x14003bd09  mov     [rsp+48h+var_20], rdx
0x14003bd0e  mov     [rsp+48h+var_18], r8
0x14003bd13  mov     [rsp+48h+var_10], r9
0x14003bd18  mov     rcx, 14Eh
0x14003bd1f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003bd26  nop     dword ptr [rax+rax+00h]
0x14003bd2b  test    al, al
0x14003bd2d  jz      short loc_14003BD83
0x14003bd2f  lea     rcx, aNtdxgkcreatedo; "NtDxgkCreateDoorbell"
0x14003bd36  mov     rdx, 14Eh
0x14003bd3d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003bd44  nop     dword ptr [rax+rax+00h]
0x14003bd49  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003bd50  nop     dword ptr [rax+rax+00h]
0x14003bd55  test    al, al
0x14003bd57  jz      short loc_14003BD83
0x14003bd59  lea     rcx, W32pServiceTableFilter
0x14003bd60  mov     edx, cs:W32pServiceLimitFilter
0x14003bd66  mov     rax, 14Eh
0x14003bd6d  lea     rcx, [rcx+rdx*4]
0x14003bd71  movsx   eax, byte ptr [rcx+rax]
0x14003bd75  or      eax, eax
0x14003bd77  jle     short loc_14003BD7E
0x14003bd79  mov     eax, 0C000001Ch
0x14003bd7e  add     rsp, 48h
0x14003bd82  retn
0x14003bd83  mov     rax, cs:__imp_NtDxgkCreateDoorbell
0x14003bd8a  mov     rcx, [rsp+48h+var_28]
0x14003bd8f  mov     rdx, [rsp+48h+var_20]
0x14003bd94  mov     r8, [rsp+48h+var_18]
0x14003bd99  mov     r9, [rsp+48h+var_10]
0x14003bd9e  add     rsp, 48h
0x14003bda2  jmp     rax
```
