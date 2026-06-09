# _stub_QueryCompositionSurfaceFrameRate

- ea: `0x140053d90`
- end: `0x140053e37`
- name: `_stub_QueryCompositionSurfaceFrameRate`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053d90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053dd9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053dd9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceFrameRate` at `0x140053e13`

## string_xrefs

- `0x140053dbf`: `NtQueryCompositionSurfaceFrameRate`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceFrameRate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceFrameRate(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceFrameRate(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053d90  sub     rsp, 48h
0x140053d94  mov     [rsp+48h+var_28], rcx
0x140053d99  mov     [rsp+48h+var_20], rdx
0x140053d9e  mov     [rsp+48h+var_18], r8
0x140053da3  mov     [rsp+48h+var_10], r9
0x140053da8  mov     rcx, 380h
0x140053daf  call    cs:__imp_IsWin32KSyscallFiltered
0x140053db6  nop     dword ptr [rax+rax+00h]
0x140053dbb  test    al, al
0x140053dbd  jz      short loc_140053E13
0x140053dbf  lea     rcx, aNtquerycomposi_5; "NtQueryCompositionSurfaceFrameRate"
0x140053dc6  mov     rdx, 380h
0x140053dcd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053dd4  nop     dword ptr [rax+rax+00h]
0x140053dd9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053de0  nop     dword ptr [rax+rax+00h]
0x140053de5  test    al, al
0x140053de7  jz      short loc_140053E13
0x140053de9  lea     rcx, W32pServiceTableFilter
0x140053df0  mov     edx, cs:W32pServiceLimitFilter
0x140053df6  mov     rax, 380h
0x140053dfd  lea     rcx, [rcx+rdx*4]
0x140053e01  movsx   eax, byte ptr [rcx+rax]
0x140053e05  or      eax, eax
0x140053e07  jle     short loc_140053E0E
0x140053e09  mov     eax, 0C000001Ch
0x140053e0e  add     rsp, 48h
0x140053e12  retn
0x140053e13  mov     rax, cs:__imp_NtQueryCompositionSurfaceFrameRate
0x140053e1a  mov     rcx, [rsp+48h+var_28]
0x140053e1f  mov     rdx, [rsp+48h+var_20]
0x140053e24  mov     r8, [rsp+48h+var_18]
0x140053e29  mov     r9, [rsp+48h+var_10]
0x140053e2e  add     rsp, 48h
0x140053e32  jmp     rax
```
