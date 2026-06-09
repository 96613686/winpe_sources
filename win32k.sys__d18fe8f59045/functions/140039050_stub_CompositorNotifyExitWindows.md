# _stub_CompositorNotifyExitWindows

- ea: `0x140039050`
- end: `0x1400390f7`
- name: `_stub_CompositorNotifyExitWindows`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039050`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039099`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039099`

## string_xrefs

- `0x14003907f`: `NtCompositorNotifyExitWindows`

## pseudocode

```c
__int64 stub_CompositorNotifyExitWindows()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtCompositorNotifyExitWindows();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtCompositorNotifyExitWindows();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039050  sub     rsp, 48h
0x140039054  mov     [rsp+48h+var_28], rcx
0x140039059  mov     [rsp+48h+var_20], rdx
0x14003905e  mov     [rsp+48h+var_18], r8
0x140039063  mov     [rsp+48h+var_10], r9
0x140039068  mov     rcx, 10Dh
0x14003906f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039076  nop     dword ptr [rax+rax+00h]
0x14003907b  test    al, al
0x14003907d  jz      short loc_1400390D3
0x14003907f  lea     rcx, aNtcompositorno; "NtCompositorNotifyExitWindows"
0x140039086  mov     rdx, 10Dh
0x14003908d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039094  nop     dword ptr [rax+rax+00h]
0x140039099  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400390a0  nop     dword ptr [rax+rax+00h]
0x1400390a5  test    al, al
0x1400390a7  jz      short loc_1400390D3
0x1400390a9  lea     rcx, W32pServiceTableFilter
0x1400390b0  mov     edx, cs:W32pServiceLimitFilter
0x1400390b6  mov     rax, 10Dh
0x1400390bd  lea     rcx, [rcx+rdx*4]
0x1400390c1  movsx   eax, byte ptr [rcx+rax]
0x1400390c5  or      eax, eax
0x1400390c7  jle     short loc_1400390CE
0x1400390c9  mov     eax, 0C000001Ch
0x1400390ce  add     rsp, 48h
0x1400390d2  retn
0x1400390d3  mov     rax, cs:__imp_NtCompositorNotifyExitWindows
0x1400390da  mov     rcx, [rsp+48h+var_28]
0x1400390df  mov     rdx, [rsp+48h+var_20]
0x1400390e4  mov     r8, [rsp+48h+var_18]
0x1400390e9  mov     r9, [rsp+48h+var_10]
0x1400390ee  add     rsp, 48h
0x1400390f2  jmp     rax
```
