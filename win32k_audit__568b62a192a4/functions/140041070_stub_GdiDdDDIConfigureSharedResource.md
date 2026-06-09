# _stub_GdiDdDDIConfigureSharedResource

- ea: `0x140041070`
- end: `0x140041117`
- name: `_stub_GdiDdDDIConfigureSharedResource`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041070`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400410b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400410b9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIConfigureSharedResource` at `0x1400410f3`

## string_xrefs

- `0x14004109f`: `NtGdiDdDDIConfigureSharedResource`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIConfigureSharedResource(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIConfigureSharedResource(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIConfigureSharedResource(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041070  sub     rsp, 48h
0x140041074  mov     [rsp+48h+var_28], rcx
0x140041079  mov     [rsp+48h+var_20], rdx
0x14004107e  mov     [rsp+48h+var_18], r8
0x140041083  mov     [rsp+48h+var_10], r9
0x140041088  mov     rcx, 1CAh
0x14004108f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041096  nop     dword ptr [rax+rax+00h]
0x14004109b  test    al, al
0x14004109d  jz      short loc_1400410F3
0x14004109f  lea     rcx, aNtgdiddddiconf; "NtGdiDdDDIConfigureSharedResource"
0x1400410a6  mov     rdx, 1CAh
0x1400410ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400410b4  nop     dword ptr [rax+rax+00h]
0x1400410b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400410c0  nop     dword ptr [rax+rax+00h]
0x1400410c5  test    al, al
0x1400410c7  jz      short loc_1400410F3
0x1400410c9  lea     rcx, W32pServiceTableFilter
0x1400410d0  mov     edx, cs:W32pServiceLimitFilter
0x1400410d6  mov     rax, 1CAh
0x1400410dd  lea     rcx, [rcx+rdx*4]
0x1400410e1  movsx   eax, byte ptr [rcx+rax]
0x1400410e5  or      eax, eax
0x1400410e7  jle     short loc_1400410EE
0x1400410e9  mov     eax, 0C000001Ch
0x1400410ee  add     rsp, 48h
0x1400410f2  retn
0x1400410f3  mov     rax, cs:__imp_NtGdiDdDDIConfigureSharedResource
0x1400410fa  mov     rcx, [rsp+48h+var_28]
0x1400410ff  mov     rdx, [rsp+48h+var_20]
0x140041104  mov     r8, [rsp+48h+var_18]
0x140041109  mov     r9, [rsp+48h+var_10]
0x14004110e  add     rsp, 48h
0x140041112  jmp     rax
```
