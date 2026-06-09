# CreateSharedMemoryW

- ea: `0x180022d74`
- end: `0x180022e3a`
- name: `CreateSharedMemoryW`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001eef4`

## callees

- `0x180022698`
- `0x180022b80`
- `0x180022d74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e15`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180022df0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180022df0`

## pseudocode

```c
HANDLE __fastcall CreateSharedMemoryW(__int64 a1, const WCHAR *a2, _DWORD *a3)
{
  struct _SECURITY_ATTRIBUTES *v5; // rdi
  struct _ACL *v6; // rsi
  HANDLE FileMappingW; // rdi
  __int128 v9; // [rsp+30h] [rbp-68h] BYREF
  __int64 v10; // [rsp+40h] [rbp-58h]
  _OWORD pSecurityDescriptor[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v12; // [rsp+68h] [rbp-30h]

  v10 = 0;
  v12 = 0;
  v9 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v5 = 0;
  v6 = BuildCustomizedSD(pSecurityDescriptor);
  if ( v6 )
  {
    LODWORD(v10) = 0;
    *((_QWORD *)&v9 + 1) = pSecurityDescriptor;
    v5 = (struct _SECURITY_ATTRIBUTES *)&v9;
    LODWORD(v9) = 24;
  }
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, v5, 0x8000004u, 0, 0x8000u, a2);
  FreeAdministratorSD(v6);
  if ( !FileMappingW )
    return 0;
  if ( a3 )
    *a3 = GetLastError() == 183;
  return FileMappingW;
}

```

## disassembly

```asm
0x180022d74  push    rbx
0x180022d76  push    rbp
0x180022d77  push    rsi
0x180022d78  push    rdi
0x180022d79  sub     rsp, 78h
0x180022d7d  xor     eax, eax
0x180022d7f  lea     rcx, [rsp+98h+pSecurityDescriptor]; pSecurityDescriptor
0x180022d84  xorps   xmm1, xmm1
0x180022d87  mov     [rsp+98h+var_58], rax
0x180022d8c  xorps   xmm0, xmm0
0x180022d8f  mov     [rsp+98h+var_30], rax
0x180022d94  movups  [rsp+98h+var_68], xmm0
0x180022d99  mov     rbx, r8
0x180022d9c  mov     rbp, rdx
0x180022d9f  movups  [rsp+98h+pSecurityDescriptor], xmm1
0x180022da4  xor     edi, edi
0x180022da6  movups  [rsp+98h+var_40], xmm1
0x180022dab  call    ?BuildCustomizedSD@@YAPEAXPEAX@Z; BuildCustomizedSD(void *)
0x180022db0  mov     rsi, rax
0x180022db3  test    rax, rax
0x180022db6  jz      short loc_180022DD3
0x180022db8  lea     rax, [rsp+98h+pSecurityDescriptor]
0x180022dbd  mov     dword ptr [rsp+98h+var_58], edi
0x180022dc1  mov     qword ptr [rsp+98h+var_68+8], rax
0x180022dc6  lea     rdi, [rsp+98h+var_68]
0x180022dcb  mov     dword ptr [rsp+98h+var_68], 18h
0x180022dd3  mov     [rsp+98h+lpName], rbp; lpName
0x180022dd8  xor     r9d, r9d; dwMaximumSizeHigh
0x180022ddb  mov     r8d, 8000004h; flProtect
0x180022de1  mov     [rsp+98h+dwMaximumSizeLow], 8000h; dwMaximumSizeLow
0x180022de9  mov     rdx, rdi; lpFileMappingAttributes
0x180022dec  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180022df0  call    cs:__imp_CreateFileMappingW
0x180022df7  nop     dword ptr [rax+rax+00h]
0x180022dfc  mov     rcx, rsi; lpMem
0x180022dff  mov     rdi, rax
0x180022e02  call    ?FreeAdministratorSD@@YAXPEAX@Z; FreeAdministratorSD(void *)
0x180022e07  test    rdi, rdi
0x180022e0a  jnz     short loc_180022E10
0x180022e0c  xor     eax, eax
0x180022e0e  jmp     short loc_180022E30
0x180022e10  test    rbx, rbx
0x180022e13  jz      short loc_180022E2D
0x180022e15  call    cs:__imp_GetLastError
0x180022e1c  nop     dword ptr [rax+rax+00h]
0x180022e21  xor     ecx, ecx
0x180022e23  cmp     eax, 0B7h
0x180022e28  setz    cl
0x180022e2b  mov     [rbx], ecx
0x180022e2d  mov     rax, rdi
0x180022e30  add     rsp, 78h
0x180022e34  pop     rdi
0x180022e35  pop     rsi
0x180022e36  pop     rbp
0x180022e37  pop     rbx
0x180022e38  retn
```
