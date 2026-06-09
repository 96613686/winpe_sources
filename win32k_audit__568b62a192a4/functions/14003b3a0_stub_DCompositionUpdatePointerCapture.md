# _stub_DCompositionUpdatePointerCapture

- ea: `0x14003b3a0`
- end: `0x14003b447`
- name: `_stub_DCompositionUpdatePointerCapture`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b3a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b3e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b3e9`

## string_xrefs

- `0x14003b3cf`: `NtDCompositionUpdatePointerCapture`

## pseudocode

```c
__int64 stub_DCompositionUpdatePointerCapture()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionUpdatePointerCapture();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionUpdatePointerCapture();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b3a0  sub     rsp, 48h
0x14003b3a4  mov     [rsp+48h+var_28], rcx
0x14003b3a9  mov     [rsp+48h+var_20], rdx
0x14003b3ae  mov     [rsp+48h+var_18], r8
0x14003b3b3  mov     [rsp+48h+var_10], r9
0x14003b3b8  mov     rcx, 143h
0x14003b3bf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b3c6  nop     dword ptr [rax+rax+00h]
0x14003b3cb  test    al, al
0x14003b3cd  jz      short loc_14003B423
0x14003b3cf  lea     rcx, aNtdcomposition_47; "NtDCompositionUpdatePointerCapture"
0x14003b3d6  mov     rdx, 143h
0x14003b3dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b3e4  nop     dword ptr [rax+rax+00h]
0x14003b3e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b3f0  nop     dword ptr [rax+rax+00h]
0x14003b3f5  test    al, al
0x14003b3f7  jz      short loc_14003B423
0x14003b3f9  lea     rcx, W32pServiceTableFilter
0x14003b400  mov     edx, cs:W32pServiceLimitFilter
0x14003b406  mov     rax, 143h
0x14003b40d  lea     rcx, [rcx+rdx*4]
0x14003b411  movsx   eax, byte ptr [rcx+rax]
0x14003b415  or      eax, eax
0x14003b417  jle     short loc_14003B41E
0x14003b419  mov     eax, 0C000001Ch
0x14003b41e  add     rsp, 48h
0x14003b422  retn
0x14003b423  mov     rax, cs:__imp_NtDCompositionUpdatePointerCapture
0x14003b42a  mov     rcx, [rsp+48h+var_28]
0x14003b42f  mov     rdx, [rsp+48h+var_20]
0x14003b434  mov     r8, [rsp+48h+var_18]
0x14003b439  mov     r9, [rsp+48h+var_10]
0x14003b43e  add     rsp, 48h
0x14003b442  jmp     rax
```
