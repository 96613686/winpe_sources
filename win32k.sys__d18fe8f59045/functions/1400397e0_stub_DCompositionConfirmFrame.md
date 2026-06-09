# _stub_DCompositionConfirmFrame

- ea: `0x1400397e0`
- end: `0x140039887`
- name: `_stub_DCompositionConfirmFrame`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400397e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039829`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039829`

## string_xrefs

- `0x14003980f`: `NtDCompositionConfirmFrame`

## pseudocode

```c
__int64 stub_DCompositionConfirmFrame()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionConfirmFrame();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionConfirmFrame();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400397e0  sub     rsp, 48h
0x1400397e4  mov     [rsp+48h+var_28], rcx
0x1400397e9  mov     [rsp+48h+var_20], rdx
0x1400397ee  mov     [rsp+48h+var_18], r8
0x1400397f3  mov     [rsp+48h+var_10], r9
0x1400397f8  mov     rcx, 118h
0x1400397ff  call    cs:__imp_IsWin32KSyscallFiltered
0x140039806  nop     dword ptr [rax+rax+00h]
0x14003980b  test    al, al
0x14003980d  jz      short loc_140039863
0x14003980f  lea     rcx, aNtdcomposition_4; "NtDCompositionConfirmFrame"
0x140039816  mov     rdx, 118h
0x14003981d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039824  nop     dword ptr [rax+rax+00h]
0x140039829  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039830  nop     dword ptr [rax+rax+00h]
0x140039835  test    al, al
0x140039837  jz      short loc_140039863
0x140039839  lea     rcx, W32pServiceTableFilter
0x140039840  mov     edx, cs:W32pServiceLimitFilter
0x140039846  mov     rax, 118h
0x14003984d  lea     rcx, [rcx+rdx*4]
0x140039851  movsx   eax, byte ptr [rcx+rax]
0x140039855  or      eax, eax
0x140039857  jle     short loc_14003985E
0x140039859  mov     eax, 0C000001Ch
0x14003985e  add     rsp, 48h
0x140039862  retn
0x140039863  mov     rax, cs:__imp_NtDCompositionConfirmFrame
0x14003986a  mov     rcx, [rsp+48h+var_28]
0x14003986f  mov     rdx, [rsp+48h+var_20]
0x140039874  mov     r8, [rsp+48h+var_18]
0x140039879  mov     r9, [rsp+48h+var_10]
0x14003987e  add     rsp, 48h
0x140039882  jmp     rax
```
