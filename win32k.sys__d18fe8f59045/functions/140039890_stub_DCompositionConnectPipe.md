# _stub_DCompositionConnectPipe

- ea: `0x140039890`
- end: `0x140039937`
- name: `_stub_DCompositionConnectPipe`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039890`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400398d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400398d9`

## string_xrefs

- `0x1400398bf`: `NtDCompositionConnectPipe`

## pseudocode

```c
__int64 stub_DCompositionConnectPipe()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionConnectPipe();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionConnectPipe();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039890  sub     rsp, 48h
0x140039894  mov     [rsp+48h+var_28], rcx
0x140039899  mov     [rsp+48h+var_20], rdx
0x14003989e  mov     [rsp+48h+var_18], r8
0x1400398a3  mov     [rsp+48h+var_10], r9
0x1400398a8  mov     rcx, 119h
0x1400398af  call    cs:__imp_IsWin32KSyscallFiltered
0x1400398b6  nop     dword ptr [rax+rax+00h]
0x1400398bb  test    al, al
0x1400398bd  jz      short loc_140039913
0x1400398bf  lea     rcx, aNtdcomposition_5; "NtDCompositionConnectPipe"
0x1400398c6  mov     rdx, 119h
0x1400398cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400398d4  nop     dword ptr [rax+rax+00h]
0x1400398d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400398e0  nop     dword ptr [rax+rax+00h]
0x1400398e5  test    al, al
0x1400398e7  jz      short loc_140039913
0x1400398e9  lea     rcx, W32pServiceTableFilter
0x1400398f0  mov     edx, cs:W32pServiceLimitFilter
0x1400398f6  mov     rax, 119h
0x1400398fd  lea     rcx, [rcx+rdx*4]
0x140039901  movsx   eax, byte ptr [rcx+rax]
0x140039905  or      eax, eax
0x140039907  jle     short loc_14003990E
0x140039909  mov     eax, 0C000001Ch
0x14003990e  add     rsp, 48h
0x140039912  retn
0x140039913  mov     rax, cs:__imp_NtDCompositionConnectPipe
0x14003991a  mov     rcx, [rsp+48h+var_28]
0x14003991f  mov     rdx, [rsp+48h+var_20]
0x140039924  mov     r8, [rsp+48h+var_18]
0x140039929  mov     r9, [rsp+48h+var_10]
0x14003992e  add     rsp, 48h
0x140039932  jmp     rax
```
