# CTempFile_Global::GetCryptContext(unsigned __int64 *)

- ea: `0x180029c80`
- end: `0x180029d01`
- name: `?GetCryptContext@CTempFile_Global@@QEAAJPEA_K@Z`
- size: `129`
- prototype: `__int64 __fastcall(CTempFile_Global *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180029d08`

## callees

- `0x180029c80`

## import_xrefs

- `ADVAPI32!CryptAcquireContextA` at `0x180029cc9`
- `ADVAPI32!CryptAcquireContextA` at `0x180029cc9`
- `KERNEL32!GetLastError` at `0x180029cd3`
- `KERNEL32!GetLastError` at `0x180029cd3`

## pseudocode

```c
__int64 __fastcall CTempFile_Global::GetCryptContext(CTempFile_Global *this, unsigned __int64 *a2)
{
  unsigned int v3; // ebx
  unsigned __int64 v4; // rax
  signed int LastError; // eax

  if ( a2 )
  {
    v4 = phProv;
    v3 = 0;
    *a2 = 0;
    if ( v4 )
    {
      *a2 = v4;
    }
    else if ( CryptAcquireContextA(&phProv, 0, 0, 1u, 0xF0000040) )
    {
      *a2 = phProv;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180029c80  mov     [rsp+arg_0], rbx
0x180029c85  push    rdi
0x180029c86  sub     rsp, 30h
0x180029c8a  mov     rdi, rdx
0x180029c8d  test    rdx, rdx
0x180029c90  jnz     short loc_180029C99
0x180029c92  mov     ebx, 80070057h
0x180029c97  jmp     short loc_180029CF4
0x180029c99  mov     rax, cs:phProv
0x180029ca0  xor     ebx, ebx
0x180029ca2  mov     [rdx], rbx
0x180029ca5  test    rax, rax
0x180029ca8  jz      short loc_180029CAF
0x180029caa  mov     [rdx], rax
0x180029cad  jmp     short loc_180029CF4
0x180029caf  mov     r9d, 1; dwProvType
0x180029cb5  mov     [rsp+38h+dwFlags], 0F0000040h; dwFlags
0x180029cbd  xor     r8d, r8d; szProvider
0x180029cc0  lea     rcx, phProv; phProv
0x180029cc7  xor     edx, edx; szContainer
0x180029cc9  call    cs:__imp_CryptAcquireContextA
0x180029ccf  test    eax, eax
0x180029cd1  jnz     short loc_180029CEA
0x180029cd3  call    cs:__imp_GetLastError
0x180029cd9  mov     ebx, eax
0x180029cdb  test    eax, eax
0x180029cdd  jle     short loc_180029CF4
0x180029cdf  movzx   ebx, ax
0x180029ce2  or      ebx, 80070000h
0x180029ce8  jmp     short loc_180029CF4
0x180029cea  mov     rcx, cs:phProv
0x180029cf1  mov     [rdi], rcx
0x180029cf4  mov     eax, ebx
0x180029cf6  mov     rbx, [rsp+38h+arg_0]
0x180029cfb  add     rsp, 30h
0x180029cff  pop     rdi
0x180029d00  retn
```
