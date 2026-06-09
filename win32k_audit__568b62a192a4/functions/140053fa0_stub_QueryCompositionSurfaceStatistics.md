# _stub_QueryCompositionSurfaceStatistics

- ea: `0x140053fa0`
- end: `0x140054047`
- name: `_stub_QueryCompositionSurfaceStatistics`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053fa0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053fe9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053fe9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceStatistics` at `0x140054023`

## string_xrefs

- `0x140053fcf`: `NtQueryCompositionSurfaceStatistics`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceStatistics(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceStatistics(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceStatistics(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053fa0  sub     rsp, 48h
0x140053fa4  mov     [rsp+48h+var_28], rcx
0x140053fa9  mov     [rsp+48h+var_20], rdx
0x140053fae  mov     [rsp+48h+var_18], r8
0x140053fb3  mov     [rsp+48h+var_10], r9
0x140053fb8  mov     rcx, 383h
0x140053fbf  call    cs:__imp_IsWin32KSyscallFiltered
0x140053fc6  nop     dword ptr [rax+rax+00h]
0x140053fcb  test    al, al
0x140053fcd  jz      short loc_140054023
0x140053fcf  lea     rcx, aNtquerycomposi_8; "NtQueryCompositionSurfaceStatistics"
0x140053fd6  mov     rdx, 383h
0x140053fdd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053fe4  nop     dword ptr [rax+rax+00h]
0x140053fe9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053ff0  nop     dword ptr [rax+rax+00h]
0x140053ff5  test    al, al
0x140053ff7  jz      short loc_140054023
0x140053ff9  lea     rcx, W32pServiceTableFilter
0x140054000  mov     edx, cs:W32pServiceLimitFilter
0x140054006  mov     rax, 383h
0x14005400d  lea     rcx, [rcx+rdx*4]
0x140054011  movsx   eax, byte ptr [rcx+rax]
0x140054015  or      eax, eax
0x140054017  jle     short loc_14005401E
0x140054019  mov     eax, 0C000001Ch
0x14005401e  add     rsp, 48h
0x140054022  retn
0x140054023  mov     rax, cs:__imp_NtQueryCompositionSurfaceStatistics
0x14005402a  mov     rcx, [rsp+48h+var_28]
0x14005402f  mov     rdx, [rsp+48h+var_20]
0x140054034  mov     r8, [rsp+48h+var_18]
0x140054039  mov     r9, [rsp+48h+var_10]
0x14005403e  add     rsp, 48h
0x140054042  jmp     rax
```
