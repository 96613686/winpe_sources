# _stub_GdiDdDDICreateAllocation

- ea: `0x140041120`
- end: `0x1400411c7`
- name: `_stub_GdiDdDDICreateAllocation`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041120`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041169`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041169`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateAllocation` at `0x1400411a3`

## string_xrefs

- `0x14004114f`: `NtGdiDdDDICreateAllocation`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateAllocation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateAllocation(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateAllocation(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041120  sub     rsp, 48h
0x140041124  mov     [rsp+48h+var_28], rcx
0x140041129  mov     [rsp+48h+var_20], rdx
0x14004112e  mov     [rsp+48h+var_18], r8
0x140041133  mov     [rsp+48h+var_10], r9
0x140041138  mov     rcx, 1CBh
0x14004113f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041146  nop     dword ptr [rax+rax+00h]
0x14004114b  test    al, al
0x14004114d  jz      short loc_1400411A3
0x14004114f  lea     rcx, aNtgdiddddicrea; "NtGdiDdDDICreateAllocation"
0x140041156  mov     rdx, 1CBh
0x14004115d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041164  nop     dword ptr [rax+rax+00h]
0x140041169  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041170  nop     dword ptr [rax+rax+00h]
0x140041175  test    al, al
0x140041177  jz      short loc_1400411A3
0x140041179  lea     rcx, W32pServiceTableFilter
0x140041180  mov     edx, cs:W32pServiceLimitFilter
0x140041186  mov     rax, 1CBh
0x14004118d  lea     rcx, [rcx+rdx*4]
0x140041191  movsx   eax, byte ptr [rcx+rax]
0x140041195  or      eax, eax
0x140041197  jle     short loc_14004119E
0x140041199  mov     eax, 0C000001Ch
0x14004119e  add     rsp, 48h
0x1400411a2  retn
0x1400411a3  mov     rax, cs:__imp_NtGdiDdDDICreateAllocation
0x1400411aa  mov     rcx, [rsp+48h+var_28]
0x1400411af  mov     rdx, [rsp+48h+var_20]
0x1400411b4  mov     r8, [rsp+48h+var_18]
0x1400411b9  mov     r9, [rsp+48h+var_10]
0x1400411be  add     rsp, 48h
0x1400411c2  jmp     rax
```
