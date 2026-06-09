# _stub_DCompositionEnableMMCSS

- ea: `0x140039f00`
- end: `0x140039fa7`
- name: `_stub_DCompositionEnableMMCSS`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039f00`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039f49`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039f49`

## string_xrefs

- `0x140039f2f`: `NtDCompositionEnableMMCSS`

## pseudocode

```c
__int64 stub_DCompositionEnableMMCSS()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionEnableMMCSS();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionEnableMMCSS();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039f00  sub     rsp, 48h
0x140039f04  mov     [rsp+48h+var_28], rcx
0x140039f09  mov     [rsp+48h+var_20], rdx
0x140039f0e  mov     [rsp+48h+var_18], r8
0x140039f13  mov     [rsp+48h+var_10], r9
0x140039f18  mov     rcx, 125h
0x140039f1f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039f26  nop     dword ptr [rax+rax+00h]
0x140039f2b  test    al, al
0x140039f2d  jz      short loc_140039F83
0x140039f2f  lea     rcx, aNtdcomposition_17; "NtDCompositionEnableMMCSS"
0x140039f36  mov     rdx, 125h
0x140039f3d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039f44  nop     dword ptr [rax+rax+00h]
0x140039f49  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039f50  nop     dword ptr [rax+rax+00h]
0x140039f55  test    al, al
0x140039f57  jz      short loc_140039F83
0x140039f59  lea     rcx, W32pServiceTableFilter
0x140039f60  mov     edx, cs:W32pServiceLimitFilter
0x140039f66  mov     rax, 125h
0x140039f6d  lea     rcx, [rcx+rdx*4]
0x140039f71  movsx   eax, byte ptr [rcx+rax]
0x140039f75  or      eax, eax
0x140039f77  jle     short loc_140039F7E
0x140039f79  mov     eax, 0C000001Ch
0x140039f7e  add     rsp, 48h
0x140039f82  retn
0x140039f83  mov     rax, cs:__imp_NtDCompositionEnableMMCSS
0x140039f8a  mov     rcx, [rsp+48h+var_28]
0x140039f8f  mov     rdx, [rsp+48h+var_20]
0x140039f94  mov     r8, [rsp+48h+var_18]
0x140039f99  mov     r9, [rsp+48h+var_10]
0x140039f9e  add     rsp, 48h
0x140039fa2  jmp     rax
```
