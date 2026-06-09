# _stub_GdiDdDDIOpenKeyedMutexFromNtHandle

- ea: `0x140045020`
- end: `0x1400450c7`
- name: `_stub_GdiDdDDIOpenKeyedMutexFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140045020`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045069`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140045069`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtGdiDdDDIOpenKeyedMutexFromNtHandle` at `0x1400450a3`

## string_xrefs

- `0x14004504f`: `NtGdiDdDDIOpenKeyedMutexFromNtHandle`

## pseudocode

```c
__int64 __fastcall stub_GdiDdDDIOpenKeyedMutexFromNtHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiDdDDIOpenKeyedMutexFromNtHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiDdDDIOpenKeyedMutexFromNtHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[68] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140045020  sub     rsp, 48h
0x140045024  mov     [rsp+48h+var_28], rcx
0x140045029  mov     [rsp+48h+var_20], rdx
0x14004502e  mov     [rsp+48h+var_18], r8
0x140045033  mov     [rsp+48h+var_10], r9
0x140045038  mov     rcx, 224h
0x14004503f  call    cs:__imp_IsWin32KSyscallFiltered
0x140045046  nop     dword ptr [rax+rax+00h]
0x14004504b  test    al, al
0x14004504d  jz      short loc_1400450A3
0x14004504f  lea     rcx, aNtgdiddddiopen_5; "NtGdiDdDDIOpenKeyedMutexFromNtHandle"
0x140045056  mov     rdx, 224h
0x14004505d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140045064  nop     dword ptr [rax+rax+00h]
0x140045069  call    cs:__imp_PsIsWin32KFilterEnabled
0x140045070  nop     dword ptr [rax+rax+00h]
0x140045075  test    al, al
0x140045077  jz      short loc_1400450A3
0x140045079  lea     rcx, W32pServiceTableFilter
0x140045080  mov     edx, cs:W32pServiceLimitFilter
0x140045086  mov     rax, 224h
0x14004508d  lea     rcx, [rcx+rdx*4]
0x140045091  movsx   eax, byte ptr [rcx+rax]
0x140045095  or      eax, eax
0x140045097  jle     short loc_14004509E
0x140045099  mov     eax, 0C000001Ch
0x14004509e  add     rsp, 48h
0x1400450a2  retn
0x1400450a3  mov     rax, cs:__imp_NtGdiDdDDIOpenKeyedMutexFromNtHandle
0x1400450aa  mov     rcx, [rsp+48h+var_28]
0x1400450af  mov     rdx, [rsp+48h+var_20]
0x1400450b4  mov     r8, [rsp+48h+var_18]
0x1400450b9  mov     r9, [rsp+48h+var_10]
0x1400450be  add     rsp, 48h
0x1400450c2  jmp     rax
```
