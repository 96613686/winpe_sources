# _stub_NotifyPresentToCompositionSurface

- ea: `0x140053a90`
- end: `0x140053b37`
- name: `_stub_NotifyPresentToCompositionSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053a90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053ad9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053ad9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtNotifyPresentToCompositionSurface` at `0x140053b13`

## string_xrefs

- `0x140053abf`: `NtNotifyPresentToCompositionSurface`

## pseudocode

```c
__int64 __fastcall stub_NotifyPresentToCompositionSurface(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtNotifyPresentToCompositionSurface(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtNotifyPresentToCompositionSurface(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[111] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053a90  sub     rsp, 48h
0x140053a94  mov     [rsp+48h+var_28], rcx
0x140053a99  mov     [rsp+48h+var_20], rdx
0x140053a9e  mov     [rsp+48h+var_18], r8
0x140053aa3  mov     [rsp+48h+var_10], r9
0x140053aa8  mov     rcx, 379h
0x140053aaf  call    cs:__imp_IsWin32KSyscallFiltered
0x140053ab6  nop     dword ptr [rax+rax+00h]
0x140053abb  test    al, al
0x140053abd  jz      short loc_140053B13
0x140053abf  lea     rcx, aNtnotifypresen; "NtNotifyPresentToCompositionSurface"
0x140053ac6  mov     rdx, 379h
0x140053acd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053ad4  nop     dword ptr [rax+rax+00h]
0x140053ad9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053ae0  nop     dword ptr [rax+rax+00h]
0x140053ae5  test    al, al
0x140053ae7  jz      short loc_140053B13
0x140053ae9  lea     rcx, W32pServiceTableFilter
0x140053af0  mov     edx, cs:W32pServiceLimitFilter
0x140053af6  mov     rax, 379h
0x140053afd  lea     rcx, [rcx+rdx*4]
0x140053b01  movsx   eax, byte ptr [rcx+rax]
0x140053b05  or      eax, eax
0x140053b07  jle     short loc_140053B0E
0x140053b09  mov     eax, 0C000001Ch
0x140053b0e  add     rsp, 48h
0x140053b12  retn
0x140053b13  mov     rax, cs:__imp_NtNotifyPresentToCompositionSurface
0x140053b1a  mov     rcx, [rsp+48h+var_28]
0x140053b1f  mov     rdx, [rsp+48h+var_20]
0x140053b24  mov     r8, [rsp+48h+var_18]
0x140053b29  mov     r9, [rsp+48h+var_10]
0x140053b2e  add     rsp, 48h
0x140053b32  jmp     rax
```
