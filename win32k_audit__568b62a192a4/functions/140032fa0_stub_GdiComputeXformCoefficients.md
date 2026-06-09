# _stub_GdiComputeXformCoefficients

- ea: `0x140032fa0`
- end: `0x140033047`
- name: `_stub_GdiComputeXformCoefficients`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140032fa0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140032fe9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140032fe9`

## string_xrefs

- `0x140032fcf`: `NtGdiComputeXformCoefficients`

## pseudocode

```c
__int64 stub_GdiComputeXformCoefficients()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiComputeXformCoefficients();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiComputeXformCoefficients();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[16] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140032fa0  sub     rsp, 48h
0x140032fa4  mov     [rsp+48h+var_28], rcx
0x140032fa9  mov     [rsp+48h+var_20], rdx
0x140032fae  mov     [rsp+48h+var_18], r8
0x140032fb3  mov     [rsp+48h+var_10], r9
0x140032fb8  mov     rcx, 83h
0x140032fbf  call    cs:__imp_IsWin32KSyscallFiltered
0x140032fc6  nop     dword ptr [rax+rax+00h]
0x140032fcb  test    al, al
0x140032fcd  jz      short loc_140033023
0x140032fcf  lea     rcx, aNtgdicomputexf; "NtGdiComputeXformCoefficients"
0x140032fd6  mov     rdx, 83h
0x140032fdd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140032fe4  nop     dword ptr [rax+rax+00h]
0x140032fe9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140032ff0  nop     dword ptr [rax+rax+00h]
0x140032ff5  test    al, al
0x140032ff7  jz      short loc_140033023
0x140032ff9  lea     rcx, W32pServiceTableFilter
0x140033000  mov     edx, cs:W32pServiceLimitFilter
0x140033006  mov     rax, 83h
0x14003300d  lea     rcx, [rcx+rdx*4]
0x140033011  movsx   eax, byte ptr [rcx+rax]
0x140033015  or      eax, eax
0x140033017  jle     short loc_14003301E
0x140033019  mov     eax, 0C000001Ch
0x14003301e  add     rsp, 48h
0x140033022  retn
0x140033023  mov     rax, cs:__imp_NtGdiComputeXformCoefficients
0x14003302a  mov     rcx, [rsp+48h+var_28]
0x14003302f  mov     rdx, [rsp+48h+var_20]
0x140033034  mov     r8, [rsp+48h+var_18]
0x140033039  mov     r9, [rsp+48h+var_10]
0x14003303e  add     rsp, 48h
0x140033042  jmp     rax
```
