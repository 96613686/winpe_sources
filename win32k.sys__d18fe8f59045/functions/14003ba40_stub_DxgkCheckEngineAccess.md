# _stub_DxgkCheckEngineAccess

- ea: `0x14003ba40`
- end: `0x14003bae7`
- name: `_stub_DxgkCheckEngineAccess`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ba40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ba89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ba89`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCheckEngineAccess` at `0x14003bac3`

## string_xrefs

- `0x14003ba6f`: `NtDxgkCheckEngineAccess`

## pseudocode

```c
__int64 __fastcall stub_DxgkCheckEngineAccess(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkCheckEngineAccess(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkCheckEngineAccess(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[41] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ba40  sub     rsp, 48h
0x14003ba44  mov     [rsp+48h+var_28], rcx
0x14003ba49  mov     [rsp+48h+var_20], rdx
0x14003ba4e  mov     [rsp+48h+var_18], r8
0x14003ba53  mov     [rsp+48h+var_10], r9
0x14003ba58  mov     rcx, 14Ah
0x14003ba5f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ba66  nop     dword ptr [rax+rax+00h]
0x14003ba6b  test    al, al
0x14003ba6d  jz      short loc_14003BAC3
0x14003ba6f  lea     rcx, aNtdxgkcheckeng; "NtDxgkCheckEngineAccess"
0x14003ba76  mov     rdx, 14Ah
0x14003ba7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ba84  nop     dword ptr [rax+rax+00h]
0x14003ba89  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ba90  nop     dword ptr [rax+rax+00h]
0x14003ba95  test    al, al
0x14003ba97  jz      short loc_14003BAC3
0x14003ba99  lea     rcx, W32pServiceTableFilter
0x14003baa0  mov     edx, cs:W32pServiceLimitFilter
0x14003baa6  mov     rax, 14Ah
0x14003baad  lea     rcx, [rcx+rdx*4]
0x14003bab1  movsx   eax, byte ptr [rcx+rax]
0x14003bab5  or      eax, eax
0x14003bab7  jle     short loc_14003BABE
0x14003bab9  mov     eax, 0C000001Ch
0x14003babe  add     rsp, 48h
0x14003bac2  retn
0x14003bac3  mov     rax, cs:__imp_NtDxgkCheckEngineAccess
0x14003baca  mov     rcx, [rsp+48h+var_28]
0x14003bacf  mov     rdx, [rsp+48h+var_20]
0x14003bad4  mov     r8, [rsp+48h+var_18]
0x14003bad9  mov     r9, [rsp+48h+var_10]
0x14003bade  add     rsp, 48h
0x14003bae2  jmp     rax
```
