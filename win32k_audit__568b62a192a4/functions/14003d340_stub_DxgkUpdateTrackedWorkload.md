# _stub_DxgkUpdateTrackedWorkload

- ea: `0x14003d340`
- end: `0x14003d3e7`
- name: `_stub_DxgkUpdateTrackedWorkload`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003d340`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003d389`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003d389`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkUpdateTrackedWorkload` at `0x14003d3c3`

## string_xrefs

- `0x14003d36f`: `NtDxgkUpdateTrackedWorkload`

## pseudocode

```c
__int64 __fastcall stub_DxgkUpdateTrackedWorkload(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkUpdateTrackedWorkload(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkUpdateTrackedWorkload(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[46] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003d340  sub     rsp, 48h
0x14003d344  mov     [rsp+48h+var_28], rcx
0x14003d349  mov     [rsp+48h+var_20], rdx
0x14003d34e  mov     [rsp+48h+var_18], r8
0x14003d353  mov     [rsp+48h+var_10], r9
0x14003d358  mov     rcx, 171h
0x14003d35f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003d366  nop     dword ptr [rax+rax+00h]
0x14003d36b  test    al, al
0x14003d36d  jz      short loc_14003D3C3
0x14003d36f  lea     rcx, aNtdxgkupdatetr; "NtDxgkUpdateTrackedWorkload"
0x14003d376  mov     rdx, 171h
0x14003d37d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003d384  nop     dword ptr [rax+rax+00h]
0x14003d389  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003d390  nop     dword ptr [rax+rax+00h]
0x14003d395  test    al, al
0x14003d397  jz      short loc_14003D3C3
0x14003d399  lea     rcx, W32pServiceTableFilter
0x14003d3a0  mov     edx, cs:W32pServiceLimitFilter
0x14003d3a6  mov     rax, 171h
0x14003d3ad  lea     rcx, [rcx+rdx*4]
0x14003d3b1  movsx   eax, byte ptr [rcx+rax]
0x14003d3b5  or      eax, eax
0x14003d3b7  jle     short loc_14003D3BE
0x14003d3b9  mov     eax, 0C000001Ch
0x14003d3be  add     rsp, 48h
0x14003d3c2  retn
0x14003d3c3  mov     rax, cs:__imp_NtDxgkUpdateTrackedWorkload
0x14003d3ca  mov     rcx, [rsp+48h+var_28]
0x14003d3cf  mov     rdx, [rsp+48h+var_20]
0x14003d3d4  mov     r8, [rsp+48h+var_18]
0x14003d3d9  mov     r9, [rsp+48h+var_10]
0x14003d3de  add     rsp, 48h
0x14003d3e2  jmp     rax
```
