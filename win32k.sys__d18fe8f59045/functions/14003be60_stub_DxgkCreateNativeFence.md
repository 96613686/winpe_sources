# _stub_DxgkCreateNativeFence

- ea: `0x14003be60`
- end: `0x14003bf07`
- name: `_stub_DxgkCreateNativeFence`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003be60`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bea9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bea9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCreateNativeFence` at `0x14003bee3`

## string_xrefs

- `0x14003be8f`: `NtDxgkCreateNativeFence`

## pseudocode

```c
__int64 __fastcall stub_DxgkCreateNativeFence(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkCreateNativeFence(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkCreateNativeFence(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[42] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003be60  sub     rsp, 48h
0x14003be64  mov     [rsp+48h+var_28], rcx
0x14003be69  mov     [rsp+48h+var_20], rdx
0x14003be6e  mov     [rsp+48h+var_18], r8
0x14003be73  mov     [rsp+48h+var_10], r9
0x14003be78  mov     rcx, 150h
0x14003be7f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003be86  nop     dword ptr [rax+rax+00h]
0x14003be8b  test    al, al
0x14003be8d  jz      short loc_14003BEE3
0x14003be8f  lea     rcx, aNtdxgkcreatena; "NtDxgkCreateNativeFence"
0x14003be96  mov     rdx, 150h
0x14003be9d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003bea4  nop     dword ptr [rax+rax+00h]
0x14003bea9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003beb0  nop     dword ptr [rax+rax+00h]
0x14003beb5  test    al, al
0x14003beb7  jz      short loc_14003BEE3
0x14003beb9  lea     rcx, W32pServiceTableFilter
0x14003bec0  mov     edx, cs:W32pServiceLimitFilter
0x14003bec6  mov     rax, 150h
0x14003becd  lea     rcx, [rcx+rdx*4]
0x14003bed1  movsx   eax, byte ptr [rcx+rax]
0x14003bed5  or      eax, eax
0x14003bed7  jle     short loc_14003BEDE
0x14003bed9  mov     eax, 0C000001Ch
0x14003bede  add     rsp, 48h
0x14003bee2  retn
0x14003bee3  mov     rax, cs:__imp_NtDxgkCreateNativeFence
0x14003beea  mov     rcx, [rsp+48h+var_28]
0x14003beef  mov     rdx, [rsp+48h+var_20]
0x14003bef4  mov     r8, [rsp+48h+var_18]
0x14003bef9  mov     r9, [rsp+48h+var_10]
0x14003befe  add     rsp, 48h
0x14003bf02  jmp     rax
```
