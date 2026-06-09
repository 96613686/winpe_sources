# _stub_QueryCompositionSurfaceStatistics

- ea: `0x140054380`
- end: `0x140054427`
- name: `_stub_QueryCompositionSurfaceStatistics`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140054380`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400543c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400543c9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceStatistics` at `0x140054403`

## string_xrefs

- `0x1400543af`: `NtQueryCompositionSurfaceStatistics`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140054380  sub     rsp, 48h
0x140054384  mov     [rsp+48h+var_28], rcx
0x140054389  mov     [rsp+48h+var_20], rdx
0x14005438e  mov     [rsp+48h+var_18], r8
0x140054393  mov     [rsp+48h+var_10], r9
0x140054398  mov     rcx, 386h
0x14005439f  call    cs:__imp_IsWin32KSyscallFiltered
0x1400543a6  nop     dword ptr [rax+rax+00h]
0x1400543ab  test    al, al
0x1400543ad  jz      short loc_140054403
0x1400543af  lea     rcx, aNtquerycomposi_8; "NtQueryCompositionSurfaceStatistics"
0x1400543b6  mov     rdx, 386h
0x1400543bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400543c4  nop     dword ptr [rax+rax+00h]
0x1400543c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400543d0  nop     dword ptr [rax+rax+00h]
0x1400543d5  test    al, al
0x1400543d7  jz      short loc_140054403
0x1400543d9  lea     rcx, W32pServiceTableFilter
0x1400543e0  mov     edx, cs:W32pServiceLimitFilter
0x1400543e6  mov     rax, 386h
0x1400543ed  lea     rcx, [rcx+rdx*4]
0x1400543f1  movsx   eax, byte ptr [rcx+rax]
0x1400543f5  or      eax, eax
0x1400543f7  jle     short loc_1400543FE
0x1400543f9  mov     eax, 0C000001Ch
0x1400543fe  add     rsp, 48h
0x140054402  retn
0x140054403  mov     rax, cs:__imp_NtQueryCompositionSurfaceStatistics
0x14005440a  mov     rcx, [rsp+48h+var_28]
0x14005440f  mov     rdx, [rsp+48h+var_20]
0x140054414  mov     r8, [rsp+48h+var_18]
0x140054419  mov     r9, [rsp+48h+var_10]
0x14005441e  add     rsp, 48h
0x140054422  jmp     rax
```
