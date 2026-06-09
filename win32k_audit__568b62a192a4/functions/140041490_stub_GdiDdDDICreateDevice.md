# _stub_GdiDdDDICreateDevice

- ea: `0x140041490`
- end: `0x140041537`
- name: `_stub_GdiDdDDICreateDevice`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041490`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400414d9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400414d9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateDevice` at `0x140041513`

## string_xrefs

- `0x1400414bf`: `NtGdiDdDDICreateDevice`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateDevice(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateDevice(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateDevice(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041490  sub     rsp, 48h
0x140041494  mov     [rsp+48h+var_28], rcx
0x140041499  mov     [rsp+48h+var_20], rdx
0x14004149e  mov     [rsp+48h+var_18], r8
0x1400414a3  mov     [rsp+48h+var_10], r9
0x1400414a8  mov     rcx, 1D0h
0x1400414af  call    cs:__imp_IsWin32KSyscallFiltered
0x1400414b6  nop     dword ptr [rax+rax+00h]
0x1400414bb  test    al, al
0x1400414bd  jz      short loc_140041513
0x1400414bf  lea     rcx, aNtgdiddddicrea_4; "NtGdiDdDDICreateDevice"
0x1400414c6  mov     rdx, 1D0h
0x1400414cd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400414d4  nop     dword ptr [rax+rax+00h]
0x1400414d9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400414e0  nop     dword ptr [rax+rax+00h]
0x1400414e5  test    al, al
0x1400414e7  jz      short loc_140041513
0x1400414e9  lea     rcx, W32pServiceTableFilter
0x1400414f0  mov     edx, cs:W32pServiceLimitFilter
0x1400414f6  mov     rax, 1D0h
0x1400414fd  lea     rcx, [rcx+rdx*4]
0x140041501  movsx   eax, byte ptr [rcx+rax]
0x140041505  or      eax, eax
0x140041507  jle     short loc_14004150E
0x140041509  mov     eax, 0C000001Ch
0x14004150e  add     rsp, 48h
0x140041512  retn
0x140041513  mov     rax, cs:__imp_NtGdiDdDDICreateDevice
0x14004151a  mov     rcx, [rsp+48h+var_28]
0x14004151f  mov     rdx, [rsp+48h+var_20]
0x140041524  mov     r8, [rsp+48h+var_18]
0x140041529  mov     r9, [rsp+48h+var_10]
0x14004152e  add     rsp, 48h
0x140041532  jmp     rax
```
