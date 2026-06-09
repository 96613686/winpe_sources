# _stub_DCompositionCommitChannel

- ea: `0x140039680`
- end: `0x140039727`
- name: `_stub_DCompositionCommitChannel`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039680`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400396c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400396c9`

## string_xrefs

- `0x1400396af`: `NtDCompositionCommitChannel`

## pseudocode

```c
__int64 __fastcall stub_DCompositionCommitChannel(int a1, int a2, int a3, int a4, __int64 a5, __int64 a6)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCommitChannel(a1, a2, a3, a4, a5, a6);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCommitChannel(a1, a2, a3, a4, a5, a6);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039680  sub     rsp, 48h
0x140039684  mov     [rsp+48h+var_28], rcx
0x140039689  mov     [rsp+48h+var_20], rdx
0x14003968e  mov     [rsp+48h+var_18], r8
0x140039693  mov     [rsp+48h+var_10], r9
0x140039698  mov     rcx, 116h
0x14003969f  call    cs:__imp_IsWin32KSyscallFiltered
0x1400396a6  nop     dword ptr [rax+rax+00h]
0x1400396ab  test    al, al
0x1400396ad  jz      short loc_140039703
0x1400396af  lea     rcx, aNtdcomposition_2; "NtDCompositionCommitChannel"
0x1400396b6  mov     rdx, 116h
0x1400396bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400396c4  nop     dword ptr [rax+rax+00h]
0x1400396c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400396d0  nop     dword ptr [rax+rax+00h]
0x1400396d5  test    al, al
0x1400396d7  jz      short loc_140039703
0x1400396d9  lea     rcx, W32pServiceTableFilter
0x1400396e0  mov     edx, cs:W32pServiceLimitFilter
0x1400396e6  mov     rax, 116h
0x1400396ed  lea     rcx, [rcx+rdx*4]
0x1400396f1  movsx   eax, byte ptr [rcx+rax]
0x1400396f5  or      eax, eax
0x1400396f7  jle     short loc_1400396FE
0x1400396f9  mov     eax, 0C000001Ch
0x1400396fe  add     rsp, 48h
0x140039702  retn
0x140039703  mov     rax, cs:__imp_NtDCompositionCommitChannel
0x14003970a  mov     rcx, [rsp+48h+var_28]
0x14003970f  mov     rdx, [rsp+48h+var_20]
0x140039714  mov     r8, [rsp+48h+var_18]
0x140039719  mov     r9, [rsp+48h+var_10]
0x14003971e  add     rsp, 48h
0x140039722  jmp     rax
```
