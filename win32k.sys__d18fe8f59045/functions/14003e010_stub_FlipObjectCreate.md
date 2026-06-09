# _stub_FlipObjectCreate

- ea: `0x14003e010`
- end: `0x14003e0b7`
- name: `_stub_FlipObjectCreate`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e010`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e059`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e059`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectCreate` at `0x14003e093`

## string_xrefs

- `0x14003e03f`: `NtFlipObjectCreate`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[48] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e010  sub     rsp, 48h
0x14003e014  mov     [rsp+48h+var_28], rcx
0x14003e019  mov     [rsp+48h+var_20], rdx
0x14003e01e  mov     [rsp+48h+var_18], r8
0x14003e023  mov     [rsp+48h+var_10], r9
0x14003e028  mov     rcx, 181h
0x14003e02f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e036  nop     dword ptr [rax+rax+00h]
0x14003e03b  test    al, al
0x14003e03d  jz      short loc_14003E093
0x14003e03f  lea     rcx, aNtflipobjectcr; "NtFlipObjectCreate"
0x14003e046  mov     rdx, 181h
0x14003e04d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e054  nop     dword ptr [rax+rax+00h]
0x14003e059  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e060  nop     dword ptr [rax+rax+00h]
0x14003e065  test    al, al
0x14003e067  jz      short loc_14003E093
0x14003e069  lea     rcx, W32pServiceTableFilter
0x14003e070  mov     edx, cs:W32pServiceLimitFilter
0x14003e076  mov     rax, 181h
0x14003e07d  lea     rcx, [rcx+rdx*4]
0x14003e081  movsx   eax, byte ptr [rcx+rax]
0x14003e085  or      eax, eax
0x14003e087  jle     short loc_14003E08E
0x14003e089  mov     eax, 0C000001Ch
0x14003e08e  add     rsp, 48h
0x14003e092  retn
0x14003e093  mov     rax, cs:__imp_NtFlipObjectCreate
0x14003e09a  mov     rcx, [rsp+48h+var_28]
0x14003e09f  mov     rdx, [rsp+48h+var_20]
0x14003e0a4  mov     r8, [rsp+48h+var_18]
0x14003e0a9  mov     r9, [rsp+48h+var_10]
0x14003e0ae  add     rsp, 48h
0x14003e0b2  jmp     rax
```
