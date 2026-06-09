# CspGetContainerInfo

- ea: `0x18002d7f0`
- end: `0x18002db81`
- name: `CspGetContainerInfo`
- size: `913`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x180015a5c`
- `0x180016624`
- `0x1800199b0`
- `0x180024250`

## callees

- `0x180009e76`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002b140`
- `0x18002cda8`
- `0x18002d7f0`
- `0x18002eb6c`
- `0x18002fb68`
- `0x180030378`
- `0x18003c240`
- `0x18003d010`

## string_xrefs

- `0x18002d83c`: `Cached_ContainerInfo`

## pseudocode

```c
__int64 __fastcall CspGetContainerInfo(__int64 a1, unsigned __int8 a2, __int64 a3, __int64 a4)
{
  char *v4; // rsi
  unsigned int CachedCardData; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  _DWORD *v11; // r14
  unsigned int v12; // edi
  __int64 v13; // rax
  int v14; // r9d
  char *v15; // rax
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // edi
  const void *v20; // rdx
  const void *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rax
  void *v24; // rax
  __int64 v25; // rcx
  void *v26; // rax
  unsigned int v28; // [rsp+40h] [rbp-268h] BYREF
  _DWORD *v29; // [rsp+48h] [rbp-260h] BYREF
  unsigned __int16 v30[264]; // [rsp+50h] [rbp-258h] BYREF

  v4 = 0;
  *(_DWORD *)(a4 + 8) = 0;
  *(_DWORD *)(a4 + 24) = 0;
  *(_QWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 32) = 0;
  v29 = 0;
  v28 = 0;
  StringCbPrintfW(v30, 0x104u, L"%s_%02x", L"Cached_ContainerInfo", a2);
  CachedCardData = GetCachedCardData(a1, v30, 2u, 1u, &v29, &v28, 0);
  v11 = v29;
  v12 = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData != 1168 )
      goto LABEL_40;
    v13 = *(_QWORD *)(a1 + 8);
    if ( !v13 )
    {
      v12 = 87;
      WppTraceIndent(v10, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
          v14,
          (__int64)"pCardState->pCardData");
      }
      goto LABEL_40;
    }
    LOBYTE(v9) = a2;
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(v13 + 152))(*(_QWORD *)(a1 + 8), v9, 0, a4);
    if ( v12 )
      goto LABEL_40;
    if ( *(_DWORD *)(a4 + 24) > 0x10000u || *(_DWORD *)(a4 + 8) > 0x10000u )
    {
      v12 = -2147024809;
      goto LABEL_40;
    }
    v15 = (char *)MIDL_user_allocate(*(unsigned int *)(a4 + 24) + 16LL + *(unsigned int *)(a4 + 8));
    v4 = v15;
    if ( !v15 )
    {
      WppTraceIndent(v16, 2u);
      v12 = 8;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v18 = 17;
      goto LABEL_31;
    }
    v19 = *(_DWORD *)(a4 + 24) + *(_DWORD *)(a4 + 8) + 16;
    *(_DWORD *)v15 = *(_DWORD *)a4;
    *((_DWORD *)v15 + 1) = *(_DWORD *)(a4 + 4);
    *((_DWORD *)v15 + 3) = *(_DWORD *)(a4 + 24);
    *((_DWORD *)v15 + 2) = *(_DWORD *)(a4 + 8);
    v20 = *(const void **)(a4 + 32);
    if ( v20 )
      memcpy_0(v15 + 16, v20, *(unsigned int *)(a4 + 24));
    v21 = *(const void **)(a4 + 16);
    if ( v21 )
      memcpy_0(&v4[*(unsigned int *)(a4 + 24) + 16], v21, *(unsigned int *)(a4 + 8));
    v12 = AddCachedCardData(a1, v30, 2u, 1u, v4, v19, 0);
  }
  else
  {
    if ( v28 < 0x10 )
      goto LABEL_23;
    *(_DWORD *)a4 = *v29;
    *(_DWORD *)(a4 + 4) = v11[1];
    v22 = (unsigned int)v11[3];
    *(_DWORD *)(a4 + 24) = v22;
    v23 = (unsigned int)v11[2];
    *(_DWORD *)(a4 + 8) = v23;
    *(_QWORD *)(a4 + 16) = 0;
    *(_QWORD *)(a4 + 32) = 0;
    if ( v22 + v23 + 16 != v28 )
    {
LABEL_23:
      v12 = -2146893820;
      goto LABEL_40;
    }
    if ( (_DWORD)v22 )
    {
      v24 = MIDL_user_allocate((unsigned int)v22);
      *(_QWORD *)(a4 + 32) = v24;
      if ( !v24 )
      {
        WppTraceIndent(v25, 2u);
        v12 = 8;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_40;
        }
        v18 = 14;
LABEL_31:
        WPP_SF_s(v17[2], v18, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
        goto LABEL_40;
      }
      memcpy_0(v24, v11 + 4, *(unsigned int *)(a4 + 24));
    }
    if ( !*(_DWORD *)(a4 + 8) )
      goto LABEL_40;
    v26 = MIDL_user_allocate(*(unsigned int *)(a4 + 8));
    *(_QWORD *)(a4 + 16) = v26;
    if ( v26 )
    {
      memcpy_0(v26, (char *)v11 + *(unsigned int *)(a4 + 24) + 16, *(unsigned int *)(a4 + 8));
      goto LABEL_40;
    }
    WppTraceIndent(0, 2u);
    v12 = 8;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 15;
      goto LABEL_31;
    }
  }
LABEL_40:
  if ( v11 )
    CspFreeH(v11);
  if ( v4 )
    CspFreeH(v4);
  return v12;
}

```

## disassembly

```asm
0x18002d7f0  push    rbx
0x18002d7f2  push    rbp
0x18002d7f3  push    rsi
0x18002d7f4  push    rdi
0x18002d7f5  push    r13
0x18002d7f7  push    r14
0x18002d7f9  push    r15
0x18002d7fb  sub     rsp, 270h
0x18002d802  mov     rax, cs:__security_cookie
0x18002d809  xor     rax, rsp
0x18002d80c  mov     [rsp+2A8h+var_48], rax
0x18002d814  xor     esi, esi
0x18002d816  movzx   r15d, dl
0x18002d81a  mov     [r9+8], esi
0x18002d81e  lea     r8, aS02x; "%s_%02x"
0x18002d825  mov     [r9+18h], esi
0x18002d829  mov     rbx, r9
0x18002d82c  mov     [r9+10h], rsi
0x18002d830  mov     rbp, rcx
0x18002d833  mov     [r9+20h], rsi
0x18002d837  lea     rcx, [rsp+2A8h+var_258]; unsigned __int16 *
0x18002d83c  lea     r9, aCachedContaine_0; "Cached_ContainerInfo"
0x18002d843  mov     [rsp+2A8h+var_260], 0
0x18002d84c  mov     edx, 104h; unsigned __int64
0x18002d851  mov     [rsp+2A8h+var_268], 0
0x18002d859  mov     dword ptr [rsp+2A8h+var_288], r15d
0x18002d85e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d863  lea     rax, [rsp+2A8h+var_268]
0x18002d868  mov     [rsp+2A8h+var_278], rsi
0x18002d86d  mov     [rsp+2A8h+var_280], rax
0x18002d872  lea     r13d, [rsi+2]
0x18002d876  lea     rax, [rsp+2A8h+var_260]
0x18002d87b  mov     r8d, r13d
0x18002d87e  lea     r9d, [rsi+1]
0x18002d882  mov     [rsp+2A8h+var_288], rax
0x18002d887  lea     rdx, [rsp+2A8h+var_258]
0x18002d88c  mov     rcx, rbp
0x18002d88f  call    GetCachedCardData
0x18002d894  mov     r14, [rsp+2A8h+var_260]
0x18002d899  mov     edi, eax
0x18002d89b  test    eax, eax
0x18002d89d  jz      loc_18002DA2B
0x18002d8a3  cmp     eax, 490h
0x18002d8a8  jnz     loc_18002DB43
0x18002d8ae  mov     rax, [rbp+8]
0x18002d8b2  test    rax, rax
0x18002d8b5  jnz     short loc_18002D911
0x18002d8b7  mov     edx, r13d
0x18002d8ba  lea     edi, [rsi+57h]
0x18002d8bd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8c9  lea     rax, WPP_GLOBAL_Control
0x18002d8d0  cmp     rcx, rax
0x18002d8d3  jz      loc_18002DB43
0x18002d8d9  test    byte ptr [rcx+1Ch], 1
0x18002d8dd  jz      loc_18002DB43
0x18002d8e3  cmp     [rcx+19h], r13b
0x18002d8e7  jb      loc_18002DB43
0x18002d8ed  mov     rcx, [rcx+10h]
0x18002d8f1  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002d8f8  lea     edx, [rsi+10h]
0x18002d8fb  mov     [rsp+2A8h+var_288], rax
0x18002d900  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002d907  call    WPP_SF_ss
0x18002d90c  jmp     loc_18002DB43
0x18002d911  mov     rcx, rax
0x18002d914  mov     r9, rbx
0x18002d917  mov     rax, [rax+98h]
0x18002d91e  xor     r8d, r8d
0x18002d921  mov     dl, r15b
0x18002d924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d929  mov     edi, eax
0x18002d92b  test    eax, eax
0x18002d92d  jnz     loc_18002DB43
0x18002d933  mov     eax, 10000h
0x18002d938  cmp     [rbx+18h], eax
0x18002d93b  ja      loc_18002DA21
0x18002d941  cmp     [rbx+8], eax
0x18002d944  ja      loc_18002DA21
0x18002d94a  mov     eax, [rbx+18h]
0x18002d94d  mov     ecx, [rbx+8]
0x18002d950  add     rax, 10h
0x18002d954  add     rcx, rax; size
0x18002d957  call    MIDL_user_allocate
0x18002d95c  mov     rsi, rax
0x18002d95f  test    rax, rax
0x18002d962  jnz     short loc_18002D9A2
0x18002d964  mov     edx, r13d
0x18002d967  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d96c  lea     edi, [rsi+8]
0x18002d96f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d976  lea     rax, WPP_GLOBAL_Control
0x18002d97d  cmp     rcx, rax
0x18002d980  jz      loc_18002DB43
0x18002d986  test    byte ptr [rcx+1Ch], 1
0x18002d98a  jz      loc_18002DB43
0x18002d990  cmp     [rcx+19h], r13b
0x18002d994  jb      loc_18002DB43
0x18002d99a  lea     edx, [rsi+11h]
0x18002d99d  jmp     loc_18002DABD
0x18002d9a2  mov     edi, [rbx+8]
0x18002d9a5  mov     eax, [rbx]
0x18002d9a7  add     edi, 10h
0x18002d9aa  add     edi, [rbx+18h]
0x18002d9ad  mov     [rsi], eax
0x18002d9af  mov     eax, [rbx+4]
0x18002d9b2  mov     [rsi+4], eax
0x18002d9b5  mov     eax, [rbx+18h]
0x18002d9b8  mov     [rsi+0Ch], eax
0x18002d9bb  mov     eax, [rbx+8]
0x18002d9be  mov     [rsi+8], eax
0x18002d9c1  mov     rdx, [rbx+20h]; Src
0x18002d9c5  test    rdx, rdx
0x18002d9c8  jz      short loc_18002D9D7
0x18002d9ca  mov     r8d, [rbx+18h]; Size
0x18002d9ce  lea     rcx, [rsi+10h]; void *
0x18002d9d2  call    memcpy_0
0x18002d9d7  mov     rdx, [rbx+10h]; Src
0x18002d9db  test    rdx, rdx
0x18002d9de  jz      short loc_18002D9F3
0x18002d9e0  mov     ecx, [rbx+18h]
0x18002d9e3  mov     r8d, [rbx+8]; Size
0x18002d9e7  add     rcx, 10h
0x18002d9eb  add     rcx, rsi; void *
0x18002d9ee  call    memcpy_0
0x18002d9f3  mov     dword ptr [rsp+2A8h+var_278], 0
0x18002d9fb  lea     rdx, [rsp+2A8h+var_258]
0x18002da00  mov     dword ptr [rsp+2A8h+var_280], edi
0x18002da04  mov     r9d, 1
0x18002da0a  mov     r8d, r13d
0x18002da0d  mov     [rsp+2A8h+var_288], rsi
0x18002da12  mov     rcx, rbp
0x18002da15  call    AddCachedCardData
0x18002da1a  mov     edi, eax
0x18002da1c  jmp     loc_18002DB43
0x18002da21  mov     edi, 80070057h
0x18002da26  jmp     loc_18002DB43
0x18002da2b  cmp     [rsp+2A8h+var_268], 10h
0x18002da30  jnb     short loc_18002DA3C
0x18002da32  mov     edi, 80090004h
0x18002da37  jmp     loc_18002DB43
0x18002da3c  mov     eax, [r14]
0x18002da3f  mov     [rbx], eax
0x18002da41  mov     eax, [r14+4]
0x18002da45  mov     [rbx+4], eax
0x18002da48  mov     edx, [r14+0Ch]
0x18002da4c  mov     [rbx+18h], edx
0x18002da4f  mov     eax, [r14+8]
0x18002da53  mov     [rbx+8], eax
0x18002da56  mov     [rbx+10h], rsi
0x18002da5a  mov     [rbx+20h], rsi
0x18002da5e  lea     rcx, [rax+10h]
0x18002da62  mov     eax, [rsp+2A8h+var_268]
0x18002da66  add     rcx, rdx
0x18002da69  cmp     rcx, rax
0x18002da6c  jnz     short loc_18002DA32
0x18002da6e  test    edx, edx
0x18002da70  jz      short loc_18002DAE6
0x18002da72  mov     ecx, edx; size
0x18002da74  call    MIDL_user_allocate
0x18002da79  mov     [rbx+20h], rax
0x18002da7d  test    rax, rax
0x18002da80  jnz     short loc_18002DAD6
0x18002da82  mov     edx, r13d
0x18002da85  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002da8a  mov     edi, 8
0x18002da8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da96  lea     rax, WPP_GLOBAL_Control
0x18002da9d  cmp     rcx, rax
0x18002daa0  jz      loc_18002DB43
0x18002daa6  test    byte ptr [rcx+1Ch], 1
0x18002daaa  jz      loc_18002DB43
0x18002dab0  cmp     [rcx+19h], r13b
0x18002dab4  jb      loc_18002DB43
0x18002daba  lea     edx, [rdi+6]
0x18002dabd  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002dac4  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002dacb  mov     rcx, [rcx+10h]
0x18002dacf  call    WPP_SF_s
0x18002dad4  jmp     short loc_18002DB43
0x18002dad6  mov     r8d, [rbx+18h]; Size
0x18002dada  lea     rdx, [r14+10h]; Src
0x18002dade  mov     rcx, rax; void *
0x18002dae1  call    memcpy_0
0x18002dae6  cmp     [rbx+8], esi
0x18002dae9  jz      short loc_18002DB43
0x18002daeb  mov     ecx, [rbx+8]; size
0x18002daee  call    MIDL_user_allocate
0x18002daf3  mov     [rbx+10h], rax
0x18002daf7  mov     rcx, rax; void *
0x18002dafa  test    rax, rax
0x18002dafd  jnz     short loc_18002DB30
0x18002daff  mov     edx, r13d
0x18002db02  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002db07  mov     edi, 8
0x18002db0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db13  lea     rax, WPP_GLOBAL_Control
0x18002db1a  cmp     rcx, rax
0x18002db1d  jz      short loc_18002DB43
0x18002db1f  test    byte ptr [rcx+1Ch], 1
0x18002db23  jz      short loc_18002DB43
0x18002db25  cmp     [rcx+19h], r13b
0x18002db29  jb      short loc_18002DB43
0x18002db2b  lea     edx, [rdi+7]
0x18002db2e  jmp     short loc_18002DABD
0x18002db30  mov     edx, [rbx+18h]
0x18002db33  mov     r8d, [rbx+8]; Size
0x18002db37  add     rdx, 10h
0x18002db3b  add     rdx, r14; Src
0x18002db3e  call    memcpy_0
0x18002db43  test    r14, r14
0x18002db46  jz      short loc_18002DB50
0x18002db48  mov     rcx, r14
0x18002db4b  call    CspFreeH
0x18002db50  test    rsi, rsi
0x18002db53  jz      short loc_18002DB5D
0x18002db55  mov     rcx, rsi
0x18002db58  call    CspFreeH
0x18002db5d  mov     eax, edi
0x18002db5f  mov     rcx, [rsp+2A8h+var_48]
0x18002db67  xor     rcx, rsp; StackCookie
0x18002db6a  call    __security_check_cookie
0x18002db6f  add     rsp, 270h
0x18002db76  pop     r15
0x18002db78  pop     r14
0x18002db7a  pop     r13
0x18002db7c  pop     rdi
0x18002db7d  pop     rsi
0x18002db7e  pop     rbp
0x18002db7f  pop     rbx
0x18002db80  retn
```
