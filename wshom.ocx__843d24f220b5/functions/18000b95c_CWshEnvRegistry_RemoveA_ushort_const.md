# CWshEnvRegistry::RemoveA(ushort const *)

- ea: `0x18000b95c`
- end: `0x18000ba12`
- name: `?RemoveA@CWshEnvRegistry@@AEAAJPEBG@Z`
- size: `182`
- prototype: `int(CWshEnvRegistry *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000b8a0`

## callees

- `0x1800059f8`
- `0x180006124`
- `0x18000b95c`
- `0x180010250`

## import_xrefs

- `ADVAPI32!RegDeleteValueA` at `0x18000b9c4`
- `ADVAPI32!RegDeleteValueA` at `0x18000b9c4`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::RemoveA(HKEY *this, const unsigned __int16 *a2)
{
  signed int v3; // ebx
  LSTATUS v4; // eax
  LPCSTR lpValueName; // [rsp+30h] [rbp-128h] BYREF
  void *Block; // [rsp+38h] [rbp-120h] BYREF
  char v8[256]; // [rsp+40h] [rbp-118h] BYREF

  lpValueName = 0;
  Block = 0;
  v3 = PWSZToPSZ(a2, v8, 256, (char **)&Block, (char **)&lpValueName);
  if ( v3 >= 0 )
  {
    v4 = RegDeleteValueA(this[9], lpValueName);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
      v3 = 0;
  }
  if ( Block )
    operator delete(Block);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b95c  mov     [rsp+arg_10], rbx
0x18000b961  push    rdi
0x18000b962  sub     rsp, 150h
0x18000b969  mov     rax, cs:__security_cookie
0x18000b970  xor     rax, rsp
0x18000b973  mov     [rsp+158h+var_18], rax
0x18000b97b  mov     rdi, rcx
0x18000b97e  mov     [rsp+158h+lpValueName], 0
0x18000b987  mov     rax, rdx
0x18000b98a  mov     [rsp+158h+Block], 0
0x18000b993  lea     rcx, [rsp+158h+lpValueName]
0x18000b998  mov     r8d, 100h; int
0x18000b99e  mov     [rsp+158h+var_138], rcx; char **
0x18000b9a3  lea     r9, [rsp+158h+Block]; char **
0x18000b9a8  mov     rcx, rax; lpWideCharStr
0x18000b9ab  lea     rdx, [rsp+158h+var_118]; char *
0x18000b9b0  call    ?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z; PWSZToPSZ(ushort const *,char *,long,char * *,char * *)
0x18000b9b5  mov     ebx, eax
0x18000b9b7  test    eax, eax
0x18000b9b9  js      short loc_18000B9E0
0x18000b9bb  mov     rdx, [rsp+158h+lpValueName]; lpValueName
0x18000b9c0  mov     rcx, [rdi+48h]; hKey
0x18000b9c4  call    cs:__imp_RegDeleteValueA
0x18000b9ca  mov     ebx, eax
0x18000b9cc  test    eax, eax
0x18000b9ce  jle     short loc_18000B9D9
0x18000b9d0  movzx   ebx, ax
0x18000b9d3  or      ebx, 80070000h
0x18000b9d9  xor     eax, eax
0x18000b9db  test    ebx, ebx
0x18000b9dd  cmovns  ebx, eax
0x18000b9e0  mov     rcx, [rsp+158h+Block]; Block
0x18000b9e5  test    rcx, rcx
0x18000b9e8  jz      short loc_18000B9EF
0x18000b9ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b9ef  mov     eax, ebx
0x18000b9f1  mov     rcx, [rsp+158h+var_18]
0x18000b9f9  xor     rcx, rsp; StackCookie
0x18000b9fc  call    __security_check_cookie
0x18000ba01  mov     rbx, [rsp+158h+arg_10]
0x18000ba09  add     rsp, 150h
0x18000ba10  pop     rdi
0x18000ba11  retn
```
