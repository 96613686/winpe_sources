# _stub_GdiDdDDIUpdateOverlay

- ea: `0x140048720`
- end: `0x1400487c7`
- name: `_stub_GdiDdDDIUpdateOverlay`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140048720`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048769`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140048769`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIUpdateOverlay` at `0x1400487a3`

## string_xrefs

- `0x14004874f`: `NtGdiDdDDIUpdateOverlay`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[78] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140048720  sub     rsp, 48h
0x140048724  mov     [rsp+48h+var_28], rcx
0x140048729  mov     [rsp+48h+var_20], rdx
0x14004872e  mov     [rsp+48h+var_18], r8
0x140048733  mov     [rsp+48h+var_10], r9
0x140048738  mov     rcx, 274h
0x14004873f  call    cs:__imp_IsWin32KSyscallFiltered
0x140048746  nop     dword ptr [rax+rax+00h]
0x14004874b  test    al, al
0x14004874d  jz      short loc_1400487A3
0x14004874f  lea     rcx, aNtgdiddddiupda_1; "NtGdiDdDDIUpdateOverlay"
0x140048756  mov     rdx, 274h
0x14004875d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140048764  nop     dword ptr [rax+rax+00h]
0x140048769  call    cs:__imp_PsIsWin32KFilterEnabled
0x140048770  nop     dword ptr [rax+rax+00h]
0x140048775  test    al, al
0x140048777  jz      short loc_1400487A3
0x140048779  lea     rcx, W32pServiceTableFilter
0x140048780  mov     edx, cs:W32pServiceLimitFilter
0x140048786  mov     rax, 274h
0x14004878d  lea     rcx, [rcx+rdx*4]
0x140048791  movsx   eax, byte ptr [rcx+rax]
0x140048795  or      eax, eax
0x140048797  jle     short loc_14004879E
0x140048799  mov     eax, 0C000001Ch
0x14004879e  add     rsp, 48h
0x1400487a2  retn
0x1400487a3  mov     rax, cs:__imp_NtGdiDdDDIUpdateOverlay
0x1400487aa  mov     rcx, [rsp+48h+var_28]
0x1400487af  mov     rdx, [rsp+48h+var_20]
0x1400487b4  mov     r8, [rsp+48h+var_18]
0x1400487b9  mov     r9, [rsp+48h+var_10]
0x1400487be  add     rsp, 48h
0x1400487c2  jmp     rax
```
