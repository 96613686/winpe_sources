# _stub_DCompositionConfirmFrame

- ea: `0x140039610`
- end: `0x1400396b7`
- name: `_stub_DCompositionConfirmFrame`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039610`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039659`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039659`

## string_xrefs

- `0x14003963f`: `NtDCompositionConfirmFrame`

## pseudocode

```c
__int64 stub_DCompositionConfirmFrame()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionConfirmFrame();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionConfirmFrame();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039610  sub     rsp, 48h
0x140039614  mov     [rsp+48h+var_28], rcx
0x140039619  mov     [rsp+48h+var_20], rdx
0x14003961e  mov     [rsp+48h+var_18], r8
0x140039623  mov     [rsp+48h+var_10], r9
0x140039628  mov     rcx, 118h
0x14003962f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039636  nop     dword ptr [rax+rax+00h]
0x14003963b  test    al, al
0x14003963d  jz      short loc_140039693
0x14003963f  lea     rcx, aNtdcomposition_4; "NtDCompositionConfirmFrame"
0x140039646  mov     rdx, 118h
0x14003964d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039654  nop     dword ptr [rax+rax+00h]
0x140039659  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039660  nop     dword ptr [rax+rax+00h]
0x140039665  test    al, al
0x140039667  jz      short loc_140039693
0x140039669  lea     rcx, W32pServiceTableFilter
0x140039670  mov     edx, cs:W32pServiceLimitFilter
0x140039676  mov     rax, 118h
0x14003967d  lea     rcx, [rcx+rdx*4]
0x140039681  movsx   eax, byte ptr [rcx+rax]
0x140039685  or      eax, eax
0x140039687  jle     short loc_14003968E
0x140039689  mov     eax, 0C000001Ch
0x14003968e  add     rsp, 48h
0x140039692  retn
0x140039693  mov     rax, cs:__imp_NtDCompositionConfirmFrame
0x14003969a  mov     rcx, [rsp+48h+var_28]
0x14003969f  mov     rdx, [rsp+48h+var_20]
0x1400396a4  mov     r8, [rsp+48h+var_18]
0x1400396a9  mov     r9, [rsp+48h+var_10]
0x1400396ae  add     rsp, 48h
0x1400396b2  jmp     rax
```
