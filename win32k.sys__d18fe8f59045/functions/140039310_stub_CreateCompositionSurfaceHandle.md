# _stub_CreateCompositionSurfaceHandle

- ea: `0x140039310`
- end: `0x1400393b7`
- name: `_stub_CreateCompositionSurfaceHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039310`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039359`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039359`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtCreateCompositionSurfaceHandle` at `0x140039393`

## string_xrefs

- `0x14003933f`: `NtCreateCompositionSurfaceHandle`

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
0x140039310  sub     rsp, 48h
0x140039314  mov     [rsp+48h+var_28], rcx
0x140039319  mov     [rsp+48h+var_20], rdx
0x14003931e  mov     [rsp+48h+var_18], r8
0x140039323  mov     [rsp+48h+var_10], r9
0x140039328  mov     rcx, 111h
0x14003932f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039336  nop     dword ptr [rax+rax+00h]
0x14003933b  test    al, al
0x14003933d  jz      short loc_140039393
0x14003933f  lea     rcx, aNtcreatecompos_0; "NtCreateCompositionSurfaceHandle"
0x140039346  mov     rdx, 111h
0x14003934d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039354  nop     dword ptr [rax+rax+00h]
0x140039359  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039360  nop     dword ptr [rax+rax+00h]
0x140039365  test    al, al
0x140039367  jz      short loc_140039393
0x140039369  lea     rcx, W32pServiceTableFilter
0x140039370  mov     edx, cs:W32pServiceLimitFilter
0x140039376  mov     rax, 111h
0x14003937d  lea     rcx, [rcx+rdx*4]
0x140039381  movsx   eax, byte ptr [rcx+rax]
0x140039385  or      eax, eax
0x140039387  jle     short loc_14003938E
0x140039389  mov     eax, 0C000001Ch
0x14003938e  add     rsp, 48h
0x140039392  retn
0x140039393  mov     rax, cs:__imp_NtCreateCompositionSurfaceHandle
0x14003939a  mov     rcx, [rsp+48h+var_28]
0x14003939f  mov     rdx, [rsp+48h+var_20]
0x1400393a4  mov     r8, [rsp+48h+var_18]
0x1400393a9  mov     r9, [rsp+48h+var_10]
0x1400393ae  add     rsp, 48h
0x1400393b2  jmp     rax
```
