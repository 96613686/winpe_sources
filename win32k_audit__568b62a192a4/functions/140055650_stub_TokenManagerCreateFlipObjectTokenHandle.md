# _stub_TokenManagerCreateFlipObjectTokenHandle

- ea: `0x140055650`
- end: `0x1400556f7`
- name: `_stub_TokenManagerCreateFlipObjectTokenHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055650`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055699`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140055699`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerCreateFlipObjectTokenHandle` at `0x1400556d3`

## string_xrefs

- `0x14005567f`: `NtTokenManagerCreateFlipObjectTokenHandle`

## pseudocode

```c
__int64 __fastcall stub_TokenManagerCreateFlipObjectTokenHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtTokenManagerCreateFlipObjectTokenHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtTokenManagerCreateFlipObjectTokenHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055650  sub     rsp, 48h
0x140055654  mov     [rsp+48h+var_28], rcx
0x140055659  mov     [rsp+48h+var_20], rdx
0x14005565e  mov     [rsp+48h+var_18], r8
0x140055663  mov     [rsp+48h+var_10], r9
0x140055668  mov     rcx, 3A4h
0x14005566f  call    cs:__imp_IsWin32KSyscallFiltered
0x140055676  nop     dword ptr [rax+rax+00h]
0x14005567b  test    al, al
0x14005567d  jz      short loc_1400556D3
0x14005567f  lea     rcx, aNttokenmanager_1; "NtTokenManagerCreateFlipObjectTokenHand"...
0x140055686  mov     rdx, 3A4h
0x14005568d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140055694  nop     dword ptr [rax+rax+00h]
0x140055699  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400556a0  nop     dword ptr [rax+rax+00h]
0x1400556a5  test    al, al
0x1400556a7  jz      short loc_1400556D3
0x1400556a9  lea     rcx, W32pServiceTableFilter
0x1400556b0  mov     edx, cs:W32pServiceLimitFilter
0x1400556b6  mov     rax, 3A4h
0x1400556bd  lea     rcx, [rcx+rdx*4]
0x1400556c1  movsx   eax, byte ptr [rcx+rax]
0x1400556c5  or      eax, eax
0x1400556c7  jle     short loc_1400556CE
0x1400556c9  mov     eax, 0C000001Ch
0x1400556ce  add     rsp, 48h
0x1400556d2  retn
0x1400556d3  mov     rax, cs:__imp_NtTokenManagerCreateFlipObjectTokenHandle
0x1400556da  mov     rcx, [rsp+48h+var_28]
0x1400556df  mov     rdx, [rsp+48h+var_20]
0x1400556e4  mov     r8, [rsp+48h+var_18]
0x1400556e9  mov     r9, [rsp+48h+var_10]
0x1400556ee  add     rsp, 48h
0x1400556f2  jmp     rax
```
