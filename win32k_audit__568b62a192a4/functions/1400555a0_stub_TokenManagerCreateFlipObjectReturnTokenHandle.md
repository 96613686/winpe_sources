# _stub_TokenManagerCreateFlipObjectReturnTokenHandle

- ea: `0x1400555a0`
- end: `0x140055647`
- name: `_stub_TokenManagerCreateFlipObjectReturnTokenHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400555a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400555e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400555e9`
- `ext-ms-win-core-win32k-tokenmgr-l1-1-0!NtTokenManagerCreateFlipObjectReturnTokenHandle` at `0x140055623`

## string_xrefs

- `0x1400555cf`: `NtTokenManagerCreateFlipObjectReturnTokenHandle`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[116] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400555a0  sub     rsp, 48h
0x1400555a4  mov     [rsp+48h+var_28], rcx
0x1400555a9  mov     [rsp+48h+var_20], rdx
0x1400555ae  mov     [rsp+48h+var_18], r8
0x1400555b3  mov     [rsp+48h+var_10], r9
0x1400555b8  mov     rcx, 3A3h
0x1400555bf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400555c6  nop     dword ptr [rax+rax+00h]
0x1400555cb  test    al, al
0x1400555cd  jz      short loc_140055623
0x1400555cf  lea     rcx, aNttokenmanager_0; "NtTokenManagerCreateFlipObjectReturnTok"...
0x1400555d6  mov     rdx, 3A3h
0x1400555dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400555e4  nop     dword ptr [rax+rax+00h]
0x1400555e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400555f0  nop     dword ptr [rax+rax+00h]
0x1400555f5  test    al, al
0x1400555f7  jz      short loc_140055623
0x1400555f9  lea     rcx, W32pServiceTableFilter
0x140055600  mov     edx, cs:W32pServiceLimitFilter
0x140055606  mov     rax, 3A3h
0x14005560d  lea     rcx, [rcx+rdx*4]
0x140055611  movsx   eax, byte ptr [rcx+rax]
0x140055615  or      eax, eax
0x140055617  jle     short loc_14005561E
0x140055619  mov     eax, 0C000001Ch
0x14005561e  add     rsp, 48h
0x140055622  retn
0x140055623  mov     rax, cs:__imp_NtTokenManagerCreateFlipObjectReturnTokenHandle
0x14005562a  mov     rcx, [rsp+48h+var_28]
0x14005562f  mov     rdx, [rsp+48h+var_20]
0x140055634  mov     r8, [rsp+48h+var_18]
0x140055639  mov     r9, [rsp+48h+var_10]
0x14005563e  add     rsp, 48h
0x140055642  jmp     rax
```
