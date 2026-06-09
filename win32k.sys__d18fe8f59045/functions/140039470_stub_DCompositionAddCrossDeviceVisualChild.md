# _stub_DCompositionAddCrossDeviceVisualChild

- ea: `0x140039470`
- end: `0x140039517`
- name: `_stub_DCompositionAddCrossDeviceVisualChild`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039470`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400394b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400394b9`

## string_xrefs

- `0x14003949f`: `NtDCompositionAddCrossDeviceVisualChild`

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
0x140039470  sub     rsp, 48h
0x140039474  mov     [rsp+48h+var_28], rcx
0x140039479  mov     [rsp+48h+var_20], rdx
0x14003947e  mov     [rsp+48h+var_18], r8
0x140039483  mov     [rsp+48h+var_10], r9
0x140039488  mov     rcx, 113h
0x14003948f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039496  nop     dword ptr [rax+rax+00h]
0x14003949b  test    al, al
0x14003949d  jz      short loc_1400394F3
0x14003949f  lea     rcx, aNtdcomposition; "NtDCompositionAddCrossDeviceVisualChild"
0x1400394a6  mov     rdx, 113h
0x1400394ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400394b4  nop     dword ptr [rax+rax+00h]
0x1400394b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400394c0  nop     dword ptr [rax+rax+00h]
0x1400394c5  test    al, al
0x1400394c7  jz      short loc_1400394F3
0x1400394c9  lea     rcx, W32pServiceTableFilter
0x1400394d0  mov     edx, cs:W32pServiceLimitFilter
0x1400394d6  mov     rax, 113h
0x1400394dd  lea     rcx, [rcx+rdx*4]
0x1400394e1  movsx   eax, byte ptr [rcx+rax]
0x1400394e5  or      eax, eax
0x1400394e7  jle     short loc_1400394EE
0x1400394e9  mov     eax, 0C000001Ch
0x1400394ee  add     rsp, 48h
0x1400394f2  retn
0x1400394f3  mov     rax, cs:__imp_NtDCompositionAddCrossDeviceVisualChild
0x1400394fa  mov     rcx, [rsp+48h+var_28]
0x1400394ff  mov     rdx, [rsp+48h+var_20]
0x140039504  mov     r8, [rsp+48h+var_18]
0x140039509  mov     r9, [rsp+48h+var_10]
0x14003950e  add     rsp, 48h
0x140039512  jmp     rax
```
