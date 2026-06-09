# _stub_FlipObjectRemovePoolBuffer

- ea: `0x14003e7a0`
- end: `0x14003e847`
- name: `_stub_FlipObjectRemovePoolBuffer`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e7a0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e7e9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e7e9`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectRemovePoolBuffer` at `0x14003e823`

## string_xrefs

- `0x14003e7cf`: `NtFlipObjectRemovePoolBuffer`

## pseudocode

```c
__int64 __fastcall stub_FlipObjectRemovePoolBuffer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtFlipObjectRemovePoolBuffer(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtFlipObjectRemovePoolBuffer(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[49] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e7a0  sub     rsp, 48h
0x14003e7a4  mov     [rsp+48h+var_28], rcx
0x14003e7a9  mov     [rsp+48h+var_20], rdx
0x14003e7ae  mov     [rsp+48h+var_18], r8
0x14003e7b3  mov     [rsp+48h+var_10], r9
0x14003e7b8  mov     rcx, 18Ch
0x14003e7bf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e7c6  nop     dword ptr [rax+rax+00h]
0x14003e7cb  test    al, al
0x14003e7cd  jz      short loc_14003E823
0x14003e7cf  lea     rcx, aNtflipobjectre_1; "NtFlipObjectRemovePoolBuffer"
0x14003e7d6  mov     rdx, 18Ch
0x14003e7dd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e7e4  nop     dword ptr [rax+rax+00h]
0x14003e7e9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e7f0  nop     dword ptr [rax+rax+00h]
0x14003e7f5  test    al, al
0x14003e7f7  jz      short loc_14003E823
0x14003e7f9  lea     rcx, W32pServiceTableFilter
0x14003e800  mov     edx, cs:W32pServiceLimitFilter
0x14003e806  mov     rax, 18Ch
0x14003e80d  lea     rcx, [rcx+rdx*4]
0x14003e811  movsx   eax, byte ptr [rcx+rax]
0x14003e815  or      eax, eax
0x14003e817  jle     short loc_14003E81E
0x14003e819  mov     eax, 0C000001Ch
0x14003e81e  add     rsp, 48h
0x14003e822  retn
0x14003e823  mov     rax, cs:__imp_NtFlipObjectRemovePoolBuffer
0x14003e82a  mov     rcx, [rsp+48h+var_28]
0x14003e82f  mov     rdx, [rsp+48h+var_20]
0x14003e834  mov     r8, [rsp+48h+var_18]
0x14003e839  mov     r9, [rsp+48h+var_10]
0x14003e83e  add     rsp, 48h
0x14003e842  jmp     rax
```
