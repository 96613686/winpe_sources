# _stub_DCompositionCreateRemoteTexture

- ea: `0x140039c00`
- end: `0x140039ca7`
- name: `_stub_DCompositionCreateRemoteTexture`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039c00`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039c49`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039c49`

## string_xrefs

- `0x140039c2f`: `NtDCompositionCreateRemoteTexture`

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
0x140039c00  sub     rsp, 48h
0x140039c04  mov     [rsp+48h+var_28], rcx
0x140039c09  mov     [rsp+48h+var_20], rdx
0x140039c0e  mov     [rsp+48h+var_18], r8
0x140039c13  mov     [rsp+48h+var_10], r9
0x140039c18  mov     rcx, 11Eh
0x140039c1f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039c26  nop     dword ptr [rax+rax+00h]
0x140039c2b  test    al, al
0x140039c2d  jz      short loc_140039C83
0x140039c2f  lea     rcx, aNtdcomposition_10; "NtDCompositionCreateRemoteTexture"
0x140039c36  mov     rdx, 11Eh
0x140039c3d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039c44  nop     dword ptr [rax+rax+00h]
0x140039c49  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039c50  nop     dword ptr [rax+rax+00h]
0x140039c55  test    al, al
0x140039c57  jz      short loc_140039C83
0x140039c59  lea     rcx, W32pServiceTableFilter
0x140039c60  mov     edx, cs:W32pServiceLimitFilter
0x140039c66  mov     rax, 11Eh
0x140039c6d  lea     rcx, [rcx+rdx*4]
0x140039c71  movsx   eax, byte ptr [rcx+rax]
0x140039c75  or      eax, eax
0x140039c77  jle     short loc_140039C7E
0x140039c79  mov     eax, 0C000001Ch
0x140039c7e  add     rsp, 48h
0x140039c82  retn
0x140039c83  mov     rax, cs:__imp_NtDCompositionCreateRemoteTexture
0x140039c8a  mov     rcx, [rsp+48h+var_28]
0x140039c8f  mov     rdx, [rsp+48h+var_20]
0x140039c94  mov     r8, [rsp+48h+var_18]
0x140039c99  mov     r9, [rsp+48h+var_10]
0x140039c9e  add     rsp, 48h
0x140039ca2  jmp     rax
```
