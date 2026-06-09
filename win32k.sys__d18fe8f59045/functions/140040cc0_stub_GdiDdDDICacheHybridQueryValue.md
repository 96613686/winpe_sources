# _stub_GdiDdDDICacheHybridQueryValue

- ea: `0x140040cc0`
- end: `0x140040d67`
- name: `_stub_GdiDdDDICacheHybridQueryValue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140040cc0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140040d09`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140040d09`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICacheHybridQueryValue` at `0x140040d43`

## string_xrefs

- `0x140040cef`: `NtGdiDdDDICacheHybridQueryValue`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICacheHybridQueryValue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICacheHybridQueryValue(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICacheHybridQueryValue(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[56] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140040cc0  sub     rsp, 48h
0x140040cc4  mov     [rsp+48h+var_28], rcx
0x140040cc9  mov     [rsp+48h+var_20], rdx
0x140040cce  mov     [rsp+48h+var_18], r8
0x140040cd3  mov     [rsp+48h+var_10], r9
0x140040cd8  mov     rcx, 1C2h
0x140040cdf  call    cs:__imp_IsWin32KSyscallFiltered
0x140040ce6  nop     dword ptr [rax+rax+00h]
0x140040ceb  test    al, al
0x140040ced  jz      short loc_140040D43
0x140040cef  lea     rcx, aNtgdiddddicach; "NtGdiDdDDICacheHybridQueryValue"
0x140040cf6  mov     rdx, 1C2h
0x140040cfd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140040d04  nop     dword ptr [rax+rax+00h]
0x140040d09  call    cs:__imp_PsIsWin32KFilterEnabled
0x140040d10  nop     dword ptr [rax+rax+00h]
0x140040d15  test    al, al
0x140040d17  jz      short loc_140040D43
0x140040d19  lea     rcx, W32pServiceTableFilter
0x140040d20  mov     edx, cs:W32pServiceLimitFilter
0x140040d26  mov     rax, 1C2h
0x140040d2d  lea     rcx, [rcx+rdx*4]
0x140040d31  movsx   eax, byte ptr [rcx+rax]
0x140040d35  or      eax, eax
0x140040d37  jle     short loc_140040D3E
0x140040d39  mov     eax, 0C000001Ch
0x140040d3e  add     rsp, 48h
0x140040d42  retn
0x140040d43  mov     rax, cs:__imp_NtGdiDdDDICacheHybridQueryValue
0x140040d4a  mov     rcx, [rsp+48h+var_28]
0x140040d4f  mov     rdx, [rsp+48h+var_20]
0x140040d54  mov     r8, [rsp+48h+var_18]
0x140040d59  mov     r9, [rsp+48h+var_10]
0x140040d5e  add     rsp, 48h
0x140040d62  jmp     rax
```
