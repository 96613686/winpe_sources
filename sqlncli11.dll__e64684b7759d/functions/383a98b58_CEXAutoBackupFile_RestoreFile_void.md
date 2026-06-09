# CEXAutoBackupFile::RestoreFile(void)

- ea: `0x383a98b58`
- end: `0x383a98c2e`
- name: `?RestoreFile@CEXAutoBackupFile@@QEAAJXZ`
- size: `214`
- prototype: `__int64 __fastcall(CEXAutoBackupFile *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x3839fb130`
- `0x383a98934`

## callees

- `0x383a98b58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a98b9b`
- `KERNEL32!GetLastError` at `0x383a98bc5`
- `KERNEL32!GetLastError` at `0x383a98b9b`
- `KERNEL32!GetLastError` at `0x383a98bc5`
- `KERNEL32!DeleteFileW` at `0x383a98bbb`
- `KERNEL32!DeleteFileW` at `0x383a98bbb`
- `KERNEL32!ReplaceFileW` at `0x383a98b91`
- `KERNEL32!ReplaceFileW` at `0x383a98b91`

## pseudocode

```c
__int64 __fastcall CEXAutoBackupFile::RestoreFile(CEXAutoBackupFile *this)
{
  const WCHAR *v1; // rdx
  const WCHAR *v3; // rcx
  signed int LastError; // eax
  signed int v5; // ebx
  signed int v6; // eax
  __int64 v7; // rdx

  v1 = (const WCHAR *)*((_QWORD *)this + 2);
  if ( !v1 )
    return 2147500037LL;
  v3 = (const WCHAR *)*((_QWORD *)this + 1);
  if ( !v3 )
    return 2147500037LL;
  if ( ReplaceFileW(v3, v1, 0, 0, 0, 0) )
  {
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v5 = LastError;
  }
  if ( v5 >= 0 )
  {
    if ( DeleteFileW(*((LPCWSTR *)this + 2)) )
    {
      v5 = 0;
    }
    else
    {
      v6 = GetLastError();
      v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        v5 = v6;
    }
  }
  if ( *((_QWORD *)this + 2) )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
  v7 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 2) = 0;
  if ( v7 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
  *((_QWORD *)this + 1) = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x383a98b58  mov     [rsp+arg_0], rbx
0x383a98b5d  push    rdi
0x383a98b5e  sub     rsp, 30h
0x383a98b62  mov     rdx, [rcx+10h]; lpReplacementFileName
0x383a98b66  mov     rdi, rcx
0x383a98b69  test    rdx, rdx
0x383a98b6c  jz      loc_383A98C1E
0x383a98b72  mov     rcx, [rcx+8]; lpReplacedFileName
0x383a98b76  test    rcx, rcx
0x383a98b79  jz      loc_383A98C1E
0x383a98b7f  and     [rsp+38h+var_10], 0
0x383a98b85  and     [rsp+38h+var_18], 0
0x383a98b8b  xor     r9d, r9d; dwReplaceFlags
0x383a98b8e  xor     r8d, r8d; lpBackupFileName
0x383a98b91  call    cs:__imp_ReplaceFileW
0x383a98b97  test    eax, eax
0x383a98b99  jnz     short loc_383A98BB1
0x383a98b9b  call    cs:__imp_GetLastError
0x383a98ba1  movzx   ebx, ax
0x383a98ba4  or      ebx, 80070000h
0x383a98baa  test    eax, eax
0x383a98bac  cmovle  ebx, eax
0x383a98baf  jmp     short loc_383A98BB3
0x383a98bb1  xor     ebx, ebx
0x383a98bb3  test    ebx, ebx
0x383a98bb5  js      short loc_383A98BDD
0x383a98bb7  mov     rcx, [rdi+10h]; lpFileName
0x383a98bbb  call    cs:__imp_DeleteFileW
0x383a98bc1  test    eax, eax
0x383a98bc3  jnz     short loc_383A98BDB
0x383a98bc5  call    cs:__imp_GetLastError
0x383a98bcb  movzx   ebx, ax
0x383a98bce  or      ebx, 80070000h
0x383a98bd4  test    eax, eax
0x383a98bd6  cmovle  ebx, eax
0x383a98bd9  jmp     short loc_383A98BDD
0x383a98bdb  xor     ebx, ebx
0x383a98bdd  mov     rdx, [rdi+10h]
0x383a98be1  test    rdx, rdx
0x383a98be4  jz      short loc_383A98BF6
0x383a98be6  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98bed  mov     rax, [rcx]
0x383a98bf0  call    qword ptr [rax+80h]
0x383a98bf6  mov     rdx, [rdi+8]
0x383a98bfa  and     qword ptr [rdi+10h], 0
0x383a98bff  test    rdx, rdx
0x383a98c02  jz      short loc_383A98C15
0x383a98c04  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98c0b  mov     r8, [rcx]
0x383a98c0e  call    qword ptr [r8+80h]
0x383a98c15  and     qword ptr [rdi+8], 0
0x383a98c1a  mov     eax, ebx
0x383a98c1c  jmp     short loc_383A98C23
0x383a98c1e  mov     eax, 80004005h
0x383a98c23  mov     rbx, [rsp+38h+arg_0]
0x383a98c28  add     rsp, 30h
0x383a98c2c  pop     rdi
0x383a98c2d  retn
```
