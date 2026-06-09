# _stub_OpenCompositionSurfaceRealizationInfo

- ea: `0x140053bf0`
- end: `0x140053c97`
- name: `_stub_OpenCompositionSurfaceRealizationInfo`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053bf0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053c39`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053c39`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtOpenCompositionSurfaceRealizationInfo` at `0x140053c73`

## string_xrefs

- `0x140053c1f`: `NtOpenCompositionSurfaceRealizationInfo`

## pseudocode

```c
__int64 __fastcall stub_OpenCompositionSurfaceRealizationInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtOpenCompositionSurfaceRealizationInfo(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtOpenCompositionSurfaceRealizationInfo(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[111] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053bf0  sub     rsp, 48h
0x140053bf4  mov     [rsp+48h+var_28], rcx
0x140053bf9  mov     [rsp+48h+var_20], rdx
0x140053bfe  mov     [rsp+48h+var_18], r8
0x140053c03  mov     [rsp+48h+var_10], r9
0x140053c08  mov     rcx, 37Bh
0x140053c0f  call    cs:__imp_IsWin32KSyscallFiltered
0x140053c16  nop     dword ptr [rax+rax+00h]
0x140053c1b  test    al, al
0x140053c1d  jz      short loc_140053C73
0x140053c1f  lea     rcx, aNtopencomposit_0; "NtOpenCompositionSurfaceRealizationInfo"
0x140053c26  mov     rdx, 37Bh
0x140053c2d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053c34  nop     dword ptr [rax+rax+00h]
0x140053c39  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053c40  nop     dword ptr [rax+rax+00h]
0x140053c45  test    al, al
0x140053c47  jz      short loc_140053C73
0x140053c49  lea     rcx, W32pServiceTableFilter
0x140053c50  mov     edx, cs:W32pServiceLimitFilter
0x140053c56  mov     rax, 37Bh
0x140053c5d  lea     rcx, [rcx+rdx*4]
0x140053c61  movsx   eax, byte ptr [rcx+rax]
0x140053c65  or      eax, eax
0x140053c67  jle     short loc_140053C6E
0x140053c69  mov     eax, 0C000001Ch
0x140053c6e  add     rsp, 48h
0x140053c72  retn
0x140053c73  mov     rax, cs:__imp_NtOpenCompositionSurfaceRealizationInfo
0x140053c7a  mov     rcx, [rsp+48h+var_28]
0x140053c7f  mov     rdx, [rsp+48h+var_20]
0x140053c84  mov     r8, [rsp+48h+var_18]
0x140053c89  mov     r9, [rsp+48h+var_10]
0x140053c8e  add     rsp, 48h
0x140053c92  jmp     rax
```
