# _stub_NotifyPresentToCompositionSurface

- ea: `0x1400536b0`
- end: `0x140053757`
- name: `_stub_NotifyPresentToCompositionSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400536b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400536f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400536f9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtNotifyPresentToCompositionSurface` at `0x140053733`

## string_xrefs

- `0x1400536df`: `NtNotifyPresentToCompositionSurface`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[110] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400536b0  sub     rsp, 48h
0x1400536b4  mov     [rsp+48h+var_28], rcx
0x1400536b9  mov     [rsp+48h+var_20], rdx
0x1400536be  mov     [rsp+48h+var_18], r8
0x1400536c3  mov     [rsp+48h+var_10], r9
0x1400536c8  mov     rcx, 376h
0x1400536cf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400536d6  nop     dword ptr [rax+rax+00h]
0x1400536db  test    al, al
0x1400536dd  jz      short loc_140053733
0x1400536df  lea     rcx, aNtnotifypresen; "NtNotifyPresentToCompositionSurface"
0x1400536e6  mov     rdx, 376h
0x1400536ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400536f4  nop     dword ptr [rax+rax+00h]
0x1400536f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053700  nop     dword ptr [rax+rax+00h]
0x140053705  test    al, al
0x140053707  jz      short loc_140053733
0x140053709  lea     rcx, W32pServiceTableFilter
0x140053710  mov     edx, cs:W32pServiceLimitFilter
0x140053716  mov     rax, 376h
0x14005371d  lea     rcx, [rcx+rdx*4]
0x140053721  movsx   eax, byte ptr [rcx+rax]
0x140053725  or      eax, eax
0x140053727  jle     short loc_14005372E
0x140053729  mov     eax, 0C000001Ch
0x14005372e  add     rsp, 48h
0x140053732  retn
0x140053733  mov     rax, cs:__imp_NtNotifyPresentToCompositionSurface
0x14005373a  mov     rcx, [rsp+48h+var_28]
0x14005373f  mov     rdx, [rsp+48h+var_20]
0x140053744  mov     r8, [rsp+48h+var_18]
0x140053749  mov     r9, [rsp+48h+var_10]
0x14005374e  add     rsp, 48h
0x140053752  jmp     rax
```
