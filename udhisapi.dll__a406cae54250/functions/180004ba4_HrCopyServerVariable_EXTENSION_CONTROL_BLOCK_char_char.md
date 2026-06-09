# HrCopyServerVariable(_EXTENSION_CONTROL_BLOCK *,char *,char * *)

- ea: `0x180004ba4`
- end: `0x180004c8d`
- name: `?HrCopyServerVariable@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEADPEAPEAD@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, char *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000512c`

## callees

- `0x180004ba4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004c4b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004c4b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004c04`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c63`

## pseudocode

```c
__int64 __fastcall HrCopyServerVariable(struct _EXTENSION_CONTROL_BLOCK *a1, char *a2, char **a3)
{
  void *v7; // rax
  void *v8; // rdi
  signed int v9; // ebx
  signed int LastError; // eax
  signed int v11; // eax
  size_t Size; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(Size) = 0;
  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  ((void (__fastcall *)(HCONN, char *, _QWORD, size_t *))a1->GetServerVariable)(a1->ConnID, a2, 0, &Size);
  if ( GetLastError() == 122 )
  {
    v7 = malloc((unsigned int)Size);
    v8 = v7;
    if ( v7 )
    {
      v9 = 0;
      if ( ((unsigned int (__fastcall *)(HCONN, char *, void *, size_t *))a1->GetServerVariable)(
             a1->ConnID,
             a2,
             v7,
             &Size) )
      {
        goto LABEL_9;
      }
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      free(v8);
      v8 = 0;
      if ( v9 >= 0 )
LABEL_9:
        *a3 = (char *)v8;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v11 = GetLastError();
    v9 = v11;
    if ( v11 > 0 )
      return (unsigned __int16)v11 | 0x80070000;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004ba4  mov     [rsp+arg_0], rbx
0x180004ba9  mov     [rsp+arg_8], rbp
0x180004bae  push    rsi
0x180004baf  push    rdi
0x180004bb0  push    r14
0x180004bb2  sub     rsp, 30h
0x180004bb6  mov     dword ptr [rsp+48h+Size], 0
0x180004bbe  mov     rsi, r8
0x180004bc1  mov     r14, rdx
0x180004bc4  mov     rbp, rcx
0x180004bc7  test    r8, r8
0x180004bca  jnz     short loc_180004BD6
0x180004bcc  mov     eax, 80070057h
0x180004bd1  jmp     loc_180004C7A
0x180004bd6  mov     qword ptr [r8], 0
0x180004bdd  lea     r9, [rsp+48h+Size]
0x180004be2  mov     rcx, [rcx+8]
0x180004be6  xor     r8d, r8d
0x180004be9  mov     rax, [rbp+0A0h]
0x180004bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf5  call    cs:__imp_GetLastError
0x180004bfb  cmp     eax, 7Ah ; 'z'
0x180004bfe  jnz     short loc_180004C63
0x180004c00  mov     ecx, dword ptr [rsp+48h+Size]; Size
0x180004c04  call    cs:__imp_malloc
0x180004c0a  mov     rdi, rax
0x180004c0d  test    rax, rax
0x180004c10  jz      short loc_180004C5C
0x180004c12  mov     rcx, [rbp+8]
0x180004c16  lea     r9, [rsp+48h+Size]
0x180004c1b  mov     r8, rax
0x180004c1e  mov     rdx, r14
0x180004c21  mov     rax, [rbp+0A0h]
0x180004c28  xor     ebx, ebx
0x180004c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c2f  test    eax, eax
0x180004c31  jnz     short loc_180004C57
0x180004c33  call    cs:__imp_GetLastError
0x180004c39  mov     ebx, eax
0x180004c3b  test    eax, eax
0x180004c3d  jle     short loc_180004C48
0x180004c3f  movzx   ebx, ax
0x180004c42  or      ebx, 80070000h
0x180004c48  mov     rcx, rdi; Block
0x180004c4b  call    cs:__imp_free
0x180004c51  xor     edi, edi
0x180004c53  test    ebx, ebx
0x180004c55  js      short loc_180004C78
0x180004c57  mov     [rsi], rdi
0x180004c5a  jmp     short loc_180004C78
0x180004c5c  mov     ebx, 8007000Eh
0x180004c61  jmp     short loc_180004C78
0x180004c63  call    cs:__imp_GetLastError
0x180004c69  mov     ebx, eax
0x180004c6b  test    eax, eax
0x180004c6d  jle     short loc_180004C78
0x180004c6f  movzx   ebx, ax
0x180004c72  or      ebx, 80070000h
0x180004c78  mov     eax, ebx
0x180004c7a  mov     rbx, [rsp+48h+arg_0]
0x180004c7f  mov     rbp, [rsp+48h+arg_8]
0x180004c84  add     rsp, 30h
0x180004c88  pop     r14
0x180004c8a  pop     rdi
0x180004c8b  pop     rsi
0x180004c8c  retn
```
