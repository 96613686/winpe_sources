# web::json::details::json_error_category_impl::message(int)

- ea: `0x180073390`
- end: `0x180073571`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800153b0`
- `0x180073390`

## string_xrefs

- `0x18007345f`: `Left-over characters in stream after parsing a JSON value`
- `0x18007341f`: `Malformed comment`
- `0x18007353c`: `Malformed token`
- `0x1800734c5`: `Unknown json error`
- `0x1800734e5`: `Unexpected token`

## pseudocode

```c
__int64 __fastcall web::json::details::json_error_category_impl::message(__int64 a1, __int64 a2, int a3)
{
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  const char *v8; // rdx
  __int64 v9; // r8
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d

  if ( a3 > 6 )
  {
    v10 = a3 - 7;
    if ( !v10 )
    {
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Malformed string literal";
      goto LABEL_25;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v9 = 15;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Malformed token";
      goto LABEL_26;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v9 = 17;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Mismatched braces";
      goto LABEL_26;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v9 = 16;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Nesting too deep";
      goto LABEL_26;
    }
    if ( v13 == 1 )
    {
      v9 = 16;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Unexpected token";
      goto LABEL_26;
    }
    goto LABEL_19;
  }
  if ( a3 == 6 )
  {
    v9 = 25;
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    v8 = "Malformed numeric literal";
  }
  else
  {
    v4 = a3 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            if ( v7 == 1 )
            {
              *(_OWORD *)a2 = 0;
              *(_QWORD *)(a2 + 16) = 0;
              *(_QWORD *)(a2 + 24) = 0;
              v8 = "Malformed object literal";
LABEL_25:
              v9 = 24;
              goto LABEL_26;
            }
LABEL_19:
            v9 = 18;
            *(_OWORD *)a2 = 0;
            *(_QWORD *)(a2 + 16) = 0;
            *(_QWORD *)(a2 + 24) = 0;
            v8 = "Unknown json error";
            goto LABEL_26;
          }
          v9 = 17;
          *(_OWORD *)a2 = 0;
          *(_QWORD *)(a2 + 16) = 0;
          *(_QWORD *)(a2 + 24) = 0;
          v8 = "Malformed literal";
        }
        else
        {
          v9 = 17;
          *(_OWORD *)a2 = 0;
          *(_QWORD *)(a2 + 16) = 0;
          *(_QWORD *)(a2 + 24) = 0;
          v8 = "Malformed comment";
        }
      }
      else
      {
        v9 = 23;
        *(_OWORD *)a2 = 0;
        *(_QWORD *)(a2 + 16) = 0;
        *(_QWORD *)(a2 + 24) = 0;
        v8 = "Malformed array literal";
      }
    }
    else
    {
      v9 = 57;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Left-over characters in stream after parsing a JSON value";
    }
  }
LABEL_26:
  std::string::_Construct<1,char const *>(a2, v8, v9);
  return a2;
}

```

## disassembly

```asm
0x180073390  push    rbx
0x180073392  sub     rsp, 30h
0x180073396  xor     ecx, ecx
0x180073398  mov     rbx, rdx
0x18007339b  cmp     r8d, 6
0x18007339f  jg      loc_18007348B
0x1800733a5  jz      loc_18007346B
0x1800733ab  sub     r8d, 1
0x1800733af  jz      loc_18007344B
0x1800733b5  sub     r8d, 1
0x1800733b9  jz      short loc_18007342B
0x1800733bb  sub     r8d, 1
0x1800733bf  jz      short loc_18007340B
0x1800733c1  sub     r8d, 1
0x1800733c5  jz      short loc_1800733EB
0x1800733c7  cmp     r8d, 1
0x1800733cb  jnz     loc_1800734B1
0x1800733d1  xorps   xmm0, xmm0
0x1800733d4  movups  xmmword ptr [rdx], xmm0
0x1800733d7  mov     [rdx+10h], rcx
0x1800733db  mov     [rdx+18h], rcx
0x1800733df  lea     rdx, aMalformedObjec; "Malformed object literal"
0x1800733e6  jmp     loc_18007355A
0x1800733eb  xorps   xmm0, xmm0
0x1800733ee  mov     r8d, 11h
0x1800733f4  movups  xmmword ptr [rdx], xmm0
0x1800733f7  mov     [rdx+10h], rcx
0x1800733fb  mov     [rdx+18h], rcx
0x1800733ff  lea     rdx, aMalformedLiter; "Malformed literal"
0x180073406  jmp     loc_180073560
0x18007340b  xorps   xmm0, xmm0
0x18007340e  mov     r8d, 11h
0x180073414  movups  xmmword ptr [rdx], xmm0
0x180073417  mov     [rdx+10h], rcx
0x18007341b  mov     [rdx+18h], rcx
0x18007341f  lea     rdx, aMalformedComme; "Malformed comment"
0x180073426  jmp     loc_180073560
0x18007342b  xorps   xmm0, xmm0
0x18007342e  mov     r8d, 17h
0x180073434  movups  xmmword ptr [rdx], xmm0
0x180073437  mov     [rdx+10h], rcx
0x18007343b  mov     [rdx+18h], rcx
0x18007343f  lea     rdx, aMalformedArray; "Malformed array literal"
0x180073446  jmp     loc_180073560
0x18007344b  xorps   xmm0, xmm0
0x18007344e  mov     r8d, 39h ; '9'
0x180073454  movups  xmmword ptr [rdx], xmm0
0x180073457  mov     [rdx+10h], rcx
0x18007345b  mov     [rdx+18h], rcx
0x18007345f  lea     rdx, aLeftOverCharac_0; "Left-over characters in stream after pa"...
0x180073466  jmp     loc_180073560
0x18007346b  xorps   xmm0, xmm0
0x18007346e  mov     r8d, 19h
0x180073474  movups  xmmword ptr [rdx], xmm0
0x180073477  mov     [rdx+10h], rcx
0x18007347b  mov     [rdx+18h], rcx
0x18007347f  lea     rdx, aMalformedNumer; "Malformed numeric literal"
0x180073486  jmp     loc_180073560
0x18007348b  sub     r8d, 7
0x18007348f  jz      loc_180073545
0x180073495  sub     r8d, 1
0x180073499  jz      loc_180073528
0x18007349f  sub     r8d, 1
0x1800734a3  jz      short loc_18007350B
0x1800734a5  sub     r8d, 1
0x1800734a9  jz      short loc_1800734EE
0x1800734ab  cmp     r8d, 1
0x1800734af  jz      short loc_1800734D1
0x1800734b1  xorps   xmm0, xmm0
0x1800734b4  mov     r8d, 12h
0x1800734ba  movups  xmmword ptr [rdx], xmm0
0x1800734bd  mov     [rdx+10h], rcx
0x1800734c1  mov     [rdx+18h], rcx
0x1800734c5  lea     rdx, aUnknownJsonErr; "Unknown json error"
0x1800734cc  jmp     loc_180073560
0x1800734d1  xorps   xmm0, xmm0
0x1800734d4  mov     r8d, 10h
0x1800734da  movups  xmmword ptr [rdx], xmm0
0x1800734dd  mov     [rdx+10h], rcx
0x1800734e1  mov     [rdx+18h], rcx
0x1800734e5  lea     rdx, aUnexpectedToke; "Unexpected token"
0x1800734ec  jmp     short loc_180073560
0x1800734ee  xorps   xmm0, xmm0
0x1800734f1  mov     r8d, 10h
0x1800734f7  movups  xmmword ptr [rdx], xmm0
0x1800734fa  mov     [rdx+10h], rcx
0x1800734fe  mov     [rdx+18h], rcx
0x180073502  lea     rdx, aNestingTooDeep; "Nesting too deep"
0x180073509  jmp     short loc_180073560
0x18007350b  xorps   xmm0, xmm0
0x18007350e  mov     r8d, 11h
0x180073514  movups  xmmword ptr [rdx], xmm0
0x180073517  mov     [rdx+10h], rcx
0x18007351b  mov     [rdx+18h], rcx
0x18007351f  lea     rdx, aMismatchedBrac; "Mismatched braces"
0x180073526  jmp     short loc_180073560
0x180073528  xorps   xmm0, xmm0
0x18007352b  mov     r8d, 0Fh
0x180073531  movups  xmmword ptr [rdx], xmm0
0x180073534  mov     [rdx+10h], rcx
0x180073538  mov     [rdx+18h], rcx
0x18007353c  lea     rdx, aMalformedToken; "Malformed token"
0x180073543  jmp     short loc_180073560
0x180073545  xorps   xmm0, xmm0
0x180073548  movups  xmmword ptr [rdx], xmm0
0x18007354b  mov     [rdx+10h], rcx
0x18007354f  mov     [rdx+18h], rcx
0x180073553  lea     rdx, aMalformedStrin; "Malformed string literal"
0x18007355a  mov     r8d, 18h
0x180073560  mov     rcx, rbx
0x180073563  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180073568  mov     rax, rbx
0x18007356b  add     rsp, 30h
0x18007356f  pop     rbx
0x180073570  retn
```
