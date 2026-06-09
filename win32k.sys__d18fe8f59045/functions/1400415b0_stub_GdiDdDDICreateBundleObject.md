# _stub_GdiDdDDICreateBundleObject

- ea: `0x1400415b0`
- end: `0x140041657`
- name: `_stub_GdiDdDDICreateBundleObject`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400415b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400415f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400415f9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateBundleObject` at `0x140041633`

## string_xrefs

- `0x1400415df`: `NtGdiDdDDICreateBundleObject`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateBundleObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateBundleObject(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateBundleObject(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400415b0  sub     rsp, 48h
0x1400415b4  mov     [rsp+48h+var_28], rcx
0x1400415b9  mov     [rsp+48h+var_20], rdx
0x1400415be  mov     [rsp+48h+var_18], r8
0x1400415c3  mov     [rsp+48h+var_10], r9
0x1400415c8  mov     rcx, 1CFh
0x1400415cf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400415d6  nop     dword ptr [rax+rax+00h]
0x1400415db  test    al, al
0x1400415dd  jz      short loc_140041633
0x1400415df  lea     rcx, aNtgdiddddicrea_0; "NtGdiDdDDICreateBundleObject"
0x1400415e6  mov     rdx, 1CFh
0x1400415ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400415f4  nop     dword ptr [rax+rax+00h]
0x1400415f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041600  nop     dword ptr [rax+rax+00h]
0x140041605  test    al, al
0x140041607  jz      short loc_140041633
0x140041609  lea     rcx, W32pServiceTableFilter
0x140041610  mov     edx, cs:W32pServiceLimitFilter
0x140041616  mov     rax, 1CFh
0x14004161d  lea     rcx, [rcx+rdx*4]
0x140041621  movsx   eax, byte ptr [rcx+rax]
0x140041625  or      eax, eax
0x140041627  jle     short loc_14004162E
0x140041629  mov     eax, 0C000001Ch
0x14004162e  add     rsp, 48h
0x140041632  retn
0x140041633  mov     rax, cs:__imp_NtGdiDdDDICreateBundleObject
0x14004163a  mov     rcx, [rsp+48h+var_28]
0x14004163f  mov     rdx, [rsp+48h+var_20]
0x140041644  mov     r8, [rsp+48h+var_18]
0x140041649  mov     r9, [rsp+48h+var_10]
0x14004164e  add     rsp, 48h
0x140041652  jmp     rax
```
