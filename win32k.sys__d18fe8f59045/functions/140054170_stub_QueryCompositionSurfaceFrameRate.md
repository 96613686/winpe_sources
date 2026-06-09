# _stub_QueryCompositionSurfaceFrameRate

- ea: `0x140054170`
- end: `0x140054217`
- name: `_stub_QueryCompositionSurfaceFrameRate`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140054170`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400541b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400541b9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceFrameRate` at `0x1400541f3`

## string_xrefs

- `0x14005419f`: `NtQueryCompositionSurfaceFrameRate`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceFrameRate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceFrameRate(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceFrameRate(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140054170  sub     rsp, 48h
0x140054174  mov     [rsp+48h+var_28], rcx
0x140054179  mov     [rsp+48h+var_20], rdx
0x14005417e  mov     [rsp+48h+var_18], r8
0x140054183  mov     [rsp+48h+var_10], r9
0x140054188  mov     rcx, 383h
0x14005418f  call    cs:__imp_IsWin32KSyscallFiltered
0x140054196  nop     dword ptr [rax+rax+00h]
0x14005419b  test    al, al
0x14005419d  jz      short loc_1400541F3
0x14005419f  lea     rcx, aNtquerycomposi_5; "NtQueryCompositionSurfaceFrameRate"
0x1400541a6  mov     rdx, 383h
0x1400541ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400541b4  nop     dword ptr [rax+rax+00h]
0x1400541b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400541c0  nop     dword ptr [rax+rax+00h]
0x1400541c5  test    al, al
0x1400541c7  jz      short loc_1400541F3
0x1400541c9  lea     rcx, W32pServiceTableFilter
0x1400541d0  mov     edx, cs:W32pServiceLimitFilter
0x1400541d6  mov     rax, 383h
0x1400541dd  lea     rcx, [rcx+rdx*4]
0x1400541e1  movsx   eax, byte ptr [rcx+rax]
0x1400541e5  or      eax, eax
0x1400541e7  jle     short loc_1400541EE
0x1400541e9  mov     eax, 0C000001Ch
0x1400541ee  add     rsp, 48h
0x1400541f2  retn
0x1400541f3  mov     rax, cs:__imp_NtQueryCompositionSurfaceFrameRate
0x1400541fa  mov     rcx, [rsp+48h+var_28]
0x1400541ff  mov     rdx, [rsp+48h+var_20]
0x140054204  mov     r8, [rsp+48h+var_18]
0x140054209  mov     r9, [rsp+48h+var_10]
0x14005420e  add     rsp, 48h
0x140054212  jmp     rax
```
