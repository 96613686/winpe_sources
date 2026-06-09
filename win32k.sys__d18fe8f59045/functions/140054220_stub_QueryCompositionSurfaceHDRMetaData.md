# _stub_QueryCompositionSurfaceHDRMetaData

- ea: `0x140054220`
- end: `0x1400542c7`
- name: `_stub_QueryCompositionSurfaceHDRMetaData`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140054220`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140054269`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140054269`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceHDRMetaData` at `0x1400542a3`

## string_xrefs

- `0x14005424f`: `NtQueryCompositionSurfaceHDRMetaData`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceHDRMetaData(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceHDRMetaData(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceHDRMetaData(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140054220  sub     rsp, 48h
0x140054224  mov     [rsp+48h+var_28], rcx
0x140054229  mov     [rsp+48h+var_20], rdx
0x14005422e  mov     [rsp+48h+var_18], r8
0x140054233  mov     [rsp+48h+var_10], r9
0x140054238  mov     rcx, 384h
0x14005423f  call    cs:__imp_IsWin32KSyscallFiltered
0x140054246  nop     dword ptr [rax+rax+00h]
0x14005424b  test    al, al
0x14005424d  jz      short loc_1400542A3
0x14005424f  lea     rcx, aNtquerycomposi_6; "NtQueryCompositionSurfaceHDRMetaData"
0x140054256  mov     rdx, 384h
0x14005425d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140054264  nop     dword ptr [rax+rax+00h]
0x140054269  call    cs:__imp_PsIsWin32KFilterEnabled
0x140054270  nop     dword ptr [rax+rax+00h]
0x140054275  test    al, al
0x140054277  jz      short loc_1400542A3
0x140054279  lea     rcx, W32pServiceTableFilter
0x140054280  mov     edx, cs:W32pServiceLimitFilter
0x140054286  mov     rax, 384h
0x14005428d  lea     rcx, [rcx+rdx*4]
0x140054291  movsx   eax, byte ptr [rcx+rax]
0x140054295  or      eax, eax
0x140054297  jle     short loc_14005429E
0x140054299  mov     eax, 0C000001Ch
0x14005429e  add     rsp, 48h
0x1400542a2  retn
0x1400542a3  mov     rax, cs:__imp_NtQueryCompositionSurfaceHDRMetaData
0x1400542aa  mov     rcx, [rsp+48h+var_28]
0x1400542af  mov     rdx, [rsp+48h+var_20]
0x1400542b4  mov     r8, [rsp+48h+var_18]
0x1400542b9  mov     r9, [rsp+48h+var_10]
0x1400542be  add     rsp, 48h
0x1400542c2  jmp     rax
```
