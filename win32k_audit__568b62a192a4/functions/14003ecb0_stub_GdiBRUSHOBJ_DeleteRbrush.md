# _stub_GdiBRUSHOBJ_DeleteRbrush

- ea: `0x14003ecb0`
- end: `0x14003ed57`
- name: `_stub_GdiBRUSHOBJ_DeleteRbrush`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ecb0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ecf9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ecf9`

## string_xrefs

- `0x14003ecdf`: `NtGdiBRUSHOBJ_DeleteRbrush`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[50] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ecb0  sub     rsp, 48h
0x14003ecb4  mov     [rsp+48h+var_28], rcx
0x14003ecb9  mov     [rsp+48h+var_20], rdx
0x14003ecbe  mov     [rsp+48h+var_18], r8
0x14003ecc3  mov     [rsp+48h+var_10], r9
0x14003ecc8  mov     rcx, 196h
0x14003eccf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ecd6  nop     dword ptr [rax+rax+00h]
0x14003ecdb  test    al, al
0x14003ecdd  jz      short loc_14003ED33
0x14003ecdf  lea     rcx, aNtgdibrushobjD; "NtGdiBRUSHOBJ_DeleteRbrush"
0x14003ece6  mov     rdx, 196h
0x14003eced  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ecf4  nop     dword ptr [rax+rax+00h]
0x14003ecf9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ed00  nop     dword ptr [rax+rax+00h]
0x14003ed05  test    al, al
0x14003ed07  jz      short loc_14003ED33
0x14003ed09  lea     rcx, W32pServiceTableFilter
0x14003ed10  mov     edx, cs:W32pServiceLimitFilter
0x14003ed16  mov     rax, 196h
0x14003ed1d  lea     rcx, [rcx+rdx*4]
0x14003ed21  movsx   eax, byte ptr [rcx+rax]
0x14003ed25  or      eax, eax
0x14003ed27  jle     short loc_14003ED2E
0x14003ed29  mov     eax, 0C000001Ch
0x14003ed2e  add     rsp, 48h
0x14003ed32  retn
0x14003ed33  mov     rax, cs:__imp_NtGdiBRUSHOBJ_DeleteRbrush
0x14003ed3a  mov     rcx, [rsp+48h+var_28]
0x14003ed3f  mov     rdx, [rsp+48h+var_20]
0x14003ed44  mov     r8, [rsp+48h+var_18]
0x14003ed49  mov     r9, [rsp+48h+var_10]
0x14003ed4e  add     rsp, 48h
0x14003ed52  jmp     rax
```
