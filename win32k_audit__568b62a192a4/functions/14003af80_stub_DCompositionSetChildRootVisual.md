# _stub_DCompositionSetChildRootVisual

- ea: `0x14003af80`
- end: `0x14003b027`
- name: `_stub_DCompositionSetChildRootVisual`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003af80`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003afc9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003afc9`

## string_xrefs

- `0x14003afaf`: `NtDCompositionSetChildRootVisual`

## pseudocode

```c
__int64 stub_DCompositionSetChildRootVisual()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSetChildRootVisual();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSetChildRootVisual();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003af80  sub     rsp, 48h
0x14003af84  mov     [rsp+48h+var_28], rcx
0x14003af89  mov     [rsp+48h+var_20], rdx
0x14003af8e  mov     [rsp+48h+var_18], r8
0x14003af93  mov     [rsp+48h+var_10], r9
0x14003af98  mov     rcx, 13Dh
0x14003af9f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003afa6  nop     dword ptr [rax+rax+00h]
0x14003afab  test    al, al
0x14003afad  jz      short loc_14003B003
0x14003afaf  lea     rcx, aNtdcomposition_41; "NtDCompositionSetChildRootVisual"
0x14003afb6  mov     rdx, 13Dh
0x14003afbd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003afc4  nop     dword ptr [rax+rax+00h]
0x14003afc9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003afd0  nop     dword ptr [rax+rax+00h]
0x14003afd5  test    al, al
0x14003afd7  jz      short loc_14003B003
0x14003afd9  lea     rcx, W32pServiceTableFilter
0x14003afe0  mov     edx, cs:W32pServiceLimitFilter
0x14003afe6  mov     rax, 13Dh
0x14003afed  lea     rcx, [rcx+rdx*4]
0x14003aff1  movsx   eax, byte ptr [rcx+rax]
0x14003aff5  or      eax, eax
0x14003aff7  jle     short loc_14003AFFE
0x14003aff9  mov     eax, 0C000001Ch
0x14003affe  add     rsp, 48h
0x14003b002  retn
0x14003b003  mov     rax, cs:__imp_NtDCompositionSetChildRootVisual
0x14003b00a  mov     rcx, [rsp+48h+var_28]
0x14003b00f  mov     rdx, [rsp+48h+var_20]
0x14003b014  mov     r8, [rsp+48h+var_18]
0x14003b019  mov     r9, [rsp+48h+var_10]
0x14003b01e  add     rsp, 48h
0x14003b022  jmp     rax
```
