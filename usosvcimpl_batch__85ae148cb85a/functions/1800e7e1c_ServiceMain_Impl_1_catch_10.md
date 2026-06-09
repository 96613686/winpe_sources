# _ServiceMain_Impl_::_1_::catch$10

- ea: `0x1800e7e1c`
- end: `0x1800e7e6a`
- name: `_ServiceMain_Impl_::_1_::catch$10`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800dff58`
- `0x1800e7e1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7e40`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e7e31`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e7e31`

## pseudocode

```c
__int64 __fastcall ServiceMain_Impl_::_1_::catch_10(__int64 a1, __int64 a2)
{
  SC_HANDLE v3; // rax

  v3 = OpenSCManagerW(0, 0, 1u);
  *(_QWORD *)(a2 + 48) = v3;
  if ( v3 || GetLastError() != 1115 )
    throw;
  return 0;
}

```

## disassembly

```asm
0x1800e7e1c  mov     [rsp+arg_8], rdx
0x1800e7e21  push    rbp
0x1800e7e22  sub     rsp, 20h
0x1800e7e26  mov     rbp, rdx
0x1800e7e29  xor     edx, edx; lpDatabaseName
0x1800e7e2b  xor     ecx, ecx; lpMachineName
0x1800e7e2d  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800e7e31  call    cs:__imp_OpenSCManagerW
0x1800e7e37  mov     [rbp+30h], rax
0x1800e7e3b  test    rax, rax
0x1800e7e3e  jnz     short loc_1800E7E59
0x1800e7e40  call    cs:__imp_GetLastError
0x1800e7e46  cmp     eax, 45Bh
0x1800e7e4b  jnz     short loc_1800E7E59
0x1800e7e4d  mov     rax, 0
0x1800e7e57  jmp     short loc_1800E7E63
0x1800e7e59  xor     edx, edx; pThrowInfo
0x1800e7e5b  xor     ecx, ecx; pExceptionObject
0x1800e7e5d  call    _CxxThrowException
0x1800e7e63  add     rsp, 20h
0x1800e7e67  pop     rbp
0x1800e7e68  retn
```
