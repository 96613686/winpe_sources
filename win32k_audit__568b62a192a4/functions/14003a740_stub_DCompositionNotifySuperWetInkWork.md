# _stub_DCompositionNotifySuperWetInkWork

- ea: `0x14003a740`
- end: `0x14003a7e7`
- name: `_stub_DCompositionNotifySuperWetInkWork`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a740`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a789`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a789`

## string_xrefs

- `0x14003a76f`: `NtDCompositionNotifySuperWetInkWork`

## pseudocode

```c
__int64 stub_DCompositionNotifySuperWetInkWork()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionNotifySuperWetInkWork();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionNotifySuperWetInkWork();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a740  sub     rsp, 48h
0x14003a744  mov     [rsp+48h+var_28], rcx
0x14003a749  mov     [rsp+48h+var_20], rdx
0x14003a74e  mov     [rsp+48h+var_18], r8
0x14003a753  mov     [rsp+48h+var_10], r9
0x14003a758  mov     rcx, 131h
0x14003a75f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a766  nop     dword ptr [rax+rax+00h]
0x14003a76b  test    al, al
0x14003a76d  jz      short loc_14003A7C3
0x14003a76f  lea     rcx, aNtdcomposition_29; "NtDCompositionNotifySuperWetInkWork"
0x14003a776  mov     rdx, 131h
0x14003a77d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a784  nop     dword ptr [rax+rax+00h]
0x14003a789  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a790  nop     dword ptr [rax+rax+00h]
0x14003a795  test    al, al
0x14003a797  jz      short loc_14003A7C3
0x14003a799  lea     rcx, W32pServiceTableFilter
0x14003a7a0  mov     edx, cs:W32pServiceLimitFilter
0x14003a7a6  mov     rax, 131h
0x14003a7ad  lea     rcx, [rcx+rdx*4]
0x14003a7b1  movsx   eax, byte ptr [rcx+rax]
0x14003a7b5  or      eax, eax
0x14003a7b7  jle     short loc_14003A7BE
0x14003a7b9  mov     eax, 0C000001Ch
0x14003a7be  add     rsp, 48h
0x14003a7c2  retn
0x14003a7c3  mov     rax, cs:__imp_NtDCompositionNotifySuperWetInkWork
0x14003a7ca  mov     rcx, [rsp+48h+var_28]
0x14003a7cf  mov     rdx, [rsp+48h+var_20]
0x14003a7d4  mov     r8, [rsp+48h+var_18]
0x14003a7d9  mov     r9, [rsp+48h+var_10]
0x14003a7de  add     rsp, 48h
0x14003a7e2  jmp     rax
```
