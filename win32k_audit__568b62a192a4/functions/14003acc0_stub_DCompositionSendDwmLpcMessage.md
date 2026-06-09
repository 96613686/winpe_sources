# _stub_DCompositionSendDwmLpcMessage

- ea: `0x14003acc0`
- end: `0x14003ad67`
- name: `_stub_DCompositionSendDwmLpcMessage`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003acc0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ad09`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ad09`

## string_xrefs

- `0x14003acef`: `NtDCompositionSendDwmLpcMessage`

## pseudocode

```c
__int64 stub_DCompositionSendDwmLpcMessage()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSendDwmLpcMessage();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSendDwmLpcMessage();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[39] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003acc0  sub     rsp, 48h
0x14003acc4  mov     [rsp+48h+var_28], rcx
0x14003acc9  mov     [rsp+48h+var_20], rdx
0x14003acce  mov     [rsp+48h+var_18], r8
0x14003acd3  mov     [rsp+48h+var_10], r9
0x14003acd8  mov     rcx, 139h
0x14003acdf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ace6  nop     dword ptr [rax+rax+00h]
0x14003aceb  test    al, al
0x14003aced  jz      short loc_14003AD43
0x14003acef  lea     rcx, aNtdcomposition_37; "NtDCompositionSendDwmLpcMessage"
0x14003acf6  mov     rdx, 139h
0x14003acfd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ad04  nop     dword ptr [rax+rax+00h]
0x14003ad09  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ad10  nop     dword ptr [rax+rax+00h]
0x14003ad15  test    al, al
0x14003ad17  jz      short loc_14003AD43
0x14003ad19  lea     rcx, W32pServiceTableFilter
0x14003ad20  mov     edx, cs:W32pServiceLimitFilter
0x14003ad26  mov     rax, 139h
0x14003ad2d  lea     rcx, [rcx+rdx*4]
0x14003ad31  movsx   eax, byte ptr [rcx+rax]
0x14003ad35  or      eax, eax
0x14003ad37  jle     short loc_14003AD3E
0x14003ad39  mov     eax, 0C000001Ch
0x14003ad3e  add     rsp, 48h
0x14003ad42  retn
0x14003ad43  mov     rax, cs:__imp_NtDCompositionSendDwmLpcMessage
0x14003ad4a  mov     rcx, [rsp+48h+var_28]
0x14003ad4f  mov     rdx, [rsp+48h+var_20]
0x14003ad54  mov     r8, [rsp+48h+var_18]
0x14003ad59  mov     r9, [rsp+48h+var_10]
0x14003ad5e  add     rsp, 48h
0x14003ad62  jmp     rax
```
