# CNetworkCfgRegSettings::IsAdapterValid(uchar *,ulong)

- ea: `0x18001c630`
- end: `0x18001c71b`
- name: `?IsAdapterValid@CNetworkCfgRegSettings@@QEAAHPEAEK@Z`
- size: `235`
- prototype: `__int64 __fastcall(CNetworkCfgRegSettings *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000cd44`

## callees

- `0x180010654`
- `0x18001c630`
- `0x180026a30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001c6fe`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001c6fe`

## pseudocode

```c
__int64 __fastcall CNetworkCfgRegSettings::IsAdapterValid(
        CNetworkCfgRegSettings *this,
        unsigned __int8 *a2,
        unsigned int a3)
{
  unsigned int v7; // ebp
  __int64 v8; // r14
  char *v9; // rdi
  unsigned int v10; // ebx
  int v11; // esi
  int i; // edi
  char v13[32]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a3 )
    return 1;
  v7 = 25;
  v13[0] = 0;
  v8 = 0;
  v9 = v13;
  v10 = 1;
  do
  {
    if ( v7 < 3 )
      break;
    StringCchPrintfA(v9, 3u, "%02x-", a2[v8]);
    v9 += 3;
    v7 -= 3;
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (unsigned int)v8 < a3 );
  if ( v9 != v13 )
    *(v9 - 1) = 0;
  if ( v13[0] )
  {
    v11 = *((_DWORD *)this + 4);
    for ( i = 0; i < v11; ++i )
    {
      if ( !(unsigned int)_o__stricmp(*((_QWORD *)this + 1) + 25LL * i, v13) )
        return v10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c630  mov     [rsp+arg_10], rbx
0x18001c635  mov     [rsp+arg_18], rbp
0x18001c63a  push    rsi
0x18001c63b  push    rdi
0x18001c63c  push    r12
0x18001c63e  push    r14
0x18001c640  push    r15
0x18001c642  sub     rsp, 50h
0x18001c646  mov     rax, cs:__security_cookie
0x18001c64d  xor     rax, rsp
0x18001c650  mov     [rsp+78h+var_38], rax
0x18001c655  mov     esi, r8d
0x18001c658  mov     r12, rdx
0x18001c65b  mov     r15, rcx
0x18001c65e  test    r8d, r8d
0x18001c661  jnz     short loc_18001C68D
0x18001c663  lea     eax, [r8+1]
0x18001c667  mov     rcx, [rsp+78h+var_38]
0x18001c66c  xor     rcx, rsp; StackCookie
0x18001c66f  call    __security_check_cookie
0x18001c674  lea     r11, [rsp+78h+var_28]
0x18001c679  mov     rbx, [r11+40h]
0x18001c67d  mov     rbp, [r11+48h]
0x18001c681  mov     rsp, r11
0x18001c684  pop     r15
0x18001c686  pop     r14
0x18001c688  pop     r12
0x18001c68a  pop     rdi
0x18001c68b  pop     rsi
0x18001c68c  retn
0x18001c68d  mov     ebp, 19h
0x18001c692  mov     [rsp+78h+var_58], 0
0x18001c697  xor     r14d, r14d
0x18001c69a  lea     rdi, [rsp+78h+var_58]
0x18001c69f  lea     ebx, [rbp-18h]
0x18001c6a2  test    esi, esi
0x18001c6a4  jz      short loc_18001C6DD
0x18001c6a6  cmp     ebp, 3
0x18001c6a9  jb      short loc_18001C6D3
0x18001c6ab  movzx   r9d, byte ptr [r14+r12]
0x18001c6b0  lea     r8, a02x; "%02x-"
0x18001c6b7  mov     edx, 3; unsigned __int64
0x18001c6bc  mov     rcx, rdi; char *
0x18001c6bf  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001c6c4  add     rdi, 3
0x18001c6c8  add     ebp, 0FFFFFFFDh
0x18001c6cb  add     r14d, ebx
0x18001c6ce  cmp     r14d, esi
0x18001c6d1  jb      short loc_18001C6A6
0x18001c6d3  lea     rax, [rsp+78h+var_58]
0x18001c6d8  cmp     rdi, rax
0x18001c6db  jnz     short loc_18001C715
0x18001c6dd  cmp     [rsp+78h+var_58], 0
0x18001c6e2  jz      short loc_18001C70C
0x18001c6e4  mov     esi, [r15+10h]
0x18001c6e8  xor     edi, edi
0x18001c6ea  cmp     edi, esi
0x18001c6ec  jge     short loc_18001C70C
0x18001c6ee  movsxd  rax, edi
0x18001c6f1  lea     rdx, [rsp+78h+var_58]
0x18001c6f6  imul    rcx, rax, 19h
0x18001c6fa  add     rcx, [r15+8]
0x18001c6fe  call    cs:__imp__o__stricmp
0x18001c704  test    eax, eax
0x18001c706  jz      short loc_18001C70E
0x18001c708  add     edi, ebx
0x18001c70a  jmp     short loc_18001C6EA
0x18001c70c  xor     ebx, ebx
0x18001c70e  mov     eax, ebx
0x18001c710  jmp     loc_18001C667
0x18001c715  mov     byte ptr [rdi-1], 0
0x18001c719  jmp     short loc_18001C6DD
```
