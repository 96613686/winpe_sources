# web::json::details::append_escape_string<char>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18002d60c`
- end: `0x18002dab4`
- name: `??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z`
- size: `1192`
- prototype: `void __fastcall(_QWORD *Src, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002cd1c`
- `0x18002cdd0`

## callees

- `0x180027ecc`
- `0x18002d60c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall web::json::details::append_escape_string<char>(_QWORD *Src, char *a2)
{
  char *v3; // rcx
  __int64 v4; // r8
  char *v5; // rdi
  char *v6; // rsi
  char v7; // r9
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rax
  unsigned __int64 v10; // rcx
  _QWORD *v11; // rax
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rax
  unsigned __int64 v14; // rcx
  _QWORD *v15; // rax
  unsigned __int64 v16; // rcx
  char v17; // r9
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  unsigned __int64 v21; // rcx
  _QWORD *v22; // rax
  unsigned __int64 v23; // rcx
  _QWORD *v24; // rax
  unsigned __int64 v25; // rcx
  _QWORD *v26; // rax
  unsigned __int64 v27; // rcx
  _QWORD *v28; // rax
  unsigned __int64 v29; // rcx
  _QWORD *v30; // rax
  unsigned __int64 v31; // rcx
  _QWORD *v32; // rax
  unsigned __int64 v33; // rcx
  _QWORD *v34; // rax
  unsigned __int64 v35; // rcx
  _QWORD *v36; // rax
  unsigned __int64 v37; // rcx
  _QWORD *v38; // rax
  unsigned __int64 v39; // rcx
  _QWORD *v40; // rax
  unsigned __int64 v41; // rcx
  _QWORD *v42; // rax
  unsigned __int64 v43; // rcx
  _QWORD *v44; // rax
  unsigned __int64 v45; // rcx
  _QWORD *v46; // rax

  v3 = a2;
  if ( *((_QWORD *)a2 + 3) <= 0xFu )
  {
    v5 = a2;
    v4 = (__int64)a2;
  }
  else
  {
    v3 = *(char **)a2;
    v4 = *(_QWORD *)a2;
    v5 = *(char **)a2;
  }
  v6 = (char *)(v4 + *((_QWORD *)a2 + 2));
  if ( v3 != v6 )
  {
    do
    {
      v7 = *v5;
      switch ( *v5 )
      {
        case 8:
          v43 = Src[2];
          if ( v43 >= Src[3] )
          {
            std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, (__int64)a2, v4, 92);
          }
          else
          {
            Src[2] = v43 + 1;
            v44 = Src;
            if ( Src[3] > 0xFu )
              v44 = (_QWORD *)*Src;
            *(_WORD *)((char *)v44 + v43) = 92;
          }
          v45 = Src[2];
          if ( v45 < Src[3] )
          {
            Src[2] = v45 + 1;
            v46 = Src;
            if ( Src[3] > 0xFu )
              v46 = (_QWORD *)*Src;
            *(_WORD *)((char *)v46 + v45) = 98;
            goto LABEL_114;
          }
          v7 = 98;
          break;
        case 9:
          v39 = Src[2];
          if ( v39 >= Src[3] )
          {
            std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, (__int64)a2, v4, 92);
          }
          else
          {
            Src[2] = v39 + 1;
            v40 = Src;
            if ( Src[3] > 0xFu )
              v40 = (_QWORD *)*Src;
            *(_WORD *)((char *)v40 + v39) = 92;
          }
          v41 = Src[2];
          if ( v41 < Src[3] )
          {
            Src[2] = v41 + 1;
            v42 = Src;
            if ( Src[3] > 0xFu )
              v42 = (_QWORD *)*Src;
            *(_WORD *)((char *)v42 + v41) = 116;
            goto LABEL_114;
          }
          v7 = 116;
          break;
        case 10:
          v35 = Src[2];
          if ( v35 >= Src[3] )
          {
            std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, (__int64)a2, v4, 92);
          }
          else
          {
            Src[2] = v35 + 1;
            v36 = Src;
            if ( Src[3] > 0xFu )
              v36 = (_QWORD *)*Src;
            *(_WORD *)((char *)v36 + v35) = 92;
          }
          v37 = Src[2];
          if ( v37 < Src[3] )
          {
            Src[2] = v37 + 1;
            v38 = Src;
            if ( Src[3] > 0xFu )
              v38 = (_QWORD *)*Src;
            *(_WORD *)((char *)v38 + v37) = 110;
            goto LABEL_114;
          }
          v7 = 110;
          break;
        case 12:
          v31 = Src[2];
          if ( v31 >= Src[3] )
          {
            std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, (__int64)a2, v4, 92);
          }
          else
          {
            Src[2] = v31 + 1;
            v32 = Src;
            if ( Src[3] > 0xFu )
              v32 = (_QWORD *)*Src;
            *(_WORD *)((char *)v32 + v31) = 92;
          }
          v33 = Src[2];
          if ( v33 < Src[3] )
          {
            Src[2] = v33 + 1;
            v34 = Src;
            if ( Src[3] > 0xFu )
              v34 = (_QWORD *)*Src;
            *(_WORD *)((char *)v34 + v33) = 102;
            goto LABEL_114;
          }
          v7 = 102;
          break;
        case 13:
          v27 = Src[2];
          if ( v27 >= Src[3] )
          {
            std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, (__int64)a2, v4, 92);
          }
          else
          {
            Src[2] = v27 + 1;
            v28 = Src;
            if ( Src[3] > 0xFu )
              v28 = (_QWORD *)*Src;
            *(_WORD *)((char *)v28 + v27) = 92;
          }
          v29 = Src[2];
          if ( v29 < Src[3] )
          {
            Src[2] = v29 + 1;
            v30 = Src;
            if ( Src[3] > 0xFu )
              v30 = (_QWORD *)*Src;
            *(_WORD *)((char *)v30 + v29) = 114;
            goto LABEL_114;
          }
          v7 = 114;
          break;
        case 34:
          v23 = Src[2];
          if ( v23 >= Src[3] )
          {
            std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, (__int64)a2, v4, 92);
          }
          else
          {
            Src[2] = v23 + 1;
            v24 = Src;
            if ( Src[3] > 0xFu )
              v24 = (_QWORD *)*Src;
            *(_WORD *)((char *)v24 + v23) = 92;
          }
          v25 = Src[2];
          if ( v25 < Src[3] )
          {
            Src[2] = v25 + 1;
            v26 = Src;
            if ( Src[3] > 0xFu )
              v26 = (_QWORD *)*Src;
            *(_WORD *)((char *)v26 + v25) = 34;
            goto LABEL_114;
          }
          v7 = 34;
          break;
        default:
          v8 = Src[2];
          if ( *v5 == 92 )
          {
            if ( v8 >= Src[3] )
            {
              std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, (__int64)a2, v4, 92);
            }
            else
            {
              Src[2] = v8 + 1;
              v20 = Src;
              if ( Src[3] > 0xFu )
                v20 = (_QWORD *)*Src;
              *(_WORD *)((char *)v20 + v8) = 92;
            }
            v21 = Src[2];
            if ( v21 < Src[3] )
            {
              Src[2] = v21 + 1;
              v22 = Src;
              if ( Src[3] > 0xFu )
                v22 = (_QWORD *)*Src;
              *(_WORD *)((char *)v22 + v21) = 92;
              goto LABEL_114;
            }
            v7 = 92;
          }
          else
          {
            if ( (unsigned __int8)v7 <= 0x1Fu )
            {
              if ( v8 >= Src[3] )
              {
                std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(
                  Src,
                  (__int64)a2,
                  v4,
                  92);
              }
              else
              {
                Src[2] = v8 + 1;
                v9 = Src;
                if ( Src[3] > 0xFu )
                  v9 = (_QWORD *)*Src;
                *(_WORD *)((char *)v9 + v8) = 92;
              }
              v10 = Src[2];
              if ( v10 >= Src[3] )
              {
                std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(
                  Src,
                  (__int64)a2,
                  v4,
                  117);
              }
              else
              {
                Src[2] = v10 + 1;
                v11 = Src;
                if ( Src[3] > 0xFu )
                  v11 = (_QWORD *)*Src;
                *(_WORD *)((char *)v11 + v10) = 117;
              }
              v12 = Src[2];
              if ( v12 >= Src[3] )
              {
                std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(
                  Src,
                  (__int64)a2,
                  v4,
                  48);
              }
              else
              {
                Src[2] = v12 + 1;
                v13 = Src;
                if ( Src[3] > 0xFu )
                  v13 = (_QWORD *)*Src;
                *(_WORD *)((char *)v13 + v12) = 48;
              }
              v14 = Src[2];
              if ( v14 >= Src[3] )
              {
                std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(
                  Src,
                  (__int64)a2,
                  v4,
                  48);
              }
              else
              {
                Src[2] = v14 + 1;
                v15 = Src;
                if ( Src[3] > 0xFu )
                  v15 = (_QWORD *)*Src;
                *(_WORD *)((char *)v15 + v14) = 48;
              }
              v16 = Src[2];
              v17 = *((_BYTE *)`web::json::details::append_escape_string<char>'::`11'::intToHex
                    + ((unsigned __int64)(unsigned __int8)*v5 >> 4));
              if ( v16 >= Src[3] )
              {
                std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(
                  Src,
                  (__int64)a2,
                  v4,
                  v17);
              }
              else
              {
                Src[2] = v16 + 1;
                v18 = Src;
                if ( Src[3] > 0xFu )
                  v18 = (_QWORD *)*Src;
                *((_BYTE *)v18 + v16) = v17;
                *((_BYTE *)v18 + v16 + 1) = 0;
              }
              v8 = Src[2];
              v7 = *((_BYTE *)`web::json::details::append_escape_string<char>'::`11'::intToHex + (*v5 & 0xFLL));
            }
            if ( v8 < Src[3] )
            {
              Src[2] = v8 + 1;
              v19 = Src;
              if ( Src[3] > 0xFu )
                v19 = (_QWORD *)*Src;
              *((_BYTE *)v19 + v8) = v7;
              *((_BYTE *)v19 + v8 + 1) = 0;
              goto LABEL_114;
            }
          }
          break;
      }
      std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, (__int64)a2, v4, v7);
LABEL_114:
      ++v5;
    }
    while ( v5 != v6 );
  }
}

```

## disassembly

```asm
0x18002d60c  mov     [rsp+arg_8], rbx
0x18002d611  mov     [rsp+arg_10], rbp
0x18002d616  mov     [rsp+arg_18], rsi
0x18002d61b  push    rdi
0x18002d61c  push    r14
0x18002d61e  push    r15
0x18002d620  sub     rsp, 20h
0x18002d624  mov     ebp, 0Fh
0x18002d629  mov     rbx, rcx
0x18002d62c  mov     rcx, rdx
0x18002d62f  cmp     [rdx+18h], rbp
0x18002d633  jbe     short loc_18002D640
0x18002d635  mov     rcx, [rdx]
0x18002d638  mov     r8, rcx
0x18002d63b  mov     rdi, rcx
0x18002d63e  jmp     short loc_18002D646
0x18002d640  mov     rdi, rdx
0x18002d643  mov     r8, rdx
0x18002d646  mov     rsi, [rdx+10h]
0x18002d64a  add     rsi, r8
0x18002d64d  cmp     rcx, rsi
0x18002d650  jz      loc_18002DA9B
0x18002d656  xor     r14d, r14d
0x18002d659  lea     r15, ?intToHex@?L@???$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV45@@Z@4V?$array@D$0BA@@5@B; std::array<char,16> const `web::json::details::append_escape_string<char>(std::string &,std::string const &)'::`11'::intToHex
0x18002d660  movsx   r9d, byte ptr [rdi]
0x18002d664  mov     ecx, r9d
0x18002d667  sub     ecx, 8
0x18002d66a  jz      loc_18002DA2D
0x18002d670  sub     ecx, 1
0x18002d673  jz      loc_18002D9D1
0x18002d679  sub     ecx, 1
0x18002d67c  jz      loc_18002D96F
0x18002d682  sub     ecx, 2
0x18002d685  jz      loc_18002D90D
0x18002d68b  sub     ecx, 1
0x18002d68e  jz      loc_18002D8AB
0x18002d694  sub     ecx, 15h
0x18002d697  jz      loc_18002D849
0x18002d69d  cmp     ecx, 3Ah ; ':'
0x18002d6a0  mov     rcx, [rbx+10h]
0x18002d6a4  jz      loc_18002D7EB
0x18002d6aa  cmp     r9b, 1Fh
0x18002d6ae  ja      loc_18002D7BF
0x18002d6b4  cmp     rcx, [rbx+18h]
0x18002d6b8  jnb     short loc_18002D6D6
0x18002d6ba  lea     rax, [rcx+1]
0x18002d6be  mov     [rbx+10h], rax
0x18002d6c2  mov     rax, rbx
0x18002d6c5  cmp     [rbx+18h], rbp
0x18002d6c9  jbe     short loc_18002D6CE
0x18002d6cb  mov     rax, [rbx]
0x18002d6ce  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18002d6d4  jmp     short loc_18002D6E1
0x18002d6d6  mov     r9b, 5Ch ; '\'
0x18002d6d9  mov     rcx, rbx; Src
0x18002d6dc  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d6e1  mov     rcx, [rbx+10h]
0x18002d6e5  cmp     rcx, [rbx+18h]
0x18002d6e9  jnb     short loc_18002D707
0x18002d6eb  lea     rax, [rcx+1]
0x18002d6ef  mov     [rbx+10h], rax
0x18002d6f3  mov     rax, rbx
0x18002d6f6  cmp     [rbx+18h], rbp
0x18002d6fa  jbe     short loc_18002D6FF
0x18002d6fc  mov     rax, [rbx]
0x18002d6ff  mov     word ptr [rax+rcx], 75h ; 'u'
0x18002d705  jmp     short loc_18002D712
0x18002d707  mov     r9b, 75h ; 'u'
0x18002d70a  mov     rcx, rbx; Src
0x18002d70d  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d712  mov     rcx, [rbx+10h]
0x18002d716  cmp     rcx, [rbx+18h]
0x18002d71a  jnb     short loc_18002D738
0x18002d71c  lea     rax, [rcx+1]
0x18002d720  mov     [rbx+10h], rax
0x18002d724  mov     rax, rbx
0x18002d727  cmp     [rbx+18h], rbp
0x18002d72b  jbe     short loc_18002D730
0x18002d72d  mov     rax, [rbx]
0x18002d730  mov     word ptr [rax+rcx], 30h ; '0'
0x18002d736  jmp     short loc_18002D743
0x18002d738  mov     r9b, 30h ; '0'
0x18002d73b  mov     rcx, rbx; Src
0x18002d73e  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d743  mov     rcx, [rbx+10h]
0x18002d747  cmp     rcx, [rbx+18h]
0x18002d74b  jnb     short loc_18002D769
0x18002d74d  lea     rax, [rcx+1]
0x18002d751  mov     [rbx+10h], rax
0x18002d755  mov     rax, rbx
0x18002d758  cmp     [rbx+18h], rbp
0x18002d75c  jbe     short loc_18002D761
0x18002d75e  mov     rax, [rbx]
0x18002d761  mov     word ptr [rax+rcx], 30h ; '0'
0x18002d767  jmp     short loc_18002D774
0x18002d769  mov     r9b, 30h ; '0'
0x18002d76c  mov     rcx, rbx; Src
0x18002d76f  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d774  movzx   eax, byte ptr [rdi]
0x18002d777  mov     rcx, [rbx+10h]
0x18002d77b  shr     rax, 4
0x18002d77f  mov     r9b, [rax+r15]
0x18002d783  cmp     rcx, [rbx+18h]
0x18002d787  jnb     short loc_18002D7A8
0x18002d789  lea     rax, [rcx+1]
0x18002d78d  mov     [rbx+10h], rax
0x18002d791  mov     rax, rbx
0x18002d794  cmp     [rbx+18h], rbp
0x18002d798  jbe     short loc_18002D79D
0x18002d79a  mov     rax, [rbx]
0x18002d79d  mov     [rax+rcx], r9b
0x18002d7a1  mov     [rax+rcx+1], r14b
0x18002d7a6  jmp     short loc_18002D7B0
0x18002d7a8  mov     rcx, rbx; Src
0x18002d7ab  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d7b0  movsx   rax, byte ptr [rdi]
0x18002d7b4  mov     rcx, [rbx+10h]
0x18002d7b8  and     rax, rbp
0x18002d7bb  mov     r9b, [rax+r15]
0x18002d7bf  cmp     rcx, [rbx+18h]
0x18002d7c3  jnb     loc_18002DA87
0x18002d7c9  lea     rax, [rcx+1]
0x18002d7cd  mov     [rbx+10h], rax
0x18002d7d1  mov     rax, rbx
0x18002d7d4  cmp     [rbx+18h], rbp
0x18002d7d8  jbe     short loc_18002D7DD
0x18002d7da  mov     rax, [rbx]
0x18002d7dd  mov     [rax+rcx], r9b
0x18002d7e1  mov     [rax+rcx+1], r14b
0x18002d7e6  jmp     loc_18002DA8F
0x18002d7eb  cmp     rcx, [rbx+18h]
0x18002d7ef  jnb     short loc_18002D80D
0x18002d7f1  lea     rax, [rcx+1]
0x18002d7f5  mov     [rbx+10h], rax
0x18002d7f9  mov     rax, rbx
0x18002d7fc  cmp     [rbx+18h], rbp
0x18002d800  jbe     short loc_18002D805
0x18002d802  mov     rax, [rbx]
0x18002d805  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18002d80b  jmp     short loc_18002D818
0x18002d80d  mov     r9b, 5Ch ; '\'
0x18002d810  mov     rcx, rbx; Src
0x18002d813  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d818  mov     rcx, [rbx+10h]
0x18002d81c  cmp     rcx, [rbx+18h]
0x18002d820  jnb     short loc_18002D841
0x18002d822  lea     rax, [rcx+1]
0x18002d826  mov     [rbx+10h], rax
0x18002d82a  mov     rax, rbx
0x18002d82d  cmp     [rbx+18h], rbp
0x18002d831  jbe     short loc_18002D836
0x18002d833  mov     rax, [rbx]
0x18002d836  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18002d83c  jmp     loc_18002DA8F
0x18002d841  mov     r9b, 5Ch ; '\'
0x18002d844  jmp     loc_18002DA87
0x18002d849  mov     rcx, [rbx+10h]
0x18002d84d  cmp     rcx, [rbx+18h]
0x18002d851  jnb     short loc_18002D86F
0x18002d853  lea     rax, [rcx+1]
0x18002d857  mov     [rbx+10h], rax
0x18002d85b  mov     rax, rbx
0x18002d85e  cmp     [rbx+18h], rbp
0x18002d862  jbe     short loc_18002D867
0x18002d864  mov     rax, [rbx]
0x18002d867  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18002d86d  jmp     short loc_18002D87A
0x18002d86f  mov     r9b, 5Ch ; '\'
0x18002d872  mov     rcx, rbx; Src
0x18002d875  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d87a  mov     rcx, [rbx+10h]
0x18002d87e  cmp     rcx, [rbx+18h]
0x18002d882  jnb     short loc_18002D8A3
0x18002d884  lea     rax, [rcx+1]
0x18002d888  mov     [rbx+10h], rax
0x18002d88c  mov     rax, rbx
0x18002d88f  cmp     [rbx+18h], rbp
0x18002d893  jbe     short loc_18002D898
0x18002d895  mov     rax, [rbx]
0x18002d898  mov     word ptr [rax+rcx], 22h ; '"'
0x18002d89e  jmp     loc_18002DA8F
0x18002d8a3  mov     r9b, 22h ; '"'
0x18002d8a6  jmp     loc_18002DA87
0x18002d8ab  mov     rcx, [rbx+10h]
0x18002d8af  cmp     rcx, [rbx+18h]
0x18002d8b3  jnb     short loc_18002D8D1
0x18002d8b5  lea     rax, [rcx+1]
0x18002d8b9  mov     [rbx+10h], rax
0x18002d8bd  mov     rax, rbx
0x18002d8c0  cmp     [rbx+18h], rbp
0x18002d8c4  jbe     short loc_18002D8C9
0x18002d8c6  mov     rax, [rbx]
0x18002d8c9  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18002d8cf  jmp     short loc_18002D8DC
0x18002d8d1  mov     r9b, 5Ch ; '\'
0x18002d8d4  mov     rcx, rbx; Src
0x18002d8d7  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d8dc  mov     rcx, [rbx+10h]
0x18002d8e0  cmp     rcx, [rbx+18h]
0x18002d8e4  jnb     short loc_18002D905
0x18002d8e6  lea     rax, [rcx+1]
0x18002d8ea  mov     [rbx+10h], rax
0x18002d8ee  mov     rax, rbx
0x18002d8f1  cmp     [rbx+18h], rbp
0x18002d8f5  jbe     short loc_18002D8FA
0x18002d8f7  mov     rax, [rbx]
0x18002d8fa  mov     word ptr [rax+rcx], 72h ; 'r'
0x18002d900  jmp     loc_18002DA8F
0x18002d905  mov     r9b, 72h ; 'r'
0x18002d908  jmp     loc_18002DA87
0x18002d90d  mov     rcx, [rbx+10h]
0x18002d911  cmp     rcx, [rbx+18h]
0x18002d915  jnb     short loc_18002D933
0x18002d917  lea     rax, [rcx+1]
0x18002d91b  mov     [rbx+10h], rax
0x18002d91f  mov     rax, rbx
0x18002d922  cmp     [rbx+18h], rbp
0x18002d926  jbe     short loc_18002D92B
0x18002d928  mov     rax, [rbx]
0x18002d92b  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18002d931  jmp     short loc_18002D93E
0x18002d933  mov     r9b, 5Ch ; '\'
0x18002d936  mov     rcx, rbx; Src
0x18002d939  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d93e  mov     rcx, [rbx+10h]
0x18002d942  cmp     rcx, [rbx+18h]
0x18002d946  jnb     short loc_18002D967
0x18002d948  lea     rax, [rcx+1]
0x18002d94c  mov     [rbx+10h], rax
0x18002d950  mov     rax, rbx
0x18002d953  cmp     [rbx+18h], rbp
0x18002d957  jbe     short loc_18002D95C
0x18002d959  mov     rax, [rbx]
0x18002d95c  mov     word ptr [rax+rcx], 66h ; 'f'
0x18002d962  jmp     loc_18002DA8F
0x18002d967  mov     r9b, 66h ; 'f'
0x18002d96a  jmp     loc_18002DA87
0x18002d96f  mov     rcx, [rbx+10h]
0x18002d973  cmp     rcx, [rbx+18h]
0x18002d977  jnb     short loc_18002D995
0x18002d979  lea     rax, [rcx+1]
0x18002d97d  mov     [rbx+10h], rax
0x18002d981  mov     rax, rbx
0x18002d984  cmp     [rbx+18h], rbp
0x18002d988  jbe     short loc_18002D98D
0x18002d98a  mov     rax, [rbx]
0x18002d98d  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18002d993  jmp     short loc_18002D9A0
0x18002d995  mov     r9b, 5Ch ; '\'
0x18002d998  mov     rcx, rbx; Src
0x18002d99b  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002d9a0  mov     rcx, [rbx+10h]
0x18002d9a4  cmp     rcx, [rbx+18h]
0x18002d9a8  jnb     short loc_18002D9C9
0x18002d9aa  lea     rax, [rcx+1]
0x18002d9ae  mov     [rbx+10h], rax
0x18002d9b2  mov     rax, rbx
0x18002d9b5  cmp     [rbx+18h], rbp
0x18002d9b9  jbe     short loc_18002D9BE
0x18002d9bb  mov     rax, [rbx]
0x18002d9be  mov     word ptr [rax+rcx], 6Eh ; 'n'
0x18002d9c4  jmp     loc_18002DA8F
0x18002d9c9  mov     r9b, 6Eh ; 'n'
0x18002d9cc  jmp     loc_18002DA87
0x18002d9d1  mov     rcx, [rbx+10h]
0x18002d9d5  cmp     rcx, [rbx+18h]
0x18002d9d9  jnb     short loc_18002D9F7
0x18002d9db  lea     rax, [rcx+1]
0x18002d9df  mov     [rbx+10h], rax
0x18002d9e3  mov     rax, rbx
0x18002d9e6  cmp     [rbx+18h], rbp
0x18002d9ea  jbe     short loc_18002D9EF
0x18002d9ec  mov     rax, [rbx]
0x18002d9ef  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18002d9f5  jmp     short loc_18002DA02
0x18002d9f7  mov     r9b, 5Ch ; '\'
0x18002d9fa  mov     rcx, rbx; Src
0x18002d9fd  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002da02  mov     rcx, [rbx+10h]
0x18002da06  cmp     rcx, [rbx+18h]
0x18002da0a  jnb     short loc_18002DA28
0x18002da0c  lea     rax, [rcx+1]
0x18002da10  mov     [rbx+10h], rax
0x18002da14  mov     rax, rbx
0x18002da17  cmp     [rbx+18h], rbp
0x18002da1b  jbe     short loc_18002DA20
0x18002da1d  mov     rax, [rbx]
0x18002da20  mov     word ptr [rax+rcx], 74h ; 't'
0x18002da26  jmp     short loc_18002DA8F
0x18002da28  mov     r9b, 74h ; 't'
0x18002da2b  jmp     short loc_18002DA87
0x18002da2d  mov     rcx, [rbx+10h]
0x18002da31  cmp     rcx, [rbx+18h]
0x18002da35  jnb     short loc_18002DA53
0x18002da37  lea     rax, [rcx+1]
0x18002da3b  mov     [rbx+10h], rax
0x18002da3f  mov     rax, rbx
0x18002da42  cmp     [rbx+18h], rbp
0x18002da46  jbe     short loc_18002DA4B
0x18002da48  mov     rax, [rbx]
  ... truncated ...
```
