# _stub_GdiDdDDICreateHwContext

- ea: `0x140041920`
- end: `0x1400419c7`
- name: `_stub_GdiDdDDICreateHwContext`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041920`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041969`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041969`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateHwContext` at `0x1400419a3`

## string_xrefs

- `0x14004194f`: `NtGdiDdDDICreateHwContext`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateHwContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateHwContext(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateHwContext(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041920  sub     rsp, 48h
0x140041924  mov     [rsp+48h+var_28], rcx
0x140041929  mov     [rsp+48h+var_20], rdx
0x14004192e  mov     [rsp+48h+var_18], r8
0x140041933  mov     [rsp+48h+var_10], r9
0x140041938  mov     rcx, 1D4h
0x14004193f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041946  nop     dword ptr [rax+rax+00h]
0x14004194b  test    al, al
0x14004194d  jz      short loc_1400419A3
0x14004194f  lea     rcx, aNtgdiddddicrea_5; "NtGdiDdDDICreateHwContext"
0x140041956  mov     rdx, 1D4h
0x14004195d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041964  nop     dword ptr [rax+rax+00h]
0x140041969  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041970  nop     dword ptr [rax+rax+00h]
0x140041975  test    al, al
0x140041977  jz      short loc_1400419A3
0x140041979  lea     rcx, W32pServiceTableFilter
0x140041980  mov     edx, cs:W32pServiceLimitFilter
0x140041986  mov     rax, 1D4h
0x14004198d  lea     rcx, [rcx+rdx*4]
0x140041991  movsx   eax, byte ptr [rcx+rax]
0x140041995  or      eax, eax
0x140041997  jle     short loc_14004199E
0x140041999  mov     eax, 0C000001Ch
0x14004199e  add     rsp, 48h
0x1400419a2  retn
0x1400419a3  mov     rax, cs:__imp_NtGdiDdDDICreateHwContext
0x1400419aa  mov     rcx, [rsp+48h+var_28]
0x1400419af  mov     rdx, [rsp+48h+var_20]
0x1400419b4  mov     r8, [rsp+48h+var_18]
0x1400419b9  mov     r9, [rsp+48h+var_10]
0x1400419be  add     rsp, 48h
0x1400419c2  jmp     rax
```
