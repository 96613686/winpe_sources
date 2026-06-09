# _stub_DCompositionNotifySuperWetInkWork

- ea: `0x14003a910`
- end: `0x14003a9b7`
- name: `_stub_DCompositionNotifySuperWetInkWork`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a910`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a959`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a959`

## string_xrefs

- `0x14003a93f`: `NtDCompositionNotifySuperWetInkWork`

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
0x14003a910  sub     rsp, 48h
0x14003a914  mov     [rsp+48h+var_28], rcx
0x14003a919  mov     [rsp+48h+var_20], rdx
0x14003a91e  mov     [rsp+48h+var_18], r8
0x14003a923  mov     [rsp+48h+var_10], r9
0x14003a928  mov     rcx, 131h
0x14003a92f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a936  nop     dword ptr [rax+rax+00h]
0x14003a93b  test    al, al
0x14003a93d  jz      short loc_14003A993
0x14003a93f  lea     rcx, aNtdcomposition_29; "NtDCompositionNotifySuperWetInkWork"
0x14003a946  mov     rdx, 131h
0x14003a94d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a954  nop     dword ptr [rax+rax+00h]
0x14003a959  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a960  nop     dword ptr [rax+rax+00h]
0x14003a965  test    al, al
0x14003a967  jz      short loc_14003A993
0x14003a969  lea     rcx, W32pServiceTableFilter
0x14003a970  mov     edx, cs:W32pServiceLimitFilter
0x14003a976  mov     rax, 131h
0x14003a97d  lea     rcx, [rcx+rdx*4]
0x14003a981  movsx   eax, byte ptr [rcx+rax]
0x14003a985  or      eax, eax
0x14003a987  jle     short loc_14003A98E
0x14003a989  mov     eax, 0C000001Ch
0x14003a98e  add     rsp, 48h
0x14003a992  retn
0x14003a993  mov     rax, cs:__imp_NtDCompositionNotifySuperWetInkWork
0x14003a99a  mov     rcx, [rsp+48h+var_28]
0x14003a99f  mov     rdx, [rsp+48h+var_20]
0x14003a9a4  mov     r8, [rsp+48h+var_18]
0x14003a9a9  mov     r9, [rsp+48h+var_10]
0x14003a9ae  add     rsp, 48h
0x14003a9b2  jmp     rax
```
