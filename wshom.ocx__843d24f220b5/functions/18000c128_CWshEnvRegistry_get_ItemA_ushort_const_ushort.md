# CWshEnvRegistry::get_ItemA(ushort const *,ushort * *)

- ea: `0x18000c128`
- end: `0x18000c2f0`
- name: `?get_ItemA@CWshEnvRegistry@@AEAAJPEBGPEAPEAG@Z`
- size: `456`
- prototype: `int(CWshEnvRegistry *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18000bfc0`

## callees

- `0x1800059f8`
- `0x1800060e4`
- `0x180006124`
- `0x180009b40`
- `0x18000c128`
- `0x180010250`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x18000c254`
- `ADVAPI32!RegQueryValueExA` at `0x18000c254`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18000c1b8`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18000c1b8`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::get_ItemA(CWshEnvRegistry *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HKEY v6; // rcx
  LSTATUS v7; // eax
  signed int v8; // ebx
  DWORD v9; // eax
  void *v10; // rax
  void *v11; // rdi
  BYTE *v12; // rsi
  LSTATUS v13; // eax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  LPCSTR lpValueName; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  char v19[256]; // [rsp+80h] [rbp-80h] BYREF
  char v20; // [rsp+180h] [rbp+80h] BYREF

  *a3 = 0;
  v6 = (HKEY)*((_QWORD *)this + 9);
  lpValueName = v19;
  Type = 0;
  cbMaxValueLen = 0;
  Block = 0;
  v7 = RegQueryInfoKeyA(v6, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    v9 = cbMaxValueLen + 1;
    cbMaxValueLen = v9;
    if ( v9 <= 0x100 )
    {
      v11 = 0;
      v12 = (BYTE *)&v20;
    }
    else
    {
      v10 = operator new(v9);
      v11 = v10;
      if ( !v10 )
        return (unsigned int)-2147024882;
      v12 = (BYTE *)v10;
    }
    v8 = PWSZToPSZ(a2, v19, 256, (char **)&Block, (char **)&lpValueName);
    if ( v8 >= 0 )
    {
      v13 = RegQueryValueExA(*((HKEY *)this + 9), lpValueName, 0, &Type, v12, &cbMaxValueLen);
      v8 = v13;
      if ( v13 == 2 )
      {
        *v12 = 0;
        v8 = 0;
        Type = 1;
      }
      else if ( v13 > 0 )
      {
        v8 = (unsigned __int16)v13 | 0x80070000;
      }
      if ( v8 >= 0 )
      {
        if ( Type - 1 <= 1 )
        {
          v8 = PSZToBSTR((LPCCH)v12, a3);
          if ( v8 >= 0 )
            v8 = 0;
        }
        else
        {
          v8 = -2147467259;
        }
      }
    }
    if ( Block )
      operator delete(Block);
    if ( v11 )
      operator delete(v11);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c128  mov     [rsp-8+arg_18], rbx
0x18000c12d  push    rbp
0x18000c12e  push    rsi
0x18000c12f  push    rdi
0x18000c130  push    r12
0x18000c132  push    r13
0x18000c134  push    r14
0x18000c136  push    r15
0x18000c138  lea     rbp, [rsp-190h]
0x18000c140  sub     rsp, 290h
0x18000c147  mov     rax, cs:__security_cookie
0x18000c14e  xor     rax, rsp
0x18000c151  mov     [rbp+1C0h+var_40], rax
0x18000c158  xor     r13d, r13d
0x18000c15b  lea     rax, [rbp+1C0h+var_240]
0x18000c15f  mov     [rsp+2C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000c164  mov     r15, r8
0x18000c167  mov     [rsp+2C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000c16c  mov     r12, rdx
0x18000c16f  mov     [r8], r13
0x18000c172  mov     r14, rcx
0x18000c175  mov     rcx, [rcx+48h]; hKey
0x18000c179  xor     r9d, r9d; lpReserved
0x18000c17c  mov     [rsp+2C0h+lpValueName], rax
0x18000c181  xor     r8d, r8d; lpcchClass
0x18000c184  lea     rax, [rsp+2C0h+cbMaxValueLen]
0x18000c189  mov     [rsp+2C0h+Type], r13d
0x18000c18e  mov     [rsp+2C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000c193  xor     edx, edx; lpClass
0x18000c195  mov     [rsp+2C0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000c19a  mov     [rsp+2C0h+lpcValues], r13; lpcValues
0x18000c19f  mov     [rsp+2C0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000c1a4  mov     [rsp+2C0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18000c1a9  mov     [rsp+2C0h+lpcSubKeys], r13; lpcSubKeys
0x18000c1ae  mov     [rsp+2C0h+cbMaxValueLen], r13d
0x18000c1b3  mov     [rsp+2C0h+Block], r13
0x18000c1b8  call    cs:__imp_RegQueryInfoKeyA
0x18000c1be  mov     ebx, eax
0x18000c1c0  test    eax, eax
0x18000c1c2  jle     short loc_18000C1CD
0x18000c1c4  movzx   ebx, ax
0x18000c1c7  or      ebx, 80070000h
0x18000c1cd  test    ebx, ebx
0x18000c1cf  js      loc_18000C2C4
0x18000c1d5  mov     eax, [rsp+2C0h+cbMaxValueLen]
0x18000c1d9  mov     ebx, 100h
0x18000c1de  inc     eax
0x18000c1e0  mov     [rsp+2C0h+cbMaxValueLen], eax
0x18000c1e4  cmp     eax, ebx
0x18000c1e6  jbe     short loc_18000C206
0x18000c1e8  mov     ecx, eax; Size
0x18000c1ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c1ef  mov     rdi, rax
0x18000c1f2  test    rax, rax
0x18000c1f5  jnz     short loc_18000C201
0x18000c1f7  mov     ebx, 8007000Eh
0x18000c1fc  jmp     loc_18000C2C4
0x18000c201  mov     rsi, rax
0x18000c204  jmp     short loc_18000C210
0x18000c206  mov     rdi, r13
0x18000c209  lea     rsi, [rbp+1C0h+var_140]
0x18000c210  lea     rax, [rsp+2C0h+lpValueName]
0x18000c215  mov     r8d, ebx; int
0x18000c218  lea     r9, [rsp+2C0h+Block]; char **
0x18000c21d  mov     [rsp+2C0h+lpcSubKeys], rax; char **
0x18000c222  lea     rdx, [rbp+1C0h+var_240]; char *
0x18000c226  mov     rcx, r12; lpWideCharStr
0x18000c229  call    ?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z; PWSZToPSZ(ushort const *,char *,long,char * *,char * *)
0x18000c22e  mov     ebx, eax
0x18000c230  test    eax, eax
0x18000c232  js      short loc_18000C2A8
0x18000c234  mov     rdx, [rsp+2C0h+lpValueName]; lpValueName
0x18000c239  lea     rax, [rsp+2C0h+cbMaxValueLen]
0x18000c23e  mov     rcx, [r14+48h]; hKey
0x18000c242  lea     r9, [rsp+2C0h+Type]; lpType
0x18000c247  mov     [rsp+2C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000c24c  xor     r8d, r8d; lpReserved
0x18000c24f  mov     [rsp+2C0h+lpcSubKeys], rsi; lpData
0x18000c254  call    cs:__imp_RegQueryValueExA
0x18000c25a  mov     ebx, eax
0x18000c25c  cmp     eax, 2
0x18000c25f  jnz     short loc_18000C271
0x18000c261  mov     [rsi], r13b
0x18000c264  mov     ebx, r13d
0x18000c267  mov     [rsp+2C0h+Type], 1
0x18000c26f  jmp     short loc_18000C27E
0x18000c271  test    eax, eax
0x18000c273  jle     short loc_18000C27E
0x18000c275  movzx   ebx, ax
0x18000c278  or      ebx, 80070000h
0x18000c27e  test    ebx, ebx
0x18000c280  js      short loc_18000C2A8
0x18000c282  mov     eax, [rsp+2C0h+Type]
0x18000c286  dec     eax
0x18000c288  cmp     eax, 1
0x18000c28b  jbe     short loc_18000C294
0x18000c28d  mov     ebx, 80004005h
0x18000c292  jmp     short loc_18000C2A8
0x18000c294  mov     rdx, r15; unsigned __int16 **
0x18000c297  mov     rcx, rsi; lpMultiByteStr
0x18000c29a  call    ?PSZToBSTR@@YAJPEBDPEAPEAG@Z; PSZToBSTR(char const *,ushort * *)
0x18000c29f  mov     ebx, eax
0x18000c2a1  test    eax, eax
0x18000c2a3  js      short loc_18000C2A8
0x18000c2a5  mov     ebx, r13d
0x18000c2a8  mov     rcx, [rsp+2C0h+Block]; Block
0x18000c2ad  test    rcx, rcx
0x18000c2b0  jz      short loc_18000C2B7
0x18000c2b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c2b7  test    rdi, rdi
0x18000c2ba  jz      short loc_18000C2C4
0x18000c2bc  mov     rcx, rdi; Block
0x18000c2bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c2c4  mov     eax, ebx
0x18000c2c6  mov     rcx, [rbp+1C0h+var_40]
0x18000c2cd  xor     rcx, rsp; StackCookie
0x18000c2d0  call    __security_check_cookie
0x18000c2d5  mov     rbx, [rsp+2C0h+arg_18]
0x18000c2dd  add     rsp, 290h
0x18000c2e4  pop     r15
0x18000c2e6  pop     r14
0x18000c2e8  pop     r13
0x18000c2ea  pop     r12
0x18000c2ec  pop     rdi
0x18000c2ed  pop     rsi
0x18000c2ee  pop     rbp
0x18000c2ef  retn
```
