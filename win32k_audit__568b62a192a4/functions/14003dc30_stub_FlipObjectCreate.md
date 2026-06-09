# _stub_FlipObjectCreate

- ea: `0x14003dc30`
- end: `0x14003dcd7`
- name: `_stub_FlipObjectCreate`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003dc30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003dc79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003dc79`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectCreate` at `0x14003dcb3`

## string_xrefs

- `0x14003dc5f`: `NtFlipObjectCreate`

## pseudocode

```c
__int64 __fastcall stub_FlipObjectCreate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtFlipObjectCreate(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtFlipObjectCreate(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[47] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003dc30  sub     rsp, 48h
0x14003dc34  mov     [rsp+48h+var_28], rcx
0x14003dc39  mov     [rsp+48h+var_20], rdx
0x14003dc3e  mov     [rsp+48h+var_18], r8
0x14003dc43  mov     [rsp+48h+var_10], r9
0x14003dc48  mov     rcx, 17Eh
0x14003dc4f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003dc56  nop     dword ptr [rax+rax+00h]
0x14003dc5b  test    al, al
0x14003dc5d  jz      short loc_14003DCB3
0x14003dc5f  lea     rcx, aNtflipobjectcr; "NtFlipObjectCreate"
0x14003dc66  mov     rdx, 17Eh
0x14003dc6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003dc74  nop     dword ptr [rax+rax+00h]
0x14003dc79  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003dc80  nop     dword ptr [rax+rax+00h]
0x14003dc85  test    al, al
0x14003dc87  jz      short loc_14003DCB3
0x14003dc89  lea     rcx, W32pServiceTableFilter
0x14003dc90  mov     edx, cs:W32pServiceLimitFilter
0x14003dc96  mov     rax, 17Eh
0x14003dc9d  lea     rcx, [rcx+rdx*4]
0x14003dca1  movsx   eax, byte ptr [rcx+rax]
0x14003dca5  or      eax, eax
0x14003dca7  jle     short loc_14003DCAE
0x14003dca9  mov     eax, 0C000001Ch
0x14003dcae  add     rsp, 48h
0x14003dcb2  retn
0x14003dcb3  mov     rax, cs:__imp_NtFlipObjectCreate
0x14003dcba  mov     rcx, [rsp+48h+var_28]
0x14003dcbf  mov     rdx, [rsp+48h+var_20]
0x14003dcc4  mov     r8, [rsp+48h+var_18]
0x14003dcc9  mov     r9, [rsp+48h+var_10]
0x14003dcce  add     rsp, 48h
0x14003dcd2  jmp     rax
```
