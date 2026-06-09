# _stub_DCompositionCreateRemoteTexture

- ea: `0x140039a30`
- end: `0x140039ad7`
- name: `_stub_DCompositionCreateRemoteTexture`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039a30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039a79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039a79`

## string_xrefs

- `0x140039a5f`: `NtDCompositionCreateRemoteTexture`

## pseudocode

```c
__int64 stub_DCompositionCreateRemoteTexture()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateRemoteTexture();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateRemoteTexture();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039a30  sub     rsp, 48h
0x140039a34  mov     [rsp+48h+var_28], rcx
0x140039a39  mov     [rsp+48h+var_20], rdx
0x140039a3e  mov     [rsp+48h+var_18], r8
0x140039a43  mov     [rsp+48h+var_10], r9
0x140039a48  mov     rcx, 11Eh
0x140039a4f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039a56  nop     dword ptr [rax+rax+00h]
0x140039a5b  test    al, al
0x140039a5d  jz      short loc_140039AB3
0x140039a5f  lea     rcx, aNtdcomposition_10; "NtDCompositionCreateRemoteTexture"
0x140039a66  mov     rdx, 11Eh
0x140039a6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039a74  nop     dword ptr [rax+rax+00h]
0x140039a79  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039a80  nop     dword ptr [rax+rax+00h]
0x140039a85  test    al, al
0x140039a87  jz      short loc_140039AB3
0x140039a89  lea     rcx, W32pServiceTableFilter
0x140039a90  mov     edx, cs:W32pServiceLimitFilter
0x140039a96  mov     rax, 11Eh
0x140039a9d  lea     rcx, [rcx+rdx*4]
0x140039aa1  movsx   eax, byte ptr [rcx+rax]
0x140039aa5  or      eax, eax
0x140039aa7  jle     short loc_140039AAE
0x140039aa9  mov     eax, 0C000001Ch
0x140039aae  add     rsp, 48h
0x140039ab2  retn
0x140039ab3  mov     rax, cs:__imp_NtDCompositionCreateRemoteTexture
0x140039aba  mov     rcx, [rsp+48h+var_28]
0x140039abf  mov     rdx, [rsp+48h+var_20]
0x140039ac4  mov     r8, [rsp+48h+var_18]
0x140039ac9  mov     r9, [rsp+48h+var_10]
0x140039ace  add     rsp, 48h
0x140039ad2  jmp     rax
```
