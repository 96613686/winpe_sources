# _stub_DCompositionReleaseAllResources

- ea: `0x14003ac80`
- end: `0x14003ad27`
- name: `_stub_DCompositionReleaseAllResources`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ac80`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003acc9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003acc9`

## string_xrefs

- `0x14003acaf`: `NtDCompositionReleaseAllResources`

## pseudocode

```c
__int64 stub_DCompositionReleaseAllResources()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionReleaseAllResources();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionReleaseAllResources();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ac80  sub     rsp, 48h
0x14003ac84  mov     [rsp+48h+var_28], rcx
0x14003ac89  mov     [rsp+48h+var_20], rdx
0x14003ac8e  mov     [rsp+48h+var_18], r8
0x14003ac93  mov     [rsp+48h+var_10], r9
0x14003ac98  mov     rcx, 136h
0x14003ac9f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003aca6  nop     dword ptr [rax+rax+00h]
0x14003acab  test    al, al
0x14003acad  jz      short loc_14003AD03
0x14003acaf  lea     rcx, aNtdcomposition_34; "NtDCompositionReleaseAllResources"
0x14003acb6  mov     rdx, 136h
0x14003acbd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003acc4  nop     dword ptr [rax+rax+00h]
0x14003acc9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003acd0  nop     dword ptr [rax+rax+00h]
0x14003acd5  test    al, al
0x14003acd7  jz      short loc_14003AD03
0x14003acd9  lea     rcx, W32pServiceTableFilter
0x14003ace0  mov     edx, cs:W32pServiceLimitFilter
0x14003ace6  mov     rax, 136h
0x14003aced  lea     rcx, [rcx+rdx*4]
0x14003acf1  movsx   eax, byte ptr [rcx+rax]
0x14003acf5  or      eax, eax
0x14003acf7  jle     short loc_14003ACFE
0x14003acf9  mov     eax, 0C000001Ch
0x14003acfe  add     rsp, 48h
0x14003ad02  retn
0x14003ad03  mov     rax, cs:__imp_NtDCompositionReleaseAllResources
0x14003ad0a  mov     rcx, [rsp+48h+var_28]
0x14003ad0f  mov     rdx, [rsp+48h+var_20]
0x14003ad14  mov     r8, [rsp+48h+var_18]
0x14003ad19  mov     r9, [rsp+48h+var_10]
0x14003ad1e  add     rsp, 48h
0x14003ad22  jmp     rax
```
