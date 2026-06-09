# WdsGetFullPathName

- ea: `0x18001c280`
- end: `0x18001c3a1`
- name: `WdsGetFullPathName`
- size: `289`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180010620`

## callees

- `0x18000179c`
- `0x18001a28c`
- `0x18001c280`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c2da`
- `KERNEL32!GetLastError` at `0x18001c34f`
- `KERNEL32!GetLastError` at `0x18001c2da`
- `KERNEL32!GetLastError` at `0x18001c34f`
- `KERNEL32!GetFullPathNameW` at `0x18001c2c8`
- `KERNEL32!GetFullPathNameW` at `0x18001c33f`
- `KERNEL32!GetFullPathNameW` at `0x18001c2c8`
- `KERNEL32!GetFullPathNameW` at `0x18001c33f`

## pseudocode

```c
__int64 __fastcall WdsGetFullPathName(LPCWSTR lpFileName, WCHAR **a2)
{
  unsigned int v4; // ebx
  DWORD FullPathNameW; // eax
  unsigned __int64 v6; // rbp
  DWORD v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // r8

  v4 = 0;
  if ( lpFileName && *lpFileName && a2 )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    v6 = FullPathNameW;
    if ( FullPathNameW )
    {
      v10 = 2LL * FullPathNameW;
      if ( !is_mul_ok(v6, 2u) )
        v10 = -1;
      v11 = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v11;
      if ( v11 )
      {
        if ( GetFullPathNameW(lpFileName, v6, v11, 0) )
        {
          *a2 = v12;
        }
        else
        {
          LastError = GetLastError();
          v4 = ElValidateWin32_8(LastError, v14, v15, 4036);
          if ( !v4 )
            v4 = 31;
          operator delete(v12);
        }
      }
      else
      {
        return 8;
      }
    }
    else
    {
      v7 = GetLastError();
      v4 = ElValidateWin32_8(v7, v8, v9, 4016);
      if ( !v4 )
        return 31;
    }
  }
  else
  {
    return 87;
  }
  return v4;
}

```

## disassembly

```asm
0x18001c280  mov     [rsp+arg_0], rbx
0x18001c285  mov     [rsp+arg_8], rbp
0x18001c28a  mov     [rsp+arg_10], rsi
0x18001c28f  push    rdi
0x18001c290  push    r14
0x18001c292  push    r15
0x18001c294  sub     rsp, 20h
0x18001c298  xor     r15d, r15d
0x18001c29b  mov     r14, rdx
0x18001c29e  mov     rdi, rcx
0x18001c2a1  mov     ebx, r15d
0x18001c2a4  test    rcx, rcx
0x18001c2a7  jz      loc_18001C380
0x18001c2ad  cmp     [rcx], r15w
0x18001c2b1  jz      loc_18001C380
0x18001c2b7  test    rdx, rdx
0x18001c2ba  jz      loc_18001C380
0x18001c2c0  xor     r9d, r9d; lpFilePart
0x18001c2c3  xor     r8d, r8d; lpBuffer
0x18001c2c6  xor     edx, edx; nBufferLength
0x18001c2c8  call    cs:__imp_GetFullPathNameW
0x18001c2cf  nop     dword ptr [rax+rax+00h]
0x18001c2d4  mov     ebp, eax
0x18001c2d6  test    eax, eax
0x18001c2d8  jnz     short loc_18001C305
0x18001c2da  call    cs:__imp_GetLastError
0x18001c2e1  nop     dword ptr [rax+rax+00h]
0x18001c2e6  mov     ecx, eax
0x18001c2e8  mov     r9d, 0FB0h
0x18001c2ee  call    ElValidateWin32_8
0x18001c2f3  mov     ebx, eax
0x18001c2f5  test    eax, eax
0x18001c2f7  jnz     loc_18001C385
0x18001c2fd  lea     ebx, [rax+1Fh]
0x18001c300  jmp     loc_18001C385
0x18001c305  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c30c  mov     eax, 2
0x18001c311  mul     rbp
0x18001c314  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c31b  cmovo   rax, rcx
0x18001c31f  mov     rcx, rax; unsigned __int64
0x18001c322  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001c327  mov     rsi, rax
0x18001c32a  test    rax, rax
0x18001c32d  jnz     short loc_18001C334
0x18001c32f  lea     ebx, [rax+8]
0x18001c332  jmp     short loc_18001C385
0x18001c334  xor     r9d, r9d; lpFilePart
0x18001c337  mov     r8, rsi; lpBuffer
0x18001c33a  mov     edx, ebp; nBufferLength
0x18001c33c  mov     rcx, rdi; lpFileName
0x18001c33f  call    cs:__imp_GetFullPathNameW
0x18001c346  nop     dword ptr [rax+rax+00h]
0x18001c34b  test    eax, eax
0x18001c34d  jnz     short loc_18001C37B
0x18001c34f  call    cs:__imp_GetLastError
0x18001c356  nop     dword ptr [rax+rax+00h]
0x18001c35b  mov     ecx, eax
0x18001c35d  mov     r9d, 0FC4h
0x18001c363  call    ElValidateWin32_8
0x18001c368  mov     ebx, eax
0x18001c36a  test    eax, eax
0x18001c36c  jnz     short loc_18001C371
0x18001c36e  lea     ebx, [rax+1Fh]
0x18001c371  mov     rcx, rsi; lpMem
0x18001c374  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c379  jmp     short loc_18001C385
0x18001c37b  mov     [r14], rsi
0x18001c37e  jmp     short loc_18001C385
0x18001c380  mov     ebx, 57h ; 'W'
0x18001c385  mov     rbp, [rsp+38h+arg_8]
0x18001c38a  mov     eax, ebx
0x18001c38c  mov     rbx, [rsp+38h+arg_0]
0x18001c391  mov     rsi, [rsp+38h+arg_10]
0x18001c396  add     rsp, 20h
0x18001c39a  pop     r15
0x18001c39c  pop     r14
0x18001c39e  pop     rdi
0x18001c39f  retn
```
