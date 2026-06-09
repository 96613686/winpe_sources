# _stub_DCompositionAddCrossDeviceVisualChild

- ea: `0x1400392a0`
- end: `0x140039347`
- name: `_stub_DCompositionAddCrossDeviceVisualChild`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400392a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400392e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400392e9`

## string_xrefs

- `0x1400392cf`: `NtDCompositionAddCrossDeviceVisualChild`

## pseudocode

```c
__int64 __fastcall stub_DCompositionAddCrossDeviceVisualChild(int a1, int a2, int a3, int a4, int a5, int a6, int a7)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionAddCrossDeviceVisualChild(a1, a2, a3, a4, a5, a6, a7);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionAddCrossDeviceVisualChild(a1, a2, a3, a4, a5, a6, a7);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400392a0  sub     rsp, 48h
0x1400392a4  mov     [rsp+48h+var_28], rcx
0x1400392a9  mov     [rsp+48h+var_20], rdx
0x1400392ae  mov     [rsp+48h+var_18], r8
0x1400392b3  mov     [rsp+48h+var_10], r9
0x1400392b8  mov     rcx, 113h
0x1400392bf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400392c6  nop     dword ptr [rax+rax+00h]
0x1400392cb  test    al, al
0x1400392cd  jz      short loc_140039323
0x1400392cf  lea     rcx, aNtdcomposition; "NtDCompositionAddCrossDeviceVisualChild"
0x1400392d6  mov     rdx, 113h
0x1400392dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400392e4  nop     dword ptr [rax+rax+00h]
0x1400392e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400392f0  nop     dword ptr [rax+rax+00h]
0x1400392f5  test    al, al
0x1400392f7  jz      short loc_140039323
0x1400392f9  lea     rcx, W32pServiceTableFilter
0x140039300  mov     edx, cs:W32pServiceLimitFilter
0x140039306  mov     rax, 113h
0x14003930d  lea     rcx, [rcx+rdx*4]
0x140039311  movsx   eax, byte ptr [rcx+rax]
0x140039315  or      eax, eax
0x140039317  jle     short loc_14003931E
0x140039319  mov     eax, 0C000001Ch
0x14003931e  add     rsp, 48h
0x140039322  retn
0x140039323  mov     rax, cs:__imp_NtDCompositionAddCrossDeviceVisualChild
0x14003932a  mov     rcx, [rsp+48h+var_28]
0x14003932f  mov     rdx, [rsp+48h+var_20]
0x140039334  mov     r8, [rsp+48h+var_18]
0x140039339  mov     r9, [rsp+48h+var_10]
0x14003933e  add     rsp, 48h
0x140039342  jmp     rax
```
