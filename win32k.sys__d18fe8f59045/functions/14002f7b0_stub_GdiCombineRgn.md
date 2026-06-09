# _stub_GdiCombineRgn

- ea: `0x14002f7b0`
- end: `0x14002f857`
- name: `_stub_GdiCombineRgn`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14002f7b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14002f7f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14002f7f9`

## string_xrefs

- `0x14002f7df`: `NtGdiCombineRgn`

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
0x14002f7b0  sub     rsp, 48h
0x14002f7b4  mov     [rsp+48h+var_28], rcx
0x14002f7b9  mov     [rsp+48h+var_20], rdx
0x14002f7be  mov     [rsp+48h+var_18], r8
0x14002f7c3  mov     [rsp+48h+var_10], r9
0x14002f7c8  mov     rcx, 2Fh ; '/'
0x14002f7cf  call    cs:__imp_IsWin32KSyscallFiltered
0x14002f7d6  nop     dword ptr [rax+rax+00h]
0x14002f7db  test    al, al
0x14002f7dd  jz      short loc_14002F833
0x14002f7df  lea     rcx, aNtgdicombinerg; "NtGdiCombineRgn"
0x14002f7e6  mov     rdx, 2Fh ; '/'
0x14002f7ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14002f7f4  nop     dword ptr [rax+rax+00h]
0x14002f7f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14002f800  nop     dword ptr [rax+rax+00h]
0x14002f805  test    al, al
0x14002f807  jz      short loc_14002F833
0x14002f809  lea     rcx, W32pServiceTableFilter
0x14002f810  mov     edx, cs:W32pServiceLimitFilter
0x14002f816  mov     rax, 2Fh ; '/'
0x14002f81d  lea     rcx, [rcx+rdx*4]
0x14002f821  movsx   eax, byte ptr [rcx+rax]
0x14002f825  or      eax, eax
0x14002f827  jle     short loc_14002F82E
0x14002f829  mov     eax, 0C000001Ch
0x14002f82e  add     rsp, 48h
0x14002f832  retn
0x14002f833  mov     rax, cs:__imp_NtGdiCombineRgn
0x14002f83a  mov     rcx, [rsp+48h+var_28]
0x14002f83f  mov     rdx, [rsp+48h+var_20]
0x14002f844  mov     r8, [rsp+48h+var_18]
0x14002f849  mov     r9, [rsp+48h+var_10]
0x14002f84e  add     rsp, 48h
0x14002f852  jmp     rax
```
