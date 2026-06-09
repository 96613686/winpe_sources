# _stub_GdiCombineTransform

- ea: `0x140036f50`
- end: `0x140036ff7`
- name: `_stub_GdiCombineTransform`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140036f50`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140036f99`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140036f99`

## string_xrefs

- `0x140036f7f`: `NtGdiCombineTransform`

## pseudocode

```c
__int64 stub_GdiCombineTransform()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiCombineTransform();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiCombineTransform();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[27] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140036f50  sub     rsp, 48h
0x140036f54  mov     [rsp+48h+var_28], rcx
0x140036f59  mov     [rsp+48h+var_20], rdx
0x140036f5e  mov     [rsp+48h+var_18], r8
0x140036f63  mov     [rsp+48h+var_10], r9
0x140036f68  mov     rcx, 0DDh
0x140036f6f  call    cs:__imp_IsWin32KSyscallFiltered
0x140036f76  nop     dword ptr [rax+rax+00h]
0x140036f7b  test    al, al
0x140036f7d  jz      short loc_140036FD3
0x140036f7f  lea     rcx, aNtgdicombinetr; "NtGdiCombineTransform"
0x140036f86  mov     rdx, 0DDh
0x140036f8d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140036f94  nop     dword ptr [rax+rax+00h]
0x140036f99  call    cs:__imp_PsIsWin32KFilterEnabled
0x140036fa0  nop     dword ptr [rax+rax+00h]
0x140036fa5  test    al, al
0x140036fa7  jz      short loc_140036FD3
0x140036fa9  lea     rcx, W32pServiceTableFilter
0x140036fb0  mov     edx, cs:W32pServiceLimitFilter
0x140036fb6  mov     rax, 0DDh
0x140036fbd  lea     rcx, [rcx+rdx*4]
0x140036fc1  movsx   eax, byte ptr [rcx+rax]
0x140036fc5  or      eax, eax
0x140036fc7  jle     short loc_140036FCE
0x140036fc9  mov     eax, 0C000001Ch
0x140036fce  add     rsp, 48h
0x140036fd2  retn
0x140036fd3  mov     rax, cs:__imp_NtGdiCombineTransform
0x140036fda  mov     rcx, [rsp+48h+var_28]
0x140036fdf  mov     rdx, [rsp+48h+var_20]
0x140036fe4  mov     r8, [rsp+48h+var_18]
0x140036fe9  mov     r9, [rsp+48h+var_10]
0x140036fee  add     rsp, 48h
0x140036ff2  jmp     rax
```
