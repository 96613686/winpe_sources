# _stub_OpenCompositionSurfaceSectionInfo

- ea: `0x140053ca0`
- end: `0x140053d47`
- name: `_stub_OpenCompositionSurfaceSectionInfo`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053ca0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053ce9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053ce9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtOpenCompositionSurfaceSectionInfo` at `0x140053d23`

## string_xrefs

- `0x140053ccf`: `NtOpenCompositionSurfaceSectionInfo`

## pseudocode

```c
__int64 __fastcall stub_OpenCompositionSurfaceSectionInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtOpenCompositionSurfaceSectionInfo(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtOpenCompositionSurfaceSectionInfo(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[111] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053ca0  sub     rsp, 48h
0x140053ca4  mov     [rsp+48h+var_28], rcx
0x140053ca9  mov     [rsp+48h+var_20], rdx
0x140053cae  mov     [rsp+48h+var_18], r8
0x140053cb3  mov     [rsp+48h+var_10], r9
0x140053cb8  mov     rcx, 37Ch
0x140053cbf  call    cs:__imp_IsWin32KSyscallFiltered
0x140053cc6  nop     dword ptr [rax+rax+00h]
0x140053ccb  test    al, al
0x140053ccd  jz      short loc_140053D23
0x140053ccf  lea     rcx, aNtopencomposit_1; "NtOpenCompositionSurfaceSectionInfo"
0x140053cd6  mov     rdx, 37Ch
0x140053cdd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053ce4  nop     dword ptr [rax+rax+00h]
0x140053ce9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053cf0  nop     dword ptr [rax+rax+00h]
0x140053cf5  test    al, al
0x140053cf7  jz      short loc_140053D23
0x140053cf9  lea     rcx, W32pServiceTableFilter
0x140053d00  mov     edx, cs:W32pServiceLimitFilter
0x140053d06  mov     rax, 37Ch
0x140053d0d  lea     rcx, [rcx+rdx*4]
0x140053d11  movsx   eax, byte ptr [rcx+rax]
0x140053d15  or      eax, eax
0x140053d17  jle     short loc_140053D1E
0x140053d19  mov     eax, 0C000001Ch
0x140053d1e  add     rsp, 48h
0x140053d22  retn
0x140053d23  mov     rax, cs:__imp_NtOpenCompositionSurfaceSectionInfo
0x140053d2a  mov     rcx, [rsp+48h+var_28]
0x140053d2f  mov     rdx, [rsp+48h+var_20]
0x140053d34  mov     r8, [rsp+48h+var_18]
0x140053d39  mov     r9, [rsp+48h+var_10]
0x140053d3e  add     rsp, 48h
0x140053d42  jmp     rax
```
