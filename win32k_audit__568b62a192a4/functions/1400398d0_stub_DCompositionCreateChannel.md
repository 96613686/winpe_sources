# _stub_DCompositionCreateChannel

- ea: `0x1400398d0`
- end: `0x140039977`
- name: `_stub_DCompositionCreateChannel`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400398d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039919`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039919`

## string_xrefs

- `0x1400398ff`: `NtDCompositionCreateChannel`

## pseudocode

```c
__int64 stub_DCompositionCreateChannel()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateChannel();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateChannel();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400398d0  sub     rsp, 48h
0x1400398d4  mov     [rsp+48h+var_28], rcx
0x1400398d9  mov     [rsp+48h+var_20], rdx
0x1400398de  mov     [rsp+48h+var_18], r8
0x1400398e3  mov     [rsp+48h+var_10], r9
0x1400398e8  mov     rcx, 11Ch
0x1400398ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400398f6  nop     dword ptr [rax+rax+00h]
0x1400398fb  test    al, al
0x1400398fd  jz      short loc_140039953
0x1400398ff  lea     rcx, aNtdcomposition_8; "NtDCompositionCreateChannel"
0x140039906  mov     rdx, 11Ch
0x14003990d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039914  nop     dword ptr [rax+rax+00h]
0x140039919  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039920  nop     dword ptr [rax+rax+00h]
0x140039925  test    al, al
0x140039927  jz      short loc_140039953
0x140039929  lea     rcx, W32pServiceTableFilter
0x140039930  mov     edx, cs:W32pServiceLimitFilter
0x140039936  mov     rax, 11Ch
0x14003993d  lea     rcx, [rcx+rdx*4]
0x140039941  movsx   eax, byte ptr [rcx+rax]
0x140039945  or      eax, eax
0x140039947  jle     short loc_14003994E
0x140039949  mov     eax, 0C000001Ch
0x14003994e  add     rsp, 48h
0x140039952  retn
0x140039953  mov     rax, cs:__imp_NtDCompositionCreateChannel
0x14003995a  mov     rcx, [rsp+48h+var_28]
0x14003995f  mov     rdx, [rsp+48h+var_20]
0x140039964  mov     r8, [rsp+48h+var_18]
0x140039969  mov     r9, [rsp+48h+var_10]
0x14003996e  add     rsp, 48h
0x140039972  jmp     rax
```
