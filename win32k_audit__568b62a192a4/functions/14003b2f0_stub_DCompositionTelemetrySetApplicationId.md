# _stub_DCompositionTelemetrySetApplicationId

- ea: `0x14003b2f0`
- end: `0x14003b397`
- name: `_stub_DCompositionTelemetrySetApplicationId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b2f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b339`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b339`

## string_xrefs

- `0x14003b31f`: `NtDCompositionTelemetrySetApplicationId`

## pseudocode

```c
__int64 stub_DCompositionTelemetrySetApplicationId()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionTelemetrySetApplicationId();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionTelemetrySetApplicationId();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b2f0  sub     rsp, 48h
0x14003b2f4  mov     [rsp+48h+var_28], rcx
0x14003b2f9  mov     [rsp+48h+var_20], rdx
0x14003b2fe  mov     [rsp+48h+var_18], r8
0x14003b303  mov     [rsp+48h+var_10], r9
0x14003b308  mov     rcx, 142h
0x14003b30f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b316  nop     dword ptr [rax+rax+00h]
0x14003b31b  test    al, al
0x14003b31d  jz      short loc_14003B373
0x14003b31f  lea     rcx, aNtdcomposition_46; "NtDCompositionTelemetrySetApplicationId"
0x14003b326  mov     rdx, 142h
0x14003b32d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b334  nop     dword ptr [rax+rax+00h]
0x14003b339  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b340  nop     dword ptr [rax+rax+00h]
0x14003b345  test    al, al
0x14003b347  jz      short loc_14003B373
0x14003b349  lea     rcx, W32pServiceTableFilter
0x14003b350  mov     edx, cs:W32pServiceLimitFilter
0x14003b356  mov     rax, 142h
0x14003b35d  lea     rcx, [rcx+rdx*4]
0x14003b361  movsx   eax, byte ptr [rcx+rax]
0x14003b365  or      eax, eax
0x14003b367  jle     short loc_14003B36E
0x14003b369  mov     eax, 0C000001Ch
0x14003b36e  add     rsp, 48h
0x14003b372  retn
0x14003b373  mov     rax, cs:__imp_NtDCompositionTelemetrySetApplicationId
0x14003b37a  mov     rcx, [rsp+48h+var_28]
0x14003b37f  mov     rdx, [rsp+48h+var_20]
0x14003b384  mov     r8, [rsp+48h+var_18]
0x14003b389  mov     r9, [rsp+48h+var_10]
0x14003b38e  add     rsp, 48h
0x14003b392  jmp     rax
```
