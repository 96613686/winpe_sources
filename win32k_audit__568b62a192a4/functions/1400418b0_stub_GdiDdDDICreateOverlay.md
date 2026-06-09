# _stub_GdiDdDDICreateOverlay

- ea: `0x1400418b0`
- end: `0x140041957`
- name: `_stub_GdiDdDDICreateOverlay`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400418b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400418f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400418f9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateOverlay` at `0x140041933`

## string_xrefs

- `0x1400418df`: `NtGdiDdDDICreateOverlay`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateOverlay(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateOverlay(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateOverlay(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400418b0  sub     rsp, 48h
0x1400418b4  mov     [rsp+48h+var_28], rcx
0x1400418b9  mov     [rsp+48h+var_20], rdx
0x1400418be  mov     [rsp+48h+var_18], r8
0x1400418c3  mov     [rsp+48h+var_10], r9
0x1400418c8  mov     rcx, 1D6h
0x1400418cf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400418d6  nop     dword ptr [rax+rax+00h]
0x1400418db  test    al, al
0x1400418dd  jz      short loc_140041933
0x1400418df  lea     rcx, aNtgdiddddicrea_10; "NtGdiDdDDICreateOverlay"
0x1400418e6  mov     rdx, 1D6h
0x1400418ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400418f4  nop     dword ptr [rax+rax+00h]
0x1400418f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041900  nop     dword ptr [rax+rax+00h]
0x140041905  test    al, al
0x140041907  jz      short loc_140041933
0x140041909  lea     rcx, W32pServiceTableFilter
0x140041910  mov     edx, cs:W32pServiceLimitFilter
0x140041916  mov     rax, 1D6h
0x14004191d  lea     rcx, [rcx+rdx*4]
0x140041921  movsx   eax, byte ptr [rcx+rax]
0x140041925  or      eax, eax
0x140041927  jle     short loc_14004192E
0x140041929  mov     eax, 0C000001Ch
0x14004192e  add     rsp, 48h
0x140041932  retn
0x140041933  mov     rax, cs:__imp_NtGdiDdDDICreateOverlay
0x14004193a  mov     rcx, [rsp+48h+var_28]
0x14004193f  mov     rdx, [rsp+48h+var_20]
0x140041944  mov     r8, [rsp+48h+var_18]
0x140041949  mov     r9, [rsp+48h+var_10]
0x14004194e  add     rsp, 48h
0x140041952  jmp     rax
```
