# _stub_DCompositionSyncWait

- ea: `0x14003b190`
- end: `0x14003b237`
- name: `_stub_DCompositionSyncWait`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b190`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b1d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b1d9`

## string_xrefs

- `0x14003b1bf`: `NtDCompositionSyncWait`

## pseudocode

```c
__int64 stub_DCompositionSyncWait()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSyncWait();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSyncWait();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b190  sub     rsp, 48h
0x14003b194  mov     [rsp+48h+var_28], rcx
0x14003b199  mov     [rsp+48h+var_20], rdx
0x14003b19e  mov     [rsp+48h+var_18], r8
0x14003b1a3  mov     [rsp+48h+var_10], r9
0x14003b1a8  mov     rcx, 140h
0x14003b1af  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b1b6  nop     dword ptr [rax+rax+00h]
0x14003b1bb  test    al, al
0x14003b1bd  jz      short loc_14003B213
0x14003b1bf  lea     rcx, aNtdcomposition_44; "NtDCompositionSyncWait"
0x14003b1c6  mov     rdx, 140h
0x14003b1cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b1d4  nop     dword ptr [rax+rax+00h]
0x14003b1d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b1e0  nop     dword ptr [rax+rax+00h]
0x14003b1e5  test    al, al
0x14003b1e7  jz      short loc_14003B213
0x14003b1e9  lea     rcx, W32pServiceTableFilter
0x14003b1f0  mov     edx, cs:W32pServiceLimitFilter
0x14003b1f6  mov     rax, 140h
0x14003b1fd  lea     rcx, [rcx+rdx*4]
0x14003b201  movsx   eax, byte ptr [rcx+rax]
0x14003b205  or      eax, eax
0x14003b207  jle     short loc_14003B20E
0x14003b209  mov     eax, 0C000001Ch
0x14003b20e  add     rsp, 48h
0x14003b212  retn
0x14003b213  mov     rax, cs:__imp_NtDCompositionSyncWait
0x14003b21a  mov     rcx, [rsp+48h+var_28]
0x14003b21f  mov     rdx, [rsp+48h+var_20]
0x14003b224  mov     r8, [rsp+48h+var_18]
0x14003b229  mov     r9, [rsp+48h+var_10]
0x14003b22e  add     rsp, 48h
0x14003b232  jmp     rax
```
