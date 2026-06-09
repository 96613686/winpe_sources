# _stub_GdiDdDDICreateKeyedMutex

- ea: `0x140041a80`
- end: `0x140041b27`
- name: `_stub_GdiDdDDICreateKeyedMutex`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041a80`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041ac9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041ac9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateKeyedMutex` at `0x140041b03`

## string_xrefs

- `0x140041aaf`: `NtGdiDdDDICreateKeyedMutex`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateKeyedMutex(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateKeyedMutex(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateKeyedMutex(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[58] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041a80  sub     rsp, 48h
0x140041a84  mov     [rsp+48h+var_28], rcx
0x140041a89  mov     [rsp+48h+var_20], rdx
0x140041a8e  mov     [rsp+48h+var_18], r8
0x140041a93  mov     [rsp+48h+var_10], r9
0x140041a98  mov     rcx, 1D6h
0x140041a9f  call    cs:__imp_IsWin32KSyscallFiltered
0x140041aa6  nop     dword ptr [rax+rax+00h]
0x140041aab  test    al, al
0x140041aad  jz      short loc_140041B03
0x140041aaf  lea     rcx, aNtgdiddddicrea_7; "NtGdiDdDDICreateKeyedMutex"
0x140041ab6  mov     rdx, 1D6h
0x140041abd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041ac4  nop     dword ptr [rax+rax+00h]
0x140041ac9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041ad0  nop     dword ptr [rax+rax+00h]
0x140041ad5  test    al, al
0x140041ad7  jz      short loc_140041B03
0x140041ad9  lea     rcx, W32pServiceTableFilter
0x140041ae0  mov     edx, cs:W32pServiceLimitFilter
0x140041ae6  mov     rax, 1D6h
0x140041aed  lea     rcx, [rcx+rdx*4]
0x140041af1  movsx   eax, byte ptr [rcx+rax]
0x140041af5  or      eax, eax
0x140041af7  jle     short loc_140041AFE
0x140041af9  mov     eax, 0C000001Ch
0x140041afe  add     rsp, 48h
0x140041b02  retn
0x140041b03  mov     rax, cs:__imp_NtGdiDdDDICreateKeyedMutex
0x140041b0a  mov     rcx, [rsp+48h+var_28]
0x140041b0f  mov     rdx, [rsp+48h+var_20]
0x140041b14  mov     r8, [rsp+48h+var_18]
0x140041b19  mov     r9, [rsp+48h+var_10]
0x140041b1e  add     rsp, 48h
0x140041b22  jmp     rax
```
