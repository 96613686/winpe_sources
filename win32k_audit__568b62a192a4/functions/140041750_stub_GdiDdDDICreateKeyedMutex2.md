# _stub_GdiDdDDICreateKeyedMutex2

- ea: `0x140041750`
- end: `0x1400417f7`
- name: `_stub_GdiDdDDICreateKeyedMutex2`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041750`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041799`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041799`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateKeyedMutex2` at `0x1400417d3`

## string_xrefs

- `0x14004177f`: `NtGdiDdDDICreateKeyedMutex2`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateKeyedMutex2(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateKeyedMutex2(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateKeyedMutex2(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041750  sub     rsp, 48h
0x140041754  mov     [rsp+48h+var_28], rcx
0x140041759  mov     [rsp+48h+var_20], rdx
0x14004175e  mov     [rsp+48h+var_18], r8
0x140041763  mov     [rsp+48h+var_10], r9
0x140041768  mov     rcx, 1D4h
0x14004176f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041776  nop     dword ptr [rax+rax+00h]
0x14004177b  test    al, al
0x14004177d  jz      short loc_1400417D3
0x14004177f  lea     rcx, aNtgdiddddicrea_8; "NtGdiDdDDICreateKeyedMutex2"
0x140041786  mov     rdx, 1D4h
0x14004178d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041794  nop     dword ptr [rax+rax+00h]
0x140041799  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400417a0  nop     dword ptr [rax+rax+00h]
0x1400417a5  test    al, al
0x1400417a7  jz      short loc_1400417D3
0x1400417a9  lea     rcx, W32pServiceTableFilter
0x1400417b0  mov     edx, cs:W32pServiceLimitFilter
0x1400417b6  mov     rax, 1D4h
0x1400417bd  lea     rcx, [rcx+rdx*4]
0x1400417c1  movsx   eax, byte ptr [rcx+rax]
0x1400417c5  or      eax, eax
0x1400417c7  jle     short loc_1400417CE
0x1400417c9  mov     eax, 0C000001Ch
0x1400417ce  add     rsp, 48h
0x1400417d2  retn
0x1400417d3  mov     rax, cs:__imp_NtGdiDdDDICreateKeyedMutex2
0x1400417da  mov     rcx, [rsp+48h+var_28]
0x1400417df  mov     rdx, [rsp+48h+var_20]
0x1400417e4  mov     r8, [rsp+48h+var_18]
0x1400417e9  mov     r9, [rsp+48h+var_10]
0x1400417ee  add     rsp, 48h
0x1400417f2  jmp     rax
```
