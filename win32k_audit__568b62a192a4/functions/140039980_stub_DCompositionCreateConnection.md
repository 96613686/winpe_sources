# _stub_DCompositionCreateConnection

- ea: `0x140039980`
- end: `0x140039a27`
- name: `_stub_DCompositionCreateConnection`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039980`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400399c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400399c9`

## string_xrefs

- `0x1400399af`: `NtDCompositionCreateConnection`

## pseudocode

```c
__int64 stub_DCompositionCreateConnection()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateConnection();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateConnection();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039980  sub     rsp, 48h
0x140039984  mov     [rsp+48h+var_28], rcx
0x140039989  mov     [rsp+48h+var_20], rdx
0x14003998e  mov     [rsp+48h+var_18], r8
0x140039993  mov     [rsp+48h+var_10], r9
0x140039998  mov     rcx, 11Dh
0x14003999f  call    cs:__imp_IsWin32KSyscallFiltered
0x1400399a6  nop     dword ptr [rax+rax+00h]
0x1400399ab  test    al, al
0x1400399ad  jz      short loc_140039A03
0x1400399af  lea     rcx, aNtdcomposition_9; "NtDCompositionCreateConnection"
0x1400399b6  mov     rdx, 11Dh
0x1400399bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400399c4  nop     dword ptr [rax+rax+00h]
0x1400399c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400399d0  nop     dword ptr [rax+rax+00h]
0x1400399d5  test    al, al
0x1400399d7  jz      short loc_140039A03
0x1400399d9  lea     rcx, W32pServiceTableFilter
0x1400399e0  mov     edx, cs:W32pServiceLimitFilter
0x1400399e6  mov     rax, 11Dh
0x1400399ed  lea     rcx, [rcx+rdx*4]
0x1400399f1  movsx   eax, byte ptr [rcx+rax]
0x1400399f5  or      eax, eax
0x1400399f7  jle     short loc_1400399FE
0x1400399f9  mov     eax, 0C000001Ch
0x1400399fe  add     rsp, 48h
0x140039a02  retn
0x140039a03  mov     rax, cs:__imp_NtDCompositionCreateConnection
0x140039a0a  mov     rcx, [rsp+48h+var_28]
0x140039a0f  mov     rdx, [rsp+48h+var_20]
0x140039a14  mov     r8, [rsp+48h+var_18]
0x140039a19  mov     r9, [rsp+48h+var_10]
0x140039a1e  add     rsp, 48h
0x140039a22  jmp     rax
```
