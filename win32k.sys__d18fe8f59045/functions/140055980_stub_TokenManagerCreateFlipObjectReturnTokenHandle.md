# _stub_TokenManagerCreateFlipObjectReturnTokenHandle

- ea: `0x140055980`
- end: `0x140055a27`
- name: `_stub_TokenManagerCreateFlipObjectReturnTokenHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140055980`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400559c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400559c9`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerCreateFlipObjectReturnTokenHandle` at `0x140055a03`

## string_xrefs

- `0x1400559af`: `NtTokenManagerCreateFlipObjectReturnTokenHandle`

## pseudocode

```c
__int64 __fastcall stub_TokenManagerCreateFlipObjectReturnTokenHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtTokenManagerCreateFlipObjectReturnTokenHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtTokenManagerCreateFlipObjectReturnTokenHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140055980  sub     rsp, 48h
0x140055984  mov     [rsp+48h+var_28], rcx
0x140055989  mov     [rsp+48h+var_20], rdx
0x14005598e  mov     [rsp+48h+var_18], r8
0x140055993  mov     [rsp+48h+var_10], r9
0x140055998  mov     rcx, 3A6h
0x14005599f  call    cs:__imp_IsWin32KSyscallFiltered
0x1400559a6  nop     dword ptr [rax+rax+00h]
0x1400559ab  test    al, al
0x1400559ad  jz      short loc_140055A03
0x1400559af  lea     rcx, aNttokenmanager_0; "NtTokenManagerCreateFlipObjectReturnTok"...
0x1400559b6  mov     rdx, 3A6h
0x1400559bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400559c4  nop     dword ptr [rax+rax+00h]
0x1400559c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400559d0  nop     dword ptr [rax+rax+00h]
0x1400559d5  test    al, al
0x1400559d7  jz      short loc_140055A03
0x1400559d9  lea     rcx, W32pServiceTableFilter
0x1400559e0  mov     edx, cs:W32pServiceLimitFilter
0x1400559e6  mov     rax, 3A6h
0x1400559ed  lea     rcx, [rcx+rdx*4]
0x1400559f1  movsx   eax, byte ptr [rcx+rax]
0x1400559f5  or      eax, eax
0x1400559f7  jle     short loc_1400559FE
0x1400559f9  mov     eax, 0C000001Ch
0x1400559fe  add     rsp, 48h
0x140055a02  retn
0x140055a03  mov     rax, cs:__imp_NtTokenManagerCreateFlipObjectReturnTokenHandle
0x140055a0a  mov     rcx, [rsp+48h+var_28]
0x140055a0f  mov     rdx, [rsp+48h+var_20]
0x140055a14  mov     r8, [rsp+48h+var_18]
0x140055a19  mov     r9, [rsp+48h+var_10]
0x140055a1e  add     rsp, 48h
0x140055a22  jmp     rax
```
