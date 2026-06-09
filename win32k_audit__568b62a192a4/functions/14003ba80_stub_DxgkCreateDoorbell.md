# _stub_DxgkCreateDoorbell

- ea: `0x14003ba80`
- end: `0x14003bb27`
- name: `_stub_DxgkCreateDoorbell`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ba80`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bac9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003bac9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkCreateDoorbell` at `0x14003bb03`

## string_xrefs

- `0x14003baaf`: `NtDxgkCreateDoorbell`

## pseudocode

```c
__int64 __fastcall stub_DxgkCreateDoorbell(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkCreateDoorbell(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkCreateDoorbell(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[41] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ba80  sub     rsp, 48h
0x14003ba84  mov     [rsp+48h+var_28], rcx
0x14003ba89  mov     [rsp+48h+var_20], rdx
0x14003ba8e  mov     [rsp+48h+var_18], r8
0x14003ba93  mov     [rsp+48h+var_10], r9
0x14003ba98  mov     rcx, 14Dh
0x14003ba9f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003baa6  nop     dword ptr [rax+rax+00h]
0x14003baab  test    al, al
0x14003baad  jz      short loc_14003BB03
0x14003baaf  lea     rcx, aNtdxgkcreatedo; "NtDxgkCreateDoorbell"
0x14003bab6  mov     rdx, 14Dh
0x14003babd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003bac4  nop     dword ptr [rax+rax+00h]
0x14003bac9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003bad0  nop     dword ptr [rax+rax+00h]
0x14003bad5  test    al, al
0x14003bad7  jz      short loc_14003BB03
0x14003bad9  lea     rcx, W32pServiceTableFilter
0x14003bae0  mov     edx, cs:W32pServiceLimitFilter
0x14003bae6  mov     rax, 14Dh
0x14003baed  lea     rcx, [rcx+rdx*4]
0x14003baf1  movsx   eax, byte ptr [rcx+rax]
0x14003baf5  or      eax, eax
0x14003baf7  jle     short loc_14003BAFE
0x14003baf9  mov     eax, 0C000001Ch
0x14003bafe  add     rsp, 48h
0x14003bb02  retn
0x14003bb03  mov     rax, cs:__imp_NtDxgkCreateDoorbell
0x14003bb0a  mov     rcx, [rsp+48h+var_28]
0x14003bb0f  mov     rdx, [rsp+48h+var_20]
0x14003bb14  mov     r8, [rsp+48h+var_18]
0x14003bb19  mov     r9, [rsp+48h+var_10]
0x14003bb1e  add     rsp, 48h
0x14003bb22  jmp     rax
```
