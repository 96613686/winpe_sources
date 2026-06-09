# _stub_DCompositionReleaseAllResources

- ea: `0x14003aab0`
- end: `0x14003ab57`
- name: `_stub_DCompositionReleaseAllResources`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003aab0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aaf9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aaf9`

## string_xrefs

- `0x14003aadf`: `NtDCompositionReleaseAllResources`

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
0x14003aab0  sub     rsp, 48h
0x14003aab4  mov     [rsp+48h+var_28], rcx
0x14003aab9  mov     [rsp+48h+var_20], rdx
0x14003aabe  mov     [rsp+48h+var_18], r8
0x14003aac3  mov     [rsp+48h+var_10], r9
0x14003aac8  mov     rcx, 136h
0x14003aacf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003aad6  nop     dword ptr [rax+rax+00h]
0x14003aadb  test    al, al
0x14003aadd  jz      short loc_14003AB33
0x14003aadf  lea     rcx, aNtdcomposition_34; "NtDCompositionReleaseAllResources"
0x14003aae6  mov     rdx, 136h
0x14003aaed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003aaf4  nop     dword ptr [rax+rax+00h]
0x14003aaf9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ab00  nop     dword ptr [rax+rax+00h]
0x14003ab05  test    al, al
0x14003ab07  jz      short loc_14003AB33
0x14003ab09  lea     rcx, W32pServiceTableFilter
0x14003ab10  mov     edx, cs:W32pServiceLimitFilter
0x14003ab16  mov     rax, 136h
0x14003ab1d  lea     rcx, [rcx+rdx*4]
0x14003ab21  movsx   eax, byte ptr [rcx+rax]
0x14003ab25  or      eax, eax
0x14003ab27  jle     short loc_14003AB2E
0x14003ab29  mov     eax, 0C000001Ch
0x14003ab2e  add     rsp, 48h
0x14003ab32  retn
0x14003ab33  mov     rax, cs:__imp_NtDCompositionReleaseAllResources
0x14003ab3a  mov     rcx, [rsp+48h+var_28]
0x14003ab3f  mov     rdx, [rsp+48h+var_20]
0x14003ab44  mov     r8, [rsp+48h+var_18]
0x14003ab49  mov     r9, [rsp+48h+var_10]
0x14003ab4e  add     rsp, 48h
0x14003ab52  jmp     rax
```
