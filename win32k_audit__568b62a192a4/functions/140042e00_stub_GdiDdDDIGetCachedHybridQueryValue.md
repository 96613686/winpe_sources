# _stub_GdiDdDDIGetCachedHybridQueryValue

- ea: `0x140042e00`
- end: `0x140042ea7`
- name: `_stub_GdiDdDDIGetCachedHybridQueryValue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140042e00`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140042e49`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140042e49`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIGetCachedHybridQueryValue` at `0x140042e83`

## string_xrefs

- `0x140042e2f`: `NtGdiDdDDIGetCachedHybridQueryValue`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIGetCachedHybridQueryValue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIGetCachedHybridQueryValue(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIGetCachedHybridQueryValue(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[62] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140042e00  sub     rsp, 48h
0x140042e04  mov     [rsp+48h+var_28], rcx
0x140042e09  mov     [rsp+48h+var_20], rdx
0x140042e0e  mov     [rsp+48h+var_18], r8
0x140042e13  mov     [rsp+48h+var_10], r9
0x140042e18  mov     rcx, 1F5h
0x140042e1f  call    cs:__imp_IsWin32KSyscallFiltered
0x140042e26  nop     dword ptr [rax+rax+00h]
0x140042e2b  test    al, al
0x140042e2d  jz      short loc_140042E83
0x140042e2f  lea     rcx, aNtgdiddddigetc; "NtGdiDdDDIGetCachedHybridQueryValue"
0x140042e36  mov     rdx, 1F5h
0x140042e3d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140042e44  nop     dword ptr [rax+rax+00h]
0x140042e49  call    cs:__imp_PsIsWin32KFilterEnabled
0x140042e50  nop     dword ptr [rax+rax+00h]
0x140042e55  test    al, al
0x140042e57  jz      short loc_140042E83
0x140042e59  lea     rcx, W32pServiceTableFilter
0x140042e60  mov     edx, cs:W32pServiceLimitFilter
0x140042e66  mov     rax, 1F5h
0x140042e6d  lea     rcx, [rcx+rdx*4]
0x140042e71  movsx   eax, byte ptr [rcx+rax]
0x140042e75  or      eax, eax
0x140042e77  jle     short loc_140042E7E
0x140042e79  mov     eax, 0C000001Ch
0x140042e7e  add     rsp, 48h
0x140042e82  retn
0x140042e83  mov     rax, cs:__imp_NtGdiDdDDIGetCachedHybridQueryValue
0x140042e8a  mov     rcx, [rsp+48h+var_28]
0x140042e8f  mov     rdx, [rsp+48h+var_20]
0x140042e94  mov     r8, [rsp+48h+var_18]
0x140042e99  mov     r9, [rsp+48h+var_10]
0x140042e9e  add     rsp, 48h
0x140042ea2  jmp     rax
```
