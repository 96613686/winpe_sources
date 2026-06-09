# CWshEnvRegistry::put_ItemA(ushort const *,ushort const *)

- ea: `0x18000c8b8`
- end: `0x18000c9ed`
- name: `?put_ItemA@CWshEnvRegistry@@AEAAJPEBG0@Z`
- size: `309`
- prototype: `int(CWshEnvRegistry *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000c6d0`

## callees

- `0x1800059f8`
- `0x180006124`
- `0x18000c8b8`
- `0x180010250`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x18000c991`
- `ADVAPI32!RegSetValueExA` at `0x18000c991`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::put_ItemA(HKEY *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  char *v5; // rdi
  signed int v6; // ebx
  __int64 v7; // rax
  LSTATUS v8; // eax
  char *v10; // [rsp+30h] [rbp-D0h] BYREF
  BYTE *lpData; // [rsp+38h] [rbp-C8h] BYREF
  LPCSTR lpValueName; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  char v14[256]; // [rsp+50h] [rbp-B0h] BYREF
  char v15[256]; // [rsp+150h] [rbp+50h] BYREF

  lpValueName = 0;
  lpData = 0;
  v5 = 0;
  v10 = 0;
  Block = 0;
  v6 = PWSZToPSZ(a2, v14, 256, (char **)&Block, (char **)&lpValueName);
  if ( v6 >= 0 )
  {
    v6 = PWSZToPSZ(a3, v15, 256, &v10, (char **)&lpData);
    if ( v6 >= 0 )
    {
      if ( lpData )
      {
        v7 = -1;
        do
          ++v7;
        while ( lpData[v7] );
      }
      else
      {
        LODWORD(v7) = 0;
      }
      v8 = RegSetValueExA(this[9], lpValueName, 0, 2u, lpData, v7 + 1);
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 >= 0 )
        v6 = 0;
    }
    v5 = v10;
  }
  if ( Block )
    operator delete(Block);
  if ( v5 )
    operator delete(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c8b8  push    rbp
0x18000c8ba  push    rbx
0x18000c8bb  push    rsi
0x18000c8bc  push    rdi
0x18000c8bd  push    r14
0x18000c8bf  lea     rbp, [rsp-160h]
0x18000c8c7  sub     rsp, 260h
0x18000c8ce  mov     rax, cs:__security_cookie
0x18000c8d5  xor     rax, rsp
0x18000c8d8  mov     [rbp+180h+var_30], rax
0x18000c8df  mov     r14, rcx
0x18000c8e2  mov     [rsp+280h+lpValueName], 0
0x18000c8eb  mov     rax, rdx
0x18000c8ee  mov     [rsp+280h+var_248], 0
0x18000c8f7  lea     rcx, [rsp+280h+lpValueName]
0x18000c8fc  mov     rsi, r8
0x18000c8ff  mov     [rsp+280h+lpData], rcx; char **
0x18000c904  lea     r9, [rsp+280h+Block]; char **
0x18000c909  xor     edi, edi
0x18000c90b  lea     rdx, [rsp+280h+var_230]; char *
0x18000c910  mov     rcx, rax; lpWideCharStr
0x18000c913  mov     [rsp+280h+var_250], rdi
0x18000c918  mov     r8d, 100h; int
0x18000c91e  mov     [rsp+280h+Block], rdi
0x18000c923  call    ?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z; PWSZToPSZ(ushort const *,char *,long,char * *,char * *)
0x18000c928  mov     ebx, eax
0x18000c92a  test    eax, eax
0x18000c92c  js      loc_18000C9B2
0x18000c932  lea     rax, [rsp+280h+var_248]
0x18000c937  mov     r8d, 100h; int
0x18000c93d  lea     r9, [rsp+280h+var_250]; char **
0x18000c942  mov     [rsp+280h+lpData], rax; char **
0x18000c947  lea     rdx, [rbp+180h+var_130]; char *
0x18000c94b  mov     rcx, rsi; lpWideCharStr
0x18000c94e  call    ?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z; PWSZToPSZ(ushort const *,char *,long,char * *,char * *)
0x18000c953  mov     ebx, eax
0x18000c955  test    eax, eax
0x18000c957  js      short loc_18000C9AD
0x18000c959  mov     rcx, [rsp+280h+var_248]
0x18000c95e  test    rcx, rcx
0x18000c961  jz      short loc_18000C972
0x18000c963  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c967  inc     rax
0x18000c96a  cmp     [rcx+rax], dil
0x18000c96e  jnz     short loc_18000C967
0x18000c970  jmp     short loc_18000C974
0x18000c972  xor     eax, eax
0x18000c974  mov     rdx, [rsp+280h+lpValueName]; lpValueName
0x18000c979  inc     eax
0x18000c97b  mov     [rsp+280h+cbData], eax; cbData
0x18000c97f  mov     r9d, 2; dwType
0x18000c985  mov     [rsp+280h+lpData], rcx; lpData
0x18000c98a  xor     r8d, r8d; Reserved
0x18000c98d  mov     rcx, [r14+48h]; hKey
0x18000c991  call    cs:__imp_RegSetValueExA
0x18000c997  mov     ebx, eax
0x18000c999  test    eax, eax
0x18000c99b  jle     short loc_18000C9A6
0x18000c99d  movzx   ebx, ax
0x18000c9a0  or      ebx, 80070000h
0x18000c9a6  xor     eax, eax
0x18000c9a8  test    ebx, ebx
0x18000c9aa  cmovns  ebx, eax
0x18000c9ad  mov     rdi, [rsp+280h+var_250]
0x18000c9b2  mov     rcx, [rsp+280h+Block]; Block
0x18000c9b7  test    rcx, rcx
0x18000c9ba  jz      short loc_18000C9C1
0x18000c9bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c9c1  test    rdi, rdi
0x18000c9c4  jz      short loc_18000C9CE
0x18000c9c6  mov     rcx, rdi; Block
0x18000c9c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c9ce  mov     eax, ebx
0x18000c9d0  mov     rcx, [rbp+180h+var_30]
0x18000c9d7  xor     rcx, rsp; StackCookie
0x18000c9da  call    __security_check_cookie
0x18000c9df  add     rsp, 260h
0x18000c9e6  pop     r14
0x18000c9e8  pop     rdi
0x18000c9e9  pop     rsi
0x18000c9ea  pop     rbx
0x18000c9eb  pop     rbp
0x18000c9ec  retn
```
