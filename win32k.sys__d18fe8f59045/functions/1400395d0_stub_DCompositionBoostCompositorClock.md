# _stub_DCompositionBoostCompositorClock

- ea: `0x1400395d0`
- end: `0x140039677`
- name: `_stub_DCompositionBoostCompositorClock`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400395d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039619`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039619`

## string_xrefs

- `0x1400395ff`: `NtDCompositionBoostCompositorClock`

## pseudocode

```c
__int64 stub_DCompositionBoostCompositorClock()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionBoostCompositorClock();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionBoostCompositorClock();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[34] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400395d0  sub     rsp, 48h
0x1400395d4  mov     [rsp+48h+var_28], rcx
0x1400395d9  mov     [rsp+48h+var_20], rdx
0x1400395de  mov     [rsp+48h+var_18], r8
0x1400395e3  mov     [rsp+48h+var_10], r9
0x1400395e8  mov     rcx, 115h
0x1400395ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400395f6  nop     dword ptr [rax+rax+00h]
0x1400395fb  test    al, al
0x1400395fd  jz      short loc_140039653
0x1400395ff  lea     rcx, aNtdcomposition_1; "NtDCompositionBoostCompositorClock"
0x140039606  mov     rdx, 115h
0x14003960d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039614  nop     dword ptr [rax+rax+00h]
0x140039619  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039620  nop     dword ptr [rax+rax+00h]
0x140039625  test    al, al
0x140039627  jz      short loc_140039653
0x140039629  lea     rcx, W32pServiceTableFilter
0x140039630  mov     edx, cs:W32pServiceLimitFilter
0x140039636  mov     rax, 115h
0x14003963d  lea     rcx, [rcx+rdx*4]
0x140039641  movsx   eax, byte ptr [rcx+rax]
0x140039645  or      eax, eax
0x140039647  jle     short loc_14003964E
0x140039649  mov     eax, 0C000001Ch
0x14003964e  add     rsp, 48h
0x140039652  retn
0x140039653  mov     rax, cs:__imp_NtDCompositionBoostCompositorClock
0x14003965a  mov     rcx, [rsp+48h+var_28]
0x14003965f  mov     rdx, [rsp+48h+var_20]
0x140039664  mov     r8, [rsp+48h+var_18]
0x140039669  mov     r9, [rsp+48h+var_10]
0x14003966e  add     rsp, 48h
0x140039672  jmp     rax
```
