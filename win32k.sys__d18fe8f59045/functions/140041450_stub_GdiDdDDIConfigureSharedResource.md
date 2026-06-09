# _stub_GdiDdDDIConfigureSharedResource

- ea: `0x140041450`
- end: `0x1400414f7`
- name: `_stub_GdiDdDDIConfigureSharedResource`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041450`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041499`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041499`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIConfigureSharedResource` at `0x1400414d3`

## string_xrefs

- `0x14004147f`: `NtGdiDdDDIConfigureSharedResource`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041450  sub     rsp, 48h
0x140041454  mov     [rsp+48h+var_28], rcx
0x140041459  mov     [rsp+48h+var_20], rdx
0x14004145e  mov     [rsp+48h+var_18], r8
0x140041463  mov     [rsp+48h+var_10], r9
0x140041468  mov     rcx, 1CDh
0x14004146f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041476  nop     dword ptr [rax+rax+00h]
0x14004147b  test    al, al
0x14004147d  jz      short loc_1400414D3
0x14004147f  lea     rcx, aNtgdiddddiconf; "NtGdiDdDDIConfigureSharedResource"
0x140041486  mov     rdx, 1CDh
0x14004148d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041494  nop     dword ptr [rax+rax+00h]
0x140041499  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400414a0  nop     dword ptr [rax+rax+00h]
0x1400414a5  test    al, al
0x1400414a7  jz      short loc_1400414D3
0x1400414a9  lea     rcx, W32pServiceTableFilter
0x1400414b0  mov     edx, cs:W32pServiceLimitFilter
0x1400414b6  mov     rax, 1CDh
0x1400414bd  lea     rcx, [rcx+rdx*4]
0x1400414c1  movsx   eax, byte ptr [rcx+rax]
0x1400414c5  or      eax, eax
0x1400414c7  jle     short loc_1400414CE
0x1400414c9  mov     eax, 0C000001Ch
0x1400414ce  add     rsp, 48h
0x1400414d2  retn
0x1400414d3  mov     rax, cs:__imp_NtGdiDdDDIConfigureSharedResource
0x1400414da  mov     rcx, [rsp+48h+var_28]
0x1400414df  mov     rdx, [rsp+48h+var_20]
0x1400414e4  mov     r8, [rsp+48h+var_18]
0x1400414e9  mov     r9, [rsp+48h+var_10]
0x1400414ee  add     rsp, 48h
0x1400414f2  jmp     rax
```
