# _stub_FlipObjectReadNextMessageToProducer

- ea: `0x14003e640`
- end: `0x14003e6e7`
- name: `_stub_FlipObjectReadNextMessageToProducer`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e640`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e689`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e689`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectReadNextMessageToProducer` at `0x14003e6c3`

## string_xrefs

- `0x14003e66f`: `NtFlipObjectReadNextMessageToProducer`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[49] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e640  sub     rsp, 48h
0x14003e644  mov     [rsp+48h+var_28], rcx
0x14003e649  mov     [rsp+48h+var_20], rdx
0x14003e64e  mov     [rsp+48h+var_18], r8
0x14003e653  mov     [rsp+48h+var_10], r9
0x14003e658  mov     rcx, 18Ah
0x14003e65f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e666  nop     dword ptr [rax+rax+00h]
0x14003e66b  test    al, al
0x14003e66d  jz      short loc_14003E6C3
0x14003e66f  lea     rcx, aNtflipobjectre; "NtFlipObjectReadNextMessageToProducer"
0x14003e676  mov     rdx, 18Ah
0x14003e67d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e684  nop     dword ptr [rax+rax+00h]
0x14003e689  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e690  nop     dword ptr [rax+rax+00h]
0x14003e695  test    al, al
0x14003e697  jz      short loc_14003E6C3
0x14003e699  lea     rcx, W32pServiceTableFilter
0x14003e6a0  mov     edx, cs:W32pServiceLimitFilter
0x14003e6a6  mov     rax, 18Ah
0x14003e6ad  lea     rcx, [rcx+rdx*4]
0x14003e6b1  movsx   eax, byte ptr [rcx+rax]
0x14003e6b5  or      eax, eax
0x14003e6b7  jle     short loc_14003E6BE
0x14003e6b9  mov     eax, 0C000001Ch
0x14003e6be  add     rsp, 48h
0x14003e6c2  retn
0x14003e6c3  mov     rax, cs:__imp_NtFlipObjectReadNextMessageToProducer
0x14003e6ca  mov     rcx, [rsp+48h+var_28]
0x14003e6cf  mov     rdx, [rsp+48h+var_20]
0x14003e6d4  mov     r8, [rsp+48h+var_18]
0x14003e6d9  mov     r9, [rsp+48h+var_10]
0x14003e6de  add     rsp, 48h
0x14003e6e2  jmp     rax
```
