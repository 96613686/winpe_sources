# _stub_GdiDdDDIUpdateAllocationProperty

- ea: `0x1400485c0`
- end: `0x140048667`
- name: `_stub_GdiDdDDIUpdateAllocationProperty`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400485c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048609`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048609`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIUpdateAllocationProperty` at `0x140048643`

## string_xrefs

- `0x1400485ef`: `NtGdiDdDDIUpdateAllocationProperty`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIUpdateAllocationProperty(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIUpdateAllocationProperty(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIUpdateAllocationProperty(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[78] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400485c0  sub     rsp, 48h
0x1400485c4  mov     [rsp+48h+var_28], rcx
0x1400485c9  mov     [rsp+48h+var_20], rdx
0x1400485ce  mov     [rsp+48h+var_18], r8
0x1400485d3  mov     [rsp+48h+var_10], r9
0x1400485d8  mov     rcx, 272h
0x1400485df  call    cs:__imp_IsWin32KSyscallFiltered
0x1400485e6  nop     dword ptr [rax+rax+00h]
0x1400485eb  test    al, al
0x1400485ed  jz      short loc_140048643
0x1400485ef  lea     rcx, aNtgdiddddiupda; "NtGdiDdDDIUpdateAllocationProperty"
0x1400485f6  mov     rdx, 272h
0x1400485fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140048604  nop     dword ptr [rax+rax+00h]
0x140048609  call    cs:__imp_PsIsWin32KFilterEnabled
0x140048610  nop     dword ptr [rax+rax+00h]
0x140048615  test    al, al
0x140048617  jz      short loc_140048643
0x140048619  lea     rcx, W32pServiceTableFilter
0x140048620  mov     edx, cs:W32pServiceLimitFilter
0x140048626  mov     rax, 272h
0x14004862d  lea     rcx, [rcx+rdx*4]
0x140048631  movsx   eax, byte ptr [rcx+rax]
0x140048635  or      eax, eax
0x140048637  jle     short loc_14004863E
0x140048639  mov     eax, 0C000001Ch
0x14004863e  add     rsp, 48h
0x140048642  retn
0x140048643  mov     rax, cs:__imp_NtGdiDdDDIUpdateAllocationProperty
0x14004864a  mov     rcx, [rsp+48h+var_28]
0x14004864f  mov     rdx, [rsp+48h+var_20]
0x140048654  mov     r8, [rsp+48h+var_18]
0x140048659  mov     r9, [rsp+48h+var_10]
0x14004865e  add     rsp, 48h
0x140048662  jmp     rax
```
