# _stub_OpenCompositionSurfaceDirtyRegion

- ea: `0x140053b40`
- end: `0x140053be7`
- name: `_stub_OpenCompositionSurfaceDirtyRegion`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053b40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053b89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053b89`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtOpenCompositionSurfaceDirtyRegion` at `0x140053bc3`

## string_xrefs

- `0x140053b6f`: `NtOpenCompositionSurfaceDirtyRegion`

## pseudocode

```c
__int64 __fastcall stub_OpenCompositionSurfaceDirtyRegion(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtOpenCompositionSurfaceDirtyRegion(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtOpenCompositionSurfaceDirtyRegion(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[111] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053b40  sub     rsp, 48h
0x140053b44  mov     [rsp+48h+var_28], rcx
0x140053b49  mov     [rsp+48h+var_20], rdx
0x140053b4e  mov     [rsp+48h+var_18], r8
0x140053b53  mov     [rsp+48h+var_10], r9
0x140053b58  mov     rcx, 37Ah
0x140053b5f  call    cs:__imp_IsWin32KSyscallFiltered
0x140053b66  nop     dword ptr [rax+rax+00h]
0x140053b6b  test    al, al
0x140053b6d  jz      short loc_140053BC3
0x140053b6f  lea     rcx, aNtopencomposit; "NtOpenCompositionSurfaceDirtyRegion"
0x140053b76  mov     rdx, 37Ah
0x140053b7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053b84  nop     dword ptr [rax+rax+00h]
0x140053b89  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053b90  nop     dword ptr [rax+rax+00h]
0x140053b95  test    al, al
0x140053b97  jz      short loc_140053BC3
0x140053b99  lea     rcx, W32pServiceTableFilter
0x140053ba0  mov     edx, cs:W32pServiceLimitFilter
0x140053ba6  mov     rax, 37Ah
0x140053bad  lea     rcx, [rcx+rdx*4]
0x140053bb1  movsx   eax, byte ptr [rcx+rax]
0x140053bb5  or      eax, eax
0x140053bb7  jle     short loc_140053BBE
0x140053bb9  mov     eax, 0C000001Ch
0x140053bbe  add     rsp, 48h
0x140053bc2  retn
0x140053bc3  mov     rax, cs:__imp_NtOpenCompositionSurfaceDirtyRegion
0x140053bca  mov     rcx, [rsp+48h+var_28]
0x140053bcf  mov     rdx, [rsp+48h+var_20]
0x140053bd4  mov     r8, [rsp+48h+var_18]
0x140053bd9  mov     r9, [rsp+48h+var_10]
0x140053bde  add     rsp, 48h
0x140053be2  jmp     rax
```
