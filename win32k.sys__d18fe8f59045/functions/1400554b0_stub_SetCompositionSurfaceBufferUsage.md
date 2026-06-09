# _stub_SetCompositionSurfaceBufferUsage

- ea: `0x1400554b0`
- end: `0x140055557`
- name: `_stub_SetCompositionSurfaceBufferUsage`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400554b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400554f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400554f9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtSetCompositionSurfaceBufferUsage` at `0x140055533`

## string_xrefs

- `0x1400554df`: `NtSetCompositionSurfaceBufferUsage`

## pseudocode

```c
__int64 __fastcall stub_SetCompositionSurfaceBufferUsage(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtSetCompositionSurfaceBufferUsage(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtSetCompositionSurfaceBufferUsage(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[115] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400554b0  sub     rsp, 48h
0x1400554b4  mov     [rsp+48h+var_28], rcx
0x1400554b9  mov     [rsp+48h+var_20], rdx
0x1400554be  mov     [rsp+48h+var_18], r8
0x1400554c3  mov     [rsp+48h+var_10], r9
0x1400554c8  mov     rcx, 39Fh
0x1400554cf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400554d6  nop     dword ptr [rax+rax+00h]
0x1400554db  test    al, al
0x1400554dd  jz      short loc_140055533
0x1400554df  lea     rcx, aNtsetcompositi; "NtSetCompositionSurfaceBufferUsage"
0x1400554e6  mov     rdx, 39Fh
0x1400554ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400554f4  nop     dword ptr [rax+rax+00h]
0x1400554f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055500  nop     dword ptr [rax+rax+00h]
0x140055505  test    al, al
0x140055507  jz      short loc_140055533
0x140055509  lea     rcx, W32pServiceTableFilter
0x140055510  mov     edx, cs:W32pServiceLimitFilter
0x140055516  mov     rax, 39Fh
0x14005551d  lea     rcx, [rcx+rdx*4]
0x140055521  movsx   eax, byte ptr [rcx+rax]
0x140055525  or      eax, eax
0x140055527  jle     short loc_14005552E
0x140055529  mov     eax, 0C000001Ch
0x14005552e  add     rsp, 48h
0x140055532  retn
0x140055533  mov     rax, cs:__imp_NtSetCompositionSurfaceBufferUsage
0x14005553a  mov     rcx, [rsp+48h+var_28]
0x14005553f  mov     rdx, [rsp+48h+var_20]
0x140055544  mov     r8, [rsp+48h+var_18]
0x140055549  mov     r9, [rsp+48h+var_10]
0x14005554e  add     rsp, 48h
0x140055552  jmp     rax
```
