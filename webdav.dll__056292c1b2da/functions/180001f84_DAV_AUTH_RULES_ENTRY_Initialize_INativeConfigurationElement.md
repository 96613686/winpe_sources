# DAV_AUTH_RULES_ENTRY::Initialize(INativeConfigurationElement *)

- ea: `0x180001f84`
- end: `0x1800021be`
- name: `?Initialize@DAV_AUTH_RULES_ENTRY@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(DAV_AUTH_RULES_ENTRY *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001d8c`

## callees

- `0x1800011d4`
- `0x180001c28`
- `0x180001f84`
- `0x180019854`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcslwr` at `0x180002071`
- `msvcrt!_wcslwr` at `0x180002071`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002061`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002061`

## string_xrefs

- `0x180001fb9`: `access`

## pseudocode

```c
__int64 __fastcall DAV_AUTH_RULES_ENTRY::Initialize(DAV_AUTH_RULES_ENTRY *this, struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD); // rax
  int v6; // ebx
  _DWORD *v7; // r12
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  bool v10; // cf
  size_t v11; // rax
  unsigned __int64 *v12; // rax
  _QWORD *v13; // rsi
  AUTH_ACCOUNT_SID *i; // rbp
  _DWORD *v15; // r15
  unsigned __int64 v16; // rbp
  __int64 v17; // rax
  size_t v18; // rax
  unsigned __int64 *v19; // rax
  _QWORD *v20; // rsi
  AUTH_ACCOUNT_SID *j; // r14
  const unsigned __int16 *v23; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v24; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int16 *v25; // [rsp+80h] [rbp+18h] BYREF

  v2 = *(_QWORD *)a2;
  v24 = 0;
  v25 = 0;
  v5 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(v2 + 48);
  v23 = 0;
  v6 = v5(a2, L"access", (char *)this + 120, 0, 0);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
           a2,
           L"users",
           &v24,
           0,
           0);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
             a2,
             L"roles",
             &v25,
             0,
             0);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
               a2,
               L"path",
               &v23,
               0,
               0);
        if ( v6 >= 0 )
        {
          v6 = STRU::Copy((DAV_AUTH_RULES_ENTRY *)((char *)this + 64), v23);
          if ( v6 >= 0 )
            _wcslwr(*((wchar_t **)this + 12));
        }
      }
    }
  }
  *((_DWORD *)this + 32) = 0;
  *((_DWORD *)this + 31) = 0;
  if ( v6 >= 0 )
  {
    v7 = (_DWORD *)((char *)this + 16);
    v6 = ParseCommaSeparatedStringToArray(
           v24,
           (struct STRU **)this + 1,
           (unsigned int *)this + 4,
           (DAV_AUTH_RULES_ENTRY *)((char *)this + 124));
    if ( v6 >= 0 )
    {
      if ( *v7 )
      {
        v8 = (unsigned int)*v7;
        v9 = 56 * v8;
        if ( !is_mul_ok(v8, 0x38u) )
          v9 = -1;
        v10 = __CFADD__(v9, 8);
        v11 = v9 + 8;
        if ( v10 )
          v11 = -1;
        v12 = (unsigned __int64 *)operator new(v11);
        if ( v12 )
        {
          *v12 = v8;
          v13 = v12 + 1;
          for ( i = (AUTH_ACCOUNT_SID *)(v12 + 1); v8; --v8 )
          {
            AUTH_ACCOUNT_SID::AUTH_ACCOUNT_SID(i);
            i = (AUTH_ACCOUNT_SID *)((char *)i + 56);
          }
        }
        else
        {
          v13 = 0;
        }
        *((_QWORD *)this + 5) = v13;
        if ( !v13 )
          return (unsigned int)-2147024888;
      }
      v15 = (_DWORD *)((char *)this + 32);
      v6 = ParseCommaSeparatedStringToArray(
             v25,
             (struct STRU **)this + 3,
             (unsigned int *)this + 8,
             (DAV_AUTH_RULES_ENTRY *)((char *)this + 124));
      if ( v6 >= 0 )
      {
        if ( *v15 )
        {
          v16 = (unsigned int)*v15;
          v17 = 56 * v16;
          if ( !is_mul_ok(v16, 0x38u) )
            v17 = -1;
          v10 = __CFADD__(v17, 8);
          v18 = v17 + 8;
          if ( v10 )
            v18 = -1;
          v19 = (unsigned __int64 *)operator new(v18);
          if ( v19 )
          {
            *v19 = v16;
            v20 = v19 + 1;
            for ( j = (AUTH_ACCOUNT_SID *)(v19 + 1); v16; --v16 )
            {
              AUTH_ACCOUNT_SID::AUTH_ACCOUNT_SID(j);
              j = (AUTH_ACCOUNT_SID *)((char *)j + 56);
            }
          }
          else
          {
            v20 = 0;
          }
          *((_QWORD *)this + 6) = v20;
          if ( !v20 )
            return (unsigned int)-2147024888;
        }
        if ( !*v7 && !*v15 )
          *((_DWORD *)this + 32) = 1;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001f84  mov     r11, rsp
0x180001f87  mov     [r11+20h], rbx
0x180001f8b  push    rbp
0x180001f8c  push    rsi
0x180001f8d  push    rdi
0x180001f8e  push    r12
0x180001f90  push    r13
0x180001f92  push    r14
0x180001f94  push    r15
0x180001f96  sub     rsp, 30h
0x180001f9a  mov     rax, [rdx]
0x180001f9d  lea     r8, [rcx+78h]
0x180001fa1  xor     r13d, r13d
0x180001fa4  mov     rsi, rdx
0x180001fa7  mov     rdi, rcx
0x180001faa  mov     [r11+10h], r13
0x180001fae  xor     r9d, r9d
0x180001fb1  mov     [r11+18h], r13
0x180001fb5  mov     rax, [rax+30h]
0x180001fb9  lea     rdx, aAccess; "access"
0x180001fc0  mov     rcx, rsi
0x180001fc3  mov     [r11+8], r13
0x180001fc7  mov     [r11-48h], r13
0x180001fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fd0  mov     ebx, eax
0x180001fd2  test    eax, eax
0x180001fd4  js      loc_180002077
0x180001fda  mov     rax, [rsi]
0x180001fdd  lea     r8, [rsp+68h+arg_8]
0x180001fe2  xor     r9d, r9d
0x180001fe5  mov     [rsp+68h+var_48], r13
0x180001fea  lea     rdx, aUsers; "users"
0x180001ff1  mov     rcx, rsi
0x180001ff4  mov     rax, [rax+40h]
0x180001ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ffd  mov     ebx, eax
0x180001fff  test    eax, eax
0x180002001  js      short loc_180002077
0x180002003  mov     rax, [rsi]
0x180002006  lea     r8, [rsp+68h+arg_10]
0x18000200e  xor     r9d, r9d
0x180002011  mov     [rsp+68h+var_48], r13
0x180002016  lea     rdx, aRoles; "roles"
0x18000201d  mov     rcx, rsi
0x180002020  mov     rax, [rax+40h]
0x180002024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002029  mov     ebx, eax
0x18000202b  test    eax, eax
0x18000202d  js      short loc_180002077
0x18000202f  mov     rax, [rsi]
0x180002032  lea     r8, [rsp+68h+arg_0]
0x180002037  xor     r9d, r9d
0x18000203a  mov     [rsp+68h+var_48], r13
0x18000203f  lea     rdx, aPath; "path"
0x180002046  mov     rcx, rsi
0x180002049  mov     rax, [rax+40h]
0x18000204d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002052  mov     ebx, eax
0x180002054  test    eax, eax
0x180002056  js      short loc_180002077
0x180002058  mov     rdx, [rsp+68h+arg_0]
0x18000205d  lea     rcx, [rdi+40h]
0x180002061  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002067  mov     ebx, eax
0x180002069  test    eax, eax
0x18000206b  js      short loc_180002077
0x18000206d  mov     rcx, [rdi+60h]; String
0x180002071  call    cs:__imp__wcslwr
0x180002077  mov     [rdi+80h], r13d
0x18000207e  lea     r14, [rdi+7Ch]
0x180002082  mov     [r14], r13d
0x180002085  test    ebx, ebx
0x180002087  js      loc_1800021A4
0x18000208d  mov     rcx, [rsp+68h+arg_8]; unsigned __int16 *
0x180002092  lea     r12, [rdi+10h]
0x180002096  mov     r8, r12; unsigned int *
0x180002099  lea     rdx, [rdi+8]; struct STRU **
0x18000209d  mov     r9, r14; struct AUTH_RULE_HINT *
0x1800020a0  call    ?ParseCommaSeparatedStringToArray@@YAJPEBGPEAPEAVSTRU@@PEAKPEAVAUTH_RULE_HINT@@@Z; ParseCommaSeparatedStringToArray(ushort const *,STRU * *,ulong *,AUTH_RULE_HINT *)
0x1800020a5  mov     ebx, eax
0x1800020a7  test    eax, eax
0x1800020a9  js      loc_1800021A4
0x1800020af  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800020b3  cmp     [r12], r13d
0x1800020b7  jbe     short loc_18000210F
0x1800020b9  mov     ebx, [r12]
0x1800020bd  lea     eax, [rsi+39h]
0x1800020c0  mul     rbx
0x1800020c3  cmovb   rax, rsi
0x1800020c7  add     rax, 8
0x1800020cb  cmovb   rax, rsi
0x1800020cf  mov     rcx, rax; Size
0x1800020d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800020d7  test    rax, rax
0x1800020da  jz      short loc_1800020FF
0x1800020dc  mov     [rax], rbx
0x1800020df  lea     rsi, [rax+8]
0x1800020e3  mov     rbp, rsi
0x1800020e6  test    rbx, rbx
0x1800020e9  jz      short loc_180002102
0x1800020eb  mov     rcx, rbp; this
0x1800020ee  call    ??0AUTH_ACCOUNT_SID@@QEAA@XZ; AUTH_ACCOUNT_SID::AUTH_ACCOUNT_SID(void)
0x1800020f3  add     rbp, 38h ; '8'
0x1800020f7  sub     rbx, 1
0x1800020fb  jnz     short loc_1800020EB
0x1800020fd  jmp     short loc_180002102
0x1800020ff  mov     rsi, r13
0x180002102  mov     [rdi+28h], rsi
0x180002106  test    rsi, rsi
0x180002109  jz      short loc_180002188
0x18000210b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000210f  mov     rcx, [rsp+68h+arg_10]; unsigned __int16 *
0x180002117  lea     r15, [rdi+20h]
0x18000211b  mov     r8, r15; unsigned int *
0x18000211e  lea     rdx, [rdi+18h]; struct STRU **
0x180002122  mov     r9, r14; struct AUTH_RULE_HINT *
0x180002125  call    ?ParseCommaSeparatedStringToArray@@YAJPEBGPEAPEAVSTRU@@PEAKPEAVAUTH_RULE_HINT@@@Z; ParseCommaSeparatedStringToArray(ushort const *,STRU * *,ulong *,AUTH_RULE_HINT *)
0x18000212a  mov     ebx, eax
0x18000212c  test    eax, eax
0x18000212e  js      short loc_1800021A4
0x180002130  cmp     [r15], r13d
0x180002133  jbe     short loc_18000218F
0x180002135  mov     ebp, [r15]
0x180002138  mov     eax, 38h ; '8'
0x18000213d  mul     rbp
0x180002140  cmovb   rax, rsi
0x180002144  add     rax, 8
0x180002148  cmovb   rax, rsi
0x18000214c  mov     rcx, rax; Size
0x18000214f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002154  test    rax, rax
0x180002157  jz      short loc_18000217C
0x180002159  mov     [rax], rbp
0x18000215c  lea     rsi, [rax+8]
0x180002160  mov     r14, rsi
0x180002163  test    rbp, rbp
0x180002166  jz      short loc_18000217F
0x180002168  mov     rcx, r14; this
0x18000216b  call    ??0AUTH_ACCOUNT_SID@@QEAA@XZ; AUTH_ACCOUNT_SID::AUTH_ACCOUNT_SID(void)
0x180002170  add     r14, 38h ; '8'
0x180002174  sub     rbp, 1
0x180002178  jnz     short loc_180002168
0x18000217a  jmp     short loc_18000217F
0x18000217c  mov     rsi, r13
0x18000217f  mov     [rdi+30h], rsi
0x180002183  test    rsi, rsi
0x180002186  jnz     short loc_18000218F
0x180002188  mov     ebx, 80070008h
0x18000218d  jmp     short loc_1800021A4
0x18000218f  cmp     [r12], r13d
0x180002193  jnz     short loc_1800021A4
0x180002195  cmp     [r15], r13d
0x180002198  jnz     short loc_1800021A4
0x18000219a  mov     dword ptr [rdi+80h], 1
0x1800021a4  mov     eax, ebx
0x1800021a6  mov     rbx, [rsp+68h+arg_18]
0x1800021ae  add     rsp, 30h
0x1800021b2  pop     r15
0x1800021b4  pop     r14
0x1800021b6  pop     r13
0x1800021b8  pop     r12
0x1800021ba  pop     rdi
0x1800021bb  pop     rsi
0x1800021bc  pop     rbp
0x1800021bd  retn
```
