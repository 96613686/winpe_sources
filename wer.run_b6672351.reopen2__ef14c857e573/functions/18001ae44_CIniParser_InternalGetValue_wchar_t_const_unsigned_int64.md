# CIniParser::InternalGetValue(wchar_t const *,unsigned __int64 *)

- ea: `0x18001ae44`
- end: `0x18001af95`
- name: `?InternalGetValue@CIniParser@@AEAAJPEB_WPEA_K@Z`
- size: `337`
- prototype: `__int64 __fastcall(CIniParser *__hidden this, const wchar_t *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180036de0`
- `0x180036f44`

## callees

- `0x18001ae44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18001af79`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18001af79`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aebf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001af2d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aebf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001af2d`

## pseudocode

```c
__int64 __fastcall CIniParser::InternalGetValue(CIniParser **this, const wchar_t *a2, unsigned __int64 *a3)
{
  __int64 v3; // rbx
  __int64 v5; // r14
  CIniParser *v7; // rsi
  CIniParser **v8; // rbp
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rax
  CIniParser *v13; // r9
  __int64 v14; // r8
  unsigned __int64 v15; // rax
  CIniParser **v17; // rcx

  v3 = -1;
  v5 = (__int64)a2;
  do
    ++v3;
  while ( a2[v3] );
  if ( this[5] == (CIniParser *)(this + 3) )
    goto LABEL_22;
  v7 = this[3];
  v8 = this + 3;
  do
  {
    v9 = *((_QWORD *)v7 + 4);
    if ( (v3 | v9) > 0x7FFFFFFF )
      __int2c();
    v10 = v5;
    v11 = 2;
    if ( !v5 )
      v10 = 2;
    if ( *((_QWORD *)v7 + 3) )
      v11 = *((_QWORD *)v7 + 3);
    if ( CompareStringOrdinal((LPCWCH)v11, v9, (LPCWCH)v10, v3, 1) == 1 )
    {
      v12 = 16;
    }
    else
    {
      v8 = (CIniParser **)v7;
      v12 = 8;
    }
    v7 = *(CIniParser **)((char *)v7 + v12);
  }
  while ( v7 != (CIniParser *)&utl::_TreeSentinel );
  if ( v8 == this + 3 )
    goto LABEL_22;
  v13 = v8[4];
  if ( (v3 | (unsigned __int64)v13) > 0x7FFFFFFF )
    __int2c();
  v14 = 2;
  if ( v8[3] )
    v14 = (__int64)v8[3];
  if ( !v5 )
    v5 = 2;
  if ( CompareStringOrdinal((LPCWCH)v5, v3, (LPCWCH)v14, (int)v13, 1) == 1 || (v17 = (CIniParser **)v8[5], v17 == this) )
LABEL_22:
    v15 = 0;
  else
    v15 = _o__wcstoui64(v17[6], 0, 10);
  *a3 = v15;
  return 0;
}

```

## disassembly

```asm
0x18001ae44  push    rbx
0x18001ae46  push    rbp
0x18001ae47  push    rsi
0x18001ae48  push    rdi
0x18001ae49  push    r12
0x18001ae4b  push    r13
0x18001ae4d  push    r14
0x18001ae4f  push    r15
0x18001ae51  sub     rsp, 38h
0x18001ae55  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ae59  mov     r12, r8
0x18001ae5c  xor     r13d, r13d
0x18001ae5f  mov     r14, rdx
0x18001ae62  mov     r15, rcx
0x18001ae65  inc     rbx
0x18001ae68  cmp     [rdx+rbx*2], r13w
0x18001ae6d  jnz     short loc_18001AE65
0x18001ae6f  lea     rdi, [rcx+18h]
0x18001ae73  cmp     [rdi+10h], rdi
0x18001ae77  jz      loc_18001AF3E
0x18001ae7d  mov     rsi, [rdi]
0x18001ae80  mov     rbp, rdi
0x18001ae83  mov     edi, 2
0x18001ae88  mov     rdx, [rsi+20h]; cchCount1
0x18001ae8c  mov     rax, rdx
0x18001ae8f  or      rax, rbx
0x18001ae92  cmp     rax, 7FFFFFFFh
0x18001ae98  ja      loc_18001AF87
0x18001ae9e  test    r14, r14
0x18001aea1  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18001aea9  mov     r8, r14
0x18001aeac  mov     rcx, rdi
0x18001aeaf  cmovz   r8, rdi; lpString2
0x18001aeb3  mov     r9d, ebx; cchCount2
0x18001aeb6  cmp     [rsi+18h], r13
0x18001aeba  cmovnz  rcx, [rsi+18h]; lpString1
0x18001aebf  call    cs:__imp_CompareStringOrdinal
0x18001aec6  nop     dword ptr [rax+rax+00h]
0x18001aecb  cmp     eax, 1
0x18001aece  jnz     loc_18001AF59
0x18001aed4  mov     eax, 10h
0x18001aed9  mov     rsi, [rax+rsi]
0x18001aedd  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18001aee4  cmp     rsi, rax
0x18001aee7  jnz     short loc_18001AE88
0x18001aee9  lea     rdi, [r15+18h]
0x18001aeed  cmp     rbp, rdi
0x18001aef0  jz      short loc_18001AF3E
0x18001aef2  mov     r9, [rbp+20h]; cchCount2
0x18001aef6  mov     rax, r9
0x18001aef9  or      rax, rbx
0x18001aefc  cmp     rax, 7FFFFFFFh
0x18001af02  ja      loc_18001AF8E
0x18001af08  cmp     [rbp+18h], r13
0x18001af0c  mov     eax, 2
0x18001af11  mov     r8d, eax
0x18001af14  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18001af1c  cmovnz  r8, [rbp+18h]; lpString2
0x18001af21  mov     edx, ebx; cchCount1
0x18001af23  test    r14, r14
0x18001af26  cmovz   r14, rax
0x18001af2a  mov     rcx, r14; lpString1
0x18001af2d  call    cs:__imp_CompareStringOrdinal
0x18001af34  nop     dword ptr [rax+rax+00h]
0x18001af39  cmp     eax, 1
0x18001af3c  jnz     short loc_18001AF66
0x18001af3e  mov     rax, r13
0x18001af41  mov     [r12], rax
0x18001af45  xor     eax, eax
0x18001af47  add     rsp, 38h
0x18001af4b  pop     r15
0x18001af4d  pop     r14
0x18001af4f  pop     r13
0x18001af51  pop     r12
0x18001af53  pop     rdi
0x18001af54  pop     rsi
0x18001af55  pop     rbp
0x18001af56  pop     rbx
0x18001af57  retn
0x18001af59  mov     rbp, rsi
0x18001af5c  mov     eax, 8
0x18001af61  jmp     loc_18001AED9
0x18001af66  mov     rcx, [rbp+28h]
0x18001af6a  cmp     rcx, r15
0x18001af6d  jz      short loc_18001AF3E
0x18001af6f  mov     rcx, [rcx+30h]
0x18001af73  xor     edx, edx
0x18001af75  lea     r8d, [rdx+0Ah]
0x18001af79  call    cs:__imp__o__wcstoui64
0x18001af80  nop     dword ptr [rax+rax+00h]
0x18001af85  jmp     short loc_18001AF41
0x18001af87  int     2Ch; Windows NT - assertion failure
0x18001af89  jmp     loc_18001AE9E
0x18001af8e  int     2Ch; Windows NT - assertion failure
0x18001af90  jmp     loc_18001AF08
```
