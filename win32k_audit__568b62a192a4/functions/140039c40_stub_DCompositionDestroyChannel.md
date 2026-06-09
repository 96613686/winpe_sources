# _stub_DCompositionDestroyChannel

- ea: `0x140039c40`
- end: `0x140039ce7`
- name: `_stub_DCompositionDestroyChannel`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039c40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039c89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039c89`

## string_xrefs

- `0x140039c6f`: `NtDCompositionDestroyChannel`

## pseudocode

```c
__int64 stub_DCompositionDestroyChannel()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionDestroyChannel();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionDestroyChannel();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039c40  sub     rsp, 48h
0x140039c44  mov     [rsp+48h+var_28], rcx
0x140039c49  mov     [rsp+48h+var_20], rdx
0x140039c4e  mov     [rsp+48h+var_18], r8
0x140039c53  mov     [rsp+48h+var_10], r9
0x140039c58  mov     rcx, 121h
0x140039c5f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039c66  nop     dword ptr [rax+rax+00h]
0x140039c6b  test    al, al
0x140039c6d  jz      short loc_140039CC3
0x140039c6f  lea     rcx, aNtdcomposition_13; "NtDCompositionDestroyChannel"
0x140039c76  mov     rdx, 121h
0x140039c7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039c84  nop     dword ptr [rax+rax+00h]
0x140039c89  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039c90  nop     dword ptr [rax+rax+00h]
0x140039c95  test    al, al
0x140039c97  jz      short loc_140039CC3
0x140039c99  lea     rcx, W32pServiceTableFilter
0x140039ca0  mov     edx, cs:W32pServiceLimitFilter
0x140039ca6  mov     rax, 121h
0x140039cad  lea     rcx, [rcx+rdx*4]
0x140039cb1  movsx   eax, byte ptr [rcx+rax]
0x140039cb5  or      eax, eax
0x140039cb7  jle     short loc_140039CBE
0x140039cb9  mov     eax, 0C000001Ch
0x140039cbe  add     rsp, 48h
0x140039cc2  retn
0x140039cc3  mov     rax, cs:__imp_NtDCompositionDestroyChannel
0x140039cca  mov     rcx, [rsp+48h+var_28]
0x140039ccf  mov     rdx, [rsp+48h+var_20]
0x140039cd4  mov     r8, [rsp+48h+var_18]
0x140039cd9  mov     r9, [rsp+48h+var_10]
0x140039cde  add     rsp, 48h
0x140039ce2  jmp     rax
```
