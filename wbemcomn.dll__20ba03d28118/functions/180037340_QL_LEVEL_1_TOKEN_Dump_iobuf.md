# QL_LEVEL_1_TOKEN::Dump(_iobuf *)

- ea: `0x180037340`
- end: `0x1800375f4`
- name: `?Dump@QL_LEVEL_1_TOKEN@@QEAAXPEAU_iobuf@@@Z`
- size: `692`
- prototype: `void __fastcall(QL_LEVEL_1_TOKEN *this, struct _iobuf *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180037220`

## callees

- `0x180003050`
- `0x18000ab30`
- `0x180037340`

## import_xrefs

- `msvcrt!fprintf` at `0x180037398`
- `msvcrt!fprintf` at `0x180037438`
- `msvcrt!fprintf` at `0x180037453`
- `msvcrt!fprintf` at `0x180037463`
- `msvcrt!fprintf` at `0x180037491`
- `msvcrt!fprintf` at `0x1800374e6`
- `msvcrt!fprintf` at `0x18003754a`
- `msvcrt!fprintf` at `0x180037560`
- `msvcrt!fprintf` at `0x180037587`
- `msvcrt!fprintf` at `0x1800375ad`
- `msvcrt!fprintf` at `0x1800375d3`
- `msvcrt!fprintf` at `0x1800375e3`
- `msvcrt!fprintf` at `0x180037398`
- `msvcrt!fprintf` at `0x180037438`
- `msvcrt!fprintf` at `0x180037453`
- `msvcrt!fprintf` at `0x180037463`
- `msvcrt!fprintf` at `0x180037491`
- `msvcrt!fprintf` at `0x1800374e6`
- `msvcrt!fprintf` at `0x18003754a`
- `msvcrt!fprintf` at `0x180037560`
- `msvcrt!fprintf` at `0x180037587`
- `msvcrt!fprintf` at `0x1800375ad`
- `msvcrt!fprintf` at `0x1800375d3`
- `msvcrt!fprintf` at `0x1800375e3`

## string_xrefs

- `0x180037385`: `TOKEN_AND `
- `0x18003738e`: `TOKEN_OR `
- `0x18003737c`: `TOKEN_NOT `
- `0x18003736a`: `Error: no token type specified\n`
- `0x1800375d9`: ` <end of token>\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall QL_LEVEL_1_TOKEN::Dump(QL_LEVEL_1_TOKEN *this, struct _iobuf *a2)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  const char *v7; // rdx
  const char *v8; // rsi
  const wchar_t *Text; // rax
  wchar_t *v10; // rbp
  const wchar_t *v11; // rax
  wchar_t *v12; // rdi
  const wchar_t *v13; // r8
  __int64 v14; // r8
  const char *v15; // rdx

  v4 = *(_DWORD *)this - 1;
  if ( !v4 )
  {
    v7 = "TOKEN_OR ";
    goto LABEL_10;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v7 = "TOKEN_AND ";
    goto LABEL_10;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v7 = "TOKEN_NOT ";
LABEL_10:
    fprintf(a2, v7);
    goto LABEL_11;
  }
  if ( v6 == 1 )
    fprintf(a2, "OP_EXPRESSION ");
  else
    fprintf(a2, "Error: no token type specified\n");
LABEL_11:
  if ( *(_DWORD *)this != 4 )
  {
LABEL_62:
    fprintf(a2, " <end of token>\n");
    return;
  }
  switch ( *((_DWORD *)this + 10) )
  {
    case 1:
      v8 = "OP_EQUAL";
      break;
    case 2:
      v8 = "OP_NOT_EQUAL";
      break;
    case 3:
      v8 = "OP_GREATERTHAN";
      break;
    case 4:
      v8 = "OP_LESSTHAN";
      break;
    case 5:
      v8 = "OP_EQUALorLESSTHAN";
      break;
    case 6:
      v8 = "OP_EQUALorGREATERTHAN";
      break;
    case 7:
      v8 = "OP_LIKE";
      break;
    default:
      v8 = "<no op>";
      break;
  }
  Text = CPropertyName::GetText((QL_LEVEL_1_TOKEN *)((char *)this + 8));
  v10 = (wchar_t *)Text;
  if ( Text )
  {
    fprintf(a2, "    Property = %S\n", Text);
    CMUILocale::_Free(v10);
    fprintf(a2, "    Operator = %s\n", v8);
    fprintf(a2, "    Value =    ");
    if ( *((_DWORD *)this + 28) )
    {
      v11 = CPropertyName::GetText((QL_LEVEL_1_TOKEN *)((char *)this + 80));
      v12 = (wchar_t *)v11;
      if ( !v11 )
        return;
      fprintf(a2, "   <Property:%S>\n", v11);
      CMUILocale::_Free(v12);
      goto LABEL_62;
    }
    if ( *((_WORD *)this + 24) != 1 )
    {
      if ( *((_WORD *)this + 24) == 2 )
      {
        v14 = (unsigned int)*((__int16 *)this + 28);
        v15 = "VT_I2 = %d\n";
      }
      else
      {
        if ( *((_WORD *)this + 24) != 3 )
        {
          if ( *((_WORD *)this + 24) == 4 )
          {
            fprintf(a2, "VT_R4 = %f\n", *((float *)this + 14));
            goto LABEL_54;
          }
          if ( *((_WORD *)this + 24) == 5 )
          {
            fprintf(a2, "VT_R8 = %f\n", *((_QWORD *)this + 7));
          }
          else
          {
            if ( *((_WORD *)this + 24) != 8 )
            {
              if ( *((_WORD *)this + 24) != 11 )
              {
                if ( *((_WORD *)this + 24) == 17 )
                  fprintf(a2, "VT_UI1 = %d\n", *((unsigned __int8 *)this + 56));
                else
                  fprintf(a2, "<unknown>\n");
                goto LABEL_54;
              }
              v13 = L"TRUE";
              if ( !*((_WORD *)this + 28) )
                v13 = L"FALSE";
              goto LABEL_53;
            }
            fprintf(a2, "VT_BSTR = %S\n", *((_QWORD *)this + 7));
          }
LABEL_54:
          if ( *((_DWORD *)this + 29) == 1 )
          {
            fprintf(a2, "Intrinsic function UPPER() applied to property\n");
          }
          else if ( *((_DWORD *)this + 29) == 2 )
          {
            fprintf(a2, "Intrinsic function LOWER() applied to property\n");
          }
          if ( *((_DWORD *)this + 30) == 1 )
          {
            fprintf(a2, "Intrinsic function UPPER() applied to const value\n");
          }
          else if ( *((_DWORD *)this + 30) == 2 )
          {
            fprintf(a2, "Intrinsic function LOWER() applied to const value\n");
          }
          goto LABEL_62;
        }
        v14 = *((unsigned int *)this + 14);
        v15 = "VT_I4 = %d\n";
      }
      fprintf(a2, v15, v14);
      goto LABEL_54;
    }
    v13 = L"NULL";
LABEL_53:
    fprintf(a2, "%S\n", v13);
    goto LABEL_54;
  }
}

```

## disassembly

```asm
0x180037340  push    rbx
0x180037342  push    rbp
0x180037343  push    rsi
0x180037344  push    rdi
0x180037345  push    r14
0x180037347  sub     rsp, 20h
0x18003734b  mov     rdi, rcx
0x18003734e  mov     rbx, rdx
0x180037351  mov     ecx, [rcx]
0x180037353  sub     ecx, 1
0x180037356  jz      short loc_18003738E
0x180037358  sub     ecx, 1
0x18003735b  jz      short loc_180037385
0x18003735d  sub     ecx, 1
0x180037360  jz      short loc_18003737C
0x180037362  cmp     ecx, 1
0x180037365  mov     rcx, rdx
0x180037368  jz      short loc_180037373
0x18003736a  lea     rdx, aErrorNoTokenTy; "Error: no token type specified\n"
0x180037371  jmp     short loc_180037398
0x180037373  lea     rdx, aOpExpression; "OP_EXPRESSION "
0x18003737a  jmp     short loc_180037398
0x18003737c  lea     rdx, aTokenNot; "TOKEN_NOT "
0x180037383  jmp     short loc_180037395
0x180037385  lea     rdx, aTokenAnd; "TOKEN_AND "
0x18003738c  jmp     short loc_180037395
0x18003738e  lea     rdx, aTokenOr; "TOKEN_OR "
0x180037395  mov     rcx, rbx; Stream
0x180037398  call    cs:__imp_fprintf
0x18003739e  cmp     dword ptr [rdi], 4
0x1800373a1  jnz     loc_1800375D9
0x1800373a7  mov     ecx, [rdi+28h]
0x1800373aa  sub     ecx, 1
0x1800373ad  jz      short loc_18003740C
0x1800373af  sub     ecx, 1
0x1800373b2  jz      short loc_180037403
0x1800373b4  sub     ecx, 1
0x1800373b7  jz      short loc_1800373FA
0x1800373b9  sub     ecx, 1
0x1800373bc  jz      short loc_1800373F1
0x1800373be  sub     ecx, 1
0x1800373c1  jz      short loc_1800373E8
0x1800373c3  sub     ecx, 1
0x1800373c6  jz      short loc_1800373DF
0x1800373c8  cmp     ecx, 1
0x1800373cb  jz      short loc_1800373D6
0x1800373cd  lea     rsi, aNoOp; "<no op>"
0x1800373d4  jmp     short loc_180037413
0x1800373d6  lea     rsi, aOpLike; "OP_LIKE"
0x1800373dd  jmp     short loc_180037413
0x1800373df  lea     rsi, aOpEqualorgreat; "OP_EQUALorGREATERTHAN"
0x1800373e6  jmp     short loc_180037413
0x1800373e8  lea     rsi, aOpEqualorlesst; "OP_EQUALorLESSTHAN"
0x1800373ef  jmp     short loc_180037413
0x1800373f1  lea     rsi, aOpLessthan; "OP_LESSTHAN"
0x1800373f8  jmp     short loc_180037413
0x1800373fa  lea     rsi, aOpGreaterthan; "OP_GREATERTHAN"
0x180037401  jmp     short loc_180037413
0x180037403  lea     rsi, aOpNotEqual; "OP_NOT_EQUAL"
0x18003740a  jmp     short loc_180037413
0x18003740c  lea     rsi, aOpEqual; "OP_EQUAL"
0x180037413  lea     rcx, [rdi+8]; this
0x180037417  call    ?GetText@CPropertyName@@QEAAPEAGXZ; CPropertyName::GetText(void)
0x18003741c  xor     r14d, r14d
0x18003741f  mov     rbp, rax
0x180037422  test    rax, rax
0x180037425  jz      loc_1800375E9
0x18003742b  mov     r8, rax
0x18003742e  lea     rdx, aPropertyS; "    Property = %S\n"
0x180037435  mov     rcx, rbx; Stream
0x180037438  call    cs:__imp_fprintf
0x18003743e  mov     rcx, rbp; void *
0x180037441  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180037446  mov     r8, rsi
0x180037449  lea     rdx, aOperatorS; "    Operator = %s\n"
0x180037450  mov     rcx, rbx; Stream
0x180037453  call    cs:__imp_fprintf
0x180037459  lea     rdx, aValue; "    Value =    "
0x180037460  mov     rcx, rbx; Stream
0x180037463  call    cs:__imp_fprintf
0x180037469  cmp     [rdi+70h], r14d
0x18003746d  jz      short loc_1800374A4
0x18003746f  lea     rcx, [rdi+50h]; this
0x180037473  call    ?GetText@CPropertyName@@QEAAPEAGXZ; CPropertyName::GetText(void)
0x180037478  mov     rdi, rax
0x18003747b  test    rax, rax
0x18003747e  jz      loc_1800375E9
0x180037484  mov     r8, rax
0x180037487  lea     rdx, aPropertyS_0; "   <Property:%S>\n"
0x18003748e  mov     rcx, rbx; Stream
0x180037491  call    cs:__imp_fprintf
0x180037497  mov     rcx, rdi; void *
0x18003749a  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003749f  jmp     loc_1800375D9
0x1800374a4  movzx   ecx, word ptr [rdi+30h]
0x1800374a8  sub     ecx, 1
0x1800374ab  jz      loc_180037576
0x1800374b1  sub     ecx, 1
0x1800374b4  jz      loc_180037568
0x1800374ba  sub     ecx, 1
0x1800374bd  jz      loc_180037552
0x1800374c3  sub     ecx, 1
0x1800374c6  jz      short loc_180037533
0x1800374c8  sub     ecx, 1
0x1800374cb  jz      short loc_180037525
0x1800374cd  sub     ecx, 3
0x1800374d0  jz      short loc_180037518
0x1800374d2  sub     ecx, 3
0x1800374d5  jz      short loc_1800374FF
0x1800374d7  cmp     ecx, 6
0x1800374da  mov     rcx, rbx; Stream
0x1800374dd  jz      short loc_1800374F1
0x1800374df  lea     rdx, aUnknown_0; "<unknown>\n"
0x1800374e6  call    cs:__imp_fprintf
0x1800374ec  jmp     loc_18003758D
0x1800374f1  movzx   r8d, byte ptr [rdi+38h]
0x1800374f6  lea     rdx, aVtUi1D; "VT_UI1 = %d\n"
0x1800374fd  jmp     short loc_180037560
0x1800374ff  cmp     [rdi+38h], r14w
0x180037504  lea     rax, aFalse; "FALSE"
0x18003750b  lea     r8, aTrue; "TRUE"
0x180037512  cmovz   r8, rax
0x180037516  jmp     short loc_18003757D
0x180037518  mov     r8, [rdi+38h]
0x18003751c  lea     rdx, aVtBstrS; "VT_BSTR = %S\n"
0x180037523  jmp     short loc_180037584
0x180037525  movsd   xmm2, qword ptr [rdi+38h]
0x18003752a  lea     rdx, aVtR8F; "VT_R8 = %f\n"
0x180037531  jmp     short loc_180037542
0x180037533  movss   xmm2, dword ptr [rdi+38h]
0x180037538  lea     rdx, aVtR4F; "VT_R4 = %f\n"
0x18003753f  cvtps2pd xmm2, xmm2
0x180037542  movq    r8, xmm2
0x180037547  mov     rcx, rbx; Stream
0x18003754a  call    cs:__imp_fprintf
0x180037550  jmp     short loc_18003758D
0x180037552  mov     r8d, [rdi+38h]
0x180037556  lea     rdx, aVtI4D; "VT_I4 = %d\n"
0x18003755d  mov     rcx, rbx; Stream
0x180037560  call    cs:__imp_fprintf
0x180037566  jmp     short loc_18003758D
0x180037568  movsx   r8d, word ptr [rdi+38h]
0x18003756d  lea     rdx, aVtI2D; "VT_I2 = %d\n"
0x180037574  jmp     short loc_18003755D
0x180037576  lea     r8, aNull_1; "NULL"
0x18003757d  lea     rdx, aS_2; "%S\n"
0x180037584  mov     rcx, rbx; Stream
0x180037587  call    cs:__imp_fprintf
0x18003758d  mov     ecx, [rdi+74h]
0x180037590  sub     ecx, 1
0x180037593  jz      short loc_1800375A3
0x180037595  cmp     ecx, 1
0x180037598  jnz     short loc_1800375B3
0x18003759a  lea     rdx, aIntrinsicFunct; "Intrinsic function LOWER() applied to p"...
0x1800375a1  jmp     short loc_1800375AA
0x1800375a3  lea     rdx, aIntrinsicFunct_1; "Intrinsic function UPPER() applied to p"...
0x1800375aa  mov     rcx, rbx; Stream
0x1800375ad  call    cs:__imp_fprintf
0x1800375b3  mov     ecx, [rdi+78h]
0x1800375b6  sub     ecx, 1
0x1800375b9  jz      short loc_1800375C9
0x1800375bb  cmp     ecx, 1
0x1800375be  jnz     short loc_1800375D9
0x1800375c0  lea     rdx, aIntrinsicFunct_0; "Intrinsic function LOWER() applied to c"...
0x1800375c7  jmp     short loc_1800375D0
0x1800375c9  lea     rdx, aIntrinsicFunct_2; "Intrinsic function UPPER() applied to c"...
0x1800375d0  mov     rcx, rbx; Stream
0x1800375d3  call    cs:__imp_fprintf
0x1800375d9  lea     rdx, aEndOfToken; " <end of token>\n"
0x1800375e0  mov     rcx, rbx; Stream
0x1800375e3  call    cs:__imp_fprintf
0x1800375e9  add     rsp, 20h
0x1800375ed  pop     r14
0x1800375ef  pop     rdi
0x1800375f0  pop     rsi
0x1800375f1  pop     rbp
0x1800375f2  pop     rbx
0x1800375f3  retn
```
