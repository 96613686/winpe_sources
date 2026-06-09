# _stub_GdiDdDDICreateContext

- ea: `0x140041280`
- end: `0x140041327`
- name: `_stub_GdiDdDDICreateContext`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140041280`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400412c9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x1400412c9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDICreateContext` at `0x140041303`

## string_xrefs

- `0x1400412af`: `NtGdiDdDDICreateContext`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDICreateContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDICreateContext(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDICreateContext(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[57] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140041280  sub     rsp, 48h
0x140041284  mov     [rsp+48h+var_28], rcx
0x140041289  mov     [rsp+48h+var_20], rdx
0x14004128e  mov     [rsp+48h+var_18], r8
0x140041293  mov     [rsp+48h+var_10], r9
0x140041298  mov     rcx, 1CDh
0x14004129f  call    cs:__imp_IsWin32KSyscallFiltered
0x1400412a6  nop     dword ptr [rax+rax+00h]
0x1400412ab  test    al, al
0x1400412ad  jz      short loc_140041303
0x1400412af  lea     rcx, aNtgdiddddicrea_1; "NtGdiDdDDICreateContext"
0x1400412b6  mov     rdx, 1CDh
0x1400412bd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x1400412c4  nop     dword ptr [rax+rax+00h]
0x1400412c9  call    cs:__imp_PsIsWin32KFilterEnabled
0x1400412d0  nop     dword ptr [rax+rax+00h]
0x1400412d5  test    al, al
0x1400412d7  jz      short loc_140041303
0x1400412d9  lea     rcx, W32pServiceTableFilter
0x1400412e0  mov     edx, cs:W32pServiceLimitFilter
0x1400412e6  mov     rax, 1CDh
0x1400412ed  lea     rcx, [rcx+rdx*4]
0x1400412f1  movsx   eax, byte ptr [rcx+rax]
0x1400412f5  or      eax, eax
0x1400412f7  jle     short loc_1400412FE
0x1400412f9  mov     eax, 0C000001Ch
0x1400412fe  add     rsp, 48h
0x140041302  retn
0x140041303  mov     rax, cs:__imp_NtGdiDdDDICreateContext
0x14004130a  mov     rcx, [rsp+48h+var_28]
0x14004130f  mov     rdx, [rsp+48h+var_20]
0x140041314  mov     r8, [rsp+48h+var_18]
0x140041319  mov     r9, [rsp+48h+var_10]
0x14004131e  add     rsp, 48h
0x140041322  jmp     rax
```
