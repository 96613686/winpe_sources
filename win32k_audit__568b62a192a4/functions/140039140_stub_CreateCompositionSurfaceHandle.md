# _stub_CreateCompositionSurfaceHandle

- ea: `0x140039140`
- end: `0x1400391e7`
- name: `_stub_CreateCompositionSurfaceHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039140`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039189`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039189`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtCreateCompositionSurfaceHandle` at `0x1400391c3`

## string_xrefs

- `0x14003916f`: `NtCreateCompositionSurfaceHandle`

## pseudocode

```c
__int64 __fastcall stub_CreateCompositionSurfaceHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtCreateCompositionSurfaceHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtCreateCompositionSurfaceHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039140  sub     rsp, 48h
0x140039144  mov     [rsp+48h+var_28], rcx
0x140039149  mov     [rsp+48h+var_20], rdx
0x14003914e  mov     [rsp+48h+var_18], r8
0x140039153  mov     [rsp+48h+var_10], r9
0x140039158  mov     rcx, 111h
0x14003915f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039166  nop     dword ptr [rax+rax+00h]
0x14003916b  test    al, al
0x14003916d  jz      short loc_1400391C3
0x14003916f  lea     rcx, aNtcreatecompos_0; "NtCreateCompositionSurfaceHandle"
0x140039176  mov     rdx, 111h
0x14003917d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039184  nop     dword ptr [rax+rax+00h]
0x140039189  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039190  nop     dword ptr [rax+rax+00h]
0x140039195  test    al, al
0x140039197  jz      short loc_1400391C3
0x140039199  lea     rcx, W32pServiceTableFilter
0x1400391a0  mov     edx, cs:W32pServiceLimitFilter
0x1400391a6  mov     rax, 111h
0x1400391ad  lea     rcx, [rcx+rdx*4]
0x1400391b1  movsx   eax, byte ptr [rcx+rax]
0x1400391b5  or      eax, eax
0x1400391b7  jle     short loc_1400391BE
0x1400391b9  mov     eax, 0C000001Ch
0x1400391be  add     rsp, 48h
0x1400391c2  retn
0x1400391c3  mov     rax, cs:__imp_NtCreateCompositionSurfaceHandle
0x1400391ca  mov     rcx, [rsp+48h+var_28]
0x1400391cf  mov     rdx, [rsp+48h+var_20]
0x1400391d4  mov     r8, [rsp+48h+var_18]
0x1400391d9  mov     r9, [rsp+48h+var_10]
0x1400391de  add     rsp, 48h
0x1400391e2  jmp     rax
```
