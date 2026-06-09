# _stub_DxgkOpenNativeFenceFromNtHandle

- ea: `0x14003cf90`
- end: `0x14003d037`
- name: `_stub_DxgkOpenNativeFenceFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003cf90`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003cfd9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003cfd9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkOpenNativeFenceFromNtHandle` at `0x14003d013`

## string_xrefs

- `0x14003cfbf`: `NtDxgkOpenNativeFenceFromNtHandle`

## pseudocode

```c
__int64 __fastcall stub_DxgkOpenNativeFenceFromNtHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkOpenNativeFenceFromNtHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkOpenNativeFenceFromNtHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[45] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003cf90  sub     rsp, 48h
0x14003cf94  mov     [rsp+48h+var_28], rcx
0x14003cf99  mov     [rsp+48h+var_20], rdx
0x14003cf9e  mov     [rsp+48h+var_18], r8
0x14003cfa3  mov     [rsp+48h+var_10], r9
0x14003cfa8  mov     rcx, 169h
0x14003cfaf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003cfb6  nop     dword ptr [rax+rax+00h]
0x14003cfbb  test    al, al
0x14003cfbd  jz      short loc_14003D013
0x14003cfbf  lea     rcx, aNtdxgkopennati; "NtDxgkOpenNativeFenceFromNtHandle"
0x14003cfc6  mov     rdx, 169h
0x14003cfcd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003cfd4  nop     dword ptr [rax+rax+00h]
0x14003cfd9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003cfe0  nop     dword ptr [rax+rax+00h]
0x14003cfe5  test    al, al
0x14003cfe7  jz      short loc_14003D013
0x14003cfe9  lea     rcx, W32pServiceTableFilter
0x14003cff0  mov     edx, cs:W32pServiceLimitFilter
0x14003cff6  mov     rax, 169h
0x14003cffd  lea     rcx, [rcx+rdx*4]
0x14003d001  movsx   eax, byte ptr [rcx+rax]
0x14003d005  or      eax, eax
0x14003d007  jle     short loc_14003D00E
0x14003d009  mov     eax, 0C000001Ch
0x14003d00e  add     rsp, 48h
0x14003d012  retn
0x14003d013  mov     rax, cs:__imp_NtDxgkOpenNativeFenceFromNtHandle
0x14003d01a  mov     rcx, [rsp+48h+var_28]
0x14003d01f  mov     rdx, [rsp+48h+var_20]
0x14003d024  mov     r8, [rsp+48h+var_18]
0x14003d029  mov     r9, [rsp+48h+var_10]
0x14003d02e  add     rsp, 48h
0x14003d032  jmp     rax
```
