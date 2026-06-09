# JSONParserLib::JSONReader::ParseNameValuePair(IMemObj *,JSONParserLib::JSON_PARSER_TOKEN,JSONParserLib::JSONNode * &)

- ea: `0x1008303b0`
- end: `0x100830744`
- name: `?ParseNameValuePair@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@W4JSON_PARSER_TOKEN@2@AEAPEAVJSONNode@2@@Z`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x100830030`

## callees

- `0x10082c530`
- `0x1008303b0`
- `0x100830bd0`
- `0x100830f60`
- `0x100831620`
- `0x1008317f0`
- `0x100831d50`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10083052a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100830666`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10083052a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100830666`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830446`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830446`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10083057b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1008306b8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10083057b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1008306b8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100830587`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1008306c4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100830587`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1008306c4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1008304eb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100830627`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1008304eb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100830627`

## string_xrefs

- `0x100830515`: `Sql\Ntdbms\storeng\jsonparser\include\JSON_Map.h`
- `0x100830651`: `Sql\Ntdbms\storeng\jsonparser\include\JSON_Map.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall JSONParserLib::JSONReader::ParseNameValuePair(__int64 a1, struct IMemObj *a2, int a3, __int64 a4)
{
  unsigned int CurrentToken; // edi
  __int64 v8; // rcx
  wchar_t *v9; // rbx
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rdi
  __int64 v14; // rsi
  wchar_t **v15; // rdi
  wchar_t *v16; // rax
  __int64 v17; // r15
  __int64 v18; // rdi
  __int64 v19; // r14
  wchar_t **v20; // rdi
  wchar_t *v21; // rax
  JSONParserLib::JSONNode *v22; // rbx
  wchar_t *String2; // [rsp+30h] [rbp-30h] BYREF
  JSONParserLib::JSONNode *v24[2]; // [rsp+38h] [rbp-28h] BYREF
  wchar_t **v25; // [rsp+48h] [rbp-18h]
  wchar_t **v26; // [rsp+50h] [rbp-10h]
  JSONParserLib::JSONNode *v27; // [rsp+A8h] [rbp+48h] BYREF

  v24[1] = (JSONParserLib::JSONNode *)-2LL;
  if ( *(_QWORD *)a4 && a3 == 5 )
  {
    LODWORD(v27) = 0;
    String2 = 0;
    CurrentToken = JSONParserLib::JSONReader::ParseString((JSONParserLib::JSONReader *)a1, a2, (void **)&String2);
    if ( !CurrentToken )
    {
      CurrentToken = JSONParserLib::JSONReader::GetCurrentToken(
                       (JSONParserLib::JSONReader *)a1,
                       (enum JSONParserLib::JSON_PARSER_TOKEN *)&v27);
      if ( !CurrentToken )
      {
        v8 = *(unsigned int *)(a1 + 32);
        if ( *(_WORD *)(*(_QWORD *)(a1 + 24) + 2 * v8) )
        {
          *(_DWORD *)(a1 + 32) = v8 + 1;
LABEL_8:
          if ( (_DWORD)v27 != 8 )
          {
            CurrentToken = 6;
            goto LABEL_10;
          }
          CurrentToken = JSONParserLib::JSONReader::GetCurrentToken(
                           (JSONParserLib::JSONReader *)a1,
                           (enum JSONParserLib::JSON_PARSER_TOKEN *)&v27);
          if ( CurrentToken || (v11 = *(unsigned int *)(a1 + 32), !*(_WORD *)(*(_QWORD *)(a1 + 24) + 2 * v11)) )
          {
            if ( CurrentToken )
              goto LABEL_10;
          }
          else
          {
            *(_DWORD *)(a1 + 32) = v11 + 1;
          }
          v24[0] = 0;
          if ( (_DWORD)v27 != 9 && (_DWORD)v27 != 6 )
          {
            CurrentToken = JSONParserLib::JSONReader::ParseSimpleValue((JSONParserLib::JSONReader *)a1);
            if ( !CurrentToken )
            {
              v12 = *(_QWORD *)(*(_QWORD *)a4 + 16LL);
              v25 = (wchar_t **)v12;
              v13 = *(_QWORD *)(v12 + 8);
              v14 = 0;
              v9 = String2;
              if ( *(_BYTE *)(v12 + 20) && v13 )
              {
                do
                {
                  if ( *(_QWORD *)v13 )
                  {
                    if ( v9 )
                      goto LABEL_25;
                  }
                  else if ( !v9 )
                  {
LABEL_25:
                    if ( !_wcsicmp(*(const wchar_t **)v13, v9) )
                      break;
                  }
                  v14 = v13;
                  v13 = *(_QWORD *)(v13 + 16);
                }
                while ( v13 );
              }
              LODWORD(v27) = 198;
              v15 = (wchar_t **)operator new(
                                  0x18u,
                                  *(struct IMemObj **)(v12 + 24),
                                  1,
                                  "Sql\\Ntdbms\\storeng\\jsonparser\\include\\JSON_Map.h",
                                  198,
                                  6u);
              v26 = v15;
              if ( v15 )
              {
                *(_OWORD *)v15 = 0;
                v15[2] = 0;
              }
              else
              {
                v15 = 0;
              }
              if ( v15 )
              {
                if ( v14 )
                  v16 = *(wchar_t **)(v14 + 16);
                else
                  v16 = *(wchar_t **)(v12 + 8);
                v15[2] = v16;
                *v15 = v9;
                if ( v15 == (wchar_t **)-8LL )
                {
                  *_errno() = 22;
                  _invalid_parameter_noinfo();
                }
                else
                {
                  v15[1] = (wchar_t *)v24[0];
                }
                if ( v14 )
                  *(_QWORD *)(v14 + 16) = v15;
                else
                  *(_QWORD *)(v12 + 8) = v15;
                ++*(_DWORD *)(v12 + 16);
                CurrentToken = 0;
                v9 = 0;
                String2 = 0;
                v24[0] = 0;
              }
              else
              {
                CurrentToken = 1;
              }
LABEL_67:
              if ( v24[0] )
                JSONParserLib::JSONNode::`scalar deleting destructor'(v24[0], 1u);
              goto LABEL_11;
            }
LABEL_66:
            v9 = String2;
            goto LABEL_67;
          }
          CurrentToken = JSONParserLib::JSONUtils::CreateNode(
                           a2,
                           (unsigned int)((_DWORD)v27 == 9) + 1,
                           *(_BYTE *)(a1 + 36),
                           *(_DWORD *)(a1 + 32) - 1,
                           v24);
          if ( CurrentToken )
            goto LABEL_66;
          v17 = *(_QWORD *)(*(_QWORD *)a4 + 16LL);
          v26 = (wchar_t **)v17;
          v18 = *(_QWORD *)(v17 + 8);
          v19 = 0;
          v9 = String2;
          if ( !*(_BYTE *)(v17 + 20) || !v18 )
          {
LABEL_51:
            LODWORD(v27) = 198;
            v20 = (wchar_t **)operator new(
                                0x18u,
                                *(struct IMemObj **)(v17 + 24),
                                1,
                                "Sql\\Ntdbms\\storeng\\jsonparser\\include\\JSON_Map.h",
                                198,
                                6u);
            v25 = v20;
            if ( v20 )
            {
              *(_OWORD *)v20 = 0;
              v20[2] = 0;
            }
            else
            {
              v20 = 0;
            }
            if ( v20 )
            {
              if ( v19 )
                v21 = *(wchar_t **)(v19 + 16);
              else
                v21 = *(wchar_t **)(v17 + 8);
              v20[2] = v21;
              *v20 = v9;
              v22 = v24[0];
              if ( v20 == (wchar_t **)-8LL )
              {
                *_errno() = 22;
                _invalid_parameter_noinfo();
              }
              else
              {
                v20[1] = (wchar_t *)v24[0];
              }
              if ( v19 )
                *(_QWORD *)(v19 + 16) = v20;
              else
                *(_QWORD *)(v17 + 8) = v20;
              ++*(_DWORD *)(v17 + 16);
              v27 = v22;
              CurrentToken = JSONParserLib::CDynamicBuffer<void *>::Add(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL), &v27);
              v24[0] = 0;
              v9 = 0;
              String2 = 0;
            }
            else
            {
              CurrentToken = 1;
            }
            goto LABEL_67;
          }
          while ( 1 )
          {
            if ( *(_QWORD *)v18 )
            {
              if ( v9 )
                goto LABEL_49;
            }
            else if ( !v9 )
            {
LABEL_49:
              if ( !_wcsicmp(*(const wchar_t **)v18, v9) )
                goto LABEL_51;
            }
            v19 = v18;
            v18 = *(_QWORD *)(v18 + 16);
            if ( !v18 )
              goto LABEL_51;
          }
        }
      }
      if ( !CurrentToken )
        goto LABEL_8;
    }
LABEL_10:
    v9 = String2;
LABEL_11:
    operator delete[](v9);
    return CurrentToken;
  }
  return 6;
}

```

## disassembly

```asm
0x1008303b0  mov     rax, rsp
0x1008303b3  push    rbp
0x1008303b4  push    rdi
0x1008303b5  push    r12
0x1008303b7  push    r14
0x1008303b9  push    r15
0x1008303bb  mov     rbp, rsp
0x1008303be  sub     rsp, 60h
0x1008303c2  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1008303ca  mov     [rax+8], rbx
0x1008303ce  mov     [rax+10h], rsi
0x1008303d2  mov     rbx, r9
0x1008303d5  mov     r14, rdx
0x1008303d8  mov     rsi, rcx
0x1008303db  cmp     qword ptr [r9], 0
0x1008303df  jz      loc_100830726
0x1008303e5  cmp     r8d, 5
0x1008303e9  jnz     loc_100830726
0x1008303ef  xor     r12d, r12d
0x1008303f2  mov     dword ptr [rbp+arg_18], r12d
0x1008303f6  mov     [rbp+String2], r12
0x1008303fa  lea     r8, [rbp+String2]
0x1008303fe  call    ?ParseString@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@AEAV?$CAutoRg@_W@@@Z; JSONParserLib::JSONReader::ParseString(IMemObj *,CAutoRg<wchar_t> &)
0x100830403  mov     edi, eax
0x100830405  test    eax, eax
0x100830407  jnz     short loc_10083043F
0x100830409  lea     rdx, [rbp+arg_18]; enum JSONParserLib::JSON_PARSER_TOKEN *
0x10083040d  mov     rcx, rsi; this
0x100830410  call    ?GetCurrentToken@JSONReader@JSONParserLib@@AEAAKAEAW4JSON_PARSER_TOKEN@2@@Z; JSONParserLib::JSONReader::GetCurrentToken(JSONParserLib::JSON_PARSER_TOKEN &)
0x100830415  mov     edi, eax
0x100830417  test    eax, eax
0x100830419  jnz     short loc_100830430
0x10083041b  mov     ecx, [rsi+20h]
0x10083041e  mov     rax, [rsi+18h]
0x100830422  cmp     [rax+rcx*2], di
0x100830426  jz      short loc_100830430
0x100830428  lea     eax, [rcx+1]
0x10083042b  mov     [rsi+20h], eax
0x10083042e  jmp     short loc_100830434
0x100830430  test    edi, edi
0x100830432  jnz     short loc_10083043F
0x100830434  cmp     dword ptr [rbp+arg_18], 8
0x100830438  jz      short loc_100830453
0x10083043a  mov     edi, 6
0x10083043f  mov     rbx, [rbp+String2]
0x100830443  mov     rcx, rbx
0x100830446  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10083044c  mov     eax, edi
0x10083044e  jmp     loc_10083072B
0x100830453  lea     rdx, [rbp+arg_18]; enum JSONParserLib::JSON_PARSER_TOKEN *
0x100830457  mov     rcx, rsi; this
0x10083045a  call    ?GetCurrentToken@JSONReader@JSONParserLib@@AEAAKAEAW4JSON_PARSER_TOKEN@2@@Z; JSONParserLib::JSONReader::GetCurrentToken(JSONParserLib::JSON_PARSER_TOKEN &)
0x10083045f  mov     edi, eax
0x100830461  test    eax, eax
0x100830463  jnz     short loc_10083047A
0x100830465  mov     ecx, [rsi+20h]
0x100830468  mov     rax, [rsi+18h]
0x10083046c  cmp     [rax+rcx*2], di
0x100830470  jz      short loc_10083047A
0x100830472  lea     eax, [rcx+1]
0x100830475  mov     [rsi+20h], eax
0x100830478  jmp     short loc_10083047E
0x10083047a  test    edi, edi
0x10083047c  jnz     short loc_10083043F
0x10083047e  mov     [rbp+var_28], r12
0x100830482  mov     eax, dword ptr [rbp+arg_18]
0x100830485  cmp     eax, 9
0x100830488  jz      loc_1008305BC
0x10083048e  cmp     eax, 6
0x100830491  jz      loc_1008305BC
0x100830497  lea     r9, [rbp+var_28]
0x10083049b  mov     r8d, eax
0x10083049e  mov     rdx, r14
0x1008304a1  mov     rcx, rsi; this
0x1008304a4  call    ?ParseSimpleValue@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@W4JSON_PARSER_TOKEN@2@AEAV?$CAutoP@VJSONNode@JSONParserLib@@@@@Z; JSONParserLib::JSONReader::ParseSimpleValue(IMemObj *,JSONParserLib::JSON_PARSER_TOKEN,CAutoP<JSONParserLib::JSONNode> &)
0x1008304a9  mov     edi, eax
0x1008304ab  test    eax, eax
0x1008304ad  jnz     loc_100830706
0x1008304b3  mov     rax, [rbx]
0x1008304b6  mov     r14, [rax+10h]
0x1008304ba  mov     [rbp+var_18], r14
0x1008304be  mov     rdi, [r14+8]
0x1008304c2  mov     rsi, r12
0x1008304c5  mov     rbx, [rbp+String2]
0x1008304c9  cmp     [r14+14h], sil
0x1008304cd  jz      short loc_100830501
0x1008304cf  test    rdi, rdi
0x1008304d2  jz      short loc_100830501
0x1008304d4  mov     rcx, [rdi]; String1
0x1008304d7  test    rcx, rcx
0x1008304da  jz      short loc_1008304E3
0x1008304dc  test    rbx, rbx
0x1008304df  jz      short loc_1008304F5
0x1008304e1  jmp     short loc_1008304E8
0x1008304e3  test    rbx, rbx
0x1008304e6  jnz     short loc_1008304F5
0x1008304e8  mov     rdx, rbx; String2
0x1008304eb  call    cs:__imp__wcsicmp
0x1008304f1  test    eax, eax
0x1008304f3  jz      short loc_100830501
0x1008304f5  mov     rsi, rdi
0x1008304f8  mov     rdi, [rdi+10h]
0x1008304fc  test    rdi, rdi
0x1008304ff  jnz     short loc_1008304D4
0x100830501  mov     dword ptr [rbp+arg_18], 0C6h
0x100830508  mov     [rsp+60h+var_38], 6
0x10083050d  mov     dword ptr [rsp+60h+var_40], 0C6h
0x100830515  lea     r9, aSqlNtdbmsStore_1; "Sql\\Ntdbms\\storeng\\jsonparser\\inclu"...
0x10083051c  mov     r8d, 1
0x100830522  mov     rdx, [r14+18h]
0x100830526  lea     ecx, [r8+17h]
0x10083052a  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100830530  mov     rdi, rax
0x100830533  mov     [rbp+var_10], rax
0x100830537  test    rax, rax
0x10083053a  jz      short loc_10083054A
0x10083053c  xorps   xmm0, xmm0
0x10083053f  xor     eax, eax
0x100830541  movups  xmmword ptr [rdi], xmm0
0x100830544  mov     [rdi+10h], rax
0x100830548  jmp     short loc_10083054D
0x10083054a  mov     rdi, r12
0x10083054d  test    rdi, rdi
0x100830550  jnz     short loc_10083055C
0x100830552  mov     edi, 1
0x100830557  jmp     loc_10083070A
0x10083055c  test    rsi, rsi
0x10083055f  jz      short loc_100830567
0x100830561  mov     rax, [rsi+10h]
0x100830565  jmp     short loc_10083056B
0x100830567  mov     rax, [r14+8]
0x10083056b  mov     [rdi+10h], rax
0x10083056f  mov     [rdi], rbx
0x100830572  lea     rcx, [rdi+8]
0x100830576  test    rcx, rcx
0x100830579  jnz     short loc_10083058F
0x10083057b  call    cs:__imp__errno
0x100830581  mov     dword ptr [rax], 16h
0x100830587  call    cs:__imp__invalid_parameter_noinfo
0x10083058d  jmp     short loc_100830596
0x10083058f  mov     rax, [rbp+var_28]
0x100830593  mov     [rcx], rax
0x100830596  test    rsi, rsi
0x100830599  jnz     short loc_1008305A1
0x10083059b  mov     [r14+8], rdi
0x10083059f  jmp     short loc_1008305A5
0x1008305a1  mov     [rsi+10h], rdi
0x1008305a5  inc     dword ptr [r14+10h]
0x1008305a9  mov     edi, r12d
0x1008305ac  mov     rbx, r12
0x1008305af  mov     [rbp+String2], rbx
0x1008305b3  mov     [rbp+var_28], r12
0x1008305b7  jmp     loc_10083070A
0x1008305bc  mov     r9d, [rsi+20h]
0x1008305c0  dec     r9d
0x1008305c3  mov     edx, r12d
0x1008305c6  cmp     eax, 9
0x1008305c9  setz    dl
0x1008305cc  inc     edx
0x1008305ce  lea     rax, [rbp+var_28]
0x1008305d2  mov     [rsp+60h+var_40], rax
0x1008305d7  movzx   r8d, byte ptr [rsi+24h]
0x1008305dc  mov     rcx, r14
0x1008305df  call    ?CreateNode@JSONUtils@JSONParserLib@@SAKPEAVIMemObj@@W4JSON_DATATYPE@2@_NKAEAV?$CAutoP@VJSONNode@JSONParserLib@@@@@Z; JSONParserLib::JSONUtils::CreateNode(IMemObj *,JSONParserLib::JSON_DATATYPE,bool,ulong,CAutoP<JSONParserLib::JSONNode> &)
0x1008305e4  mov     edi, eax
0x1008305e6  test    eax, eax
0x1008305e8  jnz     loc_100830706
0x1008305ee  mov     rax, [rbx]
0x1008305f1  mov     r15, [rax+10h]
0x1008305f5  mov     [rbp+var_10], r15
0x1008305f9  mov     rdi, [r15+8]
0x1008305fd  mov     r14, r12
0x100830600  mov     rbx, [rbp+String2]
0x100830604  cmp     [r15+14h], r14b
0x100830608  jz      short loc_10083063D
0x10083060a  test    rdi, rdi
0x10083060d  jz      short loc_10083063D
0x10083060f  nop
0x100830610  mov     rcx, [rdi]; String1
0x100830613  test    rcx, rcx
0x100830616  jz      short loc_10083061F
0x100830618  test    rbx, rbx
0x10083061b  jz      short loc_100830631
0x10083061d  jmp     short loc_100830624
0x10083061f  test    rbx, rbx
0x100830622  jnz     short loc_100830631
0x100830624  mov     rdx, rbx; String2
0x100830627  call    cs:__imp__wcsicmp
0x10083062d  test    eax, eax
0x10083062f  jz      short loc_10083063D
0x100830631  mov     r14, rdi
0x100830634  mov     rdi, [rdi+10h]
0x100830638  test    rdi, rdi
0x10083063b  jnz     short loc_100830610
0x10083063d  mov     dword ptr [rbp+arg_18], 0C6h
0x100830644  mov     [rsp+60h+var_38], 6
0x100830649  mov     dword ptr [rsp+60h+var_40], 0C6h
0x100830651  lea     r9, aSqlNtdbmsStore_1; "Sql\\Ntdbms\\storeng\\jsonparser\\inclu"...
0x100830658  mov     r8d, 1
0x10083065e  mov     rdx, [r15+18h]
0x100830662  lea     ecx, [r8+17h]
0x100830666  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10083066c  mov     rdi, rax
0x10083066f  mov     [rbp+var_18], rax
0x100830673  test    rax, rax
0x100830676  jz      short loc_100830686
0x100830678  xorps   xmm0, xmm0
0x10083067b  xor     eax, eax
0x10083067d  movups  xmmword ptr [rdi], xmm0
0x100830680  mov     [rdi+10h], rax
0x100830684  jmp     short loc_100830689
0x100830686  mov     rdi, r12
0x100830689  test    rdi, rdi
0x10083068c  jnz     short loc_100830695
0x10083068e  mov     edi, 1
0x100830693  jmp     short loc_10083070A
0x100830695  test    r14, r14
0x100830698  jz      short loc_1008306A0
0x10083069a  mov     rax, [r14+10h]
0x10083069e  jmp     short loc_1008306A4
0x1008306a0  mov     rax, [r15+8]
0x1008306a4  mov     [rdi+10h], rax
0x1008306a8  mov     [rdi], rbx
0x1008306ab  lea     rax, [rdi+8]
0x1008306af  mov     rbx, [rbp+var_28]
0x1008306b3  test    rax, rax
0x1008306b6  jnz     short loc_1008306CC
0x1008306b8  call    cs:__imp__errno
0x1008306be  mov     dword ptr [rax], 16h
0x1008306c4  call    cs:__imp__invalid_parameter_noinfo
0x1008306ca  jmp     short loc_1008306CF
0x1008306cc  mov     [rax], rbx
0x1008306cf  test    r14, r14
0x1008306d2  jnz     short loc_1008306DA
0x1008306d4  mov     [r15+8], rdi
0x1008306d8  jmp     short loc_1008306DE
0x1008306da  mov     [r14+10h], rdi
0x1008306de  inc     dword ptr [r15+10h]
0x1008306e2  mov     [rbp+arg_18], rbx
0x1008306e6  mov     rcx, [rsi+10h]
0x1008306ea  lea     rdx, [rbp+arg_18]
0x1008306ee  mov     rcx, [rcx+10h]
0x1008306f2  call    ?Add@?$CDynamicBuffer@PEAX@JSONParserLib@@QEAAKAEBQEAX@Z; JSONParserLib::CDynamicBuffer<void *>::Add(void * const &)
0x1008306f7  mov     edi, eax
0x1008306f9  mov     [rbp+var_28], r12
0x1008306fd  mov     rbx, r12
0x100830700  mov     [rbp+String2], rbx
0x100830704  jmp     short loc_10083070A
0x100830706  mov     rbx, [rbp+String2]
0x10083070a  mov     rcx, [rbp+var_28]; this
0x10083070e  test    rcx, rcx
0x100830711  jz      loc_100830443
0x100830717  mov     edx, 1; unsigned int
0x10083071c  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x100830721  jmp     loc_100830443
0x100830726  mov     eax, 6
0x10083072b  lea     r11, [rsp+60h+var_s0]
0x100830730  mov     rbx, [r11+30h]
0x100830734  mov     rsi, [r11+38h]
0x100830738  mov     rsp, r11
0x10083073b  pop     r15
0x10083073d  pop     r14
0x10083073f  pop     r12
0x100830741  pop     rdi
0x100830742  pop     rbp
0x100830743  retn
```
