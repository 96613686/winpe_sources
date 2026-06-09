# _stub_GdiDdDDICreatePagingQueue

- ea: `0x140041960`
- end: `0x140041a07`
- name: `_stub_GdiDdDDICreatePagingQueue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041960`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400419a9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400419a9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreatePagingQueue` at `0x1400419e3`

## string_xrefs

- `0x14004198f`: `NtGdiDdDDICreatePagingQueue`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreatePagingQueue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreatePagingQueue(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreatePagingQueue(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041960  sub     rsp, 48h
0x140041964  mov     [rsp+48h+var_28], rcx
0x140041969  mov     [rsp+48h+var_20], rdx
0x14004196e  mov     [rsp+48h+var_18], r8
0x140041973  mov     [rsp+48h+var_10], r9
0x140041978  mov     rcx, 1D7h
0x14004197f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041986  nop     dword ptr [rax+rax+00h]
0x14004198b  test    al, al
0x14004198d  jz      short loc_1400419E3
0x14004198f  lea     rcx, aNtgdiddddicrea_11; "NtGdiDdDDICreatePagingQueue"
0x140041996  mov     rdx, 1D7h
0x14004199d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400419a4  nop     dword ptr [rax+rax+00h]
0x1400419a9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400419b0  nop     dword ptr [rax+rax+00h]
0x1400419b5  test    al, al
0x1400419b7  jz      short loc_1400419E3
0x1400419b9  lea     rcx, W32pServiceTableFilter
0x1400419c0  mov     edx, cs:W32pServiceLimitFilter
0x1400419c6  mov     rax, 1D7h
0x1400419cd  lea     rcx, [rcx+rdx*4]
0x1400419d1  movsx   eax, byte ptr [rcx+rax]
0x1400419d5  or      eax, eax
0x1400419d7  jle     short loc_1400419DE
0x1400419d9  mov     eax, 0C000001Ch
0x1400419de  add     rsp, 48h
0x1400419e2  retn
0x1400419e3  mov     rax, cs:__imp_NtGdiDdDDICreatePagingQueue
0x1400419ea  mov     rcx, [rsp+48h+var_28]
0x1400419ef  mov     rdx, [rsp+48h+var_20]
0x1400419f4  mov     r8, [rsp+48h+var_18]
0x1400419f9  mov     r9, [rsp+48h+var_10]
0x1400419fe  add     rsp, 48h
0x140041a02  jmp     rax
```
