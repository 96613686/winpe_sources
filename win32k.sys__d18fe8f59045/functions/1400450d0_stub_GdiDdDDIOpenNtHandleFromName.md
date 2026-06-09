# _stub_GdiDdDDIOpenNtHandleFromName

- ea: `0x1400450d0`
- end: `0x140045177`
- name: `_stub_GdiDdDDIOpenNtHandleFromName`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400450d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045119`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045119`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenNtHandleFromName` at `0x140045153`

## string_xrefs

- `0x1400450ff`: `NtGdiDdDDIOpenNtHandleFromName`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenNtHandleFromName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenNtHandleFromName(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenNtHandleFromName(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400450d0  sub     rsp, 48h
0x1400450d4  mov     [rsp+48h+var_28], rcx
0x1400450d9  mov     [rsp+48h+var_20], rdx
0x1400450de  mov     [rsp+48h+var_18], r8
0x1400450e3  mov     [rsp+48h+var_10], r9
0x1400450e8  mov     rcx, 225h
0x1400450ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400450f6  nop     dword ptr [rax+rax+00h]
0x1400450fb  test    al, al
0x1400450fd  jz      short loc_140045153
0x1400450ff  lea     rcx, aNtgdiddddiopen_6; "NtGdiDdDDIOpenNtHandleFromName"
0x140045106  mov     rdx, 225h
0x14004510d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045114  nop     dword ptr [rax+rax+00h]
0x140045119  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045120  nop     dword ptr [rax+rax+00h]
0x140045125  test    al, al
0x140045127  jz      short loc_140045153
0x140045129  lea     rcx, W32pServiceTableFilter
0x140045130  mov     edx, cs:W32pServiceLimitFilter
0x140045136  mov     rax, 225h
0x14004513d  lea     rcx, [rcx+rdx*4]
0x140045141  movsx   eax, byte ptr [rcx+rax]
0x140045145  or      eax, eax
0x140045147  jle     short loc_14004514E
0x140045149  mov     eax, 0C000001Ch
0x14004514e  add     rsp, 48h
0x140045152  retn
0x140045153  mov     rax, cs:__imp_NtGdiDdDDIOpenNtHandleFromName
0x14004515a  mov     rcx, [rsp+48h+var_28]
0x14004515f  mov     rdx, [rsp+48h+var_20]
0x140045164  mov     r8, [rsp+48h+var_18]
0x140045169  mov     r9, [rsp+48h+var_10]
0x14004516e  add     rsp, 48h
0x140045172  jmp     rax
```
