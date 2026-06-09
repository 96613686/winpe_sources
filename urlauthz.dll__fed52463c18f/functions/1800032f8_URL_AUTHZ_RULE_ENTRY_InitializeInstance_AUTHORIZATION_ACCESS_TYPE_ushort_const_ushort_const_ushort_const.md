# URL_AUTHZ_RULE_ENTRY::InitializeInstance(AUTHORIZATION_ACCESS_TYPE,ushort const *,ushort const *,ushort const *)

- ea: `0x1800032f8`
- end: `0x18000342f`
- name: `?InitializeInstance@URL_AUTHZ_RULE_ENTRY@@QEAAJW4AUTHORIZATION_ACCESS_TYPE@@PEBG11@Z`
- size: `311`
- prototype: `__int64 __fastcall(__int64, int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002768`

## callees

- `0x180001008`
- `0x180002b64`
- `0x1800032f8`
- `0x180003654`

## pseudocode

```c
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::InitializeInstance(
        __int64 a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned int *v5; // rdi
  __int64 result; // rax
  unsigned __int64 v9; // rsi
  __int64 v10; // rax
  bool v11; // cf
  size_t v12; // rax
  unsigned __int64 *v13; // rax
  _QWORD *v14; // rdi
  CACHED_USER_SID *i; // rbp
  char v16; // di
  URL_AUTHZ_RULE_ENTRY *v17; // rcx
  char v18; // di
  unsigned int v19; // [rsp+58h] [rbp+10h] BYREF

  *(_DWORD *)(a1 + 16) = a2;
  v5 = (unsigned int *)(a1 + 32);
  v19 = 0;
  result = URL_AUTHZ_RULE_ENTRY::ParseCommaSeparatedStringToArray(
             (URL_AUTHZ_RULE_ENTRY *)&v19,
             a3,
             1,
             (void **)(a1 + 24),
             (unsigned int *)(a1 + 32),
             &v19);
  if ( (int)result >= 0 )
  {
    v9 = *v5;
    v10 = 56 * v9;
    if ( !is_mul_ok(v9, 0x38u) )
      v10 = -1;
    v11 = __CFADD__(v10, 8);
    v12 = v10 + 8;
    if ( v11 )
      v12 = -1;
    v13 = (unsigned __int64 *)operator new(v12);
    if ( v13 )
    {
      *v13 = v9;
      v14 = v13 + 1;
      for ( i = (CACHED_USER_SID *)(v13 + 1); v9; --v9 )
      {
        CACHED_USER_SID::CACHED_USER_SID(i);
        i = (CACHED_USER_SID *)((char *)i + 56);
      }
    }
    else
    {
      v14 = 0;
    }
    *(_QWORD *)(a1 + 40) = v14;
    if ( v14 )
    {
      v16 = v19;
      result = URL_AUTHZ_RULE_ENTRY::ParseCommaSeparatedStringToArray(
                 (URL_AUTHZ_RULE_ENTRY *)&v19,
                 a4,
                 1,
                 (void **)(a1 + 56),
                 (unsigned int *)(a1 + 64),
                 &v19);
      if ( (int)result >= 0 )
      {
        result = URL_AUTHZ_RULE_ENTRY::ParseCommaSeparatedStringToArray(
                   v17,
                   a5,
                   0,
                   (void **)(a1 + 72),
                   (unsigned int *)(a1 + 80),
                   0);
        if ( (int)result >= 0 )
        {
          v18 = v19 | v16;
          if ( (v18 & 2) != 0 )
            *(_DWORD *)(a1 + 84) = 1;
          if ( (v18 & 1) != 0 )
            *(_DWORD *)(a1 + 88) = 1;
          return 0;
        }
      }
    }
    else
    {
      return 2147942408LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800032f8  mov     r11, rsp
0x1800032fb  mov     [r11+8], rbx
0x1800032ff  mov     [r11+18h], rbp
0x180003303  push    rsi
0x180003304  push    rdi
0x180003305  push    r14
0x180003307  sub     rsp, 30h
0x18000330b  mov     [rcx+10h], edx
0x18000330e  lea     rdi, [rcx+20h]
0x180003312  mov     rax, r8
0x180003315  mov     [rsp+48h+arg_8], 0
0x18000331d  mov     r14, r9
0x180003320  mov     rbx, rcx
0x180003323  lea     r9, [rcx+18h]; void **
0x180003327  mov     r8d, 1; int
0x18000332d  lea     rcx, [r11+10h]; this
0x180003331  mov     rdx, rax; unsigned __int16 *
0x180003334  mov     [r11-20h], rcx
0x180003338  mov     [r11-28h], rdi
0x18000333c  call    ?ParseCommaSeparatedStringToArray@URL_AUTHZ_RULE_ENTRY@@AEAAJPEBGHPEAPEAXPEAK2@Z; URL_AUTHZ_RULE_ENTRY::ParseCommaSeparatedStringToArray(ushort const *,int,void * *,ulong *,ulong *)
0x180003341  test    eax, eax
0x180003343  js      loc_18000341C
0x180003349  mov     esi, [rdi]
0x18000334b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003352  mov     eax, 38h ; '8'
0x180003357  mul     rsi
0x18000335a  cmovb   rax, rcx
0x18000335e  add     rax, 8
0x180003362  cmovb   rax, rcx
0x180003366  mov     rcx, rax; Size
0x180003369  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000336e  test    rax, rax
0x180003371  jz      short loc_180003396
0x180003373  mov     [rax], rsi
0x180003376  lea     rdi, [rax+8]
0x18000337a  mov     rbp, rdi
0x18000337d  test    rsi, rsi
0x180003380  jz      short loc_180003398
0x180003382  mov     rcx, rbp; this
0x180003385  call    ??0CACHED_USER_SID@@QEAA@XZ; CACHED_USER_SID::CACHED_USER_SID(void)
0x18000338a  add     rbp, 38h ; '8'
0x18000338e  sub     rsi, 1
0x180003392  jnz     short loc_180003382
0x180003394  jmp     short loc_180003398
0x180003396  xor     edi, edi
0x180003398  mov     [rbx+28h], rdi
0x18000339c  test    rdi, rdi
0x18000339f  jnz     short loc_1800033A8
0x1800033a1  mov     eax, 80070008h
0x1800033a6  jmp     short loc_18000341C
0x1800033a8  mov     edi, [rsp+48h+arg_8]
0x1800033ac  lea     rcx, [rsp+48h+arg_8]; this
0x1800033b1  lea     rax, [rbx+40h]
0x1800033b5  mov     [rsp+48h+var_20], rcx; unsigned int *
0x1800033ba  lea     r9, [rbx+38h]; void **
0x1800033be  mov     [rsp+48h+var_28], rax; unsigned int *
0x1800033c3  mov     r8d, 1; int
0x1800033c9  mov     rdx, r14; unsigned __int16 *
0x1800033cc  call    ?ParseCommaSeparatedStringToArray@URL_AUTHZ_RULE_ENTRY@@AEAAJPEBGHPEAPEAXPEAK2@Z; URL_AUTHZ_RULE_ENTRY::ParseCommaSeparatedStringToArray(ushort const *,int,void * *,ulong *,ulong *)
0x1800033d1  test    eax, eax
0x1800033d3  js      short loc_18000341C
0x1800033d5  mov     rdx, [rsp+48h+arg_20]; unsigned __int16 *
0x1800033da  lea     rax, [rbx+50h]
0x1800033de  lea     r9, [rbx+48h]; void **
0x1800033e2  mov     [rsp+48h+var_20], 0; unsigned int *
0x1800033eb  xor     r8d, r8d; int
0x1800033ee  mov     [rsp+48h+var_28], rax; unsigned int *
0x1800033f3  call    ?ParseCommaSeparatedStringToArray@URL_AUTHZ_RULE_ENTRY@@AEAAJPEBGHPEAPEAXPEAK2@Z; URL_AUTHZ_RULE_ENTRY::ParseCommaSeparatedStringToArray(ushort const *,int,void * *,ulong *,ulong *)
0x1800033f8  test    eax, eax
0x1800033fa  js      short loc_18000341C
0x1800033fc  or      edi, [rsp+48h+arg_8]
0x180003400  test    dil, 2
0x180003404  jz      short loc_18000340D
0x180003406  mov     dword ptr [rbx+54h], 1
0x18000340d  test    dil, 1
0x180003411  jz      short loc_18000341A
0x180003413  mov     dword ptr [rbx+58h], 1
0x18000341a  xor     eax, eax
0x18000341c  mov     rbx, [rsp+48h+arg_0]
0x180003421  mov     rbp, [rsp+48h+arg_10]
0x180003426  add     rsp, 30h
0x18000342a  pop     r14
0x18000342c  pop     rdi
0x18000342d  pop     rsi
0x18000342e  retn
```
