# UpdateDirEntry

- ea: `0x180027504`
- end: `0x1800275ce`
- name: `UpdateDirEntry`
- size: `202`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000ee80`
- `0x180010448`
- `0x1800110d0`
- `0x180012a18`
- `0x180016770`
- `0x18001dc84`
- `0x180028c2c`
- `0x180028f78`
- `0x18002912c`

## callees

- `0x180011640`
- `0x180013514`
- `0x180017de0`
- `0x180027504`
- `0x1800276a4`
- `0x18002a590`

## pseudocode

```c
__int16 __fastcall UpdateDirEntry(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 result; // ax
  unsigned int TTDirectory; // esi
  __int16 v7; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+38h] [rbp-30h] BYREF

  v8 = 0;
  v7 = 0;
  if ( a3 > *(_DWORD *)(a1 + 8) )
    return 1000;
  TTDirectory = GetTTDirectory(a1, a2, &v8);
  if ( !TTDirectory )
    return 0;
  HIDWORD(v8) = a3;
  result = ZeroLongWordGap(a1, DWORD2(v8), a3, 0);
  if ( !result )
  {
    result = CalcChecksum(a1, DWORD2(v8), a3, (char *)&v8 + 4);
    if ( !result )
      return WriteGeneric(a1, (__int64)&v8, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, TTDirectory, &v7);
  }
  return result;
}

```

## disassembly

```asm
0x180027504  mov     [rsp+arg_18], rbx
0x180027509  push    rbp
0x18002750a  push    rsi
0x18002750b  push    rdi
0x18002750c  sub     rsp, 50h
0x180027510  mov     rax, cs:__security_cookie
0x180027517  xor     rax, rsp
0x18002751a  mov     [rsp+68h+var_20], rax
0x18002751f  xor     ebp, ebp
0x180027521  xorps   xmm0, xmm0
0x180027524  mov     edi, r8d
0x180027527  mov     rbx, rcx
0x18002752a  movups  [rsp+68h+var_30], xmm0
0x18002752f  mov     [rsp+68h+var_38], bp
0x180027534  cmp     r8d, [rcx+8]
0x180027538  jbe     short loc_180027541
0x18002753a  mov     eax, 3E8h
0x18002753f  jmp     short loc_1800275B1
0x180027541  lea     r8, [rsp+68h+var_30]
0x180027546  call    GetTTDirectory
0x18002754b  mov     esi, eax
0x18002754d  test    eax, eax
0x18002754f  jz      short loc_1800275AF
0x180027551  mov     edx, dword ptr [rsp+68h+var_30+8]
0x180027555  xor     r9d, r9d
0x180027558  mov     r8d, edi
0x18002755b  mov     dword ptr [rsp+68h+var_30+0Ch], edi
0x18002755f  mov     rcx, rbx
0x180027562  call    ZeroLongWordGap
0x180027567  test    ax, ax
0x18002756a  jnz     short loc_1800275B1
0x18002756c  mov     edx, dword ptr [rsp+68h+var_30+8]
0x180027570  lea     r9, [rsp+68h+var_30+4]
0x180027575  mov     r8d, edi
0x180027578  mov     rcx, rbx
0x18002757b  call    CalcChecksum
0x180027580  test    ax, ax
0x180027583  jnz     short loc_1800275B1
0x180027585  lea     rax, [rsp+68h+var_38]
0x18002758a  mov     r8d, 10h
0x180027590  mov     [rsp+68h+var_40], rax
0x180027595  lea     r9, DIRECTORY_CONTROL
0x18002759c  lea     rdx, [rsp+68h+var_30]
0x1800275a1  mov     [rsp+68h+var_48], esi
0x1800275a5  mov     rcx, rbx
0x1800275a8  call    WriteGeneric
0x1800275ad  jmp     short loc_1800275B1
0x1800275af  mov     eax, ebp
0x1800275b1  mov     rcx, [rsp+68h+var_20]
0x1800275b6  xor     rcx, rsp; StackCookie
0x1800275b9  call    __security_check_cookie
0x1800275be  mov     rbx, [rsp+68h+arg_18]
0x1800275c6  add     rsp, 50h
0x1800275ca  pop     rdi
0x1800275cb  pop     rsi
0x1800275cc  pop     rbp
0x1800275cd  retn
```
