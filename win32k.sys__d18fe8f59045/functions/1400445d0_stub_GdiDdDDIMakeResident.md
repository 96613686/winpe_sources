# _stub_GdiDdDDIMakeResident

- ea: `0x1400445d0`
- end: `0x140044677`
- name: `_stub_GdiDdDDIMakeResident`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400445d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044619`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044619`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIMakeResident` at `0x140044653`

## string_xrefs

- `0x1400445ff`: `NtGdiDdDDIMakeResident`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIMakeResident(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIMakeResident(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIMakeResident(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[66] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400445d0  sub     rsp, 48h
0x1400445d4  mov     [rsp+48h+var_28], rcx
0x1400445d9  mov     [rsp+48h+var_20], rdx
0x1400445de  mov     [rsp+48h+var_18], r8
0x1400445e3  mov     [rsp+48h+var_10], r9
0x1400445e8  mov     rcx, 215h
0x1400445ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400445f6  nop     dword ptr [rax+rax+00h]
0x1400445fb  test    al, al
0x1400445fd  jz      short loc_140044653
0x1400445ff  lea     rcx, aNtgdiddddimake; "NtGdiDdDDIMakeResident"
0x140044606  mov     rdx, 215h
0x14004460d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044614  nop     dword ptr [rax+rax+00h]
0x140044619  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044620  nop     dword ptr [rax+rax+00h]
0x140044625  test    al, al
0x140044627  jz      short loc_140044653
0x140044629  lea     rcx, W32pServiceTableFilter
0x140044630  mov     edx, cs:W32pServiceLimitFilter
0x140044636  mov     rax, 215h
0x14004463d  lea     rcx, [rcx+rdx*4]
0x140044641  movsx   eax, byte ptr [rcx+rax]
0x140044645  or      eax, eax
0x140044647  jle     short loc_14004464E
0x140044649  mov     eax, 0C000001Ch
0x14004464e  add     rsp, 48h
0x140044652  retn
0x140044653  mov     rax, cs:__imp_NtGdiDdDDIMakeResident
0x14004465a  mov     rcx, [rsp+48h+var_28]
0x14004465f  mov     rdx, [rsp+48h+var_20]
0x140044664  mov     r8, [rsp+48h+var_18]
0x140044669  mov     r9, [rsp+48h+var_10]
0x14004466e  add     rsp, 48h
0x140044672  jmp     rax
```
