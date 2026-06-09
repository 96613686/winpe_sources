# _stub_DCompositionCreateAndBindSharedSection

- ea: `0x140039770`
- end: `0x140039817`
- name: `_stub_DCompositionCreateAndBindSharedSection`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039770`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400397b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400397b9`

## string_xrefs

- `0x14003979f`: `NtDCompositionCreateAndBindSharedSection`

## pseudocode

```c
__int64 stub_DCompositionCreateAndBindSharedSection()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateAndBindSharedSection();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateAndBindSharedSection();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039770  sub     rsp, 48h
0x140039774  mov     [rsp+48h+var_28], rcx
0x140039779  mov     [rsp+48h+var_20], rdx
0x14003977e  mov     [rsp+48h+var_18], r8
0x140039783  mov     [rsp+48h+var_10], r9
0x140039788  mov     rcx, 11Ah
0x14003978f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039796  nop     dword ptr [rax+rax+00h]
0x14003979b  test    al, al
0x14003979d  jz      short loc_1400397F3
0x14003979f  lea     rcx, aNtdcomposition_6; "NtDCompositionCreateAndBindSharedSectio"...
0x1400397a6  mov     rdx, 11Ah
0x1400397ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400397b4  nop     dword ptr [rax+rax+00h]
0x1400397b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400397c0  nop     dword ptr [rax+rax+00h]
0x1400397c5  test    al, al
0x1400397c7  jz      short loc_1400397F3
0x1400397c9  lea     rcx, W32pServiceTableFilter
0x1400397d0  mov     edx, cs:W32pServiceLimitFilter
0x1400397d6  mov     rax, 11Ah
0x1400397dd  lea     rcx, [rcx+rdx*4]
0x1400397e1  movsx   eax, byte ptr [rcx+rax]
0x1400397e5  or      eax, eax
0x1400397e7  jle     short loc_1400397EE
0x1400397e9  mov     eax, 0C000001Ch
0x1400397ee  add     rsp, 48h
0x1400397f2  retn
0x1400397f3  mov     rax, cs:__imp_NtDCompositionCreateAndBindSharedSection
0x1400397fa  mov     rcx, [rsp+48h+var_28]
0x1400397ff  mov     rdx, [rsp+48h+var_20]
0x140039804  mov     r8, [rsp+48h+var_18]
0x140039809  mov     r9, [rsp+48h+var_10]
0x14003980e  add     rsp, 48h
0x140039812  jmp     rax
```
