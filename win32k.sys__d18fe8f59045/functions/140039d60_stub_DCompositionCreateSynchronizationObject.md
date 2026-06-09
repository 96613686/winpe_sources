# _stub_DCompositionCreateSynchronizationObject

- ea: `0x140039d60`
- end: `0x140039e07`
- name: `_stub_DCompositionCreateSynchronizationObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039d60`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039da9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039da9`

## string_xrefs

- `0x140039d8f`: `NtDCompositionCreateSynchronizationObject`

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
0x140039d60  sub     rsp, 48h
0x140039d64  mov     [rsp+48h+var_28], rcx
0x140039d69  mov     [rsp+48h+var_20], rdx
0x140039d6e  mov     [rsp+48h+var_18], r8
0x140039d73  mov     [rsp+48h+var_10], r9
0x140039d78  mov     rcx, 120h
0x140039d7f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039d86  nop     dword ptr [rax+rax+00h]
0x140039d8b  test    al, al
0x140039d8d  jz      short loc_140039DE3
0x140039d8f  lea     rcx, aNtdcomposition_12; "NtDCompositionCreateSynchronizationObje"...
0x140039d96  mov     rdx, 120h
0x140039d9d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039da4  nop     dword ptr [rax+rax+00h]
0x140039da9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039db0  nop     dword ptr [rax+rax+00h]
0x140039db5  test    al, al
0x140039db7  jz      short loc_140039DE3
0x140039db9  lea     rcx, W32pServiceTableFilter
0x140039dc0  mov     edx, cs:W32pServiceLimitFilter
0x140039dc6  mov     rax, 120h
0x140039dcd  lea     rcx, [rcx+rdx*4]
0x140039dd1  movsx   eax, byte ptr [rcx+rax]
0x140039dd5  or      eax, eax
0x140039dd7  jle     short loc_140039DDE
0x140039dd9  mov     eax, 0C000001Ch
0x140039dde  add     rsp, 48h
0x140039de2  retn
0x140039de3  mov     rax, cs:__imp_NtDCompositionCreateSynchronizationObject
0x140039dea  mov     rcx, [rsp+48h+var_28]
0x140039def  mov     rdx, [rsp+48h+var_20]
0x140039df4  mov     r8, [rsp+48h+var_18]
0x140039df9  mov     r9, [rsp+48h+var_10]
0x140039dfe  add     rsp, 48h
0x140039e02  jmp     rax
```
