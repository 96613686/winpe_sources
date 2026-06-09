# web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)

- ea: `0x18002e6b0`
- end: `0x18002e9fe`
- name: `?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z`
- size: `846`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002df20`
- `0x18003008c`
- `0x180030844`
- `0x180030b24`

## callees

- `0x180029a10`
- `0x18002e6b0`
- `0x18002fcb4`
- `0x180042718`
- `0x180047a30`

## pseudocode

```c
char __fastcall web::json::details::JSON_Parser<char>::GetNextToken(int *a1, __int64 a2)
{
  const struct web::json::details::json_error_category_impl *v2; // r14
  __int64 v5; // rcx
  int v6; // eax
  int v7; // esi
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
    while ( v6 != -1 && (unsigned int)o_iswspace_0((unsigned __int16)v6) );
    *(_DWORD *)a2 = 0;
    *(_QWORD *)(a2 + 40) = *((_QWORD *)a1 + 1);
    *(_QWORD *)(a2 + 48) = *((_QWORD *)a1 + 2);
    v8 = v2;
    *(_QWORD *)(a2 + 24) = 0;
    if ( *(_QWORD *)(a2 + 32) > 0xFu )
      v8 = *(const struct web::json::details::json_error_category_impl **)v2;
    *(_BYTE *)v8 = 0;
    if ( v7 == -1 )
      return (char)v8;
    if ( v7 > 55 )
      break;
    if ( v7 == 55 )
      goto LABEL_27;
    if ( v7 > 49 )
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
      v5 = (unsigned int)(v7 - 53);
      if ( v7 == 53 )
        goto LABEL_27;
LABEL_26:
      if ( (_DWORD)v5 == 1 )
      {
LABEL_27:
        LOBYTE(v8) = web::json::details::JSON_Parser<char>::CompleteNumberLiteral((__int64)a1, v7, a2);
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
        if ( *((_QWORD *)v2 + 3) > 0xFu )
          v2 = *(const struct web::json::details::json_error_category_impl **)v2;
        *(_BYTE *)v2 = 0;
        return (char)v8;
      case '-':
        goto LABEL_27;
    }
    v5 = (unsigned int)(v7 - 47);
    if ( v7 != 47 )
      goto LABEL_26;
    if ( !(*(unsigned __int8 (__fastcall **)(int *, __int64))(*(_QWORD *)a1 + 16LL))(a1, a2) )
    {
      v9 = 3;
      goto LABEL_70;
    }
  }
  if ( v7 > 102 )
  {
    switch ( v7 )
    {
      case 'n':
        if ( (**(unsigned int (__fastcall ***)(int *))a1)(a1) == 117
          && (**(unsigned int (__fastcall ***)(int *))a1)(a1) == 108 )
        {
          LODWORD(v8) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
          if ( (_DWORD)v8 == 108 )
          {
            *(_DWORD *)a2 = 11;
            return (char)v8;
          }
        }
        break;
      case 't':
        if ( (**(unsigned int (__fastcall ***)(int *))a1)(a1) == 114
          && (**(unsigned int (__fastcall ***)(int *))a1)(a1) == 117 )
        {
          LODWORD(v8) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
          if ( (_DWORD)v8 == 101 )
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
    if ( (**(unsigned int (__fastcall ***)(int *))a1)(a1) == 97
      && (**(unsigned int (__fastcall ***)(int *))a1)(a1) == 108
      && (**(unsigned int (__fastcall ***)(int *))a1)(a1) == 115 )
    {
      LODWORD(v8) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
      if ( (_DWORD)v8 == 101 )
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
    v5 = (unsigned int)(v7 - 91);
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
  if ( v11[3] > 0xFu )
    v11 = (_QWORD *)*v11;
  *(_BYTE *)v11 = 0;
  return (char)v8;
}

```

## disassembly

```asm
0x18002e6b0  mov     [rsp+arg_0], rbx
0x18002e6b5  mov     [rsp+arg_8], rbp
0x18002e6ba  mov     [rsp+arg_10], rsi
0x18002e6bf  push    rdi
0x18002e6c0  push    r12
0x18002e6c2  push    r14
0x18002e6c4  sub     rsp, 30h
0x18002e6c8  xor     ebp, ebp
0x18002e6ca  lea     r14, [rdx+8]
0x18002e6ce  mov     rdi, rdx
0x18002e6d1  mov     rbx, rcx
0x18002e6d4  lea     r12d, [rbp+2]
0x18002e6d8  jmp     short loc_18002E6E6
0x18002e6da  movzx   ecx, si
0x18002e6dd  call    _o_iswspace_0
0x18002e6e2  test    eax, eax
0x18002e6e4  jz      short loc_18002E6FB
0x18002e6e6  mov     rax, [rbx]
0x18002e6e9  mov     rcx, rbx
0x18002e6ec  mov     rax, [rax]
0x18002e6ef  call    _guard_dispatch_icall
0x18002e6f4  mov     esi, eax
0x18002e6f6  cmp     eax, 0FFFFFFFFh
0x18002e6f9  jnz     short loc_18002E6DA
0x18002e6fb  mov     [rdi], ebp
0x18002e6fd  mov     rax, [rbx+8]
0x18002e701  mov     [rdi+28h], rax
0x18002e705  mov     rax, [rbx+10h]
0x18002e709  mov     [rdi+30h], rax
0x18002e70d  mov     rax, r14
0x18002e710  mov     [rdi+18h], rbp
0x18002e714  cmp     qword ptr [rdi+20h], 0Fh
0x18002e719  jbe     short loc_18002E71E
0x18002e71b  mov     rax, [r14]
0x18002e71e  mov     [rax], bpl
0x18002e721  cmp     esi, 0FFFFFFFFh
0x18002e724  jz      loc_18002E9E5
0x18002e72a  cmp     esi, 37h ; '7'
0x18002e72d  jg      loc_18002E80B
0x18002e733  jz      loc_18002E7E8
0x18002e739  cmp     esi, 31h ; '1'
0x18002e73c  jg      loc_18002E7C9
0x18002e742  jz      loc_18002E7E8
0x18002e748  mov     ecx, esi
0x18002e74a  sub     ecx, 22h ; '"'
0x18002e74d  jz      short loc_18002E7A2
0x18002e74f  sub     ecx, 0Ah
0x18002e752  jz      short loc_18002E786
0x18002e754  sub     ecx, 1
0x18002e757  jz      loc_18002E7E8
0x18002e75d  sub     ecx, r12d
0x18002e760  jnz     short loc_18002E7DF
0x18002e762  mov     rax, [rbx]
0x18002e765  mov     rdx, rdi
0x18002e768  mov     rcx, rbx
0x18002e76b  mov     rax, [rax+10h]
0x18002e76f  call    _guard_dispatch_icall
0x18002e774  test    al, al
0x18002e776  jnz     loc_18002E6E6
0x18002e77c  mov     eax, 3
0x18002e781  jmp     loc_18002E9CD
0x18002e786  mov     dword ptr [rdi], 5
0x18002e78c  mov     [r14+10h], rbp
0x18002e790  cmp     qword ptr [r14+18h], 0Fh
0x18002e795  jbe     short loc_18002E79A
0x18002e797  mov     r14, [r14]
0x18002e79a  mov     [r14], bpl
0x18002e79d  jmp     loc_18002E9E5
0x18002e7a2  mov     rax, [rbx]
0x18002e7a5  mov     rdx, rdi
0x18002e7a8  mov     rcx, rbx
0x18002e7ab  mov     rax, [rax+18h]
0x18002e7af  call    _guard_dispatch_icall
0x18002e7b4  test    al, al
0x18002e7b6  jnz     loc_18002E9E5
0x18002e7bc  mov     dword ptr [rsp+48h+var_28], 7
0x18002e7c4  jmp     loc_18002E9D1
0x18002e7c9  mov     ecx, esi
0x18002e7cb  sub     ecx, 32h ; '2'
0x18002e7ce  jz      short loc_18002E7E8
0x18002e7d0  sub     ecx, 1
0x18002e7d3  jz      short loc_18002E7E8
0x18002e7d5  sub     ecx, 1
0x18002e7d8  jz      short loc_18002E7E8
0x18002e7da  sub     ecx, 1
0x18002e7dd  jz      short loc_18002E7E8
0x18002e7df  cmp     ecx, 1
0x18002e7e2  jnz     loc_18002E8CA
0x18002e7e8  mov     r8, rdi
0x18002e7eb  mov     dl, sil
0x18002e7ee  mov     rcx, rbx
0x18002e7f1  call    ?CompleteNumberLiteral@?$JSON_Parser@D@details@json@web@@AEAA_NDAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::CompleteNumberLiteral(char,web::json::details::JSON_Parser<char>::Token &)
0x18002e7f6  test    al, al
0x18002e7f8  jnz     loc_18002E9E5
0x18002e7fe  mov     dword ptr [rsp+48h+var_28], 6
0x18002e806  jmp     loc_18002E9D1
0x18002e80b  cmp     esi, 66h ; 'f'
0x18002e80e  jg      loc_18002E8AE
0x18002e814  jz      short loc_18002E843
0x18002e816  mov     ecx, esi
0x18002e818  sub     ecx, 38h ; '8'
0x18002e81b  jz      short loc_18002E7E8
0x18002e81d  sub     ecx, 1
0x18002e820  jz      short loc_18002E7E8
0x18002e822  sub     ecx, 1
0x18002e825  jz      short loc_18002E838
0x18002e827  sub     ecx, 21h ; '!'
0x18002e82a  jz      loc_18002E8FB
0x18002e830  cmp     ecx, r12d
0x18002e833  jmp     loc_18002E8C8
0x18002e838  mov     dword ptr [rdi], 6
0x18002e83e  jmp     loc_18002E928
0x18002e843  mov     rax, [rbx]
0x18002e846  mov     rcx, rbx
0x18002e849  mov     rax, [rax]
0x18002e84c  call    _guard_dispatch_icall
0x18002e851  cmp     eax, 61h ; 'a'
0x18002e854  jnz     loc_18002E9C8
0x18002e85a  mov     rax, [rbx]
0x18002e85d  mov     rcx, rbx
0x18002e860  mov     rax, [rax]
0x18002e863  call    _guard_dispatch_icall
0x18002e868  cmp     eax, 6Ch ; 'l'
0x18002e86b  jnz     loc_18002E9C8
0x18002e871  mov     rax, [rbx]
0x18002e874  mov     rcx, rbx
0x18002e877  mov     rax, [rax]
0x18002e87a  call    _guard_dispatch_icall
0x18002e87f  cmp     eax, 73h ; 's'
0x18002e882  jnz     loc_18002E9C8
0x18002e888  mov     rax, [rbx]
0x18002e88b  mov     rcx, rbx
0x18002e88e  mov     rax, [rax]
0x18002e891  call    _guard_dispatch_icall
0x18002e896  cmp     eax, 65h ; 'e'
0x18002e899  jnz     loc_18002E9C8
0x18002e89f  mov     dword ptr [rdi], 0Ah
0x18002e8a5  mov     [rdi+38h], bpl
0x18002e8a9  jmp     loc_18002E9E5
0x18002e8ae  cmp     esi, 6Eh ; 'n'
0x18002e8b1  jz      loc_18002E987
0x18002e8b7  cmp     esi, 74h ; 't'
0x18002e8ba  jz      loc_18002E942
0x18002e8c0  cmp     esi, 7Bh ; '{'
0x18002e8c3  jz      short loc_18002E8FB
0x18002e8c5  cmp     esi, 7Dh ; '}'
0x18002e8c8  jz      short loc_18002E8D7
0x18002e8ca  mov     dword ptr [rsp+48h+var_28], 8
0x18002e8d2  jmp     loc_18002E9D1
0x18002e8d7  dec     qword ptr [rbx+18h]
0x18002e8db  cmp     [rbx+18h], ebp
0x18002e8de  jge     short loc_18002E8ED
0x18002e8e0  mov     dword ptr [rsp+48h+var_28], 9
0x18002e8e8  jmp     loc_18002E9D1
0x18002e8ed  cmp     esi, 7Dh ; '}'
0x18002e8f0  mov     eax, 4
0x18002e8f5  cmovz   eax, r12d
0x18002e8f9  jmp     short loc_18002E926
0x18002e8fb  mov     ecx, 1
0x18002e900  add     [rbx+18h], rcx
0x18002e904  cmp     qword ptr [rbx+18h], 80h
0x18002e90c  jbe     short loc_18002E91B
0x18002e90e  mov     dword ptr [rsp+48h+var_28], 0Ah
0x18002e916  jmp     loc_18002E9D1
0x18002e91b  cmp     esi, 7Bh ; '{'
0x18002e91e  mov     eax, 3
0x18002e923  cmovz   eax, ecx
0x18002e926  mov     [rdi], eax
0x18002e928  add     rdi, 8
0x18002e92c  mov     [rdi+10h], rbp
0x18002e930  cmp     qword ptr [rdi+18h], 0Fh
0x18002e935  jbe     short loc_18002E93A
0x18002e937  mov     rdi, [rdi]
0x18002e93a  mov     [rdi], bpl
0x18002e93d  jmp     loc_18002E9E5
0x18002e942  mov     rax, [rbx]
0x18002e945  mov     rcx, rbx
0x18002e948  mov     rax, [rax]
0x18002e94b  call    _guard_dispatch_icall
0x18002e950  cmp     eax, 72h ; 'r'
0x18002e953  jnz     short loc_18002E9C8
0x18002e955  mov     rax, [rbx]
0x18002e958  mov     rcx, rbx
0x18002e95b  mov     rax, [rax]
0x18002e95e  call    _guard_dispatch_icall
0x18002e963  cmp     eax, 75h ; 'u'
0x18002e966  jnz     short loc_18002E9C8
0x18002e968  mov     rax, [rbx]
0x18002e96b  mov     rcx, rbx
0x18002e96e  mov     rax, [rax]
0x18002e971  call    _guard_dispatch_icall
0x18002e976  cmp     eax, 65h ; 'e'
0x18002e979  jnz     short loc_18002E9C8
0x18002e97b  mov     dword ptr [rdi], 0Ah
0x18002e981  mov     byte ptr [rdi+38h], 1
0x18002e985  jmp     short loc_18002E9E5
0x18002e987  mov     rax, [rbx]
0x18002e98a  mov     rcx, rbx
0x18002e98d  mov     rax, [rax]
0x18002e990  call    _guard_dispatch_icall
0x18002e995  cmp     eax, 75h ; 'u'
0x18002e998  jnz     short loc_18002E9C8
0x18002e99a  mov     rax, [rbx]
0x18002e99d  mov     rcx, rbx
0x18002e9a0  mov     rax, [rax]
0x18002e9a3  call    _guard_dispatch_icall
0x18002e9a8  cmp     eax, 6Ch ; 'l'
0x18002e9ab  jnz     short loc_18002E9C8
0x18002e9ad  mov     rax, [rbx]
0x18002e9b0  mov     rcx, rbx
0x18002e9b3  mov     rax, [rax]
0x18002e9b6  call    _guard_dispatch_icall
0x18002e9bb  cmp     eax, 6Ch ; 'l'
0x18002e9be  jnz     short loc_18002E9C8
0x18002e9c0  mov     dword ptr [rdi], 0Bh
0x18002e9c6  jmp     short loc_18002E9E5
0x18002e9c8  mov     eax, 4
0x18002e9cd  mov     dword ptr [rsp+48h+var_28], eax
0x18002e9d1  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18002e9d6  mov     qword ptr [rsp+48h+var_28+8], rax
0x18002e9db  movups  xmm0, [rsp+48h+var_28]
0x18002e9e0  movdqu  xmmword ptr [rdi+48h], xmm0
0x18002e9e5  mov     rbx, [rsp+48h+arg_0]
0x18002e9ea  mov     rbp, [rsp+48h+arg_8]
0x18002e9ef  mov     rsi, [rsp+48h+arg_10]
0x18002e9f4  add     rsp, 30h
0x18002e9f8  pop     r14
0x18002e9fa  pop     r12
0x18002e9fc  pop     rdi
0x18002e9fd  retn
```
