# _stub_OpenCompositionSurfaceSectionInfo

- ea: `0x1400538c0`
- end: `0x140053967`
- name: `_stub_OpenCompositionSurfaceSectionInfo`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400538c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053909`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053909`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtOpenCompositionSurfaceSectionInfo` at `0x140053943`

## string_xrefs

- `0x1400538ef`: `NtOpenCompositionSurfaceSectionInfo`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[111] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400538c0  sub     rsp, 48h
0x1400538c4  mov     [rsp+48h+var_28], rcx
0x1400538c9  mov     [rsp+48h+var_20], rdx
0x1400538ce  mov     [rsp+48h+var_18], r8
0x1400538d3  mov     [rsp+48h+var_10], r9
0x1400538d8  mov     rcx, 379h
0x1400538df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400538e6  nop     dword ptr [rax+rax+00h]
0x1400538eb  test    al, al
0x1400538ed  jz      short loc_140053943
0x1400538ef  lea     rcx, aNtopencomposit_1; "NtOpenCompositionSurfaceSectionInfo"
0x1400538f6  mov     rdx, 379h
0x1400538fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053904  nop     dword ptr [rax+rax+00h]
0x140053909  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053910  nop     dword ptr [rax+rax+00h]
0x140053915  test    al, al
0x140053917  jz      short loc_140053943
0x140053919  lea     rcx, W32pServiceTableFilter
0x140053920  mov     edx, cs:W32pServiceLimitFilter
0x140053926  mov     rax, 379h
0x14005392d  lea     rcx, [rcx+rdx*4]
0x140053931  movsx   eax, byte ptr [rcx+rax]
0x140053935  or      eax, eax
0x140053937  jle     short loc_14005393E
0x140053939  mov     eax, 0C000001Ch
0x14005393e  add     rsp, 48h
0x140053942  retn
0x140053943  mov     rax, cs:__imp_NtOpenCompositionSurfaceSectionInfo
0x14005394a  mov     rcx, [rsp+48h+var_28]
0x14005394f  mov     rdx, [rsp+48h+var_20]
0x140053954  mov     r8, [rsp+48h+var_18]
0x140053959  mov     r9, [rsp+48h+var_10]
0x14005395e  add     rsp, 48h
0x140053962  jmp     rax
```
