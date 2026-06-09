# _stub_DCompositionBoostCompositorClock

- ea: `0x140039400`
- end: `0x1400394a7`
- name: `_stub_DCompositionBoostCompositorClock`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039400`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039449`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039449`

## string_xrefs

- `0x14003942f`: `NtDCompositionBoostCompositorClock`

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
0x140039400  sub     rsp, 48h
0x140039404  mov     [rsp+48h+var_28], rcx
0x140039409  mov     [rsp+48h+var_20], rdx
0x14003940e  mov     [rsp+48h+var_18], r8
0x140039413  mov     [rsp+48h+var_10], r9
0x140039418  mov     rcx, 115h
0x14003941f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039426  nop     dword ptr [rax+rax+00h]
0x14003942b  test    al, al
0x14003942d  jz      short loc_140039483
0x14003942f  lea     rcx, aNtdcomposition_1; "NtDCompositionBoostCompositorClock"
0x140039436  mov     rdx, 115h
0x14003943d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039444  nop     dword ptr [rax+rax+00h]
0x140039449  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039450  nop     dword ptr [rax+rax+00h]
0x140039455  test    al, al
0x140039457  jz      short loc_140039483
0x140039459  lea     rcx, W32pServiceTableFilter
0x140039460  mov     edx, cs:W32pServiceLimitFilter
0x140039466  mov     rax, 115h
0x14003946d  lea     rcx, [rcx+rdx*4]
0x140039471  movsx   eax, byte ptr [rcx+rax]
0x140039475  or      eax, eax
0x140039477  jle     short loc_14003947E
0x140039479  mov     eax, 0C000001Ch
0x14003947e  add     rsp, 48h
0x140039482  retn
0x140039483  mov     rax, cs:__imp_NtDCompositionBoostCompositorClock
0x14003948a  mov     rcx, [rsp+48h+var_28]
0x14003948f  mov     rdx, [rsp+48h+var_20]
0x140039494  mov     r8, [rsp+48h+var_18]
0x140039499  mov     r9, [rsp+48h+var_10]
0x14003949e  add     rsp, 48h
0x1400394a2  jmp     rax
```
