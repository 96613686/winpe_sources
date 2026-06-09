# _stub_DCompositionCommitChannel

- ea: `0x1400394b0`
- end: `0x140039557`
- name: `_stub_DCompositionCommitChannel`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400394b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400394f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400394f9`

## string_xrefs

- `0x1400394df`: `NtDCompositionCommitChannel`

## pseudocode

```c
__int64 __fastcall stub_DCompositionCommitChannel(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
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
0x1400394b0  sub     rsp, 48h
0x1400394b4  mov     [rsp+48h+var_28], rcx
0x1400394b9  mov     [rsp+48h+var_20], rdx
0x1400394be  mov     [rsp+48h+var_18], r8
0x1400394c3  mov     [rsp+48h+var_10], r9
0x1400394c8  mov     rcx, 116h
0x1400394cf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400394d6  nop     dword ptr [rax+rax+00h]
0x1400394db  test    al, al
0x1400394dd  jz      short loc_140039533
0x1400394df  lea     rcx, aNtdcomposition_2; "NtDCompositionCommitChannel"
0x1400394e6  mov     rdx, 116h
0x1400394ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400394f4  nop     dword ptr [rax+rax+00h]
0x1400394f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039500  nop     dword ptr [rax+rax+00h]
0x140039505  test    al, al
0x140039507  jz      short loc_140039533
0x140039509  lea     rcx, W32pServiceTableFilter
0x140039510  mov     edx, cs:W32pServiceLimitFilter
0x140039516  mov     rax, 116h
0x14003951d  lea     rcx, [rcx+rdx*4]
0x140039521  movsx   eax, byte ptr [rcx+rax]
0x140039525  or      eax, eax
0x140039527  jle     short loc_14003952E
0x140039529  mov     eax, 0C000001Ch
0x14003952e  add     rsp, 48h
0x140039532  retn
0x140039533  mov     rax, cs:__imp_NtDCompositionCommitChannel
0x14003953a  mov     rcx, [rsp+48h+var_28]
0x14003953f  mov     rdx, [rsp+48h+var_20]
0x140039544  mov     r8, [rsp+48h+var_18]
0x140039549  mov     r9, [rsp+48h+var_10]
0x14003954e  add     rsp, 48h
0x140039552  jmp     rax
```
