# _stub_DCompositionTelemetrySetApplicationId

- ea: `0x14003b4c0`
- end: `0x14003b567`
- name: `_stub_DCompositionTelemetrySetApplicationId`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b4c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b509`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b509`

## string_xrefs

- `0x14003b4ef`: `NtDCompositionTelemetrySetApplicationId`

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
0x14003b4c0  sub     rsp, 48h
0x14003b4c4  mov     [rsp+48h+var_28], rcx
0x14003b4c9  mov     [rsp+48h+var_20], rdx
0x14003b4ce  mov     [rsp+48h+var_18], r8
0x14003b4d3  mov     [rsp+48h+var_10], r9
0x14003b4d8  mov     rcx, 142h
0x14003b4df  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b4e6  nop     dword ptr [rax+rax+00h]
0x14003b4eb  test    al, al
0x14003b4ed  jz      short loc_14003B543
0x14003b4ef  lea     rcx, aNtdcomposition_46; "NtDCompositionTelemetrySetApplicationId"
0x14003b4f6  mov     rdx, 142h
0x14003b4fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b504  nop     dword ptr [rax+rax+00h]
0x14003b509  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b510  nop     dword ptr [rax+rax+00h]
0x14003b515  test    al, al
0x14003b517  jz      short loc_14003B543
0x14003b519  lea     rcx, W32pServiceTableFilter
0x14003b520  mov     edx, cs:W32pServiceLimitFilter
0x14003b526  mov     rax, 142h
0x14003b52d  lea     rcx, [rcx+rdx*4]
0x14003b531  movsx   eax, byte ptr [rcx+rax]
0x14003b535  or      eax, eax
0x14003b537  jle     short loc_14003B53E
0x14003b539  mov     eax, 0C000001Ch
0x14003b53e  add     rsp, 48h
0x14003b542  retn
0x14003b543  mov     rax, cs:__imp_NtDCompositionTelemetrySetApplicationId
0x14003b54a  mov     rcx, [rsp+48h+var_28]
0x14003b54f  mov     rdx, [rsp+48h+var_20]
0x14003b554  mov     r8, [rsp+48h+var_18]
0x14003b559  mov     r9, [rsp+48h+var_10]
0x14003b55e  add     rsp, 48h
0x14003b562  jmp     rax
```
