# SrmDelimitedStringToVector(ushort const *,ushort,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18000eb40`
- end: `0x18000ecaf`
- name: `?SrmDelimitedStringToVector@@YAXPEBGGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `367`
- prototype: `void __fastcall(unsigned __int16 *, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000ab8c`
- `0x18000d380`

## callees

- `0x18000eb40`
- `0x18000ecb8`
- `0x1800106fc`
- `0x1800108b4`
- `0x18001b420`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000eb8d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ec4e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000eb8d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ec4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ebc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ec7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ebc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ec7d`

## pseudocode

```c
void __fastcall SrmDelimitedStringToVector(unsigned __int16 *a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rdi
  void *v8; // rdi
  char *v9; // rcx
  _WORD *v10; // rbx
  __int16 v11; // ax
  __int16 v12; // si
  unsigned __int64 v13; // r8
  LPVOID pv; // [rsp+28h] [rbp-38h] BYREF
  void *Src[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-20h]
  unsigned __int64 v17; // [rsp+48h] [rbp-18h]

  v5 = a3[1];
  v6 = *a3;
  if ( *a3 != v5 )
  {
    v7 = *a3;
    do
    {
      if ( *(_QWORD *)(v7 + 24) >= 8u )
        operator delete(*(void **)v7);
      *(_QWORD *)(v7 + 24) = 7;
      *(_QWORD *)(v7 + 16) = 0;
      *(_WORD *)v7 = 0;
      v7 += 40;
    }
    while ( v7 != v5 );
    a3[1] = v6;
  }
  pv = 0;
  SrmDuplicateStr((unsigned __int16 **)&pv, a1);
  CoTaskMemFree(0);
  v8 = pv;
  if ( pv )
  {
    v9 = (char *)pv;
    v10 = pv;
    do
    {
      v11 = *v10;
      if ( !*v10 )
        break;
      do
      {
        if ( v11 == 124 )
          break;
        v11 = *++v10;
      }
      while ( *v10 );
      v12 = *v10;
      *v10 = 0;
      v17 = 7;
      v16 = 0;
      LOWORD(Src[0]) = 0;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v9[2 * v13] );
      std::wstring::assign(Src, v9, v13);
      std::vector<std::wstring>::push_back(a3, Src);
      if ( v17 >= 8 )
        operator delete(Src[0]);
      v17 = 7;
      v16 = 0;
      LOWORD(Src[0]) = 0;
      if ( !v12 )
        break;
      *v10 = 124;
      v9 = (char *)(v10 + 1);
      v10 = v9;
    }
    while ( v9 );
  }
  CoTaskMemFree(v8);
}

```

## disassembly

```asm
0x18000eb40  mov     [rsp-38h+arg_8], rbx
0x18000eb45  push    rbp
0x18000eb46  push    rsi
0x18000eb47  push    rdi
0x18000eb48  push    r12
0x18000eb4a  push    r13
0x18000eb4c  push    r14
0x18000eb4e  push    r15
0x18000eb50  mov     rbp, rsp
0x18000eb53  sub     rsp, 60h
0x18000eb57  mov     rax, cs:__security_cookie
0x18000eb5e  xor     rax, rsp
0x18000eb61  mov     [rbp+var_8], rax
0x18000eb65  mov     r14, r8
0x18000eb68  mov     r15, rcx
0x18000eb6b  mov     rsi, [r8+8]
0x18000eb6f  mov     rbx, [r8]
0x18000eb72  mov     r13d, 7
0x18000eb78  xor     r12d, r12d
0x18000eb7b  cmp     rbx, rsi
0x18000eb7e  jz      short loc_18000EBAC
0x18000eb80  mov     rdi, rbx
0x18000eb83  cmp     qword ptr [rdi+18h], 8
0x18000eb88  jb      short loc_18000EB93
0x18000eb8a  mov     rcx, [rdi]
0x18000eb8d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000eb93  mov     [rdi+18h], r13
0x18000eb97  mov     [rdi+10h], r12
0x18000eb9b  mov     [rdi], r12w
0x18000eb9f  add     rdi, 28h ; '('
0x18000eba3  cmp     rdi, rsi
0x18000eba6  jnz     short loc_18000EB83
0x18000eba8  mov     [r14+8], rbx
0x18000ebac  mov     [rbp+var_40], r12
0x18000ebb0  mov     [rbp+pv], r12
0x18000ebb4  mov     rdx, r15; unsigned __int16 *
0x18000ebb7  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18000ebbb  call    ?SrmDuplicateStr@@YAXAEAPEAGPEBG@Z; SrmDuplicateStr(ushort * &,ushort const *)
0x18000ebc0  xor     ecx, ecx; pv
0x18000ebc2  call    cs:__imp_CoTaskMemFree
0x18000ebc8  mov     [rbp+var_40], r12
0x18000ebcc  mov     rdi, [rbp+pv]
0x18000ebd0  mov     [rbp+var_40], rdi
0x18000ebd4  test    rdi, rdi
0x18000ebd7  jz      loc_18000EC7A
0x18000ebdd  mov     rcx, rdi
0x18000ebe0  mov     rbx, rdi
0x18000ebe3  mov     r15d, 7Ch ; '|'
0x18000ebe9  movzx   eax, word ptr [rbx]
0x18000ebec  test    ax, ax
0x18000ebef  jz      loc_18000EC7A
0x18000ebf5  cmp     ax, r15w
0x18000ebf9  jz      short loc_18000EC07
0x18000ebfb  add     rbx, 2
0x18000ebff  movzx   eax, word ptr [rbx]
0x18000ec02  test    ax, ax
0x18000ec05  jnz     short loc_18000EBF5
0x18000ec07  movzx   esi, word ptr [rbx]
0x18000ec0a  mov     [rbx], r12w
0x18000ec0e  mov     [rbp+var_18], r13
0x18000ec12  mov     [rbp+var_20], r12
0x18000ec16  mov     word ptr [rbp+Src], r12w
0x18000ec1b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ec1f  inc     r8
0x18000ec22  cmp     [rcx+r8*2], r12w
0x18000ec27  jnz     short loc_18000EC1F
0x18000ec29  mov     rdx, rcx; void *
0x18000ec2c  lea     rcx, [rbp+Src]; Src
0x18000ec30  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000ec35  nop
0x18000ec36  lea     rdx, [rbp+Src]
0x18000ec3a  mov     rcx, r14
0x18000ec3d  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18000ec42  nop
0x18000ec43  cmp     [rbp+var_18], 8
0x18000ec48  jb      short loc_18000EC54
0x18000ec4a  mov     rcx, [rbp+Src]
0x18000ec4e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ec54  mov     [rbp+var_18], r13
0x18000ec58  mov     [rbp+var_20], r12
0x18000ec5c  mov     word ptr [rbp+Src], r12w
0x18000ec61  test    si, si
0x18000ec64  jz      short loc_18000EC7A
0x18000ec66  mov     [rbx], r15w
0x18000ec6a  lea     rcx, [rbx+2]
0x18000ec6e  mov     rbx, rcx
0x18000ec71  test    rcx, rcx
0x18000ec74  jnz     loc_18000EBE9
0x18000ec7a  mov     rcx, rdi; pv
0x18000ec7d  call    cs:__imp_CoTaskMemFree
0x18000ec83  mov     [rbp+var_40], r12
0x18000ec87  mov     [rbp+var_40], r12
0x18000ec8b  mov     rcx, [rbp+var_8]
0x18000ec8f  xor     rcx, rsp; StackCookie
0x18000ec92  call    __security_check_cookie
0x18000ec97  mov     rbx, [rsp+60h+arg_8]
0x18000ec9f  add     rsp, 60h
0x18000eca3  pop     r15
0x18000eca5  pop     r14
0x18000eca7  pop     r13
0x18000eca9  pop     r12
0x18000ecab  pop     rdi
0x18000ecac  pop     rsi
0x18000ecad  pop     rbp
0x18000ecae  retn
```
