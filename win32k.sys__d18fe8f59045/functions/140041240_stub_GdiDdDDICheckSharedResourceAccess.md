# _stub_GdiDdDDICheckSharedResourceAccess

- ea: `0x140041240`
- end: `0x1400412e7`
- name: `_stub_GdiDdDDICheckSharedResourceAccess`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041240`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041289`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041289`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICheckSharedResourceAccess` at `0x1400412c3`

## string_xrefs

- `0x14004126f`: `NtGdiDdDDICheckSharedResourceAccess`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICheckSharedResourceAccess(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICheckSharedResourceAccess(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICheckSharedResourceAccess(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041240  sub     rsp, 48h
0x140041244  mov     [rsp+48h+var_28], rcx
0x140041249  mov     [rsp+48h+var_20], rdx
0x14004124e  mov     [rsp+48h+var_18], r8
0x140041253  mov     [rsp+48h+var_10], r9
0x140041258  mov     rcx, 1CAh
0x14004125f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041266  nop     dword ptr [rax+rax+00h]
0x14004126b  test    al, al
0x14004126d  jz      short loc_1400412C3
0x14004126f  lea     rcx, aNtgdiddddichec_5; "NtGdiDdDDICheckSharedResourceAccess"
0x140041276  mov     rdx, 1CAh
0x14004127d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041284  nop     dword ptr [rax+rax+00h]
0x140041289  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041290  nop     dword ptr [rax+rax+00h]
0x140041295  test    al, al
0x140041297  jz      short loc_1400412C3
0x140041299  lea     rcx, W32pServiceTableFilter
0x1400412a0  mov     edx, cs:W32pServiceLimitFilter
0x1400412a6  mov     rax, 1CAh
0x1400412ad  lea     rcx, [rcx+rdx*4]
0x1400412b1  movsx   eax, byte ptr [rcx+rax]
0x1400412b5  or      eax, eax
0x1400412b7  jle     short loc_1400412BE
0x1400412b9  mov     eax, 0C000001Ch
0x1400412be  add     rsp, 48h
0x1400412c2  retn
0x1400412c3  mov     rax, cs:__imp_NtGdiDdDDICheckSharedResourceAccess
0x1400412ca  mov     rcx, [rsp+48h+var_28]
0x1400412cf  mov     rdx, [rsp+48h+var_20]
0x1400412d4  mov     r8, [rsp+48h+var_18]
0x1400412d9  mov     r9, [rsp+48h+var_10]
0x1400412de  add     rsp, 48h
0x1400412e2  jmp     rax
```
