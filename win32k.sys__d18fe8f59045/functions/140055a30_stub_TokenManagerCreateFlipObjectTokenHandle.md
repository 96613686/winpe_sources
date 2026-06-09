# _stub_TokenManagerCreateFlipObjectTokenHandle

- ea: `0x140055a30`
- end: `0x140055ad7`
- name: `_stub_TokenManagerCreateFlipObjectTokenHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055a30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055a79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055a79`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerCreateFlipObjectTokenHandle` at `0x140055ab3`

## string_xrefs

- `0x140055a5f`: `NtTokenManagerCreateFlipObjectTokenHandle`

## pseudocode

```c
__int64 __fastcall stub_TokenManagerCreateFlipObjectTokenHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtTokenManagerCreateFlipObjectTokenHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtTokenManagerCreateFlipObjectTokenHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055a30  sub     rsp, 48h
0x140055a34  mov     [rsp+48h+var_28], rcx
0x140055a39  mov     [rsp+48h+var_20], rdx
0x140055a3e  mov     [rsp+48h+var_18], r8
0x140055a43  mov     [rsp+48h+var_10], r9
0x140055a48  mov     rcx, 3A7h
0x140055a4f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055a56  nop     dword ptr [rax+rax+00h]
0x140055a5b  test    al, al
0x140055a5d  jz      short loc_140055AB3
0x140055a5f  lea     rcx, aNttokenmanager_1; "NtTokenManagerCreateFlipObjectTokenHand"...
0x140055a66  mov     rdx, 3A7h
0x140055a6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055a74  nop     dword ptr [rax+rax+00h]
0x140055a79  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055a80  nop     dword ptr [rax+rax+00h]
0x140055a85  test    al, al
0x140055a87  jz      short loc_140055AB3
0x140055a89  lea     rcx, W32pServiceTableFilter
0x140055a90  mov     edx, cs:W32pServiceLimitFilter
0x140055a96  mov     rax, 3A7h
0x140055a9d  lea     rcx, [rcx+rdx*4]
0x140055aa1  movsx   eax, byte ptr [rcx+rax]
0x140055aa5  or      eax, eax
0x140055aa7  jle     short loc_140055AAE
0x140055aa9  mov     eax, 0C000001Ch
0x140055aae  add     rsp, 48h
0x140055ab2  retn
0x140055ab3  mov     rax, cs:__imp_NtTokenManagerCreateFlipObjectTokenHandle
0x140055aba  mov     rcx, [rsp+48h+var_28]
0x140055abf  mov     rdx, [rsp+48h+var_20]
0x140055ac4  mov     r8, [rsp+48h+var_18]
0x140055ac9  mov     r9, [rsp+48h+var_10]
0x140055ace  add     rsp, 48h
0x140055ad2  jmp     rax
```
