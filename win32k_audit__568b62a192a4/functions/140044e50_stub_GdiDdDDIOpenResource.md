# _stub_GdiDdDDIOpenResource

- ea: `0x140044e50`
- end: `0x140044ef7`
- name: `_stub_GdiDdDDIOpenResource`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044e50`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044e99`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044e99`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenResource` at `0x140044ed3`

## string_xrefs

- `0x140044e7f`: `NtGdiDdDDIOpenResource`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenResource(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenResource(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenResource(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044e50  sub     rsp, 48h
0x140044e54  mov     [rsp+48h+var_28], rcx
0x140044e59  mov     [rsp+48h+var_20], rdx
0x140044e5e  mov     [rsp+48h+var_18], r8
0x140044e63  mov     [rsp+48h+var_10], r9
0x140044e68  mov     rcx, 224h
0x140044e6f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044e76  nop     dword ptr [rax+rax+00h]
0x140044e7b  test    al, al
0x140044e7d  jz      short loc_140044ED3
0x140044e7f  lea     rcx, aNtgdiddddiopen_8; "NtGdiDdDDIOpenResource"
0x140044e86  mov     rdx, 224h
0x140044e8d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044e94  nop     dword ptr [rax+rax+00h]
0x140044e99  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044ea0  nop     dword ptr [rax+rax+00h]
0x140044ea5  test    al, al
0x140044ea7  jz      short loc_140044ED3
0x140044ea9  lea     rcx, W32pServiceTableFilter
0x140044eb0  mov     edx, cs:W32pServiceLimitFilter
0x140044eb6  mov     rax, 224h
0x140044ebd  lea     rcx, [rcx+rdx*4]
0x140044ec1  movsx   eax, byte ptr [rcx+rax]
0x140044ec5  or      eax, eax
0x140044ec7  jle     short loc_140044ECE
0x140044ec9  mov     eax, 0C000001Ch
0x140044ece  add     rsp, 48h
0x140044ed2  retn
0x140044ed3  mov     rax, cs:__imp_NtGdiDdDDIOpenResource
0x140044eda  mov     rcx, [rsp+48h+var_28]
0x140044edf  mov     rdx, [rsp+48h+var_20]
0x140044ee4  mov     r8, [rsp+48h+var_18]
0x140044ee9  mov     r9, [rsp+48h+var_10]
0x140044eee  add     rsp, 48h
0x140044ef2  jmp     rax
```
