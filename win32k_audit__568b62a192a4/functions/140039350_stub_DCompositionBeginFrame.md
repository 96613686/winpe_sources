# _stub_DCompositionBeginFrame

- ea: `0x140039350`
- end: `0x1400393f7`
- name: `_stub_DCompositionBeginFrame`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039350`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039399`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039399`

## string_xrefs

- `0x14003937f`: `NtDCompositionBeginFrame`

## pseudocode

```c
__int64 stub_DCompositionBeginFrame()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionBeginFrame();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionBeginFrame();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039350  sub     rsp, 48h
0x140039354  mov     [rsp+48h+var_28], rcx
0x140039359  mov     [rsp+48h+var_20], rdx
0x14003935e  mov     [rsp+48h+var_18], r8
0x140039363  mov     [rsp+48h+var_10], r9
0x140039368  mov     rcx, 114h
0x14003936f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039376  nop     dword ptr [rax+rax+00h]
0x14003937b  test    al, al
0x14003937d  jz      short loc_1400393D3
0x14003937f  lea     rcx, aNtdcomposition_0; "NtDCompositionBeginFrame"
0x140039386  mov     rdx, 114h
0x14003938d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039394  nop     dword ptr [rax+rax+00h]
0x140039399  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400393a0  nop     dword ptr [rax+rax+00h]
0x1400393a5  test    al, al
0x1400393a7  jz      short loc_1400393D3
0x1400393a9  lea     rcx, W32pServiceTableFilter
0x1400393b0  mov     edx, cs:W32pServiceLimitFilter
0x1400393b6  mov     rax, 114h
0x1400393bd  lea     rcx, [rcx+rdx*4]
0x1400393c1  movsx   eax, byte ptr [rcx+rax]
0x1400393c5  or      eax, eax
0x1400393c7  jle     short loc_1400393CE
0x1400393c9  mov     eax, 0C000001Ch
0x1400393ce  add     rsp, 48h
0x1400393d2  retn
0x1400393d3  mov     rax, cs:__imp_NtDCompositionBeginFrame
0x1400393da  mov     rcx, [rsp+48h+var_28]
0x1400393df  mov     rdx, [rsp+48h+var_20]
0x1400393e4  mov     r8, [rsp+48h+var_18]
0x1400393e9  mov     r9, [rsp+48h+var_10]
0x1400393ee  add     rsp, 48h
0x1400393f2  jmp     rax
```
