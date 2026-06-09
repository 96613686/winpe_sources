# CspQueryCardCacheForItem

- ea: `0x18002fe08`
- end: `0x180030013`
- name: `CspQueryCardCacheForItem`
- size: `523`
- prototype: `__int64 __fastcall(struct _CARD_CACHE_QUERY_INFO *)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x18002cf2c`
- `0x18002e270`
- `0x18002f4f0`
- `0x1800300a4`
- `0x180030378`
- `0x180030500`

## callees

- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002eb6c`
- `0x18002f64c`
- `0x18002f964`
- `0x18002fe08`
- `0x1800308f4`

## pseudocode

```c
__int64 __fastcall CspQueryCardCacheForItem(struct _CARD_CACHE_QUERY_INFO *a1)
{
  __int64 v2; // rcx
  _DWORD *v3; // rax
  unsigned int CardCacheFile; // edi
  int v5; // r9d
  PVOID v6; // rcx
  BYTE *pbData; // rsi
  BOOL v9; // edx
  struct _CRYPTOAPI_BLOB v10; // [rsp+30h] [rbp-38h] BYREF

  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  v2 = *(_QWORD *)a1;
  v3 = *(_DWORD **)(*(_QWORD *)a1 + 8LL);
  if ( !v3 )
  {
    CardCacheFile = 87;
    WppTraceIndent(v2, 2u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v5,
        (__int64)"pInfo->pCardState->pCardData");
    }
    goto LABEL_36;
  }
  if ( *v3 >= 6u && *(_DWORD *)(v2 + 696) == 3 && *((_DWORD *)a1 + 2) != 1 )
    return 1168;
  if ( *((_DWORD *)a1 + 3) == 1 && !*((_DWORD *)a1 + 137) )
  {
    CardCacheFile = I_CspReadCardCacheFile(
                      (struct _CARD_STATE *)v2,
                      (struct _CARD_CACHE_QUERY_INFO *)((char *)a1 + 540));
    if ( CardCacheFile )
      goto LABEL_36;
    *((_DWORD *)a1 + 137) = 1;
  }
  *((_QWORD *)a1 + 69) = 0;
  v10 = 0;
  CardCacheFile = MyCacheLookupItem(a1, &v10);
  if ( !CardCacheFile )
  {
    pbData = v10.pbData;
    if ( v10.cbData < 0x10
      || (v6 = (PVOID)(*((unsigned int *)v10.pbData + 3) + 16LL), (unsigned __int64)v6 > v10.cbData) )
    {
      CardCacheFile = 24;
LABEL_34:
      if ( pbData )
        CspFreeH(pbData);
      goto LABEL_36;
    }
    if ( *((_DWORD *)a1 + 3) == 1 )
    {
      v9 = 1;
      if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
      {
        v6 = 0;
        v9 = v10.pbData[1] == *((_BYTE *)a1 + 541);
      }
      if ( (*((_BYTE *)a1 + 8) & 2) != 0 )
      {
        v6 = 0;
        if ( *((_WORD *)v10.pbData + 1) != *((_WORD *)a1 + 271) )
          v9 = 0;
      }
      if ( (*((_BYTE *)a1 + 8) & 4) != 0 && *((_WORD *)v10.pbData + 2) != *((_WORD *)a1 + 272) || !v9 )
      {
        *((_DWORD *)a1 + 140) = 1;
        CardCacheFile = MyCacheDeleteItem(a1);
        if ( !CardCacheFile )
          CardCacheFile = 1168;
        goto LABEL_34;
      }
    }
    *((_QWORD *)a1 + 69) = v10.pbData;
  }
LABEL_36:
  WppTraceIndent((__int64)v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardCacheFile);
  }
  return CardCacheFile;
}

```

## disassembly

```asm
0x18002fe08  push    rbx
0x18002fe0a  push    rbp
0x18002fe0b  push    rsi
0x18002fe0c  push    rdi
0x18002fe0d  push    r15
0x18002fe0f  sub     rsp, 40h
0x18002fe13  xor     edx, edx
0x18002fe15  mov     rbx, rcx
0x18002fe18  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002fe1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe24  lea     r15, WPP_GLOBAL_Control
0x18002fe2b  cmp     rcx, r15
0x18002fe2e  jz      short loc_18002FE58
0x18002fe30  test    byte ptr [rcx+1Ch], 2
0x18002fe34  jz      short loc_18002FE58
0x18002fe36  cmp     byte ptr [rcx+19h], 5
0x18002fe3a  jb      short loc_18002FE58
0x18002fe3c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002fe43  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002fe4a  mov     rcx, [rcx+10h]
0x18002fe4e  mov     edx, 10h
0x18002fe53  call    WPP_SF_s
0x18002fe58  mov     rcx, [rbx]; struct _CARD_STATE *
0x18002fe5b  mov     ebp, 1
0x18002fe60  mov     rax, [rcx+8]
0x18002fe64  test    rax, rax
0x18002fe67  jnz     short loc_18002FEBC
0x18002fe69  lea     edx, [rax+2]
0x18002fe6c  lea     edi, [rax+57h]
0x18002fe6f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002fe74  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe7b  cmp     rcx, r15
0x18002fe7e  jz      loc_18002FFC7
0x18002fe84  test    [rcx+1Ch], bpl
0x18002fe88  jz      loc_18002FFC7
0x18002fe8e  cmp     byte ptr [rcx+19h], 2
0x18002fe92  jb      loc_18002FFC7
0x18002fe98  mov     rcx, [rcx+10h]
0x18002fe9c  lea     rax, aPinfoPcardstat; "pInfo->pCardState->pCardData"
0x18002fea3  lea     edx, [rbp+10h]
0x18002fea6  mov     [rsp+68h+var_48], rax
0x18002feab  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002feb2  call    WPP_SF_ss
0x18002feb7  jmp     loc_18002FFC7
0x18002febc  cmp     dword ptr [rax], 6
0x18002febf  jb      short loc_18002FED9
0x18002fec1  cmp     dword ptr [rcx+2B8h], 3
0x18002fec8  jnz     short loc_18002FED9
0x18002feca  cmp     [rbx+8], ebp
0x18002fecd  jz      short loc_18002FED9
0x18002fecf  mov     eax, 490h
0x18002fed4  jmp     loc_180030008
0x18002fed9  cmp     [rbx+0Ch], ebp
0x18002fedc  jnz     short loc_18002FF03
0x18002fede  cmp     dword ptr [rbx+224h], 0
0x18002fee5  jnz     short loc_18002FF03
0x18002fee7  lea     rdx, [rbx+21Ch]; struct _CARD_CACHE_FILE_FORMAT *
0x18002feee  call    ?I_CspReadCardCacheFile@@YAKPEAU_CARD_STATE@@PEAU_CARD_CACHE_FILE_FORMAT@@@Z; I_CspReadCardCacheFile(_CARD_STATE *,_CARD_CACHE_FILE_FORMAT *)
0x18002fef3  mov     edi, eax
0x18002fef5  test    eax, eax
0x18002fef7  jnz     loc_18002FFC7
0x18002fefd  mov     [rbx+224h], ebp
0x18002ff03  xorps   xmm0, xmm0
0x18002ff06  mov     qword ptr [rbx+228h], 0
0x18002ff11  lea     rdx, [rsp+68h+var_38]; struct _CRYPTOAPI_BLOB *
0x18002ff16  mov     rcx, rbx; struct _CARD_CACHE_QUERY_INFO *
0x18002ff19  movups  xmmword ptr [rsp+68h+var_38.cbData], xmm0
0x18002ff1e  call    ?MyCacheLookupItem@@YAKPEAU_CARD_CACHE_QUERY_INFO@@PEAU_CRYPTOAPI_BLOB@@@Z; MyCacheLookupItem(_CARD_CACHE_QUERY_INFO *,_CRYPTOAPI_BLOB *)
0x18002ff23  mov     edi, eax
0x18002ff25  test    eax, eax
0x18002ff27  jnz     loc_18002FFC7
0x18002ff2d  cmp     [rsp+68h+var_38.cbData], 10h
0x18002ff32  mov     rsi, [rsp+68h+var_38.pbData]
0x18002ff37  jb      short loc_18002FFB5
0x18002ff39  mov     ecx, [rsi+0Ch]
0x18002ff3c  mov     eax, [rsp+68h+var_38.cbData]
0x18002ff40  add     rcx, 10h
0x18002ff44  cmp     rcx, rax
0x18002ff47  ja      short loc_18002FFB5
0x18002ff49  cmp     [rbx+0Ch], ebp
0x18002ff4c  jnz     short loc_18002FFAC
0x18002ff4e  mov     edx, ebp
0x18002ff50  test    [rbx+8], bpl
0x18002ff54  jz      short loc_18002FF64
0x18002ff56  mov     al, [rbx+21Dh]
0x18002ff5c  xor     ecx, ecx
0x18002ff5e  cmp     [rsi+1], al
0x18002ff61  cmovnz  edx, ecx
0x18002ff64  test    byte ptr [rbx+8], 2
0x18002ff68  jz      short loc_18002FF7A
0x18002ff6a  movzx   eax, word ptr [rbx+21Eh]
0x18002ff71  xor     ecx, ecx
0x18002ff73  cmp     [rsi+2], ax
0x18002ff77  cmovnz  edx, ecx
0x18002ff7a  test    byte ptr [rbx+8], 4
0x18002ff7e  jz      short loc_18002FF8D
0x18002ff80  movzx   eax, word ptr [rbx+220h]
0x18002ff87  cmp     [rsi+4], ax
0x18002ff8b  jnz     short loc_18002FF91
0x18002ff8d  test    edx, edx
0x18002ff8f  jnz     short loc_18002FFAC
0x18002ff91  mov     rcx, rbx
0x18002ff94  mov     [rbx+230h], ebp
0x18002ff9a  call    MyCacheDeleteItem
0x18002ff9f  mov     edi, eax
0x18002ffa1  test    eax, eax
0x18002ffa3  jnz     short loc_18002FFBA
0x18002ffa5  mov     edi, 490h
0x18002ffaa  jmp     short loc_18002FFBA
0x18002ffac  mov     [rbx+228h], rsi
0x18002ffb3  jmp     short loc_18002FFC7
0x18002ffb5  mov     edi, 18h
0x18002ffba  test    rsi, rsi
0x18002ffbd  jz      short loc_18002FFC7
0x18002ffbf  mov     rcx, rsi
0x18002ffc2  call    CspFreeH
0x18002ffc7  mov     edx, ebp
0x18002ffc9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002ffce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffd5  cmp     rcx, r15
0x18002ffd8  jz      short loc_180030006
0x18002ffda  test    byte ptr [rcx+1Ch], 2
0x18002ffde  jz      short loc_180030006
0x18002ffe0  cmp     byte ptr [rcx+19h], 5
0x18002ffe4  jb      short loc_180030006
0x18002ffe6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002ffed  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002fff4  mov     rcx, [rcx+10h]
0x18002fff8  mov     edx, 12h
0x18002fffd  mov     dword ptr [rsp+68h+var_48], edi
0x180030001  call    WPP_SF_sd
0x180030006  mov     eax, edi
0x180030008  add     rsp, 40h
0x18003000c  pop     r15
0x18003000e  pop     rdi
0x18003000f  pop     rsi
0x180030010  pop     rbp
0x180030011  pop     rbx
0x180030012  retn
```
