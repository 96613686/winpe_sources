# _stub_DCompositionCreateBufferCollection

- ea: `0x1400399f0`
- end: `0x140039a97`
- name: `_stub_DCompositionCreateBufferCollection`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400399f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039a39`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039a39`

## string_xrefs

- `0x140039a1f`: `NtDCompositionCreateBufferCollection`

## pseudocode

```c
__int64 stub_DCompositionCreateBufferCollection()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateBufferCollection();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateBufferCollection();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400399f0  sub     rsp, 48h
0x1400399f4  mov     [rsp+48h+var_28], rcx
0x1400399f9  mov     [rsp+48h+var_20], rdx
0x1400399fe  mov     [rsp+48h+var_18], r8
0x140039a03  mov     [rsp+48h+var_10], r9
0x140039a08  mov     rcx, 11Bh
0x140039a0f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039a16  nop     dword ptr [rax+rax+00h]
0x140039a1b  test    al, al
0x140039a1d  jz      short loc_140039A73
0x140039a1f  lea     rcx, aNtdcomposition_7; "NtDCompositionCreateBufferCollection"
0x140039a26  mov     rdx, 11Bh
0x140039a2d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039a34  nop     dword ptr [rax+rax+00h]
0x140039a39  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039a40  nop     dword ptr [rax+rax+00h]
0x140039a45  test    al, al
0x140039a47  jz      short loc_140039A73
0x140039a49  lea     rcx, W32pServiceTableFilter
0x140039a50  mov     edx, cs:W32pServiceLimitFilter
0x140039a56  mov     rax, 11Bh
0x140039a5d  lea     rcx, [rcx+rdx*4]
0x140039a61  movsx   eax, byte ptr [rcx+rax]
0x140039a65  or      eax, eax
0x140039a67  jle     short loc_140039A6E
0x140039a69  mov     eax, 0C000001Ch
0x140039a6e  add     rsp, 48h
0x140039a72  retn
0x140039a73  mov     rax, cs:__imp_NtDCompositionCreateBufferCollection
0x140039a7a  mov     rcx, [rsp+48h+var_28]
0x140039a7f  mov     rdx, [rsp+48h+var_20]
0x140039a84  mov     r8, [rsp+48h+var_18]
0x140039a89  mov     r9, [rsp+48h+var_10]
0x140039a8e  add     rsp, 48h
0x140039a92  jmp     rax
```
