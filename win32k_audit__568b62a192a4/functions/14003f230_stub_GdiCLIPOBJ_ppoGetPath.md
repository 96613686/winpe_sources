# _stub_GdiCLIPOBJ_ppoGetPath

- ea: `0x14003f230`
- end: `0x14003f2d7`
- name: `_stub_GdiCLIPOBJ_ppoGetPath`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003f230`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003f279`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003f279`

## string_xrefs

- `0x14003f25f`: `NtGdiCLIPOBJ_ppoGetPath`

## pseudocode

```c
__int64 stub_GdiCLIPOBJ_ppoGetPath()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiCLIPOBJ_ppoGetPath();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiCLIPOBJ_ppoGetPath();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[51] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003f230  sub     rsp, 48h
0x14003f234  mov     [rsp+48h+var_28], rcx
0x14003f239  mov     [rsp+48h+var_20], rdx
0x14003f23e  mov     [rsp+48h+var_18], r8
0x14003f243  mov     [rsp+48h+var_10], r9
0x14003f248  mov     rcx, 19Eh
0x14003f24f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003f256  nop     dword ptr [rax+rax+00h]
0x14003f25b  test    al, al
0x14003f25d  jz      short loc_14003F2B3
0x14003f25f  lea     rcx, aNtgdiclipobjPp; "NtGdiCLIPOBJ_ppoGetPath"
0x14003f266  mov     rdx, 19Eh
0x14003f26d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003f274  nop     dword ptr [rax+rax+00h]
0x14003f279  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003f280  nop     dword ptr [rax+rax+00h]
0x14003f285  test    al, al
0x14003f287  jz      short loc_14003F2B3
0x14003f289  lea     rcx, W32pServiceTableFilter
0x14003f290  mov     edx, cs:W32pServiceLimitFilter
0x14003f296  mov     rax, 19Eh
0x14003f29d  lea     rcx, [rcx+rdx*4]
0x14003f2a1  movsx   eax, byte ptr [rcx+rax]
0x14003f2a5  or      eax, eax
0x14003f2a7  jle     short loc_14003F2AE
0x14003f2a9  mov     eax, 0C000001Ch
0x14003f2ae  add     rsp, 48h
0x14003f2b2  retn
0x14003f2b3  mov     rax, cs:__imp_NtGdiCLIPOBJ_ppoGetPath
0x14003f2ba  mov     rcx, [rsp+48h+var_28]
0x14003f2bf  mov     rdx, [rsp+48h+var_20]
0x14003f2c4  mov     r8, [rsp+48h+var_18]
0x14003f2c9  mov     r9, [rsp+48h+var_10]
0x14003f2ce  add     rsp, 48h
0x14003f2d2  jmp     rax
```
