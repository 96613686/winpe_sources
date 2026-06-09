# _stub_FlipObjectOpen

- ea: `0x14003de40`
- end: `0x14003dee7`
- name: `_stub_FlipObjectOpen`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003de40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003de89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003de89`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectOpen` at `0x14003dec3`

## string_xrefs

- `0x14003de6f`: `NtFlipObjectOpen`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[48] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003de40  sub     rsp, 48h
0x14003de44  mov     [rsp+48h+var_28], rcx
0x14003de49  mov     [rsp+48h+var_20], rdx
0x14003de4e  mov     [rsp+48h+var_18], r8
0x14003de53  mov     [rsp+48h+var_10], r9
0x14003de58  mov     rcx, 181h
0x14003de5f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003de66  nop     dword ptr [rax+rax+00h]
0x14003de6b  test    al, al
0x14003de6d  jz      short loc_14003DEC3
0x14003de6f  lea     rcx, aNtflipobjectop; "NtFlipObjectOpen"
0x14003de76  mov     rdx, 181h
0x14003de7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003de84  nop     dword ptr [rax+rax+00h]
0x14003de89  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003de90  nop     dword ptr [rax+rax+00h]
0x14003de95  test    al, al
0x14003de97  jz      short loc_14003DEC3
0x14003de99  lea     rcx, W32pServiceTableFilter
0x14003dea0  mov     edx, cs:W32pServiceLimitFilter
0x14003dea6  mov     rax, 181h
0x14003dead  lea     rcx, [rcx+rdx*4]
0x14003deb1  movsx   eax, byte ptr [rcx+rax]
0x14003deb5  or      eax, eax
0x14003deb7  jle     short loc_14003DEBE
0x14003deb9  mov     eax, 0C000001Ch
0x14003debe  add     rsp, 48h
0x14003dec2  retn
0x14003dec3  mov     rax, cs:__imp_NtFlipObjectOpen
0x14003deca  mov     rcx, [rsp+48h+var_28]
0x14003decf  mov     rdx, [rsp+48h+var_20]
0x14003ded4  mov     r8, [rsp+48h+var_18]
0x14003ded9  mov     r9, [rsp+48h+var_10]
0x14003dede  add     rsp, 48h
0x14003dee2  jmp     rax
```
