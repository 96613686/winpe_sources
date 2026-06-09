# SetFileSecurityDescriptor(IBaseFileSystem *,ushort const *,BUFFER *)

- ea: `0x18001b218`
- end: `0x18001b2c6`
- name: `?SetFileSecurityDescriptor@@YAJPEAVIBaseFileSystem@@PEBGPEAVBUFFER@@@Z`
- size: `174`
- prototype: `signed int __fastcall(struct IBaseFileSystem *, const unsigned __int16 *, PSECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180011aec`

## callees

- `0x18001b218`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18001b28c`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18001b28c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b26c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b26c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b2ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b2ae`

## pseudocode

```c
signed int __fastcall SetFileSecurityDescriptor(
        struct IBaseFileSystem *a1,
        const unsigned __int16 *a2,
        PSECURITY_DESCRIPTOR *a3)
{
  void *v4; // rax
  void *v5; // rdi
  signed int result; // eax
  unsigned int v7; // ebx
  signed int LastError; // eax

  v4 = (void *)(*(__int64 (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, __int64, __int64, _QWORD, int, int, _QWORD))(*(_QWORD *)a1 + 72LL))(
                 a1,
                 a2,
                 1442070,
                 7,
                 0,
                 3,
                 128,
                 0);
  v5 = v4;
  if ( v4 == (void *)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v7 = 0;
    if ( !SetKernelObjectSecurity(v4, 4u, a3[4]) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v5);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18001b218  mov     r11, rsp
0x18001b21b  mov     [r11+8], rbx
0x18001b21f  mov     [r11+10h], rsi
0x18001b223  push    rdi
0x18001b224  sub     rsp, 50h
0x18001b228  mov     rax, [rcx]
0x18001b22b  mov     rsi, r8
0x18001b22e  mov     qword ptr [r11-20h], 0
0x18001b236  mov     r9d, 7
0x18001b23c  mov     [rsp+58h+var_28], 80h
0x18001b244  mov     r8d, 160116h
0x18001b24a  mov     [rsp+58h+var_30], 3
0x18001b252  mov     rax, [rax+48h]
0x18001b256  mov     qword ptr [r11-38h], 0
0x18001b25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b263  mov     rdi, rax
0x18001b266  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b26a  jnz     short loc_18001B280
0x18001b26c  call    cs:__imp_GetLastError
0x18001b272  test    eax, eax
0x18001b274  jle     short loc_18001B2B6
0x18001b276  movzx   eax, ax
0x18001b279  or      eax, 80070000h
0x18001b27e  jmp     short loc_18001B2B6
0x18001b280  mov     r8, [rsi+20h]; SecurityDescriptor
0x18001b284  xor     ebx, ebx
0x18001b286  mov     rcx, rdi; Handle
0x18001b289  lea     edx, [rbx+4]; SecurityInformation
0x18001b28c  call    cs:__imp_SetKernelObjectSecurity
0x18001b292  test    eax, eax
0x18001b294  jnz     short loc_18001B2AB
0x18001b296  call    cs:__imp_GetLastError
0x18001b29c  mov     ebx, eax
0x18001b29e  test    eax, eax
0x18001b2a0  jle     short loc_18001B2AB
0x18001b2a2  movzx   ebx, ax
0x18001b2a5  or      ebx, 80070000h
0x18001b2ab  mov     rcx, rdi; hObject
0x18001b2ae  call    cs:__imp_CloseHandle
0x18001b2b4  mov     eax, ebx
0x18001b2b6  mov     rbx, [rsp+58h+arg_0]
0x18001b2bb  mov     rsi, [rsp+58h+arg_8]
0x18001b2c0  add     rsp, 50h
0x18001b2c4  pop     rdi
0x18001b2c5  retn
```
