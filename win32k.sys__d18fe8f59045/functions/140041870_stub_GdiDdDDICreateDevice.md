# _stub_GdiDdDDICreateDevice

- ea: `0x140041870`
- end: `0x140041917`
- name: `_stub_GdiDdDDICreateDevice`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041870`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400418b9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400418b9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateDevice` at `0x1400418f3`

## string_xrefs

- `0x14004189f`: `NtGdiDdDDICreateDevice`

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
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041870  sub     rsp, 48h
0x140041874  mov     [rsp+48h+var_28], rcx
0x140041879  mov     [rsp+48h+var_20], rdx
0x14004187e  mov     [rsp+48h+var_18], r8
0x140041883  mov     [rsp+48h+var_10], r9
0x140041888  mov     rcx, 1D3h
0x14004188f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041896  nop     dword ptr [rax+rax+00h]
0x14004189b  test    al, al
0x14004189d  jz      short loc_1400418F3
0x14004189f  lea     rcx, aNtgdiddddicrea_4; "NtGdiDdDDICreateDevice"
0x1400418a6  mov     rdx, 1D3h
0x1400418ad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400418b4  nop     dword ptr [rax+rax+00h]
0x1400418b9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400418c0  nop     dword ptr [rax+rax+00h]
0x1400418c5  test    al, al
0x1400418c7  jz      short loc_1400418F3
0x1400418c9  lea     rcx, W32pServiceTableFilter
0x1400418d0  mov     edx, cs:W32pServiceLimitFilter
0x1400418d6  mov     rax, 1D3h
0x1400418dd  lea     rcx, [rcx+rdx*4]
0x1400418e1  movsx   eax, byte ptr [rcx+rax]
0x1400418e5  or      eax, eax
0x1400418e7  jle     short loc_1400418EE
0x1400418e9  mov     eax, 0C000001Ch
0x1400418ee  add     rsp, 48h
0x1400418f2  retn
0x1400418f3  mov     rax, cs:__imp_NtGdiDdDDICreateDevice
0x1400418fa  mov     rcx, [rsp+48h+var_28]
0x1400418ff  mov     rdx, [rsp+48h+var_20]
0x140041904  mov     r8, [rsp+48h+var_18]
0x140041909  mov     r9, [rsp+48h+var_10]
0x14004190e  add     rsp, 48h
0x140041912  jmp     rax
```
