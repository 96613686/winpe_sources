# _stub_GdiDdDDIGetCachedHybridQueryValue

- ea: `0x1400431e0`
- end: `0x140043287`
- name: `_stub_GdiDdDDIGetCachedHybridQueryValue`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400431e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140043229`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140043229`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIGetCachedHybridQueryValue` at `0x140043263`

## string_xrefs

- `0x14004320f`: `NtGdiDdDDIGetCachedHybridQueryValue`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIGetCachedHybridQueryValue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIGetCachedHybridQueryValue(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIGetCachedHybridQueryValue(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[63] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400431e0  sub     rsp, 48h
0x1400431e4  mov     [rsp+48h+var_28], rcx
0x1400431e9  mov     [rsp+48h+var_20], rdx
0x1400431ee  mov     [rsp+48h+var_18], r8
0x1400431f3  mov     [rsp+48h+var_10], r9
0x1400431f8  mov     rcx, 1F8h
0x1400431ff  call    cs:__imp_IsWin32KSyscallFiltered
0x140043206  nop     dword ptr [rax+rax+00h]
0x14004320b  test    al, al
0x14004320d  jz      short loc_140043263
0x14004320f  lea     rcx, aNtgdiddddigetc; "NtGdiDdDDIGetCachedHybridQueryValue"
0x140043216  mov     rdx, 1F8h
0x14004321d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140043224  nop     dword ptr [rax+rax+00h]
0x140043229  call    cs:__imp_PsIsWin32KFilterEnabled
0x140043230  nop     dword ptr [rax+rax+00h]
0x140043235  test    al, al
0x140043237  jz      short loc_140043263
0x140043239  lea     rcx, W32pServiceTableFilter
0x140043240  mov     edx, cs:W32pServiceLimitFilter
0x140043246  mov     rax, 1F8h
0x14004324d  lea     rcx, [rcx+rdx*4]
0x140043251  movsx   eax, byte ptr [rcx+rax]
0x140043255  or      eax, eax
0x140043257  jle     short loc_14004325E
0x140043259  mov     eax, 0C000001Ch
0x14004325e  add     rsp, 48h
0x140043262  retn
0x140043263  mov     rax, cs:__imp_NtGdiDdDDIGetCachedHybridQueryValue
0x14004326a  mov     rcx, [rsp+48h+var_28]
0x14004326f  mov     rdx, [rsp+48h+var_20]
0x140043274  mov     r8, [rsp+48h+var_18]
0x140043279  mov     r9, [rsp+48h+var_10]
0x14004327e  add     rsp, 48h
0x140043282  jmp     rax
```
