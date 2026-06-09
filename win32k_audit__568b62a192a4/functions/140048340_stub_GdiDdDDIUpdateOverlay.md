# _stub_GdiDdDDIUpdateOverlay

- ea: `0x140048340`
- end: `0x1400483e7`
- name: `_stub_GdiDdDDIUpdateOverlay`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140048340`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048389`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048389`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIUpdateOverlay` at `0x1400483c3`

## string_xrefs

- `0x14004836f`: `NtGdiDdDDIUpdateOverlay`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIUpdateOverlay(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIUpdateOverlay(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIUpdateOverlay(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[78] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140048340  sub     rsp, 48h
0x140048344  mov     [rsp+48h+var_28], rcx
0x140048349  mov     [rsp+48h+var_20], rdx
0x14004834e  mov     [rsp+48h+var_18], r8
0x140048353  mov     [rsp+48h+var_10], r9
0x140048358  mov     rcx, 271h
0x14004835f  call    cs:__imp_IsWin32KSyscallFiltered
0x140048366  nop     dword ptr [rax+rax+00h]
0x14004836b  test    al, al
0x14004836d  jz      short loc_1400483C3
0x14004836f  lea     rcx, aNtgdiddddiupda_1; "NtGdiDdDDIUpdateOverlay"
0x140048376  mov     rdx, 271h
0x14004837d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140048384  nop     dword ptr [rax+rax+00h]
0x140048389  call    cs:__imp_PsIsWin32KFilterEnabled
0x140048390  nop     dword ptr [rax+rax+00h]
0x140048395  test    al, al
0x140048397  jz      short loc_1400483C3
0x140048399  lea     rcx, W32pServiceTableFilter
0x1400483a0  mov     edx, cs:W32pServiceLimitFilter
0x1400483a6  mov     rax, 271h
0x1400483ad  lea     rcx, [rcx+rdx*4]
0x1400483b1  movsx   eax, byte ptr [rcx+rax]
0x1400483b5  or      eax, eax
0x1400483b7  jle     short loc_1400483BE
0x1400483b9  mov     eax, 0C000001Ch
0x1400483be  add     rsp, 48h
0x1400483c2  retn
0x1400483c3  mov     rax, cs:__imp_NtGdiDdDDIUpdateOverlay
0x1400483ca  mov     rcx, [rsp+48h+var_28]
0x1400483cf  mov     rdx, [rsp+48h+var_20]
0x1400483d4  mov     r8, [rsp+48h+var_18]
0x1400483d9  mov     r9, [rsp+48h+var_10]
0x1400483de  add     rsp, 48h
0x1400483e2  jmp     rax
```
