# _stub_QueryCompositionSurfaceRenderingRealization

- ea: `0x140053ef0`
- end: `0x140053f97`
- name: `_stub_QueryCompositionSurfaceRenderingRealization`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053ef0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053f39`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053f39`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceRenderingRealization` at `0x140053f73`

## string_xrefs

- `0x140053f1f`: `NtQueryCompositionSurfaceRenderingRealization`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceRenderingRealization(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceRenderingRealization(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceRenderingRealization(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053ef0  sub     rsp, 48h
0x140053ef4  mov     [rsp+48h+var_28], rcx
0x140053ef9  mov     [rsp+48h+var_20], rdx
0x140053efe  mov     [rsp+48h+var_18], r8
0x140053f03  mov     [rsp+48h+var_10], r9
0x140053f08  mov     rcx, 382h
0x140053f0f  call    cs:__imp_IsWin32KSyscallFiltered
0x140053f16  nop     dword ptr [rax+rax+00h]
0x140053f1b  test    al, al
0x140053f1d  jz      short loc_140053F73
0x140053f1f  lea     rcx, aNtquerycomposi_7; "NtQueryCompositionSurfaceRenderingReali"...
0x140053f26  mov     rdx, 382h
0x140053f2d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053f34  nop     dword ptr [rax+rax+00h]
0x140053f39  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053f40  nop     dword ptr [rax+rax+00h]
0x140053f45  test    al, al
0x140053f47  jz      short loc_140053F73
0x140053f49  lea     rcx, W32pServiceTableFilter
0x140053f50  mov     edx, cs:W32pServiceLimitFilter
0x140053f56  mov     rax, 382h
0x140053f5d  lea     rcx, [rcx+rdx*4]
0x140053f61  movsx   eax, byte ptr [rcx+rax]
0x140053f65  or      eax, eax
0x140053f67  jle     short loc_140053F6E
0x140053f69  mov     eax, 0C000001Ch
0x140053f6e  add     rsp, 48h
0x140053f72  retn
0x140053f73  mov     rax, cs:__imp_NtQueryCompositionSurfaceRenderingRealization
0x140053f7a  mov     rcx, [rsp+48h+var_28]
0x140053f7f  mov     rdx, [rsp+48h+var_20]
0x140053f84  mov     r8, [rsp+48h+var_18]
0x140053f89  mov     r9, [rsp+48h+var_10]
0x140053f8e  add     rsp, 48h
0x140053f92  jmp     rax
```
