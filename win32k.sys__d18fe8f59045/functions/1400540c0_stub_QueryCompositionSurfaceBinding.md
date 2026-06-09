# _stub_QueryCompositionSurfaceBinding

- ea: `0x1400540c0`
- end: `0x140054167`
- name: `_stub_QueryCompositionSurfaceBinding`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400540c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140054109`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140054109`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceBinding` at `0x140054143`

## string_xrefs

- `0x1400540ef`: `NtQueryCompositionSurfaceBinding`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceBinding(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceBinding(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceBinding(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400540c0  sub     rsp, 48h
0x1400540c4  mov     [rsp+48h+var_28], rcx
0x1400540c9  mov     [rsp+48h+var_20], rdx
0x1400540ce  mov     [rsp+48h+var_18], r8
0x1400540d3  mov     [rsp+48h+var_10], r9
0x1400540d8  mov     rcx, 382h
0x1400540df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400540e6  nop     dword ptr [rax+rax+00h]
0x1400540eb  test    al, al
0x1400540ed  jz      short loc_140054143
0x1400540ef  lea     rcx, aNtquerycomposi_4; "NtQueryCompositionSurfaceBinding"
0x1400540f6  mov     rdx, 382h
0x1400540fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140054104  nop     dword ptr [rax+rax+00h]
0x140054109  call    cs:__imp_PsIsWin32KFilterEnabled
0x140054110  nop     dword ptr [rax+rax+00h]
0x140054115  test    al, al
0x140054117  jz      short loc_140054143
0x140054119  lea     rcx, W32pServiceTableFilter
0x140054120  mov     edx, cs:W32pServiceLimitFilter
0x140054126  mov     rax, 382h
0x14005412d  lea     rcx, [rcx+rdx*4]
0x140054131  movsx   eax, byte ptr [rcx+rax]
0x140054135  or      eax, eax
0x140054137  jle     short loc_14005413E
0x140054139  mov     eax, 0C000001Ch
0x14005413e  add     rsp, 48h
0x140054142  retn
0x140054143  mov     rax, cs:__imp_NtQueryCompositionSurfaceBinding
0x14005414a  mov     rcx, [rsp+48h+var_28]
0x14005414f  mov     rdx, [rsp+48h+var_20]
0x140054154  mov     r8, [rsp+48h+var_18]
0x140054159  mov     r9, [rsp+48h+var_10]
0x14005415e  add     rsp, 48h
0x140054162  jmp     rax
```
