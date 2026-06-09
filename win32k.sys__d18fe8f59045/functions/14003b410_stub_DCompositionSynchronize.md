# _stub_DCompositionSynchronize

- ea: `0x14003b410`
- end: `0x14003b4b7`
- name: `_stub_DCompositionSynchronize`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b410`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b459`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b459`

## string_xrefs

- `0x14003b43f`: `NtDCompositionSynchronize`

## pseudocode

```c
__int64 stub_DCompositionSynchronize()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSynchronize();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSynchronize();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b410  sub     rsp, 48h
0x14003b414  mov     [rsp+48h+var_28], rcx
0x14003b419  mov     [rsp+48h+var_20], rdx
0x14003b41e  mov     [rsp+48h+var_18], r8
0x14003b423  mov     [rsp+48h+var_10], r9
0x14003b428  mov     rcx, 141h
0x14003b42f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b436  nop     dword ptr [rax+rax+00h]
0x14003b43b  test    al, al
0x14003b43d  jz      short loc_14003B493
0x14003b43f  lea     rcx, aNtdcomposition_45; "NtDCompositionSynchronize"
0x14003b446  mov     rdx, 141h
0x14003b44d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b454  nop     dword ptr [rax+rax+00h]
0x14003b459  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b460  nop     dword ptr [rax+rax+00h]
0x14003b465  test    al, al
0x14003b467  jz      short loc_14003B493
0x14003b469  lea     rcx, W32pServiceTableFilter
0x14003b470  mov     edx, cs:W32pServiceLimitFilter
0x14003b476  mov     rax, 141h
0x14003b47d  lea     rcx, [rcx+rdx*4]
0x14003b481  movsx   eax, byte ptr [rcx+rax]
0x14003b485  or      eax, eax
0x14003b487  jle     short loc_14003B48E
0x14003b489  mov     eax, 0C000001Ch
0x14003b48e  add     rsp, 48h
0x14003b492  retn
0x14003b493  mov     rax, cs:__imp_NtDCompositionSynchronize
0x14003b49a  mov     rcx, [rsp+48h+var_28]
0x14003b49f  mov     rdx, [rsp+48h+var_20]
0x14003b4a4  mov     r8, [rsp+48h+var_18]
0x14003b4a9  mov     r9, [rsp+48h+var_10]
0x14003b4ae  add     rsp, 48h
0x14003b4b2  jmp     rax
```
