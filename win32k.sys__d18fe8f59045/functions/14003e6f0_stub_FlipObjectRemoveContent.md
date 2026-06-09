# _stub_FlipObjectRemoveContent

- ea: `0x14003e6f0`
- end: `0x14003e797`
- name: `_stub_FlipObjectRemoveContent`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e6f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e739`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e739`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectRemoveContent` at `0x14003e773`

## string_xrefs

- `0x14003e71f`: `NtFlipObjectRemoveContent`

## pseudocode

```c
__int64 __fastcall stub_FlipObjectRemoveContent(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtFlipObjectRemoveContent(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtFlipObjectRemoveContent(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[49] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e6f0  sub     rsp, 48h
0x14003e6f4  mov     [rsp+48h+var_28], rcx
0x14003e6f9  mov     [rsp+48h+var_20], rdx
0x14003e6fe  mov     [rsp+48h+var_18], r8
0x14003e703  mov     [rsp+48h+var_10], r9
0x14003e708  mov     rcx, 18Bh
0x14003e70f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e716  nop     dword ptr [rax+rax+00h]
0x14003e71b  test    al, al
0x14003e71d  jz      short loc_14003E773
0x14003e71f  lea     rcx, aNtflipobjectre_0; "NtFlipObjectRemoveContent"
0x14003e726  mov     rdx, 18Bh
0x14003e72d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e734  nop     dword ptr [rax+rax+00h]
0x14003e739  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e740  nop     dword ptr [rax+rax+00h]
0x14003e745  test    al, al
0x14003e747  jz      short loc_14003E773
0x14003e749  lea     rcx, W32pServiceTableFilter
0x14003e750  mov     edx, cs:W32pServiceLimitFilter
0x14003e756  mov     rax, 18Bh
0x14003e75d  lea     rcx, [rcx+rdx*4]
0x14003e761  movsx   eax, byte ptr [rcx+rax]
0x14003e765  or      eax, eax
0x14003e767  jle     short loc_14003E76E
0x14003e769  mov     eax, 0C000001Ch
0x14003e76e  add     rsp, 48h
0x14003e772  retn
0x14003e773  mov     rax, cs:__imp_NtFlipObjectRemoveContent
0x14003e77a  mov     rcx, [rsp+48h+var_28]
0x14003e77f  mov     rdx, [rsp+48h+var_20]
0x14003e784  mov     r8, [rsp+48h+var_18]
0x14003e789  mov     r9, [rsp+48h+var_10]
0x14003e78e  add     rsp, 48h
0x14003e792  jmp     rax
```
