# _stub_GdiDdDDICreateBundleObject

- ea: `0x1400411d0`
- end: `0x140041277`
- name: `_stub_GdiDdDDICreateBundleObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400411d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041219`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041219`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateBundleObject` at `0x140041253`

## string_xrefs

- `0x1400411ff`: `NtGdiDdDDICreateBundleObject`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateBundleObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateBundleObject(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateBundleObject(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400411d0  sub     rsp, 48h
0x1400411d4  mov     [rsp+48h+var_28], rcx
0x1400411d9  mov     [rsp+48h+var_20], rdx
0x1400411de  mov     [rsp+48h+var_18], r8
0x1400411e3  mov     [rsp+48h+var_10], r9
0x1400411e8  mov     rcx, 1CCh
0x1400411ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400411f6  nop     dword ptr [rax+rax+00h]
0x1400411fb  test    al, al
0x1400411fd  jz      short loc_140041253
0x1400411ff  lea     rcx, aNtgdiddddicrea_0; "NtGdiDdDDICreateBundleObject"
0x140041206  mov     rdx, 1CCh
0x14004120d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041214  nop     dword ptr [rax+rax+00h]
0x140041219  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041220  nop     dword ptr [rax+rax+00h]
0x140041225  test    al, al
0x140041227  jz      short loc_140041253
0x140041229  lea     rcx, W32pServiceTableFilter
0x140041230  mov     edx, cs:W32pServiceLimitFilter
0x140041236  mov     rax, 1CCh
0x14004123d  lea     rcx, [rcx+rdx*4]
0x140041241  movsx   eax, byte ptr [rcx+rax]
0x140041245  or      eax, eax
0x140041247  jle     short loc_14004124E
0x140041249  mov     eax, 0C000001Ch
0x14004124e  add     rsp, 48h
0x140041252  retn
0x140041253  mov     rax, cs:__imp_NtGdiDdDDICreateBundleObject
0x14004125a  mov     rcx, [rsp+48h+var_28]
0x14004125f  mov     rdx, [rsp+48h+var_20]
0x140041264  mov     r8, [rsp+48h+var_18]
0x140041269  mov     r9, [rsp+48h+var_10]
0x14004126e  add     rsp, 48h
0x140041272  jmp     rax
```
