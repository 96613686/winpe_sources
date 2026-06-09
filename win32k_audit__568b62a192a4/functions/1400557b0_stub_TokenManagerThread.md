# _stub_TokenManagerThread

- ea: `0x1400557b0`
- end: `0x140055857`
- name: `_stub_TokenManagerThread`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400557b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400557f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400557f9`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerThread` at `0x140055833`

## string_xrefs

- `0x1400557df`: `NtTokenManagerThread`

## pseudocode

```c
__int64 __fastcall stub_TokenManagerThread(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtTokenManagerThread(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtTokenManagerThread(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400557b0  sub     rsp, 48h
0x1400557b4  mov     [rsp+48h+var_28], rcx
0x1400557b9  mov     [rsp+48h+var_20], rdx
0x1400557be  mov     [rsp+48h+var_18], r8
0x1400557c3  mov     [rsp+48h+var_10], r9
0x1400557c8  mov     rcx, 3A6h
0x1400557cf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400557d6  nop     dword ptr [rax+rax+00h]
0x1400557db  test    al, al
0x1400557dd  jz      short loc_140055833
0x1400557df  lea     rcx, aNttokenmanager_3; "NtTokenManagerThread"
0x1400557e6  mov     rdx, 3A6h
0x1400557ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400557f4  nop     dword ptr [rax+rax+00h]
0x1400557f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140055800  nop     dword ptr [rax+rax+00h]
0x140055805  test    al, al
0x140055807  jz      short loc_140055833
0x140055809  lea     rcx, W32pServiceTableFilter
0x140055810  mov     edx, cs:W32pServiceLimitFilter
0x140055816  mov     rax, 3A6h
0x14005581d  lea     rcx, [rcx+rdx*4]
0x140055821  movsx   eax, byte ptr [rcx+rax]
0x140055825  or      eax, eax
0x140055827  jle     short loc_14005582E
0x140055829  mov     eax, 0C000001Ch
0x14005582e  add     rsp, 48h
0x140055832  retn
0x140055833  mov     rax, cs:__imp_NtTokenManagerThread
0x14005583a  mov     rcx, [rsp+48h+var_28]
0x14005583f  mov     rdx, [rsp+48h+var_20]
0x140055844  mov     r8, [rsp+48h+var_18]
0x140055849  mov     r9, [rsp+48h+var_10]
0x14005584e  add     rsp, 48h
0x140055852  jmp     rax
```
