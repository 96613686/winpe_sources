# _stub_GdiDdDDIGetPostCompositionCaps

- ea: `0x1400434e0`
- end: `0x140043587`
- name: `_stub_GdiDdDDIGetPostCompositionCaps`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x1400434e0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140043529`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140043529`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIGetPostCompositionCaps` at `0x140043563`

## string_xrefs

- `0x14004350f`: `NtGdiDdDDIGetPostCompositionCaps`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIGetPostCompositionCaps(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIGetPostCompositionCaps(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIGetPostCompositionCaps(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[63] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x1400434e0  sub     rsp, 48h
0x1400434e4  mov     [rsp+48h+var_28], rcx
0x1400434e9  mov     [rsp+48h+var_20], rdx
0x1400434ee  mov     [rsp+48h+var_18], r8
0x1400434f3  mov     [rsp+48h+var_10], r9
0x1400434f8  mov     rcx, 1FFh
0x1400434ff  call    cs:__imp_IsWin32KSyscallFiltered
0x140043506  nop     dword ptr [rax+rax+00h]
0x14004350b  test    al, al
0x14004350d  jz      short loc_140043563
0x14004350f  lea     rcx, aNtgdiddddigetp; "NtGdiDdDDIGetPostCompositionCaps"
0x140043516  mov     rdx, 1FFh
0x14004351d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140043524  nop     dword ptr [rax+rax+00h]
0x140043529  call    cs:__imp_PsIsWin32KFilterEnabled
0x140043530  nop     dword ptr [rax+rax+00h]
0x140043535  test    al, al
0x140043537  jz      short loc_140043563
0x140043539  lea     rcx, W32pServiceTableFilter
0x140043540  mov     edx, cs:W32pServiceLimitFilter
0x140043546  mov     rax, 1FFh
0x14004354d  lea     rcx, [rcx+rdx*4]
0x140043551  movsx   eax, byte ptr [rcx+rax]
0x140043555  or      eax, eax
0x140043557  jle     short loc_14004355E
0x140043559  mov     eax, 0C000001Ch
0x14004355e  add     rsp, 48h
0x140043562  retn
0x140043563  mov     rax, cs:__imp_NtGdiDdDDIGetPostCompositionCaps
0x14004356a  mov     rcx, [rsp+48h+var_28]
0x14004356f  mov     rdx, [rsp+48h+var_20]
0x140043574  mov     r8, [rsp+48h+var_18]
0x140043579  mov     r9, [rsp+48h+var_10]
0x14004357e  add     rsp, 48h
0x140043582  jmp     rax
```
