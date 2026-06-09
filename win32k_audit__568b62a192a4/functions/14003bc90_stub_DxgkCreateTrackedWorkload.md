# _stub_DxgkCreateTrackedWorkload

- ea: `0x14003bc90`
- end: `0x14003bd37`
- name: `_stub_DxgkCreateTrackedWorkload`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003bc90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bcd9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bcd9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCreateTrackedWorkload` at `0x14003bd13`

## string_xrefs

- `0x14003bcbf`: `NtDxgkCreateTrackedWorkload`

## pseudocode

```c
__int64 __fastcall stub_DxgkCreateTrackedWorkload(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkCreateTrackedWorkload(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkCreateTrackedWorkload(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[42] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003bc90  sub     rsp, 48h
0x14003bc94  mov     [rsp+48h+var_28], rcx
0x14003bc99  mov     [rsp+48h+var_20], rdx
0x14003bc9e  mov     [rsp+48h+var_18], r8
0x14003bca3  mov     [rsp+48h+var_10], r9
0x14003bca8  mov     rcx, 150h
0x14003bcaf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003bcb6  nop     dword ptr [rax+rax+00h]
0x14003bcbb  test    al, al
0x14003bcbd  jz      short loc_14003BD13
0x14003bcbf  lea     rcx, aNtdxgkcreatetr; "NtDxgkCreateTrackedWorkload"
0x14003bcc6  mov     rdx, 150h
0x14003bccd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003bcd4  nop     dword ptr [rax+rax+00h]
0x14003bcd9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003bce0  nop     dword ptr [rax+rax+00h]
0x14003bce5  test    al, al
0x14003bce7  jz      short loc_14003BD13
0x14003bce9  lea     rcx, W32pServiceTableFilter
0x14003bcf0  mov     edx, cs:W32pServiceLimitFilter
0x14003bcf6  mov     rax, 150h
0x14003bcfd  lea     rcx, [rcx+rdx*4]
0x14003bd01  movsx   eax, byte ptr [rcx+rax]
0x14003bd05  or      eax, eax
0x14003bd07  jle     short loc_14003BD0E
0x14003bd09  mov     eax, 0C000001Ch
0x14003bd0e  add     rsp, 48h
0x14003bd12  retn
0x14003bd13  mov     rax, cs:__imp_NtDxgkCreateTrackedWorkload
0x14003bd1a  mov     rcx, [rsp+48h+var_28]
0x14003bd1f  mov     rdx, [rsp+48h+var_20]
0x14003bd24  mov     r8, [rsp+48h+var_18]
0x14003bd29  mov     r9, [rsp+48h+var_10]
0x14003bd2e  add     rsp, 48h
0x14003bd32  jmp     rax
```
