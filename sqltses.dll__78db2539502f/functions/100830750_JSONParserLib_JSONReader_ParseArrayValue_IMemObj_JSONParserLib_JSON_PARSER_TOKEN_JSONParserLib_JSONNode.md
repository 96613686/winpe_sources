# JSONParserLib::JSONReader::ParseArrayValue(IMemObj *,JSONParserLib::JSON_PARSER_TOKEN,JSONParserLib::JSONNode * &)

- ea: `0x100830750`
- end: `0x100830bc7`
- name: `?ParseArrayValue@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@W4JSON_PARSER_TOKEN@2@AEAPEAVJSONNode@2@@Z`
- size: `1143`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x100830030`

## callees

- `0x10048b440`
- `0x10082c530`
- `0x100830750`
- `0x100830bd0`
- `0x1008317f0`
- `0x100831d50`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1008308be`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100830aa3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1008308be`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100830aa3`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830930`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830941`
- `sqldk!??_V@YAXPEAX@Z` at `0x10083094b`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830b15`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830b26`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830b30`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830930`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830941`
- `sqldk!??_V@YAXPEAX@Z` at `0x10083094b`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830b15`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830b26`
- `sqldk!??_V@YAXPEAX@Z` at `0x100830b30`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10083091a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100830aff`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10083091a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100830aff`

## string_xrefs

- `0x1008308ac`: `Sql\Ntdbms\storeng\jsonparser\include\JSON_DynamicBuffer.h`
- `0x100830a91`: `Sql\Ntdbms\storeng\jsonparser\include\JSON_DynamicBuffer.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JSONParserLib::JSONReader::ParseArrayValue(__int64 a1, struct IMemObj *a2, int a3, __int64 a4)
{
  unsigned int v7; // esi
  JSONParserLib::JSONNode *v8; // rax
  __int64 v9; // rbp
  unsigned int v10; // eax
  unsigned int v11; // r10d
  unsigned int v12; // r9d
  unsigned int v13; // r8d
  unsigned int v14; // edx
  unsigned int v15; // ecx
  __int64 v16; // r14
  unsigned __int64 v17; // rax
  void *v18; // rax
  void *v19; // r15
  void *v20; // rdi
  void *v21; // rbx
  void *v22; // rcx
  JSONParserLib::JSONNode *v23; // r15
  __int64 v24; // rbp
  unsigned int v25; // eax
  unsigned int v26; // r10d
  unsigned int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // edx
  unsigned int v30; // ecx
  __int64 v31; // r14
  unsigned __int64 v32; // rax
  void *v33; // rax
  void *v34; // r12
  void *v35; // rdi
  void *v36; // rbx
  void *v37; // rcx
  JSONParserLib::JSONNode *Source; // [rsp+40h] [rbp-58h] BYREF
  void *v39; // [rsp+48h] [rbp-50h]
  void *v40; // [rsp+50h] [rbp-48h]
  JSONParserLib::JSONNode *v41; // [rsp+58h] [rbp-40h] BYREF
  _QWORD v42[2]; // [rsp+60h] [rbp-38h] BYREF
  JSONParserLib::JSONNode *v43; // [rsp+B8h] [rbp+20h] BYREF

  v42[1] = -2;
  if ( !*(_QWORD *)a4 )
    return 2;
  v43 = 0;
  if ( a3 == 9 || a3 == 6 )
  {
    v7 = JSONParserLib::JSONUtils::CreateNode(
           a2,
           (unsigned int)(a3 == 9) + 1,
           *(_BYTE *)(a1 + 36),
           *(_DWORD *)(a1 + 32) - 1,
           &v43);
    if ( v7 )
      goto LABEL_73;
    v23 = v43;
    v41 = v43;
    v24 = *(_QWORD *)(*(_QWORD *)a4 + 16LL);
    v25 = *(_DWORD *)(v24 + 28);
    v26 = v25 + 1;
    v27 = v25 + 1;
    if ( v25 + 1 < v25 || v25 == -1 )
      goto LABEL_72;
    if ( *(_BYTE *)(v24 + 48) )
    {
      v29 = *(_DWORD *)(v24 + 24);
      if ( v26 > v29 )
      {
        while ( !v7 )
        {
          v30 = v29 >> 1;
          if ( v29 >> 1 <= *(_DWORD *)(v24 + 36) )
            v30 = *(_DWORD *)(v24 + 36);
          if ( v30 + v29 > v29 )
            v29 += v30;
          else
            v7 = 3;
          if ( v29 >= v26 )
          {
            if ( v7 )
              goto LABEL_73;
            v27 = v29;
            goto LABEL_55;
          }
        }
        goto LABEL_73;
      }
    }
    else
    {
      v28 = v25 + *(_DWORD *)(v24 + 36) - (v25 + *(_DWORD *)(v24 + 36)) % *(_DWORD *)(v24 + 36);
      if ( v28 >= v26 )
        v27 = v25 + *(_DWORD *)(v24 + 36) - (v25 + *(_DWORD *)(v24 + 36)) % *(_DWORD *)(v24 + 36);
      v7 = v28 < v26 ? 3 : 0;
      if ( v28 < v26 )
        goto LABEL_68;
    }
LABEL_55:
    v31 = *(unsigned int *)(v24 + 32);
    if ( v27 >= (unsigned int)v31 )
      v31 = v27;
    if ( (unsigned int)v31 <= *(_DWORD *)(v24 + 24) )
      goto LABEL_70;
    _mm_lfence();
    v7 = 0;
    v32 = 8LL * (unsigned int)v31;
    if ( !is_mul_ok((unsigned int)v31, 8u) )
      v32 = -1;
    v33 = operator new[](
            v32,
            *(struct IMemObj **)(v24 + 40),
            1,
            "Sql\\Ntdbms\\storeng\\jsonparser\\include\\JSON_DynamicBuffer.h",
            225,
            6u);
    v34 = v33;
    v40 = v33;
    if ( v33 )
    {
      v35 = *(void **)(v24 + 16);
      *(_QWORD *)(v24 + 16) = 0;
      v36 = v35;
      v39 = v35;
      if ( v35 )
      {
        memcpy_s(v33, 8 * v31, v35, 8LL * *(unsigned int *)(v24 + 28));
        v36 = 0;
        v39 = 0;
        operator delete(v35, 8u);
      }
      v40 = 0;
      v37 = *(void **)(v24 + 16);
      if ( v37 != v34 )
        operator delete[](v37);
      *(_QWORD *)(v24 + 16) = v34;
      *(_DWORD *)(v24 + 24) = v31;
      operator delete[](v36);
    }
    else
    {
      v7 = 1;
    }
    operator delete[](0);
    if ( !v7 )
    {
LABEL_70:
      memcpy_s((void *const)(*(_QWORD *)(v24 + 16) + 8LL * *(unsigned int *)(v24 + 28)), 8u, &v41, 8u);
      ++*(_DWORD *)(v24 + 28);
      goto LABEL_71;
    }
LABEL_68:
    if ( v7 )
      goto LABEL_73;
LABEL_71:
    v43 = 0;
    v42[0] = v23;
    v7 = JSONParserLib::CDynamicBuffer<void *>::Add(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL), v42);
    goto LABEL_73;
  }
  v7 = JSONParserLib::JSONReader::ParseSimpleValue((JSONParserLib::JSONReader *)a1);
  if ( v7 )
    goto LABEL_73;
  v8 = v43;
  v43 = 0;
  Source = v8;
  v9 = *(_QWORD *)(*(_QWORD *)a4 + 16LL);
  v10 = *(_DWORD *)(v9 + 28);
  v11 = v10 + 1;
  v12 = v10 + 1;
  if ( v10 + 1 < v10 || v10 == -1 )
  {
LABEL_72:
    v7 = 3;
    goto LABEL_73;
  }
  if ( *(_BYTE *)(v9 + 48) )
  {
    v14 = *(_DWORD *)(v9 + 24);
    if ( v11 > v14 )
    {
      while ( !v7 )
      {
        v15 = v14 >> 1;
        if ( v14 >> 1 <= *(_DWORD *)(v9 + 36) )
          v15 = *(_DWORD *)(v9 + 36);
        if ( v15 + v14 > v14 )
          v14 += v15;
        else
          v7 = 3;
        if ( v14 >= v11 )
        {
          if ( v7 )
            goto LABEL_73;
          v12 = v14;
          goto LABEL_23;
        }
      }
      goto LABEL_73;
    }
  }
  else
  {
    v13 = v10 + *(_DWORD *)(v9 + 36) - (v10 + *(_DWORD *)(v9 + 36)) % *(_DWORD *)(v9 + 36);
    if ( v13 >= v11 )
      v12 = v10 + *(_DWORD *)(v9 + 36) - (v10 + *(_DWORD *)(v9 + 36)) % *(_DWORD *)(v9 + 36);
    v7 = v13 < v11 ? 3 : 0;
    if ( v13 < v11 )
      goto LABEL_73;
  }
LABEL_23:
  v16 = *(unsigned int *)(v9 + 32);
  if ( v12 >= (unsigned int)v16 )
    v16 = v12;
  v7 = 0;
  if ( (unsigned int)v16 <= *(_DWORD *)(v9 + 24) )
    goto LABEL_36;
  _mm_lfence();
  v17 = 8LL * (unsigned int)v16;
  if ( !is_mul_ok((unsigned int)v16, 8u) )
    v17 = -1;
  v18 = operator new[](
          v17,
          *(struct IMemObj **)(v9 + 40),
          1,
          "Sql\\Ntdbms\\storeng\\jsonparser\\include\\JSON_DynamicBuffer.h",
          225,
          6u);
  v19 = v18;
  if ( v18 )
  {
    v20 = *(void **)(v9 + 16);
    *(_QWORD *)(v9 + 16) = 0;
    v21 = v20;
    if ( v20 )
    {
      memcpy_s(v18, 8 * v16, v20, 8LL * *(unsigned int *)(v9 + 28));
      v21 = 0;
      operator delete(v20, 8u);
    }
    v22 = *(void **)(v9 + 16);
    if ( v22 != v19 )
      operator delete[](v22);
    *(_QWORD *)(v9 + 16) = v19;
    *(_DWORD *)(v9 + 24) = v16;
    operator delete[](v21);
  }
  else
  {
    v7 = 1;
  }
  operator delete[](0);
  if ( !v7 )
  {
LABEL_36:
    memcpy_s((void *const)(*(_QWORD *)(v9 + 16) + 8LL * *(unsigned int *)(v9 + 28)), 8u, &Source, 8u);
    ++*(_DWORD *)(v9 + 28);
  }
LABEL_73:
  if ( v43 )
    JSONParserLib::JSONNode::`scalar deleting destructor'(v43, 1u);
  return v7;
}

```

## disassembly

```asm
0x100830750  mov     rax, rsp
0x100830753  push    rdi
0x100830754  push    r12
0x100830756  push    r13
0x100830758  push    r14
0x10083075a  push    r15
0x10083075c  sub     rsp, 70h
0x100830760  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x100830768  mov     [rax+8], rbx
0x10083076c  mov     [rax+10h], rbp
0x100830770  mov     [rax+18h], rsi
0x100830774  mov     rbx, r9
0x100830777  mov     rax, rdx
0x10083077a  mov     r13, rcx
0x10083077d  cmp     qword ptr [r9], 0
0x100830781  jnz     short loc_10083078D
0x100830783  mov     eax, 2
0x100830788  jmp     loc_100830BA9
0x10083078d  mov     [rsp+98h+arg_18], 0
0x100830799  cmp     r8d, 9
0x10083079d  jz      loc_10083097F
0x1008307a3  cmp     r8d, 6
0x1008307a7  jz      loc_10083097F
0x1008307ad  lea     r9, [rsp+98h+arg_18]
0x1008307b5  call    ?ParseSimpleValue@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@W4JSON_PARSER_TOKEN@2@AEAV?$CAutoP@VJSONNode@JSONParserLib@@@@@Z; JSONParserLib::JSONReader::ParseSimpleValue(IMemObj *,JSONParserLib::JSON_PARSER_TOKEN,CAutoP<JSONParserLib::JSONNode> &)
0x1008307ba  mov     esi, eax
0x1008307bc  test    eax, eax
0x1008307be  jnz     loc_100830B8D
0x1008307c4  mov     rax, [rsp+98h+arg_18]
0x1008307cc  mov     [rsp+98h+arg_18], 0
0x1008307d8  mov     [rsp+98h+Source], rax
0x1008307dd  mov     rax, [rbx]
0x1008307e0  mov     rbp, [rax+10h]
0x1008307e4  mov     eax, [rbp+1Ch]
0x1008307e7  lea     r10d, [rax+1]
0x1008307eb  mov     r9d, r10d
0x1008307ee  cmp     r10d, eax
0x1008307f1  jb      loc_100830B88
0x1008307f7  cmp     r10d, 1
0x1008307fb  jb      loc_100830B88
0x100830801  cmp     [rbp+30h], sil
0x100830805  jnz     short loc_100830832
0x100830807  mov     ecx, [rbp+24h]
0x10083080a  lea     r8d, [rcx-1]
0x10083080e  add     r8d, r10d
0x100830811  xor     edx, edx
0x100830813  mov     eax, r8d
0x100830816  div     ecx
0x100830818  sub     r8d, edx
0x10083081b  cmp     r8d, r10d
0x10083081e  cmovnb  r9d, r8d
0x100830822  sbb     esi, esi
0x100830824  and     esi, 3
0x100830827  cmp     r8d, r10d
0x10083082a  jb      loc_100830B8D
0x100830830  jmp     short loc_10083086F
0x100830832  mov     edx, [rbp+18h]
0x100830835  cmp     r10d, edx
0x100830838  jbe     short loc_10083086F
0x10083083a  mov     r8d, 3
0x100830840  test    esi, esi
0x100830842  jnz     loc_100830B8D
0x100830848  mov     ecx, edx
0x10083084a  shr     ecx, 1
0x10083084c  cmp     ecx, [rbp+24h]
0x10083084f  cmovbe  ecx, [rbp+24h]
0x100830853  lea     eax, [rcx+rdx]
0x100830856  cmp     eax, edx
0x100830858  cmovbe  esi, r8d
0x10083085c  cmova   edx, eax
0x10083085f  cmp     edx, r10d
0x100830862  jb      short loc_100830840
0x100830864  test    esi, esi
0x100830866  jnz     loc_100830B8D
0x10083086c  mov     r9d, edx
0x10083086f  mov     r14d, [rbp+20h]
0x100830873  cmp     r9d, r14d
0x100830876  cmovnb  r14d, r9d
0x10083087a  xor     esi, esi
0x10083087c  cmp     r14d, [rbp+18h]
0x100830880  jbe     loc_100830959
0x100830886  lfence
0x100830889  mov     r12d, r14d
0x10083088c  mov     eax, 8
0x100830891  mul     r12
0x100830894  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10083089b  cmovo   rax, rcx
0x10083089f  mov     [rsp+98h+var_70], 6
0x1008308a4  mov     dword ptr [rsp+98h+var_78], 0E1h
0x1008308ac  lea     r9, aSqlNtdbmsStore_3; "Sql\\Ntdbms\\storeng\\jsonparser\\inclu"...
0x1008308b3  lea     r8d, [rsi+1]
0x1008308b7  mov     rdx, [rbp+28h]
0x1008308bb  mov     rcx, rax
0x1008308be  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1008308c4  mov     r15, rax
0x1008308c7  mov     rdi, rax
0x1008308ca  mov     [rsp+98h+var_60], rax
0x1008308cf  test    rax, rax
0x1008308d2  jnz     short loc_1008308D9
0x1008308d4  lea     esi, [rax+1]
0x1008308d7  jmp     short loc_100830948
0x1008308d9  mov     rdi, [rbp+10h]
0x1008308dd  mov     qword ptr [rbp+10h], 0
0x1008308e5  mov     rbx, rdi
0x1008308e8  mov     [rsp+98h+var_68], rbx
0x1008308ed  test    rdi, rdi
0x1008308f0  jz      short loc_100830920
0x1008308f2  mov     r9d, [rbp+1Ch]
0x1008308f6  shl     r9, 3; SourceSize
0x1008308fa  lea     rdx, ds:0[r14*8]; DestinationSize
0x100830902  mov     r8, rdi; Source
0x100830905  mov     rcx, r15; Destination
0x100830908  call    memcpy_s
0x10083090d  xor     ebx, ebx
0x10083090f  mov     [rsp+98h+var_68], rbx
0x100830914  lea     edx, [rbx+8]
0x100830917  mov     rcx, rdi
0x10083091a  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100830920  xor     edi, edi
0x100830922  mov     [rsp+98h+var_60], rdi
0x100830927  mov     rcx, [rbp+10h]
0x10083092b  cmp     rcx, r15
0x10083092e  jz      short loc_100830936
0x100830930  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100830936  mov     [rbp+10h], r15
0x10083093a  mov     [rbp+18h], r14d
0x10083093e  mov     rcx, rbx
0x100830941  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100830947  nop
0x100830948  mov     rcx, rdi
0x10083094b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100830951  test    esi, esi
0x100830953  jnz     loc_100830B8D
0x100830959  mov     ecx, [rbp+1Ch]
0x10083095c  mov     rax, [rbp+10h]
0x100830960  lea     rcx, [rax+rcx*8]; Destination
0x100830964  mov     r9d, 8; SourceSize
0x10083096a  lea     r8, [rsp+98h+Source]; Source
0x10083096f  mov     edx, r9d; DestinationSize
0x100830972  call    memcpy_s
0x100830977  inc     dword ptr [rbp+1Ch]
0x10083097a  jmp     loc_100830B8D
0x10083097f  mov     r9d, [rcx+20h]
0x100830983  dec     r9d
0x100830986  xor     edx, edx
0x100830988  cmp     r8d, 9
0x10083098c  setz    dl
0x10083098f  inc     edx
0x100830991  lea     rcx, [rsp+98h+arg_18]
0x100830999  mov     [rsp+98h+var_78], rcx
0x10083099e  movzx   r8d, byte ptr [r13+24h]
0x1008309a3  mov     rcx, rax
0x1008309a6  call    ?CreateNode@JSONUtils@JSONParserLib@@SAKPEAVIMemObj@@W4JSON_DATATYPE@2@_NKAEAV?$CAutoP@VJSONNode@JSONParserLib@@@@@Z; JSONParserLib::JSONUtils::CreateNode(IMemObj *,JSONParserLib::JSON_DATATYPE,bool,ulong,CAutoP<JSONParserLib::JSONNode> &)
0x1008309ab  mov     esi, eax
0x1008309ad  test    eax, eax
0x1008309af  jnz     loc_100830B8D
0x1008309b5  mov     r15, [rsp+98h+arg_18]
0x1008309bd  mov     [rsp+98h+var_40], r15
0x1008309c2  mov     rax, [rbx]
0x1008309c5  mov     rbp, [rax+10h]
0x1008309c9  mov     eax, [rbp+1Ch]
0x1008309cc  lea     r10d, [rax+1]
0x1008309d0  mov     r9d, r10d
0x1008309d3  cmp     r10d, eax
0x1008309d6  jb      loc_100830B88
0x1008309dc  cmp     r10d, 1
0x1008309e0  jb      loc_100830B88
0x1008309e6  cmp     [rbp+30h], sil
0x1008309ea  jnz     short loc_100830A17
0x1008309ec  mov     ecx, [rbp+24h]
0x1008309ef  lea     r8d, [rcx-1]
0x1008309f3  add     r8d, r10d
0x1008309f6  xor     edx, edx
0x1008309f8  mov     eax, r8d
0x1008309fb  div     ecx
0x1008309fd  sub     r8d, edx
0x100830a00  cmp     r8d, r10d
0x100830a03  cmovnb  r9d, r8d
0x100830a07  sbb     esi, esi
0x100830a09  and     esi, 3
0x100830a0c  cmp     r8d, r10d
0x100830a0f  jb      loc_100830B3A
0x100830a15  jmp     short loc_100830A54
0x100830a17  mov     edx, [rbp+18h]
0x100830a1a  cmp     r10d, edx
0x100830a1d  jbe     short loc_100830A54
0x100830a1f  mov     r8d, 3
0x100830a25  test    esi, esi
0x100830a27  jnz     loc_100830B8D
0x100830a2d  mov     ecx, edx
0x100830a2f  shr     ecx, 1
0x100830a31  cmp     ecx, [rbp+24h]
0x100830a34  cmovbe  ecx, [rbp+24h]
0x100830a38  lea     eax, [rcx+rdx]
0x100830a3b  cmp     eax, edx
0x100830a3d  cmovbe  esi, r8d
0x100830a41  cmova   edx, eax
0x100830a44  cmp     edx, r10d
0x100830a47  jb      short loc_100830A25
0x100830a49  test    esi, esi
0x100830a4b  jnz     loc_100830B8D
0x100830a51  mov     r9d, edx
0x100830a54  mov     r14d, [rbp+20h]
0x100830a58  cmp     r9d, r14d
0x100830a5b  cmovnb  r14d, r9d
0x100830a5f  cmp     r14d, [rbp+18h]
0x100830a63  jbe     loc_100830B40
0x100830a69  lfence
0x100830a6c  xor     esi, esi
0x100830a6e  mov     ecx, r14d
0x100830a71  mov     eax, 8
0x100830a76  mul     rcx
0x100830a79  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100830a80  cmovo   rax, rcx
0x100830a84  mov     [rsp+98h+var_70], 6
0x100830a89  mov     dword ptr [rsp+98h+var_78], 0E1h
0x100830a91  lea     r9, aSqlNtdbmsStore_3; "Sql\\Ntdbms\\storeng\\jsonparser\\inclu"...
0x100830a98  lea     r8d, [rsi+1]
0x100830a9c  mov     rdx, [rbp+28h]
0x100830aa0  mov     rcx, rax
0x100830aa3  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100830aa9  mov     r12, rax
0x100830aac  mov     rdi, rax
0x100830aaf  mov     [rsp+98h+var_48], rax
0x100830ab4  test    rax, rax
0x100830ab7  jnz     short loc_100830ABE
0x100830ab9  lea     esi, [rax+1]
0x100830abc  jmp     short loc_100830B2D
0x100830abe  mov     rdi, [rbp+10h]
0x100830ac2  mov     qword ptr [rbp+10h], 0
0x100830aca  mov     rbx, rdi
0x100830acd  mov     [rsp+98h+var_50], rbx
0x100830ad2  test    rdi, rdi
0x100830ad5  jz      short loc_100830B05
0x100830ad7  mov     r9d, [rbp+1Ch]
0x100830adb  shl     r9, 3; SourceSize
0x100830adf  lea     rdx, ds:0[r14*8]; DestinationSize
0x100830ae7  mov     r8, rdi; Source
0x100830aea  mov     rcx, r12; Destination
0x100830aed  call    memcpy_s
0x100830af2  xor     ebx, ebx
0x100830af4  mov     [rsp+98h+var_50], rbx
0x100830af9  lea     edx, [rbx+8]
0x100830afc  mov     rcx, rdi
0x100830aff  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100830b05  xor     edi, edi
0x100830b07  mov     [rsp+98h+var_48], rdi
0x100830b0c  mov     rcx, [rbp+10h]
0x100830b10  cmp     rcx, r12
0x100830b13  jz      short loc_100830B1B
0x100830b15  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100830b1b  mov     [rbp+10h], r12
0x100830b1f  mov     [rbp+18h], r14d
0x100830b23  mov     rcx, rbx
0x100830b26  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100830b2c  nop
0x100830b2d  mov     rcx, rdi
0x100830b30  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100830b36  test    esi, esi
0x100830b38  jz      short loc_100830B40
0x100830b3a  test    esi, esi
0x100830b3c  jnz     short loc_100830B8D
0x100830b3e  jmp     short loc_100830B61
0x100830b40  mov     ecx, [rbp+1Ch]
0x100830b43  mov     rax, [rbp+10h]
0x100830b47  lea     rcx, [rax+rcx*8]; Destination
0x100830b4b  mov     r9d, 8; SourceSize
0x100830b51  lea     r8, [rsp+98h+var_40]; Source
0x100830b56  mov     edx, r9d; DestinationSize
0x100830b59  call    memcpy_s
0x100830b5e  inc     dword ptr [rbp+1Ch]
0x100830b61  mov     [rsp+98h+arg_18], 0
0x100830b6d  mov     [rsp+98h+var_38], r15
0x100830b72  mov     rcx, [r13+10h]
0x100830b76  lea     rdx, [rsp+98h+var_38]
0x100830b7b  mov     rcx, [rcx+10h]
0x100830b7f  call    ?Add@?$CDynamicBuffer@PEAX@JSONParserLib@@QEAAKAEBQEAX@Z; JSONParserLib::CDynamicBuffer<void *>::Add(void * const &)
0x100830b84  mov     esi, eax
0x100830b86  jmp     short loc_100830B8D
0x100830b88  mov     esi, 3
0x100830b8d  mov     r15, [rsp+98h+arg_18]
0x100830b95  test    r15, r15
0x100830b98  jz      short loc_100830BA7
0x100830b9a  mov     edx, 1; unsigned int
0x100830b9f  mov     rcx, r15; this
0x100830ba2  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x100830ba7  mov     eax, esi
0x100830ba9  lea     r11, [rsp+98h+var_28]
0x100830bae  mov     rbx, [r11+30h]
0x100830bb2  mov     rbp, [r11+38h]
0x100830bb6  mov     rsi, [r11+40h]
0x100830bba  mov     rsp, r11
0x100830bbd  pop     r15
0x100830bbf  pop     r14
0x100830bc1  pop     r13
0x100830bc3  pop     r12
0x100830bc5  pop     rdi
0x100830bc6  retn
```
