# _stub_GdiCombineRgn

- ea: `0x14002f5e0`
- end: `0x14002f687`
- name: `_stub_GdiCombineRgn`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14002f5e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14002f629`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14002f629`

## string_xrefs

- `0x14002f60f`: `NtGdiCombineRgn`

## pseudocode

```c
__int64 stub_GdiCombineRgn()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiCombineRgn();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiCombineRgn();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[5] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14002f5e0  sub     rsp, 48h
0x14002f5e4  mov     [rsp+48h+var_28], rcx
0x14002f5e9  mov     [rsp+48h+var_20], rdx
0x14002f5ee  mov     [rsp+48h+var_18], r8
0x14002f5f3  mov     [rsp+48h+var_10], r9
0x14002f5f8  mov     rcx, 2Fh ; '/'
0x14002f5ff  call    cs:__imp_IsWin32KSyscallFiltered
0x14002f606  nop     dword ptr [rax+rax+00h]
0x14002f60b  test    al, al
0x14002f60d  jz      short loc_14002F663
0x14002f60f  lea     rcx, aNtgdicombinerg; "NtGdiCombineRgn"
0x14002f616  mov     rdx, 2Fh ; '/'
0x14002f61d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14002f624  nop     dword ptr [rax+rax+00h]
0x14002f629  call    cs:__imp_PsIsWin32KFilterEnabled
0x14002f630  nop     dword ptr [rax+rax+00h]
0x14002f635  test    al, al
0x14002f637  jz      short loc_14002F663
0x14002f639  lea     rcx, W32pServiceTableFilter
0x14002f640  mov     edx, cs:W32pServiceLimitFilter
0x14002f646  mov     rax, 2Fh ; '/'
0x14002f64d  lea     rcx, [rcx+rdx*4]
0x14002f651  movsx   eax, byte ptr [rcx+rax]
0x14002f655  or      eax, eax
0x14002f657  jle     short loc_14002F65E
0x14002f659  mov     eax, 0C000001Ch
0x14002f65e  add     rsp, 48h
0x14002f662  retn
0x14002f663  mov     rax, cs:__imp_NtGdiCombineRgn
0x14002f66a  mov     rcx, [rsp+48h+var_28]
0x14002f66f  mov     rdx, [rsp+48h+var_20]
0x14002f674  mov     r8, [rsp+48h+var_18]
0x14002f679  mov     r9, [rsp+48h+var_10]
0x14002f67e  add     rsp, 48h
0x14002f682  jmp     rax
```
