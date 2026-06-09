# CreateSharedFileW

- ea: `0x180022ca8`
- end: `0x180022d6b`
- name: `CreateSharedFileW`
- size: `195`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwShareMode, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180023284`

## callees

- `0x180022698`
- `0x180022b80`
- `0x180022ca8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022d40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022d40`

## pseudocode

```c
HANDLE __fastcall CreateSharedFileW(
        LPCWSTR lpFileName,
        DWORD dwShareMode,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        int a5)
{
  struct _SECURITY_ATTRIBUTES *v5; // rbx
  struct _ACL *v10; // rdi
  HANDLE FileW; // rbx
  __int128 v13; // [rsp+40h] [rbp-78h] BYREF
  __int64 v14; // [rsp+50h] [rbp-68h]
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v16; // [rsp+78h] [rbp-40h]

  v5 = 0;
  v14 = 0;
  v16 = 0;
  v13 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( a5 )
  {
    v10 = 0;
  }
  else
  {
    v10 = BuildCustomizedSD(pSecurityDescriptor);
    if ( v10 )
    {
      LODWORD(v14) = 0;
      *((_QWORD *)&v13 + 1) = pSecurityDescriptor;
      v5 = (struct _SECURITY_ATTRIBUTES *)&v13;
      LODWORD(v13) = 24;
    }
  }
  FileW = CreateFileW(lpFileName, 0xC0000000, dwShareMode, v5, dwCreationDisposition, dwFlagsAndAttributes, 0);
  FreeAdministratorSD(v10);
  return FileW;
}

```

## disassembly

```asm
0x180022ca8  push    rbx
0x180022caa  push    rbp
0x180022cab  push    rsi
0x180022cac  push    rdi
0x180022cad  push    r14
0x180022caf  push    r15
0x180022cb1  sub     rsp, 88h
0x180022cb8  xor     eax, eax
0x180022cba  xorps   xmm1, xmm1
0x180022cbd  xor     ebx, ebx
0x180022cbf  mov     [rsp+0B8h+var_68], rax
0x180022cc4  xorps   xmm0, xmm0
0x180022cc7  mov     esi, r9d
0x180022cca  mov     ebp, r8d
0x180022ccd  mov     r14d, edx
0x180022cd0  mov     r15, rcx
0x180022cd3  mov     [rsp+0B8h+var_40], rax
0x180022cd8  movups  [rsp+0B8h+var_78], xmm0
0x180022cdd  movups  [rsp+0B8h+pSecurityDescriptor], xmm1
0x180022ce2  movups  [rsp+0B8h+var_50], xmm1
0x180022ce7  cmp     [rsp+0B8h+arg_20], eax
0x180022cee  jnz     short loc_180022D1F
0x180022cf0  lea     rcx, [rsp+0B8h+pSecurityDescriptor]; pSecurityDescriptor
0x180022cf5  call    ?BuildCustomizedSD@@YAPEAXPEAX@Z; BuildCustomizedSD(void *)
0x180022cfa  mov     rdi, rax
0x180022cfd  test    rax, rax
0x180022d00  jz      short loc_180022D21
0x180022d02  lea     rax, [rsp+0B8h+pSecurityDescriptor]
0x180022d07  mov     dword ptr [rsp+0B8h+var_68], ebx
0x180022d0b  mov     qword ptr [rsp+0B8h+var_78+8], rax
0x180022d10  lea     rbx, [rsp+0B8h+var_78]
0x180022d15  mov     dword ptr [rsp+0B8h+var_78], 18h
0x180022d1d  jmp     short loc_180022D21
0x180022d1f  xor     edi, edi
0x180022d21  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x180022d2a  mov     r9, rbx; lpSecurityAttributes
0x180022d2d  mov     [rsp+0B8h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180022d31  mov     r8d, r14d; dwShareMode
0x180022d34  mov     edx, 0C0000000h; dwDesiredAccess
0x180022d39  mov     [rsp+0B8h+dwCreationDisposition], ebp; dwCreationDisposition
0x180022d3d  mov     rcx, r15; lpFileName
0x180022d40  call    cs:__imp_CreateFileW
0x180022d47  nop     dword ptr [rax+rax+00h]
0x180022d4c  mov     rcx, rdi; lpMem
0x180022d4f  mov     rbx, rax
0x180022d52  call    ?FreeAdministratorSD@@YAXPEAX@Z; FreeAdministratorSD(void *)
0x180022d57  mov     rax, rbx
0x180022d5a  add     rsp, 88h
0x180022d61  pop     r15
0x180022d63  pop     r14
0x180022d65  pop     rdi
0x180022d66  pop     rsi
0x180022d67  pop     rbp
0x180022d68  pop     rbx
0x180022d69  retn
```
