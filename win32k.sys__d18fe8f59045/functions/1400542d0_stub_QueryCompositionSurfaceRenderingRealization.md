# _stub_QueryCompositionSurfaceRenderingRealization

- ea: `0x1400542d0`
- end: `0x140054377`
- name: `_stub_QueryCompositionSurfaceRenderingRealization`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400542d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140054319`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140054319`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceRenderingRealization` at `0x140054353`

## string_xrefs

- `0x1400542ff`: `NtQueryCompositionSurfaceRenderingRealization`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceRenderingRealization(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceRenderingRealization(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceRenderingRealization(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400542d0  sub     rsp, 48h
0x1400542d4  mov     [rsp+48h+var_28], rcx
0x1400542d9  mov     [rsp+48h+var_20], rdx
0x1400542de  mov     [rsp+48h+var_18], r8
0x1400542e3  mov     [rsp+48h+var_10], r9
0x1400542e8  mov     rcx, 385h
0x1400542ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400542f6  nop     dword ptr [rax+rax+00h]
0x1400542fb  test    al, al
0x1400542fd  jz      short loc_140054353
0x1400542ff  lea     rcx, aNtquerycomposi_7; "NtQueryCompositionSurfaceRenderingReali"...
0x140054306  mov     rdx, 385h
0x14005430d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140054314  nop     dword ptr [rax+rax+00h]
0x140054319  call    cs:__imp_PsIsWin32KFilterEnabled
0x140054320  nop     dword ptr [rax+rax+00h]
0x140054325  test    al, al
0x140054327  jz      short loc_140054353
0x140054329  lea     rcx, W32pServiceTableFilter
0x140054330  mov     edx, cs:W32pServiceLimitFilter
0x140054336  mov     rax, 385h
0x14005433d  lea     rcx, [rcx+rdx*4]
0x140054341  movsx   eax, byte ptr [rcx+rax]
0x140054345  or      eax, eax
0x140054347  jle     short loc_14005434E
0x140054349  mov     eax, 0C000001Ch
0x14005434e  add     rsp, 48h
0x140054352  retn
0x140054353  mov     rax, cs:__imp_NtQueryCompositionSurfaceRenderingRealization
0x14005435a  mov     rcx, [rsp+48h+var_28]
0x14005435f  mov     rdx, [rsp+48h+var_20]
0x140054364  mov     r8, [rsp+48h+var_18]
0x140054369  mov     r9, [rsp+48h+var_10]
0x14005436e  add     rsp, 48h
0x140054372  jmp     rax
```
