# _stub_GdiComputeXformCoefficients

- ea: `0x140033170`
- end: `0x140033217`
- name: `_stub_GdiComputeXformCoefficients`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140033170`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400331b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400331b9`

## string_xrefs

- `0x14003319f`: `NtGdiComputeXformCoefficients`

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
0x140033170  sub     rsp, 48h
0x140033174  mov     [rsp+48h+var_28], rcx
0x140033179  mov     [rsp+48h+var_20], rdx
0x14003317e  mov     [rsp+48h+var_18], r8
0x140033183  mov     [rsp+48h+var_10], r9
0x140033188  mov     rcx, 83h
0x14003318f  call    cs:__imp_IsWin32KSyscallFiltered
0x140033196  nop     dword ptr [rax+rax+00h]
0x14003319b  test    al, al
0x14003319d  jz      short loc_1400331F3
0x14003319f  lea     rcx, aNtgdicomputexf; "NtGdiComputeXformCoefficients"
0x1400331a6  mov     rdx, 83h
0x1400331ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400331b4  nop     dword ptr [rax+rax+00h]
0x1400331b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400331c0  nop     dword ptr [rax+rax+00h]
0x1400331c5  test    al, al
0x1400331c7  jz      short loc_1400331F3
0x1400331c9  lea     rcx, W32pServiceTableFilter
0x1400331d0  mov     edx, cs:W32pServiceLimitFilter
0x1400331d6  mov     rax, 83h
0x1400331dd  lea     rcx, [rcx+rdx*4]
0x1400331e1  movsx   eax, byte ptr [rcx+rax]
0x1400331e5  or      eax, eax
0x1400331e7  jle     short loc_1400331EE
0x1400331e9  mov     eax, 0C000001Ch
0x1400331ee  add     rsp, 48h
0x1400331f2  retn
0x1400331f3  mov     rax, cs:__imp_NtGdiComputeXformCoefficients
0x1400331fa  mov     rcx, [rsp+48h+var_28]
0x1400331ff  mov     rdx, [rsp+48h+var_20]
0x140033204  mov     r8, [rsp+48h+var_18]
0x140033209  mov     r9, [rsp+48h+var_10]
0x14003320e  add     rsp, 48h
0x140033212  jmp     rax
```
