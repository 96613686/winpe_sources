# _stub_QueryCompositionSurfaceBinding

- ea: `0x140053ce0`
- end: `0x140053d87`
- name: `_stub_QueryCompositionSurfaceBinding`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140053ce0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053d29`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140053d29`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtQueryCompositionSurfaceBinding` at `0x140053d63`

## string_xrefs

- `0x140053d0f`: `NtQueryCompositionSurfaceBinding`

## pseudocode

```c
__int64 __fastcall stub_QueryCompositionSurfaceBinding(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtQueryCompositionSurfaceBinding(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtQueryCompositionSurfaceBinding(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[111] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140053ce0  sub     rsp, 48h
0x140053ce4  mov     [rsp+48h+var_28], rcx
0x140053ce9  mov     [rsp+48h+var_20], rdx
0x140053cee  mov     [rsp+48h+var_18], r8
0x140053cf3  mov     [rsp+48h+var_10], r9
0x140053cf8  mov     rcx, 37Fh
0x140053cff  call    cs:__imp_IsWin32KSyscallFiltered
0x140053d06  nop     dword ptr [rax+rax+00h]
0x140053d0b  test    al, al
0x140053d0d  jz      short loc_140053D63
0x140053d0f  lea     rcx, aNtquerycomposi_4; "NtQueryCompositionSurfaceBinding"
0x140053d16  mov     rdx, 37Fh
0x140053d1d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140053d24  nop     dword ptr [rax+rax+00h]
0x140053d29  call    cs:__imp_PsIsWin32KFilterEnabled
0x140053d30  nop     dword ptr [rax+rax+00h]
0x140053d35  test    al, al
0x140053d37  jz      short loc_140053D63
0x140053d39  lea     rcx, W32pServiceTableFilter
0x140053d40  mov     edx, cs:W32pServiceLimitFilter
0x140053d46  mov     rax, 37Fh
0x140053d4d  lea     rcx, [rcx+rdx*4]
0x140053d51  movsx   eax, byte ptr [rcx+rax]
0x140053d55  or      eax, eax
0x140053d57  jle     short loc_140053D5E
0x140053d59  mov     eax, 0C000001Ch
0x140053d5e  add     rsp, 48h
0x140053d62  retn
0x140053d63  mov     rax, cs:__imp_NtQueryCompositionSurfaceBinding
0x140053d6a  mov     rcx, [rsp+48h+var_28]
0x140053d6f  mov     rdx, [rsp+48h+var_20]
0x140053d74  mov     r8, [rsp+48h+var_18]
0x140053d79  mov     r9, [rsp+48h+var_10]
0x140053d7e  add     rsp, 48h
0x140053d82  jmp     rax
```
