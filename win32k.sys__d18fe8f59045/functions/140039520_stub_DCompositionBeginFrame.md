# _stub_DCompositionBeginFrame

- ea: `0x140039520`
- end: `0x1400395c7`
- name: `_stub_DCompositionBeginFrame`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039520`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039569`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039569`

## string_xrefs

- `0x14003954f`: `NtDCompositionBeginFrame`

## pseudocode

```c
__int64 stub_DCompositionBeginFrame()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionBeginFrame();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionBeginFrame();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039520  sub     rsp, 48h
0x140039524  mov     [rsp+48h+var_28], rcx
0x140039529  mov     [rsp+48h+var_20], rdx
0x14003952e  mov     [rsp+48h+var_18], r8
0x140039533  mov     [rsp+48h+var_10], r9
0x140039538  mov     rcx, 114h
0x14003953f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039546  nop     dword ptr [rax+rax+00h]
0x14003954b  test    al, al
0x14003954d  jz      short loc_1400395A3
0x14003954f  lea     rcx, aNtdcomposition_0; "NtDCompositionBeginFrame"
0x140039556  mov     rdx, 114h
0x14003955d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039564  nop     dword ptr [rax+rax+00h]
0x140039569  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039570  nop     dword ptr [rax+rax+00h]
0x140039575  test    al, al
0x140039577  jz      short loc_1400395A3
0x140039579  lea     rcx, W32pServiceTableFilter
0x140039580  mov     edx, cs:W32pServiceLimitFilter
0x140039586  mov     rax, 114h
0x14003958d  lea     rcx, [rcx+rdx*4]
0x140039591  movsx   eax, byte ptr [rcx+rax]
0x140039595  or      eax, eax
0x140039597  jle     short loc_14003959E
0x140039599  mov     eax, 0C000001Ch
0x14003959e  add     rsp, 48h
0x1400395a2  retn
0x1400395a3  mov     rax, cs:__imp_NtDCompositionBeginFrame
0x1400395aa  mov     rcx, [rsp+48h+var_28]
0x1400395af  mov     rdx, [rsp+48h+var_20]
0x1400395b4  mov     r8, [rsp+48h+var_18]
0x1400395b9  mov     r9, [rsp+48h+var_10]
0x1400395be  add     rsp, 48h
0x1400395c2  jmp     rax
```
