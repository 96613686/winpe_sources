# _stub_BindCompositionSurface

- ea: `0x140038e40`
- end: `0x140038ee7`
- name: `_stub_BindCompositionSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038e40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038e89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038e89`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtBindCompositionSurface` at `0x140038ec3`

## string_xrefs

- `0x140038e6f`: `NtBindCompositionSurface`

## pseudocode

```c
__int64 __fastcall stub_BindCompositionSurface(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtBindCompositionSurface(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtBindCompositionSurface(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140038e40  sub     rsp, 48h
0x140038e44  mov     [rsp+48h+var_28], rcx
0x140038e49  mov     [rsp+48h+var_20], rdx
0x140038e4e  mov     [rsp+48h+var_18], r8
0x140038e53  mov     [rsp+48h+var_10], r9
0x140038e58  mov     rcx, 10Ah
0x140038e5f  call    cs:__imp_IsWin32KSyscallFiltered
0x140038e66  nop     dword ptr [rax+rax+00h]
0x140038e6b  test    al, al
0x140038e6d  jz      short loc_140038EC3
0x140038e6f  lea     rcx, aNtbindcomposit; "NtBindCompositionSurface"
0x140038e76  mov     rdx, 10Ah
0x140038e7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038e84  nop     dword ptr [rax+rax+00h]
0x140038e89  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038e90  nop     dword ptr [rax+rax+00h]
0x140038e95  test    al, al
0x140038e97  jz      short loc_140038EC3
0x140038e99  lea     rcx, W32pServiceTableFilter
0x140038ea0  mov     edx, cs:W32pServiceLimitFilter
0x140038ea6  mov     rax, 10Ah
0x140038ead  lea     rcx, [rcx+rdx*4]
0x140038eb1  movsx   eax, byte ptr [rcx+rax]
0x140038eb5  or      eax, eax
0x140038eb7  jle     short loc_140038EBE
0x140038eb9  mov     eax, 0C000001Ch
0x140038ebe  add     rsp, 48h
0x140038ec2  retn
0x140038ec3  mov     rax, cs:__imp_NtBindCompositionSurface
0x140038eca  mov     rcx, [rsp+48h+var_28]
0x140038ecf  mov     rdx, [rsp+48h+var_20]
0x140038ed4  mov     r8, [rsp+48h+var_18]
0x140038ed9  mov     r9, [rsp+48h+var_10]
0x140038ede  add     rsp, 48h
0x140038ee2  jmp     rax
```
