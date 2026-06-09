# _stub_DxgkCreateTrackedWorkload

- ea: `0x14003bf10`
- end: `0x14003bfb7`
- name: `_stub_DxgkCreateTrackedWorkload`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003bf10`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bf59`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bf59`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCreateTrackedWorkload` at `0x14003bf93`

## string_xrefs

- `0x14003bf3f`: `NtDxgkCreateTrackedWorkload`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[42] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003bf10  sub     rsp, 48h
0x14003bf14  mov     [rsp+48h+var_28], rcx
0x14003bf19  mov     [rsp+48h+var_20], rdx
0x14003bf1e  mov     [rsp+48h+var_18], r8
0x14003bf23  mov     [rsp+48h+var_10], r9
0x14003bf28  mov     rcx, 151h
0x14003bf2f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003bf36  nop     dword ptr [rax+rax+00h]
0x14003bf3b  test    al, al
0x14003bf3d  jz      short loc_14003BF93
0x14003bf3f  lea     rcx, aNtdxgkcreatetr; "NtDxgkCreateTrackedWorkload"
0x14003bf46  mov     rdx, 151h
0x14003bf4d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003bf54  nop     dword ptr [rax+rax+00h]
0x14003bf59  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003bf60  nop     dword ptr [rax+rax+00h]
0x14003bf65  test    al, al
0x14003bf67  jz      short loc_14003BF93
0x14003bf69  lea     rcx, W32pServiceTableFilter
0x14003bf70  mov     edx, cs:W32pServiceLimitFilter
0x14003bf76  mov     rax, 151h
0x14003bf7d  lea     rcx, [rcx+rdx*4]
0x14003bf81  movsx   eax, byte ptr [rcx+rax]
0x14003bf85  or      eax, eax
0x14003bf87  jle     short loc_14003BF8E
0x14003bf89  mov     eax, 0C000001Ch
0x14003bf8e  add     rsp, 48h
0x14003bf92  retn
0x14003bf93  mov     rax, cs:__imp_NtDxgkCreateTrackedWorkload
0x14003bf9a  mov     rcx, [rsp+48h+var_28]
0x14003bf9f  mov     rdx, [rsp+48h+var_20]
0x14003bfa4  mov     r8, [rsp+48h+var_18]
0x14003bfa9  mov     r9, [rsp+48h+var_10]
0x14003bfae  add     rsp, 48h
0x14003bfb2  jmp     rax
```
