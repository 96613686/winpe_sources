# _stub_GdiBRUSHOBJ_DeleteRbrush

- ea: `0x14003f090`
- end: `0x14003f137`
- name: `_stub_GdiBRUSHOBJ_DeleteRbrush`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003f090`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003f0d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003f0d9`

## string_xrefs

- `0x14003f0bf`: `NtGdiBRUSHOBJ_DeleteRbrush`

## pseudocode

```c
__int64 stub_GdiBRUSHOBJ_DeleteRbrush()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiBRUSHOBJ_DeleteRbrush();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiBRUSHOBJ_DeleteRbrush();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[51] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003f090  sub     rsp, 48h
0x14003f094  mov     [rsp+48h+var_28], rcx
0x14003f099  mov     [rsp+48h+var_20], rdx
0x14003f09e  mov     [rsp+48h+var_18], r8
0x14003f0a3  mov     [rsp+48h+var_10], r9
0x14003f0a8  mov     rcx, 199h
0x14003f0af  call    cs:__imp_IsWin32KSyscallFiltered
0x14003f0b6  nop     dword ptr [rax+rax+00h]
0x14003f0bb  test    al, al
0x14003f0bd  jz      short loc_14003F113
0x14003f0bf  lea     rcx, aNtgdibrushobjD; "NtGdiBRUSHOBJ_DeleteRbrush"
0x14003f0c6  mov     rdx, 199h
0x14003f0cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003f0d4  nop     dword ptr [rax+rax+00h]
0x14003f0d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003f0e0  nop     dword ptr [rax+rax+00h]
0x14003f0e5  test    al, al
0x14003f0e7  jz      short loc_14003F113
0x14003f0e9  lea     rcx, W32pServiceTableFilter
0x14003f0f0  mov     edx, cs:W32pServiceLimitFilter
0x14003f0f6  mov     rax, 199h
0x14003f0fd  lea     rcx, [rcx+rdx*4]
0x14003f101  movsx   eax, byte ptr [rcx+rax]
0x14003f105  or      eax, eax
0x14003f107  jle     short loc_14003F10E
0x14003f109  mov     eax, 0C000001Ch
0x14003f10e  add     rsp, 48h
0x14003f112  retn
0x14003f113  mov     rax, cs:__imp_NtGdiBRUSHOBJ_DeleteRbrush
0x14003f11a  mov     rcx, [rsp+48h+var_28]
0x14003f11f  mov     rdx, [rsp+48h+var_20]
0x14003f124  mov     r8, [rsp+48h+var_18]
0x14003f129  mov     r9, [rsp+48h+var_10]
0x14003f12e  add     rsp, 48h
0x14003f132  jmp     rax
```
