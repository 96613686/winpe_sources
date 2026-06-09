# _stub_GdiDdDDICreateOutputDupl

- ea: `0x140041be0`
- end: `0x140041c87`
- name: `_stub_GdiDdDDICreateOutputDupl`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041be0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041c29`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140041c29`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateOutputDupl` at `0x140041c63`

## string_xrefs

- `0x140041c0f`: `NtGdiDdDDICreateOutputDupl`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateOutputDupl(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateOutputDupl(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateOutputDupl(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[59] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041be0  sub     rsp, 48h
0x140041be4  mov     [rsp+48h+var_28], rcx
0x140041be9  mov     [rsp+48h+var_20], rdx
0x140041bee  mov     [rsp+48h+var_18], r8
0x140041bf3  mov     [rsp+48h+var_10], r9
0x140041bf8  mov     rcx, 1D8h
0x140041bff  call    cs:__imp_IsWin32KSyscallFiltered
0x140041c06  nop     dword ptr [rax+rax+00h]
0x140041c0b  test    al, al
0x140041c0d  jz      short loc_140041C63
0x140041c0f  lea     rcx, aNtgdiddddicrea_9; "NtGdiDdDDICreateOutputDupl"
0x140041c16  mov     rdx, 1D8h
0x140041c1d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140041c24  nop     dword ptr [rax+rax+00h]
0x140041c29  call    cs:__imp_PsIsWin32KFilterEnabled
0x140041c30  nop     dword ptr [rax+rax+00h]
0x140041c35  test    al, al
0x140041c37  jz      short loc_140041C63
0x140041c39  lea     rcx, W32pServiceTableFilter
0x140041c40  mov     edx, cs:W32pServiceLimitFilter
0x140041c46  mov     rax, 1D8h
0x140041c4d  lea     rcx, [rcx+rdx*4]
0x140041c51  movsx   eax, byte ptr [rcx+rax]
0x140041c55  or      eax, eax
0x140041c57  jle     short loc_140041C5E
0x140041c59  mov     eax, 0C000001Ch
0x140041c5e  add     rsp, 48h
0x140041c62  retn
0x140041c63  mov     rax, cs:__imp_NtGdiDdDDICreateOutputDupl
0x140041c6a  mov     rcx, [rsp+48h+var_28]
0x140041c6f  mov     rdx, [rsp+48h+var_20]
0x140041c74  mov     r8, [rsp+48h+var_18]
0x140041c79  mov     r9, [rsp+48h+var_10]
0x140041c7e  add     rsp, 48h
0x140041c82  jmp     rax
```
