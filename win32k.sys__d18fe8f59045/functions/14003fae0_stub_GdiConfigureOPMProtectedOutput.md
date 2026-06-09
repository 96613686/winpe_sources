# _stub_GdiConfigureOPMProtectedOutput

- ea: `0x14003fae0`
- end: `0x14003fb87`
- name: `_stub_GdiConfigureOPMProtectedOutput`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003fae0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003fb29`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003fb29`

## string_xrefs

- `0x14003fb0f`: `NtGdiConfigureOPMProtectedOutput`

## pseudocode

```c
__int64 stub_GdiConfigureOPMProtectedOutput()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiConfigureOPMProtectedOutput();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiConfigureOPMProtectedOutput();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[53] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003fae0  sub     rsp, 48h
0x14003fae4  mov     [rsp+48h+var_28], rcx
0x14003fae9  mov     [rsp+48h+var_20], rdx
0x14003faee  mov     [rsp+48h+var_18], r8
0x14003faf3  mov     [rsp+48h+var_10], r9
0x14003faf8  mov     rcx, 1A8h
0x14003faff  call    cs:__imp_IsWin32KSyscallFiltered
0x14003fb06  nop     dword ptr [rax+rax+00h]
0x14003fb0b  test    al, al
0x14003fb0d  jz      short loc_14003FB63
0x14003fb0f  lea     rcx, aNtgdiconfigure; "NtGdiConfigureOPMProtectedOutput"
0x14003fb16  mov     rdx, 1A8h
0x14003fb1d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003fb24  nop     dword ptr [rax+rax+00h]
0x14003fb29  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003fb30  nop     dword ptr [rax+rax+00h]
0x14003fb35  test    al, al
0x14003fb37  jz      short loc_14003FB63
0x14003fb39  lea     rcx, W32pServiceTableFilter
0x14003fb40  mov     edx, cs:W32pServiceLimitFilter
0x14003fb46  mov     rax, 1A8h
0x14003fb4d  lea     rcx, [rcx+rdx*4]
0x14003fb51  movsx   eax, byte ptr [rcx+rax]
0x14003fb55  or      eax, eax
0x14003fb57  jle     short loc_14003FB5E
0x14003fb59  mov     eax, 0C000001Ch
0x14003fb5e  add     rsp, 48h
0x14003fb62  retn
0x14003fb63  mov     rax, cs:__imp_NtGdiConfigureOPMProtectedOutput
0x14003fb6a  mov     rcx, [rsp+48h+var_28]
0x14003fb6f  mov     rdx, [rsp+48h+var_20]
0x14003fb74  mov     r8, [rsp+48h+var_18]
0x14003fb79  mov     r9, [rsp+48h+var_10]
0x14003fb7e  add     rsp, 48h
0x14003fb82  jmp     rax
```
