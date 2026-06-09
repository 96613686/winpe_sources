# _stub_GdiDdDDIOpenAdapterFromHdc

- ea: `0x1400448d0`
- end: `0x140044977`
- name: `_stub_GdiDdDDIOpenAdapterFromHdc`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400448d0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044919`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044919`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenAdapterFromHdc` at `0x140044953`

## string_xrefs

- `0x1400448ff`: `NtGdiDdDDIOpenAdapterFromHdc`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenAdapterFromHdc(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenAdapterFromHdc(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenAdapterFromHdc(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[67] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400448d0  sub     rsp, 48h
0x1400448d4  mov     [rsp+48h+var_28], rcx
0x1400448d9  mov     [rsp+48h+var_20], rdx
0x1400448de  mov     [rsp+48h+var_18], r8
0x1400448e3  mov     [rsp+48h+var_10], r9
0x1400448e8  mov     rcx, 21Ch
0x1400448ef  call    cs:__imp_IsWin32KSyscallFiltered
0x1400448f6  nop     dword ptr [rax+rax+00h]
0x1400448fb  test    al, al
0x1400448fd  jz      short loc_140044953
0x1400448ff  lea     rcx, aNtgdiddddiopen_0; "NtGdiDdDDIOpenAdapterFromHdc"
0x140044906  mov     rdx, 21Ch
0x14004490d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044914  nop     dword ptr [rax+rax+00h]
0x140044919  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044920  nop     dword ptr [rax+rax+00h]
0x140044925  test    al, al
0x140044927  jz      short loc_140044953
0x140044929  lea     rcx, W32pServiceTableFilter
0x140044930  mov     edx, cs:W32pServiceLimitFilter
0x140044936  mov     rax, 21Ch
0x14004493d  lea     rcx, [rcx+rdx*4]
0x140044941  movsx   eax, byte ptr [rcx+rax]
0x140044945  or      eax, eax
0x140044947  jle     short loc_14004494E
0x140044949  mov     eax, 0C000001Ch
0x14004494e  add     rsp, 48h
0x140044952  retn
0x140044953  mov     rax, cs:__imp_NtGdiDdDDIOpenAdapterFromHdc
0x14004495a  mov     rcx, [rsp+48h+var_28]
0x14004495f  mov     rdx, [rsp+48h+var_20]
0x140044964  mov     r8, [rsp+48h+var_18]
0x140044969  mov     r9, [rsp+48h+var_10]
0x14004496e  add     rsp, 48h
0x140044972  jmp     rax
```
