# URL_AUTHZ_RULE_LIST::DoAuthorizationCheck(IHttpContext *,int *)

- ea: `0x180003158`
- end: `0x1800032f2`
- name: `?DoAuthorizationCheck@URL_AUTHZ_RULE_LIST@@QEAAJPEAVIHttpContext@@PEAH@Z`
- size: `410`
- prototype: `int __fastcall(URL_AUTHZ_RULE_LIST *this, struct IHttpContext *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000223c`

## callees

- `0x180002b88`
- `0x180003158`
- `0x180004010`

## pseudocode

```c
int __fastcall URL_AUTHZ_RULE_LIST::DoAuthorizationCheck(URL_AUTHZ_RULE_LIST *this, struct IHttpContext *a2, int *a3)
{
  int result; // eax
  struct IHttpUser *v7; // r14
  __int64 v8; // rax
  bool v9; // zf
  const unsigned __int16 *v10; // r12
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  URL_AUTHZ_RULE_LIST *v14; // rbx
  const char *v15; // r15
  int v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF
  _BYTE *v18; // [rsp+40h] [rbp-10h] BYREF
  __int64 v19; // [rsp+98h] [rbp+48h] BYREF

  v17 = 0;
  v19 = 0;
  result = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(*(_QWORD *)g_pGlobalInfo + 200LL))(
             g_pGlobalInfo,
             0,
             &v19);
  if ( result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(__int64, GUID *, struct IHttpContext *, GUID *, __int64 *))(*(_QWORD *)v19
                                                                                                  + 224LL))(
               v19,
               &GUID_424c1b8c_a1ba_44d7_ac98_9f8f457701a5,
               a2,
               &GUID_c986182c_cf4a_4482_8205_0dbbc1fd6cee,
               &v17);
    if ( result >= 0 )
    {
      v7 = (struct IHttpUser *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 312LL))(v17);
      v17 = 0;
      v8 = (*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)v7 + 8LL))(v7);
      v9 = *((_DWORD *)this + 4) == 0;
      v10 = (const unsigned __int16 *)v8;
      LODWORD(v19) = 2;
      if ( v9 )
        goto LABEL_9;
      v11 = *(_QWORD *)a2;
      v18 = 0;
      v16 = 0;
      result = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, _BYTE **, int *))(v11 + 120))(
                 a2,
                 "IS_LOGIN_PAGE",
                 &v18,
                 &v16);
      if ( result == -2147023483 )
        goto LABEL_9;
      if ( result < 0 )
        return result;
      if ( *v18 == 48 && !v18[1] )
      {
LABEL_9:
        v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 64LL))(v12);
        v14 = *(URL_AUTHZ_RULE_LIST **)this;
        v15 = (const char *)v13;
        while ( 1 )
        {
          if ( v14 == this )
          {
            *a3 = 0;
            return 0;
          }
          result = URL_AUTHZ_RULE_ENTRY::CheckAuthorizationRule(
                     v14,
                     v10,
                     v7,
                     v15,
                     (enum AUTHORIZATION_ACCESS_TYPE *)&v19);
          if ( result < 0 )
            return result;
          if ( (_DWORD)v19 != 2 )
            break;
          v14 = *(URL_AUTHZ_RULE_LIST **)v14;
        }
        *a3 = v19 == 0;
      }
      else
      {
        *a3 = 1;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003158  mov     [rsp-28h+arg_0], rbx
0x18000315d  mov     [rsp-28h+arg_8], rsi
0x180003162  push    rbp
0x180003163  push    rdi
0x180003164  push    r12
0x180003166  push    r14
0x180003168  push    r15
0x18000316a  mov     rbp, rsp
0x18000316d  sub     rsp, 50h
0x180003171  mov     rsi, rcx
0x180003174  mov     [rbp+var_18], 0
0x18000317c  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180003183  mov     rdi, r8
0x180003186  mov     rbx, rdx
0x180003189  mov     [rbp+arg_18], 0
0x180003191  lea     r8, [rbp+arg_18]
0x180003195  xor     edx, edx
0x180003197  mov     rax, [rcx]
0x18000319a  mov     rax, [rax+0C8h]
0x1800031a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a6  test    eax, eax
0x1800031a8  js      loc_1800032CE
0x1800031ae  mov     rcx, [rbp+arg_18]
0x1800031b2  lea     rdx, [rbp+var_18]
0x1800031b6  mov     [rsp+50h+var_30], rdx
0x1800031bb  lea     r9, _GUID_c986182c_cf4a_4482_8205_0dbbc1fd6cee
0x1800031c2  mov     r8, rbx
0x1800031c5  lea     rdx, _GUID_424c1b8c_a1ba_44d7_ac98_9f8f457701a5
0x1800031cc  mov     rax, [rcx]
0x1800031cf  mov     rax, [rax+0E0h]
0x1800031d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031db  test    eax, eax
0x1800031dd  js      loc_1800032CE
0x1800031e3  mov     rcx, [rbp+var_18]
0x1800031e7  mov     rax, [rcx]
0x1800031ea  mov     rax, [rax+138h]
0x1800031f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f6  mov     r14, rax
0x1800031f9  mov     [rbp+var_18], 0
0x180003201  mov     rcx, [rax]
0x180003204  mov     rax, [rcx+8]
0x180003208  mov     rcx, r14
0x18000320b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003210  cmp     dword ptr [rsi+10h], 0
0x180003214  mov     r12, rax
0x180003217  mov     dword ptr [rbp+arg_18], 2
0x18000321e  jz      short loc_18000326F
0x180003220  mov     rcx, [rbx]
0x180003223  lea     r9, [rbp+var_20]
0x180003227  lea     r8, [rbp+var_10]
0x18000322b  mov     [rbp+var_10], 0
0x180003233  lea     rdx, aIsLoginPage; "IS_LOGIN_PAGE"
0x18000323a  mov     [rbp+var_20], 0
0x180003241  mov     rax, [rcx+78h]
0x180003245  mov     rcx, rbx
0x180003248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000324d  cmp     eax, 80070585h
0x180003252  jz      short loc_18000326F
0x180003254  test    eax, eax
0x180003256  js      short loc_1800032CE
0x180003258  mov     rax, [rbp+var_10]
0x18000325c  cmp     byte ptr [rax], 30h ; '0'
0x18000325f  jnz     short loc_180003267
0x180003261  cmp     byte ptr [rax+1], 0
0x180003265  jz      short loc_18000326F
0x180003267  mov     dword ptr [rdi], 1
0x18000326d  jmp     short loc_1800032CC
0x18000326f  mov     rax, [rbx]
0x180003272  mov     rcx, rbx
0x180003275  mov     rax, [rax+18h]
0x180003279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000327e  mov     rdx, rax
0x180003281  mov     rcx, [rax]
0x180003284  mov     rax, [rcx+40h]
0x180003288  mov     rcx, rdx
0x18000328b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003290  mov     rbx, [rsi]
0x180003293  mov     r15, rax
0x180003296  jmp     short loc_1800032C1
0x180003298  lea     rax, [rbp+arg_18]
0x18000329c  mov     r9, r15; char *
0x18000329f  mov     r8, r14; struct IHttpUser *
0x1800032a2  mov     [rsp+50h+var_30], rax; enum AUTHORIZATION_ACCESS_TYPE *
0x1800032a7  mov     rdx, r12; unsigned __int16 *
0x1800032aa  mov     rcx, rbx; this
0x1800032ad  call    ?CheckAuthorizationRule@URL_AUTHZ_RULE_ENTRY@@QEAAJPEBGPEAVIHttpUser@@PEBDPEAW4AUTHORIZATION_ACCESS_TYPE@@@Z; URL_AUTHZ_RULE_ENTRY::CheckAuthorizationRule(ushort const *,IHttpUser *,char const *,AUTHORIZATION_ACCESS_TYPE *)
0x1800032b2  test    eax, eax
0x1800032b4  js      short loc_1800032CE
0x1800032b6  mov     ecx, dword ptr [rbp+arg_18]
0x1800032b9  cmp     ecx, 2
0x1800032bc  jnz     short loc_1800032E7
0x1800032be  mov     rbx, [rbx]
0x1800032c1  cmp     rbx, rsi
0x1800032c4  jnz     short loc_180003298
0x1800032c6  mov     dword ptr [rdi], 0
0x1800032cc  xor     eax, eax
0x1800032ce  lea     r11, [rsp+50h+var_s0]
0x1800032d3  mov     rbx, [r11+30h]
0x1800032d7  mov     rsi, [r11+38h]
0x1800032db  mov     rsp, r11
0x1800032de  pop     r15
0x1800032e0  pop     r14
0x1800032e2  pop     r12
0x1800032e4  pop     rdi
0x1800032e5  pop     rbp
0x1800032e6  retn
0x1800032e7  xor     eax, eax
0x1800032e9  test    ecx, ecx
0x1800032eb  setz    al
0x1800032ee  mov     [rdi], eax
0x1800032f0  jmp     short loc_1800032CC
```
