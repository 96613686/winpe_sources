# _stub_DCompositionCreateAndBindSharedSection

- ea: `0x140039940`
- end: `0x1400399e7`
- name: `_stub_DCompositionCreateAndBindSharedSection`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039940`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039989`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039989`

## string_xrefs

- `0x14003996f`: `NtDCompositionCreateAndBindSharedSection`

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
0x140039940  sub     rsp, 48h
0x140039944  mov     [rsp+48h+var_28], rcx
0x140039949  mov     [rsp+48h+var_20], rdx
0x14003994e  mov     [rsp+48h+var_18], r8
0x140039953  mov     [rsp+48h+var_10], r9
0x140039958  mov     rcx, 11Ah
0x14003995f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039966  nop     dword ptr [rax+rax+00h]
0x14003996b  test    al, al
0x14003996d  jz      short loc_1400399C3
0x14003996f  lea     rcx, aNtdcomposition_6; "NtDCompositionCreateAndBindSharedSectio"...
0x140039976  mov     rdx, 11Ah
0x14003997d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039984  nop     dword ptr [rax+rax+00h]
0x140039989  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039990  nop     dword ptr [rax+rax+00h]
0x140039995  test    al, al
0x140039997  jz      short loc_1400399C3
0x140039999  lea     rcx, W32pServiceTableFilter
0x1400399a0  mov     edx, cs:W32pServiceLimitFilter
0x1400399a6  mov     rax, 11Ah
0x1400399ad  lea     rcx, [rcx+rdx*4]
0x1400399b1  movsx   eax, byte ptr [rcx+rax]
0x1400399b5  or      eax, eax
0x1400399b7  jle     short loc_1400399BE
0x1400399b9  mov     eax, 0C000001Ch
0x1400399be  add     rsp, 48h
0x1400399c2  retn
0x1400399c3  mov     rax, cs:__imp_NtDCompositionCreateAndBindSharedSection
0x1400399ca  mov     rcx, [rsp+48h+var_28]
0x1400399cf  mov     rdx, [rsp+48h+var_20]
0x1400399d4  mov     r8, [rsp+48h+var_18]
0x1400399d9  mov     r9, [rsp+48h+var_10]
0x1400399de  add     rsp, 48h
0x1400399e2  jmp     rax
```
