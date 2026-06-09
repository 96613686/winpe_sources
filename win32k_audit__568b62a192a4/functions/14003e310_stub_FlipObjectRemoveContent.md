# _stub_FlipObjectRemoveContent

- ea: `0x14003e310`
- end: `0x14003e3b7`
- name: `_stub_FlipObjectRemoveContent`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e310`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e359`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e359`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectRemoveContent` at `0x14003e393`

## string_xrefs

- `0x14003e33f`: `NtFlipObjectRemoveContent`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[49] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e310  sub     rsp, 48h
0x14003e314  mov     [rsp+48h+var_28], rcx
0x14003e319  mov     [rsp+48h+var_20], rdx
0x14003e31e  mov     [rsp+48h+var_18], r8
0x14003e323  mov     [rsp+48h+var_10], r9
0x14003e328  mov     rcx, 188h
0x14003e32f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e336  nop     dword ptr [rax+rax+00h]
0x14003e33b  test    al, al
0x14003e33d  jz      short loc_14003E393
0x14003e33f  lea     rcx, aNtflipobjectre_0; "NtFlipObjectRemoveContent"
0x14003e346  mov     rdx, 188h
0x14003e34d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e354  nop     dword ptr [rax+rax+00h]
0x14003e359  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e360  nop     dword ptr [rax+rax+00h]
0x14003e365  test    al, al
0x14003e367  jz      short loc_14003E393
0x14003e369  lea     rcx, W32pServiceTableFilter
0x14003e370  mov     edx, cs:W32pServiceLimitFilter
0x14003e376  mov     rax, 188h
0x14003e37d  lea     rcx, [rcx+rdx*4]
0x14003e381  movsx   eax, byte ptr [rcx+rax]
0x14003e385  or      eax, eax
0x14003e387  jle     short loc_14003E38E
0x14003e389  mov     eax, 0C000001Ch
0x14003e38e  add     rsp, 48h
0x14003e392  retn
0x14003e393  mov     rax, cs:__imp_NtFlipObjectRemoveContent
0x14003e39a  mov     rcx, [rsp+48h+var_28]
0x14003e39f  mov     rdx, [rsp+48h+var_20]
0x14003e3a4  mov     r8, [rsp+48h+var_18]
0x14003e3a9  mov     r9, [rsp+48h+var_10]
0x14003e3ae  add     rsp, 48h
0x14003e3b2  jmp     rax
```
