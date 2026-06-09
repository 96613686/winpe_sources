# _stub_DCompositionDestroyConnection

- ea: `0x140039ec0`
- end: `0x140039f67`
- name: `_stub_DCompositionDestroyConnection`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039ec0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039f09`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039f09`

## string_xrefs

- `0x140039eef`: `NtDCompositionDestroyConnection`

## pseudocode

```c
__int64 stub_DCompositionDestroyConnection()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionDestroyConnection();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionDestroyConnection();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039ec0  sub     rsp, 48h
0x140039ec4  mov     [rsp+48h+var_28], rcx
0x140039ec9  mov     [rsp+48h+var_20], rdx
0x140039ece  mov     [rsp+48h+var_18], r8
0x140039ed3  mov     [rsp+48h+var_10], r9
0x140039ed8  mov     rcx, 122h
0x140039edf  call    cs:__imp_IsWin32KSyscallFiltered
0x140039ee6  nop     dword ptr [rax+rax+00h]
0x140039eeb  test    al, al
0x140039eed  jz      short loc_140039F43
0x140039eef  lea     rcx, aNtdcomposition_14; "NtDCompositionDestroyConnection"
0x140039ef6  mov     rdx, 122h
0x140039efd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039f04  nop     dword ptr [rax+rax+00h]
0x140039f09  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039f10  nop     dword ptr [rax+rax+00h]
0x140039f15  test    al, al
0x140039f17  jz      short loc_140039F43
0x140039f19  lea     rcx, W32pServiceTableFilter
0x140039f20  mov     edx, cs:W32pServiceLimitFilter
0x140039f26  mov     rax, 122h
0x140039f2d  lea     rcx, [rcx+rdx*4]
0x140039f31  movsx   eax, byte ptr [rcx+rax]
0x140039f35  or      eax, eax
0x140039f37  jle     short loc_140039F3E
0x140039f39  mov     eax, 0C000001Ch
0x140039f3e  add     rsp, 48h
0x140039f42  retn
0x140039f43  mov     rax, cs:__imp_NtDCompositionDestroyConnection
0x140039f4a  mov     rcx, [rsp+48h+var_28]
0x140039f4f  mov     rdx, [rsp+48h+var_20]
0x140039f54  mov     r8, [rsp+48h+var_18]
0x140039f59  mov     r9, [rsp+48h+var_10]
0x140039f5e  add     rsp, 48h
0x140039f62  jmp     rax
```
