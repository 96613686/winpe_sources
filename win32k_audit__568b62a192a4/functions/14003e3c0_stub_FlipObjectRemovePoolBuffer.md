# _stub_FlipObjectRemovePoolBuffer

- ea: `0x14003e3c0`
- end: `0x14003e467`
- name: `_stub_FlipObjectRemovePoolBuffer`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003e3c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e409`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003e409`
- `ext-ms-win-core-win32k-flipmgr-l1-1-1!NtFlipObjectRemovePoolBuffer` at `0x14003e443`

## string_xrefs

- `0x14003e3ef`: `NtFlipObjectRemovePoolBuffer`

## pseudocode

```c
__int64 __fastcall stub_FlipObjectRemovePoolBuffer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtFlipObjectRemovePoolBuffer(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtFlipObjectRemovePoolBuffer(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[49] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003e3c0  sub     rsp, 48h
0x14003e3c4  mov     [rsp+48h+var_28], rcx
0x14003e3c9  mov     [rsp+48h+var_20], rdx
0x14003e3ce  mov     [rsp+48h+var_18], r8
0x14003e3d3  mov     [rsp+48h+var_10], r9
0x14003e3d8  mov     rcx, 189h
0x14003e3df  call    cs:__imp_IsWin32KSyscallFiltered
0x14003e3e6  nop     dword ptr [rax+rax+00h]
0x14003e3eb  test    al, al
0x14003e3ed  jz      short loc_14003E443
0x14003e3ef  lea     rcx, aNtflipobjectre_1; "NtFlipObjectRemovePoolBuffer"
0x14003e3f6  mov     rdx, 189h
0x14003e3fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003e404  nop     dword ptr [rax+rax+00h]
0x14003e409  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003e410  nop     dword ptr [rax+rax+00h]
0x14003e415  test    al, al
0x14003e417  jz      short loc_14003E443
0x14003e419  lea     rcx, W32pServiceTableFilter
0x14003e420  mov     edx, cs:W32pServiceLimitFilter
0x14003e426  mov     rax, 189h
0x14003e42d  lea     rcx, [rcx+rdx*4]
0x14003e431  movsx   eax, byte ptr [rcx+rax]
0x14003e435  or      eax, eax
0x14003e437  jle     short loc_14003E43E
0x14003e439  mov     eax, 0C000001Ch
0x14003e43e  add     rsp, 48h
0x14003e442  retn
0x14003e443  mov     rax, cs:__imp_NtFlipObjectRemovePoolBuffer
0x14003e44a  mov     rcx, [rsp+48h+var_28]
0x14003e44f  mov     rdx, [rsp+48h+var_20]
0x14003e454  mov     r8, [rsp+48h+var_18]
0x14003e459  mov     r9, [rsp+48h+var_10]
0x14003e45e  add     rsp, 48h
0x14003e462  jmp     rax
```
