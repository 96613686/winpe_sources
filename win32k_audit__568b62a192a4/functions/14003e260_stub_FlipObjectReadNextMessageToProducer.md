# _stub_FlipObjectReadNextMessageToProducer

- ea: `0x14003e260`
- end: `0x14003e307`
- name: `_stub_FlipObjectReadNextMessageToProducer`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e260`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e2a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e2a9`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectReadNextMessageToProducer` at `0x14003e2e3`

## string_xrefs

- `0x14003e28f`: `NtFlipObjectReadNextMessageToProducer`

## pseudocode

```c
__int64 __fastcall stub_FlipObjectReadNextMessageToProducer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtFlipObjectReadNextMessageToProducer(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtFlipObjectReadNextMessageToProducer(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[48] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e260  sub     rsp, 48h
0x14003e264  mov     [rsp+48h+var_28], rcx
0x14003e269  mov     [rsp+48h+var_20], rdx
0x14003e26e  mov     [rsp+48h+var_18], r8
0x14003e273  mov     [rsp+48h+var_10], r9
0x14003e278  mov     rcx, 187h
0x14003e27f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e286  nop     dword ptr [rax+rax+00h]
0x14003e28b  test    al, al
0x14003e28d  jz      short loc_14003E2E3
0x14003e28f  lea     rcx, aNtflipobjectre; "NtFlipObjectReadNextMessageToProducer"
0x14003e296  mov     rdx, 187h
0x14003e29d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e2a4  nop     dword ptr [rax+rax+00h]
0x14003e2a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e2b0  nop     dword ptr [rax+rax+00h]
0x14003e2b5  test    al, al
0x14003e2b7  jz      short loc_14003E2E3
0x14003e2b9  lea     rcx, W32pServiceTableFilter
0x14003e2c0  mov     edx, cs:W32pServiceLimitFilter
0x14003e2c6  mov     rax, 187h
0x14003e2cd  lea     rcx, [rcx+rdx*4]
0x14003e2d1  movsx   eax, byte ptr [rcx+rax]
0x14003e2d5  or      eax, eax
0x14003e2d7  jle     short loc_14003E2DE
0x14003e2d9  mov     eax, 0C000001Ch
0x14003e2de  add     rsp, 48h
0x14003e2e2  retn
0x14003e2e3  mov     rax, cs:__imp_NtFlipObjectReadNextMessageToProducer
0x14003e2ea  mov     rcx, [rsp+48h+var_28]
0x14003e2ef  mov     rdx, [rsp+48h+var_20]
0x14003e2f4  mov     r8, [rsp+48h+var_18]
0x14003e2f9  mov     r9, [rsp+48h+var_10]
0x14003e2fe  add     rsp, 48h
0x14003e302  jmp     rax
```
