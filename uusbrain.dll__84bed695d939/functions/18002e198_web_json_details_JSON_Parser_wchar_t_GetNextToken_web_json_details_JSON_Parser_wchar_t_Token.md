# web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)

- ea: `0x18002e198`
- end: `0x18002e511`
- name: `?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z`
- size: `889`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dbdc`
- `0x18002dd88`
- `0x18002f6a4`
- `0x180030358`
- `0x180030674`

## callees

- `0x180029a10`
- `0x18002e198`
- `0x18002f1a4`
- `0x180042718`
- `0x180047a30`

## pseudocode

```c
char __fastcall web::json::details::JSON_Parser<wchar_t>::GetNextToken(int *a1, __int64 a2)
{
  const struct web::json::details::json_error_category_impl *v2; // r14
  __int64 v5; // rcx
  unsigned __int16 v6; // ax
  unsigned __int16 v7; // si
  const struct web::json::details::json_error_category_impl *v8; // rax
  int v9; // eax
  bool v10; // zf
  _QWORD *v11; // rdi
  __int128 v13; // [rsp+20h] [rbp-28h]

  v2 = (const struct web::json::details::json_error_category_impl *)(a2 + 8);
  while ( 1 )
  {
    do
    {
      v6 = (**(__int64 (__fastcall ***)(int *))a1)(a1);
      v7 = v6;
    }
    while ( v6 != 0xFFFF && (unsigned int)o_iswspace_0(v6) );
    *(_DWORD *)a2 = 0;
    *(_QWORD *)(a2 + 40) = *((_QWORD *)a1 + 1);
    *(_QWORD *)(a2 + 48) = *((_QWORD *)a1 + 2);
    v8 = v2;
    *(_QWORD *)(a2 + 24) = 0;
    if ( *(_QWORD *)(a2 + 32) > 7u )
      v8 = *(const struct web::json::details::json_error_category_impl **)v2;
    *(_WORD *)v8 = 0;
    if ( v7 == 0xFFFF )
      return (char)v8;
    if ( v7 > 0x37u )
      break;
    if ( v7 == 55 )
      goto LABEL_27;
    if ( v7 > 0x31u )
    {
      switch ( v7 )
      {
        case '2':
          goto LABEL_27;
        case '3':
          goto LABEL_27;
        case '4':
          goto LABEL_27;
      }
      v5 = (unsigned int)v7 - 53;
      if ( v7 == 53 )
        goto LABEL_27;
LABEL_26:
      if ( (_DWORD)v5 == 1 )
      {
LABEL_27:
        LOBYTE(v8) = web::json::details::JSON_Parser<wchar_t>::CompleteNumberLiteral((__int64)a1, v7, a2);
        if ( (_BYTE)v8 )
          return (char)v8;
        LODWORD(v13) = 6;
        goto LABEL_71;
      }
LABEL_47:
      LODWORD(v13) = 8;
LABEL_71:
      v8 = web::json::details::json_error_category((web::json::details *)v5);
      *((_QWORD *)&v13 + 1) = v8;
      *(_OWORD *)(a2 + 72) = v13;
      return (char)v8;
    }
    switch ( v7 )
    {
      case '1':
        goto LABEL_27;
      case '"':
        LOBYTE(v8) = (*(__int64 (__fastcall **)(int *, __int64))(*(_QWORD *)a1 + 24LL))(a1, a2);
        if ( (_BYTE)v8 )
          return (char)v8;
        LODWORD(v13) = 7;
        goto LABEL_71;
      case ',':
        *(_DWORD *)a2 = 5;
        *((_QWORD *)v2 + 2) = 0;
        if ( *((_QWORD *)v2 + 3) > 7u )
          v2 = *(const struct web::json::details::json_error_category_impl **)v2;
        *(_WORD *)v2 = 0;
        return (char)v8;
      case '-':
        goto LABEL_27;
    }
    v5 = (unsigned int)v7 - 47;
    if ( v7 != 47 )
      goto LABEL_26;
    if ( !(*(unsigned __int8 (__fastcall **)(int *, __int64))(*(_QWORD *)a1 + 16LL))(a1, a2) )
    {
      v9 = 3;
      goto LABEL_70;
    }
  }
  if ( v7 > 0x66u )
  {
    switch ( v7 )
    {
      case 'n':
        if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 117
          && (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 108 )
        {
          LOWORD(v8) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
          if ( (_WORD)v8 == 108 )
          {
            *(_DWORD *)a2 = 11;
            return (char)v8;
          }
        }
        break;
      case 't':
        if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 114
          && (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 117 )
        {
          LOWORD(v8) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
          if ( (_WORD)v8 == 101 )
          {
            *(_DWORD *)a2 = 10;
            *(_BYTE *)(a2 + 56) = 1;
            return (char)v8;
          }
        }
        break;
      case '{':
LABEL_53:
        v5 = 1;
        if ( ++*((_QWORD *)a1 + 3) > 0x80u )
        {
          LODWORD(v13) = 10;
          goto LABEL_71;
        }
        LODWORD(v8) = 3;
        if ( v7 == 123 )
          LODWORD(v8) = 1;
LABEL_57:
        *(_DWORD *)a2 = (_DWORD)v8;
        goto LABEL_58;
      default:
        v10 = v7 == 125;
        goto LABEL_46;
    }
LABEL_69:
    v9 = 4;
LABEL_70:
    LODWORD(v13) = v9;
    goto LABEL_71;
  }
  if ( v7 == 102 )
  {
    if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 97
      && (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 108
      && (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 115 )
    {
      LOWORD(v8) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
      if ( (_WORD)v8 == 101 )
      {
        *(_DWORD *)a2 = 10;
        *(_BYTE *)(a2 + 56) = 0;
        return (char)v8;
      }
    }
    goto LABEL_69;
  }
  if ( v7 == 56 || v7 == 57 )
    goto LABEL_27;
  if ( v7 != 58 )
  {
    v5 = (unsigned int)v7 - 91;
    if ( v7 != 91 )
    {
      v10 = (_DWORD)v5 == 2;
LABEL_46:
      if ( !v10 )
        goto LABEL_47;
      --*((_QWORD *)a1 + 3);
      if ( a1[6] < 0 )
      {
        LODWORD(v13) = 9;
        goto LABEL_71;
      }
      LODWORD(v8) = 4;
      if ( v7 == 125 )
        LODWORD(v8) = 2;
      goto LABEL_57;
    }
    goto LABEL_53;
  }
  *(_DWORD *)a2 = 6;
LABEL_58:
  v11 = (_QWORD *)(a2 + 8);
  v11[2] = 0;
  if ( v11[3] > 7u )
    v11 = (_QWORD *)*v11;
  *(_WORD *)v11 = 0;
  return (char)v8;
}

```

## disassembly

```asm
0x18002e198  mov     rax, rsp
0x18002e19b  mov     [rax+8], rbx
0x18002e19f  mov     [rax+10h], rbp
0x18002e1a3  mov     [rax+18h], rsi
0x18002e1a7  mov     [rax+20h], rdi
0x18002e1ab  push    r12
0x18002e1ad  push    r13
0x18002e1af  push    r14
0x18002e1b1  sub     rsp, 30h
0x18002e1b5  xor     ebp, ebp
0x18002e1b7  lea     r14, [rdx+8]
0x18002e1bb  mov     rdi, rdx
0x18002e1be  mov     rbx, rcx
0x18002e1c1  mov     r13d, 0FFFFh
0x18002e1c7  lea     r12d, [rbp+2]
0x18002e1cb  jmp     short loc_18002E1D9
0x18002e1cd  movzx   ecx, si
0x18002e1d0  call    _o_iswspace_0
0x18002e1d5  test    eax, eax
0x18002e1d7  jz      short loc_18002E1F0
0x18002e1d9  mov     rax, [rbx]
0x18002e1dc  mov     rcx, rbx
0x18002e1df  mov     rax, [rax]
0x18002e1e2  call    _guard_dispatch_icall
0x18002e1e7  movzx   esi, ax
0x18002e1ea  cmp     ax, r13w
0x18002e1ee  jnz     short loc_18002E1CD
0x18002e1f0  mov     [rdi], ebp
0x18002e1f2  mov     rax, [rbx+8]
0x18002e1f6  mov     [rdi+28h], rax
0x18002e1fa  mov     rax, [rbx+10h]
0x18002e1fe  mov     [rdi+30h], rax
0x18002e202  mov     rax, r14
0x18002e205  mov     [rdi+18h], rbp
0x18002e209  cmp     qword ptr [rdi+20h], 7
0x18002e20e  jbe     short loc_18002E213
0x18002e210  mov     rax, [r14]
0x18002e213  mov     [rax], bp
0x18002e216  cmp     si, r13w
0x18002e21a  jz      loc_18002E4F2
0x18002e220  cmp     si, 37h ; '7'
0x18002e224  ja      loc_18002E306
0x18002e22a  jz      loc_18002E2E3
0x18002e230  cmp     si, 31h ; '1'
0x18002e234  ja      loc_18002E2C3
0x18002e23a  jz      loc_18002E2E3
0x18002e240  movzx   ecx, si
0x18002e243  sub     ecx, 22h ; '"'
0x18002e246  jz      short loc_18002E29C
0x18002e248  sub     ecx, 0Ah
0x18002e24b  jz      short loc_18002E27F
0x18002e24d  sub     ecx, 1
0x18002e250  jz      loc_18002E2E3
0x18002e256  sub     ecx, r12d
0x18002e259  jnz     short loc_18002E2DA
0x18002e25b  mov     rax, [rbx]
0x18002e25e  mov     rdx, rdi
0x18002e261  mov     rcx, rbx
0x18002e264  mov     rax, [rax+10h]
0x18002e268  call    _guard_dispatch_icall
0x18002e26d  test    al, al
0x18002e26f  jnz     loc_18002E1D9
0x18002e275  mov     eax, 3
0x18002e27a  jmp     loc_18002E4DA
0x18002e27f  mov     dword ptr [rdi], 5
0x18002e285  mov     [r14+10h], rbp
0x18002e289  cmp     qword ptr [r14+18h], 7
0x18002e28e  jbe     short loc_18002E293
0x18002e290  mov     r14, [r14]
0x18002e293  mov     [r14], bp
0x18002e297  jmp     loc_18002E4F2
0x18002e29c  mov     rax, [rbx]
0x18002e29f  mov     rdx, rdi
0x18002e2a2  mov     rcx, rbx
0x18002e2a5  mov     rax, [rax+18h]
0x18002e2a9  call    _guard_dispatch_icall
0x18002e2ae  test    al, al
0x18002e2b0  jnz     loc_18002E4F2
0x18002e2b6  mov     dword ptr [rsp+48h+var_28], 7
0x18002e2be  jmp     loc_18002E4DE
0x18002e2c3  movzx   ecx, si
0x18002e2c6  sub     ecx, 32h ; '2'
0x18002e2c9  jz      short loc_18002E2E3
0x18002e2cb  sub     ecx, 1
0x18002e2ce  jz      short loc_18002E2E3
0x18002e2d0  sub     ecx, 1
0x18002e2d3  jz      short loc_18002E2E3
0x18002e2d5  sub     ecx, 1
0x18002e2d8  jz      short loc_18002E2E3
0x18002e2da  cmp     ecx, 1
0x18002e2dd  jnz     loc_18002E3CF
0x18002e2e3  mov     r8, rdi
0x18002e2e6  movzx   edx, si
0x18002e2e9  mov     rcx, rbx
0x18002e2ec  call    ?CompleteNumberLiteral@?$JSON_Parser@_W@details@json@web@@AEAA_N_WAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::CompleteNumberLiteral(wchar_t,web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002e2f1  test    al, al
0x18002e2f3  jnz     loc_18002E4F2
0x18002e2f9  mov     dword ptr [rsp+48h+var_28], 6
0x18002e301  jmp     loc_18002E4DE
0x18002e306  cmp     si, 66h ; 'f'
0x18002e30a  ja      loc_18002E3AF
0x18002e310  jz      short loc_18002E340
0x18002e312  movzx   ecx, si
0x18002e315  sub     ecx, 38h ; '8'
0x18002e318  jz      short loc_18002E2E3
0x18002e31a  sub     ecx, 1
0x18002e31d  jz      short loc_18002E2E3
0x18002e31f  sub     ecx, 1
0x18002e322  jz      short loc_18002E335
0x18002e324  sub     ecx, 21h ; '!'
0x18002e327  jz      loc_18002E401
0x18002e32d  cmp     ecx, r12d
0x18002e330  jmp     loc_18002E3CD
0x18002e335  mov     dword ptr [rdi], 6
0x18002e33b  jmp     loc_18002E42F
0x18002e340  mov     rax, [rbx]
0x18002e343  mov     rcx, rbx
0x18002e346  mov     rax, [rax]
0x18002e349  call    _guard_dispatch_icall
0x18002e34e  cmp     ax, 61h ; 'a'
0x18002e352  jnz     loc_18002E4D5
0x18002e358  mov     rax, [rbx]
0x18002e35b  mov     rcx, rbx
0x18002e35e  mov     rax, [rax]
0x18002e361  call    _guard_dispatch_icall
0x18002e366  cmp     ax, 6Ch ; 'l'
0x18002e36a  jnz     loc_18002E4D5
0x18002e370  mov     rax, [rbx]
0x18002e373  mov     rcx, rbx
0x18002e376  mov     rax, [rax]
0x18002e379  call    _guard_dispatch_icall
0x18002e37e  cmp     ax, 73h ; 's'
0x18002e382  jnz     loc_18002E4D5
0x18002e388  mov     rax, [rbx]
0x18002e38b  mov     rcx, rbx
0x18002e38e  mov     rax, [rax]
0x18002e391  call    _guard_dispatch_icall
0x18002e396  cmp     ax, 65h ; 'e'
0x18002e39a  jnz     loc_18002E4D5
0x18002e3a0  mov     dword ptr [rdi], 0Ah
0x18002e3a6  mov     [rdi+38h], bpl
0x18002e3aa  jmp     loc_18002E4F2
0x18002e3af  cmp     si, 6Eh ; 'n'
0x18002e3b3  jz      loc_18002E491
0x18002e3b9  cmp     si, 74h ; 't'
0x18002e3bd  jz      loc_18002E449
0x18002e3c3  cmp     si, 7Bh ; '{'
0x18002e3c7  jz      short loc_18002E401
0x18002e3c9  cmp     si, 7Dh ; '}'
0x18002e3cd  jz      short loc_18002E3DC
0x18002e3cf  mov     dword ptr [rsp+48h+var_28], 8
0x18002e3d7  jmp     loc_18002E4DE
0x18002e3dc  dec     qword ptr [rbx+18h]
0x18002e3e0  cmp     [rbx+18h], ebp
0x18002e3e3  jge     short loc_18002E3F2
0x18002e3e5  mov     dword ptr [rsp+48h+var_28], 9
0x18002e3ed  jmp     loc_18002E4DE
0x18002e3f2  cmp     si, 7Dh ; '}'
0x18002e3f6  mov     eax, 4
0x18002e3fb  cmovz   eax, r12d
0x18002e3ff  jmp     short loc_18002E42D
0x18002e401  mov     ecx, 1
0x18002e406  add     [rbx+18h], rcx
0x18002e40a  cmp     qword ptr [rbx+18h], 80h
0x18002e412  jbe     short loc_18002E421
0x18002e414  mov     dword ptr [rsp+48h+var_28], 0Ah
0x18002e41c  jmp     loc_18002E4DE
0x18002e421  cmp     si, 7Bh ; '{'
0x18002e425  mov     eax, 3
0x18002e42a  cmovz   eax, ecx
0x18002e42d  mov     [rdi], eax
0x18002e42f  add     rdi, 8
0x18002e433  mov     [rdi+10h], rbp
0x18002e437  cmp     qword ptr [rdi+18h], 7
0x18002e43c  jbe     short loc_18002E441
0x18002e43e  mov     rdi, [rdi]
0x18002e441  mov     [rdi], bp
0x18002e444  jmp     loc_18002E4F2
0x18002e449  mov     rax, [rbx]
0x18002e44c  mov     rcx, rbx
0x18002e44f  mov     rax, [rax]
0x18002e452  call    _guard_dispatch_icall
0x18002e457  cmp     ax, 72h ; 'r'
0x18002e45b  jnz     short loc_18002E4D5
0x18002e45d  mov     rax, [rbx]
0x18002e460  mov     rcx, rbx
0x18002e463  mov     rax, [rax]
0x18002e466  call    _guard_dispatch_icall
0x18002e46b  cmp     ax, 75h ; 'u'
0x18002e46f  jnz     short loc_18002E4D5
0x18002e471  mov     rax, [rbx]
0x18002e474  mov     rcx, rbx
0x18002e477  mov     rax, [rax]
0x18002e47a  call    _guard_dispatch_icall
0x18002e47f  cmp     ax, 65h ; 'e'
0x18002e483  jnz     short loc_18002E4D5
0x18002e485  mov     dword ptr [rdi], 0Ah
0x18002e48b  mov     byte ptr [rdi+38h], 1
0x18002e48f  jmp     short loc_18002E4F2
0x18002e491  mov     rax, [rbx]
0x18002e494  mov     rcx, rbx
0x18002e497  mov     rax, [rax]
0x18002e49a  call    _guard_dispatch_icall
0x18002e49f  cmp     ax, 75h ; 'u'
0x18002e4a3  jnz     short loc_18002E4D5
0x18002e4a5  mov     rax, [rbx]
0x18002e4a8  mov     rcx, rbx
0x18002e4ab  mov     rax, [rax]
0x18002e4ae  call    _guard_dispatch_icall
0x18002e4b3  cmp     ax, 6Ch ; 'l'
0x18002e4b7  jnz     short loc_18002E4D5
0x18002e4b9  mov     rax, [rbx]
0x18002e4bc  mov     rcx, rbx
0x18002e4bf  mov     rax, [rax]
0x18002e4c2  call    _guard_dispatch_icall
0x18002e4c7  cmp     ax, 6Ch ; 'l'
0x18002e4cb  jnz     short loc_18002E4D5
0x18002e4cd  mov     dword ptr [rdi], 0Bh
0x18002e4d3  jmp     short loc_18002E4F2
0x18002e4d5  mov     eax, 4
0x18002e4da  mov     dword ptr [rsp+48h+var_28], eax
0x18002e4de  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18002e4e3  mov     qword ptr [rsp+48h+var_28+8], rax
0x18002e4e8  movups  xmm0, [rsp+48h+var_28]
0x18002e4ed  movdqu  xmmword ptr [rdi+48h], xmm0
0x18002e4f2  mov     rbx, [rsp+48h+arg_0]
0x18002e4f7  mov     rbp, [rsp+48h+arg_8]
0x18002e4fc  mov     rsi, [rsp+48h+arg_10]
0x18002e501  mov     rdi, [rsp+48h+arg_18]
0x18002e506  add     rsp, 30h
0x18002e50a  pop     r14
0x18002e50c  pop     r13
0x18002e50e  pop     r12
0x18002e510  retn
```
