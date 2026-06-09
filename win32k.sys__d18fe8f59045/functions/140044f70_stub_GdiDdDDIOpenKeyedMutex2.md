# _stub_GdiDdDDIOpenKeyedMutex2

- ea: `0x140044f70`
- end: `0x140045017`
- name: `_stub_GdiDdDDIOpenKeyedMutex2`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140044f70`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044fb9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140044fb9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenKeyedMutex2` at `0x140044ff3`

## string_xrefs

- `0x140044f9f`: `NtGdiDdDDIOpenKeyedMutex2`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenKeyedMutex2(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenKeyedMutex2(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenKeyedMutex2(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140044f70  sub     rsp, 48h
0x140044f74  mov     [rsp+48h+var_28], rcx
0x140044f79  mov     [rsp+48h+var_20], rdx
0x140044f7e  mov     [rsp+48h+var_18], r8
0x140044f83  mov     [rsp+48h+var_10], r9
0x140044f88  mov     rcx, 223h
0x140044f8f  call    cs:__imp_IsWin32KSyscallFiltered
0x140044f96  nop     dword ptr [rax+rax+00h]
0x140044f9b  test    al, al
0x140044f9d  jz      short loc_140044FF3
0x140044f9f  lea     rcx, aNtgdiddddiopen_4; "NtGdiDdDDIOpenKeyedMutex2"
0x140044fa6  mov     rdx, 223h
0x140044fad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140044fb4  nop     dword ptr [rax+rax+00h]
0x140044fb9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140044fc0  nop     dword ptr [rax+rax+00h]
0x140044fc5  test    al, al
0x140044fc7  jz      short loc_140044FF3
0x140044fc9  lea     rcx, W32pServiceTableFilter
0x140044fd0  mov     edx, cs:W32pServiceLimitFilter
0x140044fd6  mov     rax, 223h
0x140044fdd  lea     rcx, [rcx+rdx*4]
0x140044fe1  movsx   eax, byte ptr [rcx+rax]
0x140044fe5  or      eax, eax
0x140044fe7  jle     short loc_140044FEE
0x140044fe9  mov     eax, 0C000001Ch
0x140044fee  add     rsp, 48h
0x140044ff2  retn
0x140044ff3  mov     rax, cs:__imp_NtGdiDdDDIOpenKeyedMutex2
0x140044ffa  mov     rcx, [rsp+48h+var_28]
0x140044fff  mov     rdx, [rsp+48h+var_20]
0x140045004  mov     r8, [rsp+48h+var_18]
0x140045009  mov     r9, [rsp+48h+var_10]
0x14004500e  add     rsp, 48h
0x140045012  jmp     rax
```
