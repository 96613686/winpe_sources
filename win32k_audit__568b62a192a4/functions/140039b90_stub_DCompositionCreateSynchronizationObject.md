# _stub_DCompositionCreateSynchronizationObject

- ea: `0x140039b90`
- end: `0x140039c37`
- name: `_stub_DCompositionCreateSynchronizationObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039b90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039bd9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039bd9`

## string_xrefs

- `0x140039bbf`: `NtDCompositionCreateSynchronizationObject`

## pseudocode

```c
__int64 stub_DCompositionCreateSynchronizationObject()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateSynchronizationObject();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateSynchronizationObject();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039b90  sub     rsp, 48h
0x140039b94  mov     [rsp+48h+var_28], rcx
0x140039b99  mov     [rsp+48h+var_20], rdx
0x140039b9e  mov     [rsp+48h+var_18], r8
0x140039ba3  mov     [rsp+48h+var_10], r9
0x140039ba8  mov     rcx, 120h
0x140039baf  call    cs:__imp_IsWin32KSyscallFiltered
0x140039bb6  nop     dword ptr [rax+rax+00h]
0x140039bbb  test    al, al
0x140039bbd  jz      short loc_140039C13
0x140039bbf  lea     rcx, aNtdcomposition_12; "NtDCompositionCreateSynchronizationObje"...
0x140039bc6  mov     rdx, 120h
0x140039bcd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039bd4  nop     dword ptr [rax+rax+00h]
0x140039bd9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039be0  nop     dword ptr [rax+rax+00h]
0x140039be5  test    al, al
0x140039be7  jz      short loc_140039C13
0x140039be9  lea     rcx, W32pServiceTableFilter
0x140039bf0  mov     edx, cs:W32pServiceLimitFilter
0x140039bf6  mov     rax, 120h
0x140039bfd  lea     rcx, [rcx+rdx*4]
0x140039c01  movsx   eax, byte ptr [rcx+rax]
0x140039c05  or      eax, eax
0x140039c07  jle     short loc_140039C0E
0x140039c09  mov     eax, 0C000001Ch
0x140039c0e  add     rsp, 48h
0x140039c12  retn
0x140039c13  mov     rax, cs:__imp_NtDCompositionCreateSynchronizationObject
0x140039c1a  mov     rcx, [rsp+48h+var_28]
0x140039c1f  mov     rdx, [rsp+48h+var_20]
0x140039c24  mov     r8, [rsp+48h+var_18]
0x140039c29  mov     r9, [rsp+48h+var_10]
0x140039c2e  add     rsp, 48h
0x140039c32  jmp     rax
```
