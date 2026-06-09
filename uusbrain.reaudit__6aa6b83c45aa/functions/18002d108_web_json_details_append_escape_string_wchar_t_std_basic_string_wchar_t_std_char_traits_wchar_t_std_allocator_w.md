# web::json::details::append_escape_string<wchar_t>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18002d108`
- end: `0x18002d603`
- name: `??$append_escape_string@_W@details@json@web@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z`
- size: `1275`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002cc80`
- `0x18002cf80`

## callees

- `0x180028b6c`
- `0x18002d108`

## pseudocode

```c
_QWORD *__fastcall web::json::details::append_escape_string<wchar_t>(_QWORD *Src, _QWORD *a2)
{
  _QWORD *v3; // rcx
  _QWORD *v4; // r8
  _WORD *v5; // rdi
  _QWORD *result; // rax
  _WORD *v7; // rsi
  unsigned int v8; // r9d
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rax
  unsigned __int64 v13; // rcx
  _QWORD *v14; // rax
  unsigned __int64 v15; // rcx
  _QWORD *v16; // rax
  unsigned __int64 v17; // rcx
  wchar_t v18; // r9
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  _QWORD *v23; // rax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  _QWORD *v26; // rax
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  _QWORD *v29; // rax
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  _QWORD *v32; // rax
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rcx
  _QWORD *v35; // rax
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  _QWORD *v38; // rax
  unsigned __int64 v39; // rcx

  v3 = a2;
  if ( a2[3] <= 7u )
  {
    v5 = a2;
    v4 = a2;
  }
  else
  {
    v3 = (_QWORD *)*a2;
    v4 = (_QWORD *)*a2;
    v5 = (_WORD *)*a2;
  }
  result = (_QWORD *)a2[2];
  v7 = (_WORD *)v4 + (_QWORD)result;
  if ( v3 != (_QWORD *)v7 )
  {
    do
    {
      v8 = (unsigned __int16)*v5;
      if ( v8 == 8 )
      {
        v37 = Src[2];
        if ( v37 >= Src[3] )
        {
          std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
        }
        else
        {
          Src[2] = v37 + 1;
          v38 = Src;
          if ( Src[3] > 7u )
            v38 = (_QWORD *)*Src;
          *(_DWORD *)((char *)v38 + 2 * v37) = 92;
        }
        v39 = Src[2];
        if ( v39 < Src[3] )
        {
          Src[2] = v39 + 1;
          result = Src;
          if ( Src[3] > 7u )
            result = (_QWORD *)*Src;
          *(_DWORD *)((char *)result + 2 * v39) = 98;
          goto LABEL_113;
        }
      }
      else
      {
        switch ( *v5 )
        {
          case 9:
            v34 = Src[2];
            if ( v34 >= Src[3] )
            {
              std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
            }
            else
            {
              Src[2] = v34 + 1;
              v35 = Src;
              if ( Src[3] > 7u )
                v35 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v35 + 2 * v34) = 92;
            }
            v36 = Src[2];
            if ( v36 < Src[3] )
            {
              Src[2] = v36 + 1;
              result = Src;
              if ( Src[3] > 7u )
                result = (_QWORD *)*Src;
              *(_DWORD *)((char *)result + 2 * v36) = 116;
              goto LABEL_113;
            }
            break;
          case 0xA:
            v31 = Src[2];
            if ( v31 >= Src[3] )
            {
              std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
            }
            else
            {
              Src[2] = v31 + 1;
              v32 = Src;
              if ( Src[3] > 7u )
                v32 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v32 + 2 * v31) = 92;
            }
            v33 = Src[2];
            if ( v33 < Src[3] )
            {
              Src[2] = v33 + 1;
              result = Src;
              if ( Src[3] > 7u )
                result = (_QWORD *)*Src;
              *(_DWORD *)((char *)result + 2 * v33) = 110;
              goto LABEL_113;
            }
            break;
          case 0xC:
            v28 = Src[2];
            if ( v28 >= Src[3] )
            {
              std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
            }
            else
            {
              Src[2] = v28 + 1;
              v29 = Src;
              if ( Src[3] > 7u )
                v29 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v29 + 2 * v28) = 92;
            }
            v30 = Src[2];
            if ( v30 < Src[3] )
            {
              Src[2] = v30 + 1;
              result = Src;
              if ( Src[3] > 7u )
                result = (_QWORD *)*Src;
              *(_DWORD *)((char *)result + 2 * v30) = 102;
              goto LABEL_113;
            }
            break;
          case 0xD:
            v25 = Src[2];
            if ( v25 >= Src[3] )
            {
              std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
            }
            else
            {
              Src[2] = v25 + 1;
              v26 = Src;
              if ( Src[3] > 7u )
                v26 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v26 + 2 * v25) = 92;
            }
            v27 = Src[2];
            if ( v27 < Src[3] )
            {
              Src[2] = v27 + 1;
              result = Src;
              if ( Src[3] > 7u )
                result = (_QWORD *)*Src;
              *(_DWORD *)((char *)result + 2 * v27) = 114;
              goto LABEL_113;
            }
            break;
          case 0x22:
            v22 = Src[2];
            if ( v22 >= Src[3] )
            {
              std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
            }
            else
            {
              Src[2] = v22 + 1;
              v23 = Src;
              if ( Src[3] > 7u )
                v23 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v23 + 2 * v22) = 92;
            }
            v24 = Src[2];
            if ( v24 < Src[3] )
            {
              Src[2] = v24 + 1;
              result = Src;
              if ( Src[3] > 7u )
                result = (_QWORD *)*Src;
              *(_DWORD *)((char *)result + 2 * v24) = 34;
              goto LABEL_113;
            }
            break;
          default:
            v9 = Src[2];
            if ( *v5 == 92 )
            {
              if ( v9 >= Src[3] )
              {
                std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
              }
              else
              {
                Src[2] = v9 + 1;
                v20 = Src;
                if ( Src[3] > 7u )
                  v20 = (_QWORD *)*Src;
                *(_DWORD *)((char *)v20 + 2 * v9) = 92;
              }
              v21 = Src[2];
              if ( v21 < Src[3] )
              {
                Src[2] = v21 + 1;
                result = Src;
                if ( Src[3] > 7u )
                  result = (_QWORD *)*Src;
                *(_DWORD *)((char *)result + 2 * v21) = 92;
                goto LABEL_113;
              }
            }
            else
            {
              if ( v8 <= 0x1F )
              {
                if ( v9 >= Src[3] )
                {
                  std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
                }
                else
                {
                  Src[2] = v9 + 1;
                  v10 = Src;
                  if ( Src[3] > 7u )
                    v10 = (_QWORD *)*Src;
                  *(_DWORD *)((char *)v10 + 2 * v9) = 92;
                }
                v11 = Src[2];
                if ( v11 >= Src[3] )
                {
                  std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
                }
                else
                {
                  Src[2] = v11 + 1;
                  v12 = Src;
                  if ( Src[3] > 7u )
                    v12 = (_QWORD *)*Src;
                  *(_DWORD *)((char *)v12 + 2 * v11) = 117;
                }
                v13 = Src[2];
                if ( v13 >= Src[3] )
                {
                  std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
                }
                else
                {
                  Src[2] = v13 + 1;
                  v14 = Src;
                  if ( Src[3] > 7u )
                    v14 = (_QWORD *)*Src;
                  *(_DWORD *)((char *)v14 + 2 * v13) = 48;
                }
                v15 = Src[2];
                if ( v15 >= Src[3] )
                {
                  std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
                }
                else
                {
                  Src[2] = v15 + 1;
                  v16 = Src;
                  if ( Src[3] > 7u )
                    v16 = (_QWORD *)*Src;
                  *(_DWORD *)((char *)v16 + 2 * v15) = 48;
                }
                v17 = Src[2];
                v18 = `web::json::details::append_escape_string<wchar_t>'::`11'::intToHex[((unsigned __int64)(unsigned __int16)*v5 >> 4)
                                                                                        & 0xF];
                if ( v17 >= Src[3] )
                {
                  std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
                }
                else
                {
                  Src[2] = v17 + 1;
                  v19 = Src;
                  if ( Src[3] > 7u )
                    v19 = (_QWORD *)*Src;
                  *((_WORD *)v19 + v17) = v18;
                  *((_WORD *)v19 + v17 + 1) = 0;
                }
                LOWORD(v8) = `web::json::details::append_escape_string<wchar_t>'::`11'::intToHex[*v5 & 0xF];
                v9 = Src[2];
              }
              if ( v9 < Src[3] )
              {
                Src[2] = v9 + 1;
                result = Src;
                if ( Src[3] > 7u )
                  result = (_QWORD *)*Src;
                *((_WORD *)result + v9) = v8;
                *((_WORD *)result + v9 + 1) = 0;
                goto LABEL_113;
              }
            }
            break;
        }
      }
      result = (_QWORD *)std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
LABEL_113:
      ++v5;
    }
    while ( v5 != v7 );
  }
  return result;
}

```

## disassembly

```asm
0x18002d108  mov     [rsp+arg_8], rbx
0x18002d10d  mov     [rsp+arg_10], rbp
0x18002d112  mov     [rsp+arg_18], rsi
0x18002d117  push    rdi
0x18002d118  push    r12
0x18002d11a  push    r13
0x18002d11c  push    r14
0x18002d11e  push    r15
0x18002d120  sub     rsp, 20h
0x18002d124  mov     ebp, 7
0x18002d129  mov     rbx, rcx
0x18002d12c  mov     rcx, rdx
0x18002d12f  cmp     [rdx+18h], rbp
0x18002d133  jbe     short loc_18002D140
0x18002d135  mov     rcx, [rdx]
0x18002d138  mov     r8, rcx
0x18002d13b  mov     rdi, rcx
0x18002d13e  jmp     short loc_18002D146
0x18002d140  mov     rdi, rdx
0x18002d143  mov     r8, rdx
0x18002d146  mov     rax, [rdx+10h]
0x18002d14a  lea     rsi, [r8+rax*2]
0x18002d14e  cmp     rcx, rsi
0x18002d151  jz      loc_18002D5E6
0x18002d157  mov     r15d, 5Ch ; '\'
0x18002d15d  xor     r14d, r14d
0x18002d160  lea     edx, [r15-3Ah]
0x18002d164  lea     r13d, [r15+19h]
0x18002d168  lea     r12d, [r15-2Ch]
0x18002d16c  lea     r8d, [r15+16h]
0x18002d170  lea     r10d, [r15+0Ah]
0x18002d174  lea     r11d, [r15+12h]
0x18002d178  movzx   r9d, word ptr [rdi]
0x18002d17c  mov     ecx, r9d
0x18002d17f  sub     ecx, 8
0x18002d182  jz      loc_18002D564
0x18002d188  sub     ecx, 1
0x18002d18b  jz      loc_18002D506
0x18002d191  sub     ecx, 1
0x18002d194  jz      loc_18002D49F
0x18002d19a  sub     ecx, 2
0x18002d19d  jz      loc_18002D438
0x18002d1a3  sub     ecx, 1
0x18002d1a6  jz      loc_18002D3D1
0x18002d1ac  sub     ecx, 15h
0x18002d1af  jz      loc_18002D36B
0x18002d1b5  cmp     ecx, 3Ah ; ':'
0x18002d1b8  mov     rcx, [rbx+10h]
0x18002d1bc  jz      loc_18002D311
0x18002d1c2  cmp     r9d, 1Fh
0x18002d1c6  ja      loc_18002D2E3
0x18002d1cc  cmp     rcx, [rbx+18h]
0x18002d1d0  jnb     short loc_18002D1EC
0x18002d1d2  lea     rax, [rcx+1]
0x18002d1d6  mov     [rbx+10h], rax
0x18002d1da  mov     rax, rbx
0x18002d1dd  cmp     [rbx+18h], rbp
0x18002d1e1  jbe     short loc_18002D1E6
0x18002d1e3  mov     rax, [rbx]
0x18002d1e6  mov     [rax+rcx*2], r15d
0x18002d1ea  jmp     short loc_18002D1F7
0x18002d1ec  mov     r9d, r15d
0x18002d1ef  mov     rcx, rbx; Src
0x18002d1f2  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d1f7  mov     rcx, [rbx+10h]
0x18002d1fb  cmp     rcx, [rbx+18h]
0x18002d1ff  jnb     short loc_18002D21B
0x18002d201  lea     rax, [rcx+1]
0x18002d205  mov     [rbx+10h], rax
0x18002d209  mov     rax, rbx
0x18002d20c  cmp     [rbx+18h], rbp
0x18002d210  jbe     short loc_18002D215
0x18002d212  mov     rax, [rbx]
0x18002d215  mov     [rax+rcx*2], r13d
0x18002d219  jmp     short loc_18002D226
0x18002d21b  mov     r9d, r13d
0x18002d21e  mov     rcx, rbx; Src
0x18002d221  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d226  mov     rcx, [rbx+10h]
0x18002d22a  cmp     rcx, [rbx+18h]
0x18002d22e  jnb     short loc_18002D24A
0x18002d230  lea     rax, [rcx+1]
0x18002d234  mov     [rbx+10h], rax
0x18002d238  mov     rax, rbx
0x18002d23b  cmp     [rbx+18h], rbp
0x18002d23f  jbe     short loc_18002D244
0x18002d241  mov     rax, [rbx]
0x18002d244  mov     [rax+rcx*2], r12d
0x18002d248  jmp     short loc_18002D255
0x18002d24a  mov     r9d, r12d
0x18002d24d  mov     rcx, rbx; Src
0x18002d250  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d255  mov     rcx, [rbx+10h]
0x18002d259  cmp     rcx, [rbx+18h]
0x18002d25d  jnb     short loc_18002D279
0x18002d25f  lea     rax, [rcx+1]
0x18002d263  mov     [rbx+10h], rax
0x18002d267  mov     rax, rbx
0x18002d26a  cmp     [rbx+18h], rbp
0x18002d26e  jbe     short loc_18002D273
0x18002d270  mov     rax, [rbx]
0x18002d273  mov     [rax+rcx*2], r12d
0x18002d277  jmp     short loc_18002D284
0x18002d279  mov     r9d, r12d
0x18002d27c  mov     rcx, rbx; Src
0x18002d27f  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d284  movzx   eax, word ptr [rdi]
0x18002d287  lea     r9, ?intToHex@?L@???$append_escape_string@_W@details@json@web@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@@Z@4V?$array@_W$0BA@@5@B; "0123456789ABCDEF"
0x18002d28e  mov     rcx, [rbx+10h]
0x18002d292  shr     rax, 4
0x18002d296  and     eax, 0Fh
0x18002d299  movzx   r9d, word ptr [r9+rax*2]
0x18002d29e  cmp     rcx, [rbx+18h]
0x18002d2a2  jnb     short loc_18002D2C5
0x18002d2a4  lea     rax, [rcx+1]
0x18002d2a8  mov     [rbx+10h], rax
0x18002d2ac  mov     rax, rbx
0x18002d2af  cmp     [rbx+18h], rbp
0x18002d2b3  jbe     short loc_18002D2B8
0x18002d2b5  mov     rax, [rbx]
0x18002d2b8  mov     [rax+rcx*2], r9w
0x18002d2bd  mov     [rax+rcx*2+2], r14w
0x18002d2c3  jmp     short loc_18002D2CD
0x18002d2c5  mov     rcx, rbx; Src
0x18002d2c8  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d2cd  movzx   eax, word ptr [rdi]
0x18002d2d0  lea     rcx, ?intToHex@?L@???$append_escape_string@_W@details@json@web@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@@Z@4V?$array@_W$0BA@@5@B; "0123456789ABCDEF"
0x18002d2d7  and     eax, 0Fh
0x18002d2da  movzx   r9d, word ptr [rcx+rax*2]
0x18002d2df  mov     rcx, [rbx+10h]
0x18002d2e3  cmp     rcx, [rbx+18h]
0x18002d2e7  jnb     loc_18002D5C0
0x18002d2ed  lea     rax, [rcx+1]
0x18002d2f1  mov     [rbx+10h], rax
0x18002d2f5  mov     rax, rbx
0x18002d2f8  cmp     [rbx+18h], rbp
0x18002d2fc  jbe     short loc_18002D301
0x18002d2fe  mov     rax, [rbx]
0x18002d301  mov     [rax+rcx*2], r9w
0x18002d306  mov     [rax+rcx*2+2], r14w
0x18002d30c  jmp     loc_18002D5C8
0x18002d311  cmp     rcx, [rbx+18h]
0x18002d315  jnb     short loc_18002D331
0x18002d317  lea     rax, [rcx+1]
0x18002d31b  mov     [rbx+10h], rax
0x18002d31f  mov     rax, rbx
0x18002d322  cmp     [rbx+18h], rbp
0x18002d326  jbe     short loc_18002D32B
0x18002d328  mov     rax, [rbx]
0x18002d32b  mov     [rax+rcx*2], r15d
0x18002d32f  jmp     short loc_18002D33C
0x18002d331  mov     r9d, r15d
0x18002d334  mov     rcx, rbx; Src
0x18002d337  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d33c  mov     rcx, [rbx+10h]
0x18002d340  cmp     rcx, [rbx+18h]
0x18002d344  jnb     short loc_18002D363
0x18002d346  lea     rax, [rcx+1]
0x18002d34a  mov     [rbx+10h], rax
0x18002d34e  mov     rax, rbx
0x18002d351  cmp     [rbx+18h], rbp
0x18002d355  jbe     short loc_18002D35A
0x18002d357  mov     rax, [rbx]
0x18002d35a  mov     [rax+rcx*2], r15d
0x18002d35e  jmp     loc_18002D5C8
0x18002d363  mov     r9d, r15d
0x18002d366  jmp     loc_18002D5C0
0x18002d36b  mov     rcx, [rbx+10h]
0x18002d36f  cmp     rcx, [rbx+18h]
0x18002d373  jnb     short loc_18002D38F
0x18002d375  lea     rax, [rcx+1]
0x18002d379  mov     [rbx+10h], rax
0x18002d37d  mov     rax, rbx
0x18002d380  cmp     [rbx+18h], rbp
0x18002d384  jbe     short loc_18002D389
0x18002d386  mov     rax, [rbx]
0x18002d389  mov     [rax+rcx*2], r15d
0x18002d38d  jmp     short loc_18002D39F
0x18002d38f  mov     r9d, r15d
0x18002d392  mov     rcx, rbx; Src
0x18002d395  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d39a  mov     edx, 22h ; '"'
0x18002d39f  mov     rcx, [rbx+10h]
0x18002d3a3  cmp     rcx, [rbx+18h]
0x18002d3a7  jnb     short loc_18002D3C9
0x18002d3a9  lea     rax, [rcx+1]
0x18002d3ad  mov     [rbx+10h], rax
0x18002d3b1  mov     rax, rbx
0x18002d3b4  cmp     [rbx+18h], rbp
0x18002d3b8  jbe     short loc_18002D3BD
0x18002d3ba  mov     rax, [rbx]
0x18002d3bd  mov     dword ptr [rax+rcx*2], 22h ; '"'
0x18002d3c4  jmp     loc_18002D5C8
0x18002d3c9  mov     r9d, edx
0x18002d3cc  jmp     loc_18002D5C0
0x18002d3d1  mov     rcx, [rbx+10h]
0x18002d3d5  cmp     rcx, [rbx+18h]
0x18002d3d9  jnb     short loc_18002D3F5
0x18002d3db  lea     rax, [rcx+1]
0x18002d3df  mov     [rbx+10h], rax
0x18002d3e3  mov     rax, rbx
0x18002d3e6  cmp     [rbx+18h], rbp
0x18002d3ea  jbe     short loc_18002D3EF
0x18002d3ec  mov     rax, [rbx]
0x18002d3ef  mov     [rax+rcx*2], r15d
0x18002d3f3  jmp     short loc_18002D406
0x18002d3f5  mov     r9d, r15d
0x18002d3f8  mov     rcx, rbx; Src
0x18002d3fb  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d400  mov     r8d, 72h ; 'r'
0x18002d406  mov     rcx, [rbx+10h]
0x18002d40a  cmp     rcx, [rbx+18h]
0x18002d40e  jnb     short loc_18002D430
0x18002d410  lea     rax, [rcx+1]
0x18002d414  mov     [rbx+10h], rax
0x18002d418  mov     rax, rbx
0x18002d41b  cmp     [rbx+18h], rbp
0x18002d41f  jbe     short loc_18002D424
0x18002d421  mov     rax, [rbx]
0x18002d424  mov     dword ptr [rax+rcx*2], 72h ; 'r'
0x18002d42b  jmp     loc_18002D5C8
0x18002d430  mov     r9d, r8d
0x18002d433  jmp     loc_18002D5C0
0x18002d438  mov     rcx, [rbx+10h]
0x18002d43c  cmp     rcx, [rbx+18h]
0x18002d440  jnb     short loc_18002D45C
0x18002d442  lea     rax, [rcx+1]
0x18002d446  mov     [rbx+10h], rax
0x18002d44a  mov     rax, rbx
0x18002d44d  cmp     [rbx+18h], rbp
0x18002d451  jbe     short loc_18002D456
0x18002d453  mov     rax, [rbx]
0x18002d456  mov     [rax+rcx*2], r15d
0x18002d45a  jmp     short loc_18002D46D
0x18002d45c  mov     r9d, r15d
0x18002d45f  mov     rcx, rbx; Src
0x18002d462  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d467  mov     r10d, 66h ; 'f'
0x18002d46d  mov     rcx, [rbx+10h]
0x18002d471  cmp     rcx, [rbx+18h]
0x18002d475  jnb     short loc_18002D497
0x18002d477  lea     rax, [rcx+1]
0x18002d47b  mov     [rbx+10h], rax
0x18002d47f  mov     rax, rbx
0x18002d482  cmp     [rbx+18h], rbp
0x18002d486  jbe     short loc_18002D48B
0x18002d488  mov     rax, [rbx]
0x18002d48b  mov     dword ptr [rax+rcx*2], 66h ; 'f'
0x18002d492  jmp     loc_18002D5C8
0x18002d497  mov     r9d, r10d
0x18002d49a  jmp     loc_18002D5C0
0x18002d49f  mov     rcx, [rbx+10h]
0x18002d4a3  cmp     rcx, [rbx+18h]
0x18002d4a7  jnb     short loc_18002D4C3
0x18002d4a9  lea     rax, [rcx+1]
0x18002d4ad  mov     [rbx+10h], rax
0x18002d4b1  mov     rax, rbx
0x18002d4b4  cmp     [rbx+18h], rbp
0x18002d4b8  jbe     short loc_18002D4BD
0x18002d4ba  mov     rax, [rbx]
0x18002d4bd  mov     [rax+rcx*2], r15d
0x18002d4c1  jmp     short loc_18002D4D4
0x18002d4c3  mov     r9d, r15d
0x18002d4c6  mov     rcx, rbx; Src
0x18002d4c9  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d4ce  mov     r11d, 6Eh ; 'n'
0x18002d4d4  mov     rcx, [rbx+10h]
0x18002d4d8  cmp     rcx, [rbx+18h]
0x18002d4dc  jnb     short loc_18002D4FE
0x18002d4de  lea     rax, [rcx+1]
0x18002d4e2  mov     [rbx+10h], rax
0x18002d4e6  mov     rax, rbx
0x18002d4e9  cmp     [rbx+18h], rbp
0x18002d4ed  jbe     short loc_18002D4F2
0x18002d4ef  mov     rax, [rbx]
0x18002d4f2  mov     dword ptr [rax+rcx*2], 6Eh ; 'n'
0x18002d4f9  jmp     loc_18002D5C8
0x18002d4fe  mov     r9d, r11d
0x18002d501  jmp     loc_18002D5C0
0x18002d506  mov     rcx, [rbx+10h]
0x18002d50a  cmp     rcx, [rbx+18h]
0x18002d50e  jnb     short loc_18002D52A
0x18002d510  lea     rax, [rcx+1]
0x18002d514  mov     [rbx+10h], rax
0x18002d518  mov     rax, rbx
0x18002d51b  cmp     [rbx+18h], rbp
0x18002d51f  jbe     short loc_18002D524
0x18002d521  mov     rax, [rbx]
0x18002d524  mov     [rax+rcx*2], r15d
0x18002d528  jmp     short loc_18002D535
0x18002d52a  mov     r9d, r15d
0x18002d52d  mov     rcx, rbx; Src
0x18002d530  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002d535  mov     rcx, [rbx+10h]
0x18002d539  cmp     rcx, [rbx+18h]
0x18002d53d  jnb     short loc_18002D55C
0x18002d53f  lea     rax, [rcx+1]
0x18002d543  mov     [rbx+10h], rax
0x18002d547  mov     rax, rbx
0x18002d54a  cmp     [rbx+18h], rbp
  ... truncated ...
```
