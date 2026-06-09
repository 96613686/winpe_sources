# _stub_QueryCompositionSurfaceHDRMetaData

- ea: `0x140053e40`
- end: `0x140053ee7`
- name: `_stub_QueryCompositionSurfaceHDRMetaData`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053e40`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053e89`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053e89`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceHDRMetaData` at `0x140053ec3`

## string_xrefs

- `0x140053e6f`: `NtQueryCompositionSurfaceHDRMetaData`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceHDRMetaData(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceHDRMetaData(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceHDRMetaData(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[112] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053e40  sub     rsp, 48h
0x140053e44  mov     [rsp+48h+var_28], rcx
0x140053e49  mov     [rsp+48h+var_20], rdx
0x140053e4e  mov     [rsp+48h+var_18], r8
0x140053e53  mov     [rsp+48h+var_10], r9
0x140053e58  mov     rcx, 381h
0x140053e5f  call    cs:__imp_IsWin32KSyscallFiltered
0x140053e66  nop     dword ptr [rax+rax+00h]
0x140053e6b  test    al, al
0x140053e6d  jz      short loc_140053EC3
0x140053e6f  lea     rcx, aNtquerycomposi_6; "NtQueryCompositionSurfaceHDRMetaData"
0x140053e76  mov     rdx, 381h
0x140053e7d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053e84  nop     dword ptr [rax+rax+00h]
0x140053e89  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053e90  nop     dword ptr [rax+rax+00h]
0x140053e95  test    al, al
0x140053e97  jz      short loc_140053EC3
0x140053e99  lea     rcx, W32pServiceTableFilter
0x140053ea0  mov     edx, cs:W32pServiceLimitFilter
0x140053ea6  mov     rax, 381h
0x140053ead  lea     rcx, [rcx+rdx*4]
0x140053eb1  movsx   eax, byte ptr [rcx+rax]
0x140053eb5  or      eax, eax
0x140053eb7  jle     short loc_140053EBE
0x140053eb9  mov     eax, 0C000001Ch
0x140053ebe  add     rsp, 48h
0x140053ec2  retn
0x140053ec3  mov     rax, cs:__imp_NtQueryCompositionSurfaceHDRMetaData
0x140053eca  mov     rcx, [rsp+48h+var_28]
0x140053ecf  mov     rdx, [rsp+48h+var_20]
0x140053ed4  mov     r8, [rsp+48h+var_18]
0x140053ed9  mov     r9, [rsp+48h+var_10]
0x140053ede  add     rsp, 48h
0x140053ee2  jmp     rax
```
