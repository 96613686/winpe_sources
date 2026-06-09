# _stub_GdiDdDDIDispMgrCreate

- ea: `0x1400429a0`
- end: `0x140042a47`
- name: `_stub_GdiDdDDIDispMgrCreate`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400429a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400429e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400429e9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIDispMgrCreate` at `0x140042a23`

## string_xrefs

- `0x1400429cf`: `NtGdiDdDDIDispMgrCreate`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIDispMgrCreate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIDispMgrCreate(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIDispMgrCreate(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[61] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400429a0  sub     rsp, 48h
0x1400429a4  mov     [rsp+48h+var_28], rcx
0x1400429a9  mov     [rsp+48h+var_20], rdx
0x1400429ae  mov     [rsp+48h+var_18], r8
0x1400429b3  mov     [rsp+48h+var_10], r9
0x1400429b8  mov     rcx, 1ECh
0x1400429bf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400429c6  nop     dword ptr [rax+rax+00h]
0x1400429cb  test    al, al
0x1400429cd  jz      short loc_140042A23
0x1400429cf  lea     rcx, aNtgdiddddidisp; "NtGdiDdDDIDispMgrCreate"
0x1400429d6  mov     rdx, 1ECh
0x1400429dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400429e4  nop     dword ptr [rax+rax+00h]
0x1400429e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400429f0  nop     dword ptr [rax+rax+00h]
0x1400429f5  test    al, al
0x1400429f7  jz      short loc_140042A23
0x1400429f9  lea     rcx, W32pServiceTableFilter
0x140042a00  mov     edx, cs:W32pServiceLimitFilter
0x140042a06  mov     rax, 1ECh
0x140042a0d  lea     rcx, [rcx+rdx*4]
0x140042a11  movsx   eax, byte ptr [rcx+rax]
0x140042a15  or      eax, eax
0x140042a17  jle     short loc_140042A1E
0x140042a19  mov     eax, 0C000001Ch
0x140042a1e  add     rsp, 48h
0x140042a22  retn
0x140042a23  mov     rax, cs:__imp_NtGdiDdDDIDispMgrCreate
0x140042a2a  mov     rcx, [rsp+48h+var_28]
0x140042a2f  mov     rdx, [rsp+48h+var_20]
0x140042a34  mov     r8, [rsp+48h+var_18]
0x140042a39  mov     r9, [rsp+48h+var_10]
0x140042a3e  add     rsp, 48h
0x140042a42  jmp     rax
```
