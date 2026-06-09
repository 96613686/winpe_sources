# _stub_FlipObjectOpen

- ea: `0x14003e220`
- end: `0x14003e2c7`
- name: `_stub_FlipObjectOpen`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e220`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e269`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e269`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectOpen` at `0x14003e2a3`

## string_xrefs

- `0x14003e24f`: `NtFlipObjectOpen`

## pseudocode

```c
__int64 __fastcall stub_FlipObjectOpen(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtFlipObjectOpen(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtFlipObjectOpen(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[48] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e220  sub     rsp, 48h
0x14003e224  mov     [rsp+48h+var_28], rcx
0x14003e229  mov     [rsp+48h+var_20], rdx
0x14003e22e  mov     [rsp+48h+var_18], r8
0x14003e233  mov     [rsp+48h+var_10], r9
0x14003e238  mov     rcx, 184h
0x14003e23f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e246  nop     dword ptr [rax+rax+00h]
0x14003e24b  test    al, al
0x14003e24d  jz      short loc_14003E2A3
0x14003e24f  lea     rcx, aNtflipobjectop; "NtFlipObjectOpen"
0x14003e256  mov     rdx, 184h
0x14003e25d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e264  nop     dword ptr [rax+rax+00h]
0x14003e269  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e270  nop     dword ptr [rax+rax+00h]
0x14003e275  test    al, al
0x14003e277  jz      short loc_14003E2A3
0x14003e279  lea     rcx, W32pServiceTableFilter
0x14003e280  mov     edx, cs:W32pServiceLimitFilter
0x14003e286  mov     rax, 184h
0x14003e28d  lea     rcx, [rcx+rdx*4]
0x14003e291  movsx   eax, byte ptr [rcx+rax]
0x14003e295  or      eax, eax
0x14003e297  jle     short loc_14003E29E
0x14003e299  mov     eax, 0C000001Ch
0x14003e29e  add     rsp, 48h
0x14003e2a2  retn
0x14003e2a3  mov     rax, cs:__imp_NtFlipObjectOpen
0x14003e2aa  mov     rcx, [rsp+48h+var_28]
0x14003e2af  mov     rdx, [rsp+48h+var_20]
0x14003e2b4  mov     r8, [rsp+48h+var_18]
0x14003e2b9  mov     r9, [rsp+48h+var_10]
0x14003e2be  add     rsp, 48h
0x14003e2c2  jmp     rax
```
