# AslEnvGetSystem32DirPathBuf

- ea: `0x14000f28c`
- end: `0x14000f3d2`
- name: `AslEnvGetSystem32DirPathBuf`
- size: `326`
- prototype: `__int64 __fastcall(_WORD *, __int64, _WORD *, __int16, __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000f158`
- `0x1400134e0`

## callees

- `0x14000f28c`
- `0x14001008c`
- `0x1400100c4`
- `0x1400103d8`
- `0x140011d6c`
- `0x14002e3e2`
- `0x14002e420`

## string_xrefs

- `0x14000f3bb`: `RtlStringCchCopyW failed [%x]`
- `0x14000f34e`: `AslPathToSystemPathBuf failed [%x]`
- `0x14000f35b`: `AslEnvGetSystem32DirPathBuf`
- `0x14000f396`: `AslPathCombine failed [%x]`

## pseudocode

```c
__int64 __fastcall AslEnvGetSystem32DirPathBuf(_WORD *a1, __int64 a2, _WORD *a3, __int16 a4, __int16 *a5)
{
  __int16 v9; // cx
  __int64 v10; // rax
  unsigned int v11; // ebx
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  unsigned __int16 v16[64]; // [rsp+30h] [rbp-B8h] BYREF

  memset_0(v16, 0, sizeof(v16));
  *a1 = 0;
  if ( a5 )
    v9 = *a5;
  else
    v9 = a4;
  v10 = 0;
  while ( word_140042040[8 * v10] != a4 || word_140042040[8 * v10 + 1] != v9 )
  {
    if ( (unsigned __int64)++v10 >= 8 )
      return (unsigned int)-1073741637;
  }
  v13 = AslPathToSystemPathBuf(v16, 0x40u, *(unsigned __int16 **)&word_140042040[8 * v10 + 4]);
  v11 = v13;
  if ( v13 >= 0 )
  {
    if ( a3 && *a3 )
    {
      v13 = AslPathCombine(v16, a3, a1, a2);
      v11 = v13;
      if ( v13 < 0 )
      {
        v14 = "AslPathCombine failed [%x]";
        v15 = 1585;
        goto LABEL_12;
      }
    }
    else
    {
      v13 = RtlStringCchCopyW(a1, a2, v16);
      v11 = v13;
      if ( v13 < 0 )
      {
        v14 = "RtlStringCchCopyW failed [%x]";
        v15 = 1593;
        goto LABEL_12;
      }
    }
    return 0;
  }
  v14 = "AslPathToSystemPathBuf failed [%x]";
  v15 = 1575;
LABEL_12:
  AslLogCallPrintf(1, "AslEnvGetSystem32DirPathBuf", v15, v14, v13);
  return v11;
}

```

## disassembly

```asm
0x14000f28c  push    rbx
0x14000f28e  push    rbp
0x14000f28f  push    rsi
0x14000f290  push    rdi
0x14000f291  push    r14
0x14000f293  sub     rsp, 0C0h
0x14000f29a  mov     rax, cs:__security_cookie
0x14000f2a1  xor     rax, rsp
0x14000f2a4  mov     [rsp+0E8h+var_38], rax
0x14000f2ac  mov     rdi, r8
0x14000f2af  mov     rbp, rdx
0x14000f2b2  mov     rsi, rcx
0x14000f2b5  xor     edx, edx; Val
0x14000f2b7  mov     r8d, 80h; Size
0x14000f2bd  lea     rcx, [rsp+0E8h+var_B8]; void *
0x14000f2c2  movzx   ebx, r9w
0x14000f2c6  call    memset_0
0x14000f2cb  mov     rcx, [rsp+0E8h+arg_20]
0x14000f2d3  xor     r14d, r14d
0x14000f2d6  mov     [rsi], r14w
0x14000f2da  test    rcx, rcx
0x14000f2dd  jz      short loc_14000F2E4
0x14000f2df  movzx   ecx, word ptr [rcx]
0x14000f2e2  jmp     short loc_14000F2E7
0x14000f2e4  movzx   ecx, bx
0x14000f2e7  mov     rax, r14
0x14000f2ea  lea     rdx, word_140042040
0x14000f2f1  mov     r8, rax
0x14000f2f4  add     r8, r8
0x14000f2f7  cmp     [rdx+r8*8], bx
0x14000f2fc  jnz     short loc_14000F306
0x14000f2fe  cmp     [rdx+r8*8+2], cx
0x14000f304  jz      short loc_14000F334
0x14000f306  inc     rax
0x14000f309  cmp     rax, 8
0x14000f30d  jb      short loc_14000F2F1
0x14000f30f  mov     ebx, 0C00000BBh
0x14000f314  mov     eax, ebx
0x14000f316  mov     rcx, [rsp+0E8h+var_38]
0x14000f31e  xor     rcx, rsp; StackCookie
0x14000f321  call    __security_check_cookie
0x14000f326  add     rsp, 0C0h
0x14000f32d  pop     r14
0x14000f32f  pop     rdi
0x14000f330  pop     rsi
0x14000f331  pop     rbp
0x14000f332  pop     rbx
0x14000f333  retn
0x14000f334  mov     r8, [rdx+r8*8+8]; unsigned __int16 *
0x14000f339  lea     rcx, [rsp+0E8h+var_B8]; unsigned __int16 *
0x14000f33e  mov     edx, 40h ; '@'; unsigned __int64
0x14000f343  call    AslPathToSystemPathBuf
0x14000f348  mov     ebx, eax
0x14000f34a  test    eax, eax
0x14000f34c  jns     short loc_14000F372
0x14000f34e  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x14000f355  mov     r8d, 627h
0x14000f35b  lea     rdx, aAslenvgetsyste; "AslEnvGetSystem32DirPathBuf"
0x14000f362  mov     [rsp+0E8h+var_C8], eax
0x14000f366  mov     ecx, 1
0x14000f36b  call    AslLogCallPrintf
0x14000f370  jmp     short loc_14000F314
0x14000f372  test    rdi, rdi
0x14000f375  jz      short loc_14000F3A5
0x14000f377  cmp     [rdi], r14w
0x14000f37b  jz      short loc_14000F3A5
0x14000f37d  mov     r9, rbp
0x14000f380  lea     rcx, [rsp+0E8h+var_B8]
0x14000f385  mov     r8, rsi
0x14000f388  mov     rdx, rdi
0x14000f38b  call    AslPathCombine
0x14000f390  mov     ebx, eax
0x14000f392  test    eax, eax
0x14000f394  jns     short loc_14000F3CA
0x14000f396  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14000f39d  mov     r8d, 631h
0x14000f3a3  jmp     short loc_14000F35B
0x14000f3a5  lea     r8, [rsp+0E8h+var_B8]
0x14000f3aa  mov     rdx, rbp
0x14000f3ad  mov     rcx, rsi
0x14000f3b0  call    RtlStringCchCopyW
0x14000f3b5  mov     ebx, eax
0x14000f3b7  test    eax, eax
0x14000f3b9  jns     short loc_14000F3CA
0x14000f3bb  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14000f3c2  mov     r8d, 639h
0x14000f3c8  jmp     short loc_14000F35B
0x14000f3ca  mov     ebx, r14d
0x14000f3cd  jmp     loc_14000F314
```
