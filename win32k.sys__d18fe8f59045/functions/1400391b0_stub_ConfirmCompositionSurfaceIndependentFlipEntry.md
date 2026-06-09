# _stub_ConfirmCompositionSurfaceIndependentFlipEntry

- ea: `0x1400391b0`
- end: `0x140039257`
- name: `_stub_ConfirmCompositionSurfaceIndependentFlipEntry`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400391b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400391f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400391f9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtConfirmCompositionSurfaceIndependentFlipEntry` at `0x140039233`

## string_xrefs

- `0x1400391df`: `NtConfirmCompositionSurfaceIndependentFlipEntry`

## pseudocode

```c
__int64 __fastcall stub_ConfirmCompositionSurfaceIndependentFlipEntry(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtConfirmCompositionSurfaceIndependentFlipEntry(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtConfirmCompositionSurfaceIndependentFlipEntry(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400391b0  sub     rsp, 48h
0x1400391b4  mov     [rsp+48h+var_28], rcx
0x1400391b9  mov     [rsp+48h+var_20], rdx
0x1400391be  mov     [rsp+48h+var_18], r8
0x1400391c3  mov     [rsp+48h+var_10], r9
0x1400391c8  mov     rcx, 10Fh
0x1400391cf  call    cs:__imp_IsWin32KSyscallFiltered
0x1400391d6  nop     dword ptr [rax+rax+00h]
0x1400391db  test    al, al
0x1400391dd  jz      short loc_140039233
0x1400391df  lea     rcx, aNtconfirmcompo; "NtConfirmCompositionSurfaceIndependentF"...
0x1400391e6  mov     rdx, 10Fh
0x1400391ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400391f4  nop     dword ptr [rax+rax+00h]
0x1400391f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039200  nop     dword ptr [rax+rax+00h]
0x140039205  test    al, al
0x140039207  jz      short loc_140039233
0x140039209  lea     rcx, W32pServiceTableFilter
0x140039210  mov     edx, cs:W32pServiceLimitFilter
0x140039216  mov     rax, 10Fh
0x14003921d  lea     rcx, [rcx+rdx*4]
0x140039221  movsx   eax, byte ptr [rcx+rax]
0x140039225  or      eax, eax
0x140039227  jle     short loc_14003922E
0x140039229  mov     eax, 0C000001Ch
0x14003922e  add     rsp, 48h
0x140039232  retn
0x140039233  mov     rax, cs:__imp_NtConfirmCompositionSurfaceIndependentFlipEntry
0x14003923a  mov     rcx, [rsp+48h+var_28]
0x14003923f  mov     rdx, [rsp+48h+var_20]
0x140039244  mov     r8, [rsp+48h+var_18]
0x140039249  mov     r9, [rsp+48h+var_10]
0x14003924e  add     rsp, 48h
0x140039252  jmp     rax
```
