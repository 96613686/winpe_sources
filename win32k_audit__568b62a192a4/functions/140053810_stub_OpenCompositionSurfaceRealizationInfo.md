# _stub_OpenCompositionSurfaceRealizationInfo

- ea: `0x140053810`
- end: `0x1400538b7`
- name: `_stub_OpenCompositionSurfaceRealizationInfo`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053810`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053859`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053859`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtOpenCompositionSurfaceRealizationInfo` at `0x140053893`

## string_xrefs

- `0x14005383f`: `NtOpenCompositionSurfaceRealizationInfo`

## pseudocode

```c
__int64 __fastcall stub_OpenCompositionSurfaceRealizationInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtOpenCompositionSurfaceRealizationInfo(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtOpenCompositionSurfaceRealizationInfo(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[111] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053810  sub     rsp, 48h
0x140053814  mov     [rsp+48h+var_28], rcx
0x140053819  mov     [rsp+48h+var_20], rdx
0x14005381e  mov     [rsp+48h+var_18], r8
0x140053823  mov     [rsp+48h+var_10], r9
0x140053828  mov     rcx, 378h
0x14005382f  call    cs:__imp_IsWin32KSyscallFiltered
0x140053836  nop     dword ptr [rax+rax+00h]
0x14005383b  test    al, al
0x14005383d  jz      short loc_140053893
0x14005383f  lea     rcx, aNtopencomposit_0; "NtOpenCompositionSurfaceRealizationInfo"
0x140053846  mov     rdx, 378h
0x14005384d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053854  nop     dword ptr [rax+rax+00h]
0x140053859  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053860  nop     dword ptr [rax+rax+00h]
0x140053865  test    al, al
0x140053867  jz      short loc_140053893
0x140053869  lea     rcx, W32pServiceTableFilter
0x140053870  mov     edx, cs:W32pServiceLimitFilter
0x140053876  mov     rax, 378h
0x14005387d  lea     rcx, [rcx+rdx*4]
0x140053881  movsx   eax, byte ptr [rcx+rax]
0x140053885  or      eax, eax
0x140053887  jle     short loc_14005388E
0x140053889  mov     eax, 0C000001Ch
0x14005388e  add     rsp, 48h
0x140053892  retn
0x140053893  mov     rax, cs:__imp_NtOpenCompositionSurfaceRealizationInfo
0x14005389a  mov     rcx, [rsp+48h+var_28]
0x14005389f  mov     rdx, [rsp+48h+var_20]
0x1400538a4  mov     r8, [rsp+48h+var_18]
0x1400538a9  mov     r9, [rsp+48h+var_10]
0x1400538ae  add     rsp, 48h
0x1400538b2  jmp     rax
```
