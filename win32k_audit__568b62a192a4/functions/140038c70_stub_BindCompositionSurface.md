# _stub_BindCompositionSurface

- ea: `0x140038c70`
- end: `0x140038d17`
- name: `_stub_BindCompositionSurface`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038c70`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038cb9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038cb9`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtBindCompositionSurface` at `0x140038cf3`

## string_xrefs

- `0x140038c9f`: `NtBindCompositionSurface`

## pseudocode

```c
__int64 __fastcall stub_BindCompositionSurface(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtBindCompositionSurface(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtBindCompositionSurface(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140038c70  sub     rsp, 48h
0x140038c74  mov     [rsp+48h+var_28], rcx
0x140038c79  mov     [rsp+48h+var_20], rdx
0x140038c7e  mov     [rsp+48h+var_18], r8
0x140038c83  mov     [rsp+48h+var_10], r9
0x140038c88  mov     rcx, 10Ah
0x140038c8f  call    cs:__imp_IsWin32KSyscallFiltered
0x140038c96  nop     dword ptr [rax+rax+00h]
0x140038c9b  test    al, al
0x140038c9d  jz      short loc_140038CF3
0x140038c9f  lea     rcx, aNtbindcomposit; "NtBindCompositionSurface"
0x140038ca6  mov     rdx, 10Ah
0x140038cad  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038cb4  nop     dword ptr [rax+rax+00h]
0x140038cb9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038cc0  nop     dword ptr [rax+rax+00h]
0x140038cc5  test    al, al
0x140038cc7  jz      short loc_140038CF3
0x140038cc9  lea     rcx, W32pServiceTableFilter
0x140038cd0  mov     edx, cs:W32pServiceLimitFilter
0x140038cd6  mov     rax, 10Ah
0x140038cdd  lea     rcx, [rcx+rdx*4]
0x140038ce1  movsx   eax, byte ptr [rcx+rax]
0x140038ce5  or      eax, eax
0x140038ce7  jle     short loc_140038CEE
0x140038ce9  mov     eax, 0C000001Ch
0x140038cee  add     rsp, 48h
0x140038cf2  retn
0x140038cf3  mov     rax, cs:__imp_NtBindCompositionSurface
0x140038cfa  mov     rcx, [rsp+48h+var_28]
0x140038cff  mov     rdx, [rsp+48h+var_20]
0x140038d04  mov     r8, [rsp+48h+var_18]
0x140038d09  mov     r9, [rsp+48h+var_10]
0x140038d0e  add     rsp, 48h
0x140038d12  jmp     rax
```
