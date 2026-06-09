# SspirSslQueryCredentialsAttributes

- ea: `0x180003060`
- end: `0x18000317a`
- name: `SspirSslQueryCredentialsAttributes`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800013d0`
- `0x180001510`
- `0x180003060`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirSslQueryCredentialsAttributes(
        __int64 a1,
        _QWORD *a2,
        __int128 *a3,
        unsigned int a4,
        _QWORD *a5)
{
  size_t v7; // rcx
  void *v8; // rax
  void *v9; // rbx
  int v11; // edi
  _QWORD v12[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v13; // [rsp+40h] [rbp-38h] BYREF

  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 72) )
    return 3221225659LL;
  if ( !a2 || !a3 || !a5 )
    return 3221225485LL;
  v12[0] = *a2;
  v12[1] = a2[1];
  v13 = *a3;
  switch ( a4 )
  {
    case 1u:
      goto LABEL_10;
    case 0x56u:
      v7 = 16;
      goto LABEL_13;
    case 0x57u:
LABEL_10:
      v7 = 8;
      goto LABEL_13;
  }
  if ( a4 != 88 )
    return 3221225485LL;
  v7 = 4;
LABEL_13:
  v8 = MIDL_user_allocate(v7);
  v9 = v8;
  if ( !v8 )
    return 3221225626LL;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, _QWORD, void *))(gLsapSspiExtension + 72))(
          a1,
          v12,
          &v13,
          a4,
          v8);
  if ( v11 < 0 )
    MIDL_user_free(v9);
  else
    *a5 = v9;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003060  mov     [rsp+arg_10], rbx
0x180003065  push    rbp
0x180003066  push    rsi
0x180003067  push    rdi
0x180003068  sub     rsp, 60h
0x18000306c  mov     rax, cs:__security_cookie
0x180003073  xor     rax, rsp
0x180003076  mov     [rsp+78h+var_28], rax
0x18000307b  mov     rax, cs:gLsapSspiExtension
0x180003082  mov     edi, r9d
0x180003085  mov     rsi, [rsp+78h+arg_20]
0x18000308d  mov     rbp, rcx
0x180003090  test    rax, rax
0x180003093  jz      loc_180003157
0x180003099  cmp     qword ptr [rax+48h], 0
0x18000309e  jz      loc_180003157
0x1800030a4  test    rdx, rdx
0x1800030a7  jz      loc_180003150
0x1800030ad  test    r8, r8
0x1800030b0  jz      loc_180003150
0x1800030b6  test    rsi, rsi
0x1800030b9  jz      loc_180003150
0x1800030bf  mov     rax, [rdx]
0x1800030c2  mov     [rsp+78h+var_48], rax
0x1800030c7  mov     rax, [rdx+8]
0x1800030cb  mov     [rsp+78h+var_40], rax
0x1800030d0  movups  xmm0, xmmword ptr [r8]
0x1800030d4  movdqu  [rsp+78h+var_38], xmm0
0x1800030da  cmp     r9d, 1
0x1800030de  jz      short loc_1800030F1
0x1800030e0  cmp     r9d, 56h ; 'V'
0x1800030e4  jnz     short loc_1800030EC
0x1800030e6  lea     ecx, [r9-46h]
0x1800030ea  jmp     short loc_180003100
0x1800030ec  cmp     edi, 57h ; 'W'
0x1800030ef  jnz     short loc_1800030F8
0x1800030f1  mov     ecx, 8
0x1800030f6  jmp     short loc_180003100
0x1800030f8  cmp     edi, 58h ; 'X'
0x1800030fb  jnz     short loc_180003150
0x1800030fd  lea     ecx, [rdi-54h]; size
0x180003100  call    MIDL_user_allocate
0x180003105  mov     rbx, rax
0x180003108  test    rax, rax
0x18000310b  jnz     short loc_180003114
0x18000310d  mov     eax, 0C000009Ah
0x180003112  jmp     short loc_18000315C
0x180003114  mov     rax, cs:gLsapSspiExtension
0x18000311b  lea     r8, [rsp+78h+var_38]
0x180003120  mov     r9d, edi
0x180003123  mov     [rsp+78h+var_58], rbx
0x180003128  lea     rdx, [rsp+78h+var_48]
0x18000312d  mov     rcx, rbp
0x180003130  mov     rax, [rax+48h]
0x180003134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003139  mov     edi, eax
0x18000313b  test    eax, eax
0x18000313d  js      short loc_180003144
0x18000313f  mov     [rsi], rbx
0x180003142  jmp     short loc_18000314C
0x180003144  mov     rcx, rbx; void *
0x180003147  call    MIDL_user_free
0x18000314c  mov     eax, edi
0x18000314e  jmp     short loc_18000315C
0x180003150  mov     eax, 0C000000Dh
0x180003155  jmp     short loc_18000315C
0x180003157  mov     eax, 0C00000BBh
0x18000315c  mov     rcx, [rsp+78h+var_28]
0x180003161  xor     rcx, rsp; StackCookie
0x180003164  call    __security_check_cookie
0x180003169  mov     rbx, [rsp+78h+arg_10]
0x180003171  add     rsp, 60h
0x180003175  pop     rdi
0x180003176  pop     rsi
0x180003177  pop     rbp
0x180003178  retn
```
