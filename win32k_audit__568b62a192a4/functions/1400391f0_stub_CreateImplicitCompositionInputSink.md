# _stub_CreateImplicitCompositionInputSink

- ea: `0x1400391f0`
- end: `0x140039297`
- name: `_stub_CreateImplicitCompositionInputSink`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400391f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039239`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039239`

## string_xrefs

- `0x14003921f`: `NtCreateImplicitCompositionInputSink`

## pseudocode

```c
__int64 stub_CreateImplicitCompositionInputSink()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtCreateImplicitCompositionInputSink();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtCreateImplicitCompositionInputSink();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400391f0  sub     rsp, 48h
0x1400391f4  mov     [rsp+48h+var_28], rcx
0x1400391f9  mov     [rsp+48h+var_20], rdx
0x1400391fe  mov     [rsp+48h+var_18], r8
0x140039203  mov     [rsp+48h+var_10], r9
0x140039208  mov     rcx, 112h
0x14003920f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039216  nop     dword ptr [rax+rax+00h]
0x14003921b  test    al, al
0x14003921d  jz      short loc_140039273
0x14003921f  lea     rcx, aNtcreateimplic; "NtCreateImplicitCompositionInputSink"
0x140039226  mov     rdx, 112h
0x14003922d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039234  nop     dword ptr [rax+rax+00h]
0x140039239  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039240  nop     dword ptr [rax+rax+00h]
0x140039245  test    al, al
0x140039247  jz      short loc_140039273
0x140039249  lea     rcx, W32pServiceTableFilter
0x140039250  mov     edx, cs:W32pServiceLimitFilter
0x140039256  mov     rax, 112h
0x14003925d  lea     rcx, [rcx+rdx*4]
0x140039261  movsx   eax, byte ptr [rcx+rax]
0x140039265  or      eax, eax
0x140039267  jle     short loc_14003926E
0x140039269  mov     eax, 0C000001Ch
0x14003926e  add     rsp, 48h
0x140039272  retn
0x140039273  mov     rax, cs:__imp_NtCreateImplicitCompositionInputSink
0x14003927a  mov     rcx, [rsp+48h+var_28]
0x14003927f  mov     rdx, [rsp+48h+var_20]
0x140039284  mov     r8, [rsp+48h+var_18]
0x140039289  mov     r9, [rsp+48h+var_10]
0x14003928e  add     rsp, 48h
0x140039292  jmp     rax
```
