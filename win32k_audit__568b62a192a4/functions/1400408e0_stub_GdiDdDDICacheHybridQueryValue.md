# _stub_GdiDdDDICacheHybridQueryValue

- ea: `0x1400408e0`
- end: `0x140040987`
- name: `_stub_GdiDdDDICacheHybridQueryValue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400408e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140040929`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140040929`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICacheHybridQueryValue` at `0x140040963`

## string_xrefs

- `0x14004090f`: `NtGdiDdDDICacheHybridQueryValue`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[55] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400408e0  sub     rsp, 48h
0x1400408e4  mov     [rsp+48h+var_28], rcx
0x1400408e9  mov     [rsp+48h+var_20], rdx
0x1400408ee  mov     [rsp+48h+var_18], r8
0x1400408f3  mov     [rsp+48h+var_10], r9
0x1400408f8  mov     rcx, 1BFh
0x1400408ff  call    cs:__imp_IsWin32KSyscallFiltered
0x140040906  nop     dword ptr [rax+rax+00h]
0x14004090b  test    al, al
0x14004090d  jz      short loc_140040963
0x14004090f  lea     rcx, aNtgdiddddicach; "NtGdiDdDDICacheHybridQueryValue"
0x140040916  mov     rdx, 1BFh
0x14004091d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140040924  nop     dword ptr [rax+rax+00h]
0x140040929  call    cs:__imp_PsIsWin32KFilterEnabled
0x140040930  nop     dword ptr [rax+rax+00h]
0x140040935  test    al, al
0x140040937  jz      short loc_140040963
0x140040939  lea     rcx, W32pServiceTableFilter
0x140040940  mov     edx, cs:W32pServiceLimitFilter
0x140040946  mov     rax, 1BFh
0x14004094d  lea     rcx, [rcx+rdx*4]
0x140040951  movsx   eax, byte ptr [rcx+rax]
0x140040955  or      eax, eax
0x140040957  jle     short loc_14004095E
0x140040959  mov     eax, 0C000001Ch
0x14004095e  add     rsp, 48h
0x140040962  retn
0x140040963  mov     rax, cs:__imp_NtGdiDdDDICacheHybridQueryValue
0x14004096a  mov     rcx, [rsp+48h+var_28]
0x14004096f  mov     rdx, [rsp+48h+var_20]
0x140040974  mov     r8, [rsp+48h+var_18]
0x140040979  mov     r9, [rsp+48h+var_10]
0x14004097e  add     rsp, 48h
0x140040982  jmp     rax
```
