# _stub_SetCompositionSurfaceBufferUsage

- ea: `0x1400550d0`
- end: `0x140055177`
- name: `_stub_SetCompositionSurfaceBufferUsage`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400550d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055119`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055119`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtSetCompositionSurfaceBufferUsage` at `0x140055153`

## string_xrefs

- `0x1400550ff`: `NtSetCompositionSurfaceBufferUsage`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[115] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400550d0  sub     rsp, 48h
0x1400550d4  mov     [rsp+48h+var_28], rcx
0x1400550d9  mov     [rsp+48h+var_20], rdx
0x1400550de  mov     [rsp+48h+var_18], r8
0x1400550e3  mov     [rsp+48h+var_10], r9
0x1400550e8  mov     rcx, 39Ch
0x1400550ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400550f6  nop     dword ptr [rax+rax+00h]
0x1400550fb  test    al, al
0x1400550fd  jz      short loc_140055153
0x1400550ff  lea     rcx, aNtsetcompositi; "NtSetCompositionSurfaceBufferUsage"
0x140055106  mov     rdx, 39Ch
0x14005510d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055114  nop     dword ptr [rax+rax+00h]
0x140055119  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055120  nop     dword ptr [rax+rax+00h]
0x140055125  test    al, al
0x140055127  jz      short loc_140055153
0x140055129  lea     rcx, W32pServiceTableFilter
0x140055130  mov     edx, cs:W32pServiceLimitFilter
0x140055136  mov     rax, 39Ch
0x14005513d  lea     rcx, [rcx+rdx*4]
0x140055141  movsx   eax, byte ptr [rcx+rax]
0x140055145  or      eax, eax
0x140055147  jle     short loc_14005514E
0x140055149  mov     eax, 0C000001Ch
0x14005514e  add     rsp, 48h
0x140055152  retn
0x140055153  mov     rax, cs:__imp_NtSetCompositionSurfaceBufferUsage
0x14005515a  mov     rcx, [rsp+48h+var_28]
0x14005515f  mov     rdx, [rsp+48h+var_20]
0x140055164  mov     r8, [rsp+48h+var_18]
0x140055169  mov     r9, [rsp+48h+var_10]
0x14005516e  add     rsp, 48h
0x140055172  jmp     rax
```
